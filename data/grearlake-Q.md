## 1, Some functions does not record gas used by admin

## Links to affected code
https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Delegation/OperatorDelegator.sol#L432-#L437
https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Delegation/OperatorDelegator.sol#L446-#L452
https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Delegation/OperatorDelegator.sol#L459-#L462

## Vulnerability details
Function `_recordGas()` is used to track amount of gas spent for later redemption from rewards coming from the DWR. But functions `withdrawNonBeaconChainETHBalanceWei()`, `recoverTokens()` and `startDelayedWithdrawUnstakedETH()` are not tracked, lead to less gas that caller can receive than it should

## Mitigration
Add `_recordGas()` to these functions to track gas



## 2, Withdrawers do not earn yield while waiting for a withdrawal

## Links to affected code
https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Withdraw/WithdrawQueue.sol#L206-#L233

## Vulnerability details
When user withdraw, amountToRedeem is calculated below:

    function withdraw(uint256 _amount, address _assetOut) external nonReentrant {
    .  .  .  .  .
        uint256 amountToRedeem = renzoOracle.calculateRedeemAmount(  // <---
            _amount,
            ezETH.totalSupply(),
            totalTVL
        );
During withdrawal period, if there is a reward is distributed for users, withdrawers are not able to earn them, which is not fair, since their token are still locked in the protocol

For mitigrating: amountToRedeem should be calculated when claiming

## 3, Fee are not able to be claimed in `xRenzoDeposit` when aassset is not WETH

## Links to affected code
https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Bridge/L2/xRenzoDeposit.sol#L396-#L406

## Details
As confirmed by owner [link](https://discord.com/channels/810916927919620096/1234957882051657769/1236835533062279188), `xRenzoDeposit` contract support multiple assets
But `_recoverBridgeFee()` only can handle WETH:

    function _recoverBridgeFee() internal {
        uint256 feeCollected = bridgeFeeCollected;
        bridgeFeeCollected = 0;
        // transfer collected fee to bridgeSweeper
        uint256 balanceBefore = address(this).balance;
        IWeth(address(depositToken)).withdraw(feeCollected);  // <---
        feeCollected = address(this).balance - balanceBefore;
        (bool success, ) = payable(msg.sender).call{ value: feeCollected }("");
        if (!success) revert TransferFailed();
        emit SweeperBridgeFeeCollected(msg.sender, feeCollected);
    }
When assets is not WETH, this line `IWeth(address(depositToken)).withdraw(feeCollected);` will revert, lead to `sweep` function become non-functional

## Mitigrating
Update `_recoverBridgeFee()` to support multiple tokens