## Summary
### Low Risk

|        | Title                                                                                                                                                      |
| ------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------- |
| L-01   | Admin gas fees are not paid from protocol earnings in `DepositQueue`                                                                                       |
| L-02   | `DepositQueue@stakeEthFromQueue` and `DepositQueue@stakeEthFromQueueMulti` do not try to refill the `WithdrawQueue` buffer deficit before staking ETH      |
| L-03   | `RestakeManager@setOperatorDelegatorAllocation` and `RestakeManager@addOperatorDelegator` don't check that the sum of all allocations does not exceed 100% |
| L-04   | User depositing more than the buffer deficit target for the deposited collateral token cannot withdraw their full deposit at once                          |

### Non-Critical

|       | Title                                                                               |
| ----- | ----------------------------------------------------------------------------------- |
| NC-01 | `UserWithdrawStarted` and `UserWithdrawCompleted`are never used in `RestakeManager` |
| NC-02 | `RestakeManager@chooseOperatorDelegatorForWithdraw` is never used                   |

## Low Risks
### L-01 | Admin gas fees are not paid from protocol earnings in `DepositQueue`

**Issue Description:**

In `DepositQueue`, the gas spent by the admin on `stakeEthFromQueue` and `stakeEthFromQueueMulti` operations is refunded at the end of those operations which raises a couple of issues :
* The refund can use whatever ETH is available on the contract not just protocol earnings.
* The refunded amounts are not substracted from protocol earnings.
* The admin will not be refunded in full if there isn't enough balance.

The `DepositQueue` refund should probably follow a logic similar to the `OperatorDelegator` refund where the gas spent on operations is recorded and paid from protocol earnings.

