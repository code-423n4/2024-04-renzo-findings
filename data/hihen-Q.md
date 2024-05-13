# QA Report

Issues not included in the 4naly3er-report.

## Summary

### Low Issues

Total **132 instances** over **18 issues**:

|ID|Issue|Instances|
|:--:|:---|:--:|
| [[L-01]](#l-01-array-length-is-not-checked-before-access-its-index) | Array length is not checked before access its index | 6 |
| [[L-02]](#l-02-passing-abiencodepacked-with-dynamic-arguments-to-a-hash-can-cause-collisions) | Passing `abi.encodePacked()` with dynamic arguments to a hash can cause collisions | 2 |
| [[L-03]](#l-03-variables-shadowing-other-definitions) | Variables shadowing other definitions | 6 |
| [[L-04]](#l-04-missing-zero-address-check-in-constructor) | Missing zero address check in constructor | 2 |
| [[L-05]](#l-05-missing-zero-address-check-in-initializer) | Missing zero address check in initializer | 16 |
| [[L-06]](#l-06-revert-on-transfer-to-the-zero-address) | Revert on transfer to the zero address | 3 |
| [[L-07]](#l-07-state-variables-not-limited-to-reasonable-values) | State variables not limited to reasonable values | 5 |
| [[L-08]](#l-08-addresssend-should-be-replace-with-addresscall) | `address.send()` should be replace with address.call() | 1 |
| [[L-09]](#l-09-contracts-are-not-using-their-oz-upgradeable-counterparts) | Contracts are not using their OZ Upgradeable counterparts | 9 |
| [[L-10]](#l-10-vulnerable-versions-of-packages-are-being-used) | Vulnerable versions of packages are being used | 2 |
| [[L-11]](#l-11-constructor--initialization-function-lacks-parameter-validation) | Constructor / initialization function lacks parameter validation | 6 |
| [[L-12]](#l-12-unsafe-solidity-low-level-call-can-cause-gas-grief-attack) | Unsafe solidity low-level call can cause gas grief attack | 5 |
| [[L-13]](#l-13-minting-in-a-loop-may-lead-to-a-dos) | Minting in a loop may lead to a DOS | 2 |
| [[L-14]](#l-14-functions-calling-contractsaddresses-with-transfer-hooks-should-be-protected-by-reentrancy-guard) | Functions calling contracts/addresses with transfer hooks should be protected by reentrancy guard | 9 |
| [[L-15]](#l-15-critical-functions-should-be-controlled-by-time-locks) | Critical functions should be controlled by time locks | 26 |
| [[L-16]](#l-16-missing-contract-existence-checks-before-low-level-calls) | Missing contract existence checks before low-level calls | 1 |
| [[L-17]](#l-17-tokens-may-be-minted-to-the-zero-address) | Tokens may be minted to the zero address | 11 |
| [[L-18]](#l-18-code-does-not-follow-the-best-practice-of-check-effects-interaction) | Code does not follow the best practice of check-effects-interaction | 20 |

### Non Critical Issues

Total **1087 instances** over **73 issues**:

|ID|Issue|Instances|
|:--:|:---|:--:|
| [[N-01]](#n-01-abiencodepacked-should-be-replaced-with-bytesconcat) | `abi.encodePacked()` should be replaced with `bytes.concat()` | 3 |
| [[N-02]](#n-02-import-declarations-should-import-specific-identifiers-rather-than-the-whole-file) | Import declarations should import specific identifiers, rather than the whole file | 138 |
| [[N-03]](#n-03-visibility-of-state-variables-is-not-explicitly-defined) | Visibility of state variables is not explicitly defined | 6 |
| [[N-04]](#n-04-names-of-privateinternal-state-variables-should-be-prefixed-with-an-underscore) | Names of `private`/`internal` state variables should be prefixed with an underscore | 7 |
| [[N-05]](#n-05-the-nonreentrant-modifier-should-occur-before-all-other-modifiers) | The `nonReentrant` `modifier` should occur before all other modifiers | 2 |
| [[N-06]](#n-06-redundant-inheritance-specifier) | Redundant inheritance specifier | 13 |
| [[N-07]](#n-07-use-of-override-is-unnecessary) | Use of `override` is unnecessary | 12 |
| [[N-08]](#n-08-unused-structs) | Unused `struct`s | 2 |
| [[N-09]](#n-09-custom-errors-should-be-used-rather-than-revertrequire) | Custom errors should be used rather than `revert()`/`require()` | 12 |
| [[N-10]](#n-10-add-inline-comments-for-unnamed-parameters) | Add inline comments for unnamed parameters | 7 |
| [[N-11]](#n-11-consider-providing-a-ranged-getter-for-array-state-variables) | Consider providing a ranged getter for array state variables | 3 |
| [[N-12]](#n-12-consider-splitting-complex-checks-into-multiple-steps) | Consider splitting complex checks into multiple steps | 1 |
| [[N-13]](#n-13-consider-adding-a-blockdeny-list) | Consider adding a block/deny-list | 8 |
| [[N-14]](#n-14-constantsimmutables-redefined-elsewhere) | Constants/Immutables redefined elsewhere | 7 |
| [[N-15]](#n-15-contracts-should-each-be-defined-in-separate-files) | Contracts should each be defined in separate files | 6 |
| [[N-16]](#n-16-contract-name-does-not-match-its-filename) | Contract name does not match its filename | 10 |
| [[N-17]](#n-17-consider-using-accesscontroldefaultadminrules-rather-than-accesscontrol) | Consider using `AccessControlDefaultAdminRules` rather than `AccessControl` | 1 |
| [[N-18]](#n-18-upper_case-names-should-be-reserved-for-constantimmutable-variables) | UPPER_CASE names should be reserved for `constant`/`immutable` variables | 4 |
| [[N-19]](#n-19-consider-emitting-an-event-at-the-end-of-the-constructor) | Consider emitting an event at the end of the constructor | 22 |
| [[N-20]](#n-20-empty-function-body-without-comments) | Empty function body without comments | 3 |
| [[N-21]](#n-21-events-are-emitted-without-the-sender-information) | Events are emitted without the sender information | 16 |
| [[N-22]](#n-22-inconsistent-floating-version-pragma) | Inconsistent floating version pragma | 4 |
| [[N-23]](#n-23-function-state-mutability-can-be-restricted-to-pure) | Function state mutability can be restricted to pure | 5 |
| [[N-24]](#n-24-imports-could-be-organized-more-systematically) | Imports could be organized more systematically | 20 |
| [[N-25]](#n-25-there-is-no-need-to-initialize-bool-variables-with-false) | There is no need to initialize bool variables with `false` | 3 |
| [[N-26]](#n-26-interfaces-should-be-indicated-with-an-i-prefix-in-the-contract-name) | Interfaces should be indicated with an `I` prefix in the contract name | 1 |
| [[N-27]](#n-27-invalid-natspec-comment-style) | Invalid NatSpec comment style | 1 |
| [[N-28]](#n-28-openzeppelincontracts-should-be-upgraded-to-a-newer-version) | @openzeppelin/contracts should be upgraded to a newer version | 64 |
| [[N-29]](#n-29-lib-openzeppelincontracts-upgradeable-should-be-upgraded-to-a-newer-version) | Lib @openzeppelin/contracts-upgradeable should be upgraded to a newer version | 40 |
| [[N-30]](#n-30-expressions-for-constant-values-should-use-immutable-rather-than-constant) | Expressions for constant values should use `immutable` rather than `constant` | 15 |
| [[N-31]](#n-31-consider-moving-duplicated-strings-to-constants) | Consider moving duplicated strings to constants | 10 |
| [[N-32]](#n-32-contracts-containing-only-utility-functions-should-be-made-into-libraries) | Contracts containing only utility functions should be made into libraries | 3 |
| [[N-33]](#n-33-error-names-should-use-capwords-style) | Error names should use CapWords style | 1 |
| [[N-34]](#n-34-contract-name-does-not-follow-the-solidity-style-guide) | Contract name does not follow the Solidity Style Guide | 6 |
| [[N-35]](#n-35-functions-should-be-named-in-mixedcase-style) | Functions should be named in mixedCase style | 9 |
| [[N-36]](#n-36-variable-names-for-immutables-should-use-upper_case_with_underscores) | Variable names for `immutable`s should use UPPER_CASE_WITH_UNDERSCORES | 2 |
| [[N-37]](#n-37-named-imports-of-parent-contracts-are-missing) | Named imports of parent contracts are missing | 59 |
| [[N-38]](#n-38-constants-should-be-put-on-the-left-side-of-comparisons) | Constants should be put on the left side of comparisons | 86 |
| [[N-39]](#n-39-else-block-not-required) | `else`-block not required | 4 |
| [[N-40]](#n-40-large-multiples-of-ten-should-use-scientific-notation) | Large multiples of ten should use scientific notation | 6 |
| [[N-41]](#n-41-high-cyclomatic-complexity) | High cyclomatic complexity | 1 |
| [[N-42]](#n-42-typos) | Typos | 19 |
| [[N-43]](#n-43-consider-bounding-input-array-length) | Consider bounding input array length | 18 |
| [[N-44]](#n-44-unnecessary-casting) | Unnecessary casting | 8 |
| [[N-45]](#n-45-unused-contract-variables) | Unused contract variables | 1 |
| [[N-46]](#n-46-unused-import) | Unused import | 25 |
| [[N-47]](#n-47-unused-modifiers) | Unused modifiers | 1 |
| [[N-48]](#n-48-unused-named-return) | Unused named return | 22 |
| [[N-49]](#n-49-use-delete-instead-of-assigning-values-to-false) | Use delete instead of assigning values to `false` | 1 |
| [[N-50]](#n-50-consider-using-delete-rather-than-assigning-zero-to-clear-values) | Consider using `delete` rather than assigning zero to clear values | 2 |
| [[N-51]](#n-51-use-the-latest-solidity-version) | Use the latest Solidity version | 38 |
| [[N-52]](#n-52-use-transfer-libraries-instead-of-low-level-calls-to-transfer-native-tokens) | Use transfer libraries instead of low level calls to transfer native tokens | 6 |
| [[N-53]](#n-53-use-a-struct-to-encapsulate-multiple-function-parameters) | Use a struct to encapsulate multiple function parameters | 9 |
| [[N-54]](#n-54-returning-a-struct-instead-of-a-bunch-of-variables-is-better) | Returning a struct instead of a bunch of variables is better | 7 |
| [[N-55]](#n-55-events-that-mark-critical-parameter-changes-should-contain-both-the-old-and-the-new-value) | Events that mark critical parameter changes should contain both the old and the new value | 10 |
| [[N-56]](#n-56-contract-variables-should-have-comments) | Contract variables should have comments | 4 |
| [[N-57]](#n-57-missing-event-when-a-state-variables-is-set-in-constructor) | Missing event when a state variables is set in constructor | 6 |
| [[N-58]](#n-58-empty-bytes-check-is-missing) | Empty bytes check is missing | 10 |
| [[N-59]](#n-59-dont-define-functions-with-the-same-name-in-a-contract) | Don't define functions with the same name in a contract | 2 |
| [[N-60]](#n-60-interface-files-should-not-use-fixed-compiler-versions) | Interface files should not use fixed compiler versions | 1 |
| [[N-61]](#n-61-multiple-mappings-with-same-keys-can-be-combined-into-a-single-struct-mapping-for-readability) | Multiple mappings with same keys can be combined into a single struct mapping for readability | 3 |
| [[N-62]](#n-62-missing-event-for-critical-changes) | Missing event for critical changes | 3 |
| [[N-63]](#n-63-duplicated-requirerevert-checks-should-be-refactored) | Duplicated `require()`/`revert()` checks should be refactored | 22 |
| [[N-64]](#n-64-consider-adding-emergency-stop-functionality) | Consider adding emergency-stop functionality | 12 |
| [[N-65]](#n-65-avoid-the-use-of-sensitive-terms) | Avoid the use of sensitive terms | 25 |
| [[N-66]](#n-66-missing-checks-for-uint-state-variable-assignments) | Missing checks for uint state variable assignments | 9 |
| [[N-67]](#n-67-use-the-modern-upgradeable-contract-paradigm) | Use the Modern Upgradeable Contract Paradigm | 8 |
| [[N-68]](#n-68-large-or-complicated-code-bases-should-implement-invariant-tests) | Large or complicated code bases should implement invariant tests | 1 |
| [[N-69]](#n-69-the-default-value-is-manually-set-when-it-is-declared) | The default value is manually set when it is declared | 37 |
| [[N-70]](#n-70-contracts-should-have-all-publicexternal-functions-exposed-by-interfaces) | Contracts should have all `public`/`external` functions exposed by `interface`s | 23 |
| [[N-71]](#n-71-top-level-declarations-should-be-separated-by-at-least-two-lines) | Top-level declarations should be separated by at least two lines | 89 |
| [[N-72]](#n-72-consider-adding-formal-verification-proofs) | Consider adding formal verification proofs | 40 |
| [[N-73]](#n-73-numeric-values-having-to-do-with-time-should-use-time-units-for-readability) | Numeric values having to do with time should use time units for readability | 2 |

## Low Issues

### [L-01] Array length is not checked before access its index

Accessing the elements of the array without checking or ensuring the validity of the access index in advance. It may result in an unexpected out-of-bounds error, or may result in missing elements when trying to traverse the entire array.

There are 6 instances:

- *RestakeManager.sol* ( [410-410](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L410-L410), [410-410](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L410-L410), [424-424](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L424-L424), [424-424](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L424-L424), [436-436](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L436-L436), [436-436](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L436-L436) ):

```solidity
410:             if (operatorDelegatorTokenTVLs[0][tokenIndex] < ezETHValue) {

410:             if (operatorDelegatorTokenTVLs[0][tokenIndex] < ezETHValue) {

424:                 operatorDelegatorTokenTVLs[i][tokenIndex] >= ezETHValue

424:                 operatorDelegatorTokenTVLs[i][tokenIndex] >= ezETHValue

436:             if (operatorDelegatorTokenTVLs[i][tokenIndex] >= ezETHValue) {

436:             if (operatorDelegatorTokenTVLs[i][tokenIndex] >= ezETHValue) {
```

### [L-02] Passing `abi.encodePacked()` with dynamic arguments to a hash can cause collisions

Using `abi.encodePacked` can cause hash collisions when used with **multiple dynamic arguments**. It is recommended to use `abi.encode()` instead which will pad items to 32 bytes and [prevent hash collisions](https://docs.soliditylang.org/en/v0.8.20/abi-spec.html#non-standard-packed-mode).

There are 2 instances:

- *XERC20Factory.sol* ( [147-147](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L147-L147) ):

```solidity
147:         bytes32 _salt = keccak256(abi.encodePacked(_name, _symbol, msg.sender));
```

- *OptimismMintableXERC20Factory.sol* ( [89-89](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L89-L89) ):

```solidity
89:         bytes32 _salt = keccak256(abi.encodePacked(_name, _symbol, msg.sender));
```

### [L-03] Variables shadowing other definitions

A variable declaration shadowing any other existing definition is error-prone. It can cause confusion for developers, potentially introduce bugs, and reduce the readability and maintainability.

There are 6 instances:

- *XERC20.sol* ( [62-62](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20.sol#L62-L62), [63-63](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20.sol#L63-L63), [77-77](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20.sol#L77-L77), [78-78](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20.sol#L78-L78) ):

```solidity
/// @audit Shadows `state variable _name`
62:         string memory _name,

/// @audit Shadows `state variable _symbol`
63:         string memory _symbol,

/// @audit Shadows `state variable _name`
77:         string memory _name,

/// @audit Shadows `state variable _symbol`
78:         string memory _symbol,
```

- *OptimismMintableXERC20.sol* ( [36-36](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L36-L36), [37-37](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L37-L37) ):

```solidity
/// @audit Shadows `state variable _name`
36:         string memory _name,

/// @audit Shadows `state variable _symbol`
37:         string memory _symbol,
```

### [L-04] Missing zero address check in constructor

Constructors often take address parameters to initialize important components of a contract, such as owner or linked contracts. However, without a checking, there's a risk that an address parameter could be mistakenly set to the zero address (0x0). This could be due to an error or oversight during contract deployment. A zero address in a crucial role can cause serious issues, as it cannot perform actions like a normal address, and any funds sent to it will be irretrievable. It's therefore crucial to include a zero address check in constructors to prevent such potential problems. If a zero address is detected, the constructor should revert the transaction.

There are 2 instances:

- *TimelockController.sol* ( [87-92](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L87-L92) ):

```solidity
/// @audit `proposers not checked`
/// @audit `executors not checked`
87:     constructor(
88:         uint256 minDelay,
89:         address[] memory proposers,
90:         address[] memory executors,
91:         address admin
92:     ) {
```

### [L-05] Missing zero address check in initializer

Consider adding a zero address check for each address type parameter in initializer.

<details>
<summary>There are 16 instances (click to show):</summary>

- *xRenzoDeposit.sol* ( [75-86](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L75-L86) ):

```solidity
/// @audit `_receiver not checked`
/// @audit `_oracle not checked`
75:     function initialize(
76:         uint256 _currentPrice,
77:         IERC20 _xezETH,
78:         IERC20 _depositToken,
79:         IERC20 _collateralToken,
80:         IConnext _connext,
81:         bytes32 _swapKey,
82:         address _receiver,
83:         uint32 _bridgeDestinationDomain,
84:         address _bridgeTargetAddress,
85:         IRenzoOracleL2 _oracle
86:     ) public initializer {
```

- *XERC20.sol* ( [61-65](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20.sol#L61-L65) ):

```solidity
/// @audit `_factory not checked`
61:     function initialize(
62:         string memory _name,
63:         string memory _symbol,
64:         address _factory
65:     ) public initializer {
```

- *XERC20Factory.sol* ( [54-57](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L54-L57) ):

```solidity
/// @audit `_lockboxImplementation not checked`
/// @audit `_xerc20Implementation not checked`
54:     function initialize(
55:         address _lockboxImplementation,
56:         address _xerc20Implementation
57:     ) public initializer {
```

- *XERC20Lockbox.sol* ( [44-44](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L44-L44) ):

```solidity
/// @audit `_xerc20 not checked`
/// @audit `_erc20 not checked`
44:     function initialize(address _xerc20, address _erc20, bool _isNative) public initializer {
```

- *OptimismMintableXERC20.sol* ( [35-41](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L35-L41) ):

```solidity
/// @audit `_factory not checked`
/// @audit `_l1Token not checked`
/// @audit `_optimismBridge not checked`
35:     function initialize(
36:         string memory _name,
37:         string memory _symbol,
38:         address _factory,
39:         address _l1Token,
40:         address _optimismBridge
41:     ) public initializer {
```

- *RestakeManager.sol* ( [101-108](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L101-L108) ):

```solidity
/// @audit `_roleManager not checked`
/// @audit `_ezETH not checked`
/// @audit `_renzoOracle not checked`
/// @audit `_strategyManager not checked`
/// @audit `_delegationManager not checked`
/// @audit `_depositQueue not checked`
101:     function initialize(
102:         IRoleManager _roleManager,
103:         IEzEthToken _ezETH,
104:         IRenzoOracle _renzoOracle,
105:         IStrategyManager _strategyManager,
106:         IDelegationManager _delegationManager,
107:         IDepositQueue _depositQueue
108:     ) public initializer {
```

</details>

### [L-06] Revert on transfer to the zero address

It's good practice to revert a token transfer transaction if the recipient's address is the zero address. This can prevent unintentional transfers to the zero address due to accidental operations or programming errors. Many token contracts implement such a safeguard, such as [OpenZeppelin - ERC20](https://github.com/OpenZeppelin/openzeppelin-contracts/blob/9e3f4d60c581010c4a3979480e07cc7752f124cc/contracts/token/ERC20/ERC20.sol#L232), [OpenZeppelin - ERC721](https://github.com/OpenZeppelin/openzeppelin-contracts/blob/9e3f4d60c581010c4a3979480e07cc7752f124cc/contracts/token/ERC721/ERC721.sol#L142).

There are 3 instances:

- *xRenzoBridge.sol* ( [306-306](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L306-L306) ):

```solidity
306:         IERC20(_token).safeTransfer(_to, _amount);
```

- *xRenzoDeposit.sol* ( [490-490](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L490-L490) ):

```solidity
490:         IERC20(_token).safeTransfer(_to, _amount);
```

- *XERC20Lockbox.sol* ( [134-134](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L134-L134) ):

```solidity
134:             ERC20.safeTransfer(_to, _amount);
```

### [L-07] State variables not limited to reasonable values

Consider adding appropriate minimum/maximum value checks to ensure that the following state variables can never be used to excessively harm users, including via griefing.

There are 5 instances:

- *RestakeManager.sol* ( [216-216](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L216-L216), [714-714](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L714-L714) ):

```solidity
216:         maxDepositTVL = _maxDepositTVL;

714:         collateralTokenTvlLimits[_token] = _limit;
```

- *TimelockController.sol* ( [405-405](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L405-L405) ):

```solidity
405:         _minDelay = newDelay;
```

- *WithdrawQueue.sol* ( [87-87](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L87-L87), [132-132](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L132-L132) ):

```solidity
87:         coolDownPeriod = _coolDownPeriod;

132:         coolDownPeriod = _newCoolDownPeriod;
```

### [L-08] `address.send()` should be replace with address.call()

The `<address payable>.send()` will forward 2300 gas stipend, not adjustable. The limited gas makes it more likely to fail. It is recommended to use `address.call{value: amount}()` instead, like [Address.sendValue()](https://github.com/OpenZeppelin/openzeppelin-contracts/blob/90163661df4f7df22294fcbf82dd3f6bb5547417/contracts/utils/Address.sol#L41)

There is 1 instance:

- *OperatorDelegator.sol* ( [485](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L485) ):

```solidity
485:         bool success = payable(tx.origin).send(gasRefund);
```

### [L-09] Contracts are not using their OZ Upgradeable counterparts

The non-upgradeable standard version of OpenZeppelin’s library are inherited / used by the contracts. It would be safer to use the upgradeable versions of the library contracts to avoid unexpected behavior.
Where applicable, use the contracts from `@openzeppelin/contracts-upgradeable` instead of `@openzeppelin/contracts`. See [this](https://github.com/OpenZeppelin/openzeppelin-contracts-upgradeable/tree/master/contracts) for list of available upgradeable contracts

<details>
<summary>There are 9 instances (click to show):</summary>

- *XERC20Factory.sol* ( [12](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L12) ):

```solidity
12: import "@openzeppelin/contracts/proxy/transparent/TransparentUpgradeableProxy.sol";
```

- *OptimismMintableXERC20Factory.sol* ( [12](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L12) ):

```solidity
12: import "@openzeppelin/contracts/proxy/transparent/TransparentUpgradeableProxy.sol";
```

- *OperatorDelegator.sol* ( [4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L4) ):

```solidity
4: import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";
```

- *DepositQueue.sol* ( [5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L5) ):

```solidity
5: import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";
```

- *RestakeManager.sol* ( [4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L4), [9](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L9), [10](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L10) ):

```solidity
4: import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";

9: import "@openzeppelin/contracts/token/ERC20/IERC20.sol";

10: import "@openzeppelin/contracts/token/ERC20/extensions/IERC20Metadata.sol";
```

- *WithdrawQueue.sol* ( [6](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L6), [9](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L9) ):

```solidity
6: import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";

9: import "@openzeppelin/contracts/token/ERC20/IERC20.sol";
```

</details>

### [L-10] Vulnerable versions of packages are being used

This project is using specific package versions which are vulnerable to the specific CVEs listed below. Consider switching to more recent versions of these packages that don't have these vulnerabilities.
- [CVE-2023-49798](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2023-49798) - **HIGH** - (`@openzeppelin/contracts 4.9.4`): OpenZeppelin Contracts is a library for smart contract development. A merge issue when porting the 5.0.1 patch to the 4.9 branch caused a line duplication. In the version of `Multicall.sol` released in `@openzeppelin/contracts@4.9.4` and `@openzeppelin/contracts-upgradeable@4.9.4`, all subcalls are executed twice. Concretely, this exposes a user to unintentionally duplicate operations like asset transfers. The duplicated delegatecall was removed in version 4.9.5. The 4.9.4 version is marked as deprecated. Users are advised to upgrade. There are no known workarounds for this issue.

- [CVE-2023-49798](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2023-49798) - **HIGH** - (`@openzeppelin/contracts-upgradeable 4.9.4`): OpenZeppelin Contracts is a library for smart contract development. A merge issue when porting the 5.0.1 patch to the 4.9 branch caused a line duplication. In the version of `Multicall.sol` released in `@openzeppelin/contracts@4.9.4` and `@openzeppelin/contracts-upgradeable@4.9.4`, all subcalls are executed twice. Concretely, this exposes a user to unintentionally duplicate operations like asset transfers. The duplicated delegatecall was removed in version 4.9.5. The 4.9.4 version is marked as deprecated. Users are advised to upgrade. There are no known workarounds for this issue.

There are 2 instances:

- Global finding

### [L-11] Constructor / initialization function lacks parameter validation

Constructors and initialization functions play a critical role in contracts by setting important initial states when the contract is first deployed before the system starts. The parameters passed to the constructor and initialization functions directly affect the behavior of the contract / protocol. If incorrect parameters are provided, the system may fail to run, behave abnormally, be unstable, or lack security. Therefore, it's crucial to carefully check each parameter in the constructor and initialization functions. If an exception is found, the transaction should be rolled back.

<details>
<summary>There are 6 instances (click to show):</summary>

- *XERC20.sol* ( [61-65](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20.sol#L61-L65) ):

```solidity
/// @audit `_name`
/// @audit `_symbol`
61:     function initialize(
62:         string memory _name,
63:         string memory _symbol,
64:         address _factory
65:     ) public initializer {
```

- *XERC20Lockbox.sol* ( [44-44](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L44-L44) ):

```solidity
/// @audit `_isNative`
44:     function initialize(address _xerc20, address _erc20, bool _isNative) public initializer {
```

- *OptimismMintableXERC20.sol* ( [35-41](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L35-L41) ):

```solidity
/// @audit `_name`
/// @audit `_symbol`
35:     function initialize(
36:         string memory _name,
37:         string memory _symbol,
38:         address _factory,
39:         address _l1Token,
40:         address _optimismBridge
41:     ) public initializer {
```

- *TimelockController.sol* ( [87-92](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L87-L92) ):

```solidity
/// @audit `minDelay`
87:     constructor(
88:         uint256 minDelay,
89:         address[] memory proposers,
90:         address[] memory executors,
91:         address admin
92:     ) {
```

</details>

### [L-12] Unsafe solidity low-level call can cause gas grief attack

Using the low-level calls of a solidity address can leave the contract open to gas grief attacks. These attacks occur when the called contract returns a large amount of data.
So when calling an external contract, it is necessary to check the length of the return data before reading/copying it (using `returndatasize()`).

There are 5 instances:

- *XERC20Lockbox.sol* ( [131-131](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L131-L131) ):

```solidity
131:             (bool _success, ) = payable(_to).call{ value: _amount }("");
```

- *OperatorDelegator.sol* ( [520-520](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L520-L520) ):

```solidity
520:             (bool success, ) = destination.call{ value: remainingAmount }("");
```

- *DepositQueue.sol* ( [168-168](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L168-L168) ):

```solidity
168:             (bool success, ) = feeAddress.call{ value: feeAmount }("");
```

- *RewardHandler.sol* ( [68-68](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Rewards/RewardHandler.sol#L68-L68) ):

```solidity
68:         (bool success, ) = rewardDestination.call{ value: balance }("");
```

- *TimelockController.sol* ( [369-369](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L369-L369) ):

```solidity
369:         (bool success, ) = target.call{ value: value }(data);
```

### [L-13] Minting in a loop may lead to a DOS

The signature used seems to require all the minting operations to be done at once. If there are a lot of them, there may be too many to mint in one block.

There are 2 instances:

- *XERC20Factory.sol* ( [167-169](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L167-L169) ):

```solidity
/// @audit mint by setLimits()
167:         for (uint256 _i; _i < _bridgesLength; ++_i) {
168:             XERC20(_xerc20).setLimits(_bridges[_i], _minterLimits[_i], _burnerLimits[_i]);
169:         }
```

- *OptimismMintableXERC20Factory.sol* ( [109-115](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L109-L115) ):

```solidity
/// @audit mint by setLimits()
109:         for (uint256 _i; _i < _bridgesLength; ++_i) {
110:             OptimismMintableXERC20(_xerc20).setLimits(
111:                 _bridges[_i],
112:                 _minterLimits[_i],
113:                 _burnerLimits[_i]
114:             );
115:         }
```

### [L-14] Functions calling contracts/addresses with transfer hooks should be protected by reentrancy guard

Even if the function follows the best practice of check-effects-interaction, not using a reentrancy guard when there may be transfer hooks opens the users of this protocol up to [read-only reentrancy vulnerability](https://chainsecurity.com/curve-lp-oracle-manipulation-post-mortem/) with no way to protect them except by block-listing the entire protocol.

<details>
<summary>There are 9 instances (click to show):</summary>

- *LockboxAdapterBlast.sol* ( [83-83](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L83-L83) ):

```solidity
83:         SafeERC20.safeTransferFrom(IERC20(_erc20), msg.sender, address(this), _amount);
```

- *xRenzoBridge.sol* ( [295-295](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L295-L295), [306-306](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L306-L306) ):

```solidity
295:         payable(_to).transfer(_amount);

306:         IERC20(_token).safeTransfer(_to, _amount);
```

- *xRenzoDeposit.sol* ( [479-479](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L479-L479), [490-490](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L490-L490) ):

```solidity
479:         payable(_to).transfer(_amount);

490:         IERC20(_token).safeTransfer(_to, _amount);
```

- *XERC20Lockbox.sol* ( [134-134](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L134-L134), [147-147](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L147-L147) ):

```solidity
134:             ERC20.safeTransfer(_to, _amount);

147:             ERC20.safeTransferFrom(msg.sender, address(this), _amount);
```

- *DepositQueue.sol* ( [262-262](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L262-L262) ):

```solidity
262:                 IERC20(token).safeTransfer(feeAddress, feeAmount);
```

- *RestakeManager.sol* ( [661-661](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L661-L661) ):

```solidity
661:         _token.safeTransferFrom(msg.sender, address(this), _amount);
```

</details>

### [L-15] Critical functions should be controlled by time locks

It is a good practice to give time for users to react and adjust to critical changes. A timelock provides more guarantees and reduces the level of trust required, thus decreasing risk for users. It also indicates that the project is legitimate (less risk of a malicious owner making a sandwich attack on a user).

<details>
<summary>There are 26 instances (click to show):</summary>

- *RenzoOracleL2.sol* ( [36-36](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L36-L36) ):

```solidity
36:     function setOracleAddress(AggregatorV3Interface _oracleAddress) external onlyOwner {
```

- *CCIPReceiver.sol* ( [96-96](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L96-L96), [134-134](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L134-L134) ):

```solidity
96:     function updateXRenzoBridgeL1(address _newXRenzoBridgeL1) external onlyOwner {

134:     function setRenzoDeposit(address _newXRenzoDeposit) external onlyOwner {
```

- *ConnextReceiver.sol* ( [92-92](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L92-L92), [130-130](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L130-L130) ):

```solidity
92:     function updateXRenzoBridgeL1(address _newXRenzoBridgeL1) external onlyOwner {

130:     function setRenzoDeposit(address _newXRenzoDeposit) external onlyOwner {
```

- *xRenzoDeposit.sol* ( [466-466](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L466-L466), [501-501](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L501-L501), [511-511](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L511-L511) ):

```solidity
466:     function setAllowedBridgeSweeper(address _sweeper, bool _allowed) external onlyOwner {

501:     function setOraclePriceFeed(IRenzoOracleL2 _oracle) external onlyOwner {

511:     function setReceiverPriceFeed(address _receiver) external onlyOwner {
```

- *XERC20.sol* ( [135-139](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20.sol#L135-L139) ):

```solidity
135:     function setLimits(
136:         address _bridge,
137:         uint256 _mintingLimit,
138:         uint256 _burningLimit
139:     ) external onlyOwner {
```

- *OperatorDelegator.sol* ( [106-109](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L106-L109), [117-121](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L117-L121) ):

```solidity
106:     function setTokenStrategy(
107:         IERC20 _token,
108:         IStrategy _strategy
109:     ) external nonReentrant onlyOperatorDelegatorAdmin {

117:     function setDelegateAddress(
118:         address _delegateAddress,
119:         ISignatureUtils.SignatureWithExpiry memory approverSignatureAndExpiry,
120:         bytes32 approverSalt
121:     ) external nonReentrant onlyOperatorDelegatorAdmin {
```

- *DepositQueue.sol* ( [87-87](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L87-L87), [93-96](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L93-L96), [112-112](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L112-L112) ):

```solidity
87:     function setWithdrawQueue(IWithdrawQueue _withdrawQueue) external onlyRestakeManagerAdmin {

93:     function setFeeConfig(
94:         address _feeAddress,
95:         uint256 _feeBasisPoints
96:     ) external onlyRestakeManagerAdmin {

112:     function setRestakeManager(IRestakeManager _restakeManager) external onlyRestakeManagerAdmin {
```

- *RenzoOracle.sol* ( [54-57](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L54-L57) ):

```solidity
54:     function setOracleAddress(
55:         IERC20 _token,
56:         AggregatorV3Interface _oracleAddress
57:     ) external nonReentrant onlyOracleAdmin {
```

- *RestakeManager.sol* ( [131-134](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L131-L134), [160-162](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L160-L162), [187-190](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L187-L190), [220-220](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L220-L220), [244-246](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L244-L246), [709-709](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L709-L709) ):

```solidity
131:     function addOperatorDelegator(
132:         IOperatorDelegator _newOperatorDelegator,
133:         uint256 _allocationBasisPoints
134:     ) external onlyRestakeManagerAdmin {

160:     function removeOperatorDelegator(
161:         IOperatorDelegator _operatorDelegatorToRemove
162:     ) external onlyRestakeManagerAdmin {

187:     function setOperatorDelegatorAllocation(
188:         IOperatorDelegator _operatorDelegator,
189:         uint256 _allocationBasisPoints
190:     ) external onlyRestakeManagerAdmin {

220:     function addCollateralToken(IERC20 _newCollateralToken) external onlyRestakeManagerAdmin {

244:     function removeCollateralToken(
245:         IERC20 _collateralTokenToRemove
246:     ) external onlyRestakeManagerAdmin {

709:     function setTokenTvlLimit(IERC20 _token, uint256 _limit) external onlyRestakeManagerAdmin {
```

- *RewardHandler.sol* ( [72-74](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Rewards/RewardHandler.sol#L72-L74) ):

```solidity
72:     function setRewardDestination(
73:         address _rewardDestination
74:     ) external nonReentrant onlyRestakeManagerAdmin {
```

- *WithdrawQueue.sol* ( [106-108](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L106-L108), [129-129](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L129-L129), [139-139](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L139-L139) ):

```solidity
106:     function updateWithdrawBufferTarget(
107:         TokenWithdrawBuffer[] calldata _newBufferTarget
108:     ) external onlyWithdrawQueueAdmin {

129:     function updateCoolDownPeriod(uint256 _newCoolDownPeriod) external onlyWithdrawQueueAdmin {

139:     function pause() external onlyWithdrawQueueAdmin {
```

- *EzEthToken.sol* ( [51-51](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/token/EzEthToken.sol#L51-L51) ):

```solidity
51:     function setPaused(bool _paused) external onlyTokenAdmin {
```

</details>

### [L-16] Missing contract existence checks before low-level calls

Low-level calls return success if there is no code present at the specified address. In addition to the zero-address checks, add a check to verify that `<address>.code.length > 0`.

There is 1 instance:

- *TimelockController.sol* ( [369-369](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L369-L369) ):

```solidity
369:         (bool success, ) = target.call{ value: value }(data);
```

### [L-17] Tokens may be minted to the zero address

Neither the listed functions, nor `_mint()` prevent minting to `address(0x0)`

<details>
<summary>There are 11 instances (click to show):</summary>

- *xRenzoDeposit.sol* ( [266-266](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L266-L266) ):

```solidity
266:         IXERC20(address(xezETH)).mint(msg.sender, xezETHAmount);
```

- *XERC20.sol* ( [96-96](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20.sol#L96-L96), [152-152](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20.sol#L152-L152), [174-174](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20.sol#L174-L174), [206-206](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20.sol#L206-L206), [232-232](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20.sol#L232-L232) ):

```solidity
96:     function mint(address _user, uint256 _amount) public virtual {

152:     function mintingMaxLimitOf(address _bridge) public view returns (uint256 _limit) {

174:     function mintingCurrentLimitOf(address _bridge) public view returns (uint256 _limit) {

206:         uint256 _currentLimit = mintingCurrentLimitOf(_bridge);

232:         uint256 _currentLimit = mintingCurrentLimitOf(_bridge);
```

- *XERC20Lockbox.sol* ( [150-150](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L150-L150) ):

```solidity
150:         XERC20.mint(_to, _amount);
```

- *OptimismMintableXERC20.sol* ( [64-64](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L64-L64) ):

```solidity
64:     function mint(address _to, uint256 _amount) public override(XERC20, IOptimismMintableERC20) {
```

- *RestakeManager.sol* ( [572-572](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L572-L572), [612-612](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L612-L612) ):

```solidity
572:         ezETH.mint(msg.sender, ezETHToMint);

612:         ezETH.mint(msg.sender, ezETHToMint);
```

- *EzEthToken.sol* ( [41-41](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/token/EzEthToken.sol#L41-L41) ):

```solidity
41:     function mint(address to, uint256 amount) external onlyMinterBurner {
```

</details>

### [L-18] Code does not follow the best practice of check-effects-interaction

Code should follow the best-practice of [check-effects-interaction](https://blockchain-academy.hs-mittweida.de/courses/solidity-coding-beginners-to-intermediate/lessons/solidity-11-coding-patterns/topic/checks-effects-interactions/), where state variables are updated before any external calls are made. Doing so prevents a large class of reentrancy bugs.

<details>
<summary>There are 20 instances (click to show):</summary>

- *xRenzoBridge.sol* ( [259-259](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L259-L259), [283-283](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L283-L283) ):

```solidity
/// @audit `getRate()` is called on line 215
259:                 ++i;

/// @audit `getRate()` is called on line 215
283:                 ++i;
```

- *xRenzoDeposit.sol* ( [387-387](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L387-L387), [402-402](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L402-L402) ):

```solidity
/// @audit `safeApprove()` is called on line 369
387:             amountNextWETH -= fee;

/// @audit `withdraw()` is called on line 401
402:         feeCollected = address(this).balance - balanceBefore;
```

- *XERC20Factory.sol* ( [210-210](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L210-L210) ):

```solidity
/// @audit `setLockbox()` is called on line 208
210:         _lockboxRegistry[_xerc20] = _lockbox;
```

- *OperatorDelegator.sol* ( [281-281](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L281-L281), [291-291](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L291-L291), [294-294](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L294-L294), [312-312](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L312-L312), [358-358](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L358-L358), [385-385](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L385-L385), [387-387](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L387-L387), [489-489](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L489-L489) ):

```solidity
/// @audit `completeQueuedWithdrawal()` is called on line 274
281:             queuedShares[address(tokens[i])] -= withdrawal.shares[i];

/// @audit `completeQueuedWithdrawal()` is called on line 274
291:                     bufferToFill = (balanceOfToken <= bufferToFill) ? balanceOfToken : bufferToFill;

/// @audit `completeQueuedWithdrawal()` is called on line 274
294:                     balanceOfToken -= bufferToFill;

/// @audit `completeQueuedWithdrawal()` is called on line 274
312:                 ++i;

/// @audit `stake()` is called on line 355
358:         stakedButNotVerifiedEth += msg.value;

/// @audit `verifyWithdrawalCredentials()` is called on line 372
385:             stakedButNotVerifiedEth -= (validatorCurrentBalanceGwei * GWEI_TO_WEI);

/// @audit `verifyWithdrawalCredentials()` is called on line 372
387:                 ++i;

/// @audit `send()` is called on line 485
489:         adminGasSpentInWei[tx.origin] -= gasRefund;
```

- *DepositQueue.sol* ( [179-179](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L179-L179), [272-272](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L272-L272) ):

```solidity
/// @audit `_checkAndFillETHWithdrawBuffer()` is called on line 176, triggering an external call - `getBufferDeficit()`
179:         totalEarned[address(0x0)] = totalEarned[address(0x0)] + remainingRewards;

/// @audit `balanceOf()` is called on line 255
272:             totalEarned[address(token)] = totalEarned[address(token)] + balance - feeAmount;
```

- *RestakeManager.sol* ( [547-547](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L547-L547), [549-549](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L549-L549) ):

```solidity
/// @audit `calculateTVLs()` is called on line 504, triggering an external call - `withdrawQueue()`
547:             bufferToFill = (_amount <= bufferToFill) ? _amount : bufferToFill;

/// @audit `calculateTVLs()` is called on line 504, triggering an external call - `withdrawQueue()`
549:             _amount -= bufferToFill;
```

- *WithdrawQueue.sol* ( [229-232](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L229-L232), [239-239](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L239-L239), [253-253](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L253-L253) ):

```solidity
/// @audit `safeTransferFrom()` is called on line 214
229:             amountToRedeem = renzoOracle.lookupTokenAmountFromValue(
230:                 IERC20(_assetOut),
231:                 amountToRedeem
232:             );

/// @audit `safeTransferFrom()` is called on line 214
239:         withdrawRequestNonce++;

/// @audit `safeTransferFrom()` is called on line 214
253:         claimReserve[_assetOut] += amountToRedeem;
```

</details>

## Non Critical Issues

### [N-01] `abi.encodePacked()` should be replaced with `bytes.concat()`

Solidity version 0.8.4 introduces `bytes.concat()`, which can be used to replace `abi.encodePacked()` on bytes/strings. It can make the intended operation clearer, leading to less reviewer confusion.

There are 3 instances:

- *XERC20Factory.sol* ( [158-161](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L158-L161), [201-204](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L201-L204) ):

```solidity
158:         bytes memory _bytecode = abi.encodePacked(
159:             _creation,
160:             abi.encode(xerc20Implementation, _proxyAdmin, initializeBytecode)
161:         );

201:         bytes memory _bytecode = abi.encodePacked(
202:             _creation,
203:             abi.encode(lockboxImplementation, _proxyAdmin, initializeBytecode)
204:         );
```

- *OptimismMintableXERC20Factory.sol* ( [100-103](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L100-L103) ):

```solidity
100:         bytes memory _bytecode = abi.encodePacked(
101:             _creation,
102:             abi.encode(xerc20Implementation, _proxyAdmin, initializeBytecode)
103:         );
```

### [N-02] Import declarations should import specific identifiers, rather than the whole file

Using import declarations of the form `import {<identifier_name>} from "some/file.sol"` avoids polluting the symbol namespace making flattened files smaller, and speeds up compilation (but does not save any gas).

<details>
<summary>There are 138 instances (click to show):</summary>

- *xRenzoBridge.sol* ( [4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L4), [5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L5), [6](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L6), [10](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L10), [11](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L11), [12](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L12), [14](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L14) ):

```solidity
4: import "./xRenzoBridgeStorage.sol";

5: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

6: import "../../Errors/Errors.sol";

10: import "../Connext/core/IXReceiver.sol";

11: import "../Connext/core/IWeth.sol";

12: import "../xERC20/interfaces/IXERC20.sol";

14: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";
```

- *xRenzoBridgeStorage.sol* ( [4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridgeStorage.sol#L4), [5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridgeStorage.sol#L5), [6](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridgeStorage.sol#L6), [7](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridgeStorage.sol#L7), [8](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridgeStorage.sol#L8) ):

```solidity
4: import "./IxRenzoBridge.sol";

5: import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";

6: import "../../IRestakeManager.sol";

7: import "../xERC20/interfaces/IXERC20Lockbox.sol";

8: import "../Connext/core/IConnext.sol";
```

- *RenzoOracleL2.sol* ( [4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L4), [5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L5), [9](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L9) ):

```solidity
4: import "./RenzoOracleL2Storage.sol";

5: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

9: import "../../../Errors/Errors.sol";
```

- *RenzoOracleL2Storage.sol* ( [4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/Oracle/RenzoOracleL2Storage.sol#L4), [5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/Oracle/RenzoOracleL2Storage.sol#L5) ):

```solidity
4: import "./IRenzoOracleL2.sol";

5: import "@chainlink/contracts/src/v0.8/interfaces/AggregatorV3Interface.sol";
```

- *CCIPReceiver.sol* ( [11](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L11) ):

```solidity
11: import "../../../Errors/Errors.sol";
```

- *ConnextReceiver.sol* ( [8](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L8) ):

```solidity
8: import "../../../Errors/Errors.sol";
```

- *xRenzoDeposit.sol* ( [4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L4), [5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L5), [12](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L12), [13](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L13), [14](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L14), [15](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L15), [16](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L16) ):

```solidity
4: import "./xRenzoDepositStorage.sol";

5: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

12: import "../../Errors/Errors.sol";

13: import "../xERC20/interfaces/IXERC20.sol";

14: import "../Connext/core/IWeth.sol";

15: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";

16: import "../../RateProvider/IRateProvider.sol";
```

- *xRenzoDepositStorage.sol* ( [4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDepositStorage.sol#L4), [5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDepositStorage.sol#L5), [6](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDepositStorage.sol#L6), [7](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDepositStorage.sol#L7) ):

```solidity
4: import "./IxRenzoDeposit.sol";

5: import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";

6: import "../Connext/core/IConnext.sol";

7: import "./Oracle/IRenzoOracleL2.sol";
```

- *XERC20.sol* ( [14](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20.sol#L14) ):

```solidity
14: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";
```

- *XERC20Factory.sol* ( [11](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L11), [12](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L12) ):

```solidity
11: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

12: import "@openzeppelin/contracts/proxy/transparent/TransparentUpgradeableProxy.sol";
```

- *XERC20Lockbox.sol* ( [9](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L9) ):

```solidity
9: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";
```

- *OptimismMintableXERC20Factory.sol* ( [11](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L11), [12](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L12) ):

```solidity
11: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

12: import "@openzeppelin/contracts/proxy/transparent/TransparentUpgradeableProxy.sol";
```

- *OperatorDelegator.sol* ( [4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L4), [5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L5), [6](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L6), [7](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L7), [8](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L8), [9](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L9), [10](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L10) ):

```solidity
4: import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";

5: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";

6: import "../Permissions/IRoleManager.sol";

7: import "./OperatorDelegatorStorage.sol";

8: import "../EigenLayer/interfaces/IDelegationManager.sol";

9: import "../EigenLayer/interfaces/ISignatureUtils.sol";

10: import "../Errors/Errors.sol";
```

- *OperatorDelegatorStorage.sol* ( [3](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegatorStorage.sol#L3), [4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegatorStorage.sol#L4), [5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegatorStorage.sol#L5), [6](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegatorStorage.sol#L6), [7](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegatorStorage.sol#L7), [8](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegatorStorage.sol#L8), [9](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegatorStorage.sol#L9) ):

```solidity
3: import "../Permissions/IRoleManager.sol";

4: import "../EigenLayer/interfaces/IStrategy.sol";

5: import "../EigenLayer/interfaces/IStrategyManager.sol";

6: import "../EigenLayer/interfaces/IDelegationManager.sol";

7: import "../EigenLayer/interfaces/IEigenPod.sol";

8: import "./IOperatorDelegator.sol";

9: import "../IRestakeManager.sol";
```

- *DepositQueue.sol* ( [4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L4), [5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L5), [6](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L6), [7](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L7), [8](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L8) ):

```solidity
4: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

5: import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";

6: import "./DepositQueueStorage.sol";

7: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";

8: import "../Errors/Errors.sol";
```

- *DepositQueueStorage.sol* ( [4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueueStorage.sol#L4), [5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueueStorage.sol#L5), [6](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueueStorage.sol#L6), [7](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueueStorage.sol#L7) ):

```solidity
4: import "../Permissions/IRoleManager.sol";

5: import "../Withdraw/IWithdrawQueue.sol";

6: import "../IRestakeManager.sol";

7: import "./IDepositQueue.sol";
```

- *WBETHShim.sol* ( [4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Binance/WBETHShim.sol#L4), [5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Binance/WBETHShim.sol#L5), [6](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Binance/WBETHShim.sol#L6), [7](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Binance/WBETHShim.sol#L7) ):

```solidity
4: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";

5: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

6: import "./WBETHShimStorage.sol";

7: import "../../Errors/Errors.sol";
```

- *WBETHShimStorage.sol* ( [4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Binance/WBETHShimStorage.sol#L4), [5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Binance/WBETHShimStorage.sol#L5) ):

```solidity
4: import "@chainlink/contracts/src/v0.8/interfaces/AggregatorV3Interface.sol";

5: import "./IStakedTokenV2.sol";
```

- *METHShim.sol* ( [4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Mantle/METHShim.sol#L4), [5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Mantle/METHShim.sol#L5), [6](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Mantle/METHShim.sol#L6), [7](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Mantle/METHShim.sol#L7) ):

```solidity
4: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";

5: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

6: import "./METHShimStorage.sol";

7: import "../../Errors/Errors.sol";
```

- *METHShimStorage.sol* ( [4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Mantle/METHShimStorage.sol#L4), [5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Mantle/METHShimStorage.sol#L5) ):

```solidity
4: import "@chainlink/contracts/src/v0.8/interfaces/AggregatorV3Interface.sol";

5: import "./IMethStaking.sol";
```

- *RenzoOracle.sol* ( [4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L4), [5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L5), [6](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L6), [7](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L7), [8](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L8) ):

```solidity
4: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";

5: import "../Permissions/IRoleManager.sol";

6: import "./RenzoOracleStorage.sol";

7: import "./IRenzoOracle.sol";

8: import "../Errors/Errors.sol";
```

- *RenzoOracleStorage.sol* ( [4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracleStorage.sol#L4), [5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracleStorage.sol#L5), [6](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracleStorage.sol#L6) ):

```solidity
4: import "../Permissions/IRoleManager.sol";

5: import "@chainlink/contracts/src/v0.8/interfaces/AggregatorV3Interface.sol";

6: import "@openzeppelin/contracts/token/ERC20/IERC20.sol";
```

- *RoleManager.sol* ( [4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Permissions/RoleManager.sol#L4), [5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Permissions/RoleManager.sol#L5), [6](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Permissions/RoleManager.sol#L6), [7](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Permissions/RoleManager.sol#L7) ):

```solidity
4: import "@openzeppelin/contracts-upgradeable/access/AccessControlUpgradeable.sol";

5: import "./IRoleManager.sol";

6: import "./RoleManagerStorage.sol";

7: import "../Errors/Errors.sol";
```

- *BalancerRateProvider.sol* ( [4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RateProvider/BalancerRateProvider.sol#L4), [5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RateProvider/BalancerRateProvider.sol#L5), [6](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RateProvider/BalancerRateProvider.sol#L6), [7](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RateProvider/BalancerRateProvider.sol#L7) ):

```solidity
4: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

5: import "./IRateProvider.sol";

6: import "../Errors/Errors.sol";

7: import "./BalancerRateProviderStorage.sol";
```

- *BalancerRateProviderStorage.sol* ( [4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RateProvider/BalancerRateProviderStorage.sol#L4), [5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RateProvider/BalancerRateProviderStorage.sol#L5) ):

```solidity
4: import "@openzeppelin/contracts-upgradeable/token/ERC20/IERC20Upgradeable.sol";

5: import "../IRestakeManager.sol";
```

- *RestakeManager.sol* ( [4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L4), [5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L5), [6](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L6), [7](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L7), [8](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L8), [9](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L9), [10](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L10), [11](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L11), [12](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L12), [13](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L13), [14](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L14), [15](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L15), [16](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L16), [17](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L17) ):

```solidity
4: import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";

5: import "@openzeppelin/contracts-upgradeable/token/ERC20/utils/SafeERC20Upgradeable.sol";

6: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

7: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";

8: import "@openzeppelin/contracts-upgradeable/token/ERC20/IERC20Upgradeable.sol";

9: import "@openzeppelin/contracts/token/ERC20/IERC20.sol";

10: import "@openzeppelin/contracts/token/ERC20/extensions/IERC20Metadata.sol";

11: import "./RestakeManagerStorage.sol";

12: import "./EigenLayer/interfaces/IStrategy.sol";

13: import "./EigenLayer/interfaces/IStrategyManager.sol";

14: import "./EigenLayer/interfaces/IDelegationManager.sol";

15: import "./token/IEzEthToken.sol";

16: import "./IRestakeManager.sol";

17: import "./Errors/Errors.sol";
```

- *RestakeManagerStorage.sol* ( [4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManagerStorage.sol#L4), [5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManagerStorage.sol#L5), [6](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManagerStorage.sol#L6), [7](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManagerStorage.sol#L7), [8](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManagerStorage.sol#L8), [9](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManagerStorage.sol#L9), [10](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManagerStorage.sol#L10), [11](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManagerStorage.sol#L11), [12](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManagerStorage.sol#L12), [13](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManagerStorage.sol#L13) ):

```solidity
4: import "./EigenLayer/interfaces/IStrategy.sol";

5: import "./EigenLayer/interfaces/IDelegationManager.sol";

6: import "./EigenLayer/interfaces/IStrategyManager.sol";

7: import "./token/IEzEthToken.sol";

8: import "./Delegation/IOperatorDelegator.sol";

9: import "./Permissions/IRoleManager.sol";

10: import "./Oracle/IRenzoOracle.sol";

11: import "./Deposits/IDepositQueue.sol";

12: import "./IRestakeManager.sol";

13: import "./Withdraw/IWithdrawQueue.sol";
```

- *RewardHandler.sol* ( [4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Rewards/RewardHandler.sol#L4), [5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Rewards/RewardHandler.sol#L5), [6](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Rewards/RewardHandler.sol#L6), [7](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Rewards/RewardHandler.sol#L7) ):

```solidity
4: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

5: import "./RewardHandlerStorage.sol";

6: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";

7: import "../Errors/Errors.sol";
```

- *RewardHandlerStorage.sol* ( [4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Rewards/RewardHandlerStorage.sol#L4) ):

```solidity
4: import "../Permissions/IRoleManager.sol";
```

- *TimelockController.sol* ( [6](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L6), [7](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L7), [8](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L8) ):

```solidity
6: import "@openzeppelin/contracts/access/AccessControl.sol";

7: import "@openzeppelin/contracts/token/ERC721/IERC721Receiver.sol";

8: import "@openzeppelin/contracts/token/ERC1155/IERC1155Receiver.sol";
```

- *WithdrawQueue.sol* ( [4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L4), [5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L5), [6](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L6), [7](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L7), [8](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L8), [9](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L9) ):

```solidity
4: import "./WithdrawQueueStorage.sol";

5: import "../Errors/Errors.sol";

6: import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";

7: import "@openzeppelin/contracts-upgradeable/security/PausableUpgradeable.sol";

8: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";

9: import "@openzeppelin/contracts/token/ERC20/IERC20.sol";
```

- *WithdrawQueueStorage.sol* ( [4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueueStorage.sol#L4), [5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueueStorage.sol#L5), [6](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueueStorage.sol#L6), [7](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueueStorage.sol#L7) ):

```solidity
4: import "../Permissions/IRoleManager.sol";

5: import "../Oracle/IRenzoOracle.sol";

6: import "../IRestakeManager.sol";

7: import "../token/IEzEthToken.sol";
```

- *EzEthToken.sol* ( [4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/token/EzEthToken.sol#L4), [5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/token/EzEthToken.sol#L5), [6](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/token/EzEthToken.sol#L6), [7](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/token/EzEthToken.sol#L7), [8](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/token/EzEthToken.sol#L8), [9](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/token/EzEthToken.sol#L9) ):

```solidity
4: import "@openzeppelin/contracts-upgradeable/token/ERC20/ERC20Upgradeable.sol";

5: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

6: import "./IEzEthToken.sol";

7: import "../Permissions/IRoleManager.sol";

8: import "./EzEthTokenStorage.sol";

9: import "../Errors/Errors.sol";
```

- *EzEthTokenStorage.sol* ( [3](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/token/EzEthTokenStorage.sol#L3) ):

```solidity
3: import "../Permissions/IRoleManager.sol";
```

</details>

### [N-03] Visibility of state variables is not explicitly defined

To avoid misunderstandings and unexpected state accesses, it is recommended to explicitly define the visibility of each state variable.

There are 6 instances:

- *LockboxAdapterBlast.sol* ( [31-31](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L31-L31), [32-32](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L32-L32) ):

```solidity
31:     address immutable blastStandardBridge;

32:     address immutable registry;
```

- *RenzoOracle.sol* ( [20-20](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L20-L20), [23-23](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L23-L23), [26-26](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L26-L26) ):

```solidity
20:     string constant INVALID_0_INPUT = "Invalid 0 input";

23:     uint256 constant SCALE_FACTOR = 10 ** 18;

26:     uint256 constant MAX_TIME_WINDOW = 86400 + 60; // 24 hours + 60 seconds
```

- *RestakeManager.sol* ( [38-38](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L38-L38) ):

```solidity
38:     uint256 constant BASIS_POINTS = 100;
```

### [N-04] Names of `private`/`internal` state variables should be prefixed with an underscore

It is recommended by the [Solidity Style Guide](https://docs.soliditylang.org/en/v0.8.20/style-guide.html#underscore-prefix-for-non-external-functions-and-variables).

There are 7 instances:

- *LockboxAdapterBlast.sol* ( [31-31](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L31-L31), [32-32](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L32-L32) ):

```solidity
31:     address immutable blastStandardBridge;

32:     address immutable registry;
```

- *OperatorDelegator.sol* ( [24-24](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L24-L24) ):

```solidity
24:     uint256 internal constant GWEI_TO_WEI = 1e9;
```

- *RenzoOracle.sol* ( [20-20](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L20-L20), [23-23](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L23-L23), [26-26](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L26-L26) ):

```solidity
20:     string constant INVALID_0_INPUT = "Invalid 0 input";

23:     uint256 constant SCALE_FACTOR = 10 ** 18;

26:     uint256 constant MAX_TIME_WINDOW = 86400 + 60; // 24 hours + 60 seconds
```

- *RestakeManager.sol* ( [38-38](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L38-L38) ):

```solidity
38:     uint256 constant BASIS_POINTS = 100;
```

### [N-05] The `nonReentrant` `modifier` should occur before all other modifiers

This is a best-practice to protect against reentrancy in other modifiers

There are 2 instances:

- *xRenzoBridge.sol* ( [210-213](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L210-L213) ):

```solidity
210:     function sendPrice(
211:         CCIPDestinationParam[] calldata _destinationParam,
212:         ConnextDestinationParam[] calldata _connextDestinationParam
213:     ) external payable onlyPriceFeedSender nonReentrant {
```

- *DepositQueue.sol* ( [211-216](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L211-L216) ):

```solidity
211:     function stakeEthFromQueueMulti(
212:         IOperatorDelegator[] calldata operatorDelegators,
213:         bytes[] calldata pubkeys,
214:         bytes[] calldata signatures,
215:         bytes32[] calldata depositDataRoots
216:     ) external onlyNativeEthRestakeAdmin nonReentrant {
```

### [N-06] Redundant inheritance specifier

The contracts below already extend the specified contract, so there is no need to list it in the inheritance list again.

<details>
<summary>There are 13 instances (click to show):</summary>

- *xRenzoBridge.sol* ( [16-20](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L16-L20) ):

```solidity
/// @audit ReentrancyGuardUpgradeable already extends Initializable
16: contract xRenzoBridge is
17:     IXReceiver,
18:     Initializable,
19:     ReentrancyGuardUpgradeable,
20:     xRenzoBridgeStorageV1
```

- *RenzoOracleL2.sol* ( [11-11](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L11-L11) ):

```solidity
/// @audit OwnableUpgradeable already extends Initializable
11: contract RenzoOracleL2 is Initializable, OwnableUpgradeable, RenzoOracleL2StorageV1 {
```

- *xRenzoDeposit.sol* ( [27-32](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L27-L32) ):

```solidity
/// @audit OwnableUpgradeable already extends Initializable
27: contract xRenzoDeposit is
28:     Initializable,
29:     OwnableUpgradeable,
30:     ReentrancyGuardUpgradeable,
31:     IRateProvider,
32:     xRenzoDepositStorageV3
```

- *XERC20.sol* ( [16-21](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20.sol#L16-L21) ):

```solidity
/// @audit ERC20Upgradeable already extends Initializable
/// @audit ERC20PermitUpgradeable already extends ERC20Upgradeable
16: contract XERC20 is
17:     Initializable,
18:     ERC20Upgradeable,
19:     OwnableUpgradeable,
20:     IXERC20,
21:     ERC20PermitUpgradeable
```

- *OptimismMintableXERC20Factory.sol* ( [14-14](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L14-L14) ):

```solidity
/// @audit XERC20Factory already extends Initializable
14: contract OptimismMintableXERC20Factory is Initializable, XERC20Factory {
```

- *OperatorDelegator.sol* ( [17-20](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L17-L20) ):

```solidity
/// @audit ReentrancyGuardUpgradeable already extends Initializable
17: contract OperatorDelegator is
18:     Initializable,
19:     ReentrancyGuardUpgradeable,
20:     OperatorDelegatorStorageV4
```

- *DepositQueue.sol* ( [10-10](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L10-L10) ):

```solidity
/// @audit ReentrancyGuardUpgradeable already extends Initializable
10: contract DepositQueue is Initializable, ReentrancyGuardUpgradeable, DepositQueueStorageV2 {
```

- *RenzoOracle.sol* ( [13-17](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L13-L17) ):

```solidity
/// @audit ReentrancyGuardUpgradeable already extends Initializable
13: contract RenzoOracle is
14:     IRenzoOracle,
15:     Initializable,
16:     ReentrancyGuardUpgradeable,
17:     RenzoOracleStorageV1
```

- *RestakeManager.sol* ( [26-26](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L26-L26) ):

```solidity
/// @audit ReentrancyGuardUpgradeable already extends Initializable
26: contract RestakeManager is Initializable, ReentrancyGuardUpgradeable, RestakeManagerStorageV2 {
```

- *RewardHandler.sol* ( [16-16](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Rewards/RewardHandler.sol#L16-L16) ):

```solidity
/// @audit ReentrancyGuardUpgradeable already extends Initializable
16: contract RewardHandler is Initializable, ReentrancyGuardUpgradeable, RewardHandlerStorageV1 {
```

- *WithdrawQueue.sol* ( [11-15](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L11-L15) ):

```solidity
/// @audit PausableUpgradeable already extends Initializable
11: contract WithdrawQueue is
12:     Initializable,
13:     PausableUpgradeable,
14:     ReentrancyGuardUpgradeable,
15:     WithdrawQueueStorageV1
```

- *EzEthToken.sol* ( [13-13](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/token/EzEthToken.sol#L13-L13) ):

```solidity
/// @audit ERC20Upgradeable already extends Initializable
13: contract EzEthToken is Initializable, ERC20Upgradeable, IEzEthToken, EzEthTokenStorageV1 {
```

</details>

### [N-07] Use of `override` is unnecessary

[Starting from Solidity 0.8.8](https://docs.soliditylang.org/en/v0.8.20/contracts.html#function-overriding), the override keyword is not required when overriding an interface function, except for the case where the function is defined in multiple bases.

<details>
<summary>There are 12 instances (click to show):</summary>

- *CCIPReceiver.sol* ( [66-68](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L66-L68) ):

```solidity
66:     function _ccipReceive(
67:         Client.Any2EVMMessage memory any2EvmMessage
68:     ) internal override whenNotPaused {
```

- *xRenzoDeposit.sol* ( [310-310](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L310-L310), [456-456](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L456-L456) ):

```solidity
310:     function updatePrice(uint256 _price, uint256 _timestamp) external override {

456:     function getRate() external view override returns (uint256) {
```

- *OptimismMintableXERC20.sol* ( [48-50](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L48-L50), [56-56](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L56-L56), [60-60](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L60-L60) ):

```solidity
48:     function supportsInterface(
49:         bytes4 interfaceId
50:     ) public view override(ERC165Upgradeable) returns (bool) {

56:     function remoteToken() public view override returns (address) {

60:     function bridge() public view override returns (address) {
```

- *TimelockController.sol* ( [411-416](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L411-L416), [423-429](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L423-L429), [436-442](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L436-L442) ):

```solidity
411:     function onERC721Received(
412:         address,
413:         address,
414:         uint256,
415:         bytes memory
416:     ) public virtual override returns (bytes4) {

423:     function onERC1155Received(
424:         address,
425:         address,
426:         uint256,
427:         uint256,
428:         bytes memory
429:     ) public virtual override returns (bytes4) {

436:     function onERC1155BatchReceived(
437:         address,
438:         address,
439:         uint256[] memory,
440:         uint256[] memory,
441:         bytes memory
442:     ) public virtual override returns (bytes4) {
```

- *EzEthToken.sol* ( [56-60](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/token/EzEthToken.sol#L56-L60), [77-77](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/token/EzEthToken.sol#L77-L77), [85-85](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/token/EzEthToken.sol#L85-L85) ):

```solidity
56:     function _beforeTokenTransfer(
57:         address from,
58:         address to,
59:         uint256 amount
60:     ) internal virtual override {

77:     function name() public view virtual override returns (string memory) {

85:     function symbol() public view virtual override returns (string memory) {
```

</details>

### [N-08] Unused `struct`s

Note that there may be cases where a struct superficially appears to be used, but this is only because there are multiple definitions of the struct in different files. In such cases, the struct definition should be moved into a separate file. The instances below are the unused definitions.

There are 2 instances:

- *LibConnextStorage.sol* ( [64](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/Connext/libraries/LibConnextStorage.sol#L64) ):

```solidity
64: struct ExecuteArgs {
```

- *TokenId.sol* ( [9](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/Connext/libraries/TokenId.sol#L9) ):

```solidity
9: struct TokenId {
```

### [N-09] Custom errors should be used rather than `revert()`/`require()`

Custom errors are available from solidity version 0.8.4. Custom errors are more easily processed in try-catch blocks, and are easier to re-use and maintain.

There are 12 instances:

- *TimelockController.sol* ( [267-267](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L267-L267), [268-268](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L268-L268), [284-284](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L284-L284), [285-285](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L285-L285), [297-297](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L297-L297), [349-349](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L349-L349), [350-350](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L350-L350), [370-370](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L370-L370), [377-377](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L377-L377), [378-381](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L378-L381), [388-388](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L388-L388), [403-403](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L403-L403) ):

```solidity
267:         require(targets.length == values.length, "TimelockController: length mismatch");

268:         require(targets.length == payloads.length, "TimelockController: length mismatch");

284:         require(!isOperation(id), "TimelockController: operation already scheduled");

285:         require(delay >= getMinDelay(), "TimelockController: insufficient delay");

297:         require(isOperationPending(id), "TimelockController: operation cannot be cancelled");

349:         require(targets.length == values.length, "TimelockController: length mismatch");

350:         require(targets.length == payloads.length, "TimelockController: length mismatch");

370:         require(success, "TimelockController: underlying transaction reverted");

377:         require(isOperationReady(id), "TimelockController: operation is not ready");

378:         require(
379:             predecessor == bytes32(0) || isOperationDone(predecessor),
380:             "TimelockController: missing dependency"
381:         );

388:         require(isOperationReady(id), "TimelockController: operation is not ready");

403:         require(msg.sender == address(this), "TimelockController: caller must be timelock");
```

### [N-10] Add inline comments for unnamed parameters

`function func(address a, address)` -> `function func(address a, address /* b */)`

<details>
<summary>There are 7 instances (click to show):</summary>

- *xRenzoBridge.sol* ( [139-146](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L139-L146) ):

```solidity
139:     function xReceive(
140:         bytes32 _transferId,
141:         uint256 _amount,
142:         address _asset,
143:         address _originSender,
144:         uint32 _origin,
145:         bytes memory
146:     ) external nonReentrant returns (bytes memory) {
```

- *ConnextReceiver.sol* ( [69-76](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L69-L76) ):

```solidity
69:     function xReceive(
70:         bytes32 _transferId,
71:         uint256,
72:         address,
73:         address _originSender,
74:         uint32 _origin,
75:         bytes memory _callData
76:     ) external onlySource(_originSender, _origin) whenNotPaused returns (bytes memory) {
```

- *WBETHShim.sol* ( [42-42](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Binance/WBETHShim.sol#L42-L42) ):

```solidity
42:     function getRoundData(uint80) external pure returns (uint80, int256, uint256, uint256, uint80) {
```

- *METHShim.sol* ( [42-42](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Mantle/METHShim.sol#L42-L42) ):

```solidity
42:     function getRoundData(uint80) external pure returns (uint80, int256, uint256, uint256, uint80) {
```

- *TimelockController.sol* ( [411-416](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L411-L416), [423-429](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L423-L429), [436-442](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L436-L442) ):

```solidity
411:     function onERC721Received(
412:         address,
413:         address,
414:         uint256,
415:         bytes memory
416:     ) public virtual override returns (bytes4) {

423:     function onERC1155Received(
424:         address,
425:         address,
426:         uint256,
427:         uint256,
428:         bytes memory
429:     ) public virtual override returns (bytes4) {

436:     function onERC1155BatchReceived(
437:         address,
438:         address,
439:         uint256[] memory,
440:         uint256[] memory,
441:         bytes memory
442:     ) public virtual override returns (bytes4) {
```

</details>

### [N-11] Consider providing a ranged getter for array state variables

While the compiler automatically provides a getter for accessing single elements within a public state variable array, it doesn't provide a way to fetch the whole array, or subsets thereof. Consider adding a function to allow the fetching of slices of the array, especially if the contract doesn't already have multicall functionality.

There are 3 instances:

- *RestakeManagerStorage.sol* ( [42-42](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManagerStorage.sol#L42-L42), [49-49](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManagerStorage.sol#L49-L49) ):

```solidity
42:     IOperatorDelegator[] public operatorDelegators;

49:     IERC20[] public collateralTokens;
```

- *WithdrawQueueStorage.sol* ( [50-50](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueueStorage.sol#L50-L50) ):

```solidity
50:     mapping(address => WithdrawRequest[]) public withdrawRequests;
```

### [N-12] Consider splitting complex checks into multiple steps

Assign the expression's parts to intermediate local variables, and check against those instead.

There is 1 instance:

- *XERC20Factory.sol* ( [111-111](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L111-L111) ):

```solidity
111:         if ((_baseToken == address(0) && !_isNative) || (_isNative && _baseToken != address(0))) {
```

### [N-13] Consider adding a block/deny-list

Doing so will significantly increase centralization, but will help to prevent hackers from using stolen tokens

<details>
<summary>There are 8 instances (click to show):</summary>

- *LockboxAdapterBlast.sol* ( [30](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L30) ):

```solidity
30: contract LockboxAdapterBlast {
```

- *xRenzoBridge.sol* ( [16](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L16) ):

```solidity
16: contract xRenzoBridge is
```

- *xRenzoDeposit.sol* ( [27](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L27) ):

```solidity
27: contract xRenzoDeposit is
```

- *XERC20Lockbox.sol* ( [11](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L11) ):

```solidity
11: contract XERC20Lockbox is Initializable, IXERC20Lockbox {
```

- *OperatorDelegator.sol* ( [17](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L17) ):

```solidity
17: contract OperatorDelegator is
```

- *DepositQueue.sol* ( [10](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L10) ):

```solidity
10: contract DepositQueue is Initializable, ReentrancyGuardUpgradeable, DepositQueueStorageV2 {
```

- *RestakeManager.sol* ( [26](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L26) ):

```solidity
26: contract RestakeManager is Initializable, ReentrancyGuardUpgradeable, RestakeManagerStorageV2 {
```

- *WithdrawQueue.sol* ( [11](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L11) ):

```solidity
11: contract WithdrawQueue is
```

</details>

### [N-14] Constants/Immutables redefined elsewhere

Consider defining in only one contract so that values cannot become out of sync when only one location is updated. A [cheap way](https://medium.com/coinmonks/gas-cost-of-solidity-library-functions-dbe0cedd4678) to store constants/immutables in a single location is to create an `internal constant` in a `library`. If the variable is a local cache of another contract's value, consider making the cache variable internal or private, which will require external users to query the contract with the source of truth, so that callers don't get out of sync.

<details>
<summary>There are 7 instances (click to show):</summary>

- *xRenzoBridge.sol* ( [61-61](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L61-L61) ):

```solidity
/// @audit Seen in contracts/Bridge/L2/xRenzoDeposit.sol#37
61:     uint8 public constant EXPECTED_DECIMALS = 18;
```

- *RenzoOracleL2.sol* ( [13-13](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L13-L13) ):

```solidity
/// @audit Seen in contracts/Oracle/RenzoOracle.sol#26
13:     uint256 public constant MAX_TIME_WINDOW = 86400 + 60; // 24 hours + 60 seconds
```

- *xRenzoDeposit.sol* ( [37-37](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L37-L37) ):

```solidity
/// @audit Seen in contracts/Bridge/L1/xRenzoBridge.sol#61
37:     uint8 public constant EXPECTED_DECIMALS = 18;
```

- *OperatorDelegator.sol* ( [26-26](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L26-L26) ):

```solidity
/// @audit Seen in contracts/Deposits/DepositQueue.sol#13
26:     address public constant IS_NATIVE = 0xEeeeeEeeeEeEeeEeEeEeeEEEeeeeEeeeeeeeEEeE;
```

- *DepositQueue.sol* ( [13-13](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L13-L13) ):

```solidity
/// @audit Seen in contracts/Withdraw/WithdrawQueueStorage.sol#10
13:     address public constant IS_NATIVE = 0xEeeeeEeeeEeEeeEeEeEeeEEEeeeeEeeeeeeeEEeE;
```

- *RenzoOracle.sol* ( [26-26](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L26-L26) ):

```solidity
/// @audit Seen in contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#13
26:     uint256 constant MAX_TIME_WINDOW = 86400 + 60; // 24 hours + 60 seconds
```

- *WithdrawQueueStorage.sol* ( [10-10](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueueStorage.sol#L10-L10) ):

```solidity
/// @audit Seen in contracts/Deposits/DepositQueue.sol#13
10:     address public constant IS_NATIVE = 0xEeeeeEeeeEeEeeEeEeEeeEEEeeeeEeeeeeeeEEeE;
```

</details>

### [N-15] Contracts should each be defined in separate files

Keeping each contract in a separate file makes it easier to work with multiple people, makes the code easier to maintain, and is a common practice on most projects. The following files each contains more than one contract/library/interface.

There are 6 instances:

- [*LockboxAdapterBlast.sol*](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol)

- [*xRenzoDepositStorage.sol*](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDepositStorage.sol)

- [*OperatorDelegatorStorage.sol*](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegatorStorage.sol)

- [*DepositQueueStorage.sol*](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueueStorage.sol)

- [*RoleManagerStorage.sol*](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Permissions/RoleManagerStorage.sol)

- [*RestakeManagerStorage.sol*](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManagerStorage.sol)

### [N-16] Contract name does not match its filename

According to the [Solidity Style Guide](https://docs.soliditylang.org/en/latest/style-guide.html#contract-and-library-names), contract and library names should also match their filenames.

<details>
<summary>There are 10 instances (click to show):</summary>

- *xRenzoBridgeStorage.sol* ( [18](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridgeStorage.sol#L18) ):

```solidity
/// @audit Not match filename `xRenzoBridgeStorage.sol`
18: abstract contract xRenzoBridgeStorageV1 is IxRenzoBridge {
```

- *RenzoOracleL2Storage.sol* ( [7](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/Oracle/RenzoOracleL2Storage.sol#L7) ):

```solidity
/// @audit Not match filename `RenzoOracleL2Storage.sol`
7: abstract contract RenzoOracleL2StorageV1 is IRenzoOracleL2 {
```

- *CCIPReceiver.sol* ( [14](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L14) ):

```solidity
/// @audit Not match filename `CCIPReceiver.sol`
14: contract Receiver is CCIPReceiver, Ownable, Pausable {
```

- *WBETHShimStorage.sol* ( [7](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Binance/WBETHShimStorage.sol#L7) ):

```solidity
/// @audit Not match filename `WBETHShimStorage.sol`
7: abstract contract WBETHShimStorageV1 is AggregatorV3Interface {
```

- *METHShimStorage.sol* ( [7](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Mantle/METHShimStorage.sol#L7) ):

```solidity
/// @audit Not match filename `METHShimStorage.sol`
7: abstract contract METHShimStorageV1 is AggregatorV3Interface {
```

- *RenzoOracleStorage.sol* ( [8](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracleStorage.sol#L8) ):

```solidity
/// @audit Not match filename `RenzoOracleStorage.sol`
8: abstract contract RenzoOracleStorageV1 {
```

- *BalancerRateProviderStorage.sol* ( [7](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RateProvider/BalancerRateProviderStorage.sol#L7) ):

```solidity
/// @audit Not match filename `BalancerRateProviderStorage.sol`
7: abstract contract BalancerRateProviderStorageV1 {
```

- *RewardHandlerStorage.sol* ( [6](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Rewards/RewardHandlerStorage.sol#L6) ):

```solidity
/// @audit Not match filename `RewardHandlerStorage.sol`
6: abstract contract RewardHandlerStorageV1 {
```

- *WithdrawQueueStorage.sol* ( [9](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueueStorage.sol#L9) ):

```solidity
/// @audit Not match filename `WithdrawQueueStorage.sol`
9: abstract contract WithdrawQueueStorageV1 {
```

- *EzEthTokenStorage.sol* ( [10](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/token/EzEthTokenStorage.sol#L10) ):

```solidity
/// @audit Not match filename `EzEthTokenStorage.sol`
10: contract EzEthTokenStorageV1 {
```

</details>

### [N-17] Consider using `AccessControlDefaultAdminRules` rather than `AccessControl`

The `AccessControlDefaultAdminRules` implements multiple [security best practices](https://docs.openzeppelin.com/contracts/4.x/api/access#AccessControlDefaultAdminRules) on top of the normal `AccessControl` rules, so consider using it instead.

There is 1 instance:

- *TimelockController.sol* ( [25-25](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L25-L25) ):

```solidity
25: contract TimelockController is AccessControl, IERC721Receiver, IERC1155Receiver {
```

### [N-18] UPPER_CASE names should be reserved for `constant`/`immutable` variables

If the variable needs to be different based on which class it comes from, a `view`/`pure` _function_ should be used instead (e.g. like [this](https://github.com/OpenZeppelin/openzeppelin-contracts/blob/76eee35971c2541585e05cbf258510dda7b2fbc6/contracts/token/ERC20/extensions/draft-IERC20Permit.sol#L59)).

There are 4 instances:

- *XERC20.sol* ( [31](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20.sol#L31) ):

```solidity
31:     address public FACTORY;
```

- *XERC20Lockbox.sol* ( [18](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L18), [23](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L23), [29](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L29) ):

```solidity
18:     IXERC20 public XERC20;

23:     IERC20 public ERC20;

29:     bool public IS_NATIVE;
```

### [N-19] Consider emitting an event at the end of the constructor

This will allow users to easily exactly pinpoint when and by whom a contract was constructed.

<details>
<summary>There are 22 instances (click to show):</summary>

- *LockboxAdapterBlast.sol* ( [39-39](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L39-L39) ):

```solidity
39:     constructor(address _blastStandardBridge, address _registry) {
```

- *xRenzoBridge.sol* ( [65-65](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L65-L65) ):

```solidity
65:     constructor() {
```

- *RenzoOracleL2.sol* ( [19-19](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L19-L19) ):

```solidity
19:     constructor() {
```

- *CCIPReceiver.sol* ( [43-47](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L43-L47) ):

```solidity
43:     constructor(
44:         address _router,
45:         address _xRenzoBridgeL1,
46:         uint64 _ccipEthChainSelector
47:     ) CCIPReceiver(_router) {
```

- *ConnextReceiver.sol* ( [52-52](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L52-L52) ):

```solidity
52:     constructor(address _connext, address _xRenzoBridgeL1, uint32 _connextEthChainDomain) {
```

- *xRenzoDeposit.sol* ( [59-59](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L59-L59) ):

```solidity
59:     constructor() {
```

- *XERC20.sol* ( [50-50](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20.sol#L50-L50) ):

```solidity
50:     constructor() {
```

- *XERC20Factory.sol* ( [44-44](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L44-L44) ):

```solidity
44:     constructor() {
```

- *XERC20Lockbox.sol* ( [33-33](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L33-L33) ):

```solidity
33:     constructor() {
```

- *OptimismMintableXERC20.sol* ( [24-24](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L24-L24) ):

```solidity
24:     constructor() {
```

- *OptimismMintableXERC20Factory.sol* ( [19-19](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L19-L19) ):

```solidity
19:     constructor() {
```

- *OperatorDelegator.sol* ( [69-69](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L69-L69) ):

```solidity
69:     constructor() {
```

- *DepositQueue.sol* ( [69-69](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L69-L69) ):

```solidity
69:     constructor() {
```

- *WBETHShim.sol* ( [18-18](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Binance/WBETHShim.sol#L18-L18) ):

```solidity
18:     constructor() {
```

- *METHShim.sol* ( [18-18](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Mantle/METHShim.sol#L18-L18) ):

```solidity
18:     constructor() {
```

- *RenzoOracle.sol* ( [39-39](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L39-L39) ):

```solidity
39:     constructor() {
```

- *RoleManager.sol* ( [17-17](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Permissions/RoleManager.sol#L17-L17) ):

```solidity
17:     constructor() {
```

- *BalancerRateProvider.sol* ( [12-12](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RateProvider/BalancerRateProvider.sol#L12-L12) ):

```solidity
12:     constructor() {
```

- *RestakeManager.sol* ( [96-96](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L96-L96) ):

```solidity
96:     constructor() {
```

- *RewardHandler.sol* ( [33-33](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Rewards/RewardHandler.sol#L33-L33) ):

```solidity
33:     constructor() {
```

- *WithdrawQueue.sol* ( [57-57](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L57-L57) ):

```solidity
57:     constructor() {
```

- *EzEthToken.sol* ( [28-28](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/token/EzEthToken.sol#L28-L28) ):

```solidity
28:     constructor() {
```

</details>

### [N-20] Empty function body without comments

Empty function body in solidity is not recommended, consider adding some comments to the body.

There are 3 instances:

- *xRenzoBridge.sol* ( [313-313](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L313-L313) ):

```solidity
313:     receive() external payable {}
```

- *xRenzoDeposit.sol* ( [542-542](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L542-L542) ):

```solidity
542:     receive() external payable {}
```

- *TimelockController.sol* ( [137-137](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L137-L137) ):

```solidity
137:     receive() external payable {}
```

### [N-21] Events are emitted without the sender information

When an action is triggered based on a user's action, not being able to filter based on who triggered the action makes event processing a lot more cumbersome. Including the `msg.sender` the events of these types of action will make events much more useful to end users, especially when `msg.sender` is not `tx.origin`.

<details>
<summary>There are 16 instances (click to show):</summary>

- *xRenzoBridge.sol* ( [250-257](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L250-L257), [275-280](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L275-L280) ):

```solidity
250:             emit MessageSent(
251:                 messageId,
252:                 _destinationParam[i].destinationChainSelector,
253:                 _destinationParam[i]._renzoReceiver,
254:                 exchangeRate,
255:                 address(linkToken),
256:                 fees
257:             );

275:             emit ConnextMessageSent(
276:                 _connextDestinationParam[i].destinationDomainId,
277:                 _connextDestinationParam[i]._renzoReceiver,
278:                 exchangeRate,
279:                 _connextDestinationParam[i].relayerFee
280:             );
```

- *XERC20.sol* ( [125-125](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20.sol#L125-L125) ):

```solidity
125:         emit LockboxSet(_lockbox);
```

- *XERC20Factory.sol* ( [91-91](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L91-L91), [120-120](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L120-L120) ):

```solidity
91:         emit XERC20Deployed(_xerc20);

120:         emit LockboxDeployed(_lockbox);
```

- *XERC20Lockbox.sol* ( [126-126](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L126-L126), [151-151](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L151-L151) ):

```solidity
126:         emit Withdraw(_to, _amount);

151:         emit Deposit(_to, _amount);
```

- *OptimismMintableXERC20Factory.sol* ( [56-56](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L56-L56) ):

```solidity
56:         emit XERC20Deployed(_xerc20);
```

- *OperatorDelegator.sol* ( [523-523](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L523-L523) ):

```solidity
523:             emit RewardsForwarded(destination, remainingAmount);
```

- *DepositQueue.sol* ( [155-155](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L155-L155), [171-171](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L171-L171), [182-182](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L182-L182) ):

```solidity
155:         emit FullWithdrawalETHReceived(msg.value);

171:             emit ProtocolFeesPaid(IERC20(address(0x0)), feeAmount, feeAddress);

182:         emit RewardsDeposited(IERC20(address(0x0)), remainingRewards);
```

- *TimelockController.sol* ( [404-404](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L404-L404) ):

```solidity
404:         emit MinDelayChange(_minDelay, newDelay);
```

- *WithdrawQueue.sol* ( [183-183](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L183-L183), [198-198](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L198-L198), [311-311](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L311-L311) ):

```solidity
183:         emit EthBufferFilled(msg.value);

198:         emit ERC20BufferFilled(_asset, _amount);

311:         emit WithdrawRequestClaimed(_withdrawRequest);
```

</details>

### [N-22] Inconsistent floating version pragma

Source files are using different floating version syntax, this is prone to compilation errors, and is not conducive to the code reliability and maintainability.

There are 4 instances:

- *LockboxAdapterBlast.sol* ( [2](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L2) ):

```solidity
2: pragma solidity ^0.8.13;
```

- *XERC20.sol* ( [2](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20.sol#L2) ):

```solidity
2: pragma solidity >=0.8.4 <0.9.0;
```

- *TimelockController.sol* ( [4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L4) ):

```solidity
4: pragma solidity ^0.8.0;
```

- *EzEthToken.sol* ( [2](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/token/EzEthToken.sol#L2) ):

```solidity
2: pragma solidity ^0.8.9;
```

### [N-23] Function state mutability can be restricted to pure

Function state mutability can be restricted to pure

<details>
<summary>There are 5 instances (click to show):</summary>

- *TimelockController.sol* ( [411-416](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L411-L416), [423-429](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L423-L429), [436-442](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L436-L442) ):

```solidity
411:     function onERC721Received(
412:         address,
413:         address,
414:         uint256,
415:         bytes memory
416:     ) public virtual override returns (bytes4) {

423:     function onERC1155Received(
424:         address,
425:         address,
426:         uint256,
427:         uint256,
428:         bytes memory
429:     ) public virtual override returns (bytes4) {

436:     function onERC1155BatchReceived(
437:         address,
438:         address,
439:         uint256[] memory,
440:         uint256[] memory,
441:         bytes memory
442:     ) public virtual override returns (bytes4) {
```

- *EzEthToken.sol* ( [77-77](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/token/EzEthToken.sol#L77-L77), [85-85](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/token/EzEthToken.sol#L85-L85) ):

```solidity
77:     function name() public view virtual override returns (string memory) {

85:     function symbol() public view virtual override returns (string memory) {
```

</details>

### [N-24] Imports could be organized more systematically

The contract's interface should be imported first, followed by each of the interfaces it uses, followed by all other files. The examples below do not follow this layout.

<details>
<summary>There are 20 instances (click to show):</summary>

- *LockboxAdapterBlast.sol* ( [5-5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L5-L5) ):

```solidity
/// @audit Out of order with the prev import️ ⬆
5: import { IERC20 } from "@openzeppelin/contracts/token/ERC20/IERC20.sol";
```

- *xRenzoBridge.sol* ( [7-9](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L7-L9) ):

```solidity
/// @audit Out of order with the prev import️ ⬆
7: import {
8:     IERC20MetadataUpgradeable
9: } from "@openzeppelin/contracts-upgradeable/token/ERC20/extensions/IERC20MetadataUpgradeable.sol";
```

- *xRenzoBridgeStorage.sol* ( [6-6](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridgeStorage.sol#L6-L6) ):

```solidity
/// @audit Out of order with the prev import️ ⬆
6: import "../../IRestakeManager.sol";
```

- *xRenzoDeposit.sol* ( [9-11](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L9-L11), [13-13](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L13-L13), [16-16](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L16-L16) ):

```solidity
/// @audit Out of order with the prev import️ ⬆
9: import {
10:     IERC20MetadataUpgradeable
11: } from "@openzeppelin/contracts-upgradeable/token/ERC20/extensions/IERC20MetadataUpgradeable.sol";

/// @audit Out of order with the prev import️ ⬆
13: import "../xERC20/interfaces/IXERC20.sol";

/// @audit Out of order with the prev import️ ⬆
16: import "../../RateProvider/IRateProvider.sol";
```

- *xRenzoDepositStorage.sol* ( [6-6](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDepositStorage.sol#L6-L6) ):

```solidity
/// @audit Out of order with the prev import️ ⬆
6: import "../Connext/core/IConnext.sol";
```

- *XERC20Lockbox.sol* ( [8-8](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L8-L8) ):

```solidity
/// @audit Out of order with the prev import️ ⬆
8: import { IXERC20Lockbox } from "../interfaces/IXERC20Lockbox.sol";
```

- *OptimismMintableXERC20.sol* ( [8-8](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L8-L8) ):

```solidity
/// @audit Out of order with the prev import️ ⬆
8: import { IOptimismMintableERC20 } from "../../interfaces/IOptimismMintableERC20.sol";
```

- *OperatorDelegator.sol* ( [6-6](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L6-L6), [8-8](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L8-L8) ):

```solidity
/// @audit Out of order with the prev import️ ⬆
6: import "../Permissions/IRoleManager.sol";

/// @audit Out of order with the prev import️ ⬆
8: import "../EigenLayer/interfaces/IDelegationManager.sol";
```

- *RenzoOracle.sol* ( [5-5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L5-L5), [7-7](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L7-L7) ):

```solidity
/// @audit Out of order with the prev import️ ⬆
5: import "../Permissions/IRoleManager.sol";

/// @audit Out of order with the prev import️ ⬆
7: import "./IRenzoOracle.sol";
```

- *RoleManager.sol* ( [5-5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Permissions/RoleManager.sol#L5-L5) ):

```solidity
/// @audit Out of order with the prev import️ ⬆
5: import "./IRoleManager.sol";
```

- *BalancerRateProvider.sol* ( [5-5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RateProvider/BalancerRateProvider.sol#L5-L5) ):

```solidity
/// @audit Out of order with the prev import️ ⬆
5: import "./IRateProvider.sol";
```

- *RestakeManager.sol* ( [8-8](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L8-L8), [12-12](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L12-L12) ):

```solidity
/// @audit Out of order with the prev import️ ⬆
8: import "@openzeppelin/contracts-upgradeable/token/ERC20/IERC20Upgradeable.sol";

/// @audit Out of order with the prev import️ ⬆
12: import "./EigenLayer/interfaces/IStrategy.sol";
```

- *TimelockController.sol* ( [7-7](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L7-L7) ):

```solidity
/// @audit Out of order with the prev import️ ⬆
7: import "@openzeppelin/contracts/token/ERC721/IERC721Receiver.sol";
```

- *WithdrawQueue.sol* ( [9-9](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L9-L9) ):

```solidity
/// @audit Out of order with the prev import️ ⬆
9: import "@openzeppelin/contracts/token/ERC20/IERC20.sol";
```

- *EzEthToken.sol* ( [6-6](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/token/EzEthToken.sol#L6-L6) ):

```solidity
/// @audit Out of order with the prev import️ ⬆
6: import "./IEzEthToken.sol";
```

</details>

### [N-25] There is no need to initialize bool variables with `false`

Since the bool variables are automatically set to `false` when created, it is redundant to initialize it with `false` again.

There are 3 instances:

- *RestakeManager.sol* ( [195-195](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L195-L195), [283-283](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L283-L283), [627-627](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L627-L627) ):

```solidity
195:         bool foundOd = false;

283:         bool withdrawQueueTokenBalanceRecorded = false;

627:         bool found = false;
```

### [N-26] Interfaces should be indicated with an `I` prefix in the contract name

Interfaces should be indicated with an `I` prefix in the contract name

There is 1 instance:

- *LockboxAdapterBlast.sol* ( [17](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L17) ):

```solidity
17: interface L1StandardBridge {
```

### [N-27] Invalid NatSpec comment style

NatSpec comment in solidity should use `///` or `/* ... */` syntax.

There is 1 instance:

- *RenzoOracle.sol* ( [99-100](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L99-L100) ):

```solidity
99: 
100:     // @dev Given list of tokens and balances, return total value (assumes all lookups are denomintated in same underlying currency)
```

### [N-28] @openzeppelin/contracts should be upgraded to a newer version

These contracts import contracts from `@openzeppelin/contracts`, but they are not using [the latest version](https://github.com/OpenZeppelin/openzeppelin-contracts/releases). Using the latest version ensures contract security with fixes for known vulnerabilities, access to the latest feature updates, and enhanced community support and engagement.

The imported version is `^4.9.3`.

<details>
<summary>There are 64 instances (click to show):</summary>

- *LockboxAdapterBlast.sol* ( [4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L4), [5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L5) ):

```solidity
4: import { SafeERC20 } from "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";

5: import { IERC20 } from "@openzeppelin/contracts/token/ERC20/IERC20.sol";
```

- *xRenzoBridge.sol* ( [5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L5), [7](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L7), [14](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L14) ):

```solidity
5: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

7: import {

14: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";
```

- *xRenzoBridgeStorage.sol* ( [5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridgeStorage.sol#L5) ):

```solidity
5: import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";
```

- *RenzoOracleL2.sol* ( [5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L5), [6](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L6) ):

```solidity
5: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

6: import {
```

- *CCIPReceiver.sol* ( [8](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L8), [9](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L9) ):

```solidity
8: import { Ownable } from "@openzeppelin/contracts/access/Ownable.sol";

9: import { Pausable } from "@openzeppelin/contracts/security/Pausable.sol";
```

- *ConnextReceiver.sol* ( [5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L5), [6](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L6) ):

```solidity
5: import { Ownable } from "@openzeppelin/contracts/access/Ownable.sol";

6: import { Pausable } from "@openzeppelin/contracts/security/Pausable.sol";
```

- *xRenzoDeposit.sol* ( [5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L5), [6](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L6), [9](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L9), [15](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L15) ):

```solidity
5: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

6: import {

9: import {

15: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";
```

- *xRenzoDepositStorage.sol* ( [5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDepositStorage.sol#L5) ):

```solidity
5: import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";
```

- *XERC20.sol* ( [5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20.sol#L5), [8](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20.sol#L8), [11](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20.sol#L11), [14](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20.sol#L14) ):

```solidity
5: import {

8: import {

11: import {

14: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";
```

- *XERC20Factory.sol* ( [8](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L8), [11](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L11), [12](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L12) ):

```solidity
8: import {

11: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

12: import "@openzeppelin/contracts/proxy/transparent/TransparentUpgradeableProxy.sol";
```

- *XERC20Lockbox.sol* ( [5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L5), [6](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L6), [7](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L7), [9](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L9) ):

```solidity
5: import { IERC20 } from "@openzeppelin/contracts/token/ERC20/ERC20.sol";

6: import { SafeERC20 } from "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";

7: import { SafeCast } from "@openzeppelin/contracts/utils/math/SafeCast.sol";

9: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";
```

- *OptimismMintableXERC20.sol* ( [4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L4) ):

```solidity
4: import {
```

- *OptimismMintableXERC20Factory.sol* ( [8](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L8), [11](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L11), [12](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L12) ):

```solidity
8: import {

11: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

12: import "@openzeppelin/contracts/proxy/transparent/TransparentUpgradeableProxy.sol";
```

- *OperatorDelegator.sol* ( [4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L4), [5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L5) ):

```solidity
4: import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";

5: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";
```

- *DepositQueue.sol* ( [4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L4), [5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L5), [7](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L7) ):

```solidity
4: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

5: import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";

7: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";
```

- *WBETHShim.sol* ( [4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Binance/WBETHShim.sol#L4), [5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Binance/WBETHShim.sol#L5) ):

```solidity
4: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";

5: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";
```

- *METHShim.sol* ( [4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Mantle/METHShim.sol#L4), [5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Mantle/METHShim.sol#L5) ):

```solidity
4: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";

5: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";
```

- *RenzoOracle.sol* ( [4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L4) ):

```solidity
4: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";
```

- *RenzoOracleStorage.sol* ( [6](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracleStorage.sol#L6) ):

```solidity
6: import "@openzeppelin/contracts/token/ERC20/IERC20.sol";
```

- *RoleManager.sol* ( [4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Permissions/RoleManager.sol#L4) ):

```solidity
4: import "@openzeppelin/contracts-upgradeable/access/AccessControlUpgradeable.sol";
```

- *BalancerRateProvider.sol* ( [4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RateProvider/BalancerRateProvider.sol#L4) ):

```solidity
4: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";
```

- *BalancerRateProviderStorage.sol* ( [4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RateProvider/BalancerRateProviderStorage.sol#L4) ):

```solidity
4: import "@openzeppelin/contracts-upgradeable/token/ERC20/IERC20Upgradeable.sol";
```

- *RestakeManager.sol* ( [4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L4), [5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L5), [6](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L6), [7](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L7), [8](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L8), [9](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L9), [10](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L10) ):

```solidity
4: import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";

5: import "@openzeppelin/contracts-upgradeable/token/ERC20/utils/SafeERC20Upgradeable.sol";

6: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

7: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";

8: import "@openzeppelin/contracts-upgradeable/token/ERC20/IERC20Upgradeable.sol";

9: import "@openzeppelin/contracts/token/ERC20/IERC20.sol";

10: import "@openzeppelin/contracts/token/ERC20/extensions/IERC20Metadata.sol";
```

- *RewardHandler.sol* ( [4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Rewards/RewardHandler.sol#L4), [6](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Rewards/RewardHandler.sol#L6) ):

```solidity
4: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

6: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";
```

- *TimelockController.sol* ( [6](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L6), [7](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L7), [8](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L8) ):

```solidity
6: import "@openzeppelin/contracts/access/AccessControl.sol";

7: import "@openzeppelin/contracts/token/ERC721/IERC721Receiver.sol";

8: import "@openzeppelin/contracts/token/ERC1155/IERC1155Receiver.sol";
```

- *WithdrawQueue.sol* ( [6](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L6), [7](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L7), [8](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L8), [9](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L9) ):

```solidity
6: import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";

7: import "@openzeppelin/contracts-upgradeable/security/PausableUpgradeable.sol";

8: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";

9: import "@openzeppelin/contracts/token/ERC20/IERC20.sol";
```

- *EzEthToken.sol* ( [4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/token/EzEthToken.sol#L4), [5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/token/EzEthToken.sol#L5) ):

```solidity
4: import "@openzeppelin/contracts-upgradeable/token/ERC20/ERC20Upgradeable.sol";

5: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";
```

</details>

### [N-29] Lib @openzeppelin/contracts-upgradeable should be upgraded to a newer version

These contracts import contracts from `@openzeppelin/contracts-upgradeable`, but they are not using [the latest version](https://github.com/OpenZeppelin/openzeppelin-contracts-upgradeable/releases). Using the latest version ensures contract security with fixes for known vulnerabilities, access to the latest feature updates, and enhanced community support and engagement.

The imported version is `^4.9.3`.

<details>
<summary>There are 40 instances (click to show):</summary>

- *xRenzoBridge.sol* ( [5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L5), [7](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L7), [14](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L14) ):

```solidity
5: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

7: import {

14: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";
```

- *RenzoOracleL2.sol* ( [5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L5), [6](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L6) ):

```solidity
5: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

6: import {
```

- *xRenzoDeposit.sol* ( [5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L5), [6](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L6), [9](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L9), [15](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L15) ):

```solidity
5: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

6: import {

9: import {

15: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";
```

- *XERC20.sol* ( [5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20.sol#L5), [8](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20.sol#L8), [11](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20.sol#L11), [14](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20.sol#L14) ):

```solidity
5: import {

8: import {

11: import {

14: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";
```

- *XERC20Factory.sol* ( [8](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L8), [11](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L11) ):

```solidity
8: import {

11: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";
```

- *XERC20Lockbox.sol* ( [9](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L9) ):

```solidity
9: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";
```

- *OptimismMintableXERC20.sol* ( [4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L4) ):

```solidity
4: import {
```

- *OptimismMintableXERC20Factory.sol* ( [8](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L8), [11](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L11) ):

```solidity
8: import {

11: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";
```

- *OperatorDelegator.sol* ( [5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L5) ):

```solidity
5: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";
```

- *DepositQueue.sol* ( [4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L4), [7](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L7) ):

```solidity
4: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

7: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";
```

- *WBETHShim.sol* ( [4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Binance/WBETHShim.sol#L4), [5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Binance/WBETHShim.sol#L5) ):

```solidity
4: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";

5: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";
```

- *METHShim.sol* ( [4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Mantle/METHShim.sol#L4), [5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Mantle/METHShim.sol#L5) ):

```solidity
4: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";

5: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";
```

- *RenzoOracle.sol* ( [4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L4) ):

```solidity
4: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";
```

- *RoleManager.sol* ( [4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Permissions/RoleManager.sol#L4) ):

```solidity
4: import "@openzeppelin/contracts-upgradeable/access/AccessControlUpgradeable.sol";
```

- *BalancerRateProvider.sol* ( [4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RateProvider/BalancerRateProvider.sol#L4) ):

```solidity
4: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";
```

- *BalancerRateProviderStorage.sol* ( [4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RateProvider/BalancerRateProviderStorage.sol#L4) ):

```solidity
4: import "@openzeppelin/contracts-upgradeable/token/ERC20/IERC20Upgradeable.sol";
```

- *RestakeManager.sol* ( [5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L5), [6](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L6), [7](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L7), [8](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L8) ):

```solidity
5: import "@openzeppelin/contracts-upgradeable/token/ERC20/utils/SafeERC20Upgradeable.sol";

6: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

7: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";

8: import "@openzeppelin/contracts-upgradeable/token/ERC20/IERC20Upgradeable.sol";
```

- *RewardHandler.sol* ( [4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Rewards/RewardHandler.sol#L4), [6](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Rewards/RewardHandler.sol#L6) ):

```solidity
4: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

6: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";
```

- *WithdrawQueue.sol* ( [7](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L7), [8](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L8) ):

```solidity
7: import "@openzeppelin/contracts-upgradeable/security/PausableUpgradeable.sol";

8: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";
```

- *EzEthToken.sol* ( [4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/token/EzEthToken.sol#L4), [5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/token/EzEthToken.sol#L5) ):

```solidity
4: import "@openzeppelin/contracts-upgradeable/token/ERC20/ERC20Upgradeable.sol";

5: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";
```

</details>

### [N-30] Expressions for constant values should use `immutable` rather than `constant`

While it doesn't save any gas because the compiler knows that developers often make this mistake, it's still best to use the right tool for the task at hand. There is a difference between `constant` variables and `immutable` variables, and they should each be used in their appropriate contexts. `constants` should be used for literal values written into the code, and `immutable` variables should be used for expressions, or values calculated in, or passed into the constructor.

<details>
<summary>There are 15 instances (click to show):</summary>

- *RoleManagerStorage.sol* ( [11-11](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Permissions/RoleManagerStorage.sol#L11-L11), [14-14](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Permissions/RoleManagerStorage.sol#L14-L14), [17-17](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Permissions/RoleManagerStorage.sol#L17-L17), [20-20](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Permissions/RoleManagerStorage.sol#L20-L20), [23-23](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Permissions/RoleManagerStorage.sol#L23-L23), [26-26](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Permissions/RoleManagerStorage.sol#L26-L26), [29-29](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Permissions/RoleManagerStorage.sol#L29-L29), [32-32](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Permissions/RoleManagerStorage.sol#L32-L32), [39-39](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Permissions/RoleManagerStorage.sol#L39-L39), [42-42](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Permissions/RoleManagerStorage.sol#L42-L42), [47-47](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Permissions/RoleManagerStorage.sol#L47-L47) ):

```solidity
11:     bytes32 public constant RX_ETH_MINTER_BURNER = keccak256("RX_ETH_MINTER_BURNER");

14:     bytes32 public constant OPERATOR_DELEGATOR_ADMIN = keccak256("OPERATOR_DELEGATOR_ADMIN");

17:     bytes32 public constant ORACLE_ADMIN = keccak256("ORACLE_ADMIN");

20:     bytes32 public constant RESTAKE_MANAGER_ADMIN = keccak256("RESTAKE_MANAGER_ADMIN");

23:     bytes32 public constant TOKEN_ADMIN = keccak256("TOKEN_ADMIN");

26:     bytes32 public constant NATIVE_ETH_RESTAKE_ADMIN = keccak256("NATIVE_ETH_RESTAKE_ADMIN");

29:     bytes32 public constant ERC20_REWARD_ADMIN = keccak256("ERC20_REWARD_ADMIN");

32:     bytes32 public constant DEPOSIT_WITHDRAW_PAUSER = keccak256("DEPOSIT_WITHDRAW_PAUSER");

39:     bytes32 public constant BRIDGE_ADMIN = keccak256("BRIDGE_ADMIN");

42:     bytes32 public constant PRICE_FEED_SENDER = keccak256("PRICE_FEED_SENDER");

47:     bytes32 public constant WITHDRAW_QUEUE_ADMIN = keccak256("WITHDRAW_QUEUE_ADMIN");
```

- *TimelockController.sol* ( [26-26](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L26-L26), [27-27](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L27-L27), [28-28](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L28-L28), [29-29](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L29-L29) ):

```solidity
26:     bytes32 public constant TIMELOCK_ADMIN_ROLE = keccak256("TIMELOCK_ADMIN_ROLE");

27:     bytes32 public constant PROPOSER_ROLE = keccak256("PROPOSER_ROLE");

28:     bytes32 public constant EXECUTOR_ROLE = keccak256("EXECUTOR_ROLE");

29:     bytes32 public constant CANCELLER_ROLE = keccak256("CANCELLER_ROLE");
```

</details>

### [N-31] Consider moving duplicated strings to constants

Moving duplicate strings to constants can improve code maintainability and readability.

There are 10 instances:

- *TimelockController.sol* ( [267-267](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L267-L267), [268-268](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L268-L268), [349-349](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L349-L349), [350-350](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L350-L350), [377-377](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L377-L377), [388-388](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L388-L388) ):

```solidity
267:         require(targets.length == values.length, "TimelockController: length mismatch");

268:         require(targets.length == payloads.length, "TimelockController: length mismatch");

349:         require(targets.length == values.length, "TimelockController: length mismatch");

350:         require(targets.length == payloads.length, "TimelockController: length mismatch");

377:         require(isOperationReady(id), "TimelockController: operation is not ready");

388:         require(isOperationReady(id), "TimelockController: operation is not ready");
```

- *EzEthToken.sol* ( [36-36](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/token/EzEthToken.sol#L36-L36), [36-36](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/token/EzEthToken.sol#L36-L36), [78-78](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/token/EzEthToken.sol#L78-L78), [86-86](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/token/EzEthToken.sol#L86-L86) ):

```solidity
36:         __ERC20_init("ezETH", "Renzo Restaked ETH");

36:         __ERC20_init("ezETH", "Renzo Restaked ETH");

78:         return "Renzo Restaked ETH";

86:         return "ezETH";
```

### [N-32] Contracts containing only utility functions should be made into libraries

Consider using a `library` instead of a `contract` to provide utility functions.

There are 3 instances:

- *RoleManagerStorage.sol* ( [9](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Permissions/RoleManagerStorage.sol#L9), [37](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Permissions/RoleManagerStorage.sol#L37), [45](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Permissions/RoleManagerStorage.sol#L45) ):

```solidity
9: contract RoleManagerStorageV1 {

37: contract RoleManagerStorageV2 is RoleManagerStorageV1 {

45: contract RoleManagerStorageV3 is RoleManagerStorageV2 {
```

### [N-33] Error names should use CapWords style

It is recommended by the [Solidity Style Guide](https://docs.soliditylang.org/en/latest/style-guide.html)

There is 1 instance:

- *OptimismMintableXERC20Factory.sol* ( [15](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L15) ):

```solidity
15:     error OptimismMintableXERC20Factory_NoBridges();
```

### [N-34] Contract name does not follow the Solidity Style Guide

According to the [Solidity Style Guide](https://docs.soliditylang.org/en/latest/style-guide.html#contract-and-library-names), contracts and libraries should be named using the CapWords style.

There are 6 instances:

- *xRenzoBridge.sol* ( [16](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L16) ):

```solidity
16: contract xRenzoBridge is
```

- *xRenzoBridgeStorage.sol* ( [18](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridgeStorage.sol#L18) ):

```solidity
18: abstract contract xRenzoBridgeStorageV1 is IxRenzoBridge {
```

- *xRenzoDeposit.sol* ( [27](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L27) ):

```solidity
27: contract xRenzoDeposit is
```

- *xRenzoDepositStorage.sol* ( [9](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDepositStorage.sol#L9), [47](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDepositStorage.sol#L47), [52](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDepositStorage.sol#L52) ):

```solidity
9: abstract contract xRenzoDepositStorageV1 is IxRenzoDeposit {

47: abstract contract xRenzoDepositStorageV2 is xRenzoDepositStorageV1 {

52: abstract contract xRenzoDepositStorageV3 is xRenzoDepositStorageV2 {
```

### [N-35] Functions should be named in mixedCase style

As the [Solidity Style Guide](https://docs.soliditylang.org/en/v0.8.21/style-guide.html#function-names) suggests: functions should be named in mixedCase style.

<details>
<summary>There are 9 instances (click to show):</summary>

- *CCIPReceiver.sol* ( [96](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L96), [107](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L107) ):

```solidity
96:     function updateXRenzoBridgeL1(address _newXRenzoBridgeL1) external onlyOwner {

107:     function updateCCIPEthChainSelector(uint64 _newChainSelector) external onlyOwner {
```

- *ConnextReceiver.sol* ( [92](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L92), [103](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L103) ):

```solidity
92:     function updateXRenzoBridgeL1(address _newXRenzoBridgeL1) external onlyOwner {

103:     function updateCCIPEthChainSelector(uint32 _newChainDomain) external onlyOwner {
```

- *XERC20.sol* ( [76](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20.sol#L76) ):

```solidity
76:     function __XERC20_init(
```

- *WBETHShim.sol* ( [69](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Binance/WBETHShim.sol#L69) ):

```solidity
69:     function _getWBETHData()
```

- *METHShim.sol* ( [69](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Mantle/METHShim.sol#L69) ):

```solidity
69:     function _getMETHData()
```

- *RestakeManager.sol* ( [215](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L215), [274](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L274) ):

```solidity
215:     function setMaxDepositTVL(uint256 _maxDepositTVL) external onlyRestakeManagerAdmin {

274:     function calculateTVLs() public view returns (uint256[][] memory, uint256[] memory, uint256) {
```

</details>

### [N-36] Variable names for `immutable`s should use UPPER_CASE_WITH_UNDERSCORES

For `immutable` variable names, each word should use all capital letters, with underscores separating each word (UPPER_CASE_WITH_UNDERSCORES)

There are 2 instances:

- *LockboxAdapterBlast.sol* ( [31-31](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L31-L31), [32-32](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L32-L32) ):

```solidity
31:     address immutable blastStandardBridge;

32:     address immutable registry;
```

### [N-37] Named imports of parent contracts are missing

Consider adding named imports for all parent contracts.

<details>
<summary>There are 59 instances (click to show):</summary>

- *xRenzoBridge.sol* ( [16-20](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L16-L20) ):

```solidity
/// @audit IXReceiver
/// @audit Initializable
/// @audit ReentrancyGuardUpgradeable
/// @audit xRenzoBridgeStorageV1
16: contract xRenzoBridge is
17:     IXReceiver,
18:     Initializable,
19:     ReentrancyGuardUpgradeable,
20:     xRenzoBridgeStorageV1
```

- *xRenzoBridgeStorage.sol* ( [18-18](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridgeStorage.sol#L18-L18) ):

```solidity
/// @audit IxRenzoBridge
18: abstract contract xRenzoBridgeStorageV1 is IxRenzoBridge {
```

- *RenzoOracleL2.sol* ( [11-11](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L11-L11) ):

```solidity
/// @audit Initializable
/// @audit RenzoOracleL2StorageV1
11: contract RenzoOracleL2 is Initializable, OwnableUpgradeable, RenzoOracleL2StorageV1 {
```

- *RenzoOracleL2Storage.sol* ( [7-7](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/Oracle/RenzoOracleL2Storage.sol#L7-L7) ):

```solidity
/// @audit IRenzoOracleL2
7: abstract contract RenzoOracleL2StorageV1 is IRenzoOracleL2 {
```

- *xRenzoDeposit.sol* ( [27-32](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L27-L32) ):

```solidity
/// @audit Initializable
/// @audit ReentrancyGuardUpgradeable
/// @audit IRateProvider
/// @audit xRenzoDepositStorageV3
27: contract xRenzoDeposit is
28:     Initializable,
29:     OwnableUpgradeable,
30:     ReentrancyGuardUpgradeable,
31:     IRateProvider,
32:     xRenzoDepositStorageV3
```

- *xRenzoDepositStorage.sol* ( [9-9](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDepositStorage.sol#L9-L9) ):

```solidity
/// @audit IxRenzoDeposit
9: abstract contract xRenzoDepositStorageV1 is IxRenzoDeposit {
```

- *XERC20.sol* ( [16-21](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20.sol#L16-L21) ):

```solidity
/// @audit Initializable
16: contract XERC20 is
17:     Initializable,
18:     ERC20Upgradeable,
19:     OwnableUpgradeable,
20:     IXERC20,
21:     ERC20PermitUpgradeable
```

- *XERC20Factory.sol* ( [14-14](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L14-L14) ):

```solidity
/// @audit Initializable
14: contract XERC20Factory is Initializable, IXERC20Factory {
```

- *XERC20Lockbox.sol* ( [11-11](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L11-L11) ):

```solidity
/// @audit Initializable
11: contract XERC20Lockbox is Initializable, IXERC20Lockbox {
```

- *OptimismMintableXERC20Factory.sol* ( [14-14](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L14-L14) ):

```solidity
/// @audit Initializable
14: contract OptimismMintableXERC20Factory is Initializable, XERC20Factory {
```

- *OperatorDelegator.sol* ( [17-20](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L17-L20) ):

```solidity
/// @audit Initializable
/// @audit ReentrancyGuardUpgradeable
/// @audit OperatorDelegatorStorageV4
17: contract OperatorDelegator is
18:     Initializable,
19:     ReentrancyGuardUpgradeable,
20:     OperatorDelegatorStorageV4
```

- *OperatorDelegatorStorage.sol* ( [16-16](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegatorStorage.sol#L16-L16) ):

```solidity
/// @audit IOperatorDelegator
16: abstract contract OperatorDelegatorStorageV1 is IOperatorDelegator {
```

- *DepositQueue.sol* ( [10-10](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L10-L10) ):

```solidity
/// @audit Initializable
/// @audit ReentrancyGuardUpgradeable
/// @audit DepositQueueStorageV2
10: contract DepositQueue is Initializable, ReentrancyGuardUpgradeable, DepositQueueStorageV2 {
```

- *DepositQueueStorage.sol* ( [9-9](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueueStorage.sol#L9-L9) ):

```solidity
/// @audit IDepositQueue
9: abstract contract DepositQueueStorageV1 is IDepositQueue {
```

- *WBETHShim.sol* ( [15-15](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Binance/WBETHShim.sol#L15-L15) ):

```solidity
/// @audit Initializable
/// @audit WBETHShimStorageV1
15: contract WBETHShim is Initializable, WBETHShimStorageV1 {
```

- *WBETHShimStorage.sol* ( [7-7](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Binance/WBETHShimStorage.sol#L7-L7) ):

```solidity
/// @audit AggregatorV3Interface
7: abstract contract WBETHShimStorageV1 is AggregatorV3Interface {
```

- *METHShim.sol* ( [15-15](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Mantle/METHShim.sol#L15-L15) ):

```solidity
/// @audit Initializable
/// @audit METHShimStorageV1
15: contract METHShim is Initializable, METHShimStorageV1 {
```

- *METHShimStorage.sol* ( [7-7](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Mantle/METHShimStorage.sol#L7-L7) ):

```solidity
/// @audit AggregatorV3Interface
7: abstract contract METHShimStorageV1 is AggregatorV3Interface {
```

- *RenzoOracle.sol* ( [13-17](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L13-L17) ):

```solidity
/// @audit IRenzoOracle
/// @audit Initializable
/// @audit ReentrancyGuardUpgradeable
/// @audit RenzoOracleStorageV1
13: contract RenzoOracle is
14:     IRenzoOracle,
15:     Initializable,
16:     ReentrancyGuardUpgradeable,
17:     RenzoOracleStorageV1
```

- *RoleManager.sol* ( [14-14](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Permissions/RoleManager.sol#L14-L14) ):

```solidity
/// @audit IRoleManager
/// @audit AccessControlUpgradeable
/// @audit RoleManagerStorageV3
14: contract RoleManager is IRoleManager, AccessControlUpgradeable, RoleManagerStorageV3 {
```

- *BalancerRateProvider.sol* ( [9-9](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RateProvider/BalancerRateProvider.sol#L9-L9) ):

```solidity
/// @audit Initializable
/// @audit IRateProvider
/// @audit BalancerRateProviderStorageV1
9: contract BalancerRateProvider is Initializable, IRateProvider, BalancerRateProviderStorageV1 {
```

- *RestakeManager.sol* ( [26-26](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L26-L26) ):

```solidity
/// @audit Initializable
/// @audit ReentrancyGuardUpgradeable
/// @audit RestakeManagerStorageV2
26: contract RestakeManager is Initializable, ReentrancyGuardUpgradeable, RestakeManagerStorageV2 {
```

- *RestakeManagerStorage.sol* ( [15-15](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManagerStorage.sol#L15-L15) ):

```solidity
/// @audit IRestakeManager
15: abstract contract RestakeManagerStorageV1 is IRestakeManager {
```

- *RewardHandler.sol* ( [16-16](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Rewards/RewardHandler.sol#L16-L16) ):

```solidity
/// @audit Initializable
/// @audit ReentrancyGuardUpgradeable
/// @audit RewardHandlerStorageV1
16: contract RewardHandler is Initializable, ReentrancyGuardUpgradeable, RewardHandlerStorageV1 {
```

- *TimelockController.sol* ( [25-25](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L25-L25) ):

```solidity
/// @audit AccessControl
/// @audit IERC721Receiver
/// @audit IERC1155Receiver
25: contract TimelockController is AccessControl, IERC721Receiver, IERC1155Receiver {
```

- *WithdrawQueue.sol* ( [11-15](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L11-L15) ):

```solidity
/// @audit Initializable
/// @audit PausableUpgradeable
/// @audit ReentrancyGuardUpgradeable
/// @audit WithdrawQueueStorageV1
11: contract WithdrawQueue is
12:     Initializable,
13:     PausableUpgradeable,
14:     ReentrancyGuardUpgradeable,
15:     WithdrawQueueStorageV1
```

- *EzEthToken.sol* ( [13-13](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/token/EzEthToken.sol#L13-L13) ):

```solidity
/// @audit Initializable
/// @audit ERC20Upgradeable
/// @audit IEzEthToken
/// @audit EzEthTokenStorageV1
13: contract EzEthToken is Initializable, ERC20Upgradeable, IEzEthToken, EzEthTokenStorageV1 {
```

</details>

### [N-38] Constants should be put on the left side of comparisons

Putting constants on the left side of comparison statements is a best practice known as [Yoda conditions](https://en.wikipedia.org/wiki/Yoda_conditions).
Although solidity's static typing system prevents accidental assignments within conditionals, adopting this practice can improve code readability and consistency, especially when working across multiple languages.

<details>
<summary>There are 86 instances (click to show):</summary>

- *LockboxAdapterBlast.sol* ( [41](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L41), [41](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L41), [65](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L65), [73](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L73), [73](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L73) ):

```solidity
/// @audit put `address(0)` on the left
41:         if (_blastStandardBridge == address(0) || _registry == address(0)) {

/// @audit put `address(0)` on the left
41:         if (_blastStandardBridge == address(0) || _registry == address(0)) {

/// @audit put `0` on the left
65:         if (_amount <= 0) {

/// @audit put `address(0)` on the left
73:         if (xerc20 == address(0) || lockbox == address(0)) {

/// @audit put `address(0)` on the left
73:         if (xerc20 == address(0) || lockbox == address(0)) {
```

- *xRenzoBridge.sol* ( [100](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L100), [104](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L104), [108](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L108), [112](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L112), [158](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L158) ):

```solidity
/// @audit put `EXPECTED_DECIMALS` on the left
100:         if (decimals != EXPECTED_DECIMALS) {

/// @audit put `EXPECTED_DECIMALS` on the left
104:         if (decimals != EXPECTED_DECIMALS) {

/// @audit put `EXPECTED_DECIMALS` on the left
108:         if (decimals != EXPECTED_DECIMALS) {

/// @audit put `EXPECTED_DECIMALS` on the left
112:         if (decimals != EXPECTED_DECIMALS) {

/// @audit put `0` on the left
158:         if (_amount == 0) {
```

- *CCIPReceiver.sol* ( [48](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L48), [48](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L48), [97](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L97), [108](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L108), [135](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L135) ):

```solidity
/// @audit put `address(0)` on the left
48:         if (_xRenzoBridgeL1 == address(0) || _ccipEthChainSelector == 0) revert InvalidZeroInput();

/// @audit put `0` on the left
48:         if (_xRenzoBridgeL1 == address(0) || _ccipEthChainSelector == 0) revert InvalidZeroInput();

/// @audit put `address(0)` on the left
97:         if (_newXRenzoBridgeL1 == address(0)) revert InvalidZeroInput();

/// @audit put `0` on the left
108:         if (_newChainSelector == 0) revert InvalidZeroInput();

/// @audit put `address(0)` on the left
135:         if (_newXRenzoDeposit == address(0)) revert InvalidZeroInput();
```

- *ConnextReceiver.sol* ( [53](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L53), [53](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L53), [53](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L53), [93](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L93), [104](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L104), [131](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L131) ):

```solidity
/// @audit put `address(0)` on the left
53:         if (_xRenzoBridgeL1 == address(0) || _connextEthChainDomain == 0 || _connext == address(0))

/// @audit put `address(0)` on the left
53:         if (_xRenzoBridgeL1 == address(0) || _connextEthChainDomain == 0 || _connext == address(0))

/// @audit put `0` on the left
53:         if (_xRenzoBridgeL1 == address(0) || _connextEthChainDomain == 0 || _connext == address(0))

/// @audit put `address(0)` on the left
93:         if (_newXRenzoBridgeL1 == address(0)) revert InvalidZeroInput();

/// @audit put `0` on the left
104:         if (_newChainDomain == 0) revert InvalidZeroInput();

/// @audit put `address(0)` on the left
131:         if (_newXRenzoDeposit == address(0)) revert InvalidZeroInput();
```

- *xRenzoDeposit.sol* ( [92](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L92), [97](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L97), [98](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L98), [99](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L99), [106](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L106), [110](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L110), [114](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L114), [172](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L172), [186](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L186), [209](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L209), [240](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L240), [291](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L291), [332](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L332), [424](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L424) ):

```solidity
/// @audit put `0` on the left
92:             _currentPrice == 0 ||

/// @audit put `0` on the left
97:             _swapKey == 0 ||

/// @audit put `0` on the left
98:             _bridgeDestinationDomain == 0 ||

/// @audit put `address(0)` on the left
99:             _bridgeTargetAddress == address(0)

/// @audit put `EXPECTED_DECIMALS` on the left
106:         if (decimals != EXPECTED_DECIMALS) {

/// @audit put `EXPECTED_DECIMALS` on the left
110:         if (decimals != EXPECTED_DECIMALS) {

/// @audit put `EXPECTED_DECIMALS` on the left
114:         if (decimals != EXPECTED_DECIMALS) {

/// @audit put `0` on the left
172:         if (msg.value == 0) {

/// @audit put `0` on the left
186:         if (wrappedAmount == 0) {

/// @audit put `0` on the left
209:         if (_amountIn == 0) {

/// @audit put `0` on the left
240:         if (amountOut == 0) {

/// @audit put `address(0)` on the left
291:         if (receiver == address(0) && address(oracle) == address(0)) revert PriceFeedNotAvailable();

/// @audit put `0` on the left
332:         if (_price == 0) {

/// @audit put `0` on the left
424:         if (balance == 0) {
```

- *XERC20.sol* ( [330](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20.sol#L330), [350](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20.sol#L350) ):

```solidity
/// @audit put `0` on the left
330:         if (_amount == 0) revert IXERC20_INVALID_0_VALUE();

/// @audit put `0` on the left
350:         if (_amount == 0) revert IXERC20_INVALID_0_VALUE();
```

- *XERC20Factory.sol* ( [111](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L111), [111](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L111), [116](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L116) ):

```solidity
/// @audit put `address(0)` on the left
111:         if ((_baseToken == address(0) && !_isNative) || (_isNative && _baseToken != address(0))) {

/// @audit put `address(0)` on the left
111:         if ((_baseToken == address(0) && !_isNative) || (_isNative && _baseToken != address(0))) {

/// @audit put `address(0)` on the left
116:         if (_lockboxRegistry[_xerc20] != address(0)) revert IXERC20Factory_LockboxAlreadyDeployed();
```

- *OperatorDelegator.sol* ( [135](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L135), [147](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L147), [329](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L329), [514](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L514) ):

```solidity
/// @audit put `0` on the left
135:         if (_baseGasAmountSpent == 0) revert InvalidZeroInput();

/// @audit put `0` on the left
147:         if (address(tokenStrategyMapping[token]) == address(0x0) || tokenAmount == 0)

/// @audit put `0` on the left
329:             queuedShares[address(this)] == 0

/// @audit put `0` on the left
514:                 if (remainingAmount == 0) {
```

- *DepositQueue.sol* ( [99](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L99), [138](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L138), [138](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L138), [166](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L166), [260](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L260) ):

```solidity
/// @audit put `address(0x0)` on the left
99:             if (_feeAddress == address(0x0)) revert InvalidZeroInput();

/// @audit put `0` on the left
138:         if (_amount == 0 || _asset == address(0)) revert InvalidZeroInput();

/// @audit put `address(0)` on the left
138:         if (_amount == 0 || _asset == address(0)) revert InvalidZeroInput();

/// @audit put `address(0x0)` on the left
166:         if (feeAddress != address(0x0) && feeBasisPoints > 0) {

/// @audit put `address(0x0)` on the left
260:             if (feeAddress != address(0x0) && feeBasisPoints > 0) {
```

- *RenzoOracle.sol* ( [77](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L77), [94](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L94), [130](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L130), [130](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L130), [146](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L146), [161](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L161) ):

```solidity
/// @audit put `0` on the left
77:         if (price <= 0) revert InvalidOraclePrice();

/// @audit put `0` on the left
94:         if (price <= 0) revert InvalidOraclePrice();

/// @audit put `0` on the left
130:         if (_currentValueInProtocol == 0 || _existingEzETHSupply == 0) {

/// @audit put `0` on the left
130:         if (_currentValueInProtocol == 0 || _existingEzETHSupply == 0) {

/// @audit put `0` on the left
146:         if (mintAmount == 0) revert InvalidTokenAmount();

/// @audit put `0` on the left
161:         if (redeemAmount == 0) revert InvalidTokenAmount();
```

- *BalancerRateProvider.sol* ( [37](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RateProvider/BalancerRateProvider.sol#L37), [37](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RateProvider/BalancerRateProvider.sol#L37) ):

```solidity
/// @audit put `0` on the left
37:         if (totalSupply == 0 || totalTVL == 0) revert InvalidZeroInput();

/// @audit put `0` on the left
37:         if (totalSupply == 0 || totalTVL == 0) revert InvalidZeroInput();
```

- *RestakeManager.sol* ( [367](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L367), [370](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L370), [408](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L408), [510](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L510), [515](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L515), [597](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L597) ):

```solidity
/// @audit put `0` on the left
367:         if (operatorDelegators.length == 0) revert NotFound();

/// @audit put `1` on the left
370:         if (operatorDelegators.length == 1) {

/// @audit put `1` on the left
408:         if (operatorDelegators.length == 1) {

/// @audit put `0` on the left
510:         if (maxDepositTVL != 0 && totalTVL + collateralTokenValue > maxDepositTVL) {

/// @audit put `0` on the left
515:         if (collateralTokenTvlLimits[_collateralToken] != 0) {

/// @audit put `0` on the left
597:         if (maxDepositTVL != 0 && totalTVL + msg.value > maxDepositTVL) {
```

- *RewardHandler.sol* ( [64](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Rewards/RewardHandler.sol#L64) ):

```solidity
/// @audit put `0` on the left
64:         if (balance == 0) {
```

- *TimelockController.sol* ( [102](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L102), [245](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L245), [275](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L275), [379](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L379) ):

```solidity
/// @audit put `address(0)` on the left
102:         if (admin != address(0)) {

/// @audit put `bytes32(0)` on the left
245:         if (salt != bytes32(0)) {

/// @audit put `bytes32(0)` on the left
275:         if (salt != bytes32(0)) {

/// @audit put `bytes32(0)` on the left
379:             predecessor == bytes32(0) || isOperationDone(predecessor),
```

- *WithdrawQueue.sol* ( [77](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L77), [78](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L78), [90](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L90), [91](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L91), [109](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L109), [111](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L111), [111](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L111), [130](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L130), [157](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L157), [196](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L196), [196](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L196), [208](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L208), [208](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L208), [211](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L211), [227](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L227), [302](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L302) ):

```solidity
/// @audit put `0` on the left
77:             _withdrawalBufferTarget.length == 0 ||

/// @audit put `0` on the left
78:             _coolDownPeriod == 0

/// @audit put `address(0)` on the left
90:                 _withdrawalBufferTarget[i].asset == address(0) ||

/// @audit put `0` on the left
91:                 _withdrawalBufferTarget[i].bufferAmount == 0

/// @audit put `0` on the left
109:         if (_newBufferTarget.length == 0) revert InvalidZeroInput();

/// @audit put `address(0)` on the left
111:             if (_newBufferTarget[i].asset == address(0) || _newBufferTarget[i].bufferAmount == 0)

/// @audit put `0` on the left
111:             if (_newBufferTarget[i].asset == address(0) || _newBufferTarget[i].bufferAmount == 0)

/// @audit put `0` on the left
130:         if (_newCoolDownPeriod == 0) revert InvalidZeroInput();

/// @audit put `IS_NATIVE` on the left
157:         if (_asset != IS_NATIVE) {

/// @audit put `address(0)` on the left
196:         if (_asset == address(0) || _amount == 0) revert InvalidZeroInput();

/// @audit put `0` on the left
196:         if (_asset == address(0) || _amount == 0) revert InvalidZeroInput();

/// @audit put `0` on the left
208:         if (_amount == 0 || _assetOut == address(0)) revert InvalidZeroInput();

/// @audit put `address(0)` on the left
208:         if (_amount == 0 || _assetOut == address(0)) revert InvalidZeroInput();

/// @audit put `0` on the left
211:         if (withdrawalBufferTarget[_assetOut] == 0) revert UnsupportedWithdrawAsset();

/// @audit put `IS_NATIVE` on the left
227:         if (_assetOut != IS_NATIVE) {

/// @audit put `IS_NATIVE` on the left
302:         if (_withdrawRequest.collateralToken == IS_NATIVE) {
```

- *EzEthToken.sol* ( [69](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/token/EzEthToken.sol#L69), [69](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/token/EzEthToken.sol#L69) ):

```solidity
/// @audit put `address(0)` on the left
69:         if (from != address(0) && to != address(0)) {

/// @audit put `address(0)` on the left
69:         if (from != address(0) && to != address(0)) {
```

</details>

### [N-39] `else`-block not required

One level of nesting can be removed by not having an `else` block when the `if`-block always jumps at the end. For example:
```solidity
if (condition) {
    body1...
    return x;
} else {
    body2...
}
```
can be changed to:
```solidity
if (condition) {
    body1...
    return x;
}
body2...
```

<details>
<summary>There are 4 instances (click to show):</summary>

- *xRenzoDeposit.sol* ( [279-281](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L279-L281), [292-298](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L292-L298) ):

```solidity
279:         if (_amountIn < sweepBatchSize) {
280:             return (_amountIn * bridgeFeeShare) / FEE_BASIS;
281:         } else {

292:         if (address(oracle) != address(0)) {
293:             (uint256 oraclePrice, uint256 oracleTimestamp) = oracle.getMintRate();
294:             return
295:                 oracleTimestamp > lastPriceTimestamp
296:                     ? (oraclePrice, oracleTimestamp)
297:                     : (lastPrice, lastPriceTimestamp);
298:         } else {
```

- *XERC20.sol* ( [309-311](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20.sol#L309-L311) ):

```solidity
309:         if (_limit == _maxLimit) {
310:             return _limit;
311:         } else if (_timestamp + _DURATION <= block.timestamp) {
```

- *WithdrawQueue.sol* ( [157-159](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L157-L159) ):

```solidity
157:         if (_asset != IS_NATIVE) {
158:             return IERC20(_asset).balanceOf(address(this)) - claimReserve[_asset];
159:         } else {
```

</details>

### [N-40] Large multiples of ten should use scientific notation

Use a scientific notation rather than decimal literals (e.g. `1e6` instead of `1000000`), for better code readability.

There are 6 instances:

- *xRenzoBridge.sol* ( [225-225](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L225-L225) ):

```solidity
/// @audit 200_000 -> 2e5
225:                     Client.EVMExtraArgsV1({ gasLimit: 200_000 })
```

- *xRenzoDeposit.sol* ( [40-40](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L40-L40), [386-386](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L386-L386) ):

```solidity
/// @audit 10000 -> 1e4
40:     uint32 public constant FEE_BASIS = 10000;

/// @audit 10_000 -> 1e4
386:             uint256 fee = (amountNextWETH * bridgeRouterFeeBps) / 10_000;
```

- *DepositQueue.sol* ( [103-103](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L103-L103), [167-167](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L167-L167), [261-261](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L261-L261) ):

```solidity
/// @audit 10000 -> 1e4
103:         if (_feeBasisPoints > 10000) revert OverMaxBasisPoints();

/// @audit 10000 -> 1e4
167:             feeAmount = (msg.value * feeBasisPoints) / 10000;

/// @audit 10000 -> 1e4
261:                 feeAmount = (balance * feeBasisPoints) / 10000;
```

### [N-41] High cyclomatic complexity

Consider breaking down these blocks into more manageable units, by splitting things into utility functions, by reducing nesting, and by using early returns.

<details>
<summary>There is 1 instance (click to show):</summary>

- *RestakeManager.sol* ( [400-447](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L400-L447) ):

```solidity
400:     function chooseOperatorDelegatorForWithdraw(
401:         uint256 tokenIndex,
402:         uint256 ezETHValue,
403:         uint256[][] memory operatorDelegatorTokenTVLs,
404:         uint256[] memory operatorDelegatorTVLs,
405:         uint256 totalTVL
406:     ) public view returns (IOperatorDelegator) {
407:         // If there is only one operator delegator, try to use it
408:         if (operatorDelegators.length == 1) {
409:             // If the OD doesn't have the tokens, revert
410:             if (operatorDelegatorTokenTVLs[0][tokenIndex] < ezETHValue) {
411:                 revert NotFound();
412:             }
413:             return operatorDelegators[0];
414:         }
415: 
416:         // Fnd the operator delegator with TVL above the threshold and with enough tokens
417:         uint256 odLength = operatorDelegatorTVLs.length;
418:         for (uint256 i = 0; i < odLength; ) {
419:             if (
420:                 operatorDelegatorTVLs[i] >
421:                 (operatorDelegatorAllocations[operatorDelegators[i]] * totalTVL) /
422:                     BASIS_POINTS /
423:                     BASIS_POINTS &&
424:                 operatorDelegatorTokenTVLs[i][tokenIndex] >= ezETHValue
425:             ) {
426:                 return operatorDelegators[i];
427:             }
428: 
429:             unchecked {
430:                 ++i;
431:             }
432:         }
433: 
434:         // If not found, just find one with enough tokens
435:         for (uint256 i = 0; i < odLength; ) {
436:             if (operatorDelegatorTokenTVLs[i][tokenIndex] >= ezETHValue) {
437:                 return operatorDelegators[i];
438:             }
439: 
440:             unchecked {
441:                 ++i;
442:             }
443:         }
444: 
445:         // This token cannot be withdrawn
446:         revert NotFound();
447:     }
```

</details>

### [N-42] Typos

All typos should be corrected.

<details>
<summary>There are 19 instances (click to show):</summary>

- *xRenzoBridge.sol* ( [171](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L171) ):

```solidity
/// @audit amonut
171:         // Get the amonut of ezETH before the deposit
```

- *RenzoOracleL2.sol* ( [12](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L12) ):

```solidity
/// @audit maxmimum
12:     /// @dev The maxmimum staleness allowed for a price feed from chainlink
```

- *CCIPReceiver.sol* ( [93](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L93), [104](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L104), [131](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L131) ):

```solidity
/// @audit Onwer
93:      * @dev This should be a permissioned call (onlyOnwer)

/// @audit Onwer
104:      * @dev This should be a permissioned call (onlyOnwer)

/// @audit Onwer
131:      * @dev This should be a permissioned call (onlyOnwer)
```

- *ConnextReceiver.sol* ( [89](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L89), [100](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L100), [127](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L127) ):

```solidity
/// @audit Onwer
89:      * @dev This should be a permissioned call (onlyOnwer)

/// @audit Onwer
100:      * @dev This should be a permissioned call (onlyOnwer)

/// @audit Onwer
127:      * @dev This should be a permissioned call (onlyOnwer)
```

- *xRenzoDeposit.sol* ( [160](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L160), [195](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L195), [508](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L508), [518](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L518) ):

```solidity
/// @audit funcion
160:      * @dev     This funcion allows anyone to call and deposit the native asset for xezETH

/// @audit funcion
195:      * @dev     This funcion allows anyone to call and deposit collateral for xezETH

/// @audit Onwer
508:      * @dev This should be permissioned call (onlyOnwer), can be set to address(0) for not configured

/// @audit Onwer
518:      * @dev This should be a permissioned call (onlyOnwer)
```

- *OperatorDelegator.sol* ( [202](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L202) ):

```solidity
/// @audit legth
202:         // set strategies legth for 0th index only
```

- *DepositQueue.sol* ( [150](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L150) ):

```solidity
/// @audit bufffer
150:      * @dev     check and fill ETH withdraw bufffer if required
```

- *Errors.sol* ( [46](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Errors/Errors.sol#L46) ):

```solidity
/// @audit Errror
46: /// @dev Errror when caller does not have ETH Restake Admin role
```

- *RenzoOracle.sol* ( [25](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L25) ):

```solidity
/// @audit maxmimum
25:     /// @dev The maxmimum staleness allowed for a price feed from chainlink
```

- *RoleManager.sol* ( [42](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Permissions/RoleManager.sol#L42) ):

```solidity
/// @audit Delgator
42:     /// @dev Determines if the specified address has permission to update config on the OperatorDelgator Contracts
```

- *RoleManagerStorage.sol* ( [13](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Permissions/RoleManagerStorage.sol#L13) ):

```solidity
/// @audit Delgator
13:     /// @dev role for granting capability to update config on the OperatorDelgator Contracts
```

- *RestakeManager.sol* ( [194](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L194) ):

```solidity
/// @audit mis
194:         // Ensure the OD is in the list to prevent mis-configuration
```

</details>

### [N-43] Consider bounding input array length

The functions below take in an unbounded array, and make function calls for entries in the array. While the function will revert if it eventually runs out of gas, it may be a nicer user experience to require() that the length of the array is below some reasonable maximum, so that the user doesn't have to use up a full transaction's gas only to see that the transaction reverts.

<details>
<summary>There are 18 instances (click to show):</summary>

- *xRenzoBridge.sol* ( [218](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L218), [264](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L264) ):

```solidity
218:         for (uint256 i = 0; i < _destinationParam.length; ) {

264:         for (uint256 i = 0; i < _connextDestinationParam.length; ) {
```

- *XERC20Factory.sol* ( [167](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L167) ):

```solidity
167:         for (uint256 _i; _i < _bridgesLength; ++_i) {
```

- *OptimismMintableXERC20Factory.sol* ( [109](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L109) ):

```solidity
109:         for (uint256 _i; _i < _bridgesLength; ++_i) {
```

- *OperatorDelegator.sol* ( [209](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L209), [277](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L277), [381](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L381) ):

```solidity
209:         for (uint256 i; i < tokens.length; ) {

277:         for (uint256 i; i < tokens.length; ) {

381:         for (uint256 i = 0; i < validatorFields.length; ) {
```

- *DepositQueue.sol* ( [227](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L227) ):

```solidity
227:         for (uint256 i = 0; i < arrayLength; ) {
```

- *RenzoOracle.sol* ( [111](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L111) ):

```solidity
111:         for (uint256 i = 0; i < tokenLength; ) {
```

- *RestakeManager.sol* ( [376](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L376), [418](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L418), [435](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L435) ):

```solidity
376:         for (uint256 i = 0; i < tvlLength; ) {

418:         for (uint256 i = 0; i < odLength; ) {

435:         for (uint256 i = 0; i < odLength; ) {
```

- *TimelockController.sol* ( [107](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L107), [113](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L113), [272](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L272), [355](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L355) ):

```solidity
107:         for (uint256 i = 0; i < proposers.length; ++i) {

113:         for (uint256 i = 0; i < executors.length; ++i) {

272:         for (uint256 i = 0; i < targets.length; ++i) {

355:         for (uint256 i = 0; i < targets.length; ++i) {
```

- *WithdrawQueue.sol* ( [88](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L88), [110](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L110) ):

```solidity
88:         for (uint256 i = 0; i < _withdrawalBufferTarget.length; ) {

110:         for (uint256 i = 0; i < _newBufferTarget.length; ) {
```

</details>

### [N-44] Unnecessary casting

Unnecessary castings can be removed.

<details>
<summary>There are 8 instances (click to show):</summary>

- *OperatorDelegator.sol* ( [122-122](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L122-L122), [123-123](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L123-L123) ):

```solidity
/// @audit address(_delegateAddress)
122:         if (address(_delegateAddress) == address(0x0)) revert InvalidZeroInput();

/// @audit address(delegateAddress)
123:         if (address(delegateAddress) != address(0x0)) revert DelegateAddressAlreadySet();
```

- *DepositQueue.sol* ( [255-255](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L255-L255), [262-262](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L262-L262) ):

```solidity
/// @audit IERC20(token)
255:         uint256 balance = IERC20(token).balanceOf(address(this));

/// @audit IERC20(token)
262:                 IERC20(token).safeTransfer(feeAddress, feeAmount);
```

- *RoleManager.sol* ( [23-23](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Permissions/RoleManager.sol#L23-L23) ):

```solidity
/// @audit address(roleManagerAdmin)
23:         if (address(roleManagerAdmin) == address(0x0)) revert InvalidZeroInput();
```

- *RestakeManager.sol* ( [355-355](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L355-L355) ):

```solidity
/// @audit address(withdrawQueue)
355:         totalTVL += (address(withdrawQueue).balance + totalWithdrawalQueueValue);
```

- *RewardHandler.sol* ( [42-42](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Rewards/RewardHandler.sol#L42-L42), [75-75](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Rewards/RewardHandler.sol#L75-L75) ):

```solidity
/// @audit address(_rewardDestination)
42:         if (address(_rewardDestination) == address(0x0)) revert InvalidZeroInput();

/// @audit address(_rewardDestination)
75:         if (address(_rewardDestination) == address(0x0)) revert InvalidZeroInput();
```

</details>

### [N-45] Unused contract variables

The following state variables are defined but not used.
It is recommended to check the code for logical omissions that cause them not to be used. If it's determined that they are not needed anywhere, it's best to remove them from the codebase to improve code clarity and minimize confusion.

There is 1 instance:

- *RenzoOracle.sol* ( [20-20](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L20-L20) ):

```solidity
20:     string constant INVALID_0_INPUT = "Invalid 0 input";
```

### [N-46] Unused import

The identifier is imported but never used within the file.

<details>
<summary>There are 25 instances (click to show):</summary>

- *LockboxAdapterBlast.sol* ( [6-6](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L6-L6) ):

```solidity
/// @audit IXERC20
6: import { IXERC20 } from "../../xERC20/interfaces/IXERC20.sol";
```

- *xRenzoBridgeStorage.sol* ( [9-11](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridgeStorage.sol#L9-L11), [12-12](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridgeStorage.sol#L12-L12), [13-15](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridgeStorage.sol#L13-L15), [16-16](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridgeStorage.sol#L16-L16) ):

```solidity
/// @audit IRouterClient
9: import {
10:     IRouterClient
11: } from "@chainlink/contracts-ccip/src/v0.8/ccip/interfaces/IRouterClient.sol";

/// @audit IRateProvider
12: import { IRateProvider } from "../../RateProvider/IRateProvider.sol";

/// @audit LinkTokenInterface
13: import {
14:     LinkTokenInterface
15: } from "@chainlink/contracts/src/v0.8/shared/interfaces/LinkTokenInterface.sol";

/// @audit IRoleManager
16: import { IRoleManager } from "../../Permissions/IRoleManager.sol";
```

- *RenzoOracleL2.sol* ( [6-8](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L6-L8) ):

```solidity
/// @audit OwnableUpgradeable
6: import {
7:     OwnableUpgradeable
8: } from "@openzeppelin/contracts-upgradeable/access/OwnableUpgradeable.sol";
```

- *CCIPReceiver.sol* ( [4-4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L4-L4), [5-7](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L5-L7), [8-8](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L8-L8), [9-9](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L9-L9) ):

```solidity
/// @audit Client
4: import { Client } from "@chainlink/contracts-ccip/src/v0.8/ccip/libraries/Client.sol";

/// @audit CCIPReceiver
5: import {
6:     CCIPReceiver
7: } from "@chainlink/contracts-ccip/src/v0.8/ccip/applications/CCIPReceiver.sol";

/// @audit Ownable
8: import { Ownable } from "@openzeppelin/contracts/access/Ownable.sol";

/// @audit Pausable
9: import { Pausable } from "@openzeppelin/contracts/security/Pausable.sol";
```

- *ConnextReceiver.sol* ( [4-4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L4-L4), [5-5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L5-L5), [6-6](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L6-L6) ):

```solidity
/// @audit IXReceiver
4: import { IXReceiver } from "@connext/interfaces/core/IXReceiver.sol";

/// @audit Ownable
5: import { Ownable } from "@openzeppelin/contracts/access/Ownable.sol";

/// @audit Pausable
6: import { Pausable } from "@openzeppelin/contracts/security/Pausable.sol";
```

- *xRenzoDeposit.sol* ( [6-8](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L6-L8) ):

```solidity
/// @audit OwnableUpgradeable
6: import {
7:     OwnableUpgradeable
8: } from "@openzeppelin/contracts-upgradeable/access/OwnableUpgradeable.sol";
```

- *XERC20.sol* ( [4-4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20.sol#L4-L4), [5-7](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20.sol#L5-L7), [8-10](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20.sol#L8-L10), [11-13](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20.sol#L11-L13) ):

```solidity
/// @audit IXERC20
4: import { IXERC20 } from "../interfaces/IXERC20.sol";

/// @audit ERC20Upgradeable
5: import {
6:     ERC20Upgradeable
7: } from "@openzeppelin/contracts-upgradeable/token/ERC20/ERC20Upgradeable.sol";

/// @audit ERC20PermitUpgradeable
8: import {
9:     ERC20PermitUpgradeable
10: } from "@openzeppelin/contracts-upgradeable/token/ERC20/extensions/ERC20PermitUpgradeable.sol";

/// @audit OwnableUpgradeable
11: import {
12:     OwnableUpgradeable
13: } from "@openzeppelin/contracts-upgradeable/access/OwnableUpgradeable.sol";
```

- *XERC20Factory.sol* ( [4-4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L4-L4) ):

```solidity
/// @audit IXERC20Factory
4: import { IXERC20Factory } from "../interfaces/IXERC20Factory.sol";
```

- *XERC20Lockbox.sol* ( [6-6](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L6-L6), [7-7](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L7-L7), [8-8](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L8-L8) ):

```solidity
/// @audit SafeERC20
6: import { SafeERC20 } from "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";

/// @audit SafeCast
7: import { SafeCast } from "@openzeppelin/contracts/utils/math/SafeCast.sol";

/// @audit IXERC20Lockbox
8: import { IXERC20Lockbox } from "../interfaces/IXERC20Lockbox.sol";
```

- *OptimismMintableXERC20.sol* ( [4-6](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L4-L6) ):

```solidity
/// @audit ERC165Upgradeable
4: import {
5:     ERC165Upgradeable
6: } from "@openzeppelin/contracts-upgradeable/utils/introspection/ERC165Upgradeable.sol";
```

- *OptimismMintableXERC20Factory.sol* ( [5-5](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L5-L5), [6-6](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L6-L6) ):

```solidity
/// @audit XERC20Factory
5: import { XERC20Factory } from "../XERC20Factory.sol";

/// @audit XERC20Lockbox
6: import { XERC20Lockbox } from "../XERC20Lockbox.sol";
```

</details>

### [N-47] Unused modifiers

The following `modifier`s are not used. It is recommended to check the code for logical omissions that cause them not to be used. If it's determined that they are not needed anywhere, it's best to remove them from the codebase to improve code clarity and minimize confusion.

There is 1 instance:

- *WithdrawQueue.sol* ( [45](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L45) ):

```solidity
45:     modifier onlyRestakeManager() {
```

### [N-48] Unused named return

Declaring named returns, but not using them, is confusing to the reader. Consider either completely removing them (by declaring just the type without a name), or remove the return statement and do a variable assignment. This would improve the readability of the code, and it may also help reduce regressions during future code refactors.

<details>
<summary>There are 22 instances (click to show):</summary>

- *OperatorDelegator.sol* ( [143-146](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L143-L146), [162-162](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L162-L162) ):

```solidity
/// @audit shares
143:     function deposit(
144:         IERC20 token,
145:         uint256 tokenAmount
146:     ) external nonReentrant onlyRestakeManager returns (uint256 shares) {

/// @audit shares
162:     function _deposit(IERC20 _token, uint256 _tokenAmount) internal returns (uint256 shares) {
```

- *WBETHShim.sol* ( [46-55](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Binance/WBETHShim.sol#L46-L55), [69-78](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Binance/WBETHShim.sol#L69-L78) ):

```solidity
/// @audit roundId
/// @audit answer
/// @audit startedAt
/// @audit updatedAt
/// @audit answeredInRound
46:     function latestRoundData()
47:         external
48:         view
49:         returns (
50:             uint80 roundId,
51:             int256 answer,
52:             uint256 startedAt,
53:             uint256 updatedAt,
54:             uint80 answeredInRound
55:         )

/// @audit roundId
/// @audit answer
/// @audit startedAt
/// @audit updatedAt
/// @audit answeredInRound
69:     function _getWBETHData()
70:         internal
71:         view
72:         returns (
73:             uint80 roundId,
74:             int256 answer,
75:             uint256 startedAt,
76:             uint256 updatedAt,
77:             uint80 answeredInRound
78:         )
```

- *METHShim.sol* ( [46-55](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Mantle/METHShim.sol#L46-L55), [69-78](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Mantle/METHShim.sol#L69-L78) ):

```solidity
/// @audit roundId
/// @audit answer
/// @audit startedAt
/// @audit updatedAt
/// @audit answeredInRound
46:     function latestRoundData()
47:         external
48:         view
49:         returns (
50:             uint80 roundId,
51:             int256 answer,
52:             uint256 startedAt,
53:             uint256 updatedAt,
54:             uint80 answeredInRound
55:         )

/// @audit roundId
/// @audit answer
/// @audit startedAt
/// @audit updatedAt
/// @audit answeredInRound
69:     function _getMETHData()
70:         internal
71:         view
72:         returns (
73:             uint80 roundId,
74:             int256 answer,
75:             uint256 startedAt,
76:             uint256 updatedAt,
77:             uint80 answeredInRound
78:         )
```

</details>

### [N-49] Use delete instead of assigning values to `false`

The `delete` keyword more closely matches the semantics of what is being done, and draws more attention to the changing of state, which may lead to a more thorough audit of its associated logic.

There is 1 instance:

- *RestakeManager.sol* ( [117-117](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L117-L117) ):

```solidity
117:         paused = false;
```

### [N-50] Consider using `delete` rather than assigning zero to clear values

The `delete` keyword more closely matches the semantics of what is being done, and draws more attention to the changing of state, which may lead to a more thorough audit of its associated logic.

There are 2 instances:

- *xRenzoDeposit.sol* ( [398-398](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L398-L398) ):

```solidity
398:         bridgeFeeCollected = 0;
```

- *RestakeManager.sol* ( [168-168](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L168-L168) ):

```solidity
168:                 operatorDelegatorAllocations[_operatorDelegatorToRemove] = 0;
```

### [N-51] Use the latest Solidity version

Upgrading to the [latest solidity version](https://github.com/ethereum/solc-js/tags) (0.8.19 for L2s) can optimize gas usage, take advantage of new features and improve overall contract efficiency. Where possible, based on compatibility requirements, it is recommended to use newer/latest solidity version to take advantage of the latest optimizations and features.

<details>
<summary>There are 38 instances (click to show):</summary>

- *LockboxAdapterBlast.sol* ( [2](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L2) ):

```solidity
2: pragma solidity ^0.8.13;
```

- *xRenzoBridge.sol* ( [2](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L2) ):

```solidity
2: pragma solidity 0.8.19;
```

- *xRenzoBridgeStorage.sol* ( [2](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridgeStorage.sol#L2) ):

```solidity
2: pragma solidity 0.8.19;
```

- *RenzoOracleL2.sol* ( [2](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L2) ):

```solidity
2: pragma solidity 0.8.19;
```

- *RenzoOracleL2Storage.sol* ( [2](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/Oracle/RenzoOracleL2Storage.sol#L2) ):

```solidity
2: pragma solidity 0.8.19;
```

- *CCIPReceiver.sol* ( [2](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L2) ):

```solidity
2: pragma solidity 0.8.19;
```

- *ConnextReceiver.sol* ( [2](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L2) ):

```solidity
2: pragma solidity 0.8.19;
```

- *xRenzoDeposit.sol* ( [2](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L2) ):

```solidity
2: pragma solidity 0.8.19;
```

- *xRenzoDepositStorage.sol* ( [2](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDepositStorage.sol#L2) ):

```solidity
2: pragma solidity 0.8.19;
```

- *XERC20.sol* ( [2](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20.sol#L2) ):

```solidity
2: pragma solidity >=0.8.4 <0.9.0;
```

- *XERC20Factory.sol* ( [2](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L2) ):

```solidity
2: pragma solidity >=0.8.4 <0.9.0;
```

- *XERC20Lockbox.sol* ( [2](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L2) ):

```solidity
2: pragma solidity >=0.8.4 <0.9.0;
```

- *OptimismMintableXERC20.sol* ( [2](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L2) ):

```solidity
2: pragma solidity >=0.8.4 <0.9.0;
```

- *OptimismMintableXERC20Factory.sol* ( [2](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L2) ):

```solidity
2: pragma solidity >=0.8.4 <0.9.0;
```

- *OperatorDelegator.sol* ( [2](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L2) ):

```solidity
2: pragma solidity 0.8.19;
```

- *OperatorDelegatorStorage.sol* ( [2](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegatorStorage.sol#L2) ):

```solidity
2: pragma solidity 0.8.19;
```

- *DepositQueue.sol* ( [2](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L2) ):

```solidity
2: pragma solidity 0.8.19;
```

- *DepositQueueStorage.sol* ( [2](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueueStorage.sol#L2) ):

```solidity
2: pragma solidity 0.8.19;
```

- *Errors.sol* ( [2](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Errors/Errors.sol#L2) ):

```solidity
2: pragma solidity 0.8.19;
```

- *WBETHShim.sol* ( [2](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Binance/WBETHShim.sol#L2) ):

```solidity
2: pragma solidity 0.8.19;
```

- *WBETHShimStorage.sol* ( [2](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Binance/WBETHShimStorage.sol#L2) ):

```solidity
2: pragma solidity 0.8.19;
```

- *METHShim.sol* ( [2](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Mantle/METHShim.sol#L2) ):

```solidity
2: pragma solidity 0.8.19;
```

- *METHShimStorage.sol* ( [2](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Mantle/METHShimStorage.sol#L2) ):

```solidity
2: pragma solidity 0.8.19;
```

- *RenzoOracle.sol* ( [2](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L2) ):

```solidity
2: pragma solidity 0.8.19;
```

- *RenzoOracleStorage.sol* ( [2](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracleStorage.sol#L2) ):

```solidity
2: pragma solidity 0.8.19;
```

- *RoleManager.sol* ( [2](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Permissions/RoleManager.sol#L2) ):

```solidity
2: pragma solidity 0.8.19;
```

- *RoleManagerStorage.sol* ( [2](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Permissions/RoleManagerStorage.sol#L2) ):

```solidity
2: pragma solidity 0.8.19;
```

- *BalancerRateProvider.sol* ( [2](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RateProvider/BalancerRateProvider.sol#L2) ):

```solidity
2: pragma solidity 0.8.19;
```

- *BalancerRateProviderStorage.sol* ( [2](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RateProvider/BalancerRateProviderStorage.sol#L2) ):

```solidity
2: pragma solidity 0.8.19;
```

- *RestakeManager.sol* ( [2](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L2) ):

```solidity
2: pragma solidity 0.8.19;
```

- *RestakeManagerStorage.sol* ( [2](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManagerStorage.sol#L2) ):

```solidity
2: pragma solidity 0.8.19;
```

- *RewardHandler.sol* ( [2](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Rewards/RewardHandler.sol#L2) ):

```solidity
2: pragma solidity 0.8.19;
```

- *RewardHandlerStorage.sol* ( [2](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Rewards/RewardHandlerStorage.sol#L2) ):

```solidity
2: pragma solidity 0.8.19;
```

- *TimelockController.sol* ( [4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L4) ):

```solidity
4: pragma solidity ^0.8.0;
```

- *WithdrawQueue.sol* ( [2](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L2) ):

```solidity
2: pragma solidity 0.8.19;
```

- *WithdrawQueueStorage.sol* ( [2](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueueStorage.sol#L2) ):

```solidity
2: pragma solidity 0.8.19;
```

- *EzEthToken.sol* ( [2](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/token/EzEthToken.sol#L2) ):

```solidity
2: pragma solidity ^0.8.9;
```

- *EzEthTokenStorage.sol* ( [2](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/token/EzEthTokenStorage.sol#L2) ):

```solidity
2: pragma solidity 0.8.19;
```

</details>

### [N-52] Use transfer libraries instead of low level calls to transfer native tokens

Consider using [`SafeTransferLib.safeTransferETH`](https://github.com/transmissions11/solmate/blob/fadb2e2778adbf01c80275bfb99e5c14969d964b/src/utils/SafeTransferLib.sol#L15) or [`Address.sendValue`](https://github.com/OpenZeppelin/openzeppelin-contracts/blob/9e3f4d60c581010c4a3979480e07cc7752f124cc/contracts/utils/Address.sol#L41) for clearer semantic meaning instead of using a low level `call`.

<details>
<summary>There are 6 instances (click to show):</summary>

- *xRenzoDeposit.sol* ( [403-403](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L403-L403) ):

```solidity
403:         (bool success, ) = payable(msg.sender).call{ value: feeCollected }("");
```

- *XERC20Lockbox.sol* ( [131-131](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L131-L131) ):

```solidity
131:             (bool _success, ) = payable(_to).call{ value: _amount }("");
```

- *OperatorDelegator.sol* ( [520-520](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L520-L520) ):

```solidity
520:             (bool success, ) = destination.call{ value: remainingAmount }("");
```

- *DepositQueue.sol* ( [168-168](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L168-L168), [286-286](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L286-L286) ):

```solidity
168:             (bool success, ) = feeAddress.call{ value: feeAmount }("");

286:         (bool success, ) = payable(msg.sender).call{ value: gasRefund }("");
```

- *RewardHandler.sol* ( [68-68](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Rewards/RewardHandler.sol#L68-L68) ):

```solidity
68:         (bool success, ) = rewardDestination.call{ value: balance }("");
```

</details>

### [N-53] Use a struct to encapsulate multiple function parameters

If a function has too many parameters, replacing them with a struct can improve code readability and maintainability, increase reusability, and reduce the likelihood of errors when passing the parameters.

<details>
<summary>There are 9 instances (click to show):</summary>

- *TimelockController.sol* ( [201-207](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L201-L207), [215-221](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L215-L221), [234-241](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L234-L241), [259-266](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L259-L266), [315-321](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L315-L321), [342-348](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L342-L348), [423-429](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L423-L429), [436-442](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L436-L442) ):

```solidity
201:     function hashOperation(
202:         address target,
203:         uint256 value,
204:         bytes calldata data,
205:         bytes32 predecessor,
206:         bytes32 salt
207:     ) public pure virtual returns (bytes32) {

215:     function hashOperationBatch(
216:         address[] calldata targets,
217:         uint256[] calldata values,
218:         bytes[] calldata payloads,
219:         bytes32 predecessor,
220:         bytes32 salt
221:     ) public pure virtual returns (bytes32) {

234:     function schedule(
235:         address target,
236:         uint256 value,
237:         bytes calldata data,
238:         bytes32 predecessor,
239:         bytes32 salt,
240:         uint256 delay
241:     ) public virtual onlyRole(PROPOSER_ROLE) {

259:     function scheduleBatch(
260:         address[] calldata targets,
261:         uint256[] calldata values,
262:         bytes[] calldata payloads,
263:         bytes32 predecessor,
264:         bytes32 salt,
265:         uint256 delay
266:     ) public virtual onlyRole(PROPOSER_ROLE) {

315:     function execute(
316:         address target,
317:         uint256 value,
318:         bytes calldata payload,
319:         bytes32 predecessor,
320:         bytes32 salt
321:     ) public payable virtual onlyRoleOrOpenRole(EXECUTOR_ROLE) {

342:     function executeBatch(
343:         address[] calldata targets,
344:         uint256[] calldata values,
345:         bytes[] calldata payloads,
346:         bytes32 predecessor,
347:         bytes32 salt
348:     ) public payable virtual onlyRoleOrOpenRole(EXECUTOR_ROLE) {

423:     function onERC1155Received(
424:         address,
425:         address,
426:         uint256,
427:         uint256,
428:         bytes memory
429:     ) public virtual override returns (bytes4) {

436:     function onERC1155BatchReceived(
437:         address,
438:         address,
439:         uint256[] memory,
440:         uint256[] memory,
441:         bytes memory
442:     ) public virtual override returns (bytes4) {
```

- *WithdrawQueue.sol* ( [64-71](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L64-L71) ):

```solidity
64:     function initialize(
65:         IRoleManager _roleManager,
66:         IRestakeManager _restakeManager,
67:         IEzEthToken _ezETH,
68:         IRenzoOracle _renzoOracle,
69:         uint256 _coolDownPeriod,
70:         TokenWithdrawBuffer[] calldata _withdrawalBufferTarget
71:     ) external initializer {
```

</details>

### [N-54] Returning a struct instead of a bunch of variables is better

If a function returns [too many variables](https://docs.soliditylang.org/en/v0.8.21/contracts.html#returning-multiple-values), replacing them with a struct can improve code readability, maintainability and reusability.

<details>
<summary>There are 7 instances (click to show):</summary>

- *WBETHShim.sol* ( [42-42](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Binance/WBETHShim.sol#L42-L42), [46-55](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Binance/WBETHShim.sol#L46-L55), [69-78](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Binance/WBETHShim.sol#L69-L78) ):

```solidity
42:     function getRoundData(uint80) external pure returns (uint80, int256, uint256, uint256, uint80) {

46:     function latestRoundData()
47:         external
48:         view
49:         returns (
50:             uint80 roundId,
51:             int256 answer,
52:             uint256 startedAt,
53:             uint256 updatedAt,
54:             uint80 answeredInRound
55:         )

69:     function _getWBETHData()
70:         internal
71:         view
72:         returns (
73:             uint80 roundId,
74:             int256 answer,
75:             uint256 startedAt,
76:             uint256 updatedAt,
77:             uint80 answeredInRound
78:         )
```

- *METHShim.sol* ( [42-42](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Mantle/METHShim.sol#L42-L42), [46-55](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Mantle/METHShim.sol#L46-L55), [69-78](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Mantle/METHShim.sol#L69-L78) ):

```solidity
42:     function getRoundData(uint80) external pure returns (uint80, int256, uint256, uint256, uint80) {

46:     function latestRoundData()
47:         external
48:         view
49:         returns (
50:             uint80 roundId,
51:             int256 answer,
52:             uint256 startedAt,
53:             uint256 updatedAt,
54:             uint80 answeredInRound
55:         )

69:     function _getMETHData()
70:         internal
71:         view
72:         returns (
73:             uint80 roundId,
74:             int256 answer,
75:             uint256 startedAt,
76:             uint256 updatedAt,
77:             uint80 answeredInRound
78:         )
```

- *RestakeManager.sol* ( [274-274](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L274-L274) ):

```solidity
274:     function calculateTVLs() public view returns (uint256[][] memory, uint256[] memory, uint256) {
```

</details>

### [N-55] Events that mark critical parameter changes should contain both the old and the new value

This should especially be done if the new value is not required to be different from the old value.

<details>
<summary>There are 10 instances (click to show):</summary>

- *xRenzoDeposit.sol* ( [469-469](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L469-L469) ):

```solidity
469:         emit BridgeSweeperAddressUpdated(_sweeper, _allowed);
```

- *XERC20.sol* ( [125-125](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20.sol#L125-L125) ):

```solidity
125:         emit LockboxSet(_lockbox);
```

- *OperatorDelegator.sol* ( [129-129](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L129-L129) ):

```solidity
129:         emit DelegationAddressUpdated(_delegateAddress);
```

- *DepositQueue.sol* ( [108-108](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L108-L108), [117-117](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L117-L117) ):

```solidity
108:         emit FeeConfigUpdated(_feeAddress, _feeBasisPoints);

117:         emit RestakeManagerUpdated(_restakeManager);
```

- *RestakeManager.sol* ( [156-156](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L156-L156), [169-169](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L169-L169), [211-211](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L211-L211), [716-716](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L716-L716) ):

```solidity
156:         emit OperatorDelegatorAllocationUpdated(_newOperatorDelegator, _allocationBasisPoints);

169:                 emit OperatorDelegatorAllocationUpdated(_operatorDelegatorToRemove, 0);

211:         emit OperatorDelegatorAllocationUpdated(_operatorDelegator, _allocationBasisPoints);

716:         emit CollateralTokenTvlUpdated(_token, _limit);
```

- *RewardHandler.sol* ( [79-79](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Rewards/RewardHandler.sol#L79-L79) ):

```solidity
79:         emit RewardDestinationUpdated(_rewardDestination);
```

</details>

### [N-56] Contract variables should have comments

Consider adding some comments on non-public contract variables to explain what they are supposed to do. This will help for future code reviews.

There are 4 instances:

- *LockboxAdapterBlast.sol* ( [31-31](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L31-L31), [32-32](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L32-L32) ):

```solidity
31:     address immutable blastStandardBridge;

32:     address immutable registry;
```

- *TimelockController.sol* ( [32-32](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L32-L32), [33-33](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L33-L33) ):

```solidity
32:     mapping(bytes32 => uint256) private _timestamps;

33:     uint256 private _minDelay;
```

### [N-57] Missing event when a state variables is set in constructor

The initial states set in a constructor are important and should be recorded in the event.

There are 6 instances:

- *CCIPReceiver.sol* ( [51](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L51), [54](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L54) ):

```solidity
51:         xRenzoBridgeL1 = _xRenzoBridgeL1;

54:         ccipEthChainSelector = _ccipEthChainSelector;
```

- *ConnextReceiver.sol* ( [57](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L57), [60](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L60), [63](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L63) ):

```solidity
57:         connext = _connext;

60:         xRenzoBridgeL1 = _xRenzoBridgeL1;

63:         connextEthChainDomain = _connextEthChainDomain;
```

- *TimelockController.sol* ( [117](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L117) ):

```solidity
117:         _minDelay = minDelay;
```

### [N-58] Empty bytes check is missing

Passing empty bytes to a function can cause unexpected behavior, such as certain operations failing, producing incorrect results, or wasting gas. It is recommended to check that all byte parameters are not empty.

<details>
<summary>There are 10 instances (click to show):</summary>

- *LockboxAdapterBlast.sol* ( [56-63](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L56-L63) ):

```solidity
/// @audit _extraData
56:     function bridgeTo(
57:         address _to,
58:         address _erc20,
59:         address _remoteToken,
60:         uint256 _amount,
61:         uint32 _minGasLimit,
62:         bytes calldata _extraData
63:     ) external {
```

- *ConnextReceiver.sol* ( [69-76](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L69-L76) ):

```solidity
/// @audit _callData
69:     function xReceive(
70:         bytes32 _transferId,
71:         uint256,
72:         address,
73:         address _originSender,
74:         uint32 _origin,
75:         bytes memory _callData
76:     ) external onlySource(_originSender, _origin) whenNotPaused returns (bytes memory) {
```

- *OperatorDelegator.sol* ( [349-353](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L349-L353) ):

```solidity
/// @audit pubkey
/// @audit signature
349:     function stakeEth(
350:         bytes calldata pubkey,
351:         bytes calldata signature,
352:         bytes32 depositDataRoot
353:     ) external payable onlyRestakeManager {
```

- *DepositQueue.sol* ( [187-192](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L187-L192) ):

```solidity
/// @audit pubkey
/// @audit signature
187:     function stakeEthFromQueue(
188:         IOperatorDelegator operatorDelegator,
189:         bytes calldata pubkey,
190:         bytes calldata signature,
191:         bytes32 depositDataRoot
192:     ) external onlyNativeEthRestakeAdmin {
```

- *RestakeManager.sol* ( [620-625](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L620-L625) ):

```solidity
/// @audit pubkey
/// @audit signature
620:     function stakeEthInOperatorDelegator(
621:         IOperatorDelegator operatorDelegator,
622:         bytes calldata pubkey,
623:         bytes calldata signature,
624:         bytes32 depositDataRoot
625:     ) external payable onlyDepositQueue {
```

- *TimelockController.sol* ( [234-241](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L234-L241), [315-321](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L315-L321) ):

```solidity
/// @audit data
234:     function schedule(
235:         address target,
236:         uint256 value,
237:         bytes calldata data,
238:         bytes32 predecessor,
239:         bytes32 salt,
240:         uint256 delay
241:     ) public virtual onlyRole(PROPOSER_ROLE) {

/// @audit payload
315:     function execute(
316:         address target,
317:         uint256 value,
318:         bytes calldata payload,
319:         bytes32 predecessor,
320:         bytes32 salt
321:     ) public payable virtual onlyRoleOrOpenRole(EXECUTOR_ROLE) {
```

</details>

### [N-59] Don't define functions with the same name in a contract

In Solidity, while function overriding allows for functions with the same name to coexist, it is advisable to avoid this practice to enhance code readability and maintainability. Having multiple functions with the same name, even with different parameters or in inherited contracts, can cause confusion and increase the likelihood of errors during development, testing, and debugging. Using distinct and descriptive function names not only clarifies the purpose and behavior of each function, but also helps prevent unintended function calls or incorrect overriding. By adopting a clear and consistent naming convention, developers can create more comprehensible and maintainable smart contracts.

There are 2 instances:

- *RestakeManager.sol* ( [491](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L491), [592](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L592) ):

```solidity
/// @audit Different function with same name found on line 473
491:     function deposit(

/// @audit Different function with same name found on line 582
592:     function depositETH(uint256 _referralId) public payable nonReentrant notPaused {
```

### [N-60] Interface files should not use fixed compiler versions

Interfaces should not use fixed compiler versions, since they may be used by projects using a different version.

There is 1 instance:

- *Errors.sol* ( [2](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Errors/Errors.sol#L2) ):

```solidity
2: pragma solidity 0.8.19;
```

### [N-61] Multiple mappings with same keys can be combined into a single struct mapping for readability

Well-organized data structures make code reviews easier, which may lead to fewer bugs. Consider combining related mappings into mappings to structs, so it's clear what data is related.

There are 3 instances:

- *WithdrawQueueStorage.sol* ( [44-44](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueueStorage.sol#L44-L44), [47-47](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueueStorage.sol#L47-L47), [50-50](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueueStorage.sol#L50-L50) ):

```solidity
44:     mapping(address => uint256) public withdrawalBufferTarget;

47:     mapping(address => uint256) public claimReserve;

50:     mapping(address => WithdrawRequest[]) public withdrawRequests;
```

### [N-62] Missing event for critical changes

Events should be emitted when critical changes are made to the contracts.

There are 3 instances:

- *RestakeManager.sol* ( [121-123](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L121-L123), [215-217](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L215-L217) ):

```solidity
121:     function setPaused(bool _paused) external onlyDepositWithdrawPauserAdmin {
122:         paused = _paused;
123:     }

215:     function setMaxDepositTVL(uint256 _maxDepositTVL) external onlyRestakeManagerAdmin {
216:         maxDepositTVL = _maxDepositTVL;
217:     }
```

- *EzEthToken.sol* ( [51-53](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/token/EzEthToken.sol#L51-L53) ):

```solidity
51:     function setPaused(bool _paused) external onlyTokenAdmin {
52:         paused = _paused;
53:     }
```

### [N-63] Duplicated `require()`/`revert()` checks should be refactored

Refactoring duplicate `require()`/`revert()` checks into a modifier or function can make the code more concise, readable and maintainable, and less likely to make errors or omissions when modifying the `require()` or `revert()`.

<details>
<summary>There are 22 instances (click to show):</summary>

- *xRenzoBridge.sol* ( [101-101](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L101-L101) ):

```solidity
/// @audit Duplicated on line 105, 109, 113
101:             revert InvalidTokenDecimals(EXPECTED_DECIMALS, decimals);
```

- *xRenzoDeposit.sol* ( [107-107](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L107-L107), [346-346](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L346-L346) ):

```solidity
/// @audit Duplicated on line 111, 115
107:             revert InvalidTokenDecimals(EXPECTED_DECIMALS, decimals);

/// @audit Duplicated on line 351
346:             revert InvalidTimestamp(_timestamp);
```

- *XERC20.sol* ( [330-330](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20.sol#L330-L330), [334-334](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20.sol#L334-L334) ):

```solidity
/// @audit Duplicated on line 350
330:         if (_amount == 0) revert IXERC20_INVALID_0_VALUE();

/// @audit Duplicated on line 354
334:             if (_currentLimit < _amount) revert IXERC20_NotHighEnoughLimits();
```

- *XERC20Lockbox.sol* ( [55-55](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L55-L55), [67-67](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L67-L67) ):

```solidity
/// @audit Duplicated on line 92
55:         if (!IS_NATIVE) revert IXERC20Lockbox_NotNative();

/// @audit Duplicated on line 80
67:         if (IS_NATIVE) revert IXERC20Lockbox_Native();
```

- *OperatorDelegator.sol* ( [199-199](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L199-L199), [486-486](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L486-L486) ):

```solidity
/// @audit Duplicated on line 271
199:         if (tokens.length != tokenAmounts.length) revert MismatchedArrayLengths();

/// @audit Duplicated on line 521
486:         if (!success) revert TransferFailed();
```

- *DepositQueue.sol* ( [169-169](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L169-L169) ):

```solidity
/// @audit Duplicated on line 287
169:             if (!success) revert TransferFailed();
```

- *RenzoOracle.sol* ( [73-73](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L73-L73), [76-76](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L76-L76), [77-77](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L77-L77) ):

```solidity
/// @audit Duplicated on line 90
73:         if (address(oracle) == address(0x0)) revert OracleNotFound();

/// @audit Duplicated on line 93
76:         if (timestamp < block.timestamp - MAX_TIME_WINDOW) revert OraclePriceExpired();

/// @audit Duplicated on line 94
77:         if (price <= 0) revert InvalidOraclePrice();
```

- *RestakeManager.sol* ( [139-139](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L139-L139), [146-146](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L146-L146), [511-511](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L511-L511) ):

```solidity
/// @audit Duplicated on line 224
139:                 revert AlreadyAdded();

/// @audit Duplicated on line 192
146:         if (_allocationBasisPoints > (100 * BASIS_POINTS)) revert OverMaxBasisPoints();

/// @audit Duplicated on line 598
511:             revert MaxTVLReached();
```

- *TimelockController.sol* ( [267-267](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L267-L267), [268-268](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L268-L268), [377-377](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L377-L377) ):

```solidity
/// @audit Duplicated on line 349
267:         require(targets.length == values.length, "TimelockController: length mismatch");

/// @audit Duplicated on line 350
268:         require(targets.length == payloads.length, "TimelockController: length mismatch");

/// @audit Duplicated on line 388
377:         require(isOperationReady(id), "TimelockController: operation is not ready");
```

</details>

### [N-64] Consider adding emergency-stop functionality

Adding a way to quickly halt protocol functionality in an emergency, rather than having to pause individual contracts one-by-one, will make in-progress hack mitigation faster and much less stressful.

<details>
<summary>There are 12 instances (click to show):</summary>

- *RenzoOracleL2.sol* ( [11-11](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L11-L11) ):

```solidity
11: contract RenzoOracleL2 is Initializable, OwnableUpgradeable, RenzoOracleL2StorageV1 {
```

- *CCIPReceiver.sol* ( [14-14](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L14-L14) ):

```solidity
14: contract Receiver is CCIPReceiver, Ownable, Pausable {
```

- *ConnextReceiver.sol* ( [10-10](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L10-L10) ):

```solidity
10: contract ConnextReceiver is IXReceiver, Ownable, Pausable {
```

- *xRenzoDeposit.sol* ( [27-32](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L27-L32) ):

```solidity
27: contract xRenzoDeposit is
28:     Initializable,
29:     OwnableUpgradeable,
30:     ReentrancyGuardUpgradeable,
31:     IRateProvider,
32:     xRenzoDepositStorageV3
```

- *XERC20.sol* ( [16-21](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20.sol#L16-L21) ):

```solidity
16: contract XERC20 is
17:     Initializable,
18:     ERC20Upgradeable,
19:     OwnableUpgradeable,
20:     IXERC20,
21:     ERC20PermitUpgradeable
```

- *OptimismMintableXERC20.sol* ( [11-11](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L11-L11) ):

```solidity
11: contract OptimismMintableXERC20 is ERC165Upgradeable, XERC20, IOptimismMintableERC20 {
```

- *RoleManager.sol* ( [14-14](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Permissions/RoleManager.sol#L14-L14) ):

```solidity
14: contract RoleManager is IRoleManager, AccessControlUpgradeable, RoleManagerStorageV3 {
```

- *RoleManagerStorage.sol* ( [9](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Permissions/RoleManagerStorage.sol#L9), [37-37](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Permissions/RoleManagerStorage.sol#L37-L37), [45-45](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Permissions/RoleManagerStorage.sol#L45-L45) ):

```solidity
9: contract RoleManagerStorageV1 {

37: contract RoleManagerStorageV2 is RoleManagerStorageV1 {

45: contract RoleManagerStorageV3 is RoleManagerStorageV2 {
```

- *RestakeManager.sol* ( [26-26](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L26-L26) ):

```solidity
26: contract RestakeManager is Initializable, ReentrancyGuardUpgradeable, RestakeManagerStorageV2 {
```

- *TimelockController.sol* ( [25-25](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L25-L25) ):

```solidity
25: contract TimelockController is AccessControl, IERC721Receiver, IERC1155Receiver {
```

</details>

### [N-65] Avoid the use of sensitive terms

Use [alternative variants](https://www.zdnet.com/article/mysql-drops-master-slave-and-blacklist-whitelist-terminology/), e.g. allowlist/denylist instead of whitelist/blacklist.

<details>
<summary>There are 25 instances (click to show):</summary>

- *LockboxAdapterBlast.sol* ( [40](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L40), [64](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L64), [72](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L72) ):

```solidity
40:         // Sanity check

64:         // Sanity check

72:         // Sanity check
```

- *xRenzoBridge.sol* ( [134](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L134) ):

```solidity
134:      * @notice  WARNING: This function does NOT whitelist who can send funds from the L2 via Connext.  Users should NOT
```

- *xRenzoDeposit.sol* ( [185](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L185), [326](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L326), [415](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L415) ):

```solidity
185:         // Sanity check for 0

326:      * @dev     Sanity checks input values and updates prices

415:         // Verify the caller is whitelisted
```

- *OperatorDelegator.sol* ( [49](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L49), [61](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L61) ):

```solidity
49:     /// @dev Allows only a whitelisted address to configure the contract

61:     /// @dev Allows only a whitelisted address to configure the contract
```

- *DepositQueue.sol* ( [43](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L43), [55](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L55), [61](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L61) ):

```solidity
43:     /// @dev Allows only a whitelisted address to configure the contract

55:     /// @dev Allows only a whitelisted address to trigger native ETH staking

61:     /// @dev Allows only a whitelisted address to trigger ERC20 rewards sweeping
```

- *Errors.sol* ( [97](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Errors/Errors.sol#L97) ):

```solidity
97: /// @dev Error when the origin address is not whitelisted
```

- *RenzoOracle.sol* ( [28](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L28), [145](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L145), [160](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L160) ):

```solidity
28:     /// @dev Allows only a whitelisted address to configure the contract

145:         // Sanity check

160:         // Sanity check
```

- *RoleManager.sol* ( [84](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Permissions/RoleManager.sol#L84) ):

```solidity
84:     /// @dev Determines if the specified address has permission to set whitelisted origin in xRenzoBridge
```

- *RoleManagerStorage.sol* ( [38](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Permissions/RoleManagerStorage.sol#L38) ):

```solidity
38:     /// @dev role for granting capability to update whitelisted origin in xRenzoBridge
```

- *BalancerRateProvider.sol* ( [36](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RateProvider/BalancerRateProvider.sol#L36) ):

```solidity
36:         // Sanity check
```

- *RestakeManager.sol* ( [70](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L70), [76](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L76) ):

```solidity
70:     /// @dev Allows only a whitelisted address to configure the contract

76:     /// @dev Allows only a whitelisted address to set pause state
```

- *RewardHandler.sol* ( [17](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Rewards/RewardHandler.sol#L17), [23](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Rewards/RewardHandler.sol#L23) ):

```solidity
17:     /// @dev Allows only a whitelisted address to trigger native ETH staking

23:     /// @dev Allows only a whitelisted address to configure the contract
```

- *EzEthToken.sol* ( [14](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/token/EzEthToken.sol#L14), [20](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/token/EzEthToken.sol#L20) ):

```solidity
14:     /// @dev Allows only a whitelisted address to mint or burn ezETH tokens

20:     /// @dev Allows only a whitelisted address to pause or unpause the token
```

</details>

### [N-66] Missing checks for uint state variable assignments

Consider whether reasonable bounds checks for variables would be useful.

<details>
<summary>There are 9 instances (click to show):</summary>

- *CCIPReceiver.sol* ( [110-110](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L110-L110) ):

```solidity
110:         ccipEthChainSelector = _newChainSelector;
```

- *ConnextReceiver.sol* ( [106-106](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L106-L106) ):

```solidity
106:         connextEthChainDomain = _newChainDomain;
```

- *xRenzoDeposit.sol* ( [119-119](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L119-L119), [143-143](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L143-L143) ):

```solidity
119:         lastPrice = _currentPrice;

143:         bridgeDestinationDomain = _bridgeDestinationDomain;
```

- *OperatorDelegator.sol* ( [137-137](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L137-L137) ):

```solidity
137:         baseGasAmountSpent = _baseGasAmountSpent;
```

- *RestakeManager.sol* ( [216-216](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L216-L216) ):

```solidity
216:         maxDepositTVL = _maxDepositTVL;
```

- *TimelockController.sol* ( [405-405](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L405-L405) ):

```solidity
405:         _minDelay = newDelay;
```

- *WithdrawQueue.sol* ( [87-87](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L87-L87), [132-132](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L132-L132) ):

```solidity
87:         coolDownPeriod = _coolDownPeriod;

132:         coolDownPeriod = _newCoolDownPeriod;
```

</details>

### [N-67] Use the Modern Upgradeable Contract Paradigm

Modern smart contract development often employs upgradeable contract structures, utilizing proxy patterns like OpenZeppelin’s Upgradeable Contracts. This paradigm separates logic and state, allowing developers to amend and enhance the contract's functionality without altering its state or the deployed contract address. Transitioning to this approach enhances long-term maintainability.
Resolution: Adopt a well-established proxy pattern for upgradeability, ensuring proper initialization and employing transparent proxies to mitigate potential risks. Embrace comprehensive testing and audit practices, particularly when updating contract logic, to ensure state consistency and security are preserved across upgrades. This ensures your contract remains robust and adaptable to future requirements.

<details>
<summary>There are 8 instances (click to show):</summary>

- *LockboxAdapterBlast.sol* ( [30](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L30) ):

```solidity
30: contract LockboxAdapterBlast {
```

- *CCIPReceiver.sol* ( [14](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L14) ):

```solidity
14: contract Receiver is CCIPReceiver, Ownable, Pausable {
```

- *ConnextReceiver.sol* ( [10](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L10) ):

```solidity
10: contract ConnextReceiver is IXReceiver, Ownable, Pausable {
```

- *RoleManagerStorage.sol* ( [9](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Permissions/RoleManagerStorage.sol#L9), [37](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Permissions/RoleManagerStorage.sol#L37), [45](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Permissions/RoleManagerStorage.sol#L45) ):

```solidity
9: contract RoleManagerStorageV1 {

37: contract RoleManagerStorageV2 is RoleManagerStorageV1 {

45: contract RoleManagerStorageV3 is RoleManagerStorageV2 {
```

- *TimelockController.sol* ( [25](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L25) ):

```solidity
25: contract TimelockController is AccessControl, IERC721Receiver, IERC1155Receiver {
```

- *EzEthTokenStorage.sol* ( [10](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/token/EzEthTokenStorage.sol#L10) ):

```solidity
10: contract EzEthTokenStorageV1 {
```

</details>

### [N-68] Large or complicated code bases should implement invariant tests

This includes: large code bases, or code with lots of inline-assembly, complicated math, or complicated interactions between multiple contracts.
Invariant fuzzers such as Echidna require the test writer to come up with invariants which should not be violated under any circumstances, and the fuzzer tests various inputs and function calls to ensure that the invariants always hold.
Even code with 100% code coverage can still have bugs due to the order of the operations a user performs, and invariant fuzzers may help significantly.

There is 1 instance:

- Global finding

### [N-69] The default value is manually set when it is declared

In instances where a new variable is defined, there is no need to set it to it's default value.

<details>
<summary>There are 37 instances (click to show):</summary>

- *xRenzoBridge.sol* ( [218-218](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L218-L218), [264-264](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L264-L264) ):

```solidity
218:         for (uint256 i = 0; i < _destinationParam.length; ) {

264:         for (uint256 i = 0; i < _connextDestinationParam.length; ) {
```

- *xRenzoDeposit.sol* ( [372-372](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L372-L372) ):

```solidity
372:         uint256 minOut = 0;
```

- *OperatorDelegator.sol* ( [176-176](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L176-L176), [381-381](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L381-L381), [507-507](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L507-L507) ):

```solidity
176:         for (uint256 i = 0; i < strategyLength; i++) {

381:         for (uint256 i = 0; i < validatorFields.length; ) {

507:             uint256 gasRefunded = 0;
```

- *DepositQueue.sol* ( [164-164](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L164-L164), [227-227](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L227-L227), [257-257](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L257-L257) ):

```solidity
164:         uint256 feeAmount = 0;

227:         for (uint256 i = 0; i < arrayLength; ) {

257:             uint256 feeAmount = 0;
```

- *RenzoOracle.sol* ( [109-109](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L109-L109), [111-111](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L111-L111) ):

```solidity
109:         uint256 totalValue = 0;

111:         for (uint256 i = 0; i < tokenLength; ) {
```

- *RestakeManager.sol* ( [137-137](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L137-L137), [165-165](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L165-L165), [197-197](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L197-L197), [223-223](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L223-L223), [249-249](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L249-L249), [277-277](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L277-L277), [287-287](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L287-L287), [289-289](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L289-L289), [291-291](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L291-L291), [299-299](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L299-L299), [376-376](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L376-L376), [418-418](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L418-L418), [435-435](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L435-L435), [454-454](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L454-L454), [517-517](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L517-L517), [521-521](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L521-L521), [629-629](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L629-L629), [676-676](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L676-L676), [683-683](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L683-L683), [699-699](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L699-L699) ):

```solidity
137:         for (uint256 i = 0; i < odLength; ) {

165:         for (uint256 i = 0; i < odLength; ) {

197:         for (uint256 i = 0; i < odLength; ) {

223:         for (uint256 i = 0; i < tokenLength; ) {

249:         for (uint256 i = 0; i < tokenLength; ) {

277:         uint256 totalTVL = 0;

287:         uint256 totalWithdrawalQueueValue = 0;

289:         for (uint256 i = 0; i < odLength; ) {

291:             uint256 operatorTVL = 0;

299:             for (uint256 j = 0; j < tokenLength; ) {

376:         for (uint256 i = 0; i < tvlLength; ) {

418:         for (uint256 i = 0; i < odLength; ) {

435:         for (uint256 i = 0; i < odLength; ) {

454:         for (uint256 i = 0; i < tokenLength; ) {

517:             uint256 currentTokenTVL = 0;

521:             for (uint256 i = 0; i < odLength; ) {

629:         for (uint256 i = 0; i < odLength; ) {

676:         uint256 totalRewards = 0;

683:         for (uint256 i = 0; i < tokenLength; ) {

699:         for (uint256 i = 0; i < odLength; ) {
```

- *TimelockController.sol* ( [107-107](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L107-L107), [113-113](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L113-L113), [272-272](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L272-L272), [355-355](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L355-L355) ):

```solidity
107:         for (uint256 i = 0; i < proposers.length; ++i) {

113:         for (uint256 i = 0; i < executors.length; ++i) {

272:         for (uint256 i = 0; i < targets.length; ++i) {

355:         for (uint256 i = 0; i < targets.length; ++i) {
```

- *WithdrawQueue.sol* ( [88-88](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L88-L88), [110-110](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L110-L110) ):

```solidity
88:         for (uint256 i = 0; i < _withdrawalBufferTarget.length; ) {

110:         for (uint256 i = 0; i < _newBufferTarget.length; ) {
```

</details>

### [N-70] Contracts should have all `public`/`external` functions exposed by `interface`s

All `external`/`public` functions should extend an `interface`. This is useful to ensure that the whole API is extracted and can be more easily integrated by other projects.

<details>
<summary>There are 23 instances (click to show):</summary>

- *LockboxAdapterBlast.sol* ( [30](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L30) ):

```solidity
30: contract LockboxAdapterBlast {
```

- *xRenzoBridge.sol* ( [16](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L16) ):

```solidity
16: contract xRenzoBridge is
```

- *RenzoOracleL2.sol* ( [11](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L11) ):

```solidity
11: contract RenzoOracleL2 is Initializable, OwnableUpgradeable, RenzoOracleL2StorageV1 {
```

- *CCIPReceiver.sol* ( [14](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L14) ):

```solidity
14: contract Receiver is CCIPReceiver, Ownable, Pausable {
```

- *ConnextReceiver.sol* ( [10](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L10) ):

```solidity
10: contract ConnextReceiver is IXReceiver, Ownable, Pausable {
```

- *xRenzoDeposit.sol* ( [27](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L27) ):

```solidity
27: contract xRenzoDeposit is
```

- *XERC20.sol* ( [16](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20.sol#L16) ):

```solidity
16: contract XERC20 is
```

- *XERC20Factory.sol* ( [14](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L14) ):

```solidity
14: contract XERC20Factory is Initializable, IXERC20Factory {
```

- *XERC20Lockbox.sol* ( [11](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L11) ):

```solidity
11: contract XERC20Lockbox is Initializable, IXERC20Lockbox {
```

- *OptimismMintableXERC20.sol* ( [11](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L11) ):

```solidity
11: contract OptimismMintableXERC20 is ERC165Upgradeable, XERC20, IOptimismMintableERC20 {
```

- *OptimismMintableXERC20Factory.sol* ( [14](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L14) ):

```solidity
14: contract OptimismMintableXERC20Factory is Initializable, XERC20Factory {
```

- *OperatorDelegator.sol* ( [17](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L17) ):

```solidity
17: contract OperatorDelegator is
```

- *DepositQueue.sol* ( [10](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L10) ):

```solidity
10: contract DepositQueue is Initializable, ReentrancyGuardUpgradeable, DepositQueueStorageV2 {
```

- *WBETHShim.sol* ( [15](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Binance/WBETHShim.sol#L15) ):

```solidity
15: contract WBETHShim is Initializable, WBETHShimStorageV1 {
```

- *METHShim.sol* ( [15](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Mantle/METHShim.sol#L15) ):

```solidity
15: contract METHShim is Initializable, METHShimStorageV1 {
```

- *RenzoOracle.sol* ( [13](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L13) ):

```solidity
13: contract RenzoOracle is
```

- *RoleManager.sol* ( [14](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Permissions/RoleManager.sol#L14) ):

```solidity
14: contract RoleManager is IRoleManager, AccessControlUpgradeable, RoleManagerStorageV3 {
```

- *BalancerRateProvider.sol* ( [9](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RateProvider/BalancerRateProvider.sol#L9) ):

```solidity
9: contract BalancerRateProvider is Initializable, IRateProvider, BalancerRateProviderStorageV1 {
```

- *RestakeManager.sol* ( [26](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L26) ):

```solidity
26: contract RestakeManager is Initializable, ReentrancyGuardUpgradeable, RestakeManagerStorageV2 {
```

- *RewardHandler.sol* ( [16](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Rewards/RewardHandler.sol#L16) ):

```solidity
16: contract RewardHandler is Initializable, ReentrancyGuardUpgradeable, RewardHandlerStorageV1 {
```

- *TimelockController.sol* ( [25](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L25) ):

```solidity
25: contract TimelockController is AccessControl, IERC721Receiver, IERC1155Receiver {
```

- *WithdrawQueue.sol* ( [11](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L11) ):

```solidity
11: contract WithdrawQueue is
```

- *EzEthToken.sol* ( [13](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/token/EzEthToken.sol#L13) ):

```solidity
13: contract EzEthToken is Initializable, ERC20Upgradeable, IEzEthToken, EzEthTokenStorageV1 {
```

</details>

### [N-71] Top-level declarations should be separated by at least two lines

-

<details>
<summary>There are 89 instances (click to show):</summary>

- *LockboxAdapterBlast.sol* ( [2-4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L2-L4), [7-9](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L7-L9), [15-17](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L15-L17) ):

```solidity
2: pragma solidity ^0.8.13;
3: 
4: import { SafeERC20 } from "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";

7: import { IXERC20Lockbox } from "../../xERC20/interfaces/IXERC20Lockbox.sol";
8: 
9: interface IXERC20Registry {

15: }
16: 
17: interface L1StandardBridge {
```

- *xRenzoBridge.sol* ( [2-4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L2-L4), [14-16](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L14-L16), [53-55](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L53-L55) ):

```solidity
2: pragma solidity 0.8.19;
3: 
4: import "./xRenzoBridgeStorage.sol";

14: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";
15: 
16: contract xRenzoBridge is

53:     }
54: 
55:     modifier onlyPriceFeedSender() {
```

- *xRenzoBridgeStorage.sol* ( [2-4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridgeStorage.sol#L2-L4), [16-18](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridgeStorage.sol#L16-L18) ):

```solidity
2: pragma solidity 0.8.19;
3: 
4: import "./IxRenzoBridge.sol";

16: import { IRoleManager } from "../../Permissions/IRoleManager.sol";
17: 
18: abstract contract xRenzoBridgeStorageV1 is IxRenzoBridge {
```

- *RenzoOracleL2.sol* ( [2-4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L2-L4), [9-11](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L9-L11), [21-23](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L21-L23) ):

```solidity
2: pragma solidity 0.8.19;
3: 
4: import "./RenzoOracleL2Storage.sol";

9: import "../../../Errors/Errors.sol";
10: 
11: contract RenzoOracleL2 is Initializable, OwnableUpgradeable, RenzoOracleL2StorageV1 {

21:     }
22: 
23:     function initialize(AggregatorV3Interface _oracle) public initializer {
```

- *RenzoOracleL2Storage.sol* ( [2-4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/Oracle/RenzoOracleL2Storage.sol#L2-L4), [5-7](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/Oracle/RenzoOracleL2Storage.sol#L5-L7) ):

```solidity
2: pragma solidity 0.8.19;
3: 
4: import "./IRenzoOracleL2.sol";

5: import "@chainlink/contracts/src/v0.8/interfaces/AggregatorV3Interface.sol";
6: 
7: abstract contract RenzoOracleL2StorageV1 is IRenzoOracleL2 {
```

- *CCIPReceiver.sol* ( [2-4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L2-L4) ):

```solidity
2: pragma solidity 0.8.19;
3: 
4: import { Client } from "@chainlink/contracts-ccip/src/v0.8/ccip/libraries/Client.sol";
```

- *ConnextReceiver.sol* ( [2-4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L2-L4), [8-10](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L8-L10), [67-69](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L67-L69) ):

```solidity
2: pragma solidity 0.8.19;
3: 
4: import { IXReceiver } from "@connext/interfaces/core/IXReceiver.sol";

8: import "../../../Errors/Errors.sol";
9: 
10: contract ConnextReceiver is IXReceiver, Ownable, Pausable {

67:     }
68: 
69:     function xReceive(
```

- *xRenzoDeposit.sol* ( [2-4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L2-L4) ):

```solidity
2: pragma solidity 0.8.19;
3: 
4: import "./xRenzoDepositStorage.sol";
```

- *xRenzoDepositStorage.sol* ( [2-4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDepositStorage.sol#L2-L4), [7-9](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDepositStorage.sol#L7-L9), [45-47](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDepositStorage.sol#L45-L47), [50-52](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDepositStorage.sol#L50-L52) ):

```solidity
2: pragma solidity 0.8.19;
3: 
4: import "./IxRenzoDeposit.sol";

7: import "./Oracle/IRenzoOracleL2.sol";
8: 
9: abstract contract xRenzoDepositStorageV1 is IxRenzoDeposit {

45: }
46: 
47: abstract contract xRenzoDepositStorageV2 is xRenzoDepositStorageV1 {

50: }
51: 
52: abstract contract xRenzoDepositStorageV3 is xRenzoDepositStorageV2 {
```

- *XERC20.sol* ( [2-4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20.sol#L2-L4), [14-16](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20.sol#L14-L16) ):

```solidity
2: pragma solidity >=0.8.4 <0.9.0;
3: 
4: import { IXERC20 } from "../interfaces/IXERC20.sol";

14: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";
15: 
16: contract XERC20 is
```

- *XERC20Factory.sol* ( [2-4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L2-L4), [12-14](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L12-L14) ):

```solidity
2: pragma solidity >=0.8.4 <0.9.0;
3: 
4: import { IXERC20Factory } from "../interfaces/IXERC20Factory.sol";

12: import "@openzeppelin/contracts/proxy/transparent/TransparentUpgradeableProxy.sol";
13: 
14: contract XERC20Factory is Initializable, IXERC20Factory {
```

- *XERC20Lockbox.sol* ( [2-4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L2-L4), [9-11](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L9-L11) ):

```solidity
2: pragma solidity >=0.8.4 <0.9.0;
3: 
4: import { IXERC20 } from "../interfaces/IXERC20.sol";

9: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";
10: 
11: contract XERC20Lockbox is Initializable, IXERC20Lockbox {
```

- *OptimismMintableXERC20.sol* ( [2-4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L2-L4), [9-11](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L9-L11), [46-48](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L46-L48), [54-56](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L54-L56), [58-60](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L58-L60), [62-64](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L62-L64), [66-68](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L66-L68) ):

```solidity
2: pragma solidity >=0.8.4 <0.9.0;
3: 
4: import {

9: import { XERC20 } from "../XERC20.sol";
10: 
11: contract OptimismMintableXERC20 is ERC165Upgradeable, XERC20, IOptimismMintableERC20 {

46:     }
47: 
48:     function supportsInterface(

54:     }
55: 
56:     function remoteToken() public view override returns (address) {

58:     }
59: 
60:     function bridge() public view override returns (address) {

62:     }
63: 
64:     function mint(address _to, uint256 _amount) public override(XERC20, IOptimismMintableERC20) {

66:     }
67: 
68:     function burn(address _from, uint256 _amount) public override(XERC20, IOptimismMintableERC20) {
```

- *OptimismMintableXERC20Factory.sol* ( [2-4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L2-L4), [12-14](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L12-L14) ):

```solidity
2: pragma solidity >=0.8.4 <0.9.0;
3: 
4: import { OptimismMintableXERC20 } from "./OptimismMintableXERC20.sol";

12: import "@openzeppelin/contracts/proxy/transparent/TransparentUpgradeableProxy.sol";
13: 
14: contract OptimismMintableXERC20Factory is Initializable, XERC20Factory {
```

- *OperatorDelegator.sol* ( [2-4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L2-L4), [130-132](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L130-L132) ):

```solidity
2: pragma solidity 0.8.19;
3: 
4: import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";

130:     }
131: 
132:     function setBaseGasAmountSpent(
```

- *OperatorDelegatorStorage.sol* ( [2-3](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegatorStorage.sol#L2-L3), [44-46](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegatorStorage.sol#L44-L46), [49-51](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegatorStorage.sol#L49-L51), [57-59](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegatorStorage.sol#L57-L59) ):

```solidity
2: pragma solidity 0.8.19;
3: import "../Permissions/IRoleManager.sol";

44: }
45: 
46: abstract contract OperatorDelegatorStorageV2 is OperatorDelegatorStorageV1 {

49: }
50: 
51: abstract contract OperatorDelegatorStorageV3 is OperatorDelegatorStorageV2 {

57: }
58: 
59: abstract contract OperatorDelegatorStorageV4 is OperatorDelegatorStorageV3 {
```

- *DepositQueue.sol* ( [2-4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L2-L4), [8-10](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L8-L10) ):

```solidity
2: pragma solidity 0.8.19;
3: 
4: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

8: import "../Errors/Errors.sol";
9: 
10: contract DepositQueue is Initializable, ReentrancyGuardUpgradeable, DepositQueueStorageV2 {
```

- *DepositQueueStorage.sol* ( [2-4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueueStorage.sol#L2-L4), [7-9](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueueStorage.sol#L7-L9), [24-26](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueueStorage.sol#L24-L26) ):

```solidity
2: pragma solidity 0.8.19;
3: 
4: import "../Permissions/IRoleManager.sol";

7: import "./IDepositQueue.sol";
8: 
9: abstract contract DepositQueueStorageV1 is IDepositQueue {

24: }
25: 
26: abstract contract DepositQueueStorageV2 is DepositQueueStorageV1 {
```

- *WBETHShim.sol* ( [2-4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Binance/WBETHShim.sol#L2-L4), [27-29](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Binance/WBETHShim.sol#L27-L29), [31-33](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Binance/WBETHShim.sol#L31-L33), [35-37](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Binance/WBETHShim.sol#L35-L37), [44-46](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Binance/WBETHShim.sol#L44-L46) ):

```solidity
2: pragma solidity 0.8.19;
3: 
4: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";

27:     }
28: 
29:     function decimals() external pure returns (uint8) {

31:     }
32: 
33:     function description() external pure returns (string memory) {

35:     }
36: 
37:     function version() external pure returns (uint256) {

44:     }
45: 
46:     function latestRoundData()
```

- *WBETHShimStorage.sol* ( [2-4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Binance/WBETHShimStorage.sol#L2-L4), [5-7](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Binance/WBETHShimStorage.sol#L5-L7) ):

```solidity
2: pragma solidity 0.8.19;
3: 
4: import "@chainlink/contracts/src/v0.8/interfaces/AggregatorV3Interface.sol";

5: import "./IStakedTokenV2.sol";
6: 
7: abstract contract WBETHShimStorageV1 is AggregatorV3Interface {
```

- *METHShim.sol* ( [2-4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Mantle/METHShim.sol#L2-L4), [27-29](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Mantle/METHShim.sol#L27-L29), [31-33](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Mantle/METHShim.sol#L31-L33), [35-37](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Mantle/METHShim.sol#L35-L37), [44-46](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Mantle/METHShim.sol#L44-L46) ):

```solidity
2: pragma solidity 0.8.19;
3: 
4: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";

27:     }
28: 
29:     function decimals() external pure returns (uint8) {

31:     }
32: 
33:     function description() external pure returns (string memory) {

35:     }
36: 
37:     function version() external pure returns (uint256) {

44:     }
45: 
46:     function latestRoundData()
```

- *METHShimStorage.sol* ( [2-4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Mantle/METHShimStorage.sol#L2-L4), [5-7](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Mantle/METHShimStorage.sol#L5-L7) ):

```solidity
2: pragma solidity 0.8.19;
3: 
4: import "@chainlink/contracts/src/v0.8/interfaces/AggregatorV3Interface.sol";

5: import "./IMethStaking.sol";
6: 
7: abstract contract METHShimStorageV1 is AggregatorV3Interface {
```

- *RenzoOracle.sol* ( [2-4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L2-L4) ):

```solidity
2: pragma solidity 0.8.19;
3: 
4: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";
```

- *RenzoOracleStorage.sol* ( [2-4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracleStorage.sol#L2-L4), [6-8](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracleStorage.sol#L6-L8) ):

```solidity
2: pragma solidity 0.8.19;
3: 
4: import "../Permissions/IRoleManager.sol";

6: import "@openzeppelin/contracts/token/ERC20/IERC20.sol";
7: 
8: abstract contract RenzoOracleStorageV1 {
```

- *RoleManager.sol* ( [2-4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Permissions/RoleManager.sol#L2-L4) ):

```solidity
2: pragma solidity 0.8.19;
3: 
4: import "@openzeppelin/contracts-upgradeable/access/AccessControlUpgradeable.sol";
```

- *RoleManagerStorage.sol* ( [43-45](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Permissions/RoleManagerStorage.sol#L43-L45) ):

```solidity
43: }
44: 
45: contract RoleManagerStorageV3 is RoleManagerStorageV2 {
```

- *BalancerRateProvider.sol* ( [2-4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RateProvider/BalancerRateProvider.sol#L2-L4), [7-9](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RateProvider/BalancerRateProvider.sol#L7-L9) ):

```solidity
2: pragma solidity 0.8.19;
3: 
4: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

7: import "./BalancerRateProviderStorage.sol";
8: 
9: contract BalancerRateProvider is Initializable, IRateProvider, BalancerRateProviderStorageV1 {
```

- *BalancerRateProviderStorage.sol* ( [2-4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RateProvider/BalancerRateProviderStorage.sol#L2-L4), [5-7](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RateProvider/BalancerRateProviderStorage.sol#L5-L7) ):

```solidity
2: pragma solidity 0.8.19;
3: 
4: import "@openzeppelin/contracts-upgradeable/token/ERC20/IERC20Upgradeable.sol";

5: import "../IRestakeManager.sol";
6: 
7: abstract contract BalancerRateProviderStorageV1 {
```

- *RestakeManager.sol* ( [2-4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L2-L4), [707-709](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol#L707-L709) ):

```solidity
2: pragma solidity 0.8.19;
3: 
4: import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";

707:     }
708: 
709:     function setTokenTvlLimit(IERC20 _token, uint256 _limit) external onlyRestakeManagerAdmin {
```

- *RestakeManagerStorage.sol* ( [2-4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManagerStorage.sol#L2-L4), [13-15](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManagerStorage.sol#L13-L15), [62-64](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManagerStorage.sol#L62-L64) ):

```solidity
2: pragma solidity 0.8.19;
3: 
4: import "./EigenLayer/interfaces/IStrategy.sol";

13: import "./Withdraw/IWithdrawQueue.sol";
14: 
15: abstract contract RestakeManagerStorageV1 is IRestakeManager {

62: }
63: 
64: abstract contract RestakeManagerStorageV2 is RestakeManagerStorageV1 {
```

- *RewardHandler.sol* ( [2-4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Rewards/RewardHandler.sol#L2-L4), [60-62](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Rewards/RewardHandler.sol#L60-L62), [70-72](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Rewards/RewardHandler.sol#L70-L72) ):

```solidity
2: pragma solidity 0.8.19;
3: 
4: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

60:     }
61: 
62:     function _forwardETH() internal {

70:     }
71: 
72:     function setRewardDestination(
```

- *RewardHandlerStorage.sol* ( [2-4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Rewards/RewardHandlerStorage.sol#L2-L4), [4-6](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Rewards/RewardHandlerStorage.sol#L4-L6) ):

```solidity
2: pragma solidity 0.8.19;
3: 
4: import "../Permissions/IRoleManager.sol";

4: import "../Permissions/IRoleManager.sol";
5: 
6: abstract contract RewardHandlerStorageV1 {
```

- *TimelockController.sol* ( [4-6](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol#L4-L6) ):

```solidity
4: pragma solidity ^0.8.0;
5: 
6: import "@openzeppelin/contracts/access/AccessControl.sol";
```

- *WithdrawQueue.sol* ( [2-4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L2-L4), [9-11](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L9-L11), [48-50](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol#L48-L50) ):

```solidity
2: pragma solidity 0.8.19;
3: 
4: import "./WithdrawQueueStorage.sol";

9: import "@openzeppelin/contracts/token/ERC20/IERC20.sol";
10: 
11: contract WithdrawQueue is

48:     }
49: 
50:     modifier onlyDepositQueue() {
```

- *WithdrawQueueStorage.sol* ( [2-4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueueStorage.sol#L2-L4), [7-9](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueueStorage.sol#L7-L9) ):

```solidity
2: pragma solidity 0.8.19;
3: 
4: import "../Permissions/IRoleManager.sol";

7: import "../token/IEzEthToken.sol";
8: 
9: abstract contract WithdrawQueueStorageV1 {
```

- *EzEthToken.sol* ( [2-4](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/token/EzEthToken.sol#L2-L4) ):

```solidity
2: pragma solidity ^0.8.9;
3: 
4: import "@openzeppelin/contracts-upgradeable/token/ERC20/ERC20Upgradeable.sol";
```

- *EzEthTokenStorage.sol* ( [2-3](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/token/EzEthTokenStorage.sol#L2-L3) ):

```solidity
2: pragma solidity 0.8.19;
3: import "../Permissions/IRoleManager.sol";
```

</details>

### [N-72] Consider adding formal verification proofs

Formal verification is the act of proving or disproving the correctness of intended algorithms underlying a system with respect to a certain formal specification/property/invariant, using formal methods of mathematics.

Some tools that are currently available to perform these tests on smart contracts are [SMTChecker](https://docs.soliditylang.org/en/latest/smtchecker.html) and [Certora Prover](https://www.certora.com/).

<details>
<summary>There are 40 instances (click to show):</summary>

- [*LockboxAdapterBlast.sol*](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol)

- [*LibConnextStorage.sol*](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/Connext/libraries/LibConnextStorage.sol)

- [*TokenId.sol*](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/Connext/libraries/TokenId.sol)

- [*xRenzoBridge.sol*](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol)

- [*xRenzoBridgeStorage.sol*](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridgeStorage.sol)

- [*RenzoOracleL2.sol*](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/Oracle/RenzoOracleL2.sol)

- [*RenzoOracleL2Storage.sol*](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/Oracle/RenzoOracleL2Storage.sol)

- [*CCIPReceiver.sol*](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol)

- [*ConnextReceiver.sol*](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol)

- [*xRenzoDeposit.sol*](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol)

- [*xRenzoDepositStorage.sol*](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDepositStorage.sol)

- [*XERC20.sol*](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20.sol)

- [*XERC20Factory.sol*](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Factory.sol)

- [*XERC20Lockbox.sol*](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol)

- [*OptimismMintableXERC20.sol*](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol)

- [*OptimismMintableXERC20Factory.sol*](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol)

- [*OperatorDelegator.sol*](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol)

- [*OperatorDelegatorStorage.sol*](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegatorStorage.sol)

- [*DepositQueue.sol*](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol)

- [*DepositQueueStorage.sol*](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueueStorage.sol)

- [*Errors.sol*](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Errors/Errors.sol)

- [*WBETHShim.sol*](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Binance/WBETHShim.sol)

- [*WBETHShimStorage.sol*](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Binance/WBETHShimStorage.sol)

- [*METHShim.sol*](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Mantle/METHShim.sol)

- [*METHShimStorage.sol*](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/Mantle/METHShimStorage.sol)

- [*RenzoOracle.sol*](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol)

- [*RenzoOracleStorage.sol*](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracleStorage.sol)

- [*RoleManager.sol*](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Permissions/RoleManager.sol)

- [*RoleManagerStorage.sol*](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Permissions/RoleManagerStorage.sol)

- [*BalancerRateProvider.sol*](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RateProvider/BalancerRateProvider.sol)

- [*BalancerRateProviderStorage.sol*](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RateProvider/BalancerRateProviderStorage.sol)

- [*RestakeManager.sol*](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManager.sol)

- [*RestakeManagerStorage.sol*](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/RestakeManagerStorage.sol)

- [*RewardHandler.sol*](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Rewards/RewardHandler.sol)

- [*RewardHandlerStorage.sol*](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Rewards/RewardHandlerStorage.sol)

- [*TimelockController.sol*](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/TimelockController.sol)

- [*WithdrawQueue.sol*](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueue.sol)

- [*WithdrawQueueStorage.sol*](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Withdraw/WithdrawQueueStorage.sol)

- [*EzEthToken.sol*](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/token/EzEthToken.sol)

- [*EzEthTokenStorage.sol*](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/token/EzEthTokenStorage.sol)

</details>

### [N-73] Numeric values having to do with time should use time units for readability

There are [time units](https://docs.soliditylang.org/en/latest/units-and-global-variables.html#time-units) for seconds, minutes, hours, days, and weeks, and since they're defined, they should be used.

There are 2 instances:

- *RenzoOracleL2.sol* ( [13-13](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L13-L13) ):

```solidity
/// @audit 86400
13:     uint256 public constant MAX_TIME_WINDOW = 86400 + 60; // 24 hours + 60 seconds
```

- *RenzoOracle.sol* ( [26-26](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L26-L26) ):

```solidity
/// @audit 86400
26:     uint256 constant MAX_TIME_WINDOW = 86400 + 60; // 24 hours + 60 seconds
```
