
## Low Risk Findings

| Number        | issue           | Instances  |
| ------------- |:-------------:| -----:|
| [L-01] | CCIP Router addresses cannot be updated in `CCIPReceiver` | 1 |
| [L-02] | Low level calls to account with no code will not fail      |   3 |
| [L-03] | Prevent gas griefing attacks that’s possible with custom address.call      |  3 |
| [L-04] | Missing Minimum Output slippage in `_trade` Function    |  1 |
| [L-05] | Streamlining token approvals      |  1 |
| [L-06] | Lack of Rate Limiting in sendPrice Function      |  1 |
| [L-07] | NonReentrant modifier should start     |  1 |
| [L-08] | No deadline check for signatures    |  1 |
| [L-09] | Unhandled chainlink revert would lock all price oracle access   |  1 |
| [L-10] | Potential premature exit in `setOperatorDelegatorAllocation` function   |  1 |

## [L-01] : CCIP Router addresses cannot be updated in `CCIPReceiver`

On contracts that inherit from CCIPReceiver, router addresses need to be updateable. Chainlink may update the router addresses as they did before. This issue introduces a single point of failure that is outside of the protocol's control.

An example contract that chainlink uses to demonstrate how to use the CCIPReceiver

https://github.com/smartcontractkit/ccip-tic-tac-toe/blob/main/contracts/TTTDemo.sol

here is the line they update the router

https://github.com/smartcontractkit/ccip-tic-tac-toe/blob/main/contracts/TTTDemo.sol#L81

Chainlink documents notifying users about router address updating on testnet.

https://docs.chain.link/ccip/release-notes#v120-release-on-testnet---2023-12-08

```
CCIP v1.0.0 has been deprecated on testnet. You must use the new router addresses mentioned in the CCIP v1.2.0 configuration page before January 31st, 2024
```

On Testnets, router contracts in v1.0.0 and v1.2.0 are different. It means that router contract addresses can change from version to version. So CCIPReceivers should accommodate this. Mainnet is on v1.0.0 which means its router addresses can change with an update.


Router address deprecation will cause the protocol to stop working.

Tools Used
Manual review.

Recommendations
Implement a function to update the _router address. Example shown below:

```javascript
function updateRouter(address routerAddr) external onlyOwner {
        _router = routerAddr;
    }
```

## [L-02] : Low level calls to account with no code will not fail 

Low level calls to account with no code will not fail

Low level calls `(i.e. address.call(...))` to account with no code will silently succeed without reverting or throwing any error. Quoting the reference for the CALL opcode in evm.codes:

Creates a new sub context and execute the code of the given account, then resumes the current one. Note that an account with no code will return success as true.

***Instances***

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L131

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Delegation/OperatorDelegator.sol#L520

## [L-03] : Prevent gas griefing attacks that’s possible with custom address.call 

Whenever the returned bytes data is not required, using the .call() function with non TRUSTED addresses opens the transaction to unnecessary gas griefing by return huge bytes data.

Note that this:

```javascript
(bool success, ) = payable(msg.sender).call{ value: feeCollected }("");
        if (!success) revert TransferFailed();

```
So in both cases, the bytes data is returned and copied to memory. Malicious target address can return huge bytes data to cause gas grief to the sender. 

Impact:
Malicious target address can gas grief the sender making the sender waste more gas than necessary.

Recommendation:
Short term: When returned data is not required, use a low level call:

```javascript
(bool success, ) = payable(msg.sender).call{ value: feeCollected }("");
if (!success) {
    assembly {
        revert(0, 0)
    }
}
```
Long Term: Consider using https://github.com/nomad-xyz/ExcessivelySafeCall

***Instances***

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L131

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Delegation/OperatorDelegator.sol#L520


## [L-04] : Missing Minimum Output slippage in `_trade` Function

The _trade function within the `xRenzoDeposit` contract does not enforce a minimum output requirement (minOut). However, it is called within the _deposit function, where the minimum output requirement is enforced. This may introduce a potential risk if the _trade function is used elsewhere in the contract or if its usage changes in the future considering the contract is upgradable.

