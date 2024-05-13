
## L-01 The `DepositQueue` contract does not utilize ERC20 reward tokens to replenish buffer.

The `DepositQueue.sweepERC20()` function only uses the collected ERC20 tokens to be redeposited back to the operator delegators, and not to replenish the buffer.

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Deposits/DepositQueue.sol#L254-L277

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
269         restakeManager.depositTokenRewardsFromProtocol(token, balance - feeAmount);

            // Add to the total earned
            totalEarned[address(token)] = totalEarned[address(token)] + balance - feeAmount;

            // Emit the rewards event
            emit RewardsDeposited(IERC20(address(token)), balance - feeAmount);
        }
    }
```

## L-02 The `RestakeManager.removeOperatorDelegator()` function does not include a check for any remaining balance.

The `removeOperatorDelegator()` function does not include a check to verify if the operator delegator still has a remaining balance. If the operator delegator holds any shares in the protocol's strategies, they will be effectively frozen and permanently excluded from the TVL. This freeze will subsequently impact the calculated exchange rate of ezETH, leading to potentially inaccurate actions throughout the entire protocol.

To address this issue, a remaining balance check for the operator delegator should be added.

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/RestakeManager.sol#L160-L184

```solidity
    function removeOperatorDelegator(
        IOperatorDelegator _operatorDelegatorToRemove
    ) external onlyRestakeManagerAdmin {
        // Remove it from the list
        uint256 odLength = operatorDelegators.length;
        for (uint256 i = 0; i < odLength; ) {
            if (address(operatorDelegators[i]) == address(_operatorDelegatorToRemove)) {
                // Clear the allocation
                operatorDelegatorAllocations[_operatorDelegatorToRemove] = 0;
                emit OperatorDelegatorAllocationUpdated(_operatorDelegatorToRemove, 0);

                // Remove from list
                operatorDelegators[i] = operatorDelegators[operatorDelegators.length - 1];
                operatorDelegators.pop();
                emit OperatorDelegatorRemoved(_operatorDelegatorToRemove);
                return;
            }
            unchecked {
                ++i;
            }
        }

        // If the item was not found, throw an error
        revert NotFound();
    }
```

## L-03 The `RestakeManager.removeCollateralToken()` function does not include a check to verify if the token being removed has a remaining balance.

The `removeCollateralToken()` function does not include a check to verify if the collateral token has a remaining balance at this protocol. If there are still that token held in the `WithdrawQueue` contract or within the protocol's strategies, they will effectively be frozen and permanently excluded from the TVL.

This freeze will subsequently impact the calculated exchange rate of ezETH, potentially leading to inaccurate actions being taken across the entire protocol.

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/RestakeManager.sol#L244-L263

```solidity
    function removeCollateralToken(
        IERC20 _collateralTokenToRemove
    ) external onlyRestakeManagerAdmin {
        // Remove it from the list
        uint256 tokenLength = collateralTokens.length;
        for (uint256 i = 0; i < tokenLength; ) {
            if (address(collateralTokens[i]) == address(_collateralTokenToRemove)) {
                collateralTokens[i] = collateralTokens[collateralTokens.length - 1];
                collateralTokens.pop();
                emit CollateralTokenRemoved(_collateralTokenToRemove);
                return;
            }
            unchecked {
                ++i;
            }
        }

        // If the item was not found, throw an error
        revert NotFound();
    }
```

## L-04 The `OperatorDelegator.setTokenStrategy()` function does not include a check to ensure that the token being set matches the underlying token of the strategy.

The `setTokenStrategy()` function does not include a check to verify that the provided `_token` parameter matches the underlying token of the specified `_strategy`. If the strategy associated with a given collateral token is set incorrectly, any subsequent attempts to deposit that collateral token will be reverted.

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/RestakeManager.sol#L106-L114

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

## L-05 The `RewardHandler.forwardRewards()` function appears to be unnecessary and could be removed from the codebase.

The `forwardRewards()` function is intended to process rewards received from validator nodes. This function can only be invoked by the `NativeEthRestakeAdmin` role.

However, any user can achieve the same functionality by directly calling the `receive()` function, without the need to send any Ether. This raises the question of whether the forwardRewards() function is truly necessary.

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Rewards/RewardHandler.sol#L58

```solidity
    function forwardRewards() external nonReentrant onlyNativeEthRestakeAdmin {
        _forwardETH();
    }
```

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Rewards/RewardHandler.sol#L52

```solidity
    receive() external payable nonReentrant {
        _forwardETH();
    }
```

## L-06 No need of the first parameter `recipient` of the function `OperatorDelegator.withdrawNonBeaconChainETHBalanceWei()`.

The first parameter `recipient` of the function `withdrawNonBeaconChainETHBalanceWei()` should always be the `OperatorDelegator` contract itself.

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Delegation/OperatorDelegator.sol#L433

```solidity
    function withdrawNonBeaconChainETHBalanceWei(
433     address recipient,
        uint256 amountToWithdraw
    ) external onlyNativeEthRestakeAdmin {
        eigenPod.withdrawNonBeaconChainETHBalanceWei(recipient, amountToWithdraw);
    }
```

## L-07 The `RestakeManager.initialize()` function does not include a check to ensure that the provided addresses are not the zero address.

The `initialize()` function does not include a check to verify that the `_roleManager` parameter is not the zero address.

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/RestakeManager.sol#L101-L118

## L-08 Improper allocation check in `RestakeManager.chooseOperatorDelegatorForWithdraw()`.

The allocation check is strict. When there is no operatorDelegator that exceeds the allocation, it would be better to choose one that has reached the allocation.

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/RestakeManager.sol#L419-L427

```solidity
            operatorDelegatorTVLs[i] >
            (operatorDelegatorAllocations[operatorDelegators[i]] * totalTVL) /
                BASIS_POINTS /
                BASIS_POINTS &&
```
