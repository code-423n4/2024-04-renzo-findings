## LOW FINDINGS

| Issue Number | Issue Title |
|---------------|-------------|
| [L-1] | ``block.timestamp - _withdrawRequest.createdAt < coolDownPeriod`` check breaks the intended functionality |
| [L-2] | Timestamp Verification Discrepancies Between ``RenzoOracle`` and ``_deposit()`` Function |
| [L-3] | Risk of Unchecked Oracle Price Anomalies in ``lookupTokenValue()`` function |
| [L-4] | Risk of Suboptimal Delegator Selection Due to First-Match Approach in ``chooseOperatorDelegatorForDeposit()`` |
| [L-5] | Replay Attacks and Stale Authorizations Due to Non-Expiring Signatures |
| [L-6] | Risk of Imbalanced Load Distribution Due to Default Selection Bias ``chooseOperatorDelegatorForDeposit()`` function |
| [L-7] | Unrestricted maximum value in ``coolDownPeriod()`` |
| [L-8] | ``xReceive()`` become DOS when ``RestakeManager`` paused |
| [L-9] | ``sweepBatchSize * bridgeFeeShare) / FEE_BASIS`` For large deposits protocol loss huge value since the fee calculation is fixed for deposit greater than 32ETH |
| [L-10] | Inconsistency in Price Validation Between ``Oracle`` and ``CCIPReceiver`` |
| [L-11] | Untracked ``bridgeRouterFeeBps`` Fees Compromise Protocol Accounting and Result in Losses |
| [L-12] | Misguided Zero-Value Checks for uint256 |
| [L-13] | Division by Zero in calculateRedeemAmount Function for Zero ezETH Supply |
| [L-14] | Wrong Comment in ``setPaused()`` function |
| [L-15] | The ``_allocationBasisPoints `` declaration contradict with actual implementation |
| [L-16] | Lack of check for ``_transferId`` uniqueness in ``xReceive`` function |
| [L-17] | Compromised ``WithdrawQueueAdmin`` Could Set Excessive ``coolDownPeriod`` |
| [L-18] | Lack of Clarity in ``MAX_TIME_WINDOW`` Definition Extending to ``24 Hours and 60 Seconds`` in ``RenzoOracle`` |
| [L-19] | Allowing ``withdraw()`` and ``claim()`` when contract paused poses unintended consequences |
| [L-20] | Restrictive Cross-Chain Token Address Validation |
| [L-21] | ``bridgeTo`` function vulnerable to reentrancy attacks |
| [L-22] | Immutable Delegate Address Elevates Security Risk |
| [L-23] | Fund Immobilization Risk Due to Null Strategy Address |
| [L-24] |Automatic ETH Processing and Fee Deduction Without SenderVerification |
| [L-25] | Vulnerability to Excessive Gas Cost Refunds Potentially Draining Contract Funds |

##

## [L-1] ``block.timestamp - _withdrawRequest.createdAt < coolDownPeriod`` check breaks the intended functionality

The problem arises because the code allows a claim to be processed the exact moment the ``coolDownPeriod`` equals the time difference between the current time and the request creation time. Claims to be permitted only after the entire ``coolDownPeriod`` has fully elapsed. Current check ``block.timestamp - _withdrawRequest.createdAt < coolDownPeriod`` intented functionality. This will allow claims even the coolDownPeriod not fully elapsed .


```solidity
FILE: 2024-04-renzo/contracts/Withdraw/WithdrawQueue.sol

287: if (block.timestamp - _withdrawRequest.createdAt < coolDownPeriod) revert EarlyClaim();

```

### Recommended Mitigation

```solidity

287: if (block.timestamp - _withdrawRequest.createdAt <= coolDownPeriod) revert EarlyClaim();

```


##

## [L-2] Timestamp Verification Discrepancies Between ``RenzoOracle`` and ``_deposit()`` Function

The issue arises from a mismatch in staleness thresholds: the RenzoOracle uses a staleness check of "1 day + 60 seconds," whereas the _deposit function uses exactly "1 day." This inconsistency in timestamp verification can lead to contradictory behaviors between the two components. 

```solidity
FILE: 2024-04-renzo/contracts/Oracle
/RenzoOracle.sol

 /// @dev The maxmimum staleness allowed for a price feed from chainlink
26:  uint256 constant MAX_TIME_WINDOW = 86400 + 60; // 24 hours + 60 seconds

76: if (timestamp < block.timestamp - MAX_TIME_WINDOW) revert OraclePriceExpired();

```
https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L76

