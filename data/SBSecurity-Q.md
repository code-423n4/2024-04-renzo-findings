### Low Risk

| Count | Title |
| --- | --- |
| [L-01] | WithdrawQueue::claim should expect the recipient |
| [L-02] | No way to cancel a withdrawal request |
| [L-03] | Allocation points sum of 100% is not enforced |
| [L-04] | chooseOperatorDelegatorForWithdraw should fetch the TVL |
| [L-05] | WithdrawQueue::claim rebasing tokens can block the last claim temporarily |
| [L-06] | Possible arbitrage due to the long heartbeat of stETH/ETH price feed |
| [L-07] | Inaccuracy of shares between Eigen withdrawal request and claim |

| Total Low Risk Issues | 7 |
| --- | --- |

### Governance Issue

| Count | Title |
| --- | --- |
| [G-01] | Lowering the buffer target will lock funds in WithdrawQueue |
| [G-02] | OperatorDelegator::setTokenStrategy should verify the underlying token |

| Total Governance Risk Issues | 2 |
| --- | --- |

## Low Risks

## [L-01] `WithdrawQueue::claim` should expect recipient

**Issue Description:** 

When user claim their withdraw request it will always sent the tokens to him (msg.sender), consider allowing the user to specify who to receive the tokens.

**Recommendation:**

Add a new property to the `WithdrawRequest` struct:

