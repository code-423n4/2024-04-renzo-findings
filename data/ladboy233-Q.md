## Summary

| No | Title |
| --- | --- |
| [L-01] | Loss of blast gas yield for xERC20 token on blast |
| [L-02] | Malicious proxy admin can upgrade contract and remove fund |
| [L-03] | Hardcoded default 200000 gas limit might revert on executing the transaction in L2 when deliver the price via Chainlink CCIP |
| [L-04] | Use `safeTransfer` instead of `transfer` |
| [L-05]  | `wBETHToken.exchangeRate` is not validated |
| [L-06] | `TimelockController.`sol changes minDelay applies to active proposal |
| [L-07] | In withdrawal queue, update cooldown impact current claim request.
| [L-08] | Loss of blast point if the xERC20 token contract in blast network hold USDB / WETH
| [NC-01] | Typos

## Low findings
### [L-01] Loss of blast gas yield for xERC20 token on blast.
##### Impact
According to the [docs](https://docs.blast.io/building/guides/gas-fees), xERC20 token will be deployed in blast network also and blast network has built-in feature to distribute gas spent to user, but the xERC20 token does not follow the integration guide, result in loss of gas that is being distributed to users. 

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Bridge/xERC20/contracts/XERC20.sol

##### Recommendation
Follow the Blast Network docs to avoid loss of gas. 

### [L-02] Malicious proxy admin can upgrade contract and remove fund 
##### Impact
In lockbox, user can deposit underlying token and mint xERC20 token and user can burn xERC20 token and redeem the underlying token, but if malicious `_proxyAdmin` perform a upgrade on lockbox and transfer the underlying token out, the fund is lost.

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L105
```solidity
    /**
     * @notice Deploys an XERC20Lockbox contract using CREATE3
     *
     * @dev When deploying a lockbox for the gas token of the chain, then, the base token needs to be address(0)
     * @param _xerc20 The address of the xerc20 that you want to deploy a lockbox for
     * @param _baseToken The address of the base token that you want to lock
     * @param _isNative Whether or not the base token is the native (gas) token of the chain. Eg: MATIC for polygon chain
     * @param _proxyAdmin The address of the proxy admin - will have permission to upgrade the lockbox (should be a dedicated account or contract to manage upgrades)
     * @return _lockbox The address of the lockbox
     */

    // @audit
    // frontrun
    function deployLockbox(
        address _xerc20,
        address _baseToken,
        bool _isNative,
        address _proxyAdmin
    ) external returns (address payable _lockbox) {
        if ((_baseToken == address(0) && !_isNative) || (_isNative && _baseToken != address(0))) {
            revert IXERC20Factory_BadTokenAddress();
        }

        if (XERC20(_xerc20).owner() != msg.sender) revert IXERC20Factory_NotOwner();
        if (_lockboxRegistry[_xerc20] != address(0)) revert IXERC20Factory_LockboxAlreadyDeployed();

        _lockbox = _deployLockbox(_xerc20, _baseToken, _isNative, _proxyAdmin);

        emit LockboxDeployed(_lockbox);
    }
```
##### Recommendation
Don't allow `_proxyAdmin` to transfer the funds.

### [L-03] Hardcoded default 200000 gas limit might revert on executing the transaction in L2 when deliver the price via Chainlink CCIP

##### Impact

Gas limit is hardcoded to default 200000 gas which might revert on executing the transaction in L2 when deliver the price via Chainlink CCIP
https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L225

```solidity
    function sendPrice (
        for (uint256 i = 0; i < _destinationParam.length; ) {
            Client.EVM2AnyMessage memory evm2AnyMessage = Client.EVM2AnyMessage({
                receiver: abi.encode(_destinationParam[i]._renzoReceiver), // ABI-encoded xRenzoDepsot contract address
                data: _callData, // ABI-encoded ezETH exchange rate with Timestamp
                tokenAmounts: new Client.EVMTokenAmount[](0), // Empty array indicating no tokens are being sent
                extraArgs: Client._argsToBytes(
                    // Additional arguments, setting gas limit
@>                  Client.EVMExtraArgsV1({ gasLimit: 200_000 })
                ),
                // Set the feeToken  address, indicating LINK will be used for fees
                feeToken: address(linkToken)
            });
    }
)
```

##### Recommendation
Make the gaslimit of `client.EVMExtraArgsV1({ gasLimit: 200_000 })` changeable by from the input.


### [L-04] Use `safeTransfer` instead of `transfer` 

##### Impact
It is good to add a require() statement that checks the return value of token transfers or to use something like OpenZeppelin’s safeTransfer/safeTransferFrom unless one is sure the given token reverts in case of a failure. Failure to do so will cause silent failures of transfers and affect token accounting in contract.

For example, Some tokens do not implement the ERC20 standard properly but are still accepted by most code that accepts ERC20 tokens. For example Tether (USDT)'s transfer() and transferFrom() functions do not return booleans as the specification requires, and instead have no return value. When these sorts of tokens are cast to IERC20, their function signatures do not match and therefore the calls made, revert.

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L302C1-L309C10

```solidity
    function claim(uint256 withdrawRequestIndex) external nonReentrant {
        // send selected redeem asset to user
        if (_withdrawRequest.collateralToken == IS_NATIVE) {
@>         payable(msg.sender).transfer(_withdrawRequest.amountToRedeem);
            // @audit this should use call. [low]
        } else {
@>         IERC20(_withdrawRequest.collateralToken).transfer(
                msg.sender,
                _withdrawRequest.amountToRedeem
            );
            // @audit this should use safeTransfer. [low]
        }
        // emit the event
        emit WithdrawRequestClaimed(_withdrawRequest);
    }
```

##### Recommendation

Use `safeTransfer` instead of `transfer`.
```diff
    function claim(uint256 withdrawRequestIndex) external nonReentrant {

        // send selected redeem asset to user
        if (_withdrawRequest.collateralToken == IS_NATIVE) {
-           payable(msg.sender).transfer(_withdrawRequest.amountToRedeem);
+           payable(msg.sender).safeTransfer(_withdrawRequest.amountToRedeem);
        } else {
-           IERC20(_withdrawRequest.collateralToken).transfer(
                msg.sender,
                _withdrawRequest.amountToRedeem
            );

+           IERC20(_withdrawRequest.collateralToken).safeTransfer(
                msg.sender,
                _withdrawRequest.amountToRedeem
            );
        }
        // emit the event
        emit WithdrawRequestClaimed(_withdrawRequest);
    }
```
### [L-05] `wBETHToken.exchangeRate` is not validated

##### Impact
As we can see, the wBETHToken.exchangeRate quries the exchange rate from wBETHToken contract and it relies on the admin of the wBETH token to update the exchange rate on time and accurately and frequent. It doesn't validate if the exchange rate is fresh.

Onchain address of `WrapTokenV2ETH` is https://etherscan.io/address/0xfe928a7d8be9c8cece7e97f0ed5704f4fa2cb42a#code#F22#L205

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Binance/WBETHShim.sol#L69

```solidity
    function _getWBETHData()
        internal
        view
        returns (
            uint80 roundId,
            int256 answer,
            uint256 startedAt,
            uint256 updatedAt,
            uint80 answeredInRound
        )
    {
        // @audit
        // https://etherscan.io/address/0xfe928a7d8be9c8cece7e97f0ed5704f4fa2cb42a#code#F22#L205

        // does not validate if the exchange rate is fresh
        return (0, int256(wBETHToken.exchangeRate()), 0, block.timestamp, 0);
    }
```

##### Recommendation
Validate the exchange rate.

### [L-06] `TimelockController.sol` changes minDelay applies to active proposal

##### Impact
`TimelockController::updateDelay` function is used to update the `_minDelay` for any operations through Timelock contract for execution. But if a certain proposal  is already made and `TimelockController::updateDelay` it will impact the current proposal which will delay the of the current proposal.

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L399C1-L407C1

```solidity
    function updateDelay(uint256 newDelay) external virtual {
        require(msg.sender == address(this), "TimelockController: caller must be timelock");
        emit MinDelayChange(_minDelay, newDelay);
        _minDelay = newDelay;
    }
```
##### Recommendation
Changes such as update delay should not be allowed to make when there is an active proposal in Timelock contract.

### [L-07] In withdrawal queue, update cooldown impact current claim request.
`WithdrawQueueupdate::CoolDownPeriod` function is used to update the coolDownPeriod for withdrawal requests. But if a certain withdrawal request is already made and `updateCoolDownPeriod` it will impact the current claim request which will delay the current `updateCoolDownPeriod` of the current request.

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L129

##### Impact
```solidity
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
##### Recommendation
When there is a withdrawal request already, it should be called.

### [L-08] Loss of blast point if the xERC20 token contract in blast hold USDB / WETH

According to the contest readme, the protocol wants to deploy xERC20 token related contract to blast,

However, 

If the xERC20 / lock box contract hold USDB / WETH,

the smart contract accurs points.

https://docs.blast.io/airdrop/developers#blast-points

but without setting a point admin, the point that can be converted to airdrop is lost.


### [NC-01] Typos
##### Impact
Here, inflationPercentage is a typo as it is written as inflationPercentaage in `calculateMintAmount`

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L135

```solidity
    function calculateMintAmount(
        uint256 _currentValueInProtocol,
        uint256 _newValueAdded,
        uint256 _existingEzETHSupply
    ) external pure returns (uint256) {
       
@>      uint256 inflationPercentaage = (SCALE_FACTOR * _newValueAdded) /
            (_currentValueInProtocol + _newValueAdded);
    }
```
##### Recommendation
Change the following:
```diff
    function calculateMintAmount(
        uint256 _currentValueInProtocol,
        uint256 _newValueAdded,
        uint256 _existingEzETHSupply
    ) external pure returns (uint256) {
-     uint256 inflationPercentaage = (SCALE_FACTOR * 
       _newValueAdded) /
            (_currentValueInProtocol + _newValueAdded);
        
+      uint256 inflationPercentage = (SCALE_FACTOR * 
       _newValueAdded) /
            (_currentValueInProtocol + _newValueAdded);
    }
```