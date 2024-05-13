# [L-01] outcome of getFees is not checked against 0 

## Description
Inside the `sendPrice` function, `getFee` is called to get the fees that are required for sending a message:
```javascript
    function sendPrice(
        CCIPDestinationParam[] calldata _destinationParam,
        ConnextDestinationParam[] calldata _connextDestinationParam
    ) external payable onlyPriceFeedSender nonReentrant {
        // call getRate() to get the current price of ezETH
        uint256 exchangeRate = rateProvider.getRate();
        bytes memory _callData = abi.encode(exchangeRate, block.timestamp);
        // send price feed to renzo CCIP receivers
        for (uint256 i = 0; i < _destinationParam.length; ) {
            Client.EVM2AnyMessage memory evm2AnyMessage = Client.EVM2AnyMessage({
                receiver: abi.encode(_destinationParam[i]._renzoReceiver), // ABI-encoded xRenzoDepsot contract address
                data: _callData, // ABI-encoded ezETH exchange rate with Timestamp
                tokenAmounts: new Client.EVMTokenAmount[](0), // Empty array indicating no tokens are being sent
                extraArgs: Client._argsToBytes(
                    // Additional arguments, setting gas limit
                    Client.EVMExtraArgsV1({ gasLimit: 200_000 })
                ),
                // Set the feeToken  address, indicating LINK will be used for fees
                feeToken: address(linkToken)
            });

            // Get the fee required to send the message
->            uint256 fees = linkRouterClient.getFee(
                _destinationParam[i].destinationChainSelector,
                evm2AnyMessage
            );

            if (fees > linkToken.balanceOf(address(this)))
                revert NotEnoughBalance(linkToken.balanceOf(address(this)), fees);


```

`getFee` is a function derived from the Chainlink CCIP Router Client and should therefore be implemented with the correct logic:

The [Docs](https://docs.chain.link/ccip/api-reference/i-router-client#getfee) state the following regarding `getFee`:
```javascript
//_returns 0 fees on invalid message._
```
This means that if an invalid message is used, 0 will be returned and ultimately `uint256 fees` will be 0. There is however no check implemented to make sure that `fees != 0`.
## Tools Used
Manual Review
## Recommendation
Make sure to implement a 0 check after retrieving the fees, to ensure that no invalid messages go through. 

-----------------
# [L-02] BridgeFees can be circumvented by bridging more than the sweep size

## Description
Whenever a user calls `XRenzoDeposit._deposit`, the `bridgeFee` will be calculated by calling `getBridgeFeeShare`:
```javascript

    /**
     * @notice  Internal function to trade deposit tokens for nextWETH and mint xezETH
     * @dev     Deposit Tokens should be available in the contract before calling this function
     * @param   _amountIn  Amount of tokens deposited
     * @param   _minOut  Minimum number of xezETH to accept to ensure slippage minimums
     * @param   _deadline  latest timestamp to accept this transaction
     * @return  uint256  Amount of xezETH minted to calling account
     */
    function _deposit(
        uint256 _amountIn,
        uint256 _minOut,
        uint256 _deadline
    ) internal returns (uint256) {
        // calculate bridgeFee for deposit amount
->        uint256 bridgeFee = getBridgeFeeShare(_amountIn);
        // subtract from _amountIn and add to bridgeFeeCollected
        _amountIn -= bridgeFee;
        bridgeFeeCollected += bridgeFee;
//..Ommitted Code

```

```javascript
    function getBridgeFeeShare(uint256 _amountIn) public view returns (uint256) {
        // deduct bridge Fee share
        if (_amountIn < sweepBatchSize) {
            return (_amountIn * bridgeFeeShare) / FEE_BASIS;
        } else {
            return (sweepBatchSize * bridgeFeeShare) / FEE_BASIS;
        }
    }
```
Inside here the `_amountIn` is checked against the `sweepBatchSize`, if its smaller it will return the calculated `bridgefee` which will simply be the (amount x bridgeFeeShare) divided by the fee basis.

However, whenever `_amountIn` is bigger than `sweepBatchSize`, the `bridgefee` will be capped with `_amountIn` = `sweepBatchSize`. 

This means that a user can circumvent extra fees by specifying an `_amountIn` larger than the `sweepBatchSize` and by doing so the user does not have to pay the difference between `sweepBatchSize` & `_amountIn`.
## Tools Used
Manual Review
## Recommendation
Make sure to always take the `_amountIn` regardless if it is > `sweepBatchSize`

---------------
# [L-03] Different times used for staleness checks

## Description
To make sure prices are accurately retrieved and used throughout the contract, a staleness check is performed to make sure the prices are not outdated. This happens in a couple of places inside the codebase:

such as for example:
```javascript

    function getMintRate() public view returns (uint256, uint256) {
        (, int256 price, , uint256 timestamp, ) = oracle.latestRoundData();
->        if (timestamp < block.timestamp - MAX_TIME_WINDOW) revert OraclePriceExpired();
        // scale the price to have 18 decimals
        uint256 _scaledPrice = (uint256(price)) * 10 ** (18 - oracle.decimals());
        if (_scaledPrice < 1 ether) revert InvalidOraclePrice();
        return (_scaledPrice, timestamp);
    }
}
```
where `MAX_TIME_WINDOW` is used which is set to (86460 seconds). 

Another instance which is inside of function `xRenzoDeposit._deposit`:
```javascript
//..Ommitted code
        // Fetch price and timestamp of ezETH from the configured price feed
        (uint256 _lastPrice, uint256 _lastPriceTimestamp) = getMintRate();

        // Verify the price is not stale
->        if (block.timestamp > _lastPriceTimestamp + 1 days) {
            revert OraclePriceExpired();
        }
//..Ommitted code

```
As u can see `1 days` is used here which translates to 86400 seconds.

Now as you can see we have a difference of 86460 - 86400 seconds here. Since both of these staleness checks are performed inside the same function `_deposit`, they should reflect the same amount, but they do not. 

Because of this every deposit that will happen inside the final 60 seconds should go through, but will instead fail because inside the `if` statement `1 days` is used instead of `86400 + 60`.
## Tools used
Manual Review
## Recommendation
Make sure to keep consistency throughout the codebase with regards to the use of staleness checks

-------------
# [L-04] no check is performed for authorized chainlink router
## Description
`CCIPReceive` is used to update the price feed. The function gets invoked with an `Any2EVMMessage` struct, which contains the message that needs to be processed.

```javascript
    function _ccipReceive(
        Client.Any2EVMMessage memory any2EvmMessage
    ) internal override whenNotPaused {
        address _ccipSender = abi.decode(any2EvmMessage.sender, (address));
        uint64 _ccipSourceChainSelector = any2EvmMessage.sourceChainSelector;
        // Verify origin on the price feed
        if (_ccipSender != xRenzoBridgeL1) revert InvalidSender(xRenzoBridgeL1, _ccipSender);
        // Verify Source chain of the message
        if (_ccipSourceChainSelector != ccipEthChainSelector)
            revert InvalidSourceChain(ccipEthChainSelector, _ccipSourceChainSelector);
        (uint256 _price, uint256 _timestamp) = abi.decode(any2EvmMessage.data, (uint256, uint256));
        xRenzoDeposit.updatePrice(_price, _timestamp);
        emit MessageReceived(
            any2EvmMessage.messageId,
            _ccipSourceChainSelector,
            _ccipSender,
            _price,
            _timestamp
        );
    }


```
Inside `CCIPReceive` several checks are performed to make sure the function is called from an authorized chainlink router. The [Docs](https://docs.chain.link/ccip/tutorials/programmable-token-transfers-defensive#receiving-and-processing-messages) state the following regarding the safety checks:
```javascript
//Security checks ensure the call is from the authorized router, an allowlisted source chain, and an allowlisted sender.
```
However, as we can see in the function there are no such safety checks ensured to make sure the router is authorized. 
## Tools Used
Manual Review
## Recommendation
Make sure to implement the needed checks to ensure the call is from an authorized caller.

-----------
# [L-05] BASIS_POINTS can be larger than 100% 

The `BASIS_POINTS` are used for percentages, as the code states:
```javascript

    /// @dev Basis points used for percentages (100 basis points equals 1%)
    uint256 constant BASIS_POINTS = 100;


```
 The default value is set to `100` which translates to `1%`. throughout the contract `BASIS_POINTS` are used and are of great importance, an example of this:

```javascript

    /// @dev Allows a restake manager admin to add an OperatorDelegator to the list
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
->        if (_allocationBasisPoints > (100 * BASIS_POINTS)) revert OverMaxBasisPoints();

//..Ommitted code
    }
```
As we can see `BASIS_POINTS` is used to verify a valid allocation and also used throughout more places inside the codebase.

The problem that arises however is that nowhere in the codebase a check is performed to see the total value of these `BASIS_POINTS`, this means that if we were to have for example `200` operators, the `BASIS_POINTS` would be 200 x 100 which would result in 200%. This would defeat the purpose of using such a point metric since the operators collectively should never exceed 100%.
## Tools used
Manual Review
## Recommendation
Make sure to implement the logic where `BASIS_POINTS` is capped to 100%.

-----------
## [L-06] UnderlyingSharesToView may vary significantly for different strategies

## Description
Inside `OperatorDelegator.queueWithdrawals` function `underlyingSharesToView` is called:
```javascript
    function queueWithdrawals(
        IERC20[] calldata tokens,
        uint256[] calldata tokenAmounts
    ) external nonReentrant onlyNativeEthRestakeAdmin returns (bytes32) {
//..Ommitted Code

        for (uint256 i; i < tokens.length; ) {
            if (address(tokens[i]) == IS_NATIVE) {
                // set beaconChainEthStrategy for ETH
                queuedWithdrawalParams[0].strategies[i] = eigenPodManager.beaconChainETHStrategy();

                // set shares for ETH
                queuedWithdrawalParams[0].shares[i] = tokenAmounts[i];
            } else {
                if (address(tokenStrategyMapping[tokens[i]]) == address(0))
                    revert InvalidZeroInput();

                // set the strategy of the token
                queuedWithdrawalParams[0].strategies[i] = tokenStrategyMapping[tokens[i]];

                // set the equivalent shares for tokenAmount
                queuedWithdrawalParams[0].shares[i] = tokenStrategyMapping[tokens[i]]
->                    .underlyingToSharesView(tokenAmounts[i]);
            }

            // set withdrawer as this contract address
            queuedWithdrawalParams[0].withdrawer = address(this);

            // track shares of tokens withdraw for TVL
            queuedShares[address(tokens[i])] += queuedWithdrawalParams[0].shares[i];
            unchecked {
                ++i;
            }
        }
//..Ommitted code

```
`underlyingToSharesView` is used to convert an amount of underlying tokens to the equivalent amount of shares in this strategy. However, the comments regarding `underlyingToSharesView` also state the following:
```diff

    /**
     * @notice Used to convert an amount of underlying tokens to the equivalent amount of shares in this strategy.
     * @notice In contrast to `underlyingToShares`, this function guarantees no state modifications
     * @param amountUnderlying is the amount of `underlyingToken` to calculate its conversion into strategy shares
     * @return The amount of shares corresponding to the input `amountUnderlying`
->     * @dev Implementation for these functions in particular may vary significantly for different strategies
     */
    function underlyingToSharesView(uint256 amountUnderlying) external view returns (uint256);


```
In the case of this protocol the same process of `underlyingToSharesView` is implemented for every strategy, this can lead to issues since the implementation of differs per strategy.
## Tools Used
Manual Review
## Recommendation
Make sure to handle the `underlyingToSharesView` per strategy that is being used.

-------

# [L-07] Malicious operator can manipulate the price of `ezETH`
## Description
A malicious operator can `undelegate` himself by calling `DelegationManager.undelegate()`:
[DelegationManager.sol#L211-L258](https://github.com/Layr-Labs/eigenlayer-contracts/blob/6de01c6c16d6df44af15f0b06809dc160eac0ebf/src/contracts/core/DelegationManager.sol#L211-L258)
```javascript
    function undelegate(address staker) external onlyWhenNotPaused(PAUSED_ENTER_WITHDRAWAL_QUEUE) returns (bytes32[] memory withdrawalRoots) {
```

When this operator `undelegates` himself, for example in case of `Eigenpod` shares being undelegated, the entire `Eigenpod` balance will be `0`.
Eigenpod balances are used during the calculation of the TVL, which means that this part will be erased from the TVL, leading to a price discrepancy.
## Tools used
Manual Review

-----

# [L-08] ChooseOperatorDelegatorForDeposit can exceed threshold
## Description

Inside the `deposit` function an operator is selected by calling function `chooseOperatorDelegatorForDeposit`:

```javascript
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
Whenever there are multiple operators, a loop will be entered. Inside this loop an operator below the treshold is returned.

However, after returning this `operator`, there is no check made to ensure that the `operator` still remains below the treshold. Rather it just transfers the `_amount` towards the `operator`.
```javascript
operatorDelegator.deposit(_collateralToken, _amount);
```



## Tools Used
Manual Review


## Recommendation
Ensure that you incorporate the logic where after looping through the code and identifying an operator, if there are more than one, ensuring it remains below the threshold after receiving the `_amount`.

# [L-09] extraArgs is hardcoded
## Description

Inside function `sendPrice`, `extraArgs` is extracted by taking the `gasLimit`, which is set to `200_000`:

```javascript

    function sendPrice(
        CCIPDestinationParam[] calldata _destinationParam,
        ConnextDestinationParam[] calldata _connextDestinationParam
    ) external payable onlyPriceFeedSender nonReentrant {
        // call getRate() to get the current price of ezETH
        uint256 exchangeRate = rateProvider.getRate();
        bytes memory _callData = abi.encode(exchangeRate, block.timestamp);
        // send price feed to renzo CCIP receivers
        for (uint256 i = 0; i < _destinationParam.length; ) {
            Client.EVM2AnyMessage memory evm2AnyMessage = Client.EVM2AnyMessage({
                receiver: abi.encode(_destinationParam[i]._renzoReceiver), // ABI-encoded xRenzoDepsot contract address
                data: _callData, // ABI-encoded ezETH exchange rate with Timestamp
                tokenAmounts: new Client.EVMTokenAmount[](0), // Empty array indicating no tokens are being sent
->                extraArgs: Client._argsToBytes(
                    // Additional arguments, setting gas limit
->                    Client.EVMExtraArgsV1({ gasLimit: 200_000 })
                ),
                // Set the feeToken  address, indicating LINK will be used for fees
                feeToken: address(linkToken)
            });


```

the [docs](https://docs.chain.link/ccip/getting-started) contains the following advice:
```javascript
//- Do not hardcode extraArgs: To simplify the example, extraArgs are hardcoded in the contract. The recommendation is to make sure extraArgs is mutable. For example, you can build extraArgs offchain and pass it in your functions call or store it in a storage variable that you can update on demand. Thus, you can make sure extraArgs remains backward compatible for future CCIP upgrades.
```

However, as we can see the `extraArgs` is hardcoded, which could lead to issues whenever CCIP is upgraded.
## Tools Used
Manual Review

## Recommendation
Implement the advice given in the documentation.