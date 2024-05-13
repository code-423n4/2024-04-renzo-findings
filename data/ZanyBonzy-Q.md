# 1. Previous stategy deposits not migrated when new asset strategy is set

Links to affected code *

https://github.com/code-423n4/2024-04-renzo/blob/1c7cc4e632564349b204b4b5e5f494c9b0bc631d/contracts/Delegation/OperatorDelegator.sol#L106

https://github.com/code-423n4/2024-04-renzo/blob/1c7cc4e632564349b204b4b5e5f494c9b0bc631d/contracts/Delegation/OperatorDelegator.sol#L327

## Impact

If a new strategy is set, there's no check to see if there's an existing `strategy` or transfer the current's strategy balance to the new one. Setting a new stategy doesn't migrate previous stategy's tokens to the new one which and can cause previous balances to be overwritten and issues with accounting.

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
The token balance is gotten from the `getTokenBalanceFromStrategy` function which will be overwritten if a new asset strategy is set. The value is used in calculating TVLs which is used extensively in assets deposits and redemptions.
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
***

# 2. Should introduce a minimum `ezETH` amount parameter to receive upon deposits.

Lines of code* 

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L491

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L592

### Impact

When users deposit into the protocol through the `deposit` and `depositETH` function, there's no way for intoduce the minimum amount of ezETH they'd like to receive. Considering that the calculated ezETH is dependent on oracle prices of the collateral token being deposited, the value of which is used to calculate how much ezETH to mint to the users, they have no way of predicting how many `ezETH` they will get back at the moment of minting, as the prices could be updated while the request is in the mempool. This leaves them vulnerable to unfavourable slippage or sandwich attacks.

```solidity
    function deposit(
        IERC20 _collateralToken,
        uint256 _amount,
        uint256 _referralId
    ) public nonReentrant notPaused {
        // Verify collateral token is in the list - call will revert if not found
        uint256 tokenIndex = getCollateralTokenIndex(_collateralToken);

        // Get the TVLs for each operator delegator and the total TVL
        (
            uint256[][] memory operatorDelegatorTokenTVLs,
            uint256[] memory operatorDelegatorTVLs,
            uint256 totalTVL
        ) = calculateTVLs();

        // Get the value of the collateral token being deposited
        uint256 collateralTokenValue = renzoOracle.lookupTokenValue(_collateralToken, _amount);
...
        // Calculate how much ezETH to mint
        uint256 ezETHToMint = renzoOracle.calculateMintAmount(
            totalTVL,
            collateralTokenValue,
            ezETH.totalSupply()
        );

        // Mint the ezETH
        ezETH.mint(msg.sender, ezETHToMint);

        // Emit the deposit event
        emit Deposit(msg.sender, _collateralToken, _amount, ezETHToMint, _referralId);
    }
```
### Recommended Mitigation Steps

Introduce a minimum amount out parameter.

***

# 3. `setRenzoDeposit` should check if contract is paused

Lines of code*

https://github.com/code-423n4/2024-04-renzo/blob/1c7cc4e632564349b204b4b5e5f494c9b0bc631d/contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L130

### Impact

From the comment in the constructor of ConnextReceiver.sol, the contract is paused so as to be able to setup `xRenzoDeposit` address 

```solidity
    constructor(address _connext, address _xRenzoBridgeL1, uint32 _connextEthChainDomain) {
...
        // Pause The contract to setup xRenzoDeposit
        _pause();
    }
```

And the `setRenzoDeposit` is used to set or potentially update the `xRenzoDeposit` address, but it's missing a check for contract's current paused status, meaning that the address can be set up whether the contract is paused or not, which goes against the desired behaviour of the contract. 