```solidity 
FILE: 2024-04-renzo/contracts/Bridge/L2/xRenzoDeposit.sol

52: if (block.timestamp > _lastPriceTimestamp + 1 days) {

```
https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L248

##

## [L-3] Risk of Unchecked Oracle Price Anomalies in ``lookupTokenValue()`` function

Oracles serve as bridges between external data sources and the blockchain. However, the integrity of the data they provide can be compromised by errors in data feeds, manipulation by attackers, or even technical malfunctions.

### Impact

- Sudden, unrealistic spikes or drops in price data can occur, which do not accurately reflect market conditions.

- If an attacker can influence the oracle, either directly by tampering with the data source or indirectly through market manipulation, they might feed incorrect prices to the smart contract.

```solidity
FILE: 2024-04-renzo/contracts/Oracle/RenzoOracle.sol

 /// @dev Given a single token and balance, return value of the asset in underlying currency
    /// The value returned will be denominated in the decimal precision of the lookup oracle
    /// (e.g. a value of 100 would return as 100 * 10^18)
    function lookupTokenValue(IERC20 _token, uint256 _balance) public view returns (uint256) {
        AggregatorV3Interface oracle = tokenOracleLookup[_token];
        if (address(oracle) == address(0x0)) revert OracleNotFound();

        (, int256 price, , uint256 timestamp, ) = oracle.latestRoundData();
        if (timestamp < block.timestamp - MAX_TIME_WINDOW) revert OraclePriceExpired();
        if (price <= 0) revert InvalidOraclePrice();

        // Price is times 10**18 ensure value amount is scaled
        return (uint256(price) * _balance) / SCALE_FACTOR;
    }

```
https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L68-L81

##

## [L-4] Risk of Suboptimal Delegator Selection Due to First-Match Approach in ``chooseOperatorDelegatorForDeposit()`` 

Multiple delegators have TVLs (Total Value Locked) below their respective thresholds, the function chooseOperatorDelegatorForDeposit will select and return the first delegator that meets this condition as it iterates through the list of delegators. This means that the function does not compare all delegators to find the one with the lowest TVL relative to their threshold but rather returns the first one it encounters that fits the criteria.

### Impact 
The first-match approach may inadvertently favor certain delegators that are consistently earlier in the list. This could introduce a ``bias in selection``, disadvantaging other ``delegators`` . Without considering the full context of each delegator’s current load and capabilities, there's a risk of creating imbalances where some delegators are overwhelmed while others are underutilized. This can lead to inefficiencies and increased wear on certain parts of the system.

```solidity
FILE: 2024-04-renzo/contracts/RestakeManager.sol

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

```
https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L375-L384

### Recommended Mitigation
Modify the selection algorithm to assess all delegators, calculating and comparing the difference between their current TVL and the threshold, and selecting the one with the greatest difference.

##

## [L-5] Replay Attacks and Stale Authorizations Due to Non-Expiring Signatures

Suppose a signature used in the transaction does not include an expiry time. This omission can make it vulnerable to replay attacks where the same transaction (signature) could be submitted repeatedly, potentially leading to unauthorized staking of ETH.

If the signature does not expire, it could be used long after the user’s intentions have changed. For example, a user might initially authorize a staking transaction but later, due to changing market conditions or personal preferences, wish to retract this authorization.

### Impact

- The repeated staking can cause financial discrepancies, allocate resources improperly, or disrupt the intended distribution and management of staked assets.

- The smart contract would still process the transaction based on the old, now potentially unwanted, authorization, leading to mismanagement of user funds or assets against their current wishes.

```solidity
FILE: 2024-04-renzo/contracts/RestakeManager.sol

/// @dev Called by the deposit queue to stake ETH to a validator
    /// Only callable by the deposit queue
    function stakeEthInOperatorDelegator(
        IOperatorDelegator operatorDelegator,
        bytes calldata pubkey,
        bytes calldata signature,
        bytes32 depositDataRoot
    ) external payable onlyDepositQueue {
        // Verify the OD is in the list
        bool found = false;
        uint256 odLength = operatorDelegators.length;
        for (uint256 i = 0; i < odLength; ) {
            if (operatorDelegators[i] == operatorDelegator) {
                found = true;
                break;
            }

            unchecked {
                ++i;
            }
        }
        if (!found) revert NotFound();

        // Call the OD to stake the ETH
        operatorDelegator.stakeEth{ value: msg.value }(pubkey, signature, depositDataRoot);
    }

```
https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L618-L643

