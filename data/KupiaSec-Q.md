## [L-01] [_refundGas](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L286) function in `DepositQueue` contract should use `tx.origin` instead of `msg.sender`
If the caller is the contract, the actual gas payer is `tx.origin`, thus the gas should be refunded to `tx.origin`

## [L-02] [_recordGas](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L472) function in `OperatorDelegator` contract should use `tx.origin` instead of `msg.sender`
Same reason as **L-01**

## [L-03] `RenzoOracleL2` should check for negative price returned
https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L54
In `getMintRate` function, it only checks price staleness without negativity. If price is negative, it returns a huge number because it is converted into uint256.

## [L-04] Incorrect total rewards calculation in RestakeManager contract
https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L700
In the code snippet above, the totalRewards adds the ETH balance of EigenLayer pods, this is incorrect because the ETH balance also includes the withdrawn balance of exited operators. It should be `operatorDelegators[i].eigenPod().nonRestakedBalance`

## [L-05] When removing an operator delegator, it should validate if the operator delegator has no assets staked.
Even though this is called by an admin, non validating if operator delegator is completely exit leads to incorrect calculation of TVL

## [L-06] When removing a collateral token, it should validate if the token is not used across all operator delegators
Same reason as **L-05**

## [L-07] Missing zero address check in `initialize` function of `RestakeManager` contract

## [L-08] `sweepERC20` function of `DepositQueue` contract does not fill withdraw buffer
https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Deposits/DepositQueue.sol#L254-L277
The function `DepositQueue.sweepERC20()` use reward tokens only to redeposit to the operator delegators, not to fill buffer.

## [L-09] No token match check in `OperatorDelegator.setTokenStrategy()` function
https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/RestakeManager.sol#L106-L114
There is no check for the `_token` to match the underlying token of the `_strategy` in the `setTokenStrategy()` function. If the strategy of the given token is set incorrectly, then depositting that collateral token will always be reverted.
