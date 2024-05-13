### [L-01] xRenzoBridge, xRenzoDeposit, WithdrawQueue do not call __ReentrancyGuard_init()

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L70
https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L75
https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L64

The `initialize` functions in the xRenzoBridge, xRenzoDeposit, WithdrawQueue contracts miss a call to `__ReentrancyGuard_init()`. Consider adding them.

### [L-02] WithdrawQueue is pausable but pausing it has no effect

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L140
https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L148

The WithdrawQueue can be paused by an admin with the `WITHDRAW_QUEUE_ADMIN` role. However, when `pause` is called, no effect takes place, because the main user-accessible functions `withdraw` and `claim` don't have the `whenNotPaused` modifier. Consider adding `whenNotPaused` to the `withdraw` and/or `claim` functions.

### [L-03] L2 deposits can fail if an EigenPod gets slashed

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L55

The `RenzoOracleL2.getMintRate` function , used by `xRenzoDeposit.deposit` functionality reverts if ezETH price goes below `1e18`, rejecting the oracle price as invalid. This situation is however perfectly admissible to happen because if an eigenpod gets slashed, the TVL can decrease below the ezETH supply, causing the price to go below `1e18` and breaking the L2 deposit functionality.

Consider removing this check, and instead relying on relative updates like done [here](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L337).

### [L-04] Incorrect rounding in calculation for ezETH burn in withdrawal

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L158

The math:
```Solidity
    uint256 redeemAmount = (_currentValueInProtocol * _ezETHBeingBurned) / _existingEzETHSupply;
```
is incorrectly rounding down, that is in the direction of burning less ezETH than the exact amount, therefore slightly favoring the withdrawer and penalizing the other ezETH holders.

Consider rounding this division up instead.

### [L-05] `RestakeManager::calculateTVLs()` consumes a lot of gas and can potentially revert at some point.

https://github.com/3docSec/2024-04-renzo/blob/e445c7c83daf4c2590fc6c3129f9750036faf324/contracts/RestakeManager.sol#L274

`RestakeManager::calculateTVLs()` contains a nested for loop. It loops through all the operator delegators and within each operator delegator loop, there is another loop which loops through all collateral tokens.

At the current number of operator delegators and collateral tokens (5 operator delegators and 3 collateral tokens), it is consuming almost 400k gas which is quite a lot. As more operator delegators and collateral tokens are added, this is likely to lead to excessive gas overhead for deposits. Consider calculating the TVL in another way.

### [L-06] `sweepBatchSize` is not enforced anywhere.

https://github.com/3docSec/2024-04-renzo/blob/e445c7c83daf4c2590fc6c3129f9750036faf324/contracts/Bridge/L2/xRenzoDeposit.sol#L155

`sweepBatchSize` is a state variable that isn't enforced anywhere including the [`sweep()`](https://github.com/3docSec/2024-04-renzo/blob/e445c7c83daf4c2590fc6c3129f9750036faf324/contracts/Bridge/L2/xRenzoDeposit.sol#L414) function, where it supposedly should be enforced.