```solidity
    /**
     * @notice This function updates the xRenzoDeposit Contract address
     * @dev This should be a permissioned call (onlyOnwer)
     * @param _newXRenzoDeposit New xRenzoDeposit Contract address
     */
    function setRenzoDeposit(address _newXRenzoDeposit) external onlyOwner {
        if (_newXRenzoDeposit == address(0)) revert InvalidZeroInput();
        emit XRenzoDepositUpdated(_newXRenzoDeposit, address(xRenzoDeposit));
        xRenzoDeposit = IxRenzoDeposit(_newXRenzoDeposit);
    }
```

### Recommended Mitigation Steps
Consider introducing a `whenPaused` modifier or check if contract is paused before updating the address.

***



# 4. Unspend allowances can break contract, should approve to 0 first

Lines of code* 

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L84-L86

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Bridge/L1/xRenzoBridge.sol#L181

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Bridge/L2/xRenzoDeposit.sol#L369

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Bridge/L2/xRenzoDeposit.sol#L429

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Delegation/OperatorDelegator.sol#L164

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Delegation/OperatorDelegator.sol#L297

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Deposits/DepositQueue.sol#L142

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/RestakeManager.sol#L552

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/RestakeManager.sol#L559

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/RestakeManager.sol#L664

### Impact
None of the various use of the `safeApprove` function approved to zero. Openzeppelin's `safeApprove` function is used to prevent approval front-runs by enforcing first approving to 0, then to a new amount. It's implemented as following:

```solidity
    function safeApprove(
        IERC20 token,
        address spender,
        uint256 value
    ) internal {
        // safeApprove should only be called when setting an initial allowance,
        // or when resetting it to zero. To increase and decrease it, use
        // 'safeIncreaseAllowance' and 'safeDecreaseAllowance'
        require(
            (value == 0) || (token.allowance(address(this), spender) == 0),
            "SafeERC20: approve from non-zero to non-zero allowance"
        );
        _callOptionalReturn(token, abi.encodeWithSelector(token.approve.selector, spender, value));
    }
```
For instance, in the `_trade` function in xRenzoDeposit.sol, in a case of an very extremly profitable swap in which not all approved tokens are used, the remaining unspent allowance, not zeroed out will cause any subsequent calls to approve connext to fail.

```solidity
    function _trade(uint256 _amountIn, uint256 _deadline) internal returns (uint256) {
        // Approve the deposit asset to the connext contract
        depositToken.safeApprove(address(connext), _amountIn);
...
        // Swap the tokens
        uint256 amountNextWETH = connext.swapExact(
            swapKey,
            _amountIn,
            address(depositToken),
            address(collateralToken),
            minOut,
            _deadline
        );

...
    }
```

### Recommended Mitigation Steps

Consider zeroing out approvals after transaction is done.

***

# 5. `getMintRate` reverting when there's no receiver and no oracle makes price updates by owner redundant.

Lines of code* 

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L320

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L291

### Impact
The contract owner can update token price. This can be done, regardless of if there's an oracle or a receiver or not.

```solidity
    function updatePriceByOwner(uint256 price) external onlyOwner {
        return _updatePrice(price, block.timestamp);
    }
```

The issue is that this fact is not taken into consideration when getting mint rate. The function reverts if there's no recevier and no oracle, tentatively ignoring the price updates from the owner. 

```solidity
    function getMintRate() public view returns (uint256, uint256) {
        // revert if PriceFeedNotAvailable
        if (receiver == address(0) && address(oracle) == address(0)) revert PriceFeedNotAvailable();
        if (address(oracle) != address(0)) {
            (uint256 oraclePrice, uint256 oracleTimestamp) = oracle.getMintRate();
            return
                oracleTimestamp > lastPriceTimestamp
                    ? (oraclePrice, oracleTimestamp)
                    : (lastPrice, lastPriceTimestamp);
        } else {
            return (lastPrice, lastPriceTimestamp);
        }
    }
```
Even if owner updates the prices constantly, as long as both receivers and oracles are down, the price updates will be potentially useless, rendering the function more or less redundant.

### Recommended Mitigation Steps
Consider removing the check, if price feed has not been updated by the owner in a while, the `lastPriceTimestamp` will revert in the `deposit` function where it's used as it reverts when timestamp is stale. This prevents the use of stale prices while also making use of the prices as updated by the owner.

```solidity
    function _deposit(
        uint256 _amountIn,
        uint256 _minOut,
        uint256 _deadline
    ) internal returns (uint256) {
...
        // Fetch price and timestamp of ezETH from the configured price feed
        (uint256 _lastPrice, uint256 _lastPriceTimestamp) = getMintRate();

        // Verify the price is not stale
        if (block.timestamp > _lastPriceTimestamp + 1 days) {
            revert OraclePriceExpired();
        }
```

***

# 6. Use of a general max mint/burn limit for bridge can introduce possibility of DDOS

Lines of code* 

https://github.com/code-423n4/2024-04-renzo/blob/1c7cc4e632564349b204b4b5e5f494c9b0bc631d/contracts/Bridge/xERC20/contracts/XERC20.sol#L152

https://github.com/code-423n4/2024-04-renzo/blob/1c7cc4e632564349b204b4b5e5f494c9b0bc631d/contracts/Bridge/xERC20/contracts/XERC20.sol#L163

### Impact

In XERC20.sol, there's a max limit introduced on the bridge, which indicates how much can be minted or burned by a bridge at a time. However, the protocol introduces no limit on how much tokens a user can mint/burn at a time.

```solidity
    function mintingMaxLimitOf(address _bridge) public view returns (uint256 _limit) {
        _limit = bridges[_bridge].minterParams.maxLimit;
    }
```

```solidity
    function burningMaxLimitOf(address _bridge) public view returns (uint256 _limit) {
        _limit = bridges[_bridge].burnerParams.maxLimit;
    }

```

This introduces a consequence in which whale addresses can easily use up the mint and burn limits of bridges, causing a form of DDOS for other users.
Griefers can also take advantage of this by maliciously frontrunning other users transactions with just enough amount to cause their transaction to exceed bridge limit.
In a more extreme or coordinated attack, attackers can continously mint and burn tokens (mint and burn limits are independent of each other) to slowly meet the bridge limits causing a problems for the network and bad user experience.

### Recommended Mitigation Steps

A good way is to put a max limit on how much users can mint or burn at a time.

***

# 7. `updateXRenzoBridgeL1` should check if contract is paused

Lines of code* 

https://github.com/code-423n4/2024-04-renzo/blob/1c7cc4e632564349b204b4b5e5f494c9b0bc631d/contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L96

### Impact

From the comment in the constructor of ConnextReceiver.sol, the contract is paused so as to be able to setup `xRenzoDeposit` address 

```solidity
    constructor(
        address _router,
        address _xRenzoBridgeL1,
        uint64 _ccipEthChainSelector
    ) CCIPReceiver(_router) {
...
        // Pause The contract to setup xRenzoDeposit
        _pause();
    }
```
And the `updateXRenzoBridgeL1` is used to set or potentially update the `xRenzoBridgeL1` address, but it's missing a check for contract's current paused status, meaning that the address can be set up whether the contract is paused or not, which goes against the desired behaviour of the contract. 

```solidity
    /**
     * @notice This function updates the xRenzoBridge Contract address deployed on Ethereum L1
     * @dev This should be a permissioned call (onlyOnwer)
     * @param _newXRenzoBridgeL1 New address of xRenzoBridge Contract
     */
    function updateXRenzoBridgeL1(address _newXRenzoBridgeL1) external onlyOwner {
        if (_newXRenzoBridgeL1 == address(0)) revert InvalidZeroInput();
        emit XRenzoBridgeL1Updated(_newXRenzoBridgeL1, xRenzoBridgeL1);
        xRenzoBridgeL1 = _newXRenzoBridgeL1;
    }
```

### Recommended Mitigation Steps
Consider introducing a `whenPaused` modifier or check if contract is paused before updating the address.

***

# 8. Conflicting function logics in RewardHandler.sol

Lines of code* 
https://github.com/code-423n4/2024-04-renzo/blob/1c7cc4e632564349b204b4b5e5f494c9b0bc631d/contracts/Rewards/RewardHandler.sol#L52

https://github.com/code-423n4/2024-04-renzo/blob/1c7cc4e632564349b204b4b5e5f494c9b0bc631d/contracts/Rewards/RewardHandler.sol#L58

### Impact

RewardHandler holds the `_forwardETH` function which is responsible transferring `ETH` in the contract to the `rewarddesitnation`. 
THe function can be triggered through the `receive` and `forwardRewards` functions. `forwardRewards` function is protected by the `onlyNativeEthRestakeAdmin` modifier, hinting that only the Native Eth Restake Admin should be able to call the function, but the receive function can be triggered by anyone. They both perform the same function.

```solidity
    /// @dev Forwards all native ETH rewards to the DepositQueue contract
    /// Handle ETH sent to this contract from outside the protocol that trigger contract execution - e.g. rewards
    receive() external payable nonReentrant {
        _forwardETH();
    }

```

```solidity
    /// @dev Forwards all native ETH rewards to the DepositQueue contract
    /// Handle ETH sent to this contract from validator nodes that do not trigger contract execution - e.g. rewards
    function forwardRewards() external nonReentrant onlyNativeEthRestakeAdmin {
        _forwardETH();
    }
```

Important to also note that the `forwardRewards` function is not marked payable, so admin can't directly send ETH through the function. If he desires to send ETH, he has to send it through the receive function which triggers `_forwardETH` anyway.

### Recommended Mitigation Steps

If truly desired that only the admin should be able to forward ETH, consider removing `_forwardETH` from `receive`

```solidity
    /// @dev Forwards all native ETH rewards to the DepositQueue contract
    /// Handle ETH sent to this contract from outside the protocol that trigger contract execution - e.g. rewards
    receive() external payable nonReentrant {
   //     _forwardETH();
    }

```

On the contrary, the `onlyNativeEthRestakeAdmin` modifier can be removed from `forwardRewards` so anyone can call it, or removing the function entirely.


```solidity
    /// @dev Forwards all native ETH rewards to the DepositQueue contract
    /// Handle ETH sent to this contract from validator nodes that do not trigger contract execution - e.g. rewards
    function forwardRewards() external nonReentrant /**onlyNativeEthRestakeAdmin */{
        _forwardETH();
    }
```


***

# 9. Uncleared collateral token limits will cause issues upon readding tokens

Links to affected code *

https://github.com/code-423n4/2024-04-renzo/blob/1c7cc4e632564349b204b4b5e5f494c9b0bc631d/contracts/RestakeManager.sol#L220

https://github.com/code-423n4/2024-04-renzo/blob/1c7cc4e632564349b204b4b5e5f494c9b0bc631d/contracts/RestakeManager.sol#L244

https://github.com/code-423n4/2024-04-renzo/blob/1c7cc4e632564349b204b4b5e5f494c9b0bc631d/contracts/RestakeManager.sol#L709

https://github.com/code-423n4/2024-04-renzo/blob/1c7cc4e632564349b204b4b5e5f494c9b0bc631d/contracts/RestakeManagerStorage.sol#L65

### Impact

RestakeManagerAdmin can add or remove collateral tokens as its needed. Upon adding collateral token, by default, the Tvl Limit is non existent, meaning users can deposit as much as they want without any restrictions.

```solidity
    function deposit(
        IERC20 _collateralToken,
        uint256 _amount,
        uint256 _referralId
    ) public nonReentrant notPaused {
...
        // Enforce individual token TVL limit if set, 0 means the check is not enabled
        if (collateralTokenTvlLimits[_collateralToken] != 0) {
            // Track the current token's TVL
            uint256 currentTokenTVL = 0;

            // For each OD, add up the token TVLs
            uint256 odLength = operatorDelegatorTokenTVLs.length;
            for (uint256 i = 0; i < odLength; ) {
                currentTokenTVL += operatorDelegatorTokenTVLs[i][tokenIndex];
                unchecked {
                    ++i;
                }
            }

            // Check if it is over the limit
            if (currentTokenTVL + collateralTokenValue > collateralTokenTvlLimits[_collateralToken])
                revert MaxTokenTVLReached();
        }
...
    }
```

RestakeManagerAdmin can set a tvl limit for the collateral token which updates the [collateralTokenTvlLimits](https://github.com/code-423n4/2024-04-renzo/blob/1c7cc4e632564349b204b4b5e5f494c9b0bc631d/contracts/RestakeManagerStorage.sol#L65) mapping. 

```solidity
    function setTokenTvlLimit(IERC20 _token, uint256 _limit) external onlyRestakeManagerAdmin {
        // Verify collateral token is in the list - call will revert if not found
        getCollateralTokenIndex(_token);

        // Set the limit
        collateralTokenTvlLimits[_token] = _limit;

        emit CollateralTokenTvlUpdated(_token, _limit);
    }
```

However, upon removing collateral, this mapping is not cleared, the token is only removed.

```solidity
    function removeCollateralToken(
        IERC20 _collateralTokenToRemove
    ) external onlyRestakeManagerAdmin {
        // Remove it from the list
        uint256 tokenLength = collateralTokens.length;
        for (uint256 i = 0; i < tokenLength; ) {
            if (address(collateralTokens[i]) == address(_collateralTokenToRemove)) {
                collateralTokens[i] = collateralTokens[collateralTokens.length - 1];
                collateralTokens.pop();
                emit CollateralTokenRemoved(_collateralTokenToRemove);
                return;
            }
            unchecked {
                ++i;
            }
        }

        // If the item was not found, throw an error
        revert NotFound();
    }
```

So upon readding the collateral token, the previously set tvllimit will still hold. Depending on how the protocol desires to work with collateral tokens that are readded, this can lead unexpected behaviours and reversions.

### Recommended Mitigation Steps

Unless such a behaviour is desired, its more advisable to remove tvl limits upon collateral token removal.

```solidity
    function removeCollateralToken(
        IERC20 _collateralTokenToRemove
    ) external onlyRestakeManagerAdmin {
        // Remove it from the list
        uint256 tokenLength = collateralTokens.length;
        for (uint256 i = 0; i < tokenLength; ) {
            if (address(collateralTokens[i]) == address(_collateralTokenToRemove)) {
                collateralTokenTvlLimits[_collateralTokenToRemove] = 0; ++++
                collateralTokens[i] = collateralTokens[collateralTokens.length - 1];
                collateralTokens.pop();
                emit CollateralTokenRemoved(_collateralTokenToRemove);
                return;
            }
            unchecked {
                ++i;
            }
        }

        // If the item was not found, throw an error
        revert NotFound();
    }
```
***
# 10. Include a check to ensure the set `_rewardDestination` is not the RewardHandler address

Lines of code* 

https://github.com/code-423n4/2024-04-renzo/blob/1c7cc4e632564349b204b4b5e5f494c9b0bc631d/contracts/Rewards/RewardHandler.sol#L77

### Impact
Setting `RewardHandler` as `_rewardDestination` will trigger an OOG infinte loop scenario whenever the contract recevies ETH. Or when the NativeEthRestakeAdmin tries to forward rewards.

The `_forwardETH` function will send the balance to the `rewardDestination`, in this case, `RewardHandler` which holds a `receive` function.
```solidity
    function _forwardETH() internal {
        uint256 balance = address(this).balance;
        if (balance == 0) {
            return;
        }

        (bool success, ) = rewardDestination.call{ value: balance }("");
        if (!success) revert TransferFailed();
    }
```

The receive function will again trigger the `_forwardETH` function and so the loop will continue, triggerring an out of gas error anytime ETH is deposted into the contract. The same applies for the `forwardRewards` function.
```solidity
    receive() external payable nonReentrant {
        _forwardETH();
    }
```
### Recommended Mitigation Steps

Include a check in `setRewardDestination` function.

```solidity
    function setRewardDestination(
        address _rewardDestination
    ) external nonReentrant onlyRestakeManagerAdmin {
        if (address(_rewardDestination) == address(0x0) || address(_rewardDestination) == RewardsHandler) revert();  ++++

        rewardDestination = _rewardDestination;

        emit RewardDestinationUpdated(_rewardDestination);
    }
}
```
***
# 11. Use of the same staleness window for all assets is not advisable

Lines of code*

https://github.com/code-423n4/2024-04-renzo/blob/1c7cc4e632564349b204b4b5e5f494c9b0bc631d/contracts/Oracle/RenzoOracle.sol#L26

### Impact
RenzoOracle uses the same a stale window of about a day and 1 minute for all the tokens that are in use.

```solidity
 uint256 constant MAX_TIME_WINDOW = 86400 + 60;
```

This value is used in [`lookupTokenValue`](https://github.com/code-423n4/2024-04-renzo/blob/1c7cc4e632564349b204b4b5e5f494c9b0bc631d/contracts/Oracle/RenzoOracle.sol#L71) and [`lookupTokenAmountFromValue`](https://github.com/code-423n4/2024-04-renzo/blob/1c7cc4e632564349b204b4b5e5f494c9b0bc631d/contracts/Oracle/RenzoOracle.sol#L85C14-L85C40) functions to ensure that returned prices are not stale. The returned values are then used to get token prices upon collateral token [deposit](https://github.com/code-423n4/2024-04-renzo/blob/1c7cc4e632564349b204b4b5e5f494c9b0bc631d/contracts/RestakeManager.sol#L507) or [withdrawal](https://github.com/code-423n4/2024-04-renzo/blob/1c7cc4e632564349b204b4b5e5f494c9b0bc631d/contracts/Withdraw/WithdrawQueue.sol#L229) and to calculate [rewards](https://github.com/code-423n4/2024-04-renzo/blob/1c7cc4e632564349b204b4b5e5f494c9b0bc631d/contracts/RestakeManager.sol#L688) and [tvl](https://github.com/code-423n4/2024-04-renzo/blob/1c7cc4e632564349b204b4b5e5f494c9b0bc631d/contracts/RestakeManager.sol#L307-L317).

Currently, the tokens in use have relatively the same heartbeat, so its not really much of a problem.
https://data.chain.link/feeds/ethereum/mainnet/steth-eth
https://data.chain.link/feeds/ethereum/mainnet/ezeth-eth

But, considering that collateral tokens can be [added](https://github.com/code-423n4/2024-04-renzo/blob/1c7cc4e632564349b204b4b5e5f494c9b0bc631d/contracts/RestakeManager.sol#L220), some of the added tokens may have shorter heartbeats, which will lead to protocol working with stale prices.

### Recommended Mitigation Steps
Consider using a mapping to set each collateral token, to its desired heartbeat. That way differences in hearbeats can be properly handled.
***

# 12. Price updates can be sandwiched

Links to affected code *

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L310

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L320

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L355-L356

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L456

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L245

### Impact

The protocol uses its own oracle for receiving current prices of ezETH price. The data can be updated by either the receiver or the owner. This opens an opportunity for a sandwich attack as users can monitor the mempool for price update transactions to gain an unfair advantage depending on what direction the price update is going to be. The `updatePriceByOwner` function is more vulnerable to this since the function doesn't exist in an atomic form, unlike the `updatePrice` function.

```solidity
    function updatePriceByOwner(uint256 price) external onlyOwner {
        return _updatePrice(price, block.timestamp);
    }
```

***

# 13. Inability to change native token status will break XERC20Lockbox

Links to affected code *

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L47

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L55

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L130-L135

### Impact

There are cases where chains have changed their native tokens, although rare. Polygon chain for instance is currently in the process of [changing](https://polygon.technology/blog/polygon-2-0-tokenomics) their native token from [`MATIC`](https://etherscan.io/address/0x7d1afa7b718fb893db30a3abc0cfc608aacfebb0) to [`POL`](https://etherscan.io/address/0x455e53CBB86018Ac2B8092FdCd39d8444aFFC3F6) planning on fully replacing its token status. A change like this on any of the supported chains will break functionality of XERC20Lockbox.sol and possibly force redeployment. Withdrawals will be virtually impossible leading to locked funds.


```solidity
    function _withdraw(address _to, uint256 _amount) internal {
...
        if (IS_NATIVE) {
            (bool _success, ) = payable(_to).call{ value: _amount }(""); //@note will no longer work as token is no longer native on chain.
            if (!_success) revert IXERC20Lockbox_WithdrawFailed();
        } else {
            ERC20.safeTransfer(_to, _amount);
        }
    }
```

### Recommended Mitigation Steps

Consider introducing a function to toggle the native status of the token.

***

# 14. `inflationPercentage` is misspelt

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L135

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L140

```solidity
        uint256 inflationPercentaage = (SCALE_FACTOR * _newValueAdded) /
        (_currentValueInProtocol + _newValueAdded);

        // Calculate the new supply
        uint256 newEzETHSupply = (_existingEzETHSupply * SCALE_FACTOR) /
        (SCALE_FACTOR - inflationPercentaage);

```

# 15. Should introduce a minimum deposit amount to protect from first depositor inflation attacks.

Links to affected code *

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L123

### Impact
There's no minimum amount that can be deposited leading to the `inflationPercentaage` risking being forcefully scaled up, to either mint large amount of ezeth or prevent future depositors from being able to deposit.

The [`calculateMintAmount`](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L123) function is called when users call the `deposit`/`depositETH` function is called in RestakManager.sol.This allows for depositing as little as 1 wei of tokens. A malicious user can use this to his advantage to manipulate the `inflationPercentaage` parameter so as to mint large amount of ezETH or prevent future depositors from being able to deposit.

The function initially checks if the exisiting ezETHSupply is 0, upon which the deposited amount is returned. By depositing 1 wei of token the returned ezETHToMint is 1, and 1 wei of ezETH is minted to the user.

Depending on how much TVL is available in the protocol at this moment, the next deposit by the same user might will result in subsequent user deposits that less than the amount the attacker had initially sent to return them zero tokens or not being able to mint at all.

### Recommended Mitigation Steps

The way UniswapV2 prevents this is by requiring a minimum deposit amount and sending 1000 initial shares to the zero address to make this attack more expensive.


# 16. Steth rebasing property will break approvals, accounting and various protocol limits

### Impact

The contract performs transfers and approvals without checking for token balances before and after. This will lead to issues as the protcol aims to support `stETH` which is a rebasing token. It's increase or decrease as the balance of Eth in certain pools changes to maintain peg can also break the various deposit, tvl and collateral limits.

# 17. `stETH`/`ETH` chainlink oracle has too long of heartbeat and deviation threshold

### Impact

Protocol uses `stETH`/`ETH` chainlink oracle to get its price. This can be problematic (due to the possibility of arbitrage) since stETH/ETH has a 24 hour heartbeat and a 2% deviation threshold. This deviation in price could easily cause loss of funds to the user. The large hearbeat and deviation means that the price can move up to 2% or 24 hours before a price update is triggered. The result is that the on-chain price could be much different than the true stETH price. Consider using Use the `stETH`/`USD` oracle instead because it has a 1-hour heartbeat and a 1% deviation threshold.