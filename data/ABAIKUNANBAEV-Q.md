## Finding Summary 

| ID | Description | Severity |
| - | - | :-: |
| [L-01](#l-01-avoid-directly-minting-follow-nfts-to-the-profile-owner-in-processblock) | `totalEarned` is not taken into account when calling `forwardFullWithdrawalETH()` | Low |
| [L-02](#l-02-regular-approvals-are-not-used-in-access-controls-in-follownftsol) | Incorrect removal of an element from an array | Low |
| [L-03](#l-03-users-have-no-way-of-revoking-their-signatures-in-lenshub) | ERC20 collateral tokens are not taken into account when calculating `totalTVL` | Low |
| [L-04](#l-04-removing-erc721enumerable-functionality-might-break-composability-with-other-protocols) | Overall allocation percentage is not checked to be 100% | Low |
| [L-05](#l-05-delegated-executor-configs-are-not-cleared-on-transfer) | Incorrect checking when determining an `OperatorDelegator` to withdraw | Low |
| [L-06](#l-06-act-in-actionlibsol-doesnt-check-if-the-target-publication-is-a-mirror) | `TimelockController` has no support of `ERC721TokenReceiver` | Low |
| [L-07](#l-06-act-in-actionlibsol-doesnt-check-if-the-target-publication-is-a-mirror) | Bridge fee taken beforehand may affect slippage | Low |
| [L-08](#l-06-act-in-actionlibsol-doesnt-check-if-the-target-publication-is-a-mirror) | `MAX_TIME_WINDOW` is too huge and doesn't protect from stale prices | Low |



## [L-01] `totalEarned` is not taken into account when calling `forwardFullWithdrawalETH()`

In `DepositQueue` contract, there is a function `forwardFullWithdrawalETH()` that accepts ETH and then used for filling the buffer. This function is called inside of `OperatorDelegator` when the contract receives ETH from EigenPod:

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Delegation/OperatorDelegator.sol#L501-504
```
 receive() external payable nonReentrant {
        // check if sender contract is EigenPod. forward full withdrawal eth received
        if (msg.sender == address(eigenPod)) {
            restakeManager.depositQueue().forwardFullWithdrawalETH{ value: msg.value }();
```

There is a comment that also says:

`Handle ETH sent to this contract - will get forwarded to the deposit queue for restaking as a protocol reward`

As `totalEarned` variable is used for accounting variable for protocol rewards, these rewards should be added as well.

### Recommendation

Add `totalEarned` variable in `forwardFullWithdrawalETH()`

## [L-02] Removal of an element from an array without preserving sequence

In `RestakeManager`, when removing the collateral from an array, it's done this way:

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/RestakeManager.sol#L250-255
```
                // @audit-issue index is incorrectly changed 
                collateralTokens[i] = collateralTokens[collateralTokens.length - 1];
                collateralTokens.pop();
                emit CollateralTokenRemoved(_collateralTokenToRemove);
                return;
```

But when using this method, the sequence is not preserved which is important when dealing with collateral numeration that can confuse users.


### Recommendation

Consider using similar implementation:

```
function deleteItemPreserve(uint _index) public {
        for (uint i = _index; i < arr.length - 1; i++) {
            arr[i] = arr[i + 1];
        }
        arr.pop();
    }

```

## [L-03] ERC20 collateral tokens are not taken into account when calculating `totalTVL`

The calculation of TVLs (and `totalTVL`, in particular) is implemented inside of `RestakeManager` contract:

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/RestakeManager.sol#L338
```
  totalTVL += operatorTVL;
```

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/RestakeManager.sol#L352
```
 totalTVL += address(depositQueue).balance;
```

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/RestakeManager.sol#L355
```
 totalTVL += (address(withdrawQueue).balance + totalWithdrawalQueueValue);
```

However, ERC20 collateral tokens that were arbitrarily sent to `DepositQueue` are locked in that contract until the `onlyERC20RewardsAdmin` calls `sweepERC20()`. So technically they should be accounted for in `totalTVL` as this value can be considered locked.


### Recommendation

Add `totalTVL += collateralTokens[i].balanceOf(depositQueue)`


## [L-04] Overall allocation percentage is not checked to be 100%

`setOperatorDelegatorAllocation` function is used to determine the Operator Delegator's allocation according to the `totalTVL`:

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/RestakeManager.sol#L209
```
 operatorDelegatorAllocations[_operatorDelegator] = _allocationBasisPoints;
```

So when OD is chosen in `chooseOperatorDelegatorForDeposit()`, this check is provided:

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/RestakeManager.sol#L377-384
```
if (
                tvls[i] <
                (operatorDelegatorAllocations[operatorDelegators[i]] * totalTVL) /
                    BASIS_POINTS /
                    BASIS_POINTS
            ) {
                return operatorDelegators[i];
            }
```

Basically it means that the first operator that meets this condition will be chosen for OD to deposit. TVL of an OD should be lower than his allocation multiplied by TVL. The problem is that when setting allocation to a certain OD, it's not checked whether the total percentage of all allocators is equal to 100%. It can lead to a situation where multiple allocators have, for instance, the allocation equal to 50%. 

### Recommendation

Add the check where allocations will be summed up and checked to be equal to 100.

## [L-05] Incorrect checking when determining an `OperatorDelegator` to withdraw 

When choosing the OD to withdraw from, the contract will first try to use the OD with the TVL above the allocation threshold that has the tokens:

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/RestakeManager.sol#L418-427
```
  for (uint256 i = 0; i < odLength; ) {
            if (
                operatorDelegatorTVLs[i] >
                (operatorDelegatorAllocations[operatorDelegators[i]] * totalTVL) /
                    BASIS_POINTS /
                    BASIS_POINTS &&
                operatorDelegatorTokenTVLs[i][tokenIndex] >= ezETHValue
            ) {
                return operatorDelegators[i];
            }

```

The problem is that the first condition is technically not possible and therefore will always fail:

```
 if (
                operatorDelegatorTVLs[i] >
                (operatorDelegatorAllocations[operatorDelegators[i]] * totalTVL)
```

This is because when OD is chosen for deposit, this check is implemented:

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/RestakeManager.sol#L378-381
```
 tvls[i] <
                (operatorDelegatorAllocations[operatorDelegators[i]] * totalTVL) /
                    BASIS_POINTS /
                    BASIS_POINTS
```

So basically the `tvl` can be greater than `OD allocation * totalTVL`

### Recommendation

Change the check in `chooseOperatorDelegatorForWithdraw()`.


## [L-06] `TimelockController` has no support of `ERC721TokenReceiver`

`TimelockController` supports `onERC1155Received()`, `onERC1155BatchReceived()`, `onERC721Received` so it basically supports receiving of ERC721 / ERC1155 tokens. According to the specification:

https://eips.ethereum.org/EIPS/eip-721#specification
```
A wallet/broker/auction application MUST implement the wallet interface if it will accept safe transfers.
```

The problem is that the current implementation of `supportsInterface()` doesn't have `ERC721TokenReceiver` with id of `0x150b7a02`.

Besides from deviation from specification, this also leads to some confusions as users wouldn't know if the contract actually supports receiving of the tokens.

### Recommendation

Add `ERC721TokenReceiver` interface in `supportsInterface()`.


## [L-07] Bridge fee taken beforehand may affect slippage 

Inside of `xRenzoDeposit` contract, deposits are made via `deposit()` and then internal `_deposit()` correspondinly. The problem is that the `bridgeFee` is taken before the swap is happened and not after and it's basically substracted from `amountIn`:

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Bridge/L2/xRenzoDeposit.sol#L227-236
```
    function _deposit(
        uint256 _amountIn,
        uint256 _minOut,
        uint256 _deadline
    ) internal returns (uint256) {
        // calculate bridgeFee for deposit amount
        uint256 bridgeFee = getBridgeFeeShare(_amountIn);
        // subtract from _amountIn and add to bridgeFeeCollected
        _amountIn -= bridgeFee;
        bridgeFeeCollected += bridgeFee;

```

This may lead to a situation where user will have complications calculating `_minOut`.

### Recommendation

Take the bridge fee after the swap has happened and `minOut` condition is satisfied.


## [L-08] `MAX_TIME_WINDOW` is too huge and doesn't protect from stale prices

`RenzoOracleL2` is using `MAX_TIME_WINDOW` variable when dealing with oracle stale prices:

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L13
```
uint256 public constant MAX_TIME_WINDOW = 86400 + 60; // 24 hours + 60 seconds
```

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L52
```
 if (timestamp < block.timestamp - MAX_TIME_WINDOW) revert OraclePriceExpired();
```

It's currently equal to 1 day + 60 seconds which is a huge time for oracle updates. Severe price volatility can happen within an hour and such value can lead to the stale mint rate, for instance.

### Recommendation

Decrease `MAX_TIME_WINDOW` value.