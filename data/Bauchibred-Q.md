# QA Report for Renzo

## Table of Contents

| Issue ID | Description |
| -------- | ----------- |
| [QA-01](#qa-01-renzo-currently-misses-out-on-blast-yields-and-redirected-rewards-from-the-sequencer) | Renzo currently misses out on Blast yields and redirected rewards from the sequencer |
| [QA-02](#qa-02-balancer-pools-are-going-to-use-the-wrong-rates) | Balancer pools are going to use the wrong rates |
| [QA-03](#qa-03-the-owner-is-allowed-to-set-any-price) | The owner is allowed to set any price |
| [QA-04](#qa-04-push-method-for-withdrawals-is-generally-frowned-upon) | Push method for withdrawals is generally frowned upon |
| [QA-05](#qa-05-collateral-tokens-could-be-over/undervalued-due-to-their-not-so-safe-dependance-on-external-integration-with-chainlink) | Collateral tokens could be over/undervalued due to their not so safe dependance on external integration with Chainlink |
| [QA-06](#qa-06-consider-implementing-a-better-documented-max-fees-applied-to-deposits) | Consider implementing a better documented max fees applied to deposits |
| [QA-07](#qa-07-depositqueue#sweeperc20()-in-some-cases-would-be-non-functional) | `DepositQueue#sweepERC20()` in some cases would be non-functional |
| [QA-08](#qa-08-depositing-protocol-rewards-in-some-instances-might-revert-due-to-an-underflow) | Depositing protocol rewards in some instances might revert due to an underflow |
| [QA-09](#qa-09-funds-could-be-locked-for-some-users-if-collateral-to-withdraw-is-native-eth-token) | Funds could be locked for some users if collateral to withdraw is native ETH token |
| [QA-10](#qa-10-consider-wrapping-all-latestrounddata()-calls-pertaining-collateral-tokens-in-a-try-catch) | Consider wrapping all `latestRoundData()` calls pertaining collateral tokens in a try catch |
| [QA-11](#qa-11-flawed-tvl-calculation-on-collateral-token-removal) | Flawed `TVL` calculation on collateral token removal |
| [QA-12](#qa-12-protocol-should-consider-that-steth-can-be-paused) | Protocol should consider that `stETH` can be paused |
| [QA-13](#qa-13-transfers-currently-might-fail-silently) | Transfers currently might fail silently |
| [QA-14](#qa-14-first-check-if-withdrawrequestindex-==-withdrawrequests[msg.sender].length---1-before-setting-the-storage) | First check if `withdrawRequestIndex` == `withdrawRequests[msg.sender].length - 1` before setting the storage |
| [QA-15](#qa-15-fix-documentation) | Fix documentation |
| [QA-16](#qa-16-tvl-logic-might-be-faulted-when-considering-the-integrational-context-around-it-and-the-withdrawalqueue) | TVL logic might be faulted when considering the integrational context around it and the `withdrawalQueue` |


## QA-01 Renzo currently misses out on Blast yields and redirected rewards from the sequencer

### Proof of Concept

The Renzo protocol overlooks a potential revenue stream on the Blast network, this is because Blast unlike other optimistic L2s redirects sequencer fees and also USDB/WETH yields to deployed contracts on the network.

Also, it's bee hinted in the readMe and during the contest that both the `xERC20` and `OptimismMintableXERC20` would be deployed on Blast, however these contracts lack any configuration whatsoever to claim the rewards.

### Impact

Loss of revenue for the protocol (redirected fees and USDB/WETH yields). _(could be considered leak in value)_.

> This has been submitted as low since it's not been documented that the protocol intends to have access to this, but leaving to the discretion of the judge to upgrade as this submission can be considered as medium.

### Recommendation

Reimplement the current logic of contracts to be deployed on Blast, ensure that the rewards have been set to the claimable mode to access these yield/rewards, more can be read from blast's official [docs](https://docs.blast.io/building/guides/)

## QA-02 Balancer pools are going to use the wrong rates

### Proof of Concept

Take a look at https://github.com/code-423n4/2024-04-renzo/blob/1c7cc4e632564349b204b4b5e5f494c9b0bc631d/contracts/Bridge/L2/xRenzoDeposit.sol#L451-L459

```solidity
    /**
     * @notice  Exposes the price via getRate()
     * @dev     This is required for a balancer pool to get the price of ezETH
     * @return  uint256  .
     */@audit stale rates
    function getRate() external view override returns (uint256) {
        return lastPrice;
    }

```

This function exposes the prices, note that this functionality is required to get the price of ezETH, issue with this is that the function in it's sense actually returns stale rates, this is cause it uses the last returned `lastPrice` instead of querying to get the current price.

### Impact

Note that the rate gotten from `xRenzoDeposit.getRate()` is essentially used in the `ezETH` pricing from the balancer pool, however this would be wrong, which means that the `ezETH` token would be wrongly priced.

> I'd argue this is borderline medium/low and considering this is one of the hinted attack bugs and idea listed in the readMe, judge should upgrade if they see the upside of this bug as a medium.

### Recommended Mitigation Steps

Introduce a view function that queries the contracts necessary state and returns an updated price, something similar to [\_updatePrice()](https://github.com/code-423n4/2024-04-renzo/blob/1c7cc4e632564349b204b4b5e5f494c9b0bc631d/contracts/Bridge/L2/xRenzoDeposit.sol#L330-L360), but this new function shouldn't include any state changes since it's being `view` modified.

## QA-03 The owner is allowed to set any price

### Proof of Concept

Take a look at https://github.com/code-423n4/2024-04-renzo/blob/1c7cc4e632564349b204b4b5e5f494c9b0bc631d/contracts/Bridge/L2/xRenzoDeposit.sol#L315-L360

```solidity

    function updatePriceByOwner(uint256 price) external onlyOwner {
        return _updatePrice(price, block.timestamp);
    }

        function _updatePrice(uint256 _price, uint256 _timestamp) internal {
        // Check for 0
        if (_price == 0) {
            revert InvalidZeroInput();
        }

        // Check for price divergence - more than 10%
        if (
            (_price > lastPrice && (_price - lastPrice) > (lastPrice / 10)) ||
            (_price < lastPrice && (lastPrice - _price) > (lastPrice / 10))
        ) {
            revert InvalidOraclePrice();
        }

        // Do not allow older price timestamps
        if (_timestamp <= lastPriceTimestamp) {
            revert InvalidTimestamp(_timestamp);
        }

        // Do not allow future timestamps
        if (_timestamp > block.timestamp) {
            revert InvalidTimestamp(_timestamp);
        }

        // Update values and emit event
        lastPrice = _price;
        lastPriceTimestamp = _timestamp;

        emit PriceUpdated(_price, _timestamp);
    }


```

This function indicates that the owner is allowed to set any price whatsoever for the token.

> Following COde4rena new QA rules this is very important to mention, as the owner is now allowed to set any price which would affect the amount of tokens users could get minted for their assets

### Impact

Malicious admin could break the minting logic

### Recommended Mitigation Steps

Consider clearly indicating his is possible in the docs and to users

## QA-04 Push method for withdrawals is generally frowned upon

### Proof of Concept

Take a look at how withdrawal requests are being claimed https://github.com/code-423n4/2024-04-renzo/blob/1c7cc4e632564349b204b4b5e5f494c9b0bc631d/contracts/Withdraw/WithdrawQueue.sol#L279-L312

```solidity
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
            payable(msg.sender).transfer(_withdrawRequest.amountToRedeem);
        } else {
            IERC20(_withdrawRequest.collateralToken).transfer(
                msg.sender, //@audit
                _withdrawRequest.amountToRedeem
            );
        }
        // emit the event
        emit WithdrawRequestClaimed(_withdrawRequest);
    }
```

In the `claim` function of the WithdrawQueue contract, we can see that withdrawal assets are transferred to `msg.sender` without allowing users to specify a different recipient. However, if a user gets blacklisted, they cannot claim their withdrawals, effectively locking their funds.

> NB: After finding out that the `wBETH` token is supported by protocol a more deeper analysis on this issue has been submitted under the H/M category, considering the `wBETH` token is infact blacklistable.

### Impact

This method of pushing assets to `msg.sender` and the potential for blacklisting can lead to user funds being indefinitely stuck in the protocol. Users may lose access to their funds if they are unable to claim their withdrawals due to being blacklisted.

### Recommended Mitigation Steps

Consider implementing a pull method for withdrawals, allowing users to specify a recipient address when claiming withdrawals. This would prevent funds from being stuck in the protocol if users are blacklisted.

## QA-05 Collateral tokens could be over/undervalued due to their not so safe dependance on external integration with Chainlink

### Proof of Concept

Using this search command: [https://github.com/search?q=repo%3Acode-423n4%2F2024-04-renzo+latestRoundData+NOT+language%3AMarkdown+NOT+language%3ATypeScript&type=code](https://github.com/search?q=repo%3Acode-423n4%2F2024-04-renzo+latestRoundData+NOT+language%3AMarkdown+NOT+language%3ATypeScript&type=code), we can see that in multiple instances, protocol queries Chainlink's `latestRoundData()` to get the current price, whereas this report is not attempting to show a flaw in the integration for custom oracles like the one to be set for the L2, there is a problem when this is used to price the current LSTs and any other LST that might be added in the future, considering this query is used to get the price of an asset, and this ends up in some cases deciding the amount of `ezETH` to be minted.

That is to say that the pricing logic requires us to query chainlink at the end of the calls, but evidently, we can see that these calls[ lack any check on the in-aggregator built min/max circuits](https://github.com/search?q=repo%3Acode-423n4%2F2024-04-renzo+latestRoundData+NOT+language%3AMarkdown+NOT+language%3ATypeScript&type=code), which would make protocol either overvalue or undervalue the collateral token depending on which boundary is crossed.

A little bit more on the min/max circuits is that, Chainlink price feeds aggregators have an in-built minimum & maximum prices they will return; if during a flash crash, bridge compromise, or depegging event, an asset’s value falls below the price feed’s minimum price, the oracle price feed will continue to report the (now incorrect) minimum price, so an An attacker could:

- Have their some holding of collateral token
- Real price of collateral token dropped very low
- Attacker deposits these tokens to protocol since they would value it at a higher price.
- Protocol then mints `ezETH` to attacker overvaluing the value of the tokens deposited.

### Impact

Borderline medium/low, as this essentially breaks core functionalities, note that one of the attack bug ideas is to consider when the `TVL` logic could be broken and how users could mint `ezETH` on wrong prices.

### Recommended Mitigation Steps

Store the collateral token's min/max checks, reimplement the way the `latestRoundData()` is being queried and have direct access to the price data being returned and check if its at these boundaries and revert or alternatively integrate a fallback oracle and then use the price from this instead.

## QA-06 Consider implementing a better documented max fees applied to deposits

### Proof of Concept

Take a look at https://github.com/code-423n4/2024-04-renzo/blob/1c7cc4e632564349b204b4b5e5f494c9b0bc631d/contracts/Deposits/DepositQueue.sol#L93-L109

```solidity
   function setFeeConfig(
        address _feeAddress,
        uint256 _feeBasisPoints
    ) external onlyRestakeManagerAdmin {
        // Verify address is set if basis points are non-zero
        if (_feeBasisPoints > 0) {
            if (_feeAddress == address(0x0)) revert InvalidZeroInput();
        }

        // Verify basis points are not over 100%
        if (_feeBasisPoints > 10000) revert OverMaxBasisPoints();

        feeAddress = _feeAddress;
        feeBasisPoints = _feeBasisPoints;

        emit FeeConfigUpdated(_feeAddress, _feeBasisPoints);
    }
```

We can see that max allowed fee is actually `100%` where as we can agree that in no case should this fee level be set this high, the possibility still exists and might have end users being a bit suspicious of protocol since there is a possibility to set the fee to `100%`.

### Impact

Untrustful front for users.

> Considering, the new C4 rules on Admin actions, would be key to note this is also a centralization risk front as the fee can just be set to `100%` by the admin.

### Recommended Mitigation Steps

Most renowned protocols in DEFI actually have a hardcoded max stored in their codes and this value ranges around the `20 %`, this way users are sure that in no case would the fee ever be more that `20%`.

## QA-07 `DepositQueue#sweepERC20()` in some cases would be non-functional

### Proof of Concept

Take a look at https://github.com/code-423n4/2024-04-renzo/blob/1c7cc4e632564349b204b4b5e5f494c9b0bc631d/contracts/Deposits/DepositQueue.sol#L254-L277

```solidity
    function sweepERC20(IERC20 token) external onlyERC20RewardsAdmin {
        uint256 balance = IERC20(token).balanceOf(address(this));
        if (balance > 0) {
            uint256 feeAmount = 0;

            // Sweep fees if configured
            if (feeAddress != address(0x0) && feeBasisPoints > 0) {
                feeAmount = (balance * feeBasisPoints) / 10000;
                IERC20(token).safeTransfer(feeAddress, feeAmount);

                emit ProtocolFeesPaid(token, feeAmount, feeAddress);
            }

            // Approve and deposit the rewards
            token.approve(address(restakeManager), balance - feeAmount);
            restakeManager.depositTokenRewardsFromProtocol(token, balance - feeAmount);

            // Add to the total earned
            totalEarned[address(token)] = totalEarned[address(token)] + balance - feeAmount;

            // Emit the rewards event
            emit RewardsDeposited(IERC20(address(token)), balance - feeAmount);
        }
    }
```

This function in short is used for the logic of sending/rescuing any token left in the DepositQueue to the RestakeManager, however the whole logic of the contract is wrapped under an if check, i.e `if (balance > 0)`, however the way the balance is gotten is `uint256 balance = IERC20(token).balanceOf(address(this));`.

Now it'w somewhat a popular logic that not all renowned ERC20 tokens support the `IERC20.balanceOf()` and as such if a token gets sent to the DepositQueue and doesn't support the `IERC20.balanceOf()` any attempt at sweeping this ERC20 would [revert in this line](https://github.com/code-423n4/2024-04-renzo/blob/1c7cc4e632564349b204b4b5e5f494c9b0bc631d/contracts/Deposits/DepositQueue.sol#L255).

### Impact

Protocol's core functionality is somewhat broken, since rescuing these set of tokens would now be impossible, showcasing the exact opposite of the intention behind `sweepERC20()` is being upheld.

### Recommended Mitigation Steps

Consider calling `balanceOf()` on a low level instead

## QA-08 Depositing protocol rewards in some instances might revert due to an underflow

### Proof of Concept

Take a look at https://github.com/code-423n4/2024-04-renzo/blob/1c7cc4e632564349b204b4b5e5f494c9b0bc631d/contracts/Delegation/OperatorDelegator.sol#L501-L524

```solidity
    receive() external payable nonReentrant {
        // check if sender contract is EigenPod. forward full withdrawal eth received
        if (msg.sender == address(eigenPod)) {
            restakeManager.depositQueue().forwardFullWithdrawalETH{ value: msg.value }();
        } else {
            // considered as protocol reward
            uint256 gasRefunded = 0;
            uint256 remainingAmount = msg.value;
            if (adminGasSpentInWei[tx.origin] > 0) {
                gasRefunded = _refundGas();
                // update the remaining amount
                remainingAmount -= gasRefunded;
                // If no funds left, return
                if (remainingAmount == 0) {
                    return;
                }
            }
            // Forward remaining balance to the deposit queue
            address destination = address(restakeManager.depositQueue());
            (bool success, ) = destination.call{ value: remainingAmount }("");
            if (!success) revert TransferFailed();

            emit RewardsForwarded(destination, remainingAmount);
        }
```

We can see that this is used to receive ETH in the `OperatorDelegator.sol` contract, now in the case where the deposit is not coming from `eigenPod` it's been considered as protocol rewards and an attempt is being made to pay of the `adminGasSpentInWei` if the value is positive, issue is that this attempt is not done in a safe way, i.e there is no check whatsoever that the `remainingAmount` is indeed > than the `gasRefunded` which would then cause the subtraction to underflow and then prompt a revert.

### Impact

Protocol rewards would not be deposited.

### Recommended Mitigation Steps

Consider checking if `gasRefunded > remainingAmount` and if yes, then refund only the `remainingAmount` instead.

## QA-09 Funds could be locked for some users if collateral to withdraw is native ETH token

### Proof of Concept

Take a look at https://github.com/code-423n4/2024-04-renzo/blob/1c7cc4e632564349b204b4b5e5f494c9b0bc631d/contracts/Withdraw/WithdrawQueue.sol#L279-L312

```solidity
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
            payable(msg.sender).transfer(_withdrawRequest.amountToRedeem);//@audit using payable.transfer to send eth?
        } else {
            IERC20(_withdrawRequest.collateralToken).transfer(
                msg.sender,
                _withdrawRequest.amountToRedeem
            );
        }
        // emit the event
        emit WithdrawRequestClaimed(_withdrawRequest);
    }
```

As hinted by the @audit tag we can see that there is an implementation of using `payable.transfer()` to send ETH when claiming the withdrawals however this is heavily frowned upon cause it can lead to the locking of funds. The `transfer() `call requires that the recipient is either an EOA account, or is a contract that has a payable callback. For the contract case, the `transfer()` call only provides 2300 gas for the contract to complete its operations. This means the following cases can cause the transfer to fail:

- The contract does not have a payable callback
- The contract’s payable callback spends more than 2300 gas (which is only enough to emit something)
- The contract is called through a proxy which itself uses up the 2300 gas Use OpenZeppelin’s Address.sendValue() instead
  [Reference](https://code4rena.com/reports/2022-07-golom#l02--dont-use-payabletransferpayablesend)

### Impact

Fund's lock up in some cases as the withdrawals can no longer be finalized.

### Recommended Mitigation Steps

Consider not using the `payable.transfer()` and instead send the ether via the `.call()` method.

## QA-10 Consider wrapping all `latestRoundData()` calls pertaining collateral tokens in a try catch

### Proof of Concept

Using this search command: [https://github.com/search?q=repo%3Acode-423n4%2F2024-04-renzo+latestRoundData+NOT+language%3AMarkdown+NOT+language%3ATypeScript&type=code](https://github.com/search?q=repo%3Acode-423n4%2F2024-04-renzo+latestRoundData+NOT+language%3AMarkdown+NOT+language%3ATypeScript&type=code), we can see that in multiple instances, protocol queries Chainlink's `latestRoundData()` to get the current price, whereas this report is not attempting to show a flaw in the integration for custom oracles like the one to be set for the L2, there is a problem when this is used to price the current LSTs and any other LST that might be added in the future, considering this query is used to get the price of an asset, and this ends up in some cases deciding the amount of `ezETH` to be minted.

That is to say that the pricing logic requires us to query chainlink at the end of the calls, but evidently, we can see that these calls[ lack any error handling for the potential failure of `oracle.latestRoundData()`](https://github.com/search?q=repo%3Acode-423n4%2F2024-04-renzo+latestRoundData+NOT+language%3AMarkdown+NOT+language%3ATypeScript&type=code), note that Chainlink pricefeeds could revert due to whatever reason, i.e say maintenance or maybe the Chainlink team decide to change the underlying address. Now this omission of not considering this call failing would lead to systemic issues, since calls to this would now revert halting any action that requires this call to succeed.

### Impact

Borderline medium/low, as this essentially breaks core functionalities like withdrawing/depositing, as during mints or redemption there is an evaluation of the worth of the collateral assets to be deposited which could lead to a complete revert

### Recommended Mitigation Steps

Wrap the `oracle.latestRoundData()` call in a try-catch block, then handle the error (e.g., revert with a specific message or use an alternative pricing method, the latter is a better fix as it ensures the protocol still functions as expected on the fallback oracle.

## QA-11 Flawed `TVL` calculation on collateral token removal

### Proof of Concept

In the `removeCollateralToken` function of the RestakeManager contract, collateral tokens are removed from the `collateralTokens` array without considering balances held by operators or the withdrawal queue. This flawed removal process affects the TVL calculation, leading to inaccurate TVL figures.

> NB: After understanding that this is indeed going to be called during the lifetime of the protocol a more detailed impactful finding has been submitted on how this could lead to loss of funds for users.

### Impact

The flawed TVL calculation can cause various issues across the protocol, such as inaccurate asset pricing, deposit limit enforcement failures, and incorrect operator selection for deposits.

### Recommended Mitigation Steps

Reimagine the collateral token removal logic to ensure that balances held by operators and the withdrawal queue are properly considered before removing a collateral token from the `collateralTokens` array. This will ensure that TVL calculations accurately reflect the protocol's asset holdings.

## QA-12 Protocol should consider that `stETH` can be paused

### Proof of Concept

Protocol integrates `stETH` as one of the core supported collateral tokens, however it's not been documented i any instance to users/developers that the `stETH` token can indeed be paused.

Since `stETH` can be paused, so all transfers and any interactions would revert. Even withdrawal requests will revert.

### Impact

This could lead to sneaky bug windows, but it generally is a bug rooted with an external admin, however protocol should indicate this to integrators as this could as well mean that withdrawal requests can get processed after the documented `7` days, as the attemot is going to meet a revret when the token to be withdrawn is `stETH`

### Recommended Mitigation Steps

Consider heavily documenting this.

## QA-13 Transfers currently might fail silently

### Proof of Concept

Protocol in multiple instances uses the `.call()` method to transfer native assets to their target addresses as can be confirmed by this search command: [https://github.com/search?q=repo%3Acode-423n4%2F2024-04-renzo+.call+NOT+language%3AMarkdown&type=code](https://github.com/search?q=repo%3Acode-423n4%2F2024-04-renzo+.call+NOT+language%3AMarkdown&type=code), however none of these attemopts at transfer include a logic to verify that the addresses are valid, i.e non-zero or atleast have code in them or check the success return value of this call, which would then mean that this call could silently fail, below is a minimalistic POC to prove this bug case

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.21;
import "hardhat/console.sol";
contract test {
constructor() {
bytes memory txData*; (bool success,) = payable(address(0)).call{ value: 0 }(txData*); console.log("success",success);
}
}
```

### Impact

Failed transfers would be assume as not failed.

### Recommended Mitigation Steps

Consider introducing a valid address checker before the transfers are executed.

## QA-14 First check if `withdrawRequestIndex` == `withdrawRequests[msg.sender].length - 1` before setting the storage

### Proof of Concept

Take a look at https://github.com/code-423n4/2024-04-renzo/blob/1c7cc4e632564349b204b4b5e5f494c9b0bc631d/contracts/Withdraw/WithdrawQueue.sol#L292-L297

```solidity
        // delete the withdraw request
        withdrawRequests[msg.sender][withdrawRequestIndex] = withdrawRequests[msg.sender][
            withdrawRequests[msg.sender].length - 1
        ];
        withdrawRequests[msg.sender].pop();

```

This could be made more efficient by first checking if `withdrawRequestIndex` == `withdrawRequests[msg.sender].length - 1` before setting the storage since it's going to get popped anyways.

### Impact

Lack of efficiency in code.

### Recommended Mitigation Steps

Consider applying the check.

## QA-15 Fix documentation

### Proof of Concept

Take a look at this section of the `readMe`: https://github.com/code-423n4/2024-04-renzo/blob/1c7cc4e632564349b204b4b5e5f494c9b0bc631d/README.md#L161-L166

```markdown
To submit a withdraw request:

- Calculate how much ezETH you want to burn in base units (e.g. 5000000000000000 for 0.005 ezETH)
- Call approve() on the ezETH contract to approve the RestakeManager to move your ezETH
- Call startWithdraw() on the RestakeManager with the amount of ezETH you want to burn and which collateral token you would like to get back
```

We can see the steps outlined for a withdrawal, however navigating to the `RestakeManager.sol` contract at https://github.com/code-423n4/2024-04-renzo/blob/1c7cc4e632564349b204b4b5e5f494c9b0bc631d/contracts/RestakeManager.sol we can see that there is no definition whatsoever of a `startWithdraw()` function which then leaves all three parties of users/developers & security researchers confused about this description.

### Impact

Bad code documentation, confused integration.

### Recommended Mitigation Steps

Consider correctly documenting how & what the withdrawal process should entail.

## QA-16 TVL logic might be faulted when considering the integrational context around it and the `withdrawalQueue`

### Proof of Concept

Take a look at https://github.com/code-423n4/2024-04-renzo/blob/1c7cc4e632564349b204b4b5e5f494c9b0bc631d/contracts/RestakeManager.sol#L274-L358

```solidity
    function calculateTVLs() public view returns (uint256[][] memory, uint256[] memory, uint256) {
        uint256[][] memory operatorDelegatorTokenTVLs = new uint256[][](operatorDelegators.length);
        uint256[] memory operatorDelegatorTVLs = new uint256[](operatorDelegators.length);
        uint256 totalTVL = 0;

        // Iterate through the ODs
        uint256 odLength = operatorDelegators.length;

        // flag for withdrawal queue balance set
        bool withdrawQueueTokenBalanceRecorded = false;
        address withdrawQueue = address(depositQueue.withdrawQueue());

        // withdrawalQueue total value
        uint256 totalWithdrawalQueueValue = 0;

        for (uint256 i = 0; i < odLength; ) {
            // Track the TVL for this OD
            uint256 operatorTVL = 0;

            // Track the individual token TVLs for this OD - native ETH will be last item in the array
            uint256[] memory operatorValues = new uint256[](collateralTokens.length + 1);
            operatorDelegatorTokenTVLs[i] = operatorValues;

            // Iterate through the tokens and get the value of each
            uint256 tokenLength = collateralTokens.length;
            for (uint256 j = 0; j < tokenLength; ) {
                // Get the value of this token

                uint256 operatorBalance = operatorDelegators[i].getTokenBalanceFromStrategy(
                    collateralTokens[j]
                );

                // Set the value in the array for this OD
                operatorValues[j] = renzoOracle.lookupTokenValue(
                    collateralTokens[j],
                    operatorBalance
                );

                // Add it to the total TVL for this OD
                operatorTVL += operatorValues[j];

                // record token value of withdraw queue
                if (!withdrawQueueTokenBalanceRecorded) {
                    totalWithdrawalQueueValue += renzoOracle.lookupTokenValue(
                        collateralTokens[i],
                        collateralTokens[j].balanceOf(withdrawQueue)
                    );
                }

                unchecked {
                    ++j;
                }
            }

            // Get the value of native ETH staked for the OD
            uint256 operatorEthBalance = operatorDelegators[i].getStakedETHBalance();

            // Save it to the array for the OD
            operatorValues[operatorValues.length - 1] = operatorEthBalance;

            // Add it to the total TVL for this OD
            operatorTVL += operatorEthBalance;

            // Add it to the total TVL for the protocol
            totalTVL += operatorTVL;

            // Save the TVL for this OD
            operatorDelegatorTVLs[i] = operatorTVL;

            // Set withdrawQueueTokenBalanceRecorded flag to true
            withdrawQueueTokenBalanceRecorded = true;

            unchecked {
                ++i;
            }
        }

        // Get the value of native ETH held in the deposit queue and add it to the total TVL
        totalTVL += address(depositQueue).balance;

        // Add native ETH help in withdraw Queue and totalWithdrawalQueueValue to totalTVL
        totalTVL += (address(withdrawQueue).balance + totalWithdrawalQueueValue);

        return (operatorDelegatorTokenTVLs, operatorDelegatorTVLs, totalTVL);
    }
```

We can see that while calculating the current `TVL` the ETH present in the withdrawal queue is also taken into account, however this logic seems to be flawed, cause any asset that's currently present in the withdrawal queue is due to a withdrawal request that has been passed on and as such the balance should not count in protocol as within the cooldown period these locked ETH would be claimed by the users who passed the request.

### Impact

A somewhat flawed calculation on the current TVL in protocol, submitting as QA, as one can argue this is a feature not a bug, however the attempt at querying the TVL could return inflated amount when heavy withdrawal requests have been queued.

> Keep in mind that this function inherently gets called when there is a need to price the assets to be withdrawn or to get the rate from the BalancerRateProvider, i.e:

- Withdrawal attempts could now returned flawed data for the amount of collateral to send the user due to having an inflated data returned as the `TVL` from `WithdrawQueue.withdraw()`.
- The `BalancerRateProvider.getRate()` is also heavily used across protocol, with implementations in the [xRenzoBridge](https://github.com/code-423n4/2024-04-renzo/blob/1c7cc4e632564349b204b4b5e5f494c9b0bc631d/contracts/Bridge/L1/xRenzoBridge.sol#L214-L215) which would then mean that functionalities that need price to be sent to the CCIP destination via [xRenzoBridge.sendPrice()](https://github.com/code-423n4/2024-04-renzo/blob/1c7cc4e632564349b204b4b5e5f494c9b0bc631d/contracts/Bridge/L1/xRenzoBridge.sol#L210) would all be concluding o potentially faulty price due to using an inflated TVL in the calculation.

### Recommended Mitigation Steps

Consider reimplementing the logic to have the right amount of TVL used in the calculations.