##

## [L-6] Risk of Imbalanced Load Distribution Due to Default Selection Bias ``chooseOperatorDelegatorForDeposit()`` function 

### Impact

- There could be a consistent bias towards the first OperatorDelegator, especially in scenarios where frequently all OperatorDelegators exceed their respective thresholds. This can create an uneven distribution of deposits, potentially overloading the first OperatorDelegator.

- If the first OperatorDelegator has significantly different operational characteristics or capacities compared to others, consistently defaulting to it might lead to inefficiencies or increased risks of failure.

- The function does not balance the load among OperatorDelegators effectively if it always falls back to the first. This could defeat the purpose of having multiple OperatorDelegators, which is typically to distribute workload and reduce risks.

```solidity
FILE: 2024-04-renzo/contracts/RestakeManager.sol

/// @dev Picks the OperatorDelegator with the TVL below the threshold or returns the first one in the list
    /// @return The OperatorDelegator to use
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
https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L360-L393

##

## [L-7] Unrestricted maximum value in ``coolDownPeriod()`` 

Currently the cooldown period is 7 days as per docs. If set maximum values uses can't withdraw their tokes. 

```
 wait the timeout period (7 days on mainnet), 

```

```solidity
FILE: 2024-04-renzo/contracts/Withdraw/WithdrawQueue.sol

/**
     * @notice Updates the coolDownPeriod for withdrawal requests
     * @dev    It is a permissioned call (onlyWithdrawQueueAdmin)
     * @param   _newCoolDownPeriod  new coolDownPeriod in seconds
     */
    function updateCoolDownPeriod(uint256 _newCoolDownPeriod) external onlyWithdrawQueueAdmin {
        if (_newCoolDownPeriod == 0) revert InvalidZeroInput();
        emit CoolDownPeriodUpdated(coolDownPeriod, _newCoolDownPeriod);
        coolDownPeriod = _newCoolDownPeriod;
    }

```
https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L124-L133

##

## [L-8] ``xReceive()`` become DOS when ``RestakeManager`` paused  

When RestakeManager is paused, attempting to call depositETH will lead to a revert, usually triggered by a require statement checking the paused state. This prevents any new funds from being accepted into the system, safeguarding users’ assets from being locked in a potentially compromised or unstable environment.

```solidity
FILE: 2024-04-renzo/contracts/Bridge/L1/xRenzoBridge.sol

// Deposit it into Renzo RestakeManager
        restakeManager.depositETH{ value: ethAmount }();

```
https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L174-L175

```solidity
FILE: 2024-04-renzo/contracts/RestakeManager.sol

