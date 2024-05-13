- [L-1: Centralization Risk for trusted owners](#l-1-centralization-risk-for-trusted-owners)
- [L-2: Deprecated OpenZeppelin functions should not be used](#l-2-deprecated-openzeppelin-functions-should-not-be-used)
- [L-3: Unsafe ERC20 Operations should not be used](#l-3-unsafe-erc20-operations-should-not-be-used)
- [L-4: Solidity pragma should be specific, not wide](#l-4-solidity-pragma-should-be-specific-not-wide)
- [L-5: Missing checks for `address(0)` when assigning values to address state variables](#l-5-missing-checks-for-address0-when-assigning-values-to-address-state-variables)
- [L-6: `public` functions not used internally could be marked `external`](#l-6-public-functions-not-used-internally-could-be-marked-external)
- [L-7: Define and use `constant` variables instead of using literals](#l-7-define-and-use-constant-variables-instead-of-using-literals)
- [L-8: Event is missing `indexed` fields](#l-8-event-is-missing-indexed-fields)
- [L-9: The `nonReentrant` `modifier` should occur before all other modifiers](#l-9-the-nonreentrant-modifier-should-occur-before-all-other-modifiers)
- [L-10: PUSH0 is not supported by all chains](#l-10-push0-is-not-supported-by-all-chains)
- [L-11: Modifiers invoked only once can be shoe-horned into the function](#l-11-modifiers-invoked-only-once-can-be-shoe-horned-into-the-function)
- [L-12: Large literal values multiples of 10000 can be replaced with scientific notation](#l-12-large-literal-values-multiples-of-10000-can-be-replaced-with-scientific-notation)
- [L-13: Internal functions called only once can be inlined](#l-13-internal-functions-called-only-once-can-be-inlined)
- [L-14: Inconsistency in declaring uint256/uint (or) int256/int variables within a contract](#l-14-inconsistency-in-declaring-uint256uint-or-int256int-variables-within-a-contract)


## L-1: Centralization Risk for trusted owners

Contracts have owners with privileged rights to perform admin tasks and need to be trusted to not perform malicious updates or drain funds.

- Found in contracts/Bridge/L2/Oracle/RenzoOracleL2.sol [Line: 36](contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L36)

	```solidity
	    function setOracleAddress(AggregatorV3Interface _oracleAddress) external onlyOwner {
	```

- Found in contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol [Line: 14](contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L14)

	```solidity
	contract Receiver is CCIPReceiver, Ownable, Pausable {
	```

- Found in contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol [Line: 96](contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L96)

	```solidity
	    function updateXRenzoBridgeL1(address _newXRenzoBridgeL1) external onlyOwner {
	```

- Found in contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol [Line: 107](contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L107)

	```solidity
	    function updateCCIPEthChainSelector(uint64 _newChainSelector) external onlyOwner {
	```

- Found in contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol [Line: 117](contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L117)

	```solidity
	    function unPause() external onlyOwner {
	```

- Found in contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol [Line: 125](contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L125)

	```solidity
	    function pause() external onlyOwner {
	```

- Found in contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol [Line: 134](contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L134)

	```solidity
	    function setRenzoDeposit(address _newXRenzoDeposit) external onlyOwner {
	```

- Found in contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol [Line: 10](contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L10)

	```solidity
	contract ConnextReceiver is IXReceiver, Ownable, Pausable {
	```

- Found in contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol [Line: 92](contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L92)

	```solidity
	    function updateXRenzoBridgeL1(address _newXRenzoBridgeL1) external onlyOwner {
	```

- Found in contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol [Line: 103](contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L103)

	```solidity
	    function updateCCIPEthChainSelector(uint32 _newChainDomain) external onlyOwner {
	```

- Found in contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol [Line: 113](contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L113)

	```solidity
	    function unPause() external onlyOwner {
	```

- Found in contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol [Line: 121](contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L121)

	```solidity
	    function pause() external onlyOwner {
	```

- Found in contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol [Line: 130](contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L130)

	```solidity
	    function setRenzoDeposit(address _newXRenzoDeposit) external onlyOwner {
	```

- Found in contracts/Bridge/L2/xRenzoDeposit.sol [Line: 320](contracts/Bridge/L2/xRenzoDeposit.sol#L320)

	```solidity
	    function updatePriceByOwner(uint256 price) external onlyOwner {
	```

- Found in contracts/Bridge/L2/xRenzoDeposit.sol [Line: 466](contracts/Bridge/L2/xRenzoDeposit.sol#L466)

	```solidity
	    function setAllowedBridgeSweeper(address _sweeper, bool _allowed) external onlyOwner {
	```

- Found in contracts/Bridge/L2/xRenzoDeposit.sol [Line: 478](contracts/Bridge/L2/xRenzoDeposit.sol#L478)

	```solidity
	    function recoverNative(uint256 _amount, address _to) external onlyOwner {
	```

- Found in contracts/Bridge/L2/xRenzoDeposit.sol [Line: 489](contracts/Bridge/L2/xRenzoDeposit.sol#L489)

	```solidity
	    function recoverERC20(address _token, uint256 _amount, address _to) external onlyOwner {
	```

- Found in contracts/Bridge/L2/xRenzoDeposit.sol [Line: 501](contracts/Bridge/L2/xRenzoDeposit.sol#L501)

	```solidity
	    function setOraclePriceFeed(IRenzoOracleL2 _oracle) external onlyOwner {
	```

- Found in contracts/Bridge/L2/xRenzoDeposit.sol [Line: 511](contracts/Bridge/L2/xRenzoDeposit.sol#L511)

	```solidity
	    function setReceiverPriceFeed(address _receiver) external onlyOwner {
	```

- Found in contracts/Bridge/L2/xRenzoDeposit.sol [Line: 521](contracts/Bridge/L2/xRenzoDeposit.sol#L521)

	```solidity
	    function updateBridgeFeeShare(uint256 _newShare) external onlyOwner {
	```

- Found in contracts/Bridge/L2/xRenzoDeposit.sol [Line: 532](contracts/Bridge/L2/xRenzoDeposit.sol#L532)

	```solidity
	    function updateSweepBatchSize(uint256 _newBatchSize) external onlyOwner {
	```

- Found in contracts/Bridge/xERC20/contracts/XERC20.sol [Line: 139](contracts/Bridge/xERC20/contracts/XERC20.sol#L139)

	```solidity
	    ) external onlyOwner {
	```

- Found in contracts/TimelockController.sol [Line: 25](contracts/TimelockController.sol#L25)

	```solidity
	contract TimelockController is AccessControl, IERC721Receiver, IERC1155Receiver {
	```

- Found in contracts/TimelockController.sol [Line: 241](contracts/TimelockController.sol#L241)

	```solidity
	    ) public virtual onlyRole(PROPOSER_ROLE) {
	```

- Found in contracts/TimelockController.sol [Line: 266](contracts/TimelockController.sol#L266)

	```solidity
	    ) public virtual onlyRole(PROPOSER_ROLE) {
	```

- Found in contracts/TimelockController.sol [Line: 296](contracts/TimelockController.sol#L296)

	```solidity
	    function cancel(bytes32 id) public virtual onlyRole(CANCELLER_ROLE) {
	```

- Found in contracts/TimelockController.sol [Line: 321](contracts/TimelockController.sol#L321)

	```solidity
	    ) public payable virtual onlyRoleOrOpenRole(EXECUTOR_ROLE) {
	```

- Found in contracts/TimelockController.sol [Line: 348](contracts/TimelockController.sol#L348)

	```solidity
	    ) public payable virtual onlyRoleOrOpenRole(EXECUTOR_ROLE) {
	```



## L-2: Deprecated OpenZeppelin functions should not be used

Openzeppelin has deprecated several functions and replaced with newer versions. Please consult https://docs.openzeppelin.com/

- Found in contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol [Line: 84](contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L84)

	```solidity
	        SafeERC20.safeApprove(IERC20(_erc20), lockbox, _amount);
	```

- Found in contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol [Line: 86](contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L86)

	```solidity
	        SafeERC20.safeApprove(IERC20(xerc20), blastStandardBridge, _amount);
	```

- Found in contracts/Bridge/L1/xRenzoBridge.sol [Line: 181](contracts/Bridge/L1/xRenzoBridge.sol#L181)

	```solidity
	        ezETH.safeApprove(address(xezETHLockbox), ezETHAmount);
	```

- Found in contracts/Bridge/L2/xRenzoDeposit.sol [Line: 369](contracts/Bridge/L2/xRenzoDeposit.sol#L369)

	```solidity
	        depositToken.safeApprove(address(connext), _amountIn);
	```

- Found in contracts/Bridge/L2/xRenzoDeposit.sol [Line: 429](contracts/Bridge/L2/xRenzoDeposit.sol#L429)

	```solidity
	        collateralToken.safeApprove(address(connext), balance);
	```

- Found in contracts/Delegation/OperatorDelegator.sol [Line: 164](contracts/Delegation/OperatorDelegator.sol#L164)

	```solidity
	        _token.safeApprove(address(strategyManager), _tokenAmount);
	```

- Found in contracts/Delegation/OperatorDelegator.sol [Line: 297](contracts/Delegation/OperatorDelegator.sol#L297)

	```solidity
	                    tokens[i].safeApprove(address(restakeManager.depositQueue()), bufferToFill);
	```

- Found in contracts/Deposits/DepositQueue.sol [Line: 142](contracts/Deposits/DepositQueue.sol#L142)

	```solidity
	        IERC20(_asset).safeApprove(address(withdrawQueue), _amount);
	```

- Found in contracts/RestakeManager.sol [Line: 552](contracts/RestakeManager.sol#L552)

	```solidity
	            _collateralToken.safeApprove(address(depositQueue), bufferToFill);
	```

- Found in contracts/RestakeManager.sol [Line: 559](contracts/RestakeManager.sol#L559)

	```solidity
	        _collateralToken.safeApprove(address(operatorDelegator), _amount);
	```

- Found in contracts/RestakeManager.sol [Line: 664](contracts/RestakeManager.sol#L664)

	```solidity
	        _token.safeApprove(address(operatorDelegator), _amount);
	```

- Found in contracts/TimelockController.sol [Line: 99](contracts/TimelockController.sol#L99)

	```solidity
	        _setupRole(TIMELOCK_ADMIN_ROLE, address(this));
	```

- Found in contracts/TimelockController.sol [Line: 103](contracts/TimelockController.sol#L103)

	```solidity
	            _setupRole(TIMELOCK_ADMIN_ROLE, admin);
	```

- Found in contracts/TimelockController.sol [Line: 108](contracts/TimelockController.sol#L108)

	```solidity
	            _setupRole(PROPOSER_ROLE, proposers[i]);
	```

- Found in contracts/TimelockController.sol [Line: 109](contracts/TimelockController.sol#L109)

	```solidity
	            _setupRole(CANCELLER_ROLE, proposers[i]);
	```

- Found in contracts/TimelockController.sol [Line: 114](contracts/TimelockController.sol#L114)

	```solidity
	            _setupRole(EXECUTOR_ROLE, executors[i]);
	```



## L-3: Unsafe ERC20 Operations should not be used

ERC20 functions may not behave as expected. For example: return values are not always meaningful. It is recommended to use OpenZeppelin's SafeERC20 library.

- Found in contracts/Bridge/L1/xRenzoBridge.sol [Line: 241](contracts/Bridge/L1/xRenzoBridge.sol#L241)

	```solidity
	            linkToken.approve(address(linkRouterClient), fees);
	```

- Found in contracts/Bridge/L1/xRenzoBridge.sol [Line: 295](contracts/Bridge/L1/xRenzoBridge.sol#L295)

	```solidity
	        payable(_to).transfer(_amount);
	```

- Found in contracts/Bridge/L2/xRenzoDeposit.sol [Line: 479](contracts/Bridge/L2/xRenzoDeposit.sol#L479)

	```solidity
	        payable(_to).transfer(_amount);
	```

- Found in contracts/Deposits/DepositQueue.sol [Line: 268](contracts/Deposits/DepositQueue.sol#L268)

	```solidity
	            token.approve(address(restakeManager), balance - feeAmount);
	```

- Found in contracts/Withdraw/WithdrawQueue.sol [Line: 303](contracts/Withdraw/WithdrawQueue.sol#L303)

	```solidity
	            payable(msg.sender).transfer(_withdrawRequest.amountToRedeem);
	```

- Found in contracts/Withdraw/WithdrawQueue.sol [Line: 305](contracts/Withdraw/WithdrawQueue.sol#L305)

	```solidity
	            IERC20(_withdrawRequest.collateralToken).transfer(
	```



## L-4: Solidity pragma should be specific, not wide

Consider using a specific version of Solidity in your contracts instead of a wide version. For example, instead of `pragma solidity ^0.8.0;`, use `pragma solidity 0.8.0;`

- Found in contracts/Bridge/Connext/core/IConnext.sol [Line: 2](contracts/Bridge/Connext/core/IConnext.sol#L2)

	```solidity
	pragma solidity ^0.8.0;
	```

- Found in contracts/Bridge/Connext/core/IWeth.sol [Line: 2](contracts/Bridge/Connext/core/IWeth.sol#L2)

	```solidity
	pragma solidity ^0.8.0;
	```

- Found in contracts/Bridge/Connext/core/IXReceiver.sol [Line: 2](contracts/Bridge/Connext/core/IXReceiver.sol#L2)

	```solidity
	pragma solidity ^0.8.0;
	```

- Found in contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol [Line: 2](contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L2)

	```solidity
	pragma solidity ^0.8.13;
	```

- Found in contracts/Bridge/Connext/libraries/LibConnextStorage.sol [Line: 2](contracts/Bridge/Connext/libraries/LibConnextStorage.sol#L2)

	```solidity
	pragma solidity ^0.8.0;
	```

- Found in contracts/Bridge/Connext/libraries/TokenId.sol [Line: 2](contracts/Bridge/Connext/libraries/TokenId.sol#L2)

	```solidity
	pragma solidity ^0.8.0;
	```

- Found in contracts/Bridge/xERC20/contracts/XERC20.sol [Line: 2](contracts/Bridge/xERC20/contracts/XERC20.sol#L2)

	```solidity
	pragma solidity >=0.8.4 <0.9.0;
	```

- Found in contracts/Bridge/xERC20/contracts/XERC20Factory.sol [Line: 2](contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L2)

	```solidity
	pragma solidity >=0.8.4 <0.9.0;
	```

- Found in contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol [Line: 2](contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L2)

	```solidity
	pragma solidity >=0.8.4 <0.9.0;
	```

- Found in contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol [Line: 2](contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L2)

	```solidity
	pragma solidity >=0.8.4 <0.9.0;
	```

- Found in contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol [Line: 2](contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L2)

	```solidity
	pragma solidity >=0.8.4 <0.9.0;
	```

- Found in contracts/Bridge/xERC20/interfaces/IOptimismMintableERC20.sol [Line: 2](contracts/Bridge/xERC20/interfaces/IOptimismMintableERC20.sol#L2)

	```solidity
	pragma solidity >=0.8.4 <0.9.0;
	```

- Found in contracts/Bridge/xERC20/interfaces/IXERC20.sol [Line: 2](contracts/Bridge/xERC20/interfaces/IXERC20.sol#L2)

	```solidity
	pragma solidity >=0.8.4 <0.9.0;
	```

- Found in contracts/Bridge/xERC20/interfaces/IXERC20Factory.sol [Line: 2](contracts/Bridge/xERC20/interfaces/IXERC20Factory.sol#L2)

	```solidity
	pragma solidity >=0.8.4 <0.9.0;
	```

- Found in contracts/Bridge/xERC20/interfaces/IXERC20Lockbox.sol [Line: 2](contracts/Bridge/xERC20/interfaces/IXERC20Lockbox.sol#L2)

	```solidity
	pragma solidity >=0.8.4 <0.9.0;
	```

- Found in contracts/EigenLayer/interfaces/IAVSDirectory.sol [Line: 2](contracts/EigenLayer/interfaces/IAVSDirectory.sol#L2)

	```solidity
	pragma solidity >=0.5.0;
	```

- Found in contracts/EigenLayer/interfaces/IBeaconChainOracle.sol [Line: 2](contracts/EigenLayer/interfaces/IBeaconChainOracle.sol#L2)

	```solidity
	pragma solidity >=0.5.0;
	```

- Found in contracts/EigenLayer/interfaces/IDelayedWithdrawalRouter.sol [Line: 2](contracts/EigenLayer/interfaces/IDelayedWithdrawalRouter.sol#L2)

	```solidity
	pragma solidity >=0.5.0;
	```

- Found in contracts/EigenLayer/interfaces/IDelegationFaucet.sol [Line: 2](contracts/EigenLayer/interfaces/IDelegationFaucet.sol#L2)

	```solidity
	pragma solidity >=0.5.0;
	```

- Found in contracts/EigenLayer/interfaces/IDelegationManager.sol [Line: 2](contracts/EigenLayer/interfaces/IDelegationManager.sol#L2)

	```solidity
	pragma solidity >=0.5.0;
	```

- Found in contracts/EigenLayer/interfaces/IETHPOSDeposit.sol [Line: 12](contracts/EigenLayer/interfaces/IETHPOSDeposit.sol#L12)

	```solidity
	pragma solidity >=0.5.0;
	```

- Found in contracts/EigenLayer/interfaces/IEigenPod.sol [Line: 2](contracts/EigenLayer/interfaces/IEigenPod.sol#L2)

	```solidity
	pragma solidity >=0.5.0;
	```

- Found in contracts/EigenLayer/interfaces/IEigenPodManager.sol [Line: 2](contracts/EigenLayer/interfaces/IEigenPodManager.sol#L2)

	```solidity
	pragma solidity >=0.5.0;
	```

- Found in contracts/EigenLayer/interfaces/IPausable.sol [Line: 2](contracts/EigenLayer/interfaces/IPausable.sol#L2)

	```solidity
	pragma solidity >=0.5.0;
	```

- Found in contracts/EigenLayer/interfaces/IPauserRegistry.sol [Line: 2](contracts/EigenLayer/interfaces/IPauserRegistry.sol#L2)

	```solidity
	pragma solidity >=0.5.0;
	```

- Found in contracts/EigenLayer/interfaces/ISignatureUtils.sol [Line: 2](contracts/EigenLayer/interfaces/ISignatureUtils.sol#L2)

	```solidity
	pragma solidity >=0.5.0;
	```

- Found in contracts/EigenLayer/interfaces/ISlasher.sol [Line: 2](contracts/EigenLayer/interfaces/ISlasher.sol#L2)

	```solidity
	pragma solidity >=0.5.0;
	```

- Found in contracts/EigenLayer/interfaces/IStrategy.sol [Line: 2](contracts/EigenLayer/interfaces/IStrategy.sol#L2)

	```solidity
	pragma solidity >=0.5.0;
	```

- Found in contracts/EigenLayer/interfaces/IStrategyManager.sol [Line: 2](contracts/EigenLayer/interfaces/IStrategyManager.sol#L2)

	```solidity
	pragma solidity >=0.5.0;
	```

- Found in contracts/EigenLayer/interfaces/IWhitelister.sol [Line: 2](contracts/EigenLayer/interfaces/IWhitelister.sol#L2)

	```solidity
	pragma solidity >=0.5.0;
	```

- Found in contracts/EigenLayer/libraries/BytesLib.sol [Line: 9](contracts/EigenLayer/libraries/BytesLib.sol#L9)

	```solidity
	pragma solidity >=0.8.0 <0.9.0;
	```

- Found in contracts/EigenLayer/libraries/Endian.sol [Line: 2](contracts/EigenLayer/libraries/Endian.sol#L2)

	```solidity
	pragma solidity ^0.8.0;
	```

- Found in contracts/EigenLayer/libraries/Merkle.sol [Line: 4](contracts/EigenLayer/libraries/Merkle.sol#L4)

	```solidity
	pragma solidity ^0.8.0;
	```

- Found in contracts/TimelockController.sol [Line: 4](contracts/TimelockController.sol#L4)

	```solidity
	pragma solidity ^0.8.0;
	```

- Found in contracts/token/EzEthToken.sol [Line: 2](contracts/token/EzEthToken.sol#L2)

	```solidity
	pragma solidity ^0.8.9;
	```

- Found in contracts/token/IEzEthToken.sol [Line: 2](contracts/token/IEzEthToken.sol#L2)

	```solidity
	pragma solidity ^0.8.9;
	```



## L-5: Missing checks for `address(0)` when assigning values to address state variables

Check for `address(0)` when assigning values to address state variables.

- Found in contracts/Bridge/L2/xRenzoDeposit.sol [Line: 138](contracts/Bridge/L2/xRenzoDeposit.sol#L138)

	```solidity
	        receiver = _receiver;
	```

- Found in contracts/Bridge/L2/xRenzoDeposit.sol [Line: 149](contracts/Bridge/L2/xRenzoDeposit.sol#L149)

	```solidity
	        oracle = _oracle;
	```

- Found in contracts/Bridge/L2/xRenzoDeposit.sol [Line: 467](contracts/Bridge/L2/xRenzoDeposit.sol#L467)

	```solidity
	        allowedBridgeSweepers[_sweeper] = _allowed;
	```

- Found in contracts/Bridge/L2/xRenzoDeposit.sol [Line: 503](contracts/Bridge/L2/xRenzoDeposit.sol#L503)

	```solidity
	        oracle = _oracle;
	```

- Found in contracts/Bridge/L2/xRenzoDeposit.sol [Line: 513](contracts/Bridge/L2/xRenzoDeposit.sol#L513)

	```solidity
	        receiver = _receiver;
	```

- Found in contracts/Bridge/xERC20/contracts/XERC20.sol [Line: 86](contracts/Bridge/xERC20/contracts/XERC20.sol#L86)

	```solidity
	        FACTORY = _factory;
	```

- Found in contracts/Bridge/xERC20/contracts/XERC20.sol [Line: 123](contracts/Bridge/xERC20/contracts/XERC20.sol#L123)

	```solidity
	        lockbox = _lockbox;
	```

- Found in contracts/Bridge/xERC20/contracts/XERC20.sol [Line: 208](contracts/Bridge/xERC20/contracts/XERC20.sol#L208)

	```solidity
	        bridges[_bridge].minterParams.currentLimit = _currentLimit - _change;
	```

- Found in contracts/Bridge/xERC20/contracts/XERC20.sol [Line: 220](contracts/Bridge/xERC20/contracts/XERC20.sol#L220)

	```solidity
	        bridges[_bridge].burnerParams.currentLimit = _currentLimit - _change;
	```

- Found in contracts/Bridge/xERC20/contracts/XERC20.sol [Line: 233](contracts/Bridge/xERC20/contracts/XERC20.sol#L233)

	```solidity
	        bridges[_bridge].minterParams.maxLimit = _limit;
	```

- Found in contracts/Bridge/xERC20/contracts/XERC20.sol [Line: 235](contracts/Bridge/xERC20/contracts/XERC20.sol#L235)

	```solidity
	        bridges[_bridge].minterParams.currentLimit = _calculateNewCurrentLimit(
	```

- Found in contracts/Bridge/xERC20/contracts/XERC20.sol [Line: 241](contracts/Bridge/xERC20/contracts/XERC20.sol#L241)

	```solidity
	        bridges[_bridge].minterParams.ratePerSecond = _limit / _DURATION;
	```

- Found in contracts/Bridge/xERC20/contracts/XERC20.sol [Line: 255](contracts/Bridge/xERC20/contracts/XERC20.sol#L255)

	```solidity
	        bridges[_bridge].burnerParams.maxLimit = _limit;
	```

- Found in contracts/Bridge/xERC20/contracts/XERC20.sol [Line: 257](contracts/Bridge/xERC20/contracts/XERC20.sol#L257)

	```solidity
	        bridges[_bridge].burnerParams.currentLimit = _calculateNewCurrentLimit(
	```

- Found in contracts/Bridge/xERC20/contracts/XERC20.sol [Line: 263](contracts/Bridge/xERC20/contracts/XERC20.sol#L263)

	```solidity
	        bridges[_bridge].burnerParams.ratePerSecond = _limit / _DURATION;
	```

- Found in contracts/Bridge/xERC20/contracts/XERC20Factory.sol [Line: 58](contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L58)

	```solidity
	        lockboxImplementation = _lockboxImplementation;
	```

- Found in contracts/Bridge/xERC20/contracts/XERC20Factory.sol [Line: 59](contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L59)

	```solidity
	        xerc20Implementation = _xerc20Implementation;
	```

- Found in contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol [Line: 45](contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L45)

	```solidity
	        XERC20 = IXERC20(_xerc20);
	```

- Found in contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol [Line: 46](contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L46)

	```solidity
	        ERC20 = IERC20(_erc20);
	```

- Found in contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol [Line: 44](contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L44)

	```solidity
	        l1Token = _l1Token;
	```

- Found in contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol [Line: 45](contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L45)

	```solidity
	        optimismBridge = _optimismBridge;
	```

- Found in contracts/Delegation/OperatorDelegator.sol [Line: 112](contracts/Delegation/OperatorDelegator.sol#L112)

	```solidity
	        tokenStrategyMapping[_token] = _strategy;
	```

- Found in contracts/Deposits/DepositQueue.sol [Line: 272](contracts/Deposits/DepositQueue.sol#L272)

	```solidity
	            totalEarned[address(token)] = totalEarned[address(token)] + balance - feeAmount;
	```

- Found in contracts/RestakeManager.sol [Line: 111](contracts/RestakeManager.sol#L111)

	```solidity
	        roleManager = _roleManager;
	```

- Found in contracts/RestakeManager.sol [Line: 112](contracts/RestakeManager.sol#L112)

	```solidity
	        ezETH = _ezETH;
	```

- Found in contracts/RestakeManager.sol [Line: 113](contracts/RestakeManager.sol#L113)

	```solidity
	        renzoOracle = _renzoOracle;
	```

- Found in contracts/RestakeManager.sol [Line: 114](contracts/RestakeManager.sol#L114)

	```solidity
	        strategyManager = _strategyManager;
	```

- Found in contracts/RestakeManager.sol [Line: 115](contracts/RestakeManager.sol#L115)

	```solidity
	        delegationManager = _delegationManager;
	```

- Found in contracts/RestakeManager.sol [Line: 116](contracts/RestakeManager.sol#L116)

	```solidity
	        depositQueue = _depositQueue;
	```

- Found in contracts/RestakeManager.sol [Line: 154](contracts/RestakeManager.sol#L154)

	```solidity
	        operatorDelegatorAllocations[_newOperatorDelegator] = _allocationBasisPoints;
	```

- Found in contracts/RestakeManager.sol [Line: 209](contracts/RestakeManager.sol#L209)

	```solidity
	        operatorDelegatorAllocations[_operatorDelegator] = _allocationBasisPoints;
	```

- Found in contracts/RestakeManager.sol [Line: 714](contracts/RestakeManager.sol#L714)

	```solidity
	        collateralTokenTvlLimits[_token] = _limit;
	```



## L-6: `public` functions not used internally could be marked `external`

Instead of marking a function as `public`, consider marking it as `external` if it is not used internally.

- Found in contracts/Bridge/L1/xRenzoBridge.sol [Line: 70](contracts/Bridge/L1/xRenzoBridge.sol#L70)

	```solidity
	    function initialize(
	```

- Found in contracts/Bridge/L2/Oracle/RenzoOracleL2.sol [Line: 23](contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L23)

	```solidity
	    function initialize(AggregatorV3Interface _oracle) public initializer {
	```

- Found in contracts/Bridge/L2/Oracle/RenzoOracleL2.sol [Line: 50](contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L50)

	```solidity
	    function getMintRate() public view returns (uint256, uint256) {
	```

- Found in contracts/Bridge/L2/xRenzoDeposit.sol [Line: 75](contracts/Bridge/L2/xRenzoDeposit.sol#L75)

	```solidity
	    function initialize(
	```

- Found in contracts/Bridge/L2/xRenzoDeposit.sol [Line: 414](contracts/Bridge/L2/xRenzoDeposit.sol#L414)

	```solidity
	    function sweep() public payable nonReentrant {
	```

- Found in contracts/Bridge/xERC20/contracts/XERC20.sol [Line: 61](contracts/Bridge/xERC20/contracts/XERC20.sol#L61)

	```solidity
	    function initialize(
	```

- Found in contracts/Bridge/xERC20/contracts/XERC20.sol [Line: 96](contracts/Bridge/xERC20/contracts/XERC20.sol#L96)

	```solidity
	    function mint(address _user, uint256 _amount) public virtual {
	```

- Found in contracts/Bridge/xERC20/contracts/XERC20.sol [Line: 107](contracts/Bridge/xERC20/contracts/XERC20.sol#L107)

	```solidity
	    function burn(address _user, uint256 _amount) public virtual {
	```

- Found in contracts/Bridge/xERC20/contracts/XERC20.sol [Line: 121](contracts/Bridge/xERC20/contracts/XERC20.sol#L121)

	```solidity
	    function setLockbox(address _lockbox) public {
	```

- Found in contracts/Bridge/xERC20/contracts/XERC20.sol [Line: 152](contracts/Bridge/xERC20/contracts/XERC20.sol#L152)

	```solidity
	    function mintingMaxLimitOf(address _bridge) public view returns (uint256 _limit) {
	```

- Found in contracts/Bridge/xERC20/contracts/XERC20.sol [Line: 163](contracts/Bridge/xERC20/contracts/XERC20.sol#L163)

	```solidity
	    function burningMaxLimitOf(address _bridge) public view returns (uint256 _limit) {
	```

- Found in contracts/Bridge/xERC20/contracts/XERC20Factory.sol [Line: 54](contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L54)

	```solidity
	    function initialize(
	```

- Found in contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol [Line: 44](contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L44)

	```solidity
	    function initialize(address _xerc20, address _erc20, bool _isNative) public initializer {
	```

- Found in contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol [Line: 91](contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L91)

	```solidity
	    function depositNativeTo(address _to) public payable {
	```

- Found in contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol [Line: 35](contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L35)

	```solidity
	    function initialize(
	```

- Found in contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol [Line: 48](contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L48)

	```solidity
	    function supportsInterface(
	```

- Found in contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol [Line: 56](contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L56)

	```solidity
	    function remoteToken() public view override returns (address) {
	```

- Found in contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol [Line: 60](contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L60)

	```solidity
	    function bridge() public view override returns (address) {
	```

- Found in contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol [Line: 64](contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L64)

	```solidity
	    function mint(address _to, uint256 _amount) public override(XERC20, IOptimismMintableERC20) {
	```

- Found in contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol [Line: 68](contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L68)

	```solidity
	    function burn(address _from, uint256 _amount) public override(XERC20, IOptimismMintableERC20) {
	```

- Found in contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol [Line: 37](contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L37)

	```solidity
	    function deployOptimismMintableXERC20(
	```

- Found in contracts/Delegation/OperatorDelegator.sol [Line: 172](contracts/Delegation/OperatorDelegator.sol#L172)

	```solidity
	    function getStrategyIndex(IStrategy _strategy) public view returns (uint256) {
	```

- Found in contracts/Deposits/DepositQueue.sol [Line: 74](contracts/Deposits/DepositQueue.sol#L74)

	```solidity
	    function initialize(IRoleManager _roleManager) public initializer {
	```

- Found in contracts/Oracle/Binance/WBETHShim.sol [Line: 23](contracts/Oracle/Binance/WBETHShim.sol#L23)

	```solidity
	    function initialize(IStakedTokenV2 _wBETHToken) public initializer {
	```

- Found in contracts/Oracle/Mantle/METHShim.sol [Line: 23](contracts/Oracle/Mantle/METHShim.sol#L23)

	```solidity
	    function initialize(IMethStaking _methStaking) public initializer {
	```

- Found in contracts/Oracle/RenzoOracle.sol [Line: 44](contracts/Oracle/RenzoOracle.sol#L44)

	```solidity
	    function initialize(IRoleManager _roleManager) public initializer {
	```

- Found in contracts/Permissions/RoleManager.sol [Line: 22](contracts/Permissions/RoleManager.sol#L22)

	```solidity
	    function initialize(address roleManagerAdmin) public initializer {
	```

- Found in contracts/RateProvider/BalancerRateProvider.sol [Line: 17](contracts/RateProvider/BalancerRateProvider.sol#L17)

	```solidity
	    function initialize(
	```

- Found in contracts/RestakeManager.sol [Line: 101](contracts/RestakeManager.sol#L101)

	```solidity
	    function initialize(
	```

- Found in contracts/RestakeManager.sol [Line: 400](contracts/RestakeManager.sol#L400)

	```solidity
	    function chooseOperatorDelegatorForWithdraw(
	```

- Found in contracts/Rewards/RewardHandler.sol [Line: 38](contracts/Rewards/RewardHandler.sol#L38)

	```solidity
	    function initialize(IRoleManager _roleManager, address _rewardDestination) public initializer {
	```

- Found in contracts/TimelockController.sol [Line: 142](contracts/TimelockController.sol#L142)

	```solidity
	    function supportsInterface(
	```

- Found in contracts/TimelockController.sol [Line: 234](contracts/TimelockController.sol#L234)

	```solidity
	    function schedule(
	```

- Found in contracts/TimelockController.sol [Line: 259](contracts/TimelockController.sol#L259)

	```solidity
	    function scheduleBatch(
	```

- Found in contracts/TimelockController.sol [Line: 296](contracts/TimelockController.sol#L296)

	```solidity
	    function cancel(bytes32 id) public virtual onlyRole(CANCELLER_ROLE) {
	```

- Found in contracts/TimelockController.sol [Line: 315](contracts/TimelockController.sol#L315)

	```solidity
	    function execute(
	```

- Found in contracts/TimelockController.sol [Line: 342](contracts/TimelockController.sol#L342)

	```solidity
	    function executeBatch(
	```

- Found in contracts/TimelockController.sol [Line: 411](contracts/TimelockController.sol#L411)

	```solidity
	    function onERC721Received(
	```

- Found in contracts/TimelockController.sol [Line: 423](contracts/TimelockController.sol#L423)

	```solidity
	    function onERC1155Received(
	```

- Found in contracts/TimelockController.sol [Line: 436](contracts/TimelockController.sol#L436)

	```solidity
	    function onERC1155BatchReceived(
	```

- Found in contracts/Withdraw/WithdrawQueue.sol [Line: 170](contracts/Withdraw/WithdrawQueue.sol#L170)

	```solidity
	    function getBufferDeficit(address _asset) public view returns (uint256) {
	```

- Found in contracts/Withdraw/WithdrawQueue.sol [Line: 270](contracts/Withdraw/WithdrawQueue.sol#L270)

	```solidity
	    function getOutstandingWithdrawRequests(address user) public view returns (uint256) {
	```

- Found in contracts/token/EzEthToken.sol [Line: 33](contracts/token/EzEthToken.sol#L33)

	```solidity
	    function initialize(IRoleManager _roleManager) public initializer {
	```

- Found in contracts/token/EzEthToken.sol [Line: 77](contracts/token/EzEthToken.sol#L77)

	```solidity
	    function name() public view virtual override returns (string memory) {
	```

- Found in contracts/token/EzEthToken.sol [Line: 85](contracts/token/EzEthToken.sol#L85)

	```solidity
	    function symbol() public view virtual override returns (string memory) {
	```



## L-7: Define and use `constant` variables instead of using literals

If the same constant literal value is used multiple times, create a constant state variable and reference it throughout the contract.

- Found in contracts/Bridge/L2/Oracle/RenzoOracleL2.sol [Line: 30](contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L30)

	```solidity
	        if (_oracle.decimals() > 18) revert InvalidTokenDecimals(18, _oracle.decimals());
	```

- Found in contracts/Bridge/L2/Oracle/RenzoOracleL2.sol [Line: 39](contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L39)

	```solidity
	        if (_oracleAddress.decimals() > 18)
	```

- Found in contracts/Bridge/L2/Oracle/RenzoOracleL2.sol [Line: 40](contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L40)

	```solidity
	            revert InvalidTokenDecimals(18, _oracleAddress.decimals());
	```

- Found in contracts/Bridge/L2/Oracle/RenzoOracleL2.sol [Line: 54](contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L54)

	```solidity
	        uint256 _scaledPrice = (uint256(price)) * 10 ** (18 - oracle.decimals());
	```

- Found in contracts/Bridge/L2/xRenzoDeposit.sol [Line: 140](contracts/Bridge/L2/xRenzoDeposit.sol#L140)

	```solidity
	        bridgeRouterFeeBps = 5;
	```

- Found in contracts/Bridge/L2/xRenzoDeposit.sol [Line: 152](contracts/Bridge/L2/xRenzoDeposit.sol#L152)

	```solidity
	        bridgeFeeShare = 5;
	```

- Found in contracts/Bridge/L2/xRenzoDeposit.sol [Line: 155](contracts/Bridge/L2/xRenzoDeposit.sol#L155)

	```solidity
	        sweepBatchSize = 32 ether;
	```

- Found in contracts/Bridge/L2/xRenzoDeposit.sol [Line: 338](contracts/Bridge/L2/xRenzoDeposit.sol#L338)

	```solidity
	            (_price > lastPrice && (_price - lastPrice) > (lastPrice / 10)) ||
	```

- Found in contracts/Bridge/L2/xRenzoDeposit.sol [Line: 339](contracts/Bridge/L2/xRenzoDeposit.sol#L339)

	```solidity
	            (_price < lastPrice && (lastPrice - _price) > (lastPrice / 10))
	```

- Found in contracts/Bridge/L2/xRenzoDeposit.sol [Line: 533](contracts/Bridge/L2/xRenzoDeposit.sol#L533)

	```solidity
	        if (_newBatchSize < 32 ether) revert InvalidSweepBatchSize(_newBatchSize);
	```

- Found in contracts/Delegation/OperatorDelegator.sol [Line: 81](contracts/Delegation/OperatorDelegator.sol#L81)

	```solidity
	        if (address(_roleManager) == address(0x0)) revert InvalidZeroInput();
	```

- Found in contracts/Delegation/OperatorDelegator.sol [Line: 82](contracts/Delegation/OperatorDelegator.sol#L82)

	```solidity
	        if (address(_strategyManager) == address(0x0)) revert InvalidZeroInput();
	```

- Found in contracts/Delegation/OperatorDelegator.sol [Line: 83](contracts/Delegation/OperatorDelegator.sol#L83)

	```solidity
	        if (address(_restakeManager) == address(0x0)) revert InvalidZeroInput();
	```

- Found in contracts/Delegation/OperatorDelegator.sol [Line: 84](contracts/Delegation/OperatorDelegator.sol#L84)

	```solidity
	        if (address(_delegationManager) == address(0x0)) revert InvalidZeroInput();
	```

- Found in contracts/Delegation/OperatorDelegator.sol [Line: 85](contracts/Delegation/OperatorDelegator.sol#L85)

	```solidity
	        if (address(_eigenPodManager) == address(0x0)) revert InvalidZeroInput();
	```

- Found in contracts/Delegation/OperatorDelegator.sol [Line: 110](contracts/Delegation/OperatorDelegator.sol#L110)

	```solidity
	        if (address(_token) == address(0x0)) revert InvalidZeroInput();
	```

- Found in contracts/Delegation/OperatorDelegator.sol [Line: 122](contracts/Delegation/OperatorDelegator.sol#L122)

	```solidity
	        if (address(_delegateAddress) == address(0x0)) revert InvalidZeroInput();
	```

- Found in contracts/Delegation/OperatorDelegator.sol [Line: 123](contracts/Delegation/OperatorDelegator.sol#L123)

	```solidity
	        if (address(delegateAddress) != address(0x0)) revert DelegateAddressAlreadySet();
	```

- Found in contracts/Delegation/OperatorDelegator.sol [Line: 147](contracts/Delegation/OperatorDelegator.sol#L147)

	```solidity
	        if (address(tokenStrategyMapping[token]) == address(0x0) || tokenAmount == 0)
	```

- Found in contracts/Deposits/DepositQueue.sol [Line: 77](contracts/Deposits/DepositQueue.sol#L77)

	```solidity
	        if (address(_roleManager) == address(0x0)) revert InvalidZeroInput();
	```

- Found in contracts/Deposits/DepositQueue.sol [Line: 99](contracts/Deposits/DepositQueue.sol#L99)

	```solidity
	            if (_feeAddress == address(0x0)) revert InvalidZeroInput();
	```

- Found in contracts/Deposits/DepositQueue.sol [Line: 103](contracts/Deposits/DepositQueue.sol#L103)

	```solidity
	        if (_feeBasisPoints > 10000) revert OverMaxBasisPoints();
	```

- Found in contracts/Deposits/DepositQueue.sol [Line: 113](contracts/Deposits/DepositQueue.sol#L113)

	```solidity
	        if (address(_restakeManager) == address(0x0)) revert InvalidZeroInput();
	```

- Found in contracts/Deposits/DepositQueue.sol [Line: 166](contracts/Deposits/DepositQueue.sol#L166)

	```solidity
	        if (feeAddress != address(0x0) && feeBasisPoints > 0) {
	```

- Found in contracts/Deposits/DepositQueue.sol [Line: 167](contracts/Deposits/DepositQueue.sol#L167)

	```solidity
	            feeAmount = (msg.value * feeBasisPoints) / 10000;
	```

- Found in contracts/Deposits/DepositQueue.sol [Line: 171](contracts/Deposits/DepositQueue.sol#L171)

	```solidity
	            emit ProtocolFeesPaid(IERC20(address(0x0)), feeAmount, feeAddress);
	```

- Found in contracts/Deposits/DepositQueue.sol [Line: 179](contracts/Deposits/DepositQueue.sol#L179)

	```solidity
	        totalEarned[address(0x0)] = totalEarned[address(0x0)] + remainingRewards;
	```

- Found in contracts/Deposits/DepositQueue.sol [Line: 182](contracts/Deposits/DepositQueue.sol#L182)

	```solidity
	        emit RewardsDeposited(IERC20(address(0x0)), remainingRewards);
	```

- Found in contracts/Deposits/DepositQueue.sol [Line: 202](contracts/Deposits/DepositQueue.sol#L202)

	```solidity
	        emit ETHStakedFromQueue(operatorDelegator, pubkey, 32 ether, address(this).balance);
	```

- Found in contracts/Deposits/DepositQueue.sol [Line: 239](contracts/Deposits/DepositQueue.sol#L239)

	```solidity
	                32 ether,
	```

- Found in contracts/Deposits/DepositQueue.sol [Line: 260](contracts/Deposits/DepositQueue.sol#L260)

	```solidity
	            if (feeAddress != address(0x0) && feeBasisPoints > 0) {
	```

- Found in contracts/Deposits/DepositQueue.sol [Line: 261](contracts/Deposits/DepositQueue.sol#L261)

	```solidity
	                feeAmount = (balance * feeBasisPoints) / 10000;
	```

- Found in contracts/EigenLayer/libraries/BeaconChainProofs.sol [Line: 129](contracts/EigenLayer/libraries/BeaconChainProofs.sol#L129)

	```solidity
	                32 * ((VALIDATOR_TREE_HEIGHT + 1) + BEACON_STATE_FIELD_TREE_HEIGHT),
	```

- Found in contracts/EigenLayer/libraries/BeaconChainProofs.sol [Line: 162](contracts/EigenLayer/libraries/BeaconChainProofs.sol#L162)

	```solidity
	            stateRootProof.length == 32 * (BEACON_BLOCK_HEADER_FIELD_TREE_HEIGHT),
	```

- Found in contracts/EigenLayer/libraries/BeaconChainProofs.sol [Line: 214](contracts/EigenLayer/libraries/BeaconChainProofs.sol#L214)

	```solidity
	                32 * (executionPayloadHeaderFieldTreeHeight + WITHDRAWALS_TREE_HEIGHT + 1),
	```

- Found in contracts/EigenLayer/libraries/BeaconChainProofs.sol [Line: 219](contracts/EigenLayer/libraries/BeaconChainProofs.sol#L219)

	```solidity
	                32 * (BEACON_BLOCK_HEADER_FIELD_TREE_HEIGHT + BEACON_BLOCK_BODY_FIELD_TREE_HEIGHT),
	```

- Found in contracts/EigenLayer/libraries/BeaconChainProofs.sol [Line: 223](contracts/EigenLayer/libraries/BeaconChainProofs.sol#L223)

	```solidity
	            withdrawalProof.slotProof.length == 32 * (BEACON_BLOCK_HEADER_FIELD_TREE_HEIGHT),
	```

- Found in contracts/EigenLayer/libraries/BeaconChainProofs.sol [Line: 227](contracts/EigenLayer/libraries/BeaconChainProofs.sol#L227)

	```solidity
	            withdrawalProof.timestampProof.length == 32 * (executionPayloadHeaderFieldTreeHeight),
	```

- Found in contracts/EigenLayer/libraries/BeaconChainProofs.sol [Line: 233](contracts/EigenLayer/libraries/BeaconChainProofs.sol#L233)

	```solidity
	                32 *
	```

- Found in contracts/EigenLayer/libraries/BytesLib.sol [Line: 370](contracts/EigenLayer/libraries/BytesLib.sol#L370)

	```solidity
	        require(_bytes.length >= _start + 32, "toUint256_outOfBounds");
	```

- Found in contracts/EigenLayer/libraries/BytesLib.sol [Line: 381](contracts/EigenLayer/libraries/BytesLib.sol#L381)

	```solidity
	        require(_bytes.length >= _start + 32, "toBytes32_outOfBounds");
	```

- Found in contracts/EigenLayer/libraries/Endian.sol [Line: 16](contracts/EigenLayer/libraries/Endian.sol#L16)

	```solidity
	            (n >> 56) |
	```

- Found in contracts/EigenLayer/libraries/Endian.sol [Line: 17](contracts/EigenLayer/libraries/Endian.sol#L17)

	```solidity
	            ((0x00FF000000000000 & n) >> 40) |
	```

- Found in contracts/EigenLayer/libraries/Endian.sol [Line: 18](contracts/EigenLayer/libraries/Endian.sol#L18)

	```solidity
	            ((0x0000FF0000000000 & n) >> 24) |
	```

- Found in contracts/EigenLayer/libraries/Endian.sol [Line: 19](contracts/EigenLayer/libraries/Endian.sol#L19)

	```solidity
	            ((0x000000FF00000000 & n) >> 8) |
	```

- Found in contracts/EigenLayer/libraries/Endian.sol [Line: 20](contracts/EigenLayer/libraries/Endian.sol#L20)

	```solidity
	            ((0x00000000FF000000 & n) << 8) |
	```

- Found in contracts/EigenLayer/libraries/Endian.sol [Line: 21](contracts/EigenLayer/libraries/Endian.sol#L21)

	```solidity
	            ((0x0000000000FF0000 & n) << 24) |
	```

- Found in contracts/EigenLayer/libraries/Endian.sol [Line: 22](contracts/EigenLayer/libraries/Endian.sol#L22)

	```solidity
	            ((0x000000000000FF00 & n) << 40) |
	```

- Found in contracts/EigenLayer/libraries/Endian.sol [Line: 23](contracts/EigenLayer/libraries/Endian.sol#L23)

	```solidity
	            ((0x00000000000000FF & n) << 56);
	```

- Found in contracts/EigenLayer/libraries/Merkle.sol [Line: 54](contracts/EigenLayer/libraries/Merkle.sol#L54)

	```solidity
	            proof.length != 0 && proof.length % 32 == 0,
	```

- Found in contracts/EigenLayer/libraries/Merkle.sol [Line: 58](contracts/EigenLayer/libraries/Merkle.sol#L58)

	```solidity
	        for (uint256 i = 32; i <= proof.length; i += 32) {
	```

- Found in contracts/EigenLayer/libraries/Merkle.sol [Line: 113](contracts/EigenLayer/libraries/Merkle.sol#L113)

	```solidity
	            proof.length != 0 && proof.length % 32 == 0,
	```

- Found in contracts/EigenLayer/libraries/Merkle.sol [Line: 117](contracts/EigenLayer/libraries/Merkle.sol#L117)

	```solidity
	        for (uint256 i = 32; i <= proof.length; i += 32) {
	```

- Found in contracts/Oracle/RenzoOracle.sol [Line: 45](contracts/Oracle/RenzoOracle.sol#L45)

	```solidity
	        if (address(_roleManager) == address(0x0)) revert InvalidZeroInput();
	```

- Found in contracts/Oracle/RenzoOracle.sol [Line: 58](contracts/Oracle/RenzoOracle.sol#L58)

	```solidity
	        if (address(_token) == address(0x0)) revert InvalidZeroInput();
	```

- Found in contracts/Oracle/RenzoOracle.sol [Line: 61](contracts/Oracle/RenzoOracle.sol#L61)

	```solidity
	        if (_oracleAddress.decimals() != 18)
	```

- Found in contracts/Oracle/RenzoOracle.sol [Line: 62](contracts/Oracle/RenzoOracle.sol#L62)

	```solidity
	            revert InvalidTokenDecimals(18, _oracleAddress.decimals());
	```

- Found in contracts/Oracle/RenzoOracle.sol [Line: 73](contracts/Oracle/RenzoOracle.sol#L73)

	```solidity
	        if (address(oracle) == address(0x0)) revert OracleNotFound();
	```

- Found in contracts/Oracle/RenzoOracle.sol [Line: 90](contracts/Oracle/RenzoOracle.sol#L90)

	```solidity
	        if (address(oracle) == address(0x0)) revert OracleNotFound();
	```

- Found in contracts/RateProvider/BalancerRateProvider.sol [Line: 21](contracts/RateProvider/BalancerRateProvider.sol#L21)

	```solidity
	        if (address(_restakeManager) == address(0x0)) revert InvalidZeroInput();
	```

- Found in contracts/RateProvider/BalancerRateProvider.sol [Line: 22](contracts/RateProvider/BalancerRateProvider.sol#L22)

	```solidity
	        if (address(_ezETHToken) == address(0x0)) revert InvalidZeroInput();
	```

- Found in contracts/RestakeManager.sol [Line: 146](contracts/RestakeManager.sol#L146)

	```solidity
	        if (_allocationBasisPoints > (100 * BASIS_POINTS)) revert OverMaxBasisPoints();
	```

- Found in contracts/RestakeManager.sol [Line: 191](contracts/RestakeManager.sol#L191)

	```solidity
	        if (address(_operatorDelegator) == address(0x0)) revert InvalidZeroInput();
	```

- Found in contracts/RestakeManager.sol [Line: 192](contracts/RestakeManager.sol#L192)

	```solidity
	        if (_allocationBasisPoints > (100 * BASIS_POINTS)) revert OverMaxBasisPoints();
	```

- Found in contracts/RestakeManager.sol [Line: 231](contracts/RestakeManager.sol#L231)

	```solidity
	        if (IERC20Metadata(address(_newCollateralToken)).decimals() != 18)
	```

- Found in contracts/RestakeManager.sol [Line: 233](contracts/RestakeManager.sol#L233)

	```solidity
	                18,
	```

- Found in contracts/RestakeManager.sol [Line: 615](contracts/RestakeManager.sol#L615)

	```solidity
	        emit Deposit(msg.sender, IERC20(address(0x0)), msg.value, ezETHToMint, _referralId);
	```

- Found in contracts/RestakeManager.sol [Line: 679](contracts/RestakeManager.sol#L679)

	```solidity
	        totalRewards += depositQueue.totalEarned(address(0x0));
	```

- Found in contracts/Rewards/RewardHandler.sol [Line: 41](contracts/Rewards/RewardHandler.sol#L41)

	```solidity
	        if (address(_roleManager) == address(0x0)) revert InvalidZeroInput();
	```

- Found in contracts/Rewards/RewardHandler.sol [Line: 42](contracts/Rewards/RewardHandler.sol#L42)

	```solidity
	        if (address(_rewardDestination) == address(0x0)) revert InvalidZeroInput();
	```

- Found in contracts/Rewards/RewardHandler.sol [Line: 75](contracts/Rewards/RewardHandler.sol#L75)

	```solidity
	        if (address(_rewardDestination) == address(0x0)) revert InvalidZeroInput();
	```



## L-8: Event is missing `indexed` fields

Index event fields make the field more quickly accessible to off-chain tools that parse events. However, note that each index field costs extra gas during emission, so it's not necessarily best to index the maximum allowed per event (three fields). Each event should use three indexed fields if there are three or more fields, and gas usage is not particularly of concern for the events in question. If there are fewer than three fields, all of the fields should be indexed.

- Found in contracts/Bridge/L1/xRenzoBridge.sol [Line: 25](contracts/Bridge/L1/xRenzoBridge.sol#L25)

	```solidity
	    event EzETHMinted(
	```

- Found in contracts/Bridge/L1/xRenzoBridge.sol [Line: 34](contracts/Bridge/L1/xRenzoBridge.sol#L34)

	```solidity
	    event MessageSent(
	```

- Found in contracts/Bridge/L1/xRenzoBridge.sol [Line: 43](contracts/Bridge/L1/xRenzoBridge.sol#L43)

	```solidity
	    event ConnextMessageSent(
	```

- Found in contracts/Bridge/L2/Oracle/RenzoOracleL2.sol [Line: 15](contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L15)

	```solidity
	    event OracleAddressUpdated(address newOracle, address oldOracle);
	```

- Found in contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol [Line: 24](contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L24)

	```solidity
	    event XRenzoBridgeL1Updated(address newBridgeAddress, address oldBridgeAddress);
	```

- Found in contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol [Line: 25](contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L25)

	```solidity
	    event CCIPEthChainSelectorUpdated(uint64 newSourceChainSelector, uint64 oldSourceChainSelector);
	```

- Found in contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol [Line: 26](contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L26)

	```solidity
	    event XRenzoDepositUpdated(address newRenzoDeposit, address oldRenzoDeposit);
	```

- Found in contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol [Line: 35](contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L35)

	```solidity
	    event MessageReceived(
	```

- Found in contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol [Line: 23](contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L23)

	```solidity
	    event XRenzoBridgeL1Updated(address newBridgeAddress, address oldBridgeAddress);
	```

- Found in contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol [Line: 24](contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L24)

	```solidity
	    event ConnextEthChainDomainUpdated(uint32 newSourceChainDomain, uint32 oldSourceChainDomain);
	```

- Found in contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol [Line: 25](contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L25)

	```solidity
	    event XRenzoDepositUpdated(address newRenzoDeposit, address oldRenzoDeposit);
	```

- Found in contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol [Line: 35](contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L35)

	```solidity
	    event MessageReceived(
	```

- Found in contracts/Bridge/L2/xRenzoDeposit.sol [Line: 42](contracts/Bridge/L2/xRenzoDeposit.sol#L42)

	```solidity
	    event PriceUpdated(uint256 price, uint256 timestamp);
	```

- Found in contracts/Bridge/L2/xRenzoDeposit.sol [Line: 43](contracts/Bridge/L2/xRenzoDeposit.sol#L43)

	```solidity
	    event Deposit(address indexed user, uint256 amountIn, uint256 amountOut);
	```

- Found in contracts/Bridge/L2/xRenzoDeposit.sol [Line: 44](contracts/Bridge/L2/xRenzoDeposit.sol#L44)

	```solidity
	    event BridgeSweeperAddressUpdated(address sweeper, bool allowed);
	```

- Found in contracts/Bridge/L2/xRenzoDeposit.sol [Line: 45](contracts/Bridge/L2/xRenzoDeposit.sol#L45)

	```solidity
	    event BridgeSwept(
	```

- Found in contracts/Bridge/L2/xRenzoDeposit.sol [Line: 51](contracts/Bridge/L2/xRenzoDeposit.sol#L51)

	```solidity
	    event OraclePriceFeedUpdated(address newOracle, address oldOracle);
	```

- Found in contracts/Bridge/L2/xRenzoDeposit.sol [Line: 52](contracts/Bridge/L2/xRenzoDeposit.sol#L52)

	```solidity
	    event ReceiverPriceFeedUpdated(address newReceiver, address oldReceiver);
	```

- Found in contracts/Bridge/L2/xRenzoDeposit.sol [Line: 53](contracts/Bridge/L2/xRenzoDeposit.sol#L53)

	```solidity
	    event SweeperBridgeFeeCollected(address sweeper, uint256 feeCollected);
	```

- Found in contracts/Bridge/L2/xRenzoDeposit.sol [Line: 54](contracts/Bridge/L2/xRenzoDeposit.sol#L54)

	```solidity
	    event BridgeFeeShareUpdated(uint256 oldBridgeFeeShare, uint256 newBridgeFeeShare);
	```

- Found in contracts/Bridge/L2/xRenzoDeposit.sol [Line: 55](contracts/Bridge/L2/xRenzoDeposit.sol#L55)

	```solidity
	    event SweepBatchSizeUpdated(uint256 oldSweepBatchSize, uint256 newSweepBatchSize);
	```

- Found in contracts/Bridge/xERC20/interfaces/IXERC20.sol [Line: 11](contracts/Bridge/xERC20/interfaces/IXERC20.sol#L11)

	```solidity
	    event LockboxSet(address _lockbox);
	```

- Found in contracts/Bridge/xERC20/interfaces/IXERC20.sol [Line: 20](contracts/Bridge/xERC20/interfaces/IXERC20.sol#L20)

	```solidity
	    event BridgeLimitsSet(uint256 _mintingLimit, uint256 _burningLimit, address indexed _bridge);
	```

- Found in contracts/Bridge/xERC20/interfaces/IXERC20Factory.sol [Line: 11](contracts/Bridge/xERC20/interfaces/IXERC20Factory.sol#L11)

	```solidity
	    event XERC20Deployed(address _xerc20);
	```

- Found in contracts/Bridge/xERC20/interfaces/IXERC20Factory.sol [Line: 19](contracts/Bridge/xERC20/interfaces/IXERC20Factory.sol#L19)

	```solidity
	    event LockboxDeployed(address _lockbox);
	```

- Found in contracts/Bridge/xERC20/interfaces/IXERC20Lockbox.sol [Line: 12](contracts/Bridge/xERC20/interfaces/IXERC20Lockbox.sol#L12)

	```solidity
	    event Deposit(address _sender, uint256 _amount);
	```

- Found in contracts/Bridge/xERC20/interfaces/IXERC20Lockbox.sol [Line: 21](contracts/Bridge/xERC20/interfaces/IXERC20Lockbox.sol#L21)

	```solidity
	    event Withdraw(address _sender, uint256 _amount);
	```

- Found in contracts/Delegation/OperatorDelegator.sol [Line: 28](contracts/Delegation/OperatorDelegator.sol#L28)

	```solidity
	    event TokenStrategyUpdated(IERC20 token, IStrategy strategy);
	```

- Found in contracts/Delegation/OperatorDelegator.sol [Line: 29](contracts/Delegation/OperatorDelegator.sol#L29)

	```solidity
	    event DelegationAddressUpdated(address delegateAddress);
	```

- Found in contracts/Delegation/OperatorDelegator.sol [Line: 30](contracts/Delegation/OperatorDelegator.sol#L30)

	```solidity
	    event RewardsForwarded(address rewardDestination, uint256 amount);
	```

- Found in contracts/Delegation/OperatorDelegator.sol [Line: 32](contracts/Delegation/OperatorDelegator.sol#L32)

	```solidity
	    event WithdrawStarted(
	```

- Found in contracts/Delegation/OperatorDelegator.sol [Line: 43](contracts/Delegation/OperatorDelegator.sol#L43)

	```solidity
	    event WithdrawCompleted(bytes32 withdrawalRoot, IStrategy[] strategies, uint256[] shares);
	```

- Found in contracts/Delegation/OperatorDelegator.sol [Line: 45](contracts/Delegation/OperatorDelegator.sol#L45)

	```solidity
	    event GasSpent(address admin, uint256 gasSpent);
	```

- Found in contracts/Delegation/OperatorDelegator.sol [Line: 46](contracts/Delegation/OperatorDelegator.sol#L46)

	```solidity
	    event GasRefunded(address admin, uint256 gasRefunded);
	```

- Found in contracts/Delegation/OperatorDelegator.sol [Line: 47](contracts/Delegation/OperatorDelegator.sol#L47)

	```solidity
	    event BaseGasAmountSpentUpdated(uint256 oldBaseGasAmountSpent, uint256 newBaseGasAmountSpent);
	```

- Found in contracts/Deposits/DepositQueue.sol [Line: 15](contracts/Deposits/DepositQueue.sol#L15)

	```solidity
	    event RewardsDeposited(IERC20 token, uint256 amount);
	```

- Found in contracts/Deposits/DepositQueue.sol [Line: 17](contracts/Deposits/DepositQueue.sol#L17)

	```solidity
	    event FeeConfigUpdated(address feeAddress, uint256 feeBasisPoints);
	```

- Found in contracts/Deposits/DepositQueue.sol [Line: 19](contracts/Deposits/DepositQueue.sol#L19)

	```solidity
	    event RestakeManagerUpdated(IRestakeManager restakeManager);
	```

- Found in contracts/Deposits/DepositQueue.sol [Line: 21](contracts/Deposits/DepositQueue.sol#L21)

	```solidity
	    event ETHDepositedFromProtocol(uint256 amount);
	```

- Found in contracts/Deposits/DepositQueue.sol [Line: 23](contracts/Deposits/DepositQueue.sol#L23)

	```solidity
	    event ETHStakedFromQueue(
	```

- Found in contracts/Deposits/DepositQueue.sol [Line: 30](contracts/Deposits/DepositQueue.sol#L30)

	```solidity
	    event ProtocolFeesPaid(IERC20 token, uint256 amount, address destination);
	```

- Found in contracts/Deposits/DepositQueue.sol [Line: 32](contracts/Deposits/DepositQueue.sol#L32)

	```solidity
	    event GasRefunded(address admin, uint256 gasRefunded);
	```

- Found in contracts/Deposits/DepositQueue.sol [Line: 35](contracts/Deposits/DepositQueue.sol#L35)

	```solidity
	    event WithdrawQueueUpdated(address oldWithdrawQueue, address newWithdrawQueue);
	```

- Found in contracts/Deposits/DepositQueue.sol [Line: 38](contracts/Deposits/DepositQueue.sol#L38)

	```solidity
	    event BufferFilled(address token, uint256 amount);
	```

- Found in contracts/Deposits/DepositQueue.sol [Line: 41](contracts/Deposits/DepositQueue.sol#L41)

	```solidity
	    event FullWithdrawalETHReceived(uint256 amount);
	```

- Found in contracts/EigenLayer/interfaces/IAVSDirectory.sol [Line: 17](contracts/EigenLayer/interfaces/IAVSDirectory.sol#L17)

	```solidity
	    event AVSMetadataURIUpdated(address indexed avs, string metadataURI);
	```

- Found in contracts/EigenLayer/interfaces/IAVSDirectory.sol [Line: 20](contracts/EigenLayer/interfaces/IAVSDirectory.sol#L20)

	```solidity
	    event OperatorAVSRegistrationStatusUpdated(
	```

- Found in contracts/EigenLayer/interfaces/IDelayedWithdrawalRouter.sol [Line: 18](contracts/EigenLayer/interfaces/IDelayedWithdrawalRouter.sol#L18)

	```solidity
	    event DelayedWithdrawalCreated(
	```

- Found in contracts/EigenLayer/interfaces/IDelayedWithdrawalRouter.sol [Line: 26](contracts/EigenLayer/interfaces/IDelayedWithdrawalRouter.sol#L26)

	```solidity
	    event DelayedWithdrawalsClaimed(
	```

- Found in contracts/EigenLayer/interfaces/IDelayedWithdrawalRouter.sol [Line: 33](contracts/EigenLayer/interfaces/IDelayedWithdrawalRouter.sol#L33)

	```solidity
	    event WithdrawalDelayBlocksSet(uint256 previousValue, uint256 newValue);
	```

- Found in contracts/EigenLayer/interfaces/IDelegationManager.sol [Line: 104](contracts/EigenLayer/interfaces/IDelegationManager.sol#L104)

	```solidity
	    event OperatorRegistered(address indexed operator, OperatorDetails operatorDetails);
	```

- Found in contracts/EigenLayer/interfaces/IDelegationManager.sol [Line: 107](contracts/EigenLayer/interfaces/IDelegationManager.sol#L107)

	```solidity
	    event OperatorDetailsModified(address indexed operator, OperatorDetails newOperatorDetails);
	```

- Found in contracts/EigenLayer/interfaces/IDelegationManager.sol [Line: 113](contracts/EigenLayer/interfaces/IDelegationManager.sol#L113)

	```solidity
	    event OperatorMetadataURIUpdated(address indexed operator, string metadataURI);
	```

- Found in contracts/EigenLayer/interfaces/IDelegationManager.sol [Line: 116](contracts/EigenLayer/interfaces/IDelegationManager.sol#L116)

	```solidity
	    event OperatorSharesIncreased(
	```

- Found in contracts/EigenLayer/interfaces/IDelegationManager.sol [Line: 124](contracts/EigenLayer/interfaces/IDelegationManager.sol#L124)

	```solidity
	    event OperatorSharesDecreased(
	```

- Found in contracts/EigenLayer/interfaces/IDelegationManager.sol [Line: 145](contracts/EigenLayer/interfaces/IDelegationManager.sol#L145)

	```solidity
	    event WithdrawalQueued(bytes32 withdrawalRoot, Withdrawal withdrawal);
	```

- Found in contracts/EigenLayer/interfaces/IDelegationManager.sol [Line: 148](contracts/EigenLayer/interfaces/IDelegationManager.sol#L148)

	```solidity
	    event WithdrawalCompleted(bytes32 withdrawalRoot);
	```

- Found in contracts/EigenLayer/interfaces/IDelegationManager.sol [Line: 151](contracts/EigenLayer/interfaces/IDelegationManager.sol#L151)

	```solidity
	    event WithdrawalMigrated(bytes32 oldWithdrawalRoot, bytes32 newWithdrawalRoot);
	```

- Found in contracts/EigenLayer/interfaces/IDelegationManager.sol [Line: 154](contracts/EigenLayer/interfaces/IDelegationManager.sol#L154)

	```solidity
	    event MinWithdrawalDelayBlocksSet(uint256 previousValue, uint256 newValue);
	```

- Found in contracts/EigenLayer/interfaces/IDelegationManager.sol [Line: 157](contracts/EigenLayer/interfaces/IDelegationManager.sol#L157)

	```solidity
	    event StrategyWithdrawalDelayBlocksSet(
	```

- Found in contracts/EigenLayer/interfaces/IETHPOSDeposit.sol [Line: 19](contracts/EigenLayer/interfaces/IETHPOSDeposit.sol#L19)

	```solidity
	    event DepositEvent(
	```

- Found in contracts/EigenLayer/interfaces/IEigenPod.sol [Line: 63](contracts/EigenLayer/interfaces/IEigenPod.sol#L63)

	```solidity
	    event EigenPodStaked(bytes pubkey);
	```

- Found in contracts/EigenLayer/interfaces/IEigenPod.sol [Line: 66](contracts/EigenLayer/interfaces/IEigenPod.sol#L66)

	```solidity
	    event ValidatorRestaked(uint40 validatorIndex);
	```

- Found in contracts/EigenLayer/interfaces/IEigenPod.sol [Line: 70](contracts/EigenLayer/interfaces/IEigenPod.sol#L70)

	```solidity
	    event ValidatorBalanceUpdated(
	```

- Found in contracts/EigenLayer/interfaces/IEigenPod.sol [Line: 77](contracts/EigenLayer/interfaces/IEigenPod.sol#L77)

	```solidity
	    event FullWithdrawalRedeemed(
	```

- Found in contracts/EigenLayer/interfaces/IEigenPod.sol [Line: 85](contracts/EigenLayer/interfaces/IEigenPod.sol#L85)

	```solidity
	    event PartialWithdrawalRedeemed(
	```

- Found in contracts/EigenLayer/interfaces/IEigenPod.sol [Line: 93](contracts/EigenLayer/interfaces/IEigenPod.sol#L93)

	```solidity
	    event RestakedBeaconChainETHWithdrawn(address indexed recipient, uint256 amount);
	```

- Found in contracts/EigenLayer/interfaces/IEigenPod.sol [Line: 99](contracts/EigenLayer/interfaces/IEigenPod.sol#L99)

	```solidity
	    event NonBeaconChainETHReceived(uint256 amountReceived);
	```

- Found in contracts/EigenLayer/interfaces/IEigenPod.sol [Line: 102](contracts/EigenLayer/interfaces/IEigenPod.sol#L102)

	```solidity
	    event NonBeaconChainETHWithdrawn(address indexed recipient, uint256 amountWithdrawn);
	```

- Found in contracts/EigenLayer/interfaces/IEigenPodManager.sol [Line: 27](contracts/EigenLayer/interfaces/IEigenPodManager.sol#L27)

	```solidity
	    event BeaconChainETHDeposited(address indexed podOwner, uint256 amount);
	```

- Found in contracts/EigenLayer/interfaces/IEigenPodManager.sol [Line: 30](contracts/EigenLayer/interfaces/IEigenPodManager.sol#L30)

	```solidity
	    event PodSharesUpdated(address indexed podOwner, int256 sharesDelta);
	```

- Found in contracts/EigenLayer/interfaces/IEigenPodManager.sol [Line: 33](contracts/EigenLayer/interfaces/IEigenPodManager.sol#L33)

	```solidity
	    event BeaconChainETHWithdrawalCompleted(
	```

- Found in contracts/EigenLayer/interfaces/IEigenPodManager.sol [Line: 42](contracts/EigenLayer/interfaces/IEigenPodManager.sol#L42)

	```solidity
	    event DenebForkTimestampUpdated(uint64 newValue);
	```

- Found in contracts/EigenLayer/interfaces/IPausable.sol [Line: 25](contracts/EigenLayer/interfaces/IPausable.sol#L25)

	```solidity
	    event PauserRegistrySet(IPauserRegistry pauserRegistry, IPauserRegistry newPauserRegistry);
	```

- Found in contracts/EigenLayer/interfaces/IPausable.sol [Line: 28](contracts/EigenLayer/interfaces/IPausable.sol#L28)

	```solidity
	    event Paused(address indexed account, uint256 newPausedStatus);
	```

- Found in contracts/EigenLayer/interfaces/IPausable.sol [Line: 31](contracts/EigenLayer/interfaces/IPausable.sol#L31)

	```solidity
	    event Unpaused(address indexed account, uint256 newPausedStatus);
	```

- Found in contracts/EigenLayer/interfaces/IPauserRegistry.sol [Line: 10](contracts/EigenLayer/interfaces/IPauserRegistry.sol#L10)

	```solidity
	    event PauserStatusChanged(address pauser, bool canPause);
	```

- Found in contracts/EigenLayer/interfaces/IPauserRegistry.sol [Line: 12](contracts/EigenLayer/interfaces/IPauserRegistry.sol#L12)

	```solidity
	    event UnpauserChanged(address previousUnpauser, address newUnpauser);
	```

- Found in contracts/EigenLayer/interfaces/ISlasher.sol [Line: 33](contracts/EigenLayer/interfaces/ISlasher.sol#L33)

	```solidity
	    event MiddlewareTimesAdded(
	```

- Found in contracts/EigenLayer/interfaces/ISlasher.sol [Line: 44](contracts/EigenLayer/interfaces/ISlasher.sol#L44)

	```solidity
	    event SlashingAbilityRevoked(
	```

- Found in contracts/EigenLayer/interfaces/ISocketUpdater.sol [Line: 11](contracts/EigenLayer/interfaces/ISocketUpdater.sol#L11)

	```solidity
	    event OperatorSocketUpdate(bytes32 indexed operatorId, string socket);
	```

- Found in contracts/EigenLayer/interfaces/IStrategyManager.sol [Line: 26](contracts/EigenLayer/interfaces/IStrategyManager.sol#L26)

	```solidity
	    event Deposit(address staker, IERC20 token, IStrategy strategy, uint256 shares);
	```

- Found in contracts/EigenLayer/interfaces/IStrategyManager.sol [Line: 29](contracts/EigenLayer/interfaces/IStrategyManager.sol#L29)

	```solidity
	    event UpdatedThirdPartyTransfersForbidden(IStrategy strategy, bool value);
	```

- Found in contracts/EigenLayer/interfaces/IStrategyManager.sol [Line: 32](contracts/EigenLayer/interfaces/IStrategyManager.sol#L32)

	```solidity
	    event StrategyWhitelisterChanged(address previousAddress, address newAddress);
	```

- Found in contracts/EigenLayer/interfaces/IStrategyManager.sol [Line: 35](contracts/EigenLayer/interfaces/IStrategyManager.sol#L35)

	```solidity
	    event StrategyAddedToDepositWhitelist(IStrategy strategy);
	```

- Found in contracts/EigenLayer/interfaces/IStrategyManager.sol [Line: 38](contracts/EigenLayer/interfaces/IStrategyManager.sol#L38)

	```solidity
	    event StrategyRemovedFromDepositWhitelist(IStrategy strategy);
	```

- Found in contracts/Oracle/RenzoOracle.sol [Line: 35](contracts/Oracle/RenzoOracle.sol#L35)

	```solidity
	    event OracleAddressUpdated(IERC20 token, AggregatorV3Interface oracleAddress);
	```

- Found in contracts/RestakeManager.sol [Line: 30](contracts/RestakeManager.sol#L30)

	```solidity
	    event OperatorDelegatorAdded(IOperatorDelegator od);
	```

- Found in contracts/RestakeManager.sol [Line: 31](contracts/RestakeManager.sol#L31)

	```solidity
	    event OperatorDelegatorRemoved(IOperatorDelegator od);
	```

- Found in contracts/RestakeManager.sol [Line: 32](contracts/RestakeManager.sol#L32)

	```solidity
	    event OperatorDelegatorAllocationUpdated(IOperatorDelegator od, uint256 allocation);
	```

- Found in contracts/RestakeManager.sol [Line: 34](contracts/RestakeManager.sol#L34)

	```solidity
	    event CollateralTokenAdded(IERC20 token);
	```

- Found in contracts/RestakeManager.sol [Line: 35](contracts/RestakeManager.sol#L35)

	```solidity
	    event CollateralTokenRemoved(IERC20 token);
	```

- Found in contracts/RestakeManager.sol [Line: 41](contracts/RestakeManager.sol#L41)

	```solidity
	    event Deposit(
	```

- Found in contracts/RestakeManager.sol [Line: 50](contracts/RestakeManager.sol#L50)

	```solidity
	    event UserWithdrawStarted(
	```

- Found in contracts/RestakeManager.sol [Line: 59](contracts/RestakeManager.sol#L59)

	```solidity
	    event UserWithdrawCompleted(
	```

- Found in contracts/RestakeManager.sol [Line: 68](contracts/RestakeManager.sol#L68)

	```solidity
	    event CollateralTokenTvlUpdated(IERC20 token, uint256 tvl);
	```

- Found in contracts/Rewards/RewardHandler.sol [Line: 29](contracts/Rewards/RewardHandler.sol#L29)

	```solidity
	    event RewardDestinationUpdated(address rewardDestination);
	```

- Found in contracts/TimelockController.sol [Line: 38](contracts/TimelockController.sol#L38)

	```solidity
	    event CallScheduled(
	```

- Found in contracts/TimelockController.sol [Line: 51](contracts/TimelockController.sol#L51)

	```solidity
	    event CallExecuted(
	```

- Found in contracts/TimelockController.sol [Line: 62](contracts/TimelockController.sol#L62)

	```solidity
	    event CallSalt(bytes32 indexed id, bytes32 salt);
	```

- Found in contracts/TimelockController.sol [Line: 72](contracts/TimelockController.sol#L72)

	```solidity
	    event MinDelayChange(uint256 oldDuration, uint256 newDuration);
	```

- Found in contracts/Withdraw/WithdrawQueue.sol [Line: 19](contracts/Withdraw/WithdrawQueue.sol#L19)

	```solidity
	    event WithdrawBufferTargetUpdated(uint256 oldBufferTarget, uint256 newBufferTarget);
	```

- Found in contracts/Withdraw/WithdrawQueue.sol [Line: 21](contracts/Withdraw/WithdrawQueue.sol#L21)

	```solidity
	    event CoolDownPeriodUpdated(uint256 oldCoolDownPeriod, uint256 newCoolDownPeriod);
	```

- Found in contracts/Withdraw/WithdrawQueue.sol [Line: 23](contracts/Withdraw/WithdrawQueue.sol#L23)

	```solidity
	    event EthBufferFilled(uint256 amount);
	```

- Found in contracts/Withdraw/WithdrawQueue.sol [Line: 25](contracts/Withdraw/WithdrawQueue.sol#L25)

	```solidity
	    event ERC20BufferFilled(address asset, uint256 amount);
	```

- Found in contracts/Withdraw/WithdrawQueue.sol [Line: 27](contracts/Withdraw/WithdrawQueue.sol#L27)

	```solidity
	    event WithdrawRequestCreated(
	```

- Found in contracts/Withdraw/WithdrawQueue.sol [Line: 36](contracts/Withdraw/WithdrawQueue.sol#L36)

	```solidity
	    event WithdrawRequestClaimed(WithdrawRequest withdrawRequest);
	```



## L-9: The `nonReentrant` `modifier` should occur before all other modifiers

This is a best-practice to protect against reentrancy in other modifiers.

- Found in contracts/Bridge/L1/xRenzoBridge.sol [Line: 213](contracts/Bridge/L1/xRenzoBridge.sol#L213)

	```solidity
	    ) external payable onlyPriceFeedSender nonReentrant {
	```

- Found in contracts/Deposits/DepositQueue.sol [Line: 216](contracts/Deposits/DepositQueue.sol#L216)

	```solidity
	    ) external onlyNativeEthRestakeAdmin nonReentrant {
	```



## L-10: PUSH0 is not supported by all chains

Solc compiler version 0.8.20 switches the default target EVM version to Shanghai, which means that the generated bytecode will include PUSH0 opcodes. Be sure to select the appropriate EVM version in case you intend to deploy on a chain other than mainnet like L2 chains that may not support PUSH0, otherwise deployment of your contracts will fail.

- Found in contracts/Bridge/Connext/core/IConnext.sol [Line: 2](contracts/Bridge/Connext/core/IConnext.sol#L2)

	```solidity
	pragma solidity ^0.8.0;
	```

- Found in contracts/Bridge/Connext/core/IWeth.sol [Line: 2](contracts/Bridge/Connext/core/IWeth.sol#L2)

	```solidity
	pragma solidity ^0.8.0;
	```

- Found in contracts/Bridge/Connext/core/IXReceiver.sol [Line: 2](contracts/Bridge/Connext/core/IXReceiver.sol#L2)

	```solidity
	pragma solidity ^0.8.0;
	```

- Found in contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol [Line: 2](contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L2)

	```solidity
	pragma solidity ^0.8.13;
	```

- Found in contracts/Bridge/Connext/libraries/LibConnextStorage.sol [Line: 2](contracts/Bridge/Connext/libraries/LibConnextStorage.sol#L2)

	```solidity
	pragma solidity ^0.8.0;
	```

- Found in contracts/Bridge/Connext/libraries/TokenId.sol [Line: 2](contracts/Bridge/Connext/libraries/TokenId.sol#L2)

	```solidity
	pragma solidity ^0.8.0;
	```

- Found in contracts/Bridge/xERC20/contracts/XERC20.sol [Line: 2](contracts/Bridge/xERC20/contracts/XERC20.sol#L2)

	```solidity
	pragma solidity >=0.8.4 <0.9.0;
	```

- Found in contracts/Bridge/xERC20/contracts/XERC20Factory.sol [Line: 2](contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L2)

	```solidity
	pragma solidity >=0.8.4 <0.9.0;
	```

- Found in contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol [Line: 2](contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L2)

	```solidity
	pragma solidity >=0.8.4 <0.9.0;
	```

- Found in contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol [Line: 2](contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L2)

	```solidity
	pragma solidity >=0.8.4 <0.9.0;
	```

- Found in contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol [Line: 2](contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L2)

	```solidity
	pragma solidity >=0.8.4 <0.9.0;
	```

- Found in contracts/Bridge/xERC20/interfaces/IOptimismMintableERC20.sol [Line: 2](contracts/Bridge/xERC20/interfaces/IOptimismMintableERC20.sol#L2)

	```solidity
	pragma solidity >=0.8.4 <0.9.0;
	```

- Found in contracts/Bridge/xERC20/interfaces/IXERC20.sol [Line: 2](contracts/Bridge/xERC20/interfaces/IXERC20.sol#L2)

	```solidity
	pragma solidity >=0.8.4 <0.9.0;
	```

- Found in contracts/Bridge/xERC20/interfaces/IXERC20Factory.sol [Line: 2](contracts/Bridge/xERC20/interfaces/IXERC20Factory.sol#L2)

	```solidity
	pragma solidity >=0.8.4 <0.9.0;
	```

- Found in contracts/Bridge/xERC20/interfaces/IXERC20Lockbox.sol [Line: 2](contracts/Bridge/xERC20/interfaces/IXERC20Lockbox.sol#L2)

	```solidity
	pragma solidity >=0.8.4 <0.9.0;
	```

- Found in contracts/EigenLayer/interfaces/IAVSDirectory.sol [Line: 2](contracts/EigenLayer/interfaces/IAVSDirectory.sol#L2)

	```solidity
	pragma solidity >=0.5.0;
	```

- Found in contracts/EigenLayer/interfaces/IBeaconChainOracle.sol [Line: 2](contracts/EigenLayer/interfaces/IBeaconChainOracle.sol#L2)

	```solidity
	pragma solidity >=0.5.0;
	```

- Found in contracts/EigenLayer/interfaces/IDelayedWithdrawalRouter.sol [Line: 2](contracts/EigenLayer/interfaces/IDelayedWithdrawalRouter.sol#L2)

	```solidity
	pragma solidity >=0.5.0;
	```

- Found in contracts/EigenLayer/interfaces/IDelegationFaucet.sol [Line: 2](contracts/EigenLayer/interfaces/IDelegationFaucet.sol#L2)

	```solidity
	pragma solidity >=0.5.0;
	```

- Found in contracts/EigenLayer/interfaces/IDelegationManager.sol [Line: 2](contracts/EigenLayer/interfaces/IDelegationManager.sol#L2)

	```solidity
	pragma solidity >=0.5.0;
	```

- Found in contracts/EigenLayer/interfaces/IETHPOSDeposit.sol [Line: 12](contracts/EigenLayer/interfaces/IETHPOSDeposit.sol#L12)

	```solidity
	pragma solidity >=0.5.0;
	```

- Found in contracts/EigenLayer/interfaces/IEigenPod.sol [Line: 2](contracts/EigenLayer/interfaces/IEigenPod.sol#L2)

	```solidity
	pragma solidity >=0.5.0;
	```

- Found in contracts/EigenLayer/interfaces/IEigenPodManager.sol [Line: 2](contracts/EigenLayer/interfaces/IEigenPodManager.sol#L2)

	```solidity
	pragma solidity >=0.5.0;
	```

- Found in contracts/EigenLayer/interfaces/IPausable.sol [Line: 2](contracts/EigenLayer/interfaces/IPausable.sol#L2)

	```solidity
	pragma solidity >=0.5.0;
	```

- Found in contracts/EigenLayer/interfaces/IPauserRegistry.sol [Line: 2](contracts/EigenLayer/interfaces/IPauserRegistry.sol#L2)

	```solidity
	pragma solidity >=0.5.0;
	```

- Found in contracts/EigenLayer/interfaces/ISignatureUtils.sol [Line: 2](contracts/EigenLayer/interfaces/ISignatureUtils.sol#L2)

	```solidity
	pragma solidity >=0.5.0;
	```

- Found in contracts/EigenLayer/interfaces/ISlasher.sol [Line: 2](contracts/EigenLayer/interfaces/ISlasher.sol#L2)

	```solidity
	pragma solidity >=0.5.0;
	```

- Found in contracts/EigenLayer/interfaces/IStrategy.sol [Line: 2](contracts/EigenLayer/interfaces/IStrategy.sol#L2)

	```solidity
	pragma solidity >=0.5.0;
	```

- Found in contracts/EigenLayer/interfaces/IStrategyManager.sol [Line: 2](contracts/EigenLayer/interfaces/IStrategyManager.sol#L2)

	```solidity
	pragma solidity >=0.5.0;
	```

- Found in contracts/EigenLayer/interfaces/IWhitelister.sol [Line: 2](contracts/EigenLayer/interfaces/IWhitelister.sol#L2)

	```solidity
	pragma solidity >=0.5.0;
	```

- Found in contracts/EigenLayer/libraries/BytesLib.sol [Line: 9](contracts/EigenLayer/libraries/BytesLib.sol#L9)

	```solidity
	pragma solidity >=0.8.0 <0.9.0;
	```

- Found in contracts/EigenLayer/libraries/Endian.sol [Line: 2](contracts/EigenLayer/libraries/Endian.sol#L2)

	```solidity
	pragma solidity ^0.8.0;
	```

- Found in contracts/EigenLayer/libraries/Merkle.sol [Line: 4](contracts/EigenLayer/libraries/Merkle.sol#L4)

	```solidity
	pragma solidity ^0.8.0;
	```

- Found in contracts/TimelockController.sol [Line: 4](contracts/TimelockController.sol#L4)

	```solidity
	pragma solidity ^0.8.0;
	```

- Found in contracts/token/EzEthToken.sol [Line: 2](contracts/token/EzEthToken.sol#L2)

	```solidity
	pragma solidity ^0.8.9;
	```

- Found in contracts/token/IEzEthToken.sol [Line: 2](contracts/token/IEzEthToken.sol#L2)

	```solidity
	pragma solidity ^0.8.9;
	```



## L-11: Modifiers invoked only once can be shoe-horned into the function



- Found in contracts/Bridge/L1/xRenzoBridge.sol [Line: 55](contracts/Bridge/L1/xRenzoBridge.sol#L55)

	```solidity
	    modifier onlyPriceFeedSender() {
	```

- Found in contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol [Line: 43](contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L43)

	```solidity
	    modifier onlySource(address _originSender, uint32 _origin) {
	```

- Found in contracts/Deposits/DepositQueue.sol [Line: 62](contracts/Deposits/DepositQueue.sol#L62)

	```solidity
	    modifier onlyERC20RewardsAdmin() {
	```

- Found in contracts/Oracle/RenzoOracle.sol [Line: 29](contracts/Oracle/RenzoOracle.sol#L29)

	```solidity
	    modifier onlyOracleAdmin() {
	```

- Found in contracts/RestakeManager.sol [Line: 77](contracts/RestakeManager.sol#L77)

	```solidity
	    modifier onlyDepositWithdrawPauserAdmin() {
	```

- Found in contracts/Rewards/RewardHandler.sol [Line: 18](contracts/Rewards/RewardHandler.sol#L18)

	```solidity
	    modifier onlyNativeEthRestakeAdmin() {
	```

- Found in contracts/Rewards/RewardHandler.sol [Line: 24](contracts/Rewards/RewardHandler.sol#L24)

	```solidity
	    modifier onlyRestakeManagerAdmin() {
	```

- Found in contracts/token/EzEthToken.sol [Line: 21](contracts/token/EzEthToken.sol#L21)

	```solidity
	    modifier onlyTokenAdmin() {
	```



## L-12: Large literal values multiples of 10000 can be replaced with scientific notation

Use `e` notation, for example: `1e18`, instead of its full numeric value.

- Found in contracts/Bridge/L2/xRenzoDeposit.sol [Line: 40](contracts/Bridge/L2/xRenzoDeposit.sol#L40)

	```solidity
	    uint32 public constant FEE_BASIS = 10000;
	```

- Found in contracts/Deposits/DepositQueue.sol [Line: 103](contracts/Deposits/DepositQueue.sol#L103)

	```solidity
	        if (_feeBasisPoints > 10000) revert OverMaxBasisPoints();
	```

- Found in contracts/Deposits/DepositQueue.sol [Line: 167](contracts/Deposits/DepositQueue.sol#L167)

	```solidity
	            feeAmount = (msg.value * feeBasisPoints) / 10000;
	```

- Found in contracts/Deposits/DepositQueue.sol [Line: 261](contracts/Deposits/DepositQueue.sol#L261)

	```solidity
	                feeAmount = (balance * feeBasisPoints) / 10000;
	```

- Found in contracts/EigenLayer/libraries/Endian.sol [Line: 17](contracts/EigenLayer/libraries/Endian.sol#L17)

	```solidity
	            ((0x00FF000000000000 & n) >> 40) |
	```

- Found in contracts/EigenLayer/libraries/Endian.sol [Line: 18](contracts/EigenLayer/libraries/Endian.sol#L18)

	```solidity
	            ((0x0000FF0000000000 & n) >> 24) |
	```

- Found in contracts/EigenLayer/libraries/Endian.sol [Line: 19](contracts/EigenLayer/libraries/Endian.sol#L19)

	```solidity
	            ((0x000000FF00000000 & n) >> 8) |
	```

- Found in contracts/EigenLayer/libraries/Endian.sol [Line: 20](contracts/EigenLayer/libraries/Endian.sol#L20)

	```solidity
	            ((0x00000000FF000000 & n) << 8) |
	```

- Found in contracts/EigenLayer/libraries/Endian.sol [Line: 21](contracts/EigenLayer/libraries/Endian.sol#L21)

	```solidity
	            ((0x0000000000FF0000 & n) << 24) |
	```



## L-13: Internal functions called only once can be inlined

Instead of separating the logic into a separate function, consider inlining the logic into the calling function. This can reduce the number of function calls and improve readability.

- Found in contracts/EigenLayer/libraries/BeaconChainProofs.sol [Line: 339](contracts/EigenLayer/libraries/BeaconChainProofs.sol#L339)

	```solidity
	    function getWithdrawalTimestamp(
	```

- Found in contracts/EigenLayer/libraries/Merkle.sol [Line: 48](contracts/EigenLayer/libraries/Merkle.sol#L48)

	```solidity
	    function processInclusionProofKeccak(
	```

- Found in contracts/EigenLayer/libraries/Merkle.sol [Line: 107](contracts/EigenLayer/libraries/Merkle.sol#L107)

	```solidity
	    function processInclusionProofSha256(
	```

- Found in contracts/EigenLayer/libraries/StructuredLinkedList.sol [Line: 161](contracts/EigenLayer/libraries/StructuredLinkedList.sol#L161)

	```solidity
	    function remove(List storage self, uint256 _node) internal returns (uint256) {
	```



## L-14: Inconsistency in declaring uint256/uint (or) int256/int variables within a contract

Consider keeping the naming convention consistent in a given contract

- Found in contracts/Delegation/OperatorDelegator.sol [Line: 17](contracts/Delegation/OperatorDelegator.sol#L17)

	```solidity
	contract OperatorDelegator is
	```

