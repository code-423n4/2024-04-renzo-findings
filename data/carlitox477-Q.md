# Low
## `TimelockController:cancel(bytes32)` can be frontrunned
Given that this trasaction is sent to the mempool, if the operation was not executed yet but can be executed given `block.timestamp > getTimestamp(id)`, the cancel operation can be frontrunned by an executor. To solve this there are two option:
* Simply acknowledge the bug but add in comments that caller of the function must consider this attack vector and use something like flashbots to avoid being front runned.
* Add a new invariant which consider that if `getTimestamp(id) < block.timestamp` the function must be executed, and instead of calling `isOperationPending, call next function

```solidity
    function isOperationPendingAndReady(bytes32 id) public view virtual returns (bool) {
        return getTimestamp(id) > block.timestamp;
    }
```

## `TimelockController._execute(address,uint256,bytes,bytes32,bytes32)` allowing executor to manipulate attached gas enable execution path manipulation in edge scenarios
The gas limit for a pending operation is never specified, this responsability is delegated to the executor. Depending on the target contract, gas used to exevute a transaction can be fully executed. On the other hand, in case of a malicious target contract, the execution of the transaction can be enforced to always revert.

A better approach for this function would be enforcing a gas limit when a transaction is queued.



## `TimelockController._execute(address,uint256,bytes,bytes32,bytes32)` and `TimelockController:executeBatch(address[],uint256[],bytes[],bytes32,bytes32)` lack of `msg.value` validation
`TimelockController._execute(address,uint256,bytes,bytes32,bytes32)` does not check that `msg.value == value`, and `TimelockController:executeBatch(address[],uint256[],bytes[],bytes32,bytes32)` does not check that sum of values is equal to `msg.value`. This enable the executor to use ETH stuck in the contract to execute transactions.

## `RestakeManager::deposit(IERC20,uint256,uint256)` allow draining of user funds for wierd ERC20 implementations

Tokens with behavoiur similar to`cUSDCv3`, for which calling `transfer(recipient, type(uint256).max)` transfer whole user balance instead of attempting to transfer `type(uint256).max` tokens allow to use this function to deposit 0 tokens, but also receive new minted ezETH which can be then  sel in a DEX for profit. It would be better to check the effective balance transfered after calling `_collateralToken.safeTransferFrom(msg.sender, address(this), _amount)` to prevent this vector attack.

## `WithdrawalQueue.withdraw(uint256,address)` lack of slippage protection
ezETH is backed by many assets, it could happen that one of this asset value drops significantly due to slashing or any other reason and the oracle for any reason didn't update its value, for instance due to reaching max/min value in the oracle aggregator. It would be better if users could specify a min amount of tokens to queue when calling this function.

## `RestakeManager.addOperatorDelegator(IOperatorDelegator,uint256)` and `RestakeManager.setOperatorDelegatorAllocation(IOperatorDelegator,uint256)` allows to break allocation basis points invariant
### Lines of code
https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L146
https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L192
https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L378-L382

### Description
`RestakeManager.addOperatorDelegator(IOperatorDelegator,uint256)`and `RestakeManager.setOperatorDelegatorAllocation(IOperatorDelegator,uint256)` allows to break allocation basis points invariant
$$sum_{i = 0}^{operatorDelegators.length} operatorDelegatorAllocations[operatorDelegators[i]] \leq 100 \%$$

According to `BASIS_POINTS` comments: *Basis points used for percentages (100 basis points equals 1%)*. So is expected that sum of all operator delegato allocation pointis never more than 10000 basis points.

While `addOperatorDelegator` and `setOperatorDelegatorAllocation` functions check that none operator delgator can have more than 10000 basis points, they do not check that the sum of all operator delegator allocation points is less/equal than 10000 basis points. As a consequence, first operator delegator in the array can be favored over the others if the sum of them is over 10000 basis points

### Impact
Broken invariant can lead to ignoring operator delegators TVL assignment

### POC
```solidity
    function chooseOperatorDelegatorForDeposit(
        uint256[] memory tvls,
        uint256 totalTVL
    ) public view returns (IOperatorDelegator) {
        // Ensure OperatorDelegator list is not empty
        if (operatorDelegators.length == 0) revert NotFound();

        // If there is only one operator delegator, return it
        if (operatorDelegators.length == 1) {
            return operatorDelegators[0];
        }

        // Otherwise, find the operator delegator with TVL below the threshold
        uint256 tvlLength = tvls.length;
        for (uint256 i = 0; i < tvlLength; ) {
            if (
                // @audit If sum of first and second operator is over 100_00 basis points, only these two will be chosen for new deposits, ignoring the rest
                tvls[i] <
                (operatorDelegatorAllocations[operatorDelegators[i]] * totalTVL) /
                    BASIS_POINTS /
                    BASIS_POINTS
            ) {
                return operatorDelegators[i];
            }

            unchecked {
                ++i;
            }
        }
```

### Recommended mitigation
Track current allocated basis points assigned, and always check that the sum of all operator delegator allocation points is less/equal than 10000 basis points before finalizing the execution of functions`addOperatorDelegator` and `setOperatorDelegatorAllocation`.

# Informational
## `OperatorDelegator::queueWithdrawals`: can do `queuedWithdrawalParams[0].withdrawer = address(this)` outside loop to save gas
This operation is exactly the same in every iteration, consuming more gas than needed

## `RewardHandler.setRewardDestination(address)`: Unnecessary modifier`noReentrant`
There is no risk of reentrancy un this function, so the modifier `noReentrant` is unnecessary.

## `ConnextReceiver.updateCCIPEthChainSelector(uint32)` wrong function name
It should be rennamed to `updateConnextEthChainSelector(uint32)`
