# QA Review

The following are notes I wrote while doing the security review for Renzo

They are separate by topic and include:
- Gas considerations
- Small Refactorings
- Economic Considerations
- Blast Integration specifics
- Invariants

- [QA Review](#qa-review)
- [Operator Delegator Gas Refund Logic Flaws](#operator-delegator-gas-refund-logic-flaws)
  - [Gas Refunds are not possible](#gas-refunds-are-not-possible)
  - [Gas Refunds are gameable](#gas-refunds-are-gameable)
  - [Gas Refunds are flawed for Contracts](#gas-refunds-are-flawed-for-contracts)
- [Deposit Queue](#deposit-queue)
  - [`totalEarned` logic ignores gas refunds](#totalearned-logic-ignores-gas-refunds)
- [BalancerRateProvider](#balancerrateprovider)
- [xRenzoBridge](#xrenzobridge)
- [Economic Considerations](#economic-considerations)
  - [stETH Arbitrage Via Oracle Drift to gain daily rebase from LRTs](#steth-arbitrage-via-oracle-drift-to-gain-daily-rebase-from-lrts)
  - [Withdrawal Implementation will force a discount due to unknown duration risk](#withdrawal-implementation-will-force-a-discount-due-to-unknown-duration-risk)
  - [In case of slashing, xRenzo Bridge can have accounting errors](#in-case-of-slashing-xrenzo-bridge-can-have-accounting-errors)
- [Basic Refactorings](#basic-refactorings)
  - [`withdrawRequestNonce` is unused](#withdrawrequestnonce-is-unused)
- [Blast Integration](#blast-integration)
  - [Missed opportunity to collect gas refunds](#missed-opportunity-to-collect-gas-refunds)
- [Suggested Invariants](#suggested-invariants)
  - [Deposit and Withdrawals should not create an arbitrage opportunity](#deposit-and-withdrawals-should-not-create-an-arbitrage-opportunity)
    - [A withdrawal shouldn't cause a Loss -\> PPFS doesn't decrease at time of withdrawal](#a-withdrawal-shouldnt-cause-a-loss---ppfs-doesnt-decrease-at-time-of-withdrawal)
  - [xERC20 CrossChain Total Supply matches the ezETH in the Lockbox](#xerc20-crosschain-total-supply-matches-the-ezeth-in-the-lockbox)
  - [Arbitrage Doomsday Invariant](#arbitrage-doomsday-invariant)
- [Oracle](#oracle)
  - [Oracle will stop working for new LST that get's slashed](#oracle-will-stop-working-for-new-lst-that-gets-slashed)
  - [Oracle may not update once it goes past min and max](#oracle-may-not-update-once-it-goes-past-min-and-max)


# Operator Delegator Gas Refund Logic Flaws

## Gas Refunds are not possible

We can see `0x0B1981a9Fcc24A445dE15141390d3E46DA0e425c.adminGasSpentInWei(address(0x3b8C27038848592a51384334D8090DD869a816CB))`

As well as the rest of the operatorDelegators

Have almost 1ETH of gas refund tied to their accounts

But there seems to be no way to pay these out

And paying them out would require causing a loss of yield to he rest of the depositors

Which doesn't seem to be accounted for

## Gas Refunds are gameable

Instead of capping the refund to `block.basefee + premium`

The refunds are using `tx.gasprice`, which is directly manipulatable by the eoa performing the calls

## Gas Refunds are flawed for Contracts

Since the logic is as follows:

```solidity
adminGasSpentInWei[tx.origin]
```

# Deposit Queue 

## `totalEarned` logic ignores gas refunds
https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L163-L179

```solidity
    receive() external payable nonReentrant {
        uint256 feeAmount = 0;
        // Take protocol cut of rewards if enabled
        if (feeAddress != address(0x0) && feeBasisPoints > 0) {
            feeAmount = (msg.value * feeBasisPoints) / 10000;
            (bool success, ) = feeAddress.call{ value: feeAmount }("");
            if (!success) revert TransferFailed();

            emit ProtocolFeesPaid(IERC20(address(0x0)), feeAmount, feeAddress);
        }
        // update remaining rewards
        uint256 remainingRewards = msg.value - feeAmount;
        // Check and fill ETH withdraw buffer if required
        _checkAndFillETHWithdrawBuffer(remainingRewards);

        // Add to the total earned
        totalEarned[address(0x0)] = totalEarned[address(0x0)] + remainingRewards; /// @audit THIS IS WRONG DUE TO FEES
```

Since the system pays out gas refunds, and `totalEarned` is ignoring them, it will over-report by a bit

# BalancerRateProvider

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RateProvider/BalancerRateProvider.sol#L29-L41

```solidity
    function getRate() external view returns (uint256) { /// TODO: I feel the TVL math is wrong post-withdrawal, esp post slashing
        // Get the total TVL priced in ETH from restakeManager
        (, , uint256 totalTVL) = restakeManager.calculateTVLs(); /// @audit 100% Arbitrage here due to delay + oracle swings

        // Get the total supply of the ezETH token
        uint256 totalSupply = ezETHToken.totalSupply();

        // Sanity check
        if (totalSupply == 0 || totalTVL == 0) revert InvalidZeroInput();

        // Return the rate
        return (10 ** 18 * totalTVL) / totalSupply; /// @audit this breaks if total supply is below 1e18
    }
```

# xRenzoBridge

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L139-L150

```solidity
    function xReceive(
        bytes32 _transferId,
        uint256 _amount,
        address _asset,
        address _originSender,
        uint32 _origin,
        bytes memory
    ) external nonReentrant returns (bytes memory) {
        // Only allow incoming messages from the Connext contract
        if (msg.sender != address(connext)) { /// @audit TODO: Connext integration unclear
            revert InvalidSender(address(connext), msg.sender);
        }
```


xezETH can be minted and lost by anyone, meaning that the total ezETH in the lockbox can be greater than what is claimable

This doesn't seem to cause issues


# Economic Considerations

## stETH Arbitrage Via Oracle Drift to gain daily rebase from LRTs



- LRTs are repriced up, they will raise by let's say 0.1% as a simple example
- The price is clear and the change will happen
- We deposit early
- All LRTs are underpriced
- The TVL math will be lower by X%

-> NOTE: as long as the oracles used are the exchange rate oracles, this can be performed both for depositing and withdrawing

## Withdrawal Implementation will force a discount due to unknown duration risk

This line shows the logic to queue a withdrawal:

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L236-L237

```solidity
        if (amountToRedeem > getAvailableToWithdraw(_assetOut)) revert NotEnoughWithdrawBuffer();

```

This is strictly first-in first-out

As any new withdrawal queued will reduce `claimReserve`

The problem with this approach is that while the duration of a withdrawal is guaranteed to be `coolDownPeriod`

The time to wait for `getAvailableToWithdraw(_assetOut)` to be increased and the amount by which it will grow, is undefined

This is because:
- People have no way to signal withdrawals in the Smart Contract System (undefine amount to withdraw from Eigenlayer)
- People that do not signal their intentions to withdraw may still elect to do so


## In case of slashing, xRenzo Bridge can have accounting errors

-> Oracle on L2 reports pre-slashing amount
-> Oracle on Mainnet has post-slashing amount
-> xRenzoBridge mints ezETH amount -> That's a higher amount
- Extra tokens are lost and can never be claimed

The extra tokens would be minted but not backed

That said the tokens wouldn't be redeemable


# Basic Refactorings

## `withdrawRequestNonce` is unused

Just use the previous length of the array


# Blast Integration

## Missed opportunity to collect gas refunds

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L30-L47

```solidity
contract LockboxAdapterBlast {
    address immutable blastStandardBridge;
    address immutable registry;

    // ERRORS
    error InvalidRemoteToken(address _remoteToken);
    error AmountLessThanZero();
    error InvalidAddress();

    constructor(address _blastStandardBridge, address _registry) {
        // Sanity check
        if (_blastStandardBridge == address(0) || _registry == address(0)) {
            revert InvalidAddress();
        }

        blastStandardBridge = _blastStandardBridge;
        registry = _registry;
    }
```

See:
https://docs.blast.io/building/guides/gas-fees


Without explicitly enabling gas mode, you will not be able to claim the gas back


# Suggested Invariants

## Deposit and Withdrawals should not create an arbitrage opportunity

### A withdrawal shouldn't cause a Loss -> PPFS doesn't decrease at time of withdrawal

PPFS (Price Per Full Share) reduction would indicate that the Withdrawal Mechanism is leaking value against other user operations, this is the case in the current code

## xERC20 CrossChain Total Supply matches the ezETH in the Lockbox

This invariant is currently safe, however, inaccuracies will cause loss of collateral (inability to withdraw ezETH)
Or may cause insolvency of the Lockbox

## Arbitrage Doomsday Invariant

No single token pair should allow for an immediate arbitrage

By trying various combinations of tokens in and out, you should ensure that no direct arbitrage can be achieved

It's important you consider any direct arbitrage as a potential risk as your system is factually giving away value to the caller


# Oracle

## Oracle will stop working for new LST that get's slashed

While unlikely, it is possible for new LSTs to get slashed below parity, this will cause the oracle to stop working

If you plan on adding a lot more LSTs you may want to allow them to be valued slightly below parity

## Oracle may not update once it goes past min and max

This is a common issue in validating Chainlink Oracles, you should ensure that the value from the aggregator is not at the bound of min, and max