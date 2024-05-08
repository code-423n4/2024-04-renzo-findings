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
...
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