[WithdrawQueueStorage.sol](https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Withdraw/WithdrawQueueStorage.sol#L17-L23)

```diff
struct WithdrawRequest {
    address collateralToken;
    uint256 withdrawRequestID;
    uint256 amountToRedeem;
    uint256 ezETHLocked;
    uint256 createdAt;
+   address recipient;
}
```

As well as modify the code to use it:
[WithdrawQueue.sol](https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Withdraw/WithdrawQueue.sol)

```diff
- function withdraw(uint256 _amount, address _assetOut) external nonReentrant {
+ function withdraw(uint256 _amount, address _assetOut, address recipient) external nonReentrant {
...MORE CODE
      // add withdraw request for msg.sender
      withdrawRequests[msg.sender].push(
          WithdrawRequest(
              _assetOut,
              withdrawRequestNonce,
              amountToRedeem,
              _amount,
              block.timestamp,
+             recipient
          )
      );
...MORE CODE
  }
```

```diff
function claim(uint256 withdrawRequestIndex) external nonReentrant {
    // check if provided withdrawRequest Index is valid
    if (withdrawRequestIndex >= withdrawRequests[msg.sender].length)
        revert InvalidWithdrawIndex();

    WithdrawRequest memory _withdrawRequest = withdrawRequests[msg.sender][
        withdrawRequestIndex
    ];
    if (block.timestamp - _withdrawRequest.createdAt < coolDownPeriod) revert EarlyClaim();

    // subtract value from claim reserve for claim asset
    claimReserve[_withdrawRequest.collateralToken] -= _withdrawRequest.amountToRedeem;

    // delete the withdraw request
    withdrawRequests[msg.sender][withdrawRequestIndex] = withdrawRequests[msg.sender][
        withdrawRequests[msg.sender].length - 1
    ];
    withdrawRequests[msg.sender].pop();

    // burn ezETH locked for withdraw request
    ezETH.burn(address(this), _withdrawRequest.ezETHLocked);

    // send selected redeem asset to user
    if (_withdrawRequest.collateralToken == IS_NATIVE) {
-       payable(msg.sender).transfer(_withdrawRequest.amountToRedeem);
+       payable(_withdrawRequest.recipient).transfer(_withdrawRequest.amountToRedeem);
    } else {
-       IERC20(_withdrawRequest.collateralToken).transfer(
-           msg.sender,
-           _withdrawRequest.amountToRedeem
-       );
+       IERC20(_withdrawRequest.collateralToken).transfer(_withdrawRequest.recipient, _withdrawRequest.amountToRedeem);
    }
    // emit the event
    emit WithdrawRequestClaimed(_withdrawRequest);
}
```

## [L-02] No way to cancel a withdrawal request

**Issue Description:** 

There is no way for the user who requested a withdrawal to cancel it. Due to various factors, such as unfavorable conditions or increased yield on EigenLayer, user may wish to cancel their withdrawal request and request it later.

**Recommendation:**

Implement a function that allows users to cancel their withdrawal request by deleting their `WithdrawRequest` struct and returning them their `ezETH` back. But this should only be allowed after the withdrawal delay, because if it can be done immediately, other users can be gamed, by sandwich their withdraw request with request/cancel and lower the buffer. Also, if while the user is thinking about claiming or canceling their request, the buffer is refilled, the collateral that was reserved for them must be deposited into the EigenLayer, otherwise the buffer will overflow.

## [L-03] Allocation points sum of 100% is not enforced

**Issue Description:**

When adding new `OperatorDelegator` to `RestakeManager` ([`RestakeManager::addOperatorDelegator`](https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/RestakeManager.sol#L131-L143)) or modifying the allocation points of an existing one ([`RestakeManager::setOperatorDelegatorAllocation`](https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/RestakeManager.sol#L187-L212)) the sum of all allocations is not verified to be equal to 100%. 

Currently it is possible to be both below and above, despite the intentions of the protocol to be **equal to 100% always.** Another intention that we can clearly observe is the whole idea of having an allocation points - to have an balanced distribution across the registered `OperatorDelegator`s.

Functions affected from a potential wrong sum of the allocations are [`chooseOperatorDelegatorForDeposit`](https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/RestakeManager.sol#L362-L393) and [`chooseOperatorDelegatorForWithdraw`](https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/RestakeManager.sol#L400-L447), there is a possibility deposits to enter the wrong delegator and concentrate the TVL of the protocol there.

```solidity
  function chooseOperatorDelegatorForDeposit(
      uint256[] memory tvls,
      uint256 totalTVL
  ) public view returns (IOperatorDelegator) {
...MORE CODE
      // Otherwise, find the operator delegator with TVL below the threshold
      uint256 tvlLength = tvls.length;
      for (uint256 i = 0; i < tvlLength; ) {
          if (
              tvls[i] <
              (operatorDelegatorAllocations[operatorDelegators[i]] * totalTVL) /
                  BASIS_POINTS /
                  BASIS_POINTS
          ) {
              return operatorDelegators[i];
          }
...MORE CODE
  }
```

**Recommendation:**

To fix the issue apply the following modifications to the code:

[RestakeManager.sol](https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/RestakeManager.sol#L131-L157)

```diff
function addOperatorDelegator(
    IOperatorDelegator _newOperatorDelegator,
    uint256 _allocationBasisPoints
) external onlyRestakeManagerAdmin {
+   uint256 sumOfAllocations = 0;
    // Ensure it is not already in the list
    uint256 odLength = operatorDelegators.length;
    for (uint256 i = 0; i < odLength; ) {
    
+   sumOfAllocations += operatorDelegatorAllocations[operatorDelegators[i]];

        if (address(operatorDelegators[i]) == address(_newOperatorDelegator))
            revert AlreadyAdded();
        unchecked {
            ++i;
        }
    }
    
+   if(sumOfAllocations + _allocationBasisPoints != (100 * BASIS_POINTS)) revert Missmatch();

    // Verify a valid allocation
    if (_allocationBasisPoints > (100 * BASIS_POINTS)) revert OverMaxBasisPoints();

    // Add it to the list
    operatorDelegators.push(_newOperatorDelegator);

    emit OperatorDelegatorAdded(_newOperatorDelegator);

    // Set the allocation
    operatorDelegatorAllocations[_newOperatorDelegator] = _allocationBasisPoints;

    emit OperatorDelegatorAllocationUpdated(_newOperatorDelegator, _allocationBasisPoints);
}
```

For already existing ODs new function should be added to modify all the allocation points at once:

```solidity
function setOperatorDelegatorAllocationMulti(
    uint256[] calldata _allocationBasisPoints
) external onlyRestakeManagerAdmin {
    uint256 odLength = operatorDelegators.length;

    if(_allocationBasisPoints.length != odLength) revert();

    uint sumOfAllocations = 0;

    for(uint256 i = 0; i < odLength; ) {
       uint256 allocationPoints = _allocationBasisPoints[i];

       operatorDelegatorAllocations[operatorDelegators[i]] = allocationPoints;
       sumOfAllocations += allocationPoints;
    }

    if(sumOfAllocations != 100 * BASIS_POINTS) revert();
}
```

## [L-04] `chooseOperatorDelegatorForWithdraw` should fetch the TVL

**Issue Description:**

`chooseOperatorDelegatorForWithdraw` relies on providing the accurate data to the following arguments:

- `operatorDelegatorTokenTVLs`
- `operatorDelegatorTVLs`
- `totalTVL`

instead of calculating them inside the function itself. 

This will remove the possibilities when some transactions, for example deposits and withdrawals/claims, execute before `chooseOperatorDelegatorForWithdraw` and the values given as arguments becoming stale.

[RestakeManager.sol](https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/RestakeManager.sol#L400-L406)

```solidity
  function chooseOperatorDelegatorForWithdraw(
      uint256 tokenIndex,
      uint256 ezETHValue,
      uint256[][] memory operatorDelegatorTokenTVLs,
      uint256[] memory operatorDelegatorTVLs,
      uint256 totalTVL
  ) public view returns (IOperatorDelegator) {
```

**Recommendation:**

Apply the following changes to the `chooseOperatorDelegatorForWithdraw` function:

[RestakeManager.sol](https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/RestakeManager.sol#L400-L406)

```diff
function chooseOperatorDelegatorForWithdraw(
    uint256 tokenIndex,
    uint256 ezETHValue,
-   uint256[][] memory operatorDelegatorTokenTVLs,
-   uint256[] memory operatorDelegatorTVLs,
-   uint256 totalTVL
) public view returns (IOperatorDelegator) {

+ (uint256[][] operatorDelegatorTokenTVLs, uint256[] operatorDelegatorTVLs, uint256 totalTVL) = calculateTVLs(); 

...code below remains unmodified
}
```

The drawback of this additions is the increased gas cost, but on the other hand it guarantees values will always to be up-to-date.

## [L-05] `WithdrawQueue::claim` rebasing tokens can block the last claim temporarily

**Issue Description:**

Due to explicitly mentioning that Renzo will support `stETH` (rebasing) token as collateral [here](https://github.com/code-423n4/2024-04-renzo/tree/main?tab=readme-ov-file#general-questions), the following scenario can occur and block the last withdrawal request for at least **24 hours.**

1. User has 10 `ezETH` tokens which he wants to withdraw.
2. `WithdrawQueue::withdraw` is called and these 10 restaking tokens result in 10 `stETH` tokens that he will receive when the delay period passes.
3. In the meantime, all other withdrawals are claimed and there just enough tokens to fulfil this request.
4. Rebasing of `stETH` occurs (once in 24 hours) and the `balanceOf(address(this))` decreases to 9 tokens, whereas `amountToRedeem`, calculated at step 2, remains the same - 10 tokens. 
5. User wants to claim but the transfer will revert due to insufficient funds in the `WithdrawQueue`:

[WithdrawQueue.sol](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L279-L312)

```solidity
function claim(uint256 withdrawRequestIndex) external nonReentrant {
...MORE CODE
 else {
      IERC20(_withdrawRequest.collateralToken).transfer(
          msg.sender,
          _withdrawRequest.amountToRedeem //@audit doesn't apply the rebasing
      );
  }
}
```

**Recommendation:**

Consider using `wstETH` which is the non-rebasing version of the `stETH`. 

> Usage of rebasing tokens has not been a problem so far because Renzo’s withdrawal functionality is not live yet.
>

## [L-06] Possible arbitrage due to the long heartbeat of `stETH/ETH` price feed

**Issue Description:**

Renzo protocol relies on `stETH/ETH` price feed to convert `stETH` when used for deposit, withdrawal, etc. But this price feed has too long heartbeat - **24 hours**, which can open arbitrage opportunities if the price is not updated accurately.

This is the price feed: [stETH/ETH](https://data.chain.link/feeds/ethereum/mainnet/steth-eth)

![Untitled](https://i.imgur.com/I1uy7hg.png)

The 24-hour heartbeat and 0.5% deviation threshold means that price can move up to 0.5% or stay flat for 24 hours before triggering a price update, which is unlikely to be reached, but historically it is not impossible, you can check this graph for example:

![287544459-d64c81e0-0e8a-4fe9-8063-166d9c5d9bcd.png](https://i.imgur.com/9nrNWBT.png)

This allows you to deposit at these times to mint more `ezETH` or withdraw at a better rate.

The same issue was reported here and I used it as a guide - you can check it out as it has many more diagrams and explanations of possible situations.
https://github.com/code-423n4/2023-11-kelp-findings/issues/584

**Recommendation:** 

It's hard to give a proper solution, one of them we also pointed out in our Kelp issue was to use multiple oracles, like this `stETH/USD`, but that will certainly make the system more complex, so can't suggest anything exactly.

## [L-07] Inaccuracy of shares between Eigen withdrawal request and claim

**Issue Description:**

Withdrawals from EigenLayer will not be up to date, because the shares for the given amount are calculated upon request and various price changes may occur until they are claimed.

When a withdrawal is queued, it calculates how many shares to withdraw based on the `underlyingToShare` exchange rate at the time of the request.

[OperatorDelegator.sol#L193-L256](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L193-L256)

```solidity
function queueWithdrawals(
    IERC20[] calldata tokens,
    uint256[] calldata tokenAmounts
) external nonReentrant onlyNativeEthRestakeAdmin returns (bytes32) {
    ..
          if (address(tokenStrategyMapping[tokens[i]]) == address(0))
              revert InvalidZeroInput();

          // set the strategy of the token
          queuedWithdrawalParams[0].strategies[i] = tokenStrategyMapping[tokens[i]];

          // set the equivalent shares for tokenAmount
          queuedWithdrawalParams[0].shares[i] = tokenStrategyMapping[tokens[i]]
              .underlyingToSharesView(tokenAmounts[i]); // <----------- @audit it will convert the tokenAmount to shares at the time of request
                
        ....

        // set withdrawer as this contract address
        queuedWithdrawalParams[0].withdrawer = address(this);

        // track shares of tokens withdraw for TVL
        queuedShares[address(tokens[i])] += queuedWithdrawalParams[0].shares[i];
        unchecked {
            ++i;
        }
    }

    ...
}
```

And then the shares that were saved in `queuedShares` will be withdrawn, but what if the exchange rate changes during the withdrawal delay has passed and be able to call `completeQueuedWithdrawal()`.

 

1. Let's assume that `1 stETH` equals `1 EigenLayer-stETH` and the withdrawal buffer is full, so all deposits will be made to Eigen.
2. Alice deposits `5e18` stETH.
3. After some time, Bob deposits `100e18 stETH` and then requests an immediate withdrawal, and at the time of the request, the amount of his withdrawal shares will be `100e18 EigenLayer-stETH`.
4. Now assume that the value of EigenLayer-stETH increases, meaning that 1 EigenLayer-stETH is now worth more stETH. This is expected behavior as EigenLayer-stETH is similar to an ERC4626 vault and value may increase over time.
5. Let's say `1 EigenLayer-stETH` is now worth `1.1 stETH`.
6. For the initial `100stETH` that bob deposited, now **only 90.9 EigenLayer-stETH** can be exchanged and plus the `5stETH` deposited by Alice gives us a total of `90.9 + 4.54 = 95.44`, but bob's request was for 100.

This would mean that Bob's withdrawal request would not be fulfilled because there were changes in the exchange rate between the request and the claim.

A similar finding was reported here: https://github.com/sherlock-audit/2024-02-rio-network-core-protocol-judging/issues/109

**Recommendation:** 

It is hard to give appropriate solution to this, because this is how EigenLayer shares works, but it can be something to check in `completeQueuedWithdrawal()`, if the initial shares are still the same and if the exchange rate was updated.


## Governance Risks

## [G-01] Lowering the buffer target will lock funds in `WithdrawQueue`

**Issue Description:**

Due to lack of checking if the `WithdrawQueue` balance for the given asset is more than the bufferTarget in `WithdrawQueue::updateWithdrawBufferTarget` the funds will remain in the contract, they will be able to be withdrawn, but there will be a mismatch between the actual balance and the buffer value:

Consider the following scenario:

- `stETH::balanceOf(address(this))` - 100e18
- `withdrawalBufferTarget[stETH]` - 150e18 (can be any number above 100e18)
- Renzo admins decide to lower the buffer, without checking the balance and set it to 80e18 (can be any number below 100e18).

Now those 20e18 are available for withdraw but when someone checks the buffer it will show them 80e18 even if they can withdraw 100e18.
This is because when withdrawing it only checks `getAvailableToWithdraw`.

[WithdrawQueue.sol#L156-L162](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L156-L162)

```solidity
function getAvailableToWithdraw(address _asset) public view returns (uint256) {
    if (_asset != IS_NATIVE) {
        return IERC20(_asset).balanceOf(address(this)) - claimReserve[_asset];
    } else {
        return address(this).balance - claimReserve[_asset];
    }
}
```

**Recommendation:**

Add a check to not allow updating the buffer if the balanceOf in the contract is bigger.

```diff
function updateWithdrawBufferTarget(
    TokenWithdrawBuffer[] calldata _newBufferTarget
) external onlyWithdrawQueueAdmin {
    if (_newBufferTarget.length == 0) revert InvalidZeroInput();
    for (uint256 i = 0; i < _newBufferTarget.length; ) {
        if (_newBufferTarget[i].asset == address(0) || _newBufferTarget[i].bufferAmount == 0)
            revert InvalidZeroInput();
        emit WithdrawBufferTargetUpdated(
            withdrawalBufferTarget[_newBufferTarget[i].asset],
            _newBufferTarget[i].bufferAmount
        );
+       if (IERC20(_newBufferTarget[i].asset).balanceOf(address(this)) > _newBufferTarget[i].bufferAmount) {
+           revert 
+       }
        withdrawalBufferTarget[_newBufferTarget[i].asset] = _newBufferTarget[i].bufferAmount;
        unchecked {
            ++i;
        }
    }
}
```

## [G-02] `OperatorDelegator::setTokenStrategy` should verify the underlying token

**Issue Description:** 

When adding new `EigenLayer` strategy, the `tokenStrategyMapping` mapping is being updated, but there is no validation whether this strategy supports this particular token. If such a mismatch occur all the deposits with non-native tokens will be reverting and this part of the system will experience DoS until strategy token is being updated.

We can see that there is such validation presented in [`OperatorDelegator::setTokenStrategy`](https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Delegation/OperatorDelegator.sol#L106-L114):

```solidity
  function setTokenStrategy(
      IERC20 _token,
      IStrategy _strategy
  ) external nonReentrant onlyOperatorDelegatorAdmin {
      if (address(_token) == address(0x0)) revert InvalidZeroInput();

      tokenStrategyMapping[_token] = _strategy;
      emit TokenStrategyUpdated(_token, _strategy);
  }
```

This is the function that is executed in `EigenLayer` strategy and prevents non-supported tokens from being sent: 

[StrategyBase.sol](https://github.com/Layr-Labs/eigenlayer-contracts/blob/dbfa12128a41341b936f3e8da5d6da58c6233877/src/contracts/strategies/StrategyBase.sol#L171-L173)

```solidity
function _beforeDeposit(IERC20 token, uint256 amount) internal virtual {
    require(token == underlyingToken, "StrategyBase.deposit: Can only deposit underlyingToken");
}
```

**Recommendation:**

In `setTokenStrategy` add the following code to prevent authorised users from assigning strategy to non-supported token:

```diff
function setTokenStrategy(
    IERC20 _token,
    IStrategy _strategy
) external nonReentrant onlyOperatorDelegatorAdmin {
    if (address(_token) == address(0x0)) revert InvalidZeroInput();
    
+   if (_strategy.underlyingToken() != _token) revert TokenNotSupported();
	
    tokenStrategyMapping[_token] = _strategy;
    emit TokenStrategyUpdated(_token, _strategy);
}
```