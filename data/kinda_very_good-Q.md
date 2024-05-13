[L1] if a user deposits less than the current withdrawbuffer, the call will revert 
```
 uint256 bufferToFill = depositQueue.withdrawQueue().getBufferDeficit(
            address(_collateralToken)
        );
        if (bufferToFill > 0) {
            bufferToFill = (_amount <= bufferToFill) ? _amount : bufferToFill;
            // update amount to send to the operator Delegator
            _amount -= bufferToFill;

            // safe Approve for depositQueue
            _collateralToken.safeApprove(address(depositQueue), bufferToFill);

            // fill Withdraw Buffer via depositQueue
            depositQueue.fillERC20withdrawBuffer(address(_collateralToken), bufferToFill);
        }

        // Approve the tokens to the operator delegator
        _collateralToken.safeApprove(address(operatorDelegator), _amount);

        // Call deposit on the operator delegator
        operatorDelegator.deposit(_collateralToken, _amount);
```

this sets the amount to zero if less than or equal the buffer to zero 

```
 function deposit(
        IERC20 token,
        uint256 tokenAmount
    ) external nonReentrant onlyRestakeManager returns (uint256 shares) {
        if (address(tokenStrategyMapping[token]) == address(0x0) || tokenAmount == 0)
            revert InvalidZeroInput();
```
this will cause a revert as the amount is already set to zero 

[L2] Removing an operator delegator on RestakeManager does not reset its allocation or basis points 
```
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
```
only the operator delegator itself is removed 

[L3] a delegator can end up holding more than the allocation it is meant to be holding 
```
 if (operatorDelegators.length == 0) revert NotFound();

        // If there is only one operator delegator, return it
        if (operatorDelegators.length == 1) {
            return operatorDelegators[0];
        }

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

            unchecked {
                ++i;
            }
        }

        // Default to the first operator delegator
        return operatorDelegators[0];
```
when computing it doesnt account for the new increase in tvl and delegator tvl meaning a delegator meant to handle only 5 % but is at 4.9% could push up to 7 ot 8 % will a new deposit 

[L4] There might be disparities between l1 and l2 timestamps when sending feeds to l2 

[L5] OptimismMintableXERC20 should be initialized in the same call it is deployed to avoid frontrun 
```
In OptimismMintableXERC20Factory::deployOptimismMintableXERC20, the contract is deployed but not initialized which cause lead to an initialization frontrun
```