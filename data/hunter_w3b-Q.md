## [L-01] The Transaction is revert it and gas spent is not recorded for `NativeEth Restake Admin` account

When the `onlyNativeEthRestakeAdmin` calls the `delegationManager` contract of EL for the `queueWithdrawals` or `completeQueuedWithdrawal` functions, if either `queueWithdrawals` or `completeQueuedWithdrawal` is paused in EL, the transaction is reverted, and the gas spent by the NativeEth Restake Admin is not recorded.

> Gas can be spent by a revert, but the remaining gas is refunded.

**queueWithdrawals()**

```solidity
            // record gas spent
201 --->    uint256 gasBefore = gasleft();
            //..
            // queue withdrawal in EigenLayer
252 --->    bytes32 withdrawalRoot = delegationManager.queueWithdrawals(queuedWithdrawalParams)[0];

            //...
            // update the gas spent for RestakeAdmin
266 --->    _recordGas(gasBefore);
```

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Delegation/OperatorDelegator.sol#L193-L256

**completeQueuedWithdrawal()**

```solidity

289 --->   uint256 gasBefore = gasleft();

           //...

           // complete the queued withdrawal from EigenLayer with receiveAsToken set to true
289 --->   delegationManager.completeQueuedWithdrawal(withdrawal, tokens, middlewareTimesIndex, true);

           //...

           // record current spent gas
351 --->   _recordGas(gasBefore);
```

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Delegation/OperatorDelegator.sol#L265-L325

**EL DelegationManager contract**::
https://github.com/code-423n4/2023-04-eigenlayer/blob/main/src/contracts/core/DelegationManager.sol

## [L-02] Lack of slippage control on `restakeManager.Depoist()`

There is no protection for the user in the current implementation. minShares checks are commonly implemented in staking contracts.

No `minShares` slippage param when minting `ezETH` leaves users with no control over minted shares amount

When users [deposit](https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/RestakeManager.sol#L473C1-L475C6) `ERC20` tokens to mint ezETH, an oracle(chainlink) is used to determine the current price of the token (e.g LST) . Since the amount of ezETH received by the user is determined by an interaction with an oracle, the amount received can vary while the request is waiting to be executed.

The function that uses the oracle's price feed for the value of the tokens is the `RenzoOracle::lookupTokenValue`

```solidity
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

Essentially, the user has no way to predict how many ezETH they will get back at the moment of minting, as the price could be updated while the request is in the mempool. `minAmountOut` or `minShares` checks are commonly implemented to allow for user defined slippage control.

## [L-03] Prevent deposits to the nodes with max amount of assets being staked already

If the node has staked already 1e23 of assets, it should not receive any transfers, since there is no more space to stake at EigenLayer.

```solidity
        // Approve the tokens to the operator delegator
        _collateralToken.safeApprove(address(operatorDelegator), _amount);

        // Call deposit on the operator delegator
        operatorDelegator.deposit(_collateralToken, _amount);
```

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/RestakeManager.sol#L558-L562

```solidity
        // Approve the tokens to the operator delegator
        _token.safeApprove(address(operatorDelegator), _amount);

        // Deposit the tokens into EigenLayer
        operatorDelegator.deposit(_token, _amount);
```

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/RestakeManager.sol#L663-L667

## [L-04] Implementing a receive() Function for Accidental ETH Deposits in RestakeManager

`RestakeManager` contract is user interaction to send ETH and LST tokens if some user mistakenly deposits ETH directly to the contract address without calling depositETH() function the ETH becomes locked in the contract without any further action. There is no mechanism to handle such deposits.

```solidity
    function depositETH() external payable {
        depositETH(0);
    }
```

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/RestakeManager.sol#L582-L584

```diff
+    receive() external payable {
+        depositETH(0);
+    }
```

## [L-05] Exceeding the maximum number of strategies per operator delegator can cause tokens to be stuck

The current implementation of the setTokenStrategy() function allows for an unlimited number of strategies to be set for a single operator delegator, which can result in the exceeding of the maximum number of strategies allowed per staker in the EigenLayer protocol.

```solidity
    function setTokenStrategy(
        IERC20 _token,
        IStrategy _strategy
    ) external nonReentrant onlyOperatorDelegatorAdmin {
        if (address(_token) == address(0x0)) revert InvalidZeroInput();

        tokenStrategyMapping[_token] = _strategy;
        emit TokenStrategyUpdated(_token, _strategy);
    }
```

This can cause tokens to become stuck in the operator delegator, as there is no mechanism in place to retrieve them.

Due to this check in EigenLayer:

```solidity
        // if they dont have existing shares of this strategy, add it to their strats
        if (stakerStrategyShares[depositor][strategy] == 0) {
            require(
                stakerStrategyList[depositor].length < MAX_STAKER_STRATEGY_LIST_LENGTH,
                "StrategyManager._addShares: deposit would exceed MAX_STAKER_STRATEGY_LIST_LENGTH"
            );
            stakerStrategyList[depositor].push(strategy);
        }
```

https://github.com/code-423n4/2023-04-eigenlayer/blob/main/src/contracts/core/StrategyManager.sol#L634-L642

```solidity
    uint8 internal constant MAX_STAKER_STRATEGY_LIST_LENGTH = 32;
```

https://github.com/code-423n4/2023-04-eigenlayer/blob/main/src/contracts/core/StrategyManagerStorage.sol#L27C1-L28C66

if this more then that this revert it and the tokens is stuck in the operatorDelegator because there is no way retrive back the erc20 token Strategies.

## [L-06] No defense mechanism has been implemented for unauthorized multiple reward generation

The current system allows users to a loophole by repeatedly generating rewards using the same ezETH. This exploit involves a sequence of steps where a user deposits a certain amount of ETH to mint ezETH, converts the ezETH back to ETH, deposits the ETH again to receive additional ezETH, and repeats the process multiple times.

This unauthorized action enables users to generate rewards multiple times.

Deposit a specific amount of ETH to mint ezETH.
Convert the received ezETH in Dex's back to ETH.
Deposit the obtained ETH once again to receive additional ezETH.
Repeat the process iteratively to generate rewards multiple times.

## [L-07] Lack of zero value checks can result in the loss of user funds

If the OperatorDelegator is zero address this could lead to send stake deposit LST to zero address during user deposits.

```solidity
     function addOperatorDelegator(
        IOperatorDelegator _newOperatorDelegator,
        uint256 _allocationBasisPoints
    ) external onlyRestakeManagerAdmin {
        // Ensure it is not already in the list
        uint256 odLength = operatorDelegators.length;
        for (uint256 i = 0; i < odLength; ) {
            if (address(operatorDelegators[i]) == address(_newOperatorDelegator))
                revert AlreadyAdded();
            unchecked {
                ++i;
            }
        }

        // Verify a valid allocation
        if (_allocationBasisPoints > (100 * BASIS_POINTS)) revert OverMaxBasisPoints();

        // Add it to the list
        operatorDelegators.push(_newOperatorDelegator);

        emit OperatorDelegatorAdded(_newOperatorDelegator);

        // Set the allocation
        operatorDelegatorAllocations[_newOperatorDelegator] = _allocationBasisPoints;

        emit OperatorDelegatorAllocationUpdated(_newOperatorDelegator, _allocationBasisPoints);
    }
```

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/RestakeManager.sol#L131

```solidity
    function initialize(
        IRoleManager _roleManager,
        IEzEthToken _ezETH,
        IRenzoOracle _renzoOracle,
        IStrategyManager _strategyManager,
        IDelegationManager _delegationManager,
        IDepositQueue _depositQueue
    ) public initializer {
        __ReentrancyGuard_init();

        roleManager = _roleManager;
        ezETH = _ezETH;
        renzoOracle = _renzoOracle;
        strategyManager = _strategyManager;
        delegationManager = _delegationManager;
        depositQueue = _depositQueue;
        paused = false;
    }
```

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/RestakeManager.sol#L101-L118

The deposit function does not check if the `_amount` parameter is greater than zero. If a user accidentally sets `_amount` to zero, it could result in a failed transaction

```solidity
        function deposit(
        IERC20 _collateralToken,
        uint256 _amount,
        uint256 _referralId
    ) public nonReentrant notPaused {
        // Verify collateral token is in the list - call will revert if not found
        uint256 tokenIndex = getCollateralTokenIndex(_collateralToken);

//.....


    function depositETH(uint256 _referralId) public payable nonReentrant notPaused {
        // Get the total TVL
        (, , uint256 totalTVL) = calculateTVLs();
```

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/RestakeManager.sol#L491

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/RestakeManager.sol#L592

## [L-08] If the strategy for a token changes or is mistakenly updated by the admin

In the `OperatorDelegator::setTokenStrategy()` function of the contract, allows the `OperatorDelegatorAdmin` to overwrite the strategy for a token without proper validation. This can lead to incorrect strategy assignment or manipulation of token strategies.

```solidity
    function setTokenStrategy(
        IERC20 _token,
        IStrategy _strategy
    ) external nonReentrant onlyOperatorDelegatorAdmin {
        if (address(_token) == address(0x0)) revert InvalidZeroInput();

        tokenStrategyMapping[_token] = _strategy;
        emit TokenStrategyUpdated(_token, _strategy);
    }
```

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Delegation/OperatorDelegator.sol#L106C1-L114C6

If the Operator Delegator Admin accidentally setTokenStrategy for a token that has already set its strategy for a different strategy, due to the absence of the token already added in this strategy check, it can lead to
miscalcutaion of `getTokenBalanceFromStrategy`

```solidity
    function getTokenBalanceFromStrategy(IERC20 token) external view returns (uint256) {
        return
            queuedShares[address(this)] == 0
                ? tokenStrategyMapping[token].userUnderlyingView(address(this))
                : tokenStrategyMapping[token].userUnderlyingView(address(this)) +
                    tokenStrategyMapping[token].sharesToUnderlyingView(
                        queuedShares[address(token)]
                    );
    }
```

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Delegation/OperatorDelegator.sol#L327-L335

This discrepancy will extend to the affecting the calculation of `RestakeManager::calculateTVLs()` function when calculate total asset deposited in the protocol.

```solidity
                uint256 operatorBalance = operatorDelegators[i].getTokenBalanceFromStrategy(
                    collateralTokens[j]
                );
```

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/RestakeManager.sol#L302-L304

And this will extend the miscalcutaion of assets deposit and mint ezETH tokens.

## [INFO-01] No validation of `pubkey`,`signature`,`depositDataRoot`

The stakeEth function in the OperatorDelegator contract lacks validation for the pubkey, signature, and depositDataRoot parameters.

```solidity
function stakeEth(bytes calldata pubkey, bytes calldata signature, bytes32 depositDataRoot)
        external
        payable
        onlyRestakeManager
    {
        // Call the stake function in the EigenPodManager
        eigenPodManager.stake{value: msg.value}(pubkey, signature, depositDataRoot);

        // Increment the staked but not verified ETH
        stakedButNotVerifiedEth += msg.value;
    }
```

## [INFO-02] If `maxDepositTVL` limit can be set to 0, effectively disabling the TVL check.

This could be a potential risk if not managed carefully, as it allows unlimited deposits, potentially exceeding the capacity of the system.

```solidity
    function setMaxDepositTVL(uint256 _maxDepositTVL) external onlyRestakeManagerAdmin {
        maxDepositTVL = _maxDepositTVL;
    }
```

Unexpected Amount of Supported Assets Could Increase ezETH price If, for any reason, the RestakeManager contract received an unexpected amount of supported assets, the ezETH price would increase.

The inflation percentage will increase if the user deposits less `_newValueAdded`, they revert it.

```solidity
        // Calculate the percentage of value after the deposit
        uint256 inflationPercentaage = (SCALE_FACTOR * _newValueAdded) /
            (_currentValueInProtocol + _newValueAdded);
```

## [INFO-03] Discrepancy Between Documentation and Code

if the limit is set for the collateral tokens this is also applied to `ETH`

1. Documentation Claims:

https://docs.renzoprotocol.com/docs/product/deposit-boosts

> Renzo never caps ETH Deposits on EigenLayer

The Renzo Protocol documentation explicitly states that "Renzo never caps ETH Deposits on EigenLayer." This statement is clear, suggesting that users can deposit any amount of ETH without restrictions.

2. Code Implementation:

However, In depositETH function includes a check for a maximum deposit TVL. If the total TVL, including the deposited ETH, exceeds the maximum limit, the transaction will revert.

```solidity
    function depositETH(uint256 _referralId) public payable nonReentrant notPaused {
        // Get the total TVL
        (, , uint256 totalTVL) = calculateTVLs();

        // Enforce TVL limit if set
        if (maxDepositTVL != 0 && totalTVL + msg.value > maxDepositTVL) {
            revert MaxTVLReached();
        }
```

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/RestakeManager.sol#L592-L599

## [INFO-04] `restakeManager` and `withdrawQueue` should be initialized in `DepositQueue::initialize` function

```solidity
    function initialize(IRoleManager _roleManager) public initializer {
        __ReentrancyGuard_init();

        if (address(_roleManager) == address(0x0)) revert InvalidZeroInput();

        roleManager = _roleManager;
        // @audit restakeManager = _restakeManager;
    }
```

```solidity
    function setWithdrawQueue(IWithdrawQueue _withdrawQueue) external onlyRestakeManagerAdmin {
        if (address(_withdrawQueue) == address(0)) revert InvalidZeroInput();
        emit WithdrawQueueUpdated(address(withdrawQueue), address(_withdrawQueue));
        withdrawQueue = _withdrawQueue;
    }


    function setRestakeManager(IRestakeManager _restakeManager) external onlyRestakeManagerAdmin {
        if (address(_restakeManager) == address(0x0)) revert InvalidZeroInput();

        restakeManager = _restakeManager;

        emit RestakeManagerUpdated(_restakeManager);
    }
```

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Deposits/DepositQueue.sol#L73-L118

## [INFO-05] During flash crashes, oracles might return inaccurate prices

Implement checks to ensure that the price returned by the oracle lies within an expected range to guard against potential flash crash vulnerabilities.

Define a reasonable price range based on historical data for stETH/ETH or wbETH/ETH pairs, as they typically maintain a stable price. However, precautions must be taken for potential flash crashes. If the price falls outside this range, consider reverting the transaction."

no upper bound check

```solidity
        (, int256 price, , uint256 timestamp, ) = oracle.latestRoundData();
        if (timestamp < block.timestamp - MAX_TIME_WINDOW) revert OraclePriceExpired();
        if (price <= 0) revert InvalidOraclePrice();
```

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Oracle/RenzoOracle.sol#L75-L78