[DepositQueue.sol](https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Deposits/DepositQueue.sol#L283-L289)

```solidity
	function stakeEthFromQueue(
        IOperatorDelegator operatorDelegator,
        bytes calldata pubkey,
        bytes calldata signature,
        bytes32 depositDataRoot
    ) external onlyNativeEthRestakeAdmin {
        uint256 gasBefore = gasleft();
        
        // ...

        // Refund the gas to the Admin address if enough ETH available
        _refundGas(gasBefore);
    }
    
	function stakeEthFromQueueMulti(
        IOperatorDelegator[] calldata operatorDelegators,
        bytes[] calldata pubkeys,
        bytes[] calldata signatures,
        bytes32[] calldata depositDataRoots
    ) external onlyNativeEthRestakeAdmin nonReentrant {
        uint256 gasBefore = gasleft();

		// ...

        // Refund the gas to the Admin address if enough ETH available
        _refundGas(gasBefore);
    }

    function _refundGas(uint256 initialGas) internal {
        uint256 gasUsed = (initialGas - gasleft()) * tx.gasprice;
        uint256 gasRefund = address(this).balance >= gasUsed ? gasUsed : address(this).balance;
        (bool success, ) = payable(msg.sender).call{ value: gasRefund }("");
        if (!success) revert TransferFailed();
        emit GasRefunded(msg.sender, gasRefund);
    }
```

### L-02 | `DepositQueue@stakeEthFromQueue` and `DepositQueue@stakeEthFromQueueMulti` do not try to refill the `WithdrawQueue` buffer deficit before staking ETH 

**Issue Description:**

Both of those operations should probably try to refill the `WithdrawQueue` buffer deficit before staking ETH to prevent situations where an Eigen withdrawal will is needed right after a deposit.

[DepositQueue.sol](https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Deposits/DepositQueue.sol#L187C5-L250)

```solidity
    function stakeEthFromQueue(
        IOperatorDelegator operatorDelegator,
        bytes calldata pubkey,
        bytes calldata signature,
        bytes32 depositDataRoot
    ) external onlyNativeEthRestakeAdmin {
        // ...
        restakeManager.stakeEthInOperatorDelegator{ value: 32 ether }(
            operatorDelegator,
            pubkey,
            signature,
            depositDataRoot
        );
		// ...
    }

    /// @dev Function called by ETH Restake Admin to start the restaking process in Native ETH
    /// Only callable by a permissioned account
    /// Can stake multiple validators with 1 tx
    function stakeEthFromQueueMulti(
        IOperatorDelegator[] calldata operatorDelegators,
        bytes[] calldata pubkeys,
        bytes[] calldata signatures,
        bytes32[] calldata depositDataRoots
    ) external onlyNativeEthRestakeAdmin nonReentrant {
        // ...

        // Iterate through the arrays and stake each one
        uint256 arrayLength = operatorDelegators.length;
        for (uint256 i = 0; i < arrayLength; ) {
            // Send the ETH and the params through to the restake manager
            restakeManager.stakeEthInOperatorDelegator{ value: 32 ether }(
                operatorDelegators[i],
                pubkeys[i],
                signatures[i],
                depositDataRoots[i]
            );

            emit ETHStakedFromQueue(
                operatorDelegators[i],
                pubkeys[i],
                32 ether,
                address(this).balance
            );

            unchecked {
                ++i;
            }
        }

        // ...
    }
```

### L-03 |  `RestakeManager@setOperatorDelegatorAllocation` and `RestakeManager@addOperatorDelegator` don't check that the sum of all allocations does not exceed 100%

**Issue Description:**

Both functions only check that the currently added / updated operator delegator allocation does not exceed 100%.

[RestakeManager.sol](https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/RestakeManager.sol#L131-L157)

```solidity
	function addOperatorDelegator(
        IOperatorDelegator _newOperatorDelegator,
        uint256 _allocationBasisPoints
    ) external onlyRestakeManagerAdmin {
        // ...

        // Verify a valid allocation
        if (_allocationBasisPoints > (100 * BASIS_POINTS)) revert OverMaxBasisPoints();

        // ...
    }

	function setOperatorDelegatorAllocation(
        IOperatorDelegator _operatorDelegator,
        uint256 _allocationBasisPoints
    ) external onlyRestakeManagerAdmin {
        // ...
        if (_allocationBasisPoints > (100 * BASIS_POINTS)) revert OverMaxBasisPoints();

        // ...
    }
```
### L-04 |  User depositing more than the buffer deficit target for the deposited collateral token cannot withdraw their full deposit at once

**Issue Description:**

This mainly stems from the fact that the `WithdrawQueue` balance for an asset is always filled up to that asset buffer deficit target in [RestakeManager@deposit](https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/RestakeManager.sol#L555) and [OperatorDelegator@completeQueueWithdrawal](https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Delegation/OperatorDelegator.sol#L300).

This means that the maximum available amount to withdraw for an asset is the buffer deficit target for that asset (assuming there are no pending withdrawals for that asset, otherwise it will be lower).

For example, if the buffer deficit target for `stETH` is `1 ether` :
* Bob deposits `10 ether` of `stETH`
* `1 ether` of `stETH` is sent to the `WithdrawQueue` and `9 ether` is left on the `DepositQueue`
* So Bob can only withdraw `1 ether` of `stETH` at most each time and wait for the next buffer refill (from other deposits or EigenLayer withdrawals) to initiate another withdrawal.

[WithdrawQueue](https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Withdraw/WithdrawQueue.sol#L156-L162)

```solidity
    function fillERC20WithdrawBuffer(
        address _asset,
        uint256 _amount
    ) external nonReentrant onlyDepositQueue {
        if (_asset == address(0) || _amount == 0) revert InvalidZeroInput();
        IERC20(_asset).safeTransferFrom(msg.sender, address(this), _amount);
        emit ERC20BufferFilled(_asset, _amount);
    }

	function getBufferDeficit(address _asset) public view returns (uint256) {
        uint256 availableToWithdraw = getAvailableToWithdraw(_asset);
        return
            withdrawalBufferTarget[_asset] > availableToWithdraw
                ? withdrawalBufferTarget[_asset] - availableToWithdraw
                : 0;
    }
    
    function getAvailableToWithdraw(address _asset) public view returns (uint256) {
        if (_asset != IS_NATIVE) {
            return IERC20(_asset).balanceOf(address(this)) - claimReserve[_asset];
        } else {
            return address(this).balance - claimReserve[_asset];
        }
    }

	function withdraw(uint256 _amount, address _assetOut) external nonReentrant {
        // ...
        // revert if amount to redeem is greater than withdrawBufferTarget
        if (amountToRedeem > getAvailableToWithdraw(_assetOut)) revert NotEnoughWithdrawBuffer();
		// ...
    }
```

## Non-Critical
### NC-01 | `UserWithdrawStarted` and `UserWithdrawCompleted`are never used in `RestakeManager`

### NC-02 | `RestakeManager@chooseOperatorDelegatorForWithdraw` is never used