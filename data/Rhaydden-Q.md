## Quality Assurance



<details>
  <summary> NOTE</summary>

---

To maintain clarity and conciseness, we have selectively shortened the provided code snippets to highlight the most pertinent parts. Some sections may be condensed, and certain references are accessible through search commands due to the project's scope and time limitations.

---

Note to the judge: To avoid cluttering the judging repo, we have included some potentially subjective findings in this report that could be considered either _`medium or low severity`_. We have indicated these instances within the reports. If the judge deems it appropriate, we would appreciate these findings being upgraded accordingly."

---

</details>



## Table of Contents

| Issue ID | Description |
| -------- | ----------- |
| [QA-01](#qa-01-hardcoded-gas-limit-in-ccip-message-sending-leads-to-potential-excess-gas-usage) | Hardcoded Gas Limit in CCIP Message Sending Leads to Potential Excess Gas Usage |
| [QA-02](#qa-02-lack-of-solvency-checks-in-removecollateraltoken-function) | Lack of Solvency Checks in `removeCollateralToken` Function |
| [QA-03](#qa-03-potential-for-link-token-approval-overwriting-in-sendprice-function) | Potential for LINK token approval overwriting in `sendPrice` function |
| [QA-04](#qa-04-unchecked-link-token-approval-in-sendprice-function) | Unchecked LINK Token Approval in `sendPrice` Function |
| [QA-05](#qa-05-abiencodepacked-should-not-be-used-with-dynamic-types-when-passing-the-result-to-a-hash-function-such-as-keccak256) | `abi.encodePacked()` should not be used with dynamic types when passing the result to a hash function such as `keccak256()` |
| [QA-06](#qa-06-incorrect-maxdeposit-tvl-value-may-prevent-users-from-depositing-funds) | Incorrect `maxDepositTVL` value may prevent users from depositing funds |
| [QA-07](#qa-07-absence-of-timelock-to-critical-functions) | Absence of timelock to critical functions |
| [QA-08](#qa-08-redundant-usage-of-safecast) | Redundant usage of `safecast` |
| [QA-09](#qa-09-logic-issue) | Logic Issue |
| [QA-10](#qa-10-external-calls-inside-a-loop-in-lookuptokenvalues-function) | External calls inside a loop in `lookupTokenValues` function |
| [QA-11](#qa-11-lack-of-event-for-failure-in-sendprice-function) | Lack of Event for Failure in sendPrice Function |
| [QA-12](#qa-12-settokentvllimit-function-name-and-event-name-are-somewhat-misleading) | `setTokenTvlLimit` function name and event name are somewhat misleading |
| [QA-13](#qa-13-lack-of-check-of-the-return-value) | Lack of check of the return value |
| [QA-14](#qa-14-external-calls-inside-the-calculatetvls-function) | External Calls inside the `calculateTVLs` function |
| [QA-15](#qa-15-ignored-return-value-in-restakemanager) | Ignored return value in RestakeManager |
| [QA-16](#qa-16-missing-zero-check-on-the-feeaddress-assignment-in-setfeeconfig-function) | Missing zero-check on the `feeAddress` assignment in `setFeeConfig` function |
| [QA-17](#qa-17-mix-up-in-comments) | Mix-up in comments |
| [QA-18](#qa-18-typos-multiple-instances) | Typos (Multiple Instances) |
| [QA-19](#qa-19-erc20-approvetransfer-call-is-not-safe) | ERC20 Approve/Transfer Call is Not Safe |
| [QA-20](#qa-20-the-nonreentrant-modifier-should-occur-before-all-other-modifiers) | The `nonReentrant` `modifier` should occur before all other modifiers |
| [QA-21](#qa-21-push0-is-not-supported-by-all-chains) | PUSH0 is not supported by all chains |
| [QA-22](#qa-22-large-literal-values-multiples-of-10000-can-be-replaced-with-scientific-notation) | Large literal values multiples of 10000 can be replaced with scientific notation |
| [QA-23](#qa-23-modifiers-invoked-only-once-can-be-shoe-horned-into-the-function) | Modifiers invoked only once can be shoe-horned into the function |
| [QA-24](#qa-24-event-is-missing-indexed-fields) | Event is missing `indexed` fields |










## [QA-01]   Hardcoded Gas Limit in CCIP Message Sending Leads to Potential Excess Gas Usage

### Impact
The hardcoded gas limit of 200,000 in the CCIP message sending function may lead to unnecessary gas consumption, especially when the message is sent to an externally owned account (EOA) that does not require complex computations or the execution of a `ccipReceive()` function. This can result in higher transaction costs and reduced efficiency in cross-chain communication.

>Borderline medium/low as this could cause loss a financial loss to the user.

### Proof of Concept
In the `sendPrice` function , the `gasLimit` is hardcoded within the `extraArgs` parameter for CCIP messages, as shown below:


https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L223-L225

```solidity
extraArgs: Client._argsToBytes(
    Client.EVMExtraArgsV1({ gasLimit: 200_000 })
),
```

This setting is used regardless of the nature of the destination address, which could be an EOA that does not necessitate such a high gas limit. The relevant part of the function is as follows:

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L218-L229

```solidity
for (uint256 i = 0; i < _destinationParam.length; ) {
    Client.EVM2AnyMessage memory evm2AnyMessage = Client.EVM2AnyMessage({
        receiver: abi.encode(_destinationParam[i]._renzoReceiver),
        data: _callData,
        tokenAmounts: new Client.EVMTokenAmount[](0),
        extraArgs: Client._argsToBytes(
            Client.EVMExtraArgsV1({ gasLimit: 200_000 })
        ),
        feeToken: address(linkToken)
    });

    // Sending logic...
}
```


This implementation does not account for scenarios where a lower gas limit could suffice, potentially leading to wasted gas and increased costs.

### Recommended Mitigation Steps:
- Adjust the `sendPrice` function to accept a `gasLimit` parameter or determine it dynamically based on the type of the receiver address. This allows for adjusting the gas limit based on actual needs rather than using a one-size-fits-all value.

For production code, it is recommended to adhere to the following best practices:
1. Avoid Hardcoding extraArgs: It is recommended to ensure that extraArgs is mutable. Implementing this flexibility allows for building extraArgs off-chain and passing it in function calls or storing it in a storage variable that can be updated as needed. By doing so, you maintain backward compatibility for potential future CCIP upgrades. 


Check more details here: https://docs.chain.link/ccip/getting-started







## [QA-02] Lack of Solvency Checks in `removeCollateralToken` Function

## Impact
The current implementation of the `removeCollateralToken` function in the `RestakeManager.sol` contract does not perform any checks related to the solvency or financial health of the system after removing a token. This could potentially lead to a situation where the removal of a token compromises the overall solvency or financial stability of the protocol, putting both current and future users at risk.

>Borderline medium/low

## Proof of Concept

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L244-L263

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

Scenario:
1. The protocol has multiple collateral tokens, including Token A and Token B.
2. Token A has a significant share of the total value locked (TVL) in the system.
3. An admin calls the `removeCollateralToken` function to remove Token A from the list of supported tokens.
4. The function successfully removes Token A without performing any solvency checks.
5. The removal of Token A leads to a situation where the system's liabilities exceed its remaining assets, compromising the solvency of the protocol.
6. Future depositors unknowingly bear higher risk or potentially cover losses that were exacerbated by the reduced asset base.

## Recommended Mitigation Steps:


1. Implement solvency checks in the `removeCollateralToken` function to ensure that the removal of a token does not compromise the financial stability of the protocol.

2. If the solvency checks fail, the function should revert the removal of the token and prevent the operation from proceeding.

3. Consider implementing a governance mechanism that allows stakeholders to vote on the removal of a collateral token, taking into account the potential impact on the system's solvency.

Here's an example of how the `removeCollateralToken` function could be modified to include solvency checks:

```diff
function removeCollateralToken(
    IERC20 _collateralTokenToRemove
) external onlyRestakeManagerAdmin {
    // Remove it from the list
    uint256 tokenLength = collateralTokens.length;
    for (uint256 i = 0; i < tokenLength; ) {
        if (address(collateralTokens[i]) == address(_collateralTokenToRemove)) {
+            // Temporarily remove the token
            collateralTokens[i] = collateralTokens[collateralTokens.length - 1];
            collateralTokens.pop();

+            // Check system solvency or other financial health metrics
+           if (!checkSystemHealth()) {
+               // Revert the removal if the system health is compromised
+                collateralTokens.push(collateralTokens[i]);
+                collateralTokens[i] = _collateralTokenToRemove;
+               revert SystemHealthCompromised();
+            }

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

With these mitigation steps, the protocol can ensure that the removal of a collateral token does not inadvertently compromise the financial stability and protect the interests of all participants.
















## [QA-03] Potential for LINK token approval overwriting in `sendPrice` function

If the `linkRouterClient` doesn't spend the entire approved amount or modifies the allowance internally, subsequent iterations of the loop in the `sendPrice` function might not have sufficient allowance to send the message. This could lead to failed message sending and unexpected behavior.

### Proof of Concept
The relevant code snippet is as follows:

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L231-L247

```solidity
// approve the Router to transfer LINK tokens on contract's behalf. It will spend the fees in LINK
linkToken.approve(address(linkRouterClient), fees);

// Send the message through the router and store the returned message ID
bytes32 messageId = linkRouterClient.ccipSend(
    _destinationParam[i].destinationChainSelector,
    evm2AnyMessage
);
```

In each iteration of the loop, the contract approves the `linkRouterClient` to spend the exact amount of `fees` in LINK tokens. However, if the `linkRouterClient` doesn't spend the entire approved amount or modifies the allowance internally, the subsequent iterations might not have sufficient allowance to send the message.

### Recommended Mitigation Steps:
1. Approve the maximum allowance for `linkRouterClient` before the loop:

```solidity
// Approve the maximum allowance for linkRouterClient
linkToken.approve(address(linkRouterClient), type(uint256).max);

for (uint256 i = 0; i < _destinationParam.length; ) {
    // ...
    // Remove the linkToken.approve call from inside the loop
    // ...
}
```

2. Check the current allowance and increase it if necessary:

```solidity
uint256 currentAllowance = linkToken.allowance(address(this), address(linkRouterClient));
if (currentAllowance < fees) {
    linkToken.approve(address(linkRouterClient), fees);
}
```

We recommend choosing the approach that aligns with the trust level in the `linkRouterClient` contract and the desired balance between gas efficiency and granular control over the allowance.






## [QA-04]  Unchecked LINK Token Approval in `sendPrice` Function

### Impact

>Borderline medium/low 

The `sendPrice` function approves the `linkRouterClient` to transfer the total `fees` amount of LINK tokens before sending the messages. If the message sending fails after the approval, the approved LINK tokens remain available for the `linkRouterClient` to spend, even though the messages were not sent successfully. This could lead to unauthorized spending of LINK tokens and potential loss of funds.

### Proof of Concept
Here's the relevant code snippet:

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L231-L247

```solidity
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
```

The code approves the `linkRouterClient` to spend the total `fees` amount of LINK tokens before calling `ccipSend` to send the messages. If the `ccipSend` call fails, the approved LINK tokens remain available for the `linkRouterClient` to spend.

### Recommended Mitigation Steps
To mitigate this issue, we recommend:

1. Move the LINK token approval after the `ccipSend` call to ensure that LINK tokens are approved only when the message is sent successfully.

2. Approve only the individual `fee` amount required for each message instead of the total `fees` amount.

Here's an example of how the code can be modified:

```diff
// Get the fee required to send the message
-            uint256 fees = linkRouterClient.getFee(
+           uint256 fee = linkRouterClient.getFee(
                _destinationParam[i].destinationChainSelector,
                evm2AnyMessage
            );

-           if (fees > linkToken.balanceOf(address(this)))
+           if (fee > linkToken.balanceOf(address(this)))
                revert NotEnoughBalance(linkToken.balanceOf(address(this)), fees);

-            // approve the Router to transfer LINK tokens on contract's behalf. It will spend the fees in LINK
-            linkToken.approve(address(linkRouterClient), fees);

-            // Send the message through the router and store the returned message ID
-            bytes32 messageId = linkRouterClient.ccipSend(
-                _destinationParam[i].destinationChainSelector,
-                evm2AnyMessage
-            );


+           // Send the message through the router and store the returned message ID
+          bytes32 messageId = linkRouterClient.ccipSend{value: fee}(
+           _destinationParam[i].destinationChainSelector,
+            evm2AnyMessage
+           );

+          // approve the Router to transfer LINK tokens on contract's behalf. It will spend the fee in LINK
+         linkToken.approve(address(linkRouterClient), fee);
```

By implementing these changes, the contract will approve LINK tokens only when the messages are sent successfully, mitigating the risk of unauthorized spending and potential loss of funds.











## [QA-05] `abi.encodePacked()` should not be used with dynamic types when passing the result to a hash function such as `keccak256()`

Use `abi.encode()` instead which will pad items to 32 bytes, which will [prevent hash collisions](https://docs.soliditylang.org/en/v0.8.13/abi-spec.html#non-standard-packed-mode) (e.g. `abi.encodePacked(0x123,0x456)` => `0x123456` => `abi.encodePacked(0x1,0x23456)`, but `abi.encode(0x123,0x456)` => `0x0...1230...456`). 

Unless there is a compelling reason, `abi.encode` should be preferred. If there is only one argument to `abi.encodePacked()` it can often be cast to `bytes()` or `bytes32()` [instead](https://ethereum.stackexchange.com/questions/30912/how-to-compare-strings-in-solidity#answer-82739).
If all arguments are strings and or bytes, `bytes.concat()` should be used instead.


## Here are the instances:

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L147-L148
	```solidity
	        bytes32 _salt = keccak256(abi.encodePacked(_name, _symbol, msg.sender));
	```


https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L158-L159
	```solidity
	        bytes memory _bytecode = abi.encodePacked(
	```


https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L201-L202
	```solidity
	        bytes memory _bytecode = abi.encodePacked(
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L89-L90
	```solidity
	        bytes32 _salt = keccak256(abi.encodePacked(_name, _symbol, msg.sender));
	```


https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L100-L101
	```solidity
	        bytes memory _bytecode = abi.encodePacked(
	```









## [QA-06] Incorrect `maxDepositTVL` value may prevent users from depositing funds

### Impact
If the `maxDepositTVL` value is set to a value lower than the current total value locked (TVL) in the protocol, users will be unable to deposit any more funds (either ERC20 tokens or ETH) until the TVL decreases below the `maxDepositTVL` threshold. This could lead to a situation where users' funds are temporarily stuck, preventing them from participating in the protocol.

### Proof of Concept
In the `deposit` function, there is a check to enforce a maximum TVL limit:

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L509-L512

```solidity
// Enforce TVL limit if set, 0 means the check is not enabled
if (maxDepositTVL != 0 && totalTVL + collateralTokenValue > maxDepositTVL) {
    revert MaxTVLReached();
}
```

Similarly, in the `depositETH` function, there is a similar check:
https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L596-L599

```solidity
// Enforce TVL limit if set
if (maxDepositTVL != 0 && totalTVL + msg.value > maxDepositTVL) {
    revert MaxTVLReached();
}
```

If the `maxDepositTVL` is set to a value that is lower than the current total value locked (TVL) in the protocol, these checks will cause the `deposit` and `depositETH` functions to revert, preventing users from depositing funds.

### Recommended Mitigation Steps:

Consider implementing a mechanism to automatically adjust the `maxDepositTVL` based on the protocol's growth rate













## [QA-07] Absence of timelock to critical functions


It is a good practice to give time for users to react and adjust to critical changes. A timelock provides more guarantees and reduces the level of trust required, thus decreasing risk for users. It also indicates that the project is legitimate (less risk of a malicious Manager making a frontrunning/sandwich attack on the fees).
Consider adding a timelock to the `setFeeConfig` function:

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L93-L109

```solidity
function setFeeConfig(
        address _feeAddress,
        uint256 _feeBasisPoints
    ) external onlyRestakeManagerAdmin {
        // Verify address is set if basis points are non-zero
        if (_feeBasisPoints > 0) {
            if (_feeAddress == address(0x0)) revert InvalidZeroInput();
        }

        // Verify basis points are not over 100%
        if (_feeBasisPoints > 10000) revert OverMaxBasisPoints();

        feeAddress = _feeAddress;
        feeBasisPoints = _feeBasisPoints;

        emit FeeConfigUpdated(_feeAddress, _feeBasisPoints);
    }
```








## [QA-08] Redundant usage of `safecast` 

The `SafeCast` library from OpenZeppelin is imported in the contract but it is not used anywhere in the code. The `SafeCast` library is indeed useful for safely casting between different numeric types to prevent overflows or underflows, but there are no such casting operations in the provided contract code.

Here is the import statement:

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L7-L8

```solidity
import { SafeCast } from "@openzeppelin/contracts/utils/math/SafeCast.sol";
```

And it is declared for use with:
https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L13-L14

```solidity
using SafeCast for uint256;
```

However, we reviewed the entire contract, there are no instances where `uint256` types are being cast to other types using `SafeCast`. All operations with `uint256` are straightforward assignments, parameter passing, or arithmetic operations that do not involve type casting.

If there is no future plan to include such type casting operations, you could safely remove the `SafeCast` import and its associated `using` declaration to clean up the code and reduce any unnecessary dependencies.

 







## [QA-09]  Logic Issue

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L244-L263

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
    
```
### Impact: Very low

The mild logic issue here is related to the loop's termination condition and the use of the `unchecked` block. The loop iterates through the `collateralTokens` array to find the token to remove. When it finds the token, it replaces it with the last token in the array and then removes the last element using `pop()`. This is a common technique to efficiently remove items from an array without preserving order.

Albeit, if the token to be removed is the last token in the array. In this case, the token is replaced with itself and then `pop()` is called. This does not cause a functional issue but is redundant and could be confusing. It's a minor inefficiency because it involves an unnecessary assignment.

### Suggested Improvement

To make the code cleaner and avoid unnecessary operations, you can add a check to see if the token to remove is already the last one in the array:

```diff
/// @dev Allows restake manager to remove a collateral token
function removeCollateralToken(
    IERC20 _collateralTokenToRemove
) external onlyRestakeManagerAdmin {
    // Remove it from the list
    uint256 tokenLength = collateralTokens.length;
    for (uint256 i = 0; i < tokenLength; ) {
        if (address(collateralTokens[i]) == address(_collateralTokenToRemove)) {
+            if (i != collateralTokens.length - 1) {
                collateralTokens[i] = collateralTokens[collateralTokens.length - 1];
+            }
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

This modification ensures that the unnecessary assignment is avoided when the token to be removed is already the last one in the array.


















## [QA-10] External calls inside a loop in `lookupTokenValues` function

The `lookupTokenValues` function makes external calls to `lookupTokenValue` inside a loop, which in turn makes external calls to Chainlink oracles. This pattern can lead to high gas costs and potential performance issues if the number of tokens is large.

### Proof of Concept
The `lookupTokenValues` function:
https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L103-L120

```solidity
function lookupTokenValues(
    IERC20[] memory _tokens,
    uint256[] memory _balances
) external view returns (uint256) {
    if (_tokens.length != _balances.length) revert MismatchedArrayLengths();

    uint256 totalValue = 0;
    uint256 tokenLength = _tokens.length;
    for (uint256 i = 0; i < tokenLength; ) {
        totalValue += lookupTokenValue(_tokens[i], _balances[i]);
        unchecked {
            ++i;
        }
    }

    return totalValue;
}
```

The `lookupTokenValue` function which is called in the loop:

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L71-L81

```solidity
function lookupTokenValue(IERC20 _token, uint256 _balance) public view returns (uint256) {
    AggregatorV3Interface oracle = tokenOracleLookup[_token];
    if (address(oracle) == address(0x0)) revert OracleNotFound();

    (, int256 price, , uint256 timestamp, ) = oracle.latestRoundData();
    if (timestamp < block.timestamp - MAX_TIME_WINDOW) revert OraclePriceExpired();
    if (price <= 0) revert InvalidOraclePrice();

    return (uint256(price) * _balance) / SCALE_FACTOR;
}
```

### Recommended Mitigation Steps:
- Limit the maximum number of tokens that can be passed into `lookupTokenValues`. This puts an upper bound on the gas cost.

- Consider caching oracle prices to avoid repeated external calls for the same token within a short timeframe. The trade-off is potentially using slightly stale prices.

- If the set of tokens is known in advance and relatively static, consider having a separate function to update all the prices in one transaction, and then `lookupTokenValues` can use the cached values without making external calls.





## [QA-11]  Lack of Event for Failure in sendPrice Function

### Impact
If sending the price feed fails in the sendPrice function, there is no event emitted or error thrown to indicate the failure. This makes it difficult to track and identify issues when the price feed sending fails. It can lead to silent failures and inconsistencies in the price feed data across different chains without any visible indication of the problem.

### Proof of Concept
The sendPrice function sends the price feed to multiple destination chains using CCIP and Connext. However, if any of these sending operations fail, there is no specific event emitted or error thrown to indicate the failure.

Here are the relevant code snippets:

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L217-L261

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L263-L286

```solidity
// send price feed to renzo CCIP receivers
for (uint256 i = 0; i < _destinationParam.length; ) {
    // ...
    bytes32 messageId = linkRouterClient.ccipSend(
        _destinationParam[i].destinationChainSelector,
        evm2AnyMessage
    );

    emit MessageSent(
        messageId,
        _destinationParam[i].destinationChainSelector,
        _destinationParam[i]._renzoReceiver,
        exchangeRate,
        address(linkToken),
        fees
    );
    // ...
}

// send price feed to renzo connext receiver
for (uint256 i = 0; i < _connextDestinationParam.length; ) {
    connext.xcall{ value: _connextDestinationParam[i].relayerFee }(
        // ...
    );

    emit ConnextMessageSent(
        _connextDestinationParam[i].destinationDomainId,
        _connextDestinationParam[i]._renzoReceiver,
        exchangeRate,
        _connextDestinationParam[i].relayerFee
    );
    // ...
}
```

In both loops, there are events emitted (MessageSent and ConnextMessageSent) when the price feed is sent successfully. However, there are no events emitted or errors thrown if the sending operations (ccipSend or xcall) fail.

### Recommended Mitigation Steps:
- Introduce error handling and event emission for failure cases in the sendPrice function.
- Wrap the ccipSend and xcall operations in a try-catch block to catch any potential exceptions.
- In the catch block, emit a new event (e.g., MessageSendFailed or ConnextMessageSendFailed) with relevant details such as the destination chain, receiver address, and error message.
- Consider throwing an exception or reverting the transaction if the failure is critical and should prevent further execution.






## [QA-12] `setTokenTvlLimit` function name and event name are somewhat misleading


The function name and event name do not accurately reflect the behavior of the function, which could lead to confusion and incorrect usage by developers or auditors.

The setTokenTvlLimit function sets the TVL limit for a specific collateral token in the collateralTokenTvlLimits mapping:

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L709-L719

```solidity
function setTokenTvlLimit(IERC20 _token, uint256 _limit) external onlyRestakeManagerAdmin {
    // Verify collateral token is in the list - call will revert if not found
    getCollateralTokenIndex(_token);

    // Set the limit
    collateralTokenTvlLimits[_token] = _limit;

    emit CollateralTokenTvlUpdated(_token, _limit);
}
```

However, the function name and event name suggest that it is setting an overall TVL limit for the protocol, rather than a limit for a specific collateral token.
 
### Recommendation: 

We recommend renaming the function to `setCollateralTokenTvlLimit` and update the event name to `CollateralTokenTvlLimitUpdated` to accurately reflect the behavior of the function:

```solidity
function setCollateralTokenTvlLimit(IERC20 _token, uint256 _limit) external onlyRestakeManagerAdmin {
    // Verify collateral token is in the list - call will revert if not found
    getCollateralTokenIndex(_token);

    // Set the limit
    collateralTokenTvlLimits[_token] = _limit;

    emit CollateralTokenTvlLimitUpdated(_token, _limit);
}
```

This will make it clear that the function is setting a TVL limit specifically for a collateral token, rather than an overall TVL limit for the protocol.











## [QA-13] Lack of check of the return value

The `sweepERC20` function ignores the return value of the `token.approve(address(restakeManager), balance - feeAmount)` call. Here's the relevant part of the code:

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L268
```solidity
token.approve(address(restakeManager), balance - feeAmount);
```

In Solidity, the `approve` function of ERC20 tokens is expected to return a boolean value indicating whether the approval was successful. However, in this code snippet, the return value is not checked or stored. This can potentially lead to issues if the `approve` call fails silently (i.e., it returns `false`), as the subsequent operations might assume that the approval was successful.

To improve the safety and reliability of this function, we recommended checking the return value of the `approve` call and handle the case where it returns `false`. Here's how the modification could be done to include this check:

```solidity
bool approvalSuccess = token.approve(address(restakeManager), balance - feeAmount);
if (!approvalSuccess) {
    revert ApprovalFailed();
}
```

This change ensures that the function will revert if the token approval fails, preventing any further actions that depend on this approval from being executed.












## [QA-14]  External Calls inside the `calculateTVLs` function 


The `calculateTVLs` function has external calls inside a loop. Specifically, the function makes external calls to `operatorDelegators[i].getTokenBalanceFromStrategy(collateralTokens[j])` and `renzoOracle.lookupTokenValue(collateralTokens[j], operatorBalance)` within nested loops iterating over operator delegators and collateral tokens. Here's the relevant part of the code:

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L289-L349



```solidity
for (uint256 i = 0; i < odLength; ) {
    uint256 operatorTVL = 0;
    uint256[] memory operatorValues = new uint256[](collateralTokens.length + 1);
    operatorDelegatorTokenTVLs[i] = operatorValues;

    uint256 tokenLength = collateralTokens.length;
    for (uint256 j = 0; j < tokenLength; ) {
        uint256 operatorBalance = operatorDelegators[i].getTokenBalanceFromStrategy(collateralTokens[j]);
        operatorValues[j] = renzoOracle.lookupTokenValue(collateralTokens[j], operatorBalance);
        operatorTVL += operatorValues[j];

        if (!withdrawQueueTokenBalanceRecorded) {
            totalWithdrawalQueueValue += renzoOracle.lookupTokenValue(
                collateralTokens[i],
                collateralTokens[j].balanceOf(withdrawQueue)
            );
        }

        unchecked {
            ++j;
        }
    }

    uint256 operatorEthBalance = operatorDelegators[i].getStakedETHBalance();
    operatorValues[operatorValues.length - 1] = operatorEthBalance;
    operatorTVL += operatorEthBalance;
    totalTVL += operatorTVL;
    operatorDelegatorTVLs[i] = operatorTVL;

    withdrawQueueTokenBalanceRecorded = true;

    unchecked {
        ++i;
    }
}
```

These external calls within loops can potentially lead to high gas costs, especially if the number of iterations is large. This pattern can also increase the risk of the contract being affected by external failures or changes in the state of the called contracts.








## [QA-15]  Ignored return value in RestakeManager

In the `depositTokenRewardsFromProtocol` function within the `RestakeManager.sol` contract, the return value of the `operatorDelegator.deposit(_token, _amount)` call is indeed ignored. Here's the relevant part of the function:

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L666-L668

```solidity
// Deposit the tokens into EigenLayer
operatorDelegator.deposit(_token, _amount);
```

This function call to `operatorDelegator.deposit(_token, _amount)` does not capture any return value, nor does it check for any state changes or conditions post-call that might depend on the outcome of the deposit operation. This could potentially lead to issues if the deposit operation fails silently (i.e., it does not revert but also does not perform as expected), as the contract would continue execution without handling such a case.

In Solidity, it's often important to handle return values or ensure that called functions revert on failure to prevent subtle bugs and ensure contract reliability. If the `deposit` function in the `IOperatorDelegator` interface is expected to return a value indicating success, or if its successful execution is critical, it would be prudent to modify the `depositTokenRewardsFromProtocol` function to handle this return value appropriately.


Also, the `deposit` function in the `RestakeManager` contract does not handle or check the return value of the `operatorDelegator.deposit(_collateralToken, _amount)` call. This function call is made to deposit the specified amount of a collateral token into the designated `OperatorDelegator`. Here's the relevant part of the code:


https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L562-L563

```solidity
// Call deposit on the operator delegator
operatorDelegator.deposit(_collateralToken, _amount);
```

This line indicates that the function is called, but no return value is captured or checked. This is common in Solidity when the called function does not return any value or when the return value is not needed for further processing. Albeit it's important to ensure that the `deposit` function in the `OperatorDelegator` contract is designed to handle errors internally (e.g., by using `revert` statements) to ensure that any issues during the deposit process are appropriately managed.






## [QA-16] Missing zero-check on the `feeAddress` assignment in `setFeeConfig` function 

Here's the relevant part of the code:

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L93-L110

```solidity
function setFeeConfig(
    address _feeAddress,
    uint256 _feeBasisPoints
) external onlyRestakeManagerAdmin {
    // Verify address is set if basis points are non-zero
    if (_feeBasisPoints > 0) {
        if (_feeAddress == address(0x0)) revert InvalidZeroInput();
    }

    // Verify basis points are not over 100%
    if (_feeBasisPoints > 10000) revert OverMaxBasisPoints();

    feeAddress = _feeAddress;
    feeBasisPoints = _feeBasisPoints;

    emit FeeConfigUpdated(_feeAddress, _feeBasisPoints);
}
```

The function checks if `_feeAddress` is zero only when `_feeBasisPoints` is greater than zero. However, it directly assigns `_feeAddress` to `feeAddress` without checking if it's zero when `_feeBasisPoints` is zero.

To fix this, we recommend adding a separate zero-check for `_feeAddress` before assigning it to `feeAddress`. Here's the updated code:

```solidity
function setFeeConfig(
    address _feeAddress,
    uint256 _feeBasisPoints
) external onlyRestakeManagerAdmin {
    // Verify address is set if basis points are non-zero
    if (_feeBasisPoints > 0) {
        if (_feeAddress == address(0x0)) revert InvalidZeroInput();
    }

    // Verify basis points are not over 100%
    if (_feeBasisPoints > 10000) revert OverMaxBasisPoints();

    // Verify fee address is not zero
    if (_feeAddress == address(0x0)) revert InvalidZeroInput();

    feeAddress = _feeAddress;
    feeBasisPoints = _feeBasisPoints;

    emit FeeConfigUpdated(_feeAddress, _feeBasisPoints);
}
```

By adding the separate zero-check for `_feeAddress`, you ensure that the `feeAddress` is not set to the zero address, regardless of the value of `_feeBasisPoints`.





## [QA-17] Mix-up in comments
The comments for the `unPause()` and `pause()` functions are swapped. 

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L117-L127

```solidity
function unPause() external onlyOwner {
        _unpause();
    }

    /**
     * @notice UnPause the contract
     * @dev This should be a permissioned call (onlyOwner)
     */
    function pause() external onlyOwner {
        _pause();
    }
```

The comment for `unPause()` should mention unpausing the contract, while the comment for `pause()` should mention pausing the contract. The code logic itself is correct, just the comments needed to be swapped to match the corresponding functions.









## [QA-18]  Typos _(Multiple Instances)

### Instance 1: 
 "inflationPercentaage" is misspelled. It should be "inflationPercentage" instead:

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L135-L136

```solidity
// Calculate the percentage of value after the deposit
uint256 inflationPercentaage = (SCALE_FACTOR * _newValueAdded) /
    (_currentValueInProtocol + _newValueAdded);
```

The correct spelling should be:

```solidity
// Calculate the percentage of value after the deposit
uint256 inflationPercentage = (SCALE_FACTOR * _newValueAdded) /
    (_currentValueInProtocol + _newValueAdded);
```


### Instance 2:
In the comments for several functions in several contracts, the word "onlyOwner" is misspelled as "onlyOnwer".

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L93-L94

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L104-L105

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L131-L132


https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L89-L90

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L100-L101

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L127-L128


They should be corrected `onlyOwner`

> This is just a typographical error in the comments and does not affect the functionality of the contracts, as the actual modifier used in the function definitions is correctly spelled as `onlyOwner`.



### Instance 3:

The word "maxmimum" should be corrected to "maximum". Here's the corrected comment:

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L12-L13

> Other than this minor typo in the comment, the contract code itself does not appear to have any typographical errors.



### Instance 4:

In the comment for the `isWithdrawQueueAdmin` function, "haas" should be "has":

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Permissions/RoleManager.sol#L96-L97

It should be corrected to:

```solidity
/// @dev Determine if the specified address has permission to update Withdraw Queue params
```

> This is just a comment typo and does not affect the functionality of the contract, but it's good practice to fix such typos for clarity and professionalism in the codebase.











## [QA-19] ERC20 Approve/Transfer Call is Not Safe

The `approve` function can be vulnerable to a specific attack, where a malicious actor can double spend tokens. This scenario occurs when the owner changes the approved allowance from N to M (N>0, M>0). The malicious spender can observe this change and quickly transfer the original N tokens before the change is mined, and then spend the additional M tokens afterwards. This could result in a total transfer of N+M tokens, which is not what the owner intended. More info you can see in this [link](https://docs.google.com/document/d/1YLPtQxZu1UAvO9cZ1O2RPXBbT0mooh4DYKjA_jp-RLM/edit#heading=h.m9fhqynw2xvt)

For this reason, it's recommended to use safeIncreaseAllowance() or safeDecreaseAllowance() for better control. If these methods are not available, using safeApprove() is also an option as it reverts if the current approval is not zero, providing an additional layer of security.


Also, ERC20 functions may not behave as expected. For example: return values are not always meaningful. It is recommended to use OpenZeppelin's SafeERC20 library. Use `safeTransfer` instead.

Here are the instances:

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L241
	```solidity
	            linkToken.approve(address(linkRouterClient), fees);
	```


https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L295
	```solidity
	        payable(_to).transfer(_amount);
	```


https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L479
	```solidity
	        payable(_to).transfer(_amount);
	```


https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L268
	```solidity
	            token.approve(address(restakeManager), balance - feeAmount);
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L303
	```solidity
	            payable(msg.sender).transfer(_withdrawRequest.amountToRedeem);
	```


https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L305
	```solidity
	            IERC20(_withdrawRequest.collateralToken).transfer(
	```







## [QA-20]  The `nonReentrant` `modifier` should occur before all other modifiers

This is a best-practice to protect against reentrancy in other modifiers.


### Instances: 

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L213

	```solidity
	    ) external payable onlyPriceFeedSender nonReentrant {
	```


https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L216
	```solidity
	    ) external onlyNativeEthRestakeAdmin nonReentrant {
	```


## [QA-21]  PUSH0 is not supported by all chains

Solc compiler version 0.8.20 switches the default target EVM version to Shanghai, which means that the generated bytecode will include PUSH0 opcodes. Be sure to select the appropriate EVM version in case you intend to deploy on a chain other than mainnet like L2 chains that may not support PUSH0, otherwise deployment of your contracts will fail.

Found in the following contracts:

- LockboxAdapterBlast.sol
- LibConnextStorage.sol 
- TokenId.sol
- XERC20.sol
- XERC20Factory.sol
- XERC20Lockbox.sol
- OptimismMintableXERC20.sol
- OptimismMintableXERC20Factory.sol
- XERC20Factory.sol 
- TimelockController.sol 
- EzEthToken.sol
- CCIPReceiver.sol








## [QA-22] Large literal values multiples of 10000 can be replaced with scientific notation

Use `e` notation, for example: `1e18`, instead of its full numeric value.


### Instances:

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L40-L41

	```solidity
	    uint32 public constant FEE_BASIS = 10000;
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L103-L104

	```solidity
	        if (_feeBasisPoints > 10000) revert OverMaxBasisPoints();
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L167

	```solidity
	            feeAmount = (msg.value * feeBasisPoints) / 10000;
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L261

	```solidity
	                feeAmount = (balance * feeBasisPoints) / 10000;





## [QA-23] Modifiers invoked only once can be shoe-horned into the function

### Instances:


https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L55

	```solidity
	    modifier onlyPriceFeedSender() {
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L43(contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L43)

	```solidity
	    modifier onlySource(address _originSender, uint32 _origin) {
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L62

	```solidity
	    modifier onlyERC20RewardsAdmin() {
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L29

	```solidity
	    modifier onlyOracleAdmin() {
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L77

	```solidity
	    modifier onlyDepositWithdrawPauserAdmin() {
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Rewards/RewardHandler.sol#L18

	```solidity
	    modifier onlyNativeEthRestakeAdmin() {
	```


https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Rewards/RewardHandler.sol#L24

	```solidity
	    modifier onlyRestakeManagerAdmin() {
	```


https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/token/EzEthToken.sol#L21

	```solidity
	    modifier onlyTokenAdmin() {
	```












## [QA-24] Event is missing `indexed` fields

Index event fields make the field more quickly accessible to off-chain tools that parse events. However, note that each index field costs extra gas during emission, so it's not necessarily best to index the maximum allowed per event (three fields). Each event should use three indexed fields if there are three or more fields, and gas usage is not particularly of concern for the events in question. If there are fewer than three fields, all of the fields should be indexed.

### Instances:

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L25

	```solidity
	    event EzETHMinted(
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L34

	```solidity
	    event MessageSent(
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L43

	```solidity
	    event ConnextMessageSent(
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L15

	```solidity
	    event OracleAddressUpdated(address newOracle, address oldOracle);
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L24

	```solidity
	    event XRenzoBridgeL1Updated(address newBridgeAddress, address oldBridgeAddress);
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L25

	```solidity
	    event CCIPEthChainSelectorUpdated(uint64 newSourceChainSelector, uint64 oldSourceChainSelector);
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L26

	```solidity
	    event XRenzoDepositUpdated(address newRenzoDeposit, address oldRenzoDeposit);
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L35

	```solidity
	    event MessageReceived(
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L23

	```solidity
	    event XRenzoBridgeL1Updated(address newBridgeAddress, address oldBridgeAddress);
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L24

	```solidity
	    event ConnextEthChainDomainUpdated(uint32 newSourceChainDomain, uint32 oldSourceChainDomain);
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L25

	```solidity
	    event XRenzoDepositUpdated(address newRenzoDeposit, address oldRenzoDeposit);
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L35

	```solidity
	    event MessageReceived(
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L42

	```solidity
	    event PriceUpdated(uint256 price, uint256 timestamp);
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L43

	```solidity
	    event Deposit(address indexed user, uint256 amountIn, uint256 amountOut);
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L44

	```solidity
	    event BridgeSweeperAddressUpdated(address sweeper, bool allowed);
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L45

	```solidity
	    event BridgeSwept(
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L51

	```solidity
	    event OraclePriceFeedUpdated(address newOracle, address oldOracle);
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L52

	```solidity
	    event ReceiverPriceFeedUpdated(address newReceiver, address oldReceiver);
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L53

	```solidity
	    event SweeperBridgeFeeCollected(address sweeper, uint256 feeCollected);
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L54

	```solidity
	    event BridgeFeeShareUpdated(uint256 oldBridgeFeeShare, uint256 newBridgeFeeShare);
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L55


	```solidity
	    event SweepBatchSizeUpdated(uint256 oldSweepBatchSize, uint256 newSweepBatchSize);
	```


https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L28

	```solidity
	    event TokenStrategyUpdated(IERC20 token, IStrategy strategy);
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L29

	```solidity
	    event DelegationAddressUpdated(address delegateAddress);
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L30

	```solidity
	    event RewardsForwarded(address rewardDestination, uint256 amount);
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L32

	```solidity
	    event WithdrawStarted(
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L43

	```solidity
	    event WithdrawCompleted(bytes32 withdrawalRoot, IStrategy[] strategies, uint256[] shares);
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L45

	```solidity
	    event GasSpent(address admin, uint256 gasSpent);
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L46

	```solidity
	    event GasRefunded(address admin, uint256 gasRefunded);
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L47

	```solidity
	    event BaseGasAmountSpentUpdated(uint256 oldBaseGasAmountSpent, uint256 newBaseGasAmountSpent);
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L15

	```solidity
	    event RewardsDeposited(IERC20 token, uint256 amount);
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L17

	```solidity
	    event FeeConfigUpdated(address feeAddress, uint256 feeBasisPoints);
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L19

	```solidity
	    event RestakeManagerUpdated(IRestakeManager restakeManager);
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L21

	```solidity
	    event ETHDepositedFromProtocol(uint256 amount);
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L23

	```solidity
	    event ETHStakedFromQueue(
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L30

	```solidity
	    event ProtocolFeesPaid(IERC20 token, uint256 amount, address destination);
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L32

	```solidity
	    event GasRefunded(address admin, uint256 gasRefunded);
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L35

	```solidity
	    event WithdrawQueueUpdated(address oldWithdrawQueue, address newWithdrawQueue);
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L38

	```solidity
	    event BufferFilled(address token, uint256 amount);
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L41

	```solidity
	    event FullWithdrawalETHReceived(uint256 amount);
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L35

	```solidity
	    event OracleAddressUpdated(IERC20 token, AggregatorV3Interface oracleAddress);
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L30

	```solidity
	    event OperatorDelegatorAdded(IOperatorDelegator od);
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L31

	```solidity
	    event OperatorDelegatorRemoved(IOperatorDelegator od);
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L32

	```solidity
	    event OperatorDelegatorAllocationUpdated(IOperatorDelegator od, uint256 allocation);
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L34

	```solidity
	    event CollateralTokenAdded(IERC20 token);
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L35

	```solidity
	    event CollateralTokenRemoved(IERC20 token);
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L41

	```solidity
	    event Deposit(
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L50

	```solidity
	    event UserWithdrawStarted(
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L59

	```solidity
	    event UserWithdrawCompleted(
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L68

	```solidity
	    event CollateralTokenTvlUpdated(IERC20 token, uint256 tvl);
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Rewards/RewardHandler.sol#L29

	```solidity
	    event RewardDestinationUpdated(address rewardDestination);
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L38

	```solidity
	    event CallScheduled(
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L51

	```solidity
	    event CallExecuted(
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L62

	```solidity
	    event CallSalt(bytes32 indexed id, bytes32 salt);
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L72

	```solidity
	    event MinDelayChange(uint256 oldDuration, uint256 newDuration);
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L19

	```solidity
	    event WithdrawBufferTargetUpdated(uint256 oldBufferTarget, uint256 newBufferTarget);
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L21

	```solidity
	    event CoolDownPeriodUpdated(uint256 oldCoolDownPeriod, uint256 newCoolDownPeriod);
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L23

	```solidity
	    event EthBufferFilled(uint256 amount);
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L25

	```solidity
	    event ERC20BufferFilled(address asset, uint256 amount);
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L27

	```solidity
	    event WithdrawRequestCreated(
	```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L36

	```solidity
	    event WithdrawRequestClaimed(WithdrawRequest withdrawRequest);
	```



