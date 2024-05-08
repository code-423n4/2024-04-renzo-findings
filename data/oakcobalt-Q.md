### Low-01 Risk of fund loss if tx reverts on Blast chain
**Instances(1)**
In contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol, when sending assets to Blast chain `bridgeTo` will initiate token bridge call on L1 Blast bridge (`L1StandardBridge(blastStandardBridge).bridgeERC20To`).

There is no guarantee that the crosschain token bridging will succeed on the destination. And if the token briding fails on destination, a withdrawal process will be started and [user will have to claim the tokens on L1](https://ethereum.org/en/developers/tutorials/optimism-std-bridge-annotated-code/#deposit-flow-layer-2). According to [L1StandardBridge.sol](https://etherscan.io/address/0xd2c23a5a280aff9182b953579f62edddf1c7ff22#code#F5#L181), tokens will be returned to sender(LockboxAdapterBlast.sol) on the source chain.

When brdigeERC20 fails on destination (e.g. due to insufficient `minGasLimit` forwarded), LockboxAdapterBlast.sol will have no methods to claim erc20 tokens.  Funds will be locked.
```solidity
//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol
    function bridgeTo(
        address _to,
        address _erc20,
        address _remoteToken,
        uint256 _amount,
|>      uint32 _minGasLimit,
        bytes calldata _extraData
    ) external {
...
        L1StandardBridge(blastStandardBridge).bridgeERC20To(
            xerc20,
            _remoteToken,
            _to,
            _amount,
            _minGasLimit,
            _extraData
        );
```
(https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L61)

Note that `minGasLimit` is minimum amount of gas that the bridge can be relayed with and if this value is too low, bridging will fail at the destination.

Recommendations:
Considering adding claiming failed ERC20Bridge flow in LockboxAdapterBlast.sol.

### Low-02 Incorrect comment - Send the price feed from L1->L2
**Instances(1)**
In contracts/Bridge/L1/xRenzoBridge.sol, `sendPrice()` has incorrect code comment. `sendPrice` is used to send priceFeed from L1 to L2.

```solidity
//contracts/Bridge/L1/xRenzoBridge.sol
    /**
|>   * @notice  Send the price feed to the L1
     * @dev     Calls the getRate() function to get the current ezETH to ETH price and sends to the L2.
     *          This should be a permissioned call for only PRICE_FEED_SENDER role
     * @param _destinationParam array of CCIP destination chain param
     * @param _connextDestinationParam array of connext destination chain param
     */
    function sendPrice(
...
```
(https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L204)

Recommendations:
Change to `Send the price feed from L1 to L2`.

### Low-03 Missing `reentrancyGuardUpgradable` init in initialize call
**Instances(3)**
There are multiple contracts that inherit Openzepplin's reentrancyGuardUpgradable contract. However, the `__ReentrancyGuard_init()` is missing from `initialize()` in some cases.
(1)
contracts/Bridge/L1/xRenzoBridge.sol
```solidity
    function initialize(
```
(https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L70)
(2)
contracts/Bridge/L2/xRenzoDeposit.sol
```solidity
    function initialize(
```
(https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L75)
(3)
contracts/Withdraw/WithdrawQueue.sol
```solidity
    function initialize(
```
(https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L64)

Recommendations:
Add `__ReentrancyGuard_init()` in `initialize()`.

### Low-04 if baseToken has non-18 decimal, XERC20 will have incorrect token balance accounting in XERC20Lockbox.sol
**Instances(1)**
In contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol,`_deposit` will directly use baseToken `_amount` as XERC20.mint amount. 

This is problematic if baseToken doesn't have 18 decimals. Because XERC20 is [permissionless deployed from XERC20Factory.sol](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L74) will always have the default 18 decimal (inherited from ERC20Upgradeable), this means when baseToken decimal differs XERC20Lockbox needs to scale the decimal difference.

```solidity
//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol
    function _deposit(address _to, uint256 _amount) internal {
        if (!IS_NATIVE) {
            ERC20.safeTransferFrom(msg.sender, address(this), _amount);
        }
       //@audit this only works if baseToken has 18 decimals
|>      XERC20.mint(_to, _amount);
        emit Deposit(_to, _amount);
    }
```
(https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L150)

Recommendations:
In xERC20LockBox::deposit, consider query the baseToken decimal and scale the amount value before passing to `XERC20.mint`.

### Low-05 Unnecessary code in for-loop - Consider moving withdrawer setter outside the for-loop.
**Instances(1)**
In contracts/Delegation/OperatorDelegator.sol, `queueWithdrawals()` sets `queuedWithdrawalParams[0].withdrawer` to the same `address(this)` value in a for-loop. This is unnecessary and wastes runtime gas.

```solidity
//contracts/Delegation/OperatorDelegator.sol
    function queueWithdrawals(
        IERC20[] calldata tokens,
        uint256[] calldata tokenAmounts
    ) external nonReentrant onlyNativeEthRestakeAdmin returns (bytes32) {
...
        for (uint256 i; i < tokens.length; ) {
...
            // set withdrawer as this contract address
            queuedWithdrawalParams[0].withdrawer = address(this);
...
            }
```
(https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L229)
Recommendations:
Move `queuedWithdrawalParams[0].withdrawer = address(this)` outside of for-loop.

### Low-06 `stakedButNotVerifiedEth` accoutning might be incorrect if the input validators' restake balance is greater than `_MAX_RESTAKED_BALANCE_GWEI_PER_VALIDATOR`, `totalTVLs` might be incorrect
**Instances(1)**
In contracts/Delegation/OperatorDelegator.sol, `verifyWithdrawalCredentials()` will verify validator credentials and decrease the `stakeButNotVerifiedETH` as the validator's balance is verified. 
```solidity
//contracts/Delegation/OperatorDelegator.sol
    function verifyWithdrawalCredentials(
        uint64 oracleTimestamp,
        BeaconChainProofs.StateRootProof calldata stateRootProof,
        uint40[] calldata validatorIndices,
        bytes[] calldata withdrawalCredentialProofs,
        bytes32[][] calldata validatorFields
    ) external onlyNativeEthRestakeAdmin {
...
        eigenPod.verifyWithdrawalCredentials(
            oracleTimestamp,
            stateRootProof,
            validatorIndices,
            withdrawalCredentialProofs,
            validatorFields
        );
        // Decrement the staked but not verified ETH
        for (uint256 i = 0; i < validatorFields.length; ) {
            uint64 validatorCurrentBalanceGwei = BeaconChainProofs.getEffectiveBalanceGwei(
                validatorFields[i]
            );
            //@audit In edge case: validatorCurrentBalanceGwei > _MAX_RESTAKED_BALANCE_GWEI_PER_VALIDATOR, stakedButNotVerifiedEth will be subtracted with an incorrect value.
|>          stakedButNotVerifiedEth -= (validatorCurrentBalanceGwei * GWEI_TO_WEI);
...
```
(https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L385)

However, the issue is the accounting of `stakeButNotVerifiedETH` didn't account for an edge case. The edge case: validator's effectiveBalance(`validatorCurrentBalanceGwei`) is [greater than _MAX_RESTAKED_BALANCE_GWEI_PER_VALIDATOR](https://github.com/Layr-Labs/eigenlayer-contracts/blob/15b679b08e7a3589ff83a5e84076ca4e0a00ec0b/src/contracts/pods/EigenPod.sol#L490-L491) (a preset cap in deployed EigenPod).

```solidity
//For Reference: EigenPod.sol
    function _verifyWithdrawalCredentials(
...
        if (validatorEffectiveBalanceGwei > MAX_RESTAKED_BALANCE_GWEI_PER_VALIDATOR) {
            validatorInfo.restakedBalanceGwei = MAX_RESTAKED_BALANCE_GWEI_PER_VALIDATOR;
...
```
(https://github.com/Layr-Labs/eigenlayer-contracts/blob/15b679b08e7a3589ff83a5e84076ca4e0a00ec0b/src/contracts/pods/EigenPod.sol#L490-L491)

This edge case will cause EigenPod to only use `_MAX_RESTAKED_BALANCE_GWEI_PER_VALIDATOR` and write to validator accounting(validatorInfo) as opposed to `validatorCurrentBalanceGwei`. In this case, verified ETH is `_MAX_RESTAKED_BALANCE_GWEI_PER_VALIDATOR`. But `stakeButNotVerifiedETH` will still subtract `validatorCurrentBalanceGwei`, which results in `stakeButNotVerifiedETH` being underestimated.

In addition, since `stakeButNotVerifiedETH` is added into `getStakedETHBalance()` which gets added into `totalTVLs()`(RestakeManger.sol), this means `totalTVLs` is underestimated.

Recommendations:
Consider adding check in OperatorDelegator::verifyWithdrawalCredentials to query EigenPod and confirm the actual verified restakedBalance. Or cache `_MAX_RESTAKED_BALANCE_GWEI_PER_VALIDATOR` value to check against `validatorCurrentBalanceGwei`.

### Low-07 Two addresses are assigned as native ETH including address(0x0). Consider only using `IS_NATIVE` as eth address.
**Instances(1)**
In contracts/Deposits/DepositQueue.sol, Native ETH address is defined as ` address public constant IS_NATIVE = 0xEeeeeEeeeEeEeeEeEeEeeEEEeeeeEeeeeeeeEEeE` already.

However, in `receive()`, Native ETH is also represented as address(0x0).
```solidity
//contracts/Deposits/DepositQueue.sol
    receive() external payable nonReentrant {
...
        totalEarned[address(0x0)] = totalEarned[address(0x0)] + remainingRewards;
...
```
(https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L179)

### Low-08 Inconsistent gas refund calculation
**Instances(1)**
Gas refund calculation is implemented in DepositQueue.sol and OperatorDelegator.sol. However the implementation differs in that `baseGasAmountSpent` which is an overhead gas cost is accounted for in OperatorDelegator.sol, but not accounted for in DepositQueue.sol.

In DepositQueue.sol, [_refundGas()](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L284) will account for `gasUsed` as `(initialGas - gasleft())*tx.gasPrice`. However in OperatorDelegator.sol the [gasSpend](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L471) is `(initialGas - gasleft() + baseGasAmountSpent) * tx.gasprice`.

Recommendations:
Consider unify the gas refund calculation in both contracts and add a `baseGasAmountSpent` value for DepositQueue.sol

### Low-09 Incorrect Comment - 1 mETH to ETH underlying the token in the wBETH protocol
**Instances(1)**
In contracts/Oracle/Binance/WBETHShim.sol, `_getWBETHData()` has an incorrect comment.

```solidity
    /**
|>   * @notice  This function gets the price of 1 mETH in ETH from the mETH staking contract with 18 decimal precision
     * @dev     This function does not implement the full Chainlink AggregatorV3Interface
     * @return  roundId  0 - never returns valid round ID
     * @return  answer  The conversion rate of 1 mETH to ETH.
     * @return  startedAt  0 - never returns valid timestamp
     * @return  updatedAt  The current timestamp.
     * @return  answeredInRound  0 - never returns valid round ID
     */
    function _getWBETHData()
```
(https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Binance/WBETHShim.sol#L61)

This should change to 1 WBETH in ETH.

Recommendations:
Change to 1 WBETH in ETH.

### Low-10 `collateralTokenTvlLimits` might be exceeded due to missing check in `depositTokenRewardsFromProtocol()`
**Instances(1)**
In contracts/RestakeManager.sol, each collateral token has a max deposit limit ([collateralTokenTvlLimits](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L714)).[This limit is checked in most deposit flow](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L529-L530) except for `depositTokenRewardsFromProtocol()`.

As a result, this limit can be exceeded from `depositTokenRewardsFromProtocol()`, resulting in `collateralTokenTVLLimits` being exceeded.
```solidity
//contracts/RestakeManager.sol
    function depositTokenRewardsFromProtocol(
        IERC20 _token,
        uint256 _amount
    ) external onlyDepositQueue {
        // Get the TVLs for each operator delegator and the total TVL
        (, uint256[] memory operatorDelegatorTVLs, uint256 totalTVL) = calculateTVLs();

        // Determine which operator delegator to use
        IOperatorDelegator operatorDelegator = chooseOperatorDelegatorForDeposit(
            operatorDelegatorTVLs,
            totalTVL
        );

        // Transfer the tokens to this address
        _token.safeTransferFrom(msg.sender, address(this), _amount);

        // Approve the tokens to the operator delegator
        _token.safeApprove(address(operatorDelegator), _amount);

        // Deposit the tokens into EigenLayer
        operatorDelegator.deposit(_token, _amount);
    }
```
(https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L647)

Recommendations:
Add collateralTokenTvlLimits check in `depositTokenRewardsFromProtocol()` as well.

### Low-11 Missing step of filling withdraw buffer in the `depositTokenRewardsFromProtocol` flow
**Instances(1)**
Based on [discord](https://discord.com/channels/810916927919620096/1233459941474435102/1235249612038738002), `withdrawQueue` get filled by 3 ways:
1. New Deposits
2. Daily Rewards Coming in the Protocol.
3. Manual withdrawal from EigenLayer. Permissioned call from OperatorDelegator.

However, the second way is not consistently implemented. Notably, filling withdraw buffer is missed during `depositTokenRewardsFromProtocol` flow.

```solidity
//contracts/RestakeManager.sol
    function depositTokenRewardsFromProtocol(
        IERC20 _token,
        uint256 _amount
    ) external onlyDepositQueue {
        // Get the TVLs for each operator delegator and the total TVL
        (, uint256[] memory operatorDelegatorTVLs, uint256 totalTVL) = calculateTVLs();

        // Determine which operator delegator to use
        IOperatorDelegator operatorDelegator = chooseOperatorDelegatorForDeposit(
            operatorDelegatorTVLs,
            totalTVL
        );

        // Transfer the tokens to this address
        _token.safeTransferFrom(msg.sender, address(this), _amount);

        // Approve the tokens to the operator delegator
        _token.safeApprove(address(operatorDelegator), _amount);

        // Deposit the tokens into EigenLayer
        operatorDelegator.deposit(_token, _amount);
    }
```
(https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L647)

As seen, total amount transferred from DepositQueue is redeposited in OD. No [check and refill withdraw buffer](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L543) is called.

Note refill buffer is not called in [DepositQueue::sweepERC20](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L254) either. (sweepERC20 -> restakeManager.depositTokenRewardsFromProtocol)

Recommendations:
Add refill withdraw buffer call in `depositTokenRewardsFromProtocol()`.
