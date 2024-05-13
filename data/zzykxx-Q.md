## [1] Malicious operator delegator can manipulayte TVL by unstaking from Eigenlayer

Operators can undelegate shares delegated to them via [DelegationManager::undelegate()](https://github.com/Layr-Labs/eigenlayer-contracts/blob/mainnet/src/contracts/core/DelegationManager.sol#L211) in Eigenlayer. An operator can undelegate all of the shares delegate to him by Renzo `OperatorDelegator(s)`, which will cause an instant drop in the TVL, potentially causing damage.

## [2] Oracles safety mechanisms might brick the system if a big legitimate price swing happens

There are two instances of this:

- [RenzoOracleL2::getMintRate()](https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L54) always reverts if the reported price `ezETH` price is less than 1 ether.
Altought unlikely, it's possible for the price of `ezETH` to drop below 1 ether.
If this happens, prices on L2s won't be able to be reported anymore, and minting of `xezETH` tokens will be bricked.

- [xRenzoDeposit::_updatePrice()](https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Bridge/L2/xRenzoDeposit.sol#L337-L342) always reverts if the reported price change differs by at 10% from the previous one. Altought unlikely, it's possible for the price of `ezETH` to swing 10%. A big slashing event might cause a 10% drop, if this happens prices on L2 will become (and stay) stale until the `ezETH` goes back within a 10% range of the last reported price.

Introduce admin functionality to adjust the oracle contraints instead of using hardcoded values.

## [3] Lack of proper functionality to withdraw router fees from `xRenzoDeposit`

`xRenzoDeposit` [collects router fees](https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Bridge/L2/xRenzoDeposit.sol#L385-L388) and leaves them in the contract in order to be withdrawn later. The system doesn't track the amount of router fees that are being collected and the only way to withdraw them is via [xRenzoDeposit::recoverERC20](https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Bridge/L2/xRenzoDeposit.sol#L489).

Introduce a proper router fees accouting mechanism, and funcionality to withdraw router fees.

## [4] `EnumerableSetUpgradeable` return values are never checked

The openzeppelin `EnumerableSetUpgradeable` library doesn't revert when trying to add an item that already exists to a set, but [returns `false` instead](https://github.com/OpenZeppelin/openzeppelin-contracts-upgradeable/blob/release-v4.9/contracts/utils/structs/EnumerableSetUpgradeable.sol#L65-L75).
The contract `XERC20Factory` uses the library in two instances, both times without ensuring the returned value is `true`:
- When [deploying a XERC20 token](https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L165)
- When [deploying a lockbox](https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L209)

Require the returned value to be `true` and revert if this is not the case.

## [5] `stakeEthFromQueue()` allows to deposit twice in the same validator

[DepositQueue::stakeEthFromQueue()](https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Deposits/DepositQueue.sol#L187) is admin callable function used to take ETH from the `DepositQueue` and deposit them into an `OperatorDelegator`'s validator. The `OperatorDelegator` to deposit to is passed by an admin as an input parameter, but the function never checks if the selected `OperatorDelegator` validator has already been deposited into.

If an `OperatorDelegator` validator gets two deposits, the extra `32 ETH` will be queued as a partial withdrawal by the beacon chain, causing the Renzo protocol to collect the "rewards" fee over it, causing a loss to users.

In [DepositQueue::stakeEthFromQueue()](https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Deposits/DepositQueue.sol#L187) ensure the selected validator has never been deposited into before.

## [6] `approve` used instead of `safeApprove` in `sweepERC20()`

In [DepositQueue::sweepERC20()](https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Deposits/DepositQueue.sol#L268) approvals are given via `approve()`. This might lead to the function reverting in case the asset being transferred is not fully ERC20 compliant.

Use `safeApprove()` instead.

## [7] `RenzoOracle` always uses ~24 hours to ensure a price feed is not expired

The functions:

- [RenzoOracle::lookupTokenValue()](https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Oracle/RenzoOracle.sol#L76)
- [RenzoOracle::lookupTokenAmountFromValue()](https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Oracle/RenzoOracle.sol#L93)

Both reverts if the last price update for the given token was performed more than `MAX_TIME_WINDOW` (24 hours + 60 seconds) seconds before the function execution. Different chainlink price feeds can have different heartbeat updates. For instance a chainlink price feed with an heartbeat of 1 hour should be considered stale after 1 hour passed, instead of 24 hours.

Introduce a mapping that uses the correct heartbeat for each supported chainlink price feed to ensure the price is not stale.

## [8] Adding/removing operator delegators might cause instant TVL increase/decrease

The functions [RestakeManager::addOperatorDelegator()](https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/RestakeManager.sol#L131) and [RestakeManager::removeOperatorDelegator()](https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/RestakeManager.sol#L160C14-L160C37) allow to add and remove operator delegators to Renzo.

Both functions don't ensure that operators added and removed are currently holding no shares. If an operator delegator that is currently holding shares is added, the TVL will instantly increase. If an operator delegator that is currently holding shares is removed, the TVL will instantly decrease.

Both functions should ensure that the operator delegators that are being added/removed should not hold shares. This is especially true for operator delegators being added. Operator delegator being removed might need to be removed no-matter-what for being deemed malicious.

## [9] Adding too many operator delegators and/or collateral tokens could DOS the protocol

A critical component of the protocol is the [TVL calculation](https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/RestakeManager.sol#L274), which is perfomed in multiple instances:

- [RestakeManager::depositETH()](https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/RestakeManager.sol#L594)
- [RestakeManager::deposit()](https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/RestakeManager.sol#L504)
- [RestakeManager::depositTokenRewardsFromProtocol()](https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/RestakeManager.sol#L652)
- [WithdrawQueue::withdraw()](https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Withdraw/WithdrawQueue.sol#L217)
- [BalancerRateProvider::getRate()](https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/RateProvider/BalancerRateProvider.sol)

To perform the calculations, the protocol loops over all of the operator delegators, and for each operator delegator it loops over all of the collateral tokens. Both the amount of collateral tokens and operator delegators that can be added to the protocol is unbounded. This could cause the TVL calculation to run out of gas, DOSing all of the protocol operations.

- In [RestakeManager::addOperatorDelegator()](https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/RestakeManager.sol#L131) revert if too many operator delegators are already in the protocol.
- In [RestakeManager::addCollateralToken()](https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/RestakeManager.sol#L220) revert if too many operator delegators are already being used the protocol.

To understand what the maximum caps should be it's necessary to perform some tests to understand the gas usage of the protocol.

## [10] The sum of operator delegators TVL can be more/less than 100%

[RestakeManager::setOperatorDelegatorAllocation()](https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/RestakeManager.sol#L187) allows to set the percentage of TVL that an operator delegator is expected to manage. The function never ensures the sum of the TVL allocations is 100%:

If the sum of TVLs allocation is not 100% (either higher or lower), the extra TVL will always be allocated to the [first operator in the `operatorDelegators` array](https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/RestakeManager.sol#L391-L392), which is unfavourable to other operator delegators.

Change [RestakeManager::setOperatorDelegatorAllocation()](https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/RestakeManager.sol#L391-L392) into a function that accepts as input an array of `uint256`, which should be the same lenght as the current amount of operator delegators in the protocol. Each value in the array represents the TVL percentage to be allocated to the respective operator delegator. The function should ensure the sum of these values to always be 100%.

## [11] The `ReentrancyGuardUpgradeable` contract is not initialized in `WithdrawQueue`

The function [WithdrawQueue::initialize()](https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Withdraw/WithdrawQueue.sol#L64C14-L64C24) doesn't initialize the `ReentrancyGuardUpgradeable`.

Add the following to the function:

```solidity
__ReentrancyGuard_init();
```

## [12] Submitting two claim requests might lead to unexpected results

Withdrawals requests are tracked via an array, `withdrawRequests`.
The function [WithdrawQueue::claim()](https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Withdraw/WithdrawQueue.sol#L279) accepts as input the position in the array of the withdrawal request to be claimed. When the claim is perfomed the corresponding element in the array is deleted by [swapping it with the last element, and then popping the array](https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Withdraw/WithdrawQueue.sol#L293-L296).

This might lead to unexpected results when two claims are perfomed at about the same time. It's impossible to predict which transaction will be executed first, and once a transaction is executed the elements in the array are swapped around, leading to the second transaction potentially claiming a different withdrawal than the intended one.