592: function depositETH(uint256 _referralId) public payable nonReentrant notPaused {

```
https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L592

##

## [L-9] ``sweepBatchSize * bridgeFeeShare) / FEE_BASIS`` For large deposits protocol loss huge value since the fee calculation is fixed for deposit greater than 32ETH 

When a user deposits an amount significantly larger than 32 ETH, the system still only deducts the fee equivalent to what would be deducted for 32 ETH. This creates an imbalance where the system may not be collecting sufficient fees proportional to the amount being processed. This could potentially lead to revenue loss for the system if the cost of handling larger transactions (like security, operational costs) scales with the transaction size.

Let's recalculate the fee using the correct bridgeFeeShare of 0.05% for a 1000 ETH deposit, based on your specifications:

### POC

Lets assume,
sweepBatchSize = 32 ETH
bridgeFeeShare = 5 (which equates to 0.05% fee since FEE_BASIS is 10000)
FEE_BASIS = 10000
_amountIn = 1000 ETH

As per implementation
Fee = (32 ETH * 5) / 10000 = 160 / 10000 = 0.016 ETH - > 0.0016%

As per original deposit
Fee = (1000 ETH * 5) / 10000 = 5000 / 10000 = 0.5 ETH  - > 0.05%

Loss to Protocol = Fee using proportional mechanism - Fee using current mechanism
Loss to Protocol = 0.5 ETH - 0.016 ETH = 0.484 ETH

Its very huge lose to protocol and This breaks the 0.05% fee invariants 

```solidity
FILE: 2024-04-renzo/contracts/Bridge/L2/xRenzoDeposit.sol

/**
     * @notice Function returns bridge fee share for deposit
     * @param _amountIn deposit amount in terms of ETH
     */
    function getBridgeFeeShare(uint256 _amountIn) public view returns (uint256) {
        // deduct bridge Fee share
        if (_amountIn < sweepBatchSize) {
            return (_amountIn * bridgeFeeShare) / FEE_BASIS;
        } else {
            return (sweepBatchSize * bridgeFeeShare) / FEE_BASIS;
        }
    }

``` 
https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L273C4-L284

### Recommended Mitigation
Implement the 0.05% percent invariant for all deposits 

##

## [L-10] Inconsistency in Price Validation Between ``Oracle`` and ``CCIPReceiver``

When fetching the price from RenzoOracleL2, the system strictly checks that the ezETH price is not less than 1 ether, reverting with InvalidOraclePrice() if it is. However, when updating ezETH via CCIPReceiver, there is no check to ensure that the price of ezETH meets this criterion. Technically, when fetching price data from CCIPReceiver, the lastPrice can be below 1 ETH. This represents an inconsistency in the price implementation.

```solidity
FILE: 2024-04-renzo/contracts/Bridge/L2/Oracle/RenzoOracleL2.sol

55: if (_scaledPrice < 1 ether) revert InvalidOraclePrice();

```
https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L55

```solidity
FILE: 2024-04-renzo/contracts/Bridge/L2/xRenzoDeposit.sol

 /**
     * @notice  Updates the price feed
     * @dev     This function will receive the price feed and timestamp from the L1 through CCIPReceiver middleware contract.
     *          It should verify the origin of the call and only allow permissioned source to call.
     * @param   _price The price of ezETH sent via L1.
     * @param   _timestamp The timestamp at which L1 sent the price.
     */
    function updatePrice(uint256 _price, uint256 _timestamp) external override {
        if (msg.sender != receiver) revert InvalidSender(receiver, msg.sender);
        _updatePrice(_price, _timestamp);
    }


/**
     * @notice  Internal function to update price
     * @dev     Sanity checks input values and updates prices
     * @param   _price  Current price of ezETH to ETH - 18 decimal precision
     * @param   _timestamp  The timestamp of the price update
     */
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
https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L330-L359

##

## [L-11] Untracked ``bridgeRouterFeeBps`` Fees Compromise Protocol Accounting and Result in Losses

The ``bridgeRouterFeeBps`` fee is deducted from ``amountNextWETH``, but it is not accounted for, and it is unclear what happens to that fee. Although the fee is subtracted from the amount, the protocol does not track this fee, nor is it claimed anywhere within the protocol. It remains unclear what happens to the fee once it is deducted from the amount. This will ``break`` the over all ``protocol accounting`` .

```solidity
FILE: 2024-04-renzo/contracts/Bridge/L2/xRenzoDeposit.sol

 // Subtract the bridge router fee
        if (bridgeRouterFeeBps > 0) {
            uint256 fee = (amountNextWETH * bridgeRouterFeeBps) / 10_000;
            amountNextWETH -= fee;
        }

```
https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L384-L388

##

## [L-12] Misguided Zero-Value Checks for uint256

Since ``uint256`` cannot be negative, the check ``_amount < 0`` is inherently impossible. This leaves only the possibility of _amount being equal to zero as a valid check.

```solidity
FILE: 2024-04-renzo/contracts/Bridge/Connext/integratio/LockboxAdapterBlast.sol

65: if (_amount <= 0) {

```
https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L65

### Recommended Mitigation
```solidity

if (_amount == 0) {

```

##

## [L-13] Division by Zero in calculateRedeemAmount Function for Zero ezETH Supply 

The operation (_currentValueInProtocol * _ezETHBeingBurned) / _existingEzETHSupply can lead to a division by zero if _existingEzETHSupply is zero. 

```solidity
FILE: 2024-04-renzo/contracts/Oracle/RenzoOracle.sol

 function calculateRedeemAmount(
        uint256 _ezETHBeingBurned,
        uint256 _existingEzETHSupply,
        uint256 _currentValueInProtocol
    ) external pure returns (uint256) {
        // This is just returning the percentage of TVL that matches the percentage of ezETH being burned
        uint256 redeemAmount = (_currentValueInProtocol * _ezETHBeingBurned) / _existingEzETHSupply;

        // Sanity check
        if (redeemAmount == 0) revert InvalidTokenAmount();

        return redeemAmount;
    }

``` 
https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L152-L164

##

## [L-14] Wrong Comment in ``setPaused()`` function

The comment suggest only restake manager admin to set the paused state. But in actual implementation ``onlyDepositWithdrawPauserAdmin `` set the paused state .

```diff
FILE: 2024-04-renzo/contracts/RestakeManager.sol

- /// @dev Allows a restake manager admin to set the paused state of the contract
+ /// @dev Allows a DepositWithdrawPauserAdmin to set the paused state of the contract
    function setPaused(bool _paused) external onlyDepositWithdrawPauserAdmin {
        paused = _paused;
    }

```

##

## [L-15] The ``_allocationBasisPoints `` declaration contradict with actual implementation

Declaration suggests this will accept uint256 range of the values . But in actual implementations this will revert if the value is greater than 10000.

```solidity
FILE: 2024-04-renzo/contracts/RestakeManager.sol

133: uint256 _allocationBasisPoints

146: if (_allocationBasisPoints > (100 * BASIS_POINTS)) revert OverMaxBasisPoints();

``` 
https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L146

##

## [L-16] Lack of check for ``_transferId`` uniqueness in ``xReceive`` function

Even though _transferId is generated using Keccak-256—a cryptographic hashing function—it's worth acknowledging that while extremely rare, the possibility of collisions (two distinct input sets producing the same hash output) theoretically exists. Despite the low probability, the possibility of a collision cannot be completely dismissed, especially as computational power increases or through a breakthrough in cryptographic research.

  
The EzETHMinted event is designed to log instances of minting operations for ezETH. However, if the Connext contract calls the function associated with this event multiple times using the same _transferId for different transactions, the uniqueness and traceability of these events are compromised. Each event emission with the same _transferId but varying other parameters (such as _amount, _origin, or _originSender) could lead to difficulties in accurately tracking each transaction's specifics, potentially confusing event monitoring tools and data consumers.

```solidity
FILE: 2024-04-renzo/contracts/Bridge/L1/xRenzoBridge.sol

function xReceive(
        bytes32 _transferId,
        uint256 _amount,
        address _asset,
        address _originSender,
        uint32 _origin,
        bytes memory
    ) external nonReentrant returns (bytes memory) {

// Emit the event
        emit EzETHMinted(_transferId, _amount, _origin, _originSender, ezETHAmount);

```
https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L195-L196

##

## [L-17] Compromised ``WithdrawQueueAdmin`` Could Set Excessive ``coolDownPeriod``

The function updateCoolDownPeriod allows a WithdrawQueueAdmin to change the cooldown period, which is a critical parameter affecting the operation of the claim() function. If this period is set to an excessively long duration maliciously or due to a compromise, it can effectively prevent users from claiming their withdrawals, resulting in a Denial of Service (DoS) for all users dependent on this functionality.

```solidity
FILE: 2024-04-renzo/contracts/Withdraw/WithdrawQueue.sol

 function updateCoolDownPeriod(uint256 _newCoolDownPeriod) external onlyWithdrawQueueAdmin {
        if (_newCoolDownPeriod == 0) revert InvalidZeroInput();
        emit CoolDownPeriodUpdated(coolDownPeriod, _newCoolDownPeriod);
        coolDownPeriod = _newCoolDownPeriod;
    }

```
https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L129-L133

##

## [L-18] Lack of Clarity in ``MAX_TIME_WINDOW`` Definition Extending to ``24 Hours and 60 Seconds`` in ``RenzoOracle``

In the RenzoOracle implementation, the staleness threshold for price feeds is set to 1 day plus 1 minute (86460 seconds), deviating from the typical 1-day period commonly used in other oracles. This deviation is not clearly documented, potentially leading to confusion regarding the freshness criteria of data. Properly documenting and justifying the rationale for this additional 60 seconds is crucial to ensure transparency and prevent misunderstandings about the oracle's data validity period. Clear documentation is also essential for maintaining consistent expectations and operations across systems that depend on this oracle for timely and accurate data.

```solidity
FILE: 2024-04-renzo/contracts/Oracle/RenzoOracle.sol

/// @dev The maxmimum staleness allowed for a price feed from chainlink
    uint256 constant MAX_TIME_WINDOW = 86400 + 60; // 24 hours + 60 seconds

```
https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L25-L26

##

## [L-19] Allowing ``withdraw()`` and ``claim()`` when contract paused poses unintended consequences 

If withdrawal and claim functionalities are allowed during a pause, it could lead to security vulnerabilities being exploited despite the pause, negating the purpose of freezing the contract’s operations. Allowing transactions during a pause can lead to inconsistencies in state, especially if the pause is intended to halt all contract activities for a critical update or fix.

Implement WhenNotPaused Modifier for both withdraw and claim functions

```solidity
FILE: 2024-04-renzo/contracts/Withdraw/WithdrawQueue.sol

206: function withdraw(uint256 _amount, address _assetOut) external nonReentrant {

279: function claim(uint256 withdrawRequestIndex) external nonReentrant {

```
https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L279

##

## [L-20] Restrictive Cross-Chain Token Address Validation

The contract uses the IXERC20Registry interface to fetch the xerc20 address for a given ERC20 token (_erc20). This fetched address is then compared to the _remoteToken parameter, which is intended to represent the token's address on the destination chain.

By requiring that these addresses match, the contract assumes that the same token must have the same address on both chains. This assumption does not accommodate scenarios where a token’s address on the destination chain might differ due to reasons like:
Different deployment transactions or contexts.
Different governance or administrative procedures on another chain.

This check prevents the use of the bridge for cases where tokens are represented differently across chains. It restricts users only to scenarios where the token deployment has been mirrored exactly across chains, which is not always feasible or desirable.

```solidity
FILE: 2024-04-renzo/contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol

 // If using xERC20, the assumption is that the contract should be deployed at same address
        // on both networks.
        if (xerc20 != _remoteToken) {

```
https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L77-L79

##

## [L-21]  ``bridgeTo`` function vulnerable to reentrancy attacks

The function bridgeTo involves multiple state changes and external calls without a reentrancy guard:

This exposes the function to potential reentrancy attacks, especially since it interacts with multiple external contracts (the ERC20 token, the lockbox, and the bridge). Even though the SafeERC20 library mitigates some risks, comprehensive reentrancy protection is advisable.

```solidity
FILE: 2024-04-renzo/contracts/Bridge/Connext/integration
/LockboxAdapterBlast.sol

 function bridgeTo(
        address _to,
        address _erc20,
        address _remoteToken,
        uint256 _amount,
        uint32 _minGasLimit,
        bytes calldata _extraData
    ) external {
        // Sanity check
        if (_amount <= 0) {
            revert AmountLessThanZero();
        }

        address xerc20 = IXERC20Registry(registry).getXERC20(_erc20);
        address lockbox = IXERC20Registry(registry).getLockbox(xerc20);

        // Sanity check
        if (xerc20 == address(0) || lockbox == address(0)) {
            revert InvalidAddress();
        }

        // If using xERC20, the assumption is that the contract should be deployed at same address
        // on both networks.
        if (xerc20 != _remoteToken) {
            revert InvalidRemoteToken(_remoteToken);
        }

        SafeERC20.safeTransferFrom(IERC20(_erc20), msg.sender, address(this), _amount);
        SafeERC20.safeApprove(IERC20(_erc20), lockbox, _amount);
        IXERC20Lockbox(lockbox).deposit(_amount);
        SafeERC20.safeApprove(IERC20(xerc20), blastStandardBridge, _amount);
        L1StandardBridge(blastStandardBridge).bridgeERC20To(
            xerc20,
            _remoteToken,
            _to,
            _amount,
            _minGasLimit,
            _extraData
        );
    }

```
https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L56-L95

##

## [L-22] Immutable Delegate Address Elevates Security Risk

- If the delegate address becomes compromised (e.g., the private keys are stolen, or the address is otherwise controlled by a malicious actor), the contract has no built-in mechanism to change this address. This immutability could lead to security vulnerabilities, as the compromised delegate might have significant control or influence over the operations intended for delegation.

```solidity
FILE: 2024-04-renzo/contracts/Delegation/OperatorDelegator.sol

/// @dev Sets the address to delegate tokens to in EigenLayer -- THIS CAN ONLY BE SET ONCE
    function setDelegateAddress(
        address _delegateAddress,
        ISignatureUtils.SignatureWithExpiry memory approverSignatureAndExpiry,
        bytes32 approverSalt
    ) external nonReentrant onlyOperatorDelegatorAdmin {
        if (address(_delegateAddress) == address(0x0)) revert InvalidZeroInput();
        if (address(delegateAddress) != address(0x0)) revert DelegateAddressAlreadySet();

        delegateAddress = _delegateAddress;

        delegationManager.delegateTo(delegateAddress, approverSignatureAndExpiry, approverSalt);

        emit DelegationAddressUpdated(_delegateAddress);
    }

```
https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L116-L130

##

## [L-23] Fund Immobilization Risk Due to Null Strategy Address

The setTokenStrategy function in the OperatorDelegator contract allows for the strategy of a specific ERC20 token to be set to the zero address, effectively disabling the strategy. This operation does not include checks or mechanisms to handle tokens already deposited under the previously active strategy, nor does it facilitate an easy recovery or reactivation path. This can result in tokens being locked within the contract, with no strategy available for managing or withdrawing these assets.

```solidity
2024-04-renzo/contracts/Delegation/OperatorDelegator.sol

/// @dev Sets the strategy for a given token - setting strategy to 0x0 removes the ability to deposit and withdraw token
    function setTokenStrategy(
        IERC20 _token,
        IStrategy _strategy
    ) external nonReentrant onlyOperatorDelegatorAdmin {
        if (address(_token) == address(0x0)) revert InvalidZeroInput();

        tokenStrategyMapping[_token] = _strategy;
        emit TokenStrategyUpdated(_token, _strategy);
    }

```
https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L105-L114

##

## [L-24] Automatic ETH Processing and Fee Deduction Without Sender Verification

The receive() function does not differentiate the source of the incoming ETH. Whether the ETH is sent as intended protocol rewards, or mistakenly sent by an external user, it is processed in the same manner. 

Accidental Deposits: Users who mistakenly send ETH to the contract address will have their funds automatically processed as rewards, with a portion deducted as fees. Since Ethereum transactions are irreversible, once the ETH is sent and processed, recovering it would depend entirely on the actions of the contract administrators, assuming they can identify the transaction as a mistake and choose to return the funds.

Unintended Fee Deductions: In cases of accidental ETH sends, not only is the ETH handled as rewards, but a fee is also deducted and sent to the fee address, further complicating the situation for the unintended sender.

```solidity
FILE: 2024-04-renzo/contracts/Deposits/DepositQueue.sol

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
        totalEarned[address(0x0)] = totalEarned[address(0x0)] + remainingRewards;

        // Emit the rewards event
        emit RewardsDeposited(IERC20(address(0x0)), remainingRewards);
    }


```
https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L163-L183

##

## [L-25] Vulnerability to Excessive Gas Cost Refunds Potentially Draining Contract Funds

The potential vulnerability in the _refundGas function arises from its method of calculating the gas costs for refunding the administrators of the contract. This calculation uses the formula gasUsed * tx.gasprice, where gasUsed is the difference between the gas available at the start of the transaction (initialGas) and the gas left at the point of calculation (gasleft()), and tx.gasprice is the gas price set by the user who initiated the transaction.

Imagine an administrator or a malicious user initiates a transaction interacting with the contract, and deliberately sets a very high tx.gasprice, much higher than the average network gas price.

Calculation:

Suppose the transaction uses 100,000 gas (gasUsed).
The user sets tx.gasprice to 1,000 gwei, significantly above normal rates.
The refund amount would be 100,000 * 1,000 gwei = 100,000,000 gwei, or 0.1 ether.

If the _refundGas function does not cap the refund amount or if the transaction's gas price is exceptionally high, there's a risk that a large portion of the contract's ETH balance could be used to cover these gas costs. This is particularly concerning if the function is called with high frequency or during periods of high gas prices.

```solidity
FILE: 2024-04-renzo/contracts/Deposits/DepositQueue.sol

 /**
     * @notice Internal function used to refund gas to admin accounts if enough balance
     * @param initialGas Initial Gas available
     */
    function _refundGas(uint256 initialGas) internal {
        uint256 gasUsed = (initialGas - gasleft()) * tx.gasprice;
        uint256 gasRefund = address(this).balance >= gasUsed ? gasUsed : address(this).balance;
        (bool success, ) = payable(msg.sender).call{ value: gasRefund }("");
        if (!success) revert TransferFailed();
        emit GasRefunded(msg.sender, gasRefund);
    }

```
https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L279-L289





 



