```javascript
function _trade(uint256 _amountIn, uint256 _deadline) internal returns (uint256) {
        // Approve the deposit asset to the connext contract
        depositToken.safeApprove(address(connext), _amountIn);

        // We will accept any amount of tokens out here... The caller of this function should verify the amount meets minimums
        uint256 minOut = 0;

        // Swap the tokens
        uint256 amountNextWETH = connext.swapExact(
            swapKey,
            _amountIn,
            address(depositToken),
            address(collateralToken),
            minOut,
            _deadline
        );

        // Subtract the bridge router fee
        if (bridgeRouterFeeBps > 0) {
            uint256 fee = (amountNextWETH * bridgeRouterFeeBps) / 10_000;
            amountNextWETH -= fee;
        }

        return amountNextWETH;
    }
```

The current implementation relies on the `_deposit` function to enforce the minimum output requirement, which may increase code complexity and reduce modularity. However, since the requirement is enforced at a higher level, the risk is minimal.
Recommendation:
Consider adding a minimum output requirement to the _trade function for better code modularity and to prevent potential misuse in case the function is used elsewhere in the contract or if its usage changes in the future.

## [L-05] : Streamlining token approvals

Streamlining token approvals in 

Incorporating forceApprove(), could offer a more streamlined approach to managing ERC20 token allowances; particularly in complex interactions involving asset transfers . By enabling the contract to set precise allowances in a single step, this method could eliminate the need for conditional checks and subsequent resetting of allowances, thus simplifying the logic and potentially enhancing contract efficiency. 

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Bridge/L1/xRenzoBridge.sol#L241

```javascript
  linkToken.approve(address(linkRouterClient), fees);
```

## [L-06] : Lack of Rate Limiting in sendPrice Function

The sendPrice function facilitates the transmission of price feed data from Layer 2 (L2) to Layer 1 (L1) and other destinations. However, it lacks rate limiting, which poses security risks and potential abuse scenarios.

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
            uint256 fees = linkRouterClient.getFee( 
                _destinationParam[i].destinationChainSelector,
                evm2AnyMessage
            );

            if (fees > linkToken.balanceOf(address(this)))
                revert NotEnoughBalance(linkToken.balanceOf(address(this)), fees);

            // approve the Router to transfer LINK tokens on contract's behalf. It will spend the fees in LINK
            linkToken.approve(address(linkRouterClient), fees);

            // Send the message through the router and store the returned message ID
            bytes32 messageId = linkRouterClient.ccipSend(
                _destinationParam[i].destinationChainSelector,
                evm2AnyMessage
            );

            // Emit an event with message details
            emit MessageSent(
                messageId,
                _destinationParam[i].destinationChainSelector,
                _destinationParam[i]._renzoReceiver,
                exchangeRate,
                address(linkToken),
                fees
            );
            unchecked {
                ++i;
            }
        }

        // send price feed to renzo connext receiver
        for (uint256 i = 0; i < _connextDestinationParam.length; ) {
            connext.xcall{ value: _connextDestinationParam[i].relayerFee }(
                _connextDestinationParam[i].destinationDomainId,
                _connextDestinationParam[i]._renzoReceiver,
                address(0),
                msg.sender,
                0,
                0,
                _callData
            );

            emit ConnextMessageSent(
                _connextDestinationParam[i].destinationDomainId,
                _connextDestinationParam[i]._renzoReceiver,
                exchangeRate,
                _connextDestinationParam[i].relayerFee
            );

            unchecked {
                ++i;
            }
        }
    }
```


The function does not implement rate limits for sending price feed data. This omission allows potential abuse, including spamming the function with multiple calls, causing unnecessary congestion and potential disruptions to the bridge system.
Potential for Abuse:
Without rate limits, malicious actors or malfunctioning components could exploit the function to overwhelm the network or drain resources by repeatedly sending price feed data. This could lead to excessive gas consumption, network congestion, and potential financial loss.

Implement Rate Limits:
Introduce rate limiting mechanisms on a per-lane basis with aggregate limits to control the frequency of price feed transmissions. This should include well-defined throughput rates and refill rates to prevent abuse and ensure optimal resource usage.


## [L-07]: NonReentrant modifier should start

The order of modifiers can influence the behavior of a function. Generally, NonReentrant must come first than other modifiers.

 The nonReentrant modifier could be placed and executed before other modifiers in functions to prevent reentrancies through other modifiers and make code more efficient. To follow the best practice, please consider placing the nonReentrant modifier first. 

Remediation:
Reorder modifiers so that NonReentrant is placed before other modifiers.

***Instances***

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Bridge/L1/xRenzoBridge.sol#L213



## [L-08] : No deadline check for signatures 

The stakeEth function uses a signature to ensure only authorized parties can call the function

```Javascript
 function stakeEth(
        bytes calldata pubkey,
        bytes calldata signature,
        bytes32 depositDataRoot
    ) external payable onlyRestakeManager {
        // Call the stake function in the EigenPodManager
        eigenPodManager.stake{ value: msg.value }(pubkey, signature, depositDataRoot);

        // Increment the staked but not verified ETH
        stakedButNotVerifiedEth += msg.value;
    }
```

The signature should not be valid forever and therefore the function should consider using deadline for it

## [L-09] : Unhandled chainlink revert would lock all price oracle access

Call to `latestRoundData` could potentially revert and make it impossible to query any prices. Feeds cannot be changed after they are configured
this would result in a permanent denial of service.

Proof of Concept
Chainlink's multisigs can immediately block access to price feeds at will. Therefore, to prevent denial of service scenarios, it is recommended to query Chainlink price feeds using a defensive approach with Solidity’s try/catch structure. In this way, if the call to the price feed fails, the caller contract is still in control and can handle any errors safely and explicitly.

```javascript

        (, int256 price, , uint256 timestamp, ) = oracle.latestRoundData();
        if (timestamp < block.timestamp - MAX_TIME_WINDOW) revert OraclePriceExpired();
        if (price <= 0) revert InvalidOraclePrice();

        // Price is times 10**18 ensure token amount is scaled
        return (_value * SCALE_FACTOR) / uint256(price);
    }

```


Tools Used
Manual Review

Recommended Mitigation Steps
Surround the call to latestRoundData() with try/catch instead of calling it directly. In a scenario where the call reverts, the catch block can be used to call a fallback oracle or handle the error in any other suitable way. 

***Instances***

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Oracle/RenzoOracle.sol#L92

## [L-10] : Potential premature exit in `setOperatorDelegatorAllocation` function

 The setOperatorDelegatorAllocation function in the smart contract has a potential issue with the use of the break statement inside the for loop. If the condition for the break statement is met, the loop will exit prematurely without iterating through the entire array of operatorDelegators. This could lead to misconfigurations or missed allocations if there are duplicate entries in the array.

```javascript
 // Ensure the OD is in the list to prevent mis-configuration
        bool foundOd = false;
        uint256 odLength = operatorDelegators.length;
        for (uint256 i = 0; i < odLength; ) {
            if (address(operatorDelegators[i]) == address(_operatorDelegator)) {
                foundOd = true;
                break;
            }
            unchecked {
                ++i;
            }
        }
        if (!foundOd) revert NotFound();

```

Impact: If there are duplicate entries in the operatorDelegators array, the premature exit of the loop could result in certain items not being checked for, potentially leading to misconfigurations or missed allocations. This could introduce vulnerabilities or unexpected behavior in the contract.

Recommendation: Refactor the function to ensure that all items in the operatorDelegators array are properly checked before proceeding. Instead of using break, use a straightforward iteration through the array without premature exits. This will ensure that all items are properly handled. 

***Instances***
https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/RestakeManager.sol#L200


## Non-Critical Findings

| Number        | issue           | Instances  |
| ------------- |:-------------:| -----:|
| [NC-01] | Activate the Optimizer | 1 |
| [NC-02] | Navigating new frontiers in transaction fairness    |   1 |
| [NC-03] | Use constants for literal or magic values     |  4 |
| [NC-04] | Typos in Natspec comments    |  7 |
| [NC-05] | Private function with embedded modifier reduces contract size      |  4 |
| [NC-06] | Else block is not required    |  2 |
| [NC-07] | Missing event for important parameter change     |  1 |
| [NC-08] | Miss-matching comments could be confusing    |  4 |
| [NC-09] | Pausable could be bypassed    |  1 |


## [NC-01] : Activate the Optimizer

Before deploying your contract, activate the optimizer when compiling using “solc —optimize —bin sourceFile.sol”. By default, the optimizer will optimize the contract assuming it is called 200 times across its lifetime. If you want the initial contract deployment to be cheaper and the later function executions to be more expensive, set it to “ —optimize-runs=1”. Conversely, if you expect many transactions and do not care for higher deployment cost and output size, set “—optimize-runs” to a high number.

module.exports = {
solidity: {
version: "0.8.24",
settings: {
optimizer: {
  enabled: true,
  runs: 1000,
},
},
},
};
Please visit this site for further information:

https://docs.soliditylang.org/en/v0.5.4/using-the-compiler.html#using-the-commandline-compiler

Here’s one example of instance on opcode comparison that delineates the gas saving mechanism:

for !=0 before optimization
PUSH1 0x00
DUP2
EQ
ISZERO
PUSH1 [cont offset]
JUMPI
after optimization
DUP1
PUSH1 [revert offset]
JUMPI
Disclaimer: There have been several bugs with security implications related to optimizations. For this reason, Solidity compiler optimizations are disabled by default, and it is unclear how many contracts in the wild actually use them. Therefore, it is unclear how well they are being tested and exercised. High-severity security issues due to optimization bugs have occurred in the past.


## [NC-02] : Navigating new frontiers in transaction fairness

Navigating new frontiers in transaction fairness
As Layer 2, like Arbitrum or Base, considers moving towards a more decentralized sequencer model, the platform faces the challenge of maintaining its current mitigation of frontrunning risks inherent in a “first come, first served” system.

The transition could reintroduce vulnerabilities to transaction ordering manipulation, demanding innovative solutions to uphold transaction fairness. Strategies such as commit-reveal schemes, submarine sends, Fair Sequencing Services (FSS), decentralized MEV mitigation techniques, and the incorporation of time-locks and randomness could play pivotal roles. These measures aim to preserve the integrity of transaction sequencing, ensuring that the L2’s evolution towards decentralization enhances its ecosystem without compromising the security and fairness that are crucial for user trust and platform reliability.

## [NC-03] : Use constants for literal or magic values

Use constants for literal or magic values

Consider defining constants for literal or magic values as it improves readability and prevents duplication of config values.

***Instances***

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Bridge/L1/xRenzoBridge.sol#L225

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Bridge/L2/xRenzoDeposit.sol#L155

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Bridge/L2/xRenzoDeposit.sol#L152

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/RestakeManager.sol#L231


## [NC-04] : Typos in Natspec comments 

Typos in Natspec comments

***Instances***

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Bridge/L1/xRenzoBridge.sol#L171 `amonut`

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Bridge/L1/xRenzoBridge.sol#L171  `onlyOnwer`

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L93  `onlyOnwer`

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L89  `onlyOnwer`

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L89  `onlyOnwer`

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L127


## [NC-05] : Private function with embedded modifier reduces contract size

Private function with embedded modifier reduces contract size

Consider having the logic of a modifier embedded through a private function to reduce contract size if need be. A private visibility that is more efficient on function calls than the internal visibility is adopted because the modifier will only be making this call inside the contract.

```javascript
  if (_newXRenzoDeposit == address(0)) revert InvalidZeroInput();
```
```javascript
  if (_newChainSelector == 0) revert InvalidZeroInput();
```
```javascript
  if (msg.sender != FACTORY) revert IXERC20_NotFactory();
```
```javascript
    if (_amount == 0) revert IXERC20_INVALID_0_VALUE();
```

add modifiers and use then in functions directly for instance

```javascript
modifier validAddress(address _address) {
    require(_address != address(0), "InvalidZeroInput");
    _;
}
```
this modifier could be used in a function directly

```javascript
function updateXRenzoBridgeL1(address _newXRenzoDeposit) external validAddress(_newXRenzoDeposit) {
    // Function logic
}
```

## [NC-06] : Else block is not required 

One level of nesting can be removed by not having an else block when the if-block returns,

***Instances***

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Bridge/L2/xRenzoDeposit.sol#L279

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Bridge/xERC20/contracts/XERC20.sol#L309


##  [NC-07] : Missing event for important parameter change 


Important parameter or configuration changes should trigger an event to allow being tracked off-chain.

***Instances***

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Bridge/L1/xRenzoBridge.sol#L70

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Bridge/L1/xRenzoBridge.sol#L294

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Bridge/L1/xRenzoBridge.sol#L305

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Delegation/OperatorDelegator.sol#L74

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Delegation/OperatorDelegator.sol#L101

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Delegation/OperatorDelegator.sol#L143

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Delegation/OperatorDelegator.sol#L349


## [NC-08]  Miss-matching comments could be confusing

function comments are interchanged which could be very confusing while pausing and unPausing contracts

***Instances***

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L122

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L114

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L118

https://github.com/code-423n4/2024-04-renzo/blob/main/contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L110

## [NC-09] : Pausable could be bypassed 

It's generally recommended to use well-tested, audited, and community-reviewed contracts like `OpenZeppelin's Pausable` rather than implementing your own. These contracts have undergone thorough security reviews and are less likely to have vulnerabilities. Moreover, they often provide additional functionality and flexibility, such as pausing only specific functions or providing emergency stop functionalities. 