Consider utilizing the `sweepBatchSize` in the [`sweep()`](https://github.com/3docSec/2024-04-renzo/blob/e445c7c83daf4c2590fc6c3129f9750036faf324/contracts/Bridge/L2/xRenzoDeposit.sol#L414) function.

### [L-07] `ConnextReceiver::xReceive()` should wrap the call to `xRenzoDeposit.updatePrice()` in a try/catch block.

When the admin calls [`xRenzoBridge::sendPrice()`](https://github.com/3docSec/2024-04-renzo/blob/c894bacebace90ebb6356eec568274ac3ca22296/contracts/Bridge/L1/xRenzoBridge.sol#L210) to send the price feed to L2, the continued execution flow in L2 may silently revert (particularly because `xRenzoDeposit.updatePrice()` can revert).

`ConnextReceiver::xReceive()` :
```solidity
    function xReceive(
        bytes32 _transferId,
        uint256,
        address,
        address _originSender,
        uint32 _origin,
        bytes memory _callData
    ) external onlySource(_originSender, _origin) whenNotPaused returns (bytes memory) {
        (uint256 _price, uint256 _timestamp) = abi.decode(_callData, (uint256, uint256));
        xRenzoDeposit.updatePrice(_price, _timestamp);

        emit MessageReceived(_transferId, _origin, _originSender, _price, _timestamp);
    }
```

`xRenzoDeposit.updatePrice()` : 
```solidity

    function updatePrice(uint256 _price, uint256 _timestamp) external override {
        if (msg.sender != receiver) revert InvalidSender(receiver, msg.sender);
        _updatePrice(_price, _timestamp);
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

Consider wrapping the `xRenzoDeposit.updatePrice(_price, _timestamp);` line in a try/catch block.

```solidity
    function xReceive(
        bytes32 _transferId,
        uint256,
        address,
        address _originSender,
        uint32 _origin,
        bytes memory _callData
    ) external onlySource(_originSender, _origin) whenNotPaused returns (bytes memory) {
        (uint256 _price, uint256 _timestamp) = abi.decode(_callData, (uint256, uint256));
------> xRenzoDeposit.updatePrice(_price, _timestamp);

        emit MessageReceived(_transferId, _origin, _originSender, _price, _timestamp);
    }
```

### [L-08] In [`RestakeManager.chooseOperatorDelegatorForDeposit()`](https://github.com/3docSec/2024-04-renzo/blob/c894bacebace90ebb6356eec568274ac3ca22296/contracts/RestakeManager.sol#L362C1-L393C6), allocations adding up to 10,000 are not enforced.

In the function [`RestakeManager.chooseOperatorDelegatorForDeposit()`](https://github.com/3docSec/2024-04-renzo/blob/c894bacebace90ebb6356eec568274ac3ca22296/contracts/RestakeManager.sol#L362C1-L393C6), allocations adding up to 10,000 are not enforced which is error-prone, especially since when onboarding a new operator allocations would need to be modified in the same transaction.

```solidity

    function chooseOperatorDelegatorForDeposit(
        uint256[] memory tvls,
        uint256 totalTVL
    ) public view returns (IOperatorDelegator) {
        .........

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
    }
```

### [L-09] amount of `ezETH` is minted at a different rate from the amount of `TVL` to be increased.

```solidity

    function deposit(
        IERC20 _collateralToken,
        uint256 _amount,
        uint256 _referralId
    ) public nonReentrant notPaused {
        ....................

        // Check the withdraw buffer and fill if below buffer target
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
------> operatorDelegator.deposit(_collateralToken, _amount);

        // Calculate how much ezETH to mint
------> uint256 ezETHToMint = renzoOracle.calculateMintAmount(
            totalTVL,
            collateralTokenValue,
            ezETH.totalSupply()
        );

        // Mint the ezETH
------> ezETH.mint(msg.sender, ezETHToMint);

        .................
    }

```

The amount of collateral which gets deposited to the operator delegator (which is reflected on the total TVL) is not strictly the same as the share of TVL that would be redeemable for the minted `ezETH`. Minor discrepancies can arise due to internal rounding of strategy's shares.

### [L-10] Users may not be able to redeem their bridged L2 xezETH <-> L1 ezETH if there is not enough ezETH liquidity in the lockbox

There can be scenarios where there isn't enough ezETH liquidity in the ezETH lockbox, which would make users bridging their xezETH to ezETH unable to redeem their ezETH.

The total minted supply of xezETH will not be available to be redeemed until `sweep()` is called on each L2. As a result, the xezETH on L2s will most always be larger than the amount redeemable for ezETH in the L1 lockbox.

Consider calling `sweep()` frequently enough.

### [I-01] The WBETHShim and METHShim contracts import ReentrancyGuardUpgradeable but don't use it

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Binance/WBETHShim.sol#L4
https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Mantle/METHShim.sol#L4

Consider removing these imports to save space.

### [I-02] Typo in RenzoOracle:L135

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L135

Consider renaming the `inflationPercentaage` variable to `inflationPercentage`