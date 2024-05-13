# QA Report

### Low-01

**xRenzoDeposit.sol _updatePrice 10% divergence check is risky**

The check in the [_updatePrice()](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L337) to check for price divergence of about 10% is risky. Mainly once there is a divergence greater than ten percent, due to volatile market change. The built in oracle then remains broken, leaving the contract dependent on the chainlink oracle. The internal oracle can only resume to function once the price returns to function within the 10% range or with false price updates.

**Mitigation**
Remove the divergence check completely.

### Low-02

**Multiple return values expected to call in XERC20Lockbox.sol**

In [XERC20Lockbox.sol](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L131) the _withdraw function expects more than a single return variable in the line

```
(bool _success, ) = payable(_to).call{ value: _amount }("");
```

**Mitigation**

A single variable success should suffice as call only returns 1 or 0.

### Low-03

**100% fee reduction allowed in DepositQueue.sol**

In [DepositQueue.sol](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L102) the function setFeeConfig allows a 100% reward reduction, which seems too liberal.

**Mitigation**

Cap fee basis at 50%

### Low-04

**Access control discrepancy in RewardHandler.sol**

In [RewardHandler.sol](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Rewards/RewardHandler.sol#L52) there appears to be an access control error. The [forwardRewards()](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Rewards/RewardHandler.sol#L58C14-L58C30) function has a restricted access control modifier which can easily be bypassed by calling the [receive()](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Rewards/RewardHandler.sol#L52) ether function

**Mitigation**

If access control is not needed it should be removed, could save gas for the protocol, however if it is needed and to be taken seriously then the receive function shouldn't allow any user to have the same level of access.

### Low-05

**Withdraw function in WithdrawQueue.sol lacks zero check on TVL**

In [WithdrawQueue.sol](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L217) the total value locked variable returned is not checked if it is equal to zero and a revert is not included. This will cause the EVM to revert on a division by zero call on the next [line()](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L220).

**Mitigation**

Add a custom error and revert if the oracle returns a tvl equal to zero.

### Low-06

**Balance rate provider could return separate values to prevent precision loss**

In [BalancerRateProvider.sol](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RateProvider/BalancerRateProvider.sol#L40C10-L40C52) the getRate function could return both the totalTVL and totalSupply values to prevent precision loss.

**Mitigation**

Have two return variables for getRate() and modify further calculations to prevent precision loss