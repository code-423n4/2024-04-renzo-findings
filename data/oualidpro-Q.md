## Summary

### Low Risk Issues

| |Issue|Instances|
|-|:-|:-:|
| [[L&#x2011;1](#l1-vulnerable-versions-of-packages-are-being-used)] | Vulnerable versions of packages are being used | 1 | 
| [[L&#x2011;2](#l2-setuprole-function-is-deprecated)] | `_setupRole` function is deprecated | 5 | 
| [[L&#x2011;3](#l3-constant-decimal-values)] | Constant decimal values | 2 | 
| [[L&#x2011;4](#l4-increase-decrease-or-forceapprove-allowance-should-be-used-instead-of-approve)] | increase/decrease or forceApprove allowance should be used instead of approve | 1 | 
| [[L&#x2011;5](#l5-initialization-can-be-front-run)] | Initialization can be front-run | 15 | 
| [[L&#x2011;6](#l6-loss-of-precision)] | Loss of precision | 7 | 
| [[L&#x2011;7](#l7-missing-contract-existence-checks-before-low-level-calls)] | Missing contract-existence checks before low-level calls | 1 | 
| [[L&#x2011;8](#l8-no-limits-when-setting-min-max-amounts)] | No limits when setting min/max amounts | 1 | 
| [[L&#x2011;9](#l9-onlyowner-functions-not-accessible-if-owner-renounces-ownership)] | `onlyOwner` functions not accessible if `owner` renounces ownership | 10 | 
| [[L&#x2011;10](#l10-owner-can-renounce-while-system-is-paused)] | Owner can renounce while system is paused | 2 | 
| [[L&#x2011;11](#l11-governance-operations-should-be-behind-a-timelock)] | Governance operations should be behind a timelock | 71 | 
| [[L&#x2011;12](#l12-consider-using-openzeppelin-s-safecast-library-to-prevent-unexpected-overflows-when-casting-from-various-type-int-uint-values)] | Consider using OpenZeppelin’s SafeCast library to prevent unexpected overflows when casting from various type int/uint values | 4 | 
| [[L&#x2011;13](#l13-setters-should-have-initial-value-check)] | Setters should have initial value check | 7 | 
| [[L&#x2011;14](#l14-solidity-version-0-8-20-may-not-work-on-other-chains-due-to-push0)] | Solidity version 0.8.20 may not work on other chains due to `PUSH0` | 1 | 
| [[L&#x2011;15](#l15-unsafe-downcast)] | Unsafe downcast | 1 | 
| [[L&#x2011;16](#l16-unsafe-erc20-operation-approve)] | Unsafe ERC20 operation `approve()` | 1 | 
| [[L&#x2011;17](#l17-unspecific-compiler-version-pragma)] | Unspecific compiler version pragma | 5 | 
| [[L&#x2011;18](#l18-unused-empty-receive-fallback-function)] | Unused/empty `receive()`/`fallback()` function | 3 | 
| [[L&#x2011;19](#l19-upgradeable-contract-uses-non-upgradeable-version-of-the-openzeppelin-libraries-contracts)] | Upgradeable contract uses non-upgradeable version of the OpenZeppelin libraries/contracts | 10 | 
| [[L&#x2011;20](#l20-upgradeable-contract-is-missing-a-gap-50-storage-variable-to-allow-for-new-storage-variables-in-later-versions)] | Upgradeable contract is missing a `__gap[50]` storage variable to allow for new storage variables in later versions | 13 | 
| [[L&#x2011;21](#l21-safeapprove-is-deprecated)] | `safeApprove()` is deprecated | 11 | 
| [[L&#x2011;22](#l22-consider-using-descriptive-constant-s-when-passing-zero-as-a-function-argument)] | Consider using descriptive `constant`s when passing zero as a function argument | 5 | 
| [[L&#x2011;23](#l23-check-of-division-by-zero)] | Check of division by zero | 3 | 
| [[L&#x2011;24](#l24-privileged-functions-can-create-points-of-failure)] | Privileged functions can create points of failure | 68 | 
| [[L&#x2011;25](#l25-functions-calling-contracts-addresses-with-transfer-hooks-are-missing-reentrancy-guards)] | Functions calling contracts/addresses with transfer hooks are missing reentrancy guards | 2 | 
| [[L&#x2011;26](#l26-some-function-should-not-be-marked-as-payable)] | Some function should not be marked as payable | 1 | 
| [[L&#x2011;27](#l27-code-does-not-follow-the-best-practice-of-check-effects-interaction)] | Code does not follow the best practice of check-effects-interaction | 1 | 
| [[L&#x2011;28](#l28-prevent-re-setting-a-state-variable-with-the-same-value)] | prevent re-setting a state variable with the same value | 13 | 
| [[L&#x2011;29](#l29-use-of-tx-origin-is-unsafe-in-almost-every-context)] | Use of `tx.origin` is unsafe in almost every context | 6 | 
| [[L&#x2011;30](#l30-missing-checks-in-initializer-function)] | Missing checks in initializer function | 1 | 
| [[L&#x2011;31](#l31-variables-shadowing-other-definitions)] | Variables shadowing other definitions | 11 | 
| [[L&#x2011;32](#l32-solidity-bug-in-legacy-code-generation-when-accessing-the-selector-member-on-expressions-with-side-effects)] | [Solidity]: Bug in Legacy Code Generation When Accessing the .selector Member on Expressions with Side Effects | 1 | 
| [[L&#x2011;33](#l33-empty-receive-functions-can-cause-gas-issues)] | Empty receive functions can cause gas issues | 3 | 

Total: 287 instances over 33 issues

### Non-critical Issues

| |Issue|Instances|
|-|:-|:-:|
| [[NC&#x2011;1](#nc1-consider-using-modifiers-for-address-control)] | Consider using modifiers for address control | 7 | 
| [[NC&#x2011;2](#nc2-natspec-natspec-author-is-missing-from-contract)] | [NatSpec] Natspec `@author` is missing from `contract` | 45 | 
| [[NC&#x2011;3](#nc3-avoid-the-use-of-sensitive-terms)] | Avoid the use of sensitive terms | 17 | 
| [[NC&#x2011;4](#nc4-variable-names-that-consist-of-all-capital-letters-should-be-reserved-for-constant-immutable-variables)] | Variable names that consist of all capital letters should be reserved for `constant`/`immutable` variables | 4 | 
| [[NC&#x2011;5](#nc5-common-functions-should-be-refactored-to-a-common-base-contract)] | Common functions should be refactored to a common base contract | 7 | 
| [[NC&#x2011;6](#nc6-overly-complicated-arithmetic)] | Overly complicated arithmetic | 1 | 
| [[NC&#x2011;7](#nc7-constant-redefined-elsewhere)] | Constant redefined elsewhere | 4 | 
| [[NC&#x2011;8](#nc8-constants-in-comparisons-should-appear-on-the-left-side)] | Constants in comparisons should appear on the left side | 79 | 
| [[NC&#x2011;9](#nc9-natspec-natspec-description-is-missing-from-contract)] | [NatSpec] Natspec description is missing from `contract` | 133 | 
| [[NC&#x2011;10](#nc10-contract-does-not-follow-the-solidity-style-guide-s-suggested-layout-ordering)] | Contract does not follow the Solidity style guide's suggested layout ordering | 3 | 
| [[NC&#x2011;11](#nc11-control-structures-do-not-follow-the-solidity-style-guide)] | Control structures do not follow the Solidity Style Guide | 81 | 
| [[NC&#x2011;12](#nc12-custom-error-has-no-error-details)] | Custom error has no error details | 43 | 
| [[NC&#x2011;13](#nc13-default-address-0-can-be-returned)] | Default address(0) can be returned | 2 | 
| [[NC&#x2011;14](#nc14-consider-using-delete-rather-than-assigning-zero-to-clear-values)] | Consider using `delete` rather than assigning `zero` to clear values | 2 | 
| [[NC&#x2011;15](#nc15-dependence-on-external-protocols)] | Dependence on external protocols | 9 | 
| [[NC&#x2011;16](#nc16-else-block-not-required)] | `else`-block not required | 4 | 
| [[NC&#x2011;17](#nc17-consider-adding-emergency-stop-functionality)] | Consider adding emergency-stop functionality | 1 | 
| [[NC&#x2011;18](#nc18-empty-bytes-check-is-missing)] | Empty bytes check is missing | 20 | 
| [[NC&#x2011;19](#nc19-events-are-missing-sender-information)] | Events are missing sender information | 69 | 
| [[NC&#x2011;20](#nc20-events-may-be-emitted-out-of-order-due-to-reentrancy)] | Events may be emitted out of order due to reentrancy | 10 | 
| [[NC&#x2011;21](#nc21-explicitly-define-visibility-of-state-variables-to-prevent-misconceptions-on-what-can-access-the-variable)] | Explicitly define visibility of state variables to prevent misconceptions on what can access the variable | 6 | 
| [[NC&#x2011;22](#nc22-defining-all-external-public-functions-in-contract-interfaces)] | Defining All External/Public Functions in Contract Interfaces | 69 | 
| [[NC&#x2011;23](#nc23-fixed-compiler-version-required-for-non-library-interface-files)] | Fixed Compiler Version Required for Non-Library/Interface Files | 8 | 
| [[NC&#x2011;24](#nc24-floating-pragma-should-be-avoided)] | Floating pragma should be avoided | 8 | 
| [[NC&#x2011;25](#nc25-function-ordering-does-not-follow-the-solidity-style-guide)] | Function ordering does not follow the Solidity style guide | 19 | 
| [[NC&#x2011;26](#nc26-address-s-shouldn-t-be-hard-coded)] | `address`s shouldn't be hard-coded | 3 | 
| [[NC&#x2011;27](#nc27-array-indicies-should-be-referenced-via-enum-s-rather-than-via-numeric-literals)] | Array indicies should be referenced via `enum`s rather than via numeric literals | 15 | 
| [[NC&#x2011;28](#nc28-hardcoded-string-that-is-repeatedly-used-can-be-replaced-with-a-constant)] | Hardcoded string that is repeatedly used can be replaced with a constant | 2 | 
| [[NC&#x2011;29](#nc29-duplicated-require-checks-should-be-refactored-to-a-modifier-or-function)] | Duplicated `require()` checks should be refactored to a modifier or function | 3 | 
| [[NC&#x2011;30](#nc30-some-if-statement-can-be-converted-to-a-ternary)] | Some if-statement can be converted to a ternary | 3 | 
| [[NC&#x2011;31](#nc31-imports-could-be-organized-more-systematically)] | Imports could be organized more systematically | 16 | 
| [[NC&#x2011;32](#nc32-import-declarations-should-import-specific-identifiers-rather-than-the-whole-file)] | Import declarations should import specific identifiers, rather than the whole file | 138 | 
| [[NC&#x2011;33](#nc33-inconsistent-spacing-in-comments)] | Inconsistent spacing in comments | 1 | 
| [[NC&#x2011;34](#nc34-inconsistent-usage-of-require-error)] | Inconsistent usage of `require`/`error` | 12 | 
| [[NC&#x2011;35](#nc35-inconsistent-method-of-specifying-a-floating-pragma)] | Inconsistent method of specifying a floating pragma | 5 | 
| [[NC&#x2011;36](#nc36-incorrect-natspec-syntax)] | Incorrect NatSpec Syntax | 1 | 
| [[NC&#x2011;37](#nc37-interfaces-should-be-indicated-with-an-i-prefix-in-the-contract-name)] | Interfaces should be indicated with an `I` prefix in the contract name | 1 | 
| [[NC&#x2011;38](#nc38-interfaces-should-be-defined-in-separate-files-from-their-usage)] | Interfaces should be defined in separate files from their usage | 2 | 
| [[NC&#x2011;39](#nc39-large-numeric-literals-should-use-underscores-for-readability)] | Large numeric literals should use underscores for readability | 6 | 
| [[NC&#x2011;40](#nc40-long-functions-should-be-refactored-into-multiple-smaller-functions)] | Long functions should be refactored into multiple, smaller, functions | 13 | 
| [[NC&#x2011;41](#nc41-long-lines-of-code)] | Long lines of code | 28 | 
| [[NC&#x2011;42](#nc42-missing-event-and-or-timelock-for-critical-parameter-change)] | Missing event and or timelock for critical parameter change | 3 | 
| [[NC&#x2011;43](#nc43-file-is-missing-natspec)] | File is missing NatSpec | 4 | 
| [[NC&#x2011;44](#nc44-mixed-usage-of-int-uint-with-int256-uint256)] | Mixed usage of `int`/`uint` with `int256`/`uint256` | 2 | 
| [[NC&#x2011;45](#nc45-consider-using-named-mappings)] | Consider using named mappings | 15 | 
| [[NC&#x2011;46](#nc46-consider-using-later-versions-of-solidity-for-more-cappabilities)] | Consider using later versions of solidity for more cappabilities | 4 | 
| [[NC&#x2011;47](#nc47-the-nonreentrant-modifier-should-occur-before-all-other-modifiers)] | The `nonReentrant` `modifier` should occur before all other modifiers | 2 | 
| [[NC&#x2011;48](#nc48-events-that-mark-critical-parameter-changes-should-contain-both-the-old-and-the-new-value)] | Events that mark critical parameter changes should contain both the old and the new value | 12 | 
| [[NC&#x2011;49](#nc49-use-of-override-is-unnecessary)] | Use of `override` is unnecessary | 9 | 
| [[NC&#x2011;50](#nc50-public-functions-not-called-by-the-contract-should-be-declared-external-instead)] | `public` functions not called by the contract should be declared `external` instead | 34 | 
| [[NC&#x2011;51](#nc51-adding-a-return-statement-when-the-function-defines-a-named-return-variable-is-redundant)] | Adding a `return` statement when the function defines a named return variable, is redundant | 1 | 
| [[NC&#x2011;52](#nc52-redundant-inheritance-specifier)] | Redundant inheritance specifier | 13 | 
| [[NC&#x2011;53](#nc53-setters-should-prevent-re-setting-of-the-same-value)] | Setters should prevent re-setting of the same value | 14 | 
| [[NC&#x2011;54](#nc54-natspec-return-argument-is-missing)] | NatSpec `@return` argument is missing | 43 | 
| [[NC&#x2011;55](#nc55-consider-using-safetransferlib-safetransfereth-or-address-sendvalue-for-clearer-semantic-meaning)] | Consider using `SafeTransferLib.safeTransferETH()` or `Address.sendValue()` for clearer semantic meaning | 7 | 
| [[NC&#x2011;56](#nc56-polymorphic-functions-make-security-audits-more-time-consuming-and-error-prone)] | Polymorphic functions make security audits more time-consuming and error-prone | 2 | 
| [[NC&#x2011;57](#nc57-large-multiples-of-ten-should-use-scientific-notation-e-g-1e6-rather-than-decimal-literals-e-g-1000000-for-readability)] | Large multiples of ten should use scientific notation (e.g. `1e6`) rather than decimal literals (e.g. `1000000`), for readability | 5 | 
| [[NC&#x2011;58](#nc58-consider-moving-msg-sender-checks-to-a-common-authorization-modifier)] | Consider moving `msg.sender` checks to a common authorization `modifier` | 1 | 
| [[NC&#x2011;59](#nc59-empty-receive-payable-fallback-function-does-not-authorize-requests)] | Empty `receive()`/`payable fallback()` function does not authorize requests | 3 | 
| [[NC&#x2011;60](#nc60-state-variables-should-have-natspec-comments)] | State variables should have `Natspec` comments | 22 | 
| [[NC&#x2011;61](#nc61-contracts-should-have-full-test-coverage)] | Contracts should have full test coverage | 1 | 
| [[NC&#x2011;62](#nc62-numeric-values-having-to-do-with-time-should-use-time-units-for-readability)] | Numeric values having to do with time should use time units for readability | 2 | 
| [[NC&#x2011;63](#nc63-natspec-natspec-title-is-missing-from-contract)] | [NatSpec] Natspec `@title` is missing from `contract` | 38 | 
| [[NC&#x2011;64](#nc64-top-level-pragma-declarations-should-be-separated-by-two-blank-lines)] | Top level pragma declarations should be separated by two blank lines | 59 | 
| [[NC&#x2011;65](#nc65-critical-functions-should-be-a-two-step-procedure)] | Critical functions should be a two step procedure | 33 | 
| [[NC&#x2011;66](#nc66-typos)] | Typos | 5 | 
| [[NC&#x2011;67](#nc67-uint-variables-should-have-the-bit-size-defined-explicitly)] | uint variables should have the bit size defined explicitly | 2 | 
| [[NC&#x2011;68](#nc68-uncommented-fields-in-a-struct)] | Uncommented fields in a struct | 4 | 
| [[NC&#x2011;69](#nc69-event-is-missing-indexed-fields)] | Event is missing `indexed` fields | 60 | 
| [[NC&#x2011;70](#nc70-unused-error-definition)] | Unused `error` definition | 3 | 
| [[NC&#x2011;71](#nc71-unused-event-definition)] | Unused `event` definition | 2 | 
| [[NC&#x2011;72](#nc72-unused-import)] | Unused Import | 25 | 
| [[NC&#x2011;73](#nc73-unused-internal-private-contract-variable)] | Unused `internal`/`private` contract variable | 1 | 
| [[NC&#x2011;74](#nc74-missing-upgradability-functionality)] | Missing upgradability functionality | 1 | 
| [[NC&#x2011;75](#nc75-constants-should-be-defined-rather-than-using-magic-numbers)] | Constants should be defined rather than using magic numbers | 32 | 
| [[NC&#x2011;76](#nc76-use-inheritdoc-rather-than-using-a-non-standard-annotation)] | Use `@inheritdoc` rather than using a non-standard annotation | 4 | 
| [[NC&#x2011;77](#nc77-use-the-latest-solidity-prior-to-0-8-20-if-on-l2s-for-deployment)] | Use the latest solidity (prior to 0.8.20 if on L2s) for deployment | 35 | 
| [[NC&#x2011;78](#nc78-use-a-single-file-for-system-wide-constants)] | Use a single file for system wide constants | 11 | 
| [[NC&#x2011;79](#nc79-consider-using-smtchecker)] | Consider using SMTChecker | 40 | 
| [[NC&#x2011;80](#nc80-variable-name-must-be-in-mixedcase)] | Variable name must be in mixedCase | 1 | 
| [[NC&#x2011;81](#nc81-whitespace-in-expressions)] | Whitespace in Expressions | 40 | 
| [[NC&#x2011;82](#nc82-complex-function-controle-flow)] | Complex function controle flow | 1 | 
| [[NC&#x2011;83](#nc83-consider-bounding-input-array-length)] | Consider bounding input array length | 17 | 
| [[NC&#x2011;84](#nc84-a-function-which-defines-named-returns-in-it-s-declaration-doesn-t-need-to-use-return)] | A function which defines named returns in it's declaration doesn't need to use return | 2 | 
| [[NC&#x2011;85](#nc85-natspec-natspec-dev-is-missing-from-contract)] | [NatSpec] Natspec `@dev` is missing from `contract` | 155 | 
| [[NC&#x2011;86](#nc86-contract-should-expose-an-interface)] | Contract should expose an `interface` | 69 | 
| [[NC&#x2011;87](#nc87-named-imports-of-parent-contracts-are-missing)] | Named imports of parent contracts are missing | 68 | 
| [[NC&#x2011;88](#nc88-natspec-natspec-notice-is-missing-from-contract)] | [NatSpec] Natspec `@notice` is missing from `contract` | 327 | 
| [[NC&#x2011;89](#nc89-contract-names-should-use-camelcase)] | `contract` names should use CamelCase | 6 | 
| [[NC&#x2011;90](#nc90-expressions-for-constant-values-should-use-immutable-rather-than-constant)] | Expressions for constant values should use `immutable` rather than `constant` | 19 | 
| [[NC&#x2011;91](#nc91-consider-using-accesscontroldefaultadminrules-rather-than-accesscontrol)] | Consider using `AccessControlDefaultAdminRules` rather than `AccessControl` | 1 | 
| [[NC&#x2011;92](#nc92-immutable-variable-names-don-t-follow-the-solidity-style-guide)] | `immutable` variable names don\'t follow the Solidity style guide | 2 | 
| [[NC&#x2011;93](#nc93-add-inline-comments-for-unnamed-parameters)] | Add inline comments for unnamed parameters | 7 | 
| [[NC&#x2011;94](#nc94-use-the-latest-solidity-version-for-better-security)] | Use the latest Solidity version for better security | 40 | 
| [[NC&#x2011;95](#nc95-consider-adding-formal-verification-proofs)] | Consider adding formal verification proofs | 1 | 
| [[NC&#x2011;96](#nc96-missing-zero-address-check-in-functions-with-address-parameters)] | Missing zero address check in functions with address parameters | 3 | 
| [[NC&#x2011;97](#nc97-use-a-struct-to-encapsulate-multiple-function-parameters)] | Use a struct to encapsulate multiple function parameters | 25 | 
| [[NC&#x2011;98](#nc98-use-custom-errors-rather-than-revert-require-strings-for-better-readability)] | Use custom errors rather than `revert()`/`require()` strings for better readability | 12 | 
| [[NC&#x2011;99](#nc99-use-inheritdoc-for-overridden-functions)] | Use `@inheritdoc` for overridden functions | 15 | 
| [[NC&#x2011;100](#nc100-multiple-mappings-with-same-keys-can-be-combined-into-a-single-struct-mapping-for-readability)] | Multiple mappings with same keys can be combined into a single struct mapping for readability | 5 | 
| [[NC&#x2011;101](#nc101-constructor-should-emit-an-event)] | constructor should emit an event | 22 | 
| [[NC&#x2011;102](#nc102-error-should-be-named-using-capwords-style)] | `error` should be named using CapWords style | 1 | 
| [[NC&#x2011;103](#nc103-use-erc1155holder-over-erc1155receiver)] | Use `ERC1155Holder` over `ERC1155Receiver` | 1 | 
| [[NC&#x2011;104](#nc104-complex-functions-should-include-comments)] | Complex functions should include comments | 3 | 
| [[NC&#x2011;105](#nc105-make-use-of-solidiy-s-using-keyword)] | Make use of Solidiy's `using` keyword | 20 | 
| [[NC&#x2011;106](#nc106-solidity-all-verbatim-blocks-are-considered-identical-by-deduplicator-and-can-incorrectly-be-unified)] | [Solidity]: All `verbatim` blocks are considered identical by deduplicator and can incorrectly be unified | 32 | 
| [[NC&#x2011;107](#nc107-natspec-natspec-param-is-missing-from-error)] | [NatSpec] Natspec `@param` is missing from `error` | 164 | 
| [[NC&#x2011;108](#nc108-openzeppelin-libraries-should-be-upgraded-to-a-newer-version)] | OpenZeppelin libraries should be upgraded to a newer version | 104 | 
| [[NC&#x2011;109](#nc109-not-using-the-latest-version-of-prb-math-from-dependencies)] | Not using the latest version of `prb-math` from dependencies | 1 | 
| [[NC&#x2011;110](#nc110-non-constant-immutable-state-variables-are-missing-a-setter-post-deployment)] | Non constant/immutable state variables are missing a setter post deployment | 82 | 
| [[NC&#x2011;111](#nc111-consider-making-private-state-variables-internal-to-increase-flexibility)] | Consider making private state variables internal to increase flexibility | 3 | 
| [[NC&#x2011;112](#nc112-using-low-level-call-for-transfers)] | Using Low-Level Call for Transfers | 7 | 
| [[NC&#x2011;113](#nc113-off-by-one-timestamp-error)] | Off-by-one timestamp error | 2 | 
| [[NC&#x2011;114](#nc114-lack-of-space-near-the-operator)] | Lack of space near the operator | 8 | 
| [[NC&#x2011;115](#nc115-incorrect-withdraw-declaration)] | Incorrect withdraw declaration | 2 | 
| [[NC&#x2011;116](#nc116-avoid-mutating-function-parameters)] | Avoid mutating function parameters | 2 | 
| [[NC&#x2011;117](#nc117-a-event-should-be-emitted-if-a-non-immutable-state-variable-is-set-in-a-constructor)] | A event should be emitted if a non immutable state variable is set in a constructor | 7 | 
| [[NC&#x2011;118](#nc118-returning-a-struct-instead-of-returning-many-variables-is-better)] | Returning a struct instead of returning many variables is better | 6 | 
| [[NC&#x2011;119](#nc119-solidity-order-of-argument-evaluation-disrupted-in-non-expression-split-code-by-optimizer-sequences-with-fullinliner)] | [Solidity]: Order of Argument Evaluation Disrupted in Non-Expression-Split Code by Optimizer Sequences with FullInliner | 35 | 
| [[NC&#x2011;120](#nc120-not-using-the-named-return-variables-anywhere-in-the-function-is-confusing)] | Not using the named return variables anywhere in the function is confusing | 6 | 
| [[NC&#x2011;121](#nc121-use-named-return-values)] | Use named return values | 68 | 
| [[NC&#x2011;122](#nc122-consider-moving-duplicated-strings-to-constants)] | Consider moving duplicated strings to constants | 4 | 
| [[NC&#x2011;123](#nc123-unused-public-contract-variable)] | Unused `public` contract variable | 2 | 
| [[NC&#x2011;124](#nc124-missing-checks-for-uint-state-variable-assignments)] | Missing checks for uint state variable assignments | 7 | 
| [[NC&#x2011;125](#nc125-consider-adding-validation-of-user-inputs)] | Consider adding validation of user inputs | 80 | 
| [[NC&#x2011;126](#nc126-consider-disallowing-transfers-to-address-this)] | Consider disallowing transfers to `address(this)` | 3 | 
| [[NC&#x2011;127](#nc127-unusual-loop-variable)] | Unusual loop variable | 2 | 
| [[NC&#x2011;128](#nc128-consider-using-named-function-calls)] | Consider using named function calls | 73 | 

Total: 3017 instances over 128 issues

## Low Risk Issues

### [L&#x2011;1] Vulnerable versions of packages are being used 
This project's specific package versions are vulnerable to the specific CVEs listed below. Consider switching to more recent versions of these packages that don't have these vulnerabilities


*There are 1 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: package.json


<details><summary>Vulnerabilities related to `@openzeppelin/contracts`:</summary>


- [CVE-2022-31170](https://github.com/OpenZeppelin/openzeppelin-contracts/security/advisories/GHSA-qh9x-gcfh-pcrw) :ERC165Checker.supportsInterface is designed to always successfully return a boolean, and under no circumstance revert. However, an incorrect assumption about Solidity 0.8's abi.decode allows some cases to revert, given a target contract that doesn't implement EIP-165 as expected, specifically if it returns a value other than 0 or 1.

The contracts that may be affected are those that use ERC165Checker to check for support for an interface and then handle the lack of support in a way other than reverting.


- [CVE-2022-31172](https://github.com/OpenZeppelin/openzeppelin-contracts/security/advisories/GHSA-4g63-c64m-25w9) :SignatureChecker.isValidSignatureNow is not expected to revert. However, an incorrect assumption about Solidity 0.8's abi.decode allows some cases to revert, given a target contract that doesn't implement EIP-1271 as expected.

The contracts that may be affected are those that use SignatureChecker to check the validity of a signature and handle invalid signatures in a way other than reverting. We believe this to be unlikely.


- [CVE-2022-31198](https://github.com/OpenZeppelin/openzeppelin-contracts/security/advisories/GHSA-xrc4-737v-9q75) :This issue concerns instances of Governor that use the module GovernorVotesQuorumFraction, a mechanism that determines quorum requirements as a percentage of the voting token's total supply. In affected instances, when a proposal is passed to lower the quorum requirement, past proposals may become executable if they had been defeated only due to lack of quorum, and the number of votes it received meets the new quorum requirement.

Analysis of instances on chain found only one proposal that met this condition, and we are actively monitoring for new occurrences of this particular issue.


- [CVE-2022-35915](https://github.com/OpenZeppelin/openzeppelin-contracts/security/advisories/GHSA-7grf-83vw-6f5x) :This issue concerns instances of Governor that use the module GovernorVotesQuorumFraction, a mechanism that determines quorum requirements as a percentage of the voting token's total supply. In affected instances, when a proposal is passed to lower the quorum requirement, past proposals may become executable if they had been defeated only due to lack of quorum, and the number of votes it received meets the new quorum requirement.

Analysis of instances on chain found only one proposal that met this condition, and we are actively monitoring for new occurrences of this particular issue.


- [CVE-2022-35961](https://github.com/OpenZeppelin/openzeppelin-contracts/security/advisories/GHSA-4h98-2769-gh6h) :The functions ECDSA.recover and ECDSA.tryRecover are vulnerable to a kind of signature malleability due to accepting EIP-2098 compact signatures in addition to the traditional 65 byte signature format. This is only an issue for the functions that take a single bytes argument, and not the functions that take r, v, s or r, vs as separate arguments.

The potentially affected contracts are those that implement signature reuse or replay protection by marking the signature itself as used rather than the signed message or a nonce included in it. A user may take a signature that has already been submitted, submit it again in a different form, and bypass this protection.


- [CVE-2021-46320](https://github.com/OpenZeppelin/openzeppelin-contracts/security/advisories/GHSA-9c22-pwxw-p6hx) :Initializer functions that are invoked separate from contract creation (the most prominent example being minimal proxies) may be reentered if they make an untrusted non-view external call.

Once an initializer has finished running it can never be re-executed. However, an exception put in place to support multiple inheritance made reentrancy possible in the scenario described above, breaking the expectation that there is a single execution.

Note that upgradeable proxies are commonly initialized together with contract creation, where reentrancy is not feasible, so the impact of this issue is believed to be minor.


- [CVE-2023-34234](https://github.com/OpenZeppelin/openzeppelin-contracts/security/advisories/GHSA-5h3x-9wvq-w4m2) :By frontrunning the creation of a proposal, an attacker can become the proposer and gain the ability to cancel it. The attacker can do this repeatedly to try to prevent a proposal from being proposed at all.
This impacts the Governor contract in v4.9.0 only, and the GovernorCompatibilityBravo contract since v4.3.0.


- [CVE-2023-30541](https://github.com/OpenZeppelin/openzeppelin-contracts/security/advisories/GHSA-mx2q-35m2-x2rh) :A function in the implementation contract may be inaccessible if its selector clashes with one of the proxy's own selectors. Specifically, if the clashing function has a different signature with incompatible ABI encoding, the proxy could revert while attempting to decode the arguments from calldata.
The probability of an accidental clash is negligible, but one could be caused deliberately.


- [CVE-2023-30542](https://github.com/OpenZeppelin/openzeppelin-contracts/security/advisories/GHSA-93hq-5wgc-jc82) :The proposal creation entrypoint (propose) in GovernorCompatibilityBravo allows the creation of proposals with a signatures array shorter than the calldatas array. This causes the additional elements of the latter to be ignored, and if the proposal succeeds the corresponding actions would eventually execute without any calldata. The ProposalCreated event correctly represents what will eventually execute, but the proposal parameters as queried through getActions appear to respect the original intended calldata.


- [No known CVE](https://github.com/OpenZeppelin/openzeppelin-contracts/security/advisories/GHSA-m6w8-fq7v-ph4m) :The GovernorCompatibilityBravo module may lead to the creation of governance proposals that execute function calls with incorrect arguments due to bad ABI encoding. This happens if the proposal is created using explicit function signatures, e.g. a proposal to invoke the function foo(uint256) is created as propose([target], [0], ["foo(uint256)"], ["0x00..01"]). If the function selector is provided as part of the encoded proposal data the issue is not present, e.g. the same proposal is created as propose([target], [0], ["0x2fbebd3800..01"]), where 2fbebd38 is the function selector.

We've assessed the instances of this contract found on chain, and did not find any occurrence of this bug in the past. Proposal creation through Tally or OpenZeppelin Defender is not affected. The core Governor contract on its own is not affected.
</details>
1: 


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//package.json#L1-L1) 


</details>


### [L&#x2011;2] `_setupRole` function is deprecated 
Check the following link for more details [Doc](https://docs.openzeppelin.com/contracts/4.x/api/access)


*There are 5 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/TimelockController.sol

99:         _setupRole(TIMELOCK_ADMIN_ROLE, address(this));

103:             _setupRole(TIMELOCK_ADMIN_ROLE, admin);

108:             _setupRole(PROPOSER_ROLE, proposers[i]);

109:             _setupRole(CANCELLER_ROLE, proposers[i]);

114:             _setupRole(EXECUTOR_ROLE, executors[i]);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L99-L99) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L103-L103), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L108-L108), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L109-L109), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L114-L114)


</details>


### [L&#x2011;3] Constant decimal values 
The use of fixed decimal values such as 1e18 or 1e8 in Solidity contracts can lead to inaccuracies, bugs, and vulnerabilities, particularly when interacting with tokens having different decimal configurations.Not all ERC20 tokens follow the standard 18 decimal places, and assumptions about decimal places can lead to miscalculations.
Always retrieve and use the `decimals()` function from the token contract itself when performing calculations involving token amounts.This ensures that your contract correctly handles tokens with any number of decimal places, mitigating the risk of numerical errors or under / overflows that could jeopardize contract integrity and user funds. 


*There are 2 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Bridge/L2/xRenzoDeposit.sol

253:         uint256 xezETHAmount = (1e18 * amountOut) / _lastPrice;

253:         uint256 xezETHAmount = (1e18 * amountOut) / _lastPrice;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L253-L253) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L253-L253)


</details>


### [L&#x2011;4] increase/decrease or forceApprove allowance should be used instead of approve 
In order to prevent front running, increase/decrease or forceApprove allowance should be used in place of approve where possible 


*There are 1 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Deposits/DepositQueue.sol

268:             token.approve(address(restakeManager), balance - feeAmount);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L268-L268) 


</details>


### [L&#x2011;5] Initialization can be front-run 
The `initialize()` functions are not protected by a modifier, which allow attackers to call this function once the contract is deployed through the proxy. Consider adding modifiers to protect this function or create a contract that both deploy the project and initialize it on the same transaction.


*There are 15 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Bridge/L1/xRenzoBridge.sol

70:     function initialize(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L70-L70) 


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2.sol

23:     function initialize(AggregatorV3Interface _oracle) public initializer {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L23-L23) 


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

75:     function initialize(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L75-L75) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Factory.sol

54:     function initialize(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L54-L54) 


```solidity

File: contracts/Delegation/OperatorDelegator.sol

74:     function initialize(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L74-L74) 


```solidity

File: contracts/Deposits/DepositQueue.sol

74:     function initialize(IRoleManager _roleManager) public initializer {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L74-L74) 


```solidity

File: contracts/Oracle/Binance/WBETHShim.sol

23:     function initialize(IStakedTokenV2 _wBETHToken) public initializer {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L23-L23) 


```solidity

File: contracts/Oracle/Mantle/METHShim.sol

23:     function initialize(IMethStaking _methStaking) public initializer {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L23-L23) 


```solidity

File: contracts/Oracle/RenzoOracle.sol

44:     function initialize(IRoleManager _roleManager) public initializer {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L44-L44) 


```solidity

File: contracts/Permissions/RoleManager.sol

22:     function initialize(address roleManagerAdmin) public initializer {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L22-L22) 


```solidity

File: contracts/RateProvider/BalancerRateProvider.sol

17:     function initialize(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProvider.sol#L17-L17) 


```solidity

File: contracts/RestakeManager.sol

101:     function initialize(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L101-L101) 


```solidity

File: contracts/Rewards/RewardHandler.sol

38:     function initialize(IRoleManager _roleManager, address _rewardDestination) public initializer {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L38-L38) 


```solidity

File: contracts/Withdraw/WithdrawQueue.sol

64:     function initialize(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L64-L64) 


```solidity

File: contracts/token/EzEthToken.sol

33:     function initialize(IRoleManager _roleManager) public initializer {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L33-L33) 


</details>


### [L&#x2011;6] Loss of precision 
Division by large numbers may result in the result being zero, due to solidity not supporting fractions. Consider requiring a minimum amount for the numerator to ensure that it is always larger than the denominator


*There are 7 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Bridge/L2/xRenzoDeposit.sol

253:         uint256 xezETHAmount = (1e18 * amountOut) / _lastPrice;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L253-L253) 


```solidity

File: contracts/Oracle/RenzoOracle.sol

97:         return (_value * SCALE_FACTOR) / uint256(price);

158:         uint256 redeemAmount = (_currentValueInProtocol * _ezETHBeingBurned) / _existingEzETHSupply;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L97-L97) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L158-L158)


```solidity

File: contracts/RestakeManager.sol

379:                 (operatorDelegatorAllocations[operatorDelegators[i]] * totalTVL) /

379:                 (operatorDelegatorAllocations[operatorDelegators[i]] * totalTVL) /

421:                 (operatorDelegatorAllocations[operatorDelegators[i]] * totalTVL) /

421:                 (operatorDelegatorAllocations[operatorDelegators[i]] * totalTVL) /


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L379-L379) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L379-L379), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L421-L421), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L421-L421)


</details>


### [L&#x2011;7] Missing contract-existence checks before low-level calls 
Low-level calls return success if there is no code present at the specified address. In addition to the zero-address checks, add a check to verify that `<address>.code.length > 0`


*There are 1 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/TimelockController.sol

369:         (bool success, ) = target.call{ value: value }(data);
370:         require(success, "TimelockController: underlying transaction reverted");


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L369-L370) 


</details>


### [L&#x2011;8] No limits when setting min/max amounts 
It is important to ensure that the min/max amounts are set to a reasonable value.


*There are 1 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/RestakeManager.sol

215:     function setMaxDepositTVL(uint256 _maxDepositTVL) external onlyRestakeManagerAdmin {
216:         maxDepositTVL = _maxDepositTVL;
217:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L215-L217) 


</details>


### [L&#x2011;9] `onlyOwner` functions not accessible if `owner` renounces ownership 
The `owner` is able to perform certain privileged activities, but it's possible to set the owner to `address(0)`. This can represent a certain risk if the ownership is renounced for any other reason than by design.
Renouncing ownership will leave the contract without an `owner`, therefore limiting any functionality that needs authority.


*There are 10 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol

96:     function updateXRenzoBridgeL1(address _newXRenzoBridgeL1) external onlyOwner {

107:     function updateCCIPEthChainSelector(uint64 _newChainSelector) external onlyOwner {

117:     function unPause() external onlyOwner {

125:     function pause() external onlyOwner {

134:     function setRenzoDeposit(address _newXRenzoDeposit) external onlyOwner {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L96-L96) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L107-L107), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L117-L117), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L125-L125), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L134-L134)


```solidity

File: contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol

92:     function updateXRenzoBridgeL1(address _newXRenzoBridgeL1) external onlyOwner {

103:     function updateCCIPEthChainSelector(uint32 _newChainDomain) external onlyOwner {

113:     function unPause() external onlyOwner {

121:     function pause() external onlyOwner {

130:     function setRenzoDeposit(address _newXRenzoDeposit) external onlyOwner {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L92-L92) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L103-L103), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L113-L113), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L121-L121), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L130-L130)


</details>


### [L&#x2011;10] Owner can renounce while system is paused 
The contract owner or single user with a role is not prevented from renouncing the role/ownership while the contract is paused, which would cause any user assets stored in the protocol, to be locked indefinitely


*There are 2 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol

43:     constructor(
44:         address _router,
45:         address _xRenzoBridgeL1,
46:         uint64 _ccipEthChainSelector
47:     ) CCIPReceiver(_router) {
48:         if (_xRenzoBridgeL1 == address(0) || _ccipEthChainSelector == 0) revert InvalidZeroInput();
49: 
50:         // Set xRenzoBridge L1 contract address
51:         xRenzoBridgeL1 = _xRenzoBridgeL1;
52: 
53:         // Set ccip source chain selector for Ethereum L1
54:         ccipEthChainSelector = _ccipEthChainSelector;
55: 
56:         // Pause The contract to setup xRenzoDeposit
57:         _pause();
58:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L43-L58) 


```solidity

File: contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol

52:     constructor(address _connext, address _xRenzoBridgeL1, uint32 _connextEthChainDomain) {
53:         if (_xRenzoBridgeL1 == address(0) || _connextEthChainDomain == 0 || _connext == address(0))
54:             revert InvalidZeroInput();
55: 
56:         // Set connext bridge address
57:         connext = _connext;
58: 
59:         // Set xRenzoBridge L1 contract address
60:         xRenzoBridgeL1 = _xRenzoBridgeL1;
61: 
62:         // Set connext source chain Domain Id for Ethereum L1
63:         connextEthChainDomain = _connextEthChainDomain;
64: 
65:         // Pause The contract to setup xRenzoDeposit
66:         _pause();
67:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L52-L67) 


</details>


### [L&#x2011;11] Governance operations should be behind a timelock 
All critical and governance operations should be protected by a timelock. For example from the point of view of a user, the changing of the owner of a contract is a high risk operation that may have outcomes ranging from an attacker gaining control over the protocol, to the function no longer functioning due to a typo in the destination address. To give users plenty of warning so that they can validate any ownership changes, changes of ownership should be behind a timelock.


*There are 71 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Bridge/L1/xRenzoBridge.sol

294:     function recoverNative(uint256 _amount, address _to) external onlyBridgeAdmin {
295:         payable(_to).transfer(_amount);
296:     }

305:     function recoverERC20(address _token, uint256 _amount, address _to) external onlyBridgeAdmin {
306:         IERC20(_token).safeTransfer(_to, _amount);
307:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L294-L296) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L305-L307)


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2.sol

36:     function setOracleAddress(AggregatorV3Interface _oracleAddress) external onlyOwner {
37:         if (address(_oracleAddress) == address(0)) revert InvalidZeroInput();
38:         // Verify that the pricing of the oracle is less than or equal to 18 decimals - pricing calculations will be off otherwise
39:         if (_oracleAddress.decimals() > 18)
40:             revert InvalidTokenDecimals(18, _oracleAddress.decimals());
41: 
42:         emit OracleAddressUpdated(address(_oracleAddress), address(oracle));
43:         oracle = _oracleAddress;
44:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L36-L44) 


```solidity

File: contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol

096:     function updateXRenzoBridgeL1(address _newXRenzoBridgeL1) external onlyOwner {
097:         if (_newXRenzoBridgeL1 == address(0)) revert InvalidZeroInput();
098:         emit XRenzoBridgeL1Updated(_newXRenzoBridgeL1, xRenzoBridgeL1);
099:         xRenzoBridgeL1 = _newXRenzoBridgeL1;
100:     }

107:     function updateCCIPEthChainSelector(uint64 _newChainSelector) external onlyOwner {
108:         if (_newChainSelector == 0) revert InvalidZeroInput();
109:         emit CCIPEthChainSelectorUpdated(_newChainSelector, ccipEthChainSelector);
110:         ccipEthChainSelector = _newChainSelector;
111:     }

117:     function unPause() external onlyOwner {
118:         _unpause();
119:     }

125:     function pause() external onlyOwner {
126:         _pause();
127:     }

134:     function setRenzoDeposit(address _newXRenzoDeposit) external onlyOwner {
135:         if (_newXRenzoDeposit == address(0)) revert InvalidZeroInput();
136:         emit XRenzoDepositUpdated(_newXRenzoDeposit, address(xRenzoDeposit));
137:         xRenzoDeposit = IxRenzoDeposit(_newXRenzoDeposit);
138:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L96-L100) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L107-L111), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L117-L119), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L125-L127), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L134-L138)


```solidity

File: contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol

69:     function xReceive(
70:         bytes32 _transferId,
71:         uint256,
72:         address,
73:         address _originSender,
74:         uint32 _origin,
75:         bytes memory _callData
76:     ) external onlySource(_originSender, _origin) whenNotPaused returns (bytes memory) {
77:         (uint256 _price, uint256 _timestamp) = abi.decode(_callData, (uint256, uint256));
78:         xRenzoDeposit.updatePrice(_price, _timestamp);
79: 
80:         emit MessageReceived(_transferId, _origin, _originSender, _price, _timestamp);
81:     }

92:     function updateXRenzoBridgeL1(address _newXRenzoBridgeL1) external onlyOwner {
93:         if (_newXRenzoBridgeL1 == address(0)) revert InvalidZeroInput();
94:         emit XRenzoBridgeL1Updated(_newXRenzoBridgeL1, xRenzoBridgeL1);
95:         xRenzoBridgeL1 = _newXRenzoBridgeL1;
96:     }

103:     function updateCCIPEthChainSelector(uint32 _newChainDomain) external onlyOwner {
104:         if (_newChainDomain == 0) revert InvalidZeroInput();
105:         emit ConnextEthChainDomainUpdated(_newChainDomain, connextEthChainDomain);
106:         connextEthChainDomain = _newChainDomain;
107:     }

113:     function unPause() external onlyOwner {
114:         _unpause();
115:     }

121:     function pause() external onlyOwner {
122:         _pause();
123:     }

130:     function setRenzoDeposit(address _newXRenzoDeposit) external onlyOwner {
131:         if (_newXRenzoDeposit == address(0)) revert InvalidZeroInput();
132:         emit XRenzoDepositUpdated(_newXRenzoDeposit, address(xRenzoDeposit));
133:         xRenzoDeposit = IxRenzoDeposit(_newXRenzoDeposit);
134:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L69-L81) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L92-L96), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L103-L107), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L113-L115), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L121-L123), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L130-L134)


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

466:     function setAllowedBridgeSweeper(address _sweeper, bool _allowed) external onlyOwner {
467:         allowedBridgeSweepers[_sweeper] = _allowed;
468: 
469:         emit BridgeSweeperAddressUpdated(_sweeper, _allowed);
470:     }

478:     function recoverNative(uint256 _amount, address _to) external onlyOwner {
479:         payable(_to).transfer(_amount);
480:     }

489:     function recoverERC20(address _token, uint256 _amount, address _to) external onlyOwner {
490:         IERC20(_token).safeTransfer(_to, _amount);
491:     }

501:     function setOraclePriceFeed(IRenzoOracleL2 _oracle) external onlyOwner {
502:         emit OraclePriceFeedUpdated(address(_oracle), address(oracle));
503:         oracle = _oracle;
504:     }

511:     function setReceiverPriceFeed(address _receiver) external onlyOwner {
512:         emit ReceiverPriceFeedUpdated(_receiver, receiver);
513:         receiver = _receiver;
514:     }

521:     function updateBridgeFeeShare(uint256 _newShare) external onlyOwner {
522:         if (_newShare > 100) revert InvalidBridgeFeeShare(_newShare);
523:         emit BridgeFeeShareUpdated(bridgeFeeShare, _newShare);
524:         bridgeFeeShare = _newShare;
525:     }

532:     function updateSweepBatchSize(uint256 _newBatchSize) external onlyOwner {
533:         if (_newBatchSize < 32 ether) revert InvalidSweepBatchSize(_newBatchSize);
534:         emit SweepBatchSizeUpdated(sweepBatchSize, _newBatchSize);
535:         sweepBatchSize = _newBatchSize;
536:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L466-L470) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L478-L480), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L489-L491), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L501-L504), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L511-L514), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L521-L525), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L532-L536)


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20.sol

76:     function __XERC20_init(
77:         string memory _name,
78:         string memory _symbol,
79:         address _factory
80:     ) internal onlyInitializing {
81:         __ERC20_init(_name, _symbol);
82:         __ERC20Permit_init(_name);
83:         __Ownable_init();
84: 
85:         _transferOwnership(_factory);
86:         FACTORY = _factory;
87:     }

135:     function setLimits(
136:         address _bridge,
137:         uint256 _mintingLimit,
138:         uint256 _burningLimit
139:     ) external onlyOwner {
140:         _changeMinterLimit(_bridge, _mintingLimit);
141:         _changeBurnerLimit(_bridge, _burningLimit);
142:         emit BridgeLimitsSet(_mintingLimit, _burningLimit, _bridge);
143:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L76-L87) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L135-L143)


```solidity

File: contracts/Delegation/OperatorDelegator.sol

101:     function activateRestaking() external nonReentrant onlyNativeEthRestakeAdmin {
102:         eigenPod.activateRestaking();
103:     }

106:     function setTokenStrategy(
107:         IERC20 _token,
108:         IStrategy _strategy
109:     ) external nonReentrant onlyOperatorDelegatorAdmin {
110:         if (address(_token) == address(0x0)) revert InvalidZeroInput();
111: 
112:         tokenStrategyMapping[_token] = _strategy;
113:         emit TokenStrategyUpdated(_token, _strategy);
114:     }

117:     function setDelegateAddress(
118:         address _delegateAddress,
119:         ISignatureUtils.SignatureWithExpiry memory approverSignatureAndExpiry,
120:         bytes32 approverSalt
121:     ) external nonReentrant onlyOperatorDelegatorAdmin {
122:         if (address(_delegateAddress) == address(0x0)) revert InvalidZeroInput();
123:         if (address(delegateAddress) != address(0x0)) revert DelegateAddressAlreadySet();
124: 
125:         delegateAddress = _delegateAddress;
126: 
127:         delegationManager.delegateTo(delegateAddress, approverSignatureAndExpiry, approverSalt);
128: 
129:         emit DelegationAddressUpdated(_delegateAddress);
130:     }

132:     function setBaseGasAmountSpent(
133:         uint256 _baseGasAmountSpent
134:     ) external nonReentrant onlyOperatorDelegatorAdmin {
135:         if (_baseGasAmountSpent == 0) revert InvalidZeroInput();
136:         emit BaseGasAmountSpentUpdated(baseGasAmountSpent, _baseGasAmountSpent);
137:         baseGasAmountSpent = _baseGasAmountSpent;
138:     }

143:     function deposit(
144:         IERC20 token,
145:         uint256 tokenAmount
146:     ) external nonReentrant onlyRestakeManager returns (uint256 shares) {
147:         if (address(tokenStrategyMapping[token]) == address(0x0) || tokenAmount == 0)
148:             revert InvalidZeroInput();
149: 
150:         // Move the tokens into this contract
151:         token.safeTransferFrom(msg.sender, address(this), tokenAmount);
152: 
153:         return _deposit(token, tokenAmount);
154:     }

193:     function queueWithdrawals(
194:         IERC20[] calldata tokens,
195:         uint256[] calldata tokenAmounts
196:     ) external nonReentrant onlyNativeEthRestakeAdmin returns (bytes32) {
197:         // record gas spent
198:         uint256 gasBefore = gasleft();
199:         if (tokens.length != tokenAmounts.length) revert MismatchedArrayLengths();
200:         IDelegationManager.QueuedWithdrawalParams[]
201:             memory queuedWithdrawalParams = new IDelegationManager.QueuedWithdrawalParams[](1);
202:         // set strategies legth for 0th index only
203:         queuedWithdrawalParams[0].strategies = new IStrategy[](tokens.length);
204:         queuedWithdrawalParams[0].shares = new uint256[](tokens.length);
205: 
206:         // Save the nonce before starting the withdrawal
207:         uint96 nonce = uint96(delegationManager.cumulativeWithdrawalsQueued(address(this)));
208: 
209:         for (uint256 i; i < tokens.length; ) {
210:             if (address(tokens[i]) == IS_NATIVE) {
211:                 // set beaconChainEthStrategy for ETH
212:                 queuedWithdrawalParams[0].strategies[i] = eigenPodManager.beaconChainETHStrategy();
213: 
214:                 // set shares for ETH
215:                 queuedWithdrawalParams[0].shares[i] = tokenAmounts[i];
216:             } else {
217:                 if (address(tokenStrategyMapping[tokens[i]]) == address(0))
218:                     revert InvalidZeroInput();
219: 
220:                 // set the strategy of the token
221:                 queuedWithdrawalParams[0].strategies[i] = tokenStrategyMapping[tokens[i]];
222: 
223:                 // set the equivalent shares for tokenAmount
224:                 queuedWithdrawalParams[0].shares[i] = tokenStrategyMapping[tokens[i]]
225:                     .underlyingToSharesView(tokenAmounts[i]);
226:             }
227: 
228:             // set withdrawer as this contract address
229:             queuedWithdrawalParams[0].withdrawer = address(this);
230: 
231:             // track shares of tokens withdraw for TVL
232:             queuedShares[address(tokens[i])] += queuedWithdrawalParams[0].shares[i];
233:             unchecked {
234:                 ++i;
235:             }
236:         }
237: 
238:         // queue withdrawal in EigenLayer
239:         bytes32 withdrawalRoot = delegationManager.queueWithdrawals(queuedWithdrawalParams)[0];
240:         // Emit the withdrawal started event
241:         emit WithdrawStarted(
242:             withdrawalRoot,
243:             address(this),
244:             delegateAddress,
245:             address(this),
246:             nonce,
247:             block.number,
248:             queuedWithdrawalParams[0].strategies,
249:             queuedWithdrawalParams[0].shares
250:         );
251: 
252:         // update the gas spent for RestakeAdmin
253:         _recordGas(gasBefore);
254: 
255:         return withdrawalRoot;
256:     }

265:     function completeQueuedWithdrawal(
266:         IDelegationManager.Withdrawal calldata withdrawal,
267:         IERC20[] calldata tokens,
268:         uint256 middlewareTimesIndex
269:     ) external nonReentrant onlyNativeEthRestakeAdmin {
270:         uint256 gasBefore = gasleft();
271:         if (tokens.length != withdrawal.strategies.length) revert MismatchedArrayLengths();
272: 
273:         // complete the queued withdrawal from EigenLayer with receiveAsToken set to true
274:         delegationManager.completeQueuedWithdrawal(withdrawal, tokens, middlewareTimesIndex, true);
275: 
276:         IWithdrawQueue withdrawQueue = restakeManager.depositQueue().withdrawQueue();
277:         for (uint256 i; i < tokens.length; ) {
278:             if (address(tokens[i]) == address(0)) revert InvalidZeroInput();
279: 
280:             // deduct queued shares for tracking TVL
281:             queuedShares[address(tokens[i])] -= withdrawal.shares[i];
282: 
283:             // check if token is not Native ETH
284:             if (address(tokens[i]) != IS_NATIVE) {
285:                 // Check the withdraw buffer and fill if below buffer target
286:                 uint256 bufferToFill = withdrawQueue.getBufferDeficit(address(tokens[i]));
287: 
288:                 // get balance of this contract
289:                 uint256 balanceOfToken = tokens[i].balanceOf(address(this));
290:                 if (bufferToFill > 0) {
291:                     bufferToFill = (balanceOfToken <= bufferToFill) ? balanceOfToken : bufferToFill;
292: 
293:                     // update amount to send to the operator Delegator
294:                     balanceOfToken -= bufferToFill;
295: 
296:                     // safe Approve for depositQueue
297:                     tokens[i].safeApprove(address(restakeManager.depositQueue()), bufferToFill);
298: 
299:                     // fill Withdraw Buffer via depositQueue
300:                     restakeManager.depositQueue().fillERC20withdrawBuffer(
301:                         address(tokens[i]),
302:                         bufferToFill
303:                     );
304:                 }
305: 
306:                 // Deposit remaining tokens back to eigenLayer
307:                 if (balanceOfToken > 0) {
308:                     _deposit(tokens[i], balanceOfToken);
309:                 }
310:             }
311:             unchecked {
312:                 ++i;
313:             }
314:         }
315: 
316:         // emits the Withdraw Completed event with withdrawalRoot
317:         emit WithdrawCompleted(
318:             delegationManager.calculateWithdrawalRoot(withdrawal),
319:             withdrawal.strategies,
320:             withdrawal.shares
321:         );
322:         // record current spent gas
323:         _recordGas(gasBefore);
324:     }

349:     function stakeEth(
350:         bytes calldata pubkey,
351:         bytes calldata signature,
352:         bytes32 depositDataRoot
353:     ) external payable onlyRestakeManager {
354:         // Call the stake function in the EigenPodManager
355:         eigenPodManager.stake{ value: msg.value }(pubkey, signature, depositDataRoot);
356: 
357:         // Increment the staked but not verified ETH
358:         stakedButNotVerifiedEth += msg.value;
359:     }

364:     function verifyWithdrawalCredentials(
365:         uint64 oracleTimestamp,
366:         BeaconChainProofs.StateRootProof calldata stateRootProof,
367:         uint40[] calldata validatorIndices,
368:         bytes[] calldata withdrawalCredentialProofs,
369:         bytes32[][] calldata validatorFields
370:     ) external onlyNativeEthRestakeAdmin {
371:         uint256 gasBefore = gasleft();
372:         eigenPod.verifyWithdrawalCredentials(
373:             oracleTimestamp,
374:             stateRootProof,
375:             validatorIndices,
376:             withdrawalCredentialProofs,
377:             validatorFields
378:         );
379: 
380:         // Decrement the staked but not verified ETH
381:         for (uint256 i = 0; i < validatorFields.length; ) {
382:             uint64 validatorCurrentBalanceGwei = BeaconChainProofs.getEffectiveBalanceGwei(
383:                 validatorFields[i]
384:             );
385:             stakedButNotVerifiedEth -= (validatorCurrentBalanceGwei * GWEI_TO_WEI);
386:             unchecked {
387:                 ++i;
388:             }
389:         }
390:         // update the gas spent for RestakeAdmin
391:         _recordGas(gasBefore);
392:     }

405:     function verifyAndProcessWithdrawals(
406:         uint64 oracleTimestamp,
407:         BeaconChainProofs.StateRootProof calldata stateRootProof,
408:         BeaconChainProofs.WithdrawalProof[] calldata withdrawalProofs,
409:         bytes[] calldata validatorFieldsProofs,
410:         bytes32[][] calldata validatorFields,
411:         bytes32[][] calldata withdrawalFields
412:     ) external onlyNativeEthRestakeAdmin {
413:         uint256 gasBefore = gasleft();
414:         eigenPod.verifyAndProcessWithdrawals(
415:             oracleTimestamp,
416:             stateRootProof,
417:             withdrawalProofs,
418:             validatorFieldsProofs,
419:             validatorFields,
420:             withdrawalFields
421:         );
422:         // update the gas spent for RestakeAdmin
423:         _recordGas(gasBefore);
424:     }

432:     function withdrawNonBeaconChainETHBalanceWei(
433:         address recipient,
434:         uint256 amountToWithdraw
435:     ) external onlyNativeEthRestakeAdmin {
436:         eigenPod.withdrawNonBeaconChainETHBalanceWei(recipient, amountToWithdraw);
437:     }

446:     function recoverTokens(
447:         IERC20[] memory tokenList,
448:         uint256[] memory amountsToWithdraw,
449:         address recipient
450:     ) external onlyNativeEthRestakeAdmin {
451:         eigenPod.recoverTokens(tokenList, amountsToWithdraw, recipient);
452:     }

459:     function startDelayedWithdrawUnstakedETH() external onlyNativeEthRestakeAdmin {
460:         // Call the start delayed withdraw function in the EigenPodManager
461:         // This will queue up a delayed withdrawal that will be sent back to this address after the timeout
462:         eigenPod.withdrawBeforeRestaking();
463:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L101-L103) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L106-L114), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L117-L130), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L132-L138), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L143-L154), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L193-L256), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L265-L324), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L349-L359), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L364-L392), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L405-L424), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L432-L437), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L446-L452), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L459-L463)


```solidity

File: contracts/Deposits/DepositQueue.sol

87:     function setWithdrawQueue(IWithdrawQueue _withdrawQueue) external onlyRestakeManagerAdmin {
88:         if (address(_withdrawQueue) == address(0)) revert InvalidZeroInput();
89:         emit WithdrawQueueUpdated(address(withdrawQueue), address(_withdrawQueue));
90:         withdrawQueue = _withdrawQueue;
91:     }

093:     function setFeeConfig(
094:         address _feeAddress,
095:         uint256 _feeBasisPoints
096:     ) external onlyRestakeManagerAdmin {
097:         // Verify address is set if basis points are non-zero
098:         if (_feeBasisPoints > 0) {
099:             if (_feeAddress == address(0x0)) revert InvalidZeroInput();
100:         }
101: 
102:         // Verify basis points are not over 100%
103:         if (_feeBasisPoints > 10000) revert OverMaxBasisPoints();
104: 
105:         feeAddress = _feeAddress;
106:         feeBasisPoints = _feeBasisPoints;
107: 
108:         emit FeeConfigUpdated(_feeAddress, _feeBasisPoints);
109:     }

112:     function setRestakeManager(IRestakeManager _restakeManager) external onlyRestakeManagerAdmin {
113:         if (address(_restakeManager) == address(0x0)) revert InvalidZeroInput();
114: 
115:         restakeManager = _restakeManager;
116: 
117:         emit RestakeManagerUpdated(_restakeManager);
118:     }

123:     function depositETHFromProtocol() external payable onlyRestakeManager {
124:         _checkAndFillETHWithdrawBuffer(msg.value);
125:         emit ETHDepositedFromProtocol(msg.value);
126:     }

134:     function fillERC20withdrawBuffer(
135:         address _asset,
136:         uint256 _amount
137:     ) external nonReentrant onlyRestakeManager {
138:         if (_amount == 0 || _asset == address(0)) revert InvalidZeroInput();
139:         // safeTransfer from restake manager to this address
140:         IERC20(_asset).safeTransferFrom(msg.sender, address(this), _amount);
141:         // approve the token amount for withdraw queue
142:         IERC20(_asset).safeApprove(address(withdrawQueue), _amount);
143:         // call the withdraw queue to fill up the buffer
144:         withdrawQueue.fillERC20WithdrawBuffer(_asset, _amount);
145:     }

187:     function stakeEthFromQueue(
188:         IOperatorDelegator operatorDelegator,
189:         bytes calldata pubkey,
190:         bytes calldata signature,
191:         bytes32 depositDataRoot
192:     ) external onlyNativeEthRestakeAdmin {
193:         uint256 gasBefore = gasleft();
194:         // Send the ETH and the params through to the restake manager
195:         restakeManager.stakeEthInOperatorDelegator{ value: 32 ether }(
196:             operatorDelegator,
197:             pubkey,
198:             signature,
199:             depositDataRoot
200:         );
201: 
202:         emit ETHStakedFromQueue(operatorDelegator, pubkey, 32 ether, address(this).balance);
203: 
204:         // Refund the gas to the Admin address if enough ETH available
205:         _refundGas(gasBefore);
206:     }

211:     function stakeEthFromQueueMulti(
212:         IOperatorDelegator[] calldata operatorDelegators,
213:         bytes[] calldata pubkeys,
214:         bytes[] calldata signatures,
215:         bytes32[] calldata depositDataRoots
216:     ) external onlyNativeEthRestakeAdmin nonReentrant {
217:         uint256 gasBefore = gasleft();
218:         // Verify all arrays are the same length
219:         if (
220:             operatorDelegators.length != pubkeys.length ||
221:             operatorDelegators.length != signatures.length ||
222:             operatorDelegators.length != depositDataRoots.length
223:         ) revert MismatchedArrayLengths();
224: 
225:         // Iterate through the arrays and stake each one
226:         uint256 arrayLength = operatorDelegators.length;
227:         for (uint256 i = 0; i < arrayLength; ) {
228:             // Send the ETH and the params through to the restake manager
229:             restakeManager.stakeEthInOperatorDelegator{ value: 32 ether }(
230:                 operatorDelegators[i],
231:                 pubkeys[i],
232:                 signatures[i],
233:                 depositDataRoots[i]
234:             );
235: 
236:             emit ETHStakedFromQueue(
237:                 operatorDelegators[i],
238:                 pubkeys[i],
239:                 32 ether,
240:                 address(this).balance
241:             );
242: 
243:             unchecked {
244:                 ++i;
245:             }
246:         }
247: 
248:         // Refund the gas to the Admin address if enough ETH available
249:         _refundGas(gasBefore);
250:     }

254:     function sweepERC20(IERC20 token) external onlyERC20RewardsAdmin {
255:         uint256 balance = IERC20(token).balanceOf(address(this));
256:         if (balance > 0) {
257:             uint256 feeAmount = 0;
258: 
259:             // Sweep fees if configured
260:             if (feeAddress != address(0x0) && feeBasisPoints > 0) {
261:                 feeAmount = (balance * feeBasisPoints) / 10000;
262:                 IERC20(token).safeTransfer(feeAddress, feeAmount);
263: 
264:                 emit ProtocolFeesPaid(token, feeAmount, feeAddress);
265:             }
266: 
267:             // Approve and deposit the rewards
268:             token.approve(address(restakeManager), balance - feeAmount);
269:             restakeManager.depositTokenRewardsFromProtocol(token, balance - feeAmount);
270: 
271:             // Add to the total earned
272:             totalEarned[address(token)] = totalEarned[address(token)] + balance - feeAmount;
273: 
274:             // Emit the rewards event
275:             emit RewardsDeposited(IERC20(address(token)), balance - feeAmount);
276:         }
277:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L87-L91) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L93-L109), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L112-L118), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L123-L126), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L134-L145), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L187-L206), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L211-L250), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L254-L277)


```solidity

File: contracts/Oracle/RenzoOracle.sol

54:     function setOracleAddress(
55:         IERC20 _token,
56:         AggregatorV3Interface _oracleAddress
57:     ) external nonReentrant onlyOracleAdmin {
58:         if (address(_token) == address(0x0)) revert InvalidZeroInput();
59: 
60:         // Verify that the pricing of the oracle is 18 decimals - pricing calculations will be off otherwise
61:         if (_oracleAddress.decimals() != 18)
62:             revert InvalidTokenDecimals(18, _oracleAddress.decimals());
63: 
64:         tokenOracleLookup[_token] = _oracleAddress;
65:         emit OracleAddressUpdated(_token, _oracleAddress);
66:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L54-L66) 


```solidity

File: contracts/RestakeManager.sol

121:     function setPaused(bool _paused) external onlyDepositWithdrawPauserAdmin {
122:         paused = _paused;
123:     }

131:     function addOperatorDelegator(
132:         IOperatorDelegator _newOperatorDelegator,
133:         uint256 _allocationBasisPoints
134:     ) external onlyRestakeManagerAdmin {
135:         // Ensure it is not already in the list
136:         uint256 odLength = operatorDelegators.length;
137:         for (uint256 i = 0; i < odLength; ) {
138:             if (address(operatorDelegators[i]) == address(_newOperatorDelegator))
139:                 revert AlreadyAdded();
140:             unchecked {
141:                 ++i;
142:             }
143:         }
144: 
145:         // Verify a valid allocation
146:         if (_allocationBasisPoints > (100 * BASIS_POINTS)) revert OverMaxBasisPoints();
147: 
148:         // Add it to the list
149:         operatorDelegators.push(_newOperatorDelegator);
150: 
151:         emit OperatorDelegatorAdded(_newOperatorDelegator);
152: 
153:         // Set the allocation
154:         operatorDelegatorAllocations[_newOperatorDelegator] = _allocationBasisPoints;
155: 
156:         emit OperatorDelegatorAllocationUpdated(_newOperatorDelegator, _allocationBasisPoints);
157:     }

160:     function removeOperatorDelegator(
161:         IOperatorDelegator _operatorDelegatorToRemove
162:     ) external onlyRestakeManagerAdmin {
163:         // Remove it from the list
164:         uint256 odLength = operatorDelegators.length;
165:         for (uint256 i = 0; i < odLength; ) {
166:             if (address(operatorDelegators[i]) == address(_operatorDelegatorToRemove)) {
167:                 // Clear the allocation
168:                 operatorDelegatorAllocations[_operatorDelegatorToRemove] = 0;
169:                 emit OperatorDelegatorAllocationUpdated(_operatorDelegatorToRemove, 0);
170: 
171:                 // Remove from list
172:                 operatorDelegators[i] = operatorDelegators[operatorDelegators.length - 1];
173:                 operatorDelegators.pop();
174:                 emit OperatorDelegatorRemoved(_operatorDelegatorToRemove);
175:                 return;
176:             }
177:             unchecked {
178:                 ++i;
179:             }
180:         }
181: 
182:         // If the item was not found, throw an error
183:         revert NotFound();
184:     }

187:     function setOperatorDelegatorAllocation(
188:         IOperatorDelegator _operatorDelegator,
189:         uint256 _allocationBasisPoints
190:     ) external onlyRestakeManagerAdmin {
191:         if (address(_operatorDelegator) == address(0x0)) revert InvalidZeroInput();
192:         if (_allocationBasisPoints > (100 * BASIS_POINTS)) revert OverMaxBasisPoints();
193: 
194:         // Ensure the OD is in the list to prevent mis-configuration
195:         bool foundOd = false;
196:         uint256 odLength = operatorDelegators.length;
197:         for (uint256 i = 0; i < odLength; ) {
198:             if (address(operatorDelegators[i]) == address(_operatorDelegator)) {
199:                 foundOd = true;
200:                 break;
201:             }
202:             unchecked {
203:                 ++i;
204:             }
205:         }
206:         if (!foundOd) revert NotFound();
207: 
208:         // Set the allocation
209:         operatorDelegatorAllocations[_operatorDelegator] = _allocationBasisPoints;
210: 
211:         emit OperatorDelegatorAllocationUpdated(_operatorDelegator, _allocationBasisPoints);
212:     }

215:     function setMaxDepositTVL(uint256 _maxDepositTVL) external onlyRestakeManagerAdmin {
216:         maxDepositTVL = _maxDepositTVL;
217:     }

220:     function addCollateralToken(IERC20 _newCollateralToken) external onlyRestakeManagerAdmin {
221:         // Ensure it is not already in the list
222:         uint256 tokenLength = collateralTokens.length;
223:         for (uint256 i = 0; i < tokenLength; ) {
224:             if (address(collateralTokens[i]) == address(_newCollateralToken)) revert AlreadyAdded();
225:             unchecked {
226:                 ++i;
227:             }
228:         }
229: 
230:         // Verify the token has 18 decimal precision - pricing calculations will be off otherwise
231:         if (IERC20Metadata(address(_newCollateralToken)).decimals() != 18)
232:             revert InvalidTokenDecimals(
233:                 18,
234:                 IERC20Metadata(address(_newCollateralToken)).decimals()
235:             );
236: 
237:         // Add it to the list
238:         collateralTokens.push(_newCollateralToken);
239: 
240:         emit CollateralTokenAdded(_newCollateralToken);
241:     }

244:     function removeCollateralToken(
245:         IERC20 _collateralTokenToRemove
246:     ) external onlyRestakeManagerAdmin {
247:         // Remove it from the list
248:         uint256 tokenLength = collateralTokens.length;
249:         for (uint256 i = 0; i < tokenLength; ) {
250:             if (address(collateralTokens[i]) == address(_collateralTokenToRemove)) {
251:                 collateralTokens[i] = collateralTokens[collateralTokens.length - 1];
252:                 collateralTokens.pop();
253:                 emit CollateralTokenRemoved(_collateralTokenToRemove);
254:                 return;
255:             }
256:             unchecked {
257:                 ++i;
258:             }
259:         }
260: 
261:         // If the item was not found, throw an error
262:         revert NotFound();
263:     }

620:     function stakeEthInOperatorDelegator(
621:         IOperatorDelegator operatorDelegator,
622:         bytes calldata pubkey,
623:         bytes calldata signature,
624:         bytes32 depositDataRoot
625:     ) external payable onlyDepositQueue {
626:         // Verify the OD is in the list
627:         bool found = false;
628:         uint256 odLength = operatorDelegators.length;
629:         for (uint256 i = 0; i < odLength; ) {
630:             if (operatorDelegators[i] == operatorDelegator) {
631:                 found = true;
632:                 break;
633:             }
634: 
635:             unchecked {
636:                 ++i;
637:             }
638:         }
639:         if (!found) revert NotFound();
640: 
641:         // Call the OD to stake the ETH
642:         operatorDelegator.stakeEth{ value: msg.value }(pubkey, signature, depositDataRoot);
643:     }

647:     function depositTokenRewardsFromProtocol(
648:         IERC20 _token,
649:         uint256 _amount
650:     ) external onlyDepositQueue {
651:         // Get the TVLs for each operator delegator and the total TVL
652:         (, uint256[] memory operatorDelegatorTVLs, uint256 totalTVL) = calculateTVLs();
653: 
654:         // Determine which operator delegator to use
655:         IOperatorDelegator operatorDelegator = chooseOperatorDelegatorForDeposit(
656:             operatorDelegatorTVLs,
657:             totalTVL
658:         );
659: 
660:         // Transfer the tokens to this address
661:         _token.safeTransferFrom(msg.sender, address(this), _amount);
662: 
663:         // Approve the tokens to the operator delegator
664:         _token.safeApprove(address(operatorDelegator), _amount);
665: 
666:         // Deposit the tokens into EigenLayer
667:         operatorDelegator.deposit(_token, _amount);
668:     }

709:     function setTokenTvlLimit(IERC20 _token, uint256 _limit) external onlyRestakeManagerAdmin {
710:         // Verify collateral token is in the list - call will revert if not found
711:         getCollateralTokenIndex(_token);
712: 
713:         // Set the limit
714:         collateralTokenTvlLimits[_token] = _limit;
715: 
716:         emit CollateralTokenTvlUpdated(_token, _limit);
717:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L121-L123) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L131-L157), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L160-L184), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L187-L212), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L215-L217), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L220-L241), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L244-L263), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L620-L643), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L647-L668), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L709-L717)


```solidity

File: contracts/Rewards/RewardHandler.sol

58:     function forwardRewards() external nonReentrant onlyNativeEthRestakeAdmin {
59:         _forwardETH();
60:     }

72:     function setRewardDestination(
73:         address _rewardDestination
74:     ) external nonReentrant onlyRestakeManagerAdmin {
75:         if (address(_rewardDestination) == address(0x0)) revert InvalidZeroInput();
76: 
77:         rewardDestination = _rewardDestination;
78: 
79:         emit RewardDestinationUpdated(_rewardDestination);
80:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L58-L60) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L72-L80)


```solidity

File: contracts/TimelockController.sol

234:     function schedule(
235:         address target,
236:         uint256 value,
237:         bytes calldata data,
238:         bytes32 predecessor,
239:         bytes32 salt,
240:         uint256 delay
241:     ) public virtual onlyRole(PROPOSER_ROLE) {
242:         bytes32 id = hashOperation(target, value, data, predecessor, salt);
243:         _schedule(id, delay);
244:         emit CallScheduled(id, 0, target, value, data, predecessor, delay);
245:         if (salt != bytes32(0)) {
246:             emit CallSalt(id, salt);
247:         }
248:     }

259:     function scheduleBatch(
260:         address[] calldata targets,
261:         uint256[] calldata values,
262:         bytes[] calldata payloads,
263:         bytes32 predecessor,
264:         bytes32 salt,
265:         uint256 delay
266:     ) public virtual onlyRole(PROPOSER_ROLE) {
267:         require(targets.length == values.length, "TimelockController: length mismatch");
268:         require(targets.length == payloads.length, "TimelockController: length mismatch");
269: 
270:         bytes32 id = hashOperationBatch(targets, values, payloads, predecessor, salt);
271:         _schedule(id, delay);
272:         for (uint256 i = 0; i < targets.length; ++i) {
273:             emit CallScheduled(id, i, targets[i], values[i], payloads[i], predecessor, delay);
274:         }
275:         if (salt != bytes32(0)) {
276:             emit CallSalt(id, salt);
277:         }
278:     }

296:     function cancel(bytes32 id) public virtual onlyRole(CANCELLER_ROLE) {
297:         require(isOperationPending(id), "TimelockController: operation cannot be cancelled");
298:         delete _timestamps[id];
299: 
300:         emit Cancelled(id);
301:     }

315:     function execute(
316:         address target,
317:         uint256 value,
318:         bytes calldata payload,
319:         bytes32 predecessor,
320:         bytes32 salt
321:     ) public payable virtual onlyRoleOrOpenRole(EXECUTOR_ROLE) {
322:         bytes32 id = hashOperation(target, value, payload, predecessor, salt);
323: 
324:         _beforeCall(id, predecessor);
325:         _execute(target, value, payload);
326:         emit CallExecuted(id, 0, target, value, payload);
327:         _afterCall(id);
328:     }

342:     function executeBatch(
343:         address[] calldata targets,
344:         uint256[] calldata values,
345:         bytes[] calldata payloads,
346:         bytes32 predecessor,
347:         bytes32 salt
348:     ) public payable virtual onlyRoleOrOpenRole(EXECUTOR_ROLE) {
349:         require(targets.length == values.length, "TimelockController: length mismatch");
350:         require(targets.length == payloads.length, "TimelockController: length mismatch");
351: 
352:         bytes32 id = hashOperationBatch(targets, values, payloads, predecessor, salt);
353: 
354:         _beforeCall(id, predecessor);
355:         for (uint256 i = 0; i < targets.length; ++i) {
356:             address target = targets[i];
357:             uint256 value = values[i];
358:             bytes calldata payload = payloads[i];
359:             _execute(target, value, payload);
360:             emit CallExecuted(id, i, target, value, payload);
361:         }
362:         _afterCall(id);
363:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L234-L248) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L259-L278), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L296-L301), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L315-L328), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L342-L363)


```solidity

File: contracts/Withdraw/WithdrawQueue.sol

106:     function updateWithdrawBufferTarget(
107:         TokenWithdrawBuffer[] calldata _newBufferTarget
108:     ) external onlyWithdrawQueueAdmin {
109:         if (_newBufferTarget.length == 0) revert InvalidZeroInput();
110:         for (uint256 i = 0; i < _newBufferTarget.length; ) {
111:             if (_newBufferTarget[i].asset == address(0) || _newBufferTarget[i].bufferAmount == 0)
112:                 revert InvalidZeroInput();
113:             emit WithdrawBufferTargetUpdated(
114:                 withdrawalBufferTarget[_newBufferTarget[i].asset],
115:                 _newBufferTarget[i].bufferAmount
116:             );
117:             withdrawalBufferTarget[_newBufferTarget[i].asset] = _newBufferTarget[i].bufferAmount;
118:             unchecked {
119:                 ++i;
120:             }
121:         }
122:     }

129:     function updateCoolDownPeriod(uint256 _newCoolDownPeriod) external onlyWithdrawQueueAdmin {
130:         if (_newCoolDownPeriod == 0) revert InvalidZeroInput();
131:         emit CoolDownPeriodUpdated(coolDownPeriod, _newCoolDownPeriod);
132:         coolDownPeriod = _newCoolDownPeriod;
133:     }

139:     function pause() external onlyWithdrawQueueAdmin {
140:         _pause();
141:     }

147:     function unpause() external onlyWithdrawQueueAdmin {
148:         _unpause();
149:     }

182:     function fillEthWithdrawBuffer() external payable nonReentrant onlyDepositQueue {
183:         emit EthBufferFilled(msg.value);
184:     }

192:     function fillERC20WithdrawBuffer(
193:         address _asset,
194:         uint256 _amount
195:     ) external nonReentrant onlyDepositQueue {
196:         if (_asset == address(0) || _amount == 0) revert InvalidZeroInput();
197:         IERC20(_asset).safeTransferFrom(msg.sender, address(this), _amount);
198:         emit ERC20BufferFilled(_asset, _amount);
199:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L106-L122) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L129-L133), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L139-L141), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L147-L149), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L182-L184), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L192-L199)


```solidity

File: contracts/token/EzEthToken.sol

41:     function mint(address to, uint256 amount) external onlyMinterBurner {
42:         _mint(to, amount);
43:     }

46:     function burn(address from, uint256 amount) external onlyMinterBurner {
47:         _burn(from, amount);
48:     }

51:     function setPaused(bool _paused) external onlyTokenAdmin {
52:         paused = _paused;
53:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L41-L43) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L46-L48), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L51-L53)


</details>


### [L&#x2011;12] Consider using OpenZeppelin’s SafeCast library to prevent unexpected overflows when casting from various type int/uint values 



*There are 4 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Bridge/L2/Oracle/RenzoOracleL2.sol

//@audit `price` is getting converted from `int256` to `uint256`
54:         uint256 _scaledPrice = (uint256(price)) * 10 ** (18 - oracle.decimals());


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L54-L54) 


```solidity

File: contracts/Delegation/OperatorDelegator.sol

//@audit `podOwnerShares` is getting converted from `int256` to `uint256`
344:                 : queuedShares[IS_NATIVE] + stakedButNotVerifiedEth + uint256(podOwnerShares);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L344-L344) 


```solidity

File: contracts/Oracle/RenzoOracle.sol

//@audit `price` is getting converted from `int256` to `uint256`
80:         return (uint256(price) * _balance) / SCALE_FACTOR;

//@audit `price` is getting converted from `int256` to `uint256`
97:         return (_value * SCALE_FACTOR) / uint256(price);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L80-L80) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L97-L97)


</details>


### [L&#x2011;13] Setters should have initial value check 
Setters should have initial value check to prevent assigning wrong value to the variable. Assginment of wrong value can lead to unexpected behavior of the contract.


*There are 7 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Bridge/L2/xRenzoDeposit.sol

466:     function setAllowedBridgeSweeper(address _sweeper, bool _allowed) external onlyOwner {

501:     function setOraclePriceFeed(IRenzoOracleL2 _oracle) external onlyOwner {

511:     function setReceiverPriceFeed(address _receiver) external onlyOwner {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L466-L466) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L501-L501), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L511-L511)


```solidity

File: contracts/RestakeManager.sol

121:     function setPaused(bool _paused) external onlyDepositWithdrawPauserAdmin {

215:     function setMaxDepositTVL(uint256 _maxDepositTVL) external onlyRestakeManagerAdmin {

709:     function setTokenTvlLimit(IERC20 _token, uint256 _limit) external onlyRestakeManagerAdmin {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L121-L121) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L215-L215), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L709-L709)


```solidity

File: contracts/token/EzEthToken.sol

51:     function setPaused(bool _paused) external onlyTokenAdmin {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L51-L51) 


</details>


### [L&#x2011;14] Solidity version 0.8.20 may not work on other chains due to `PUSH0` 
The compiler for Solidity 0.8.20 switches the default target EVM version to [Shanghai](https://blog.soliditylang.org/2023/05/10/solidity-0.8.20-release-announcement/#important-note), which includes the new `PUSH0` op code. This op code may not yet be implemented on all L2s, so deployment on these chains will fail. To work around this issue, use an earlier [EVM](https://docs.soliditylang.org/en/v0.8.20/using-the-compiler.html?ref=zaryabs.com#setting-the-evm-version-to-target) [version](https://book.getfoundry.sh/reference/config/solidity-compiler#evm_version)


*There are 1 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/token/EzEthTokenStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthTokenStorage.sol#L2-L2) 


</details>


### [L&#x2011;15] Unsafe downcast 
When a type is downcast to a smaller type, the higher order bits are truncated, effectively applying a modulo to the original value. Without any other checks, this wrapping will lead to unexpected behavior and bugs


*There are 1 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Delegation/OperatorDelegator.sol

//@audit converting from `uint256` to `uint96`
207:         uint96 nonce = uint96(delegationManager.cumulativeWithdrawalsQueued(address(this)));


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L207-L207) 


</details>


### [L&#x2011;16] Unsafe ERC20 operation `approve()` 
Approve call do not handle non-standard erc20 behavior.
- Some token contracts do not return any value.
- Some token contracts revert the transaction when the allowance is not zero.
Use `safeApprove` instead of `approve`


*There are 1 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Deposits/DepositQueue.sol

268:             token.approve(address(restakeManager), balance - feeAmount);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L268-L268) 


</details>


### [L&#x2011;17] Unspecific compiler version pragma 



*There are 5 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Bridge/xERC20/contracts/XERC20.sol

2: pragma solidity >=0.8.4 <0.9.0;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L2-L2) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Factory.sol

2: pragma solidity >=0.8.4 <0.9.0;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L2-L2) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol

2: pragma solidity >=0.8.4 <0.9.0;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L2-L2) 


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol

2: pragma solidity >=0.8.4 <0.9.0;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L2-L2) 


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol

2: pragma solidity >=0.8.4 <0.9.0;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L2-L2) 


</details>


### [L&#x2011;18] Unused/empty `receive()`/`fallback()` function 
If the intention is for the Ether to be used, the function should call another function or emit an event, otherwise it should revert.


*There are 3 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Bridge/L1/xRenzoBridge.sol

313:     receive() external payable {}
314: }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L313-L314) 


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

542:     receive() external payable {}
543: }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L542-L543) 


```solidity

File: contracts/TimelockController.sol

137:     receive() external payable {}
138: 


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L137-L138) 


</details>


### [L&#x2011;19] Upgradeable contract uses non-upgradeable version of the OpenZeppelin libraries/contracts 
OpenZeppelin has an [Upgradeable](https://github.com/OpenZeppelin/openzeppelin-contracts-upgradeable/tree/master/contracts/utils) variants of each of its libraries and contracts, and upgradeable contracts should use those variants.


*There are 10 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol

5: import { IERC20 } from "@openzeppelin/contracts/token/ERC20/ERC20.sol";

6: import { SafeERC20 } from "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";

7: import { SafeCast } from "@openzeppelin/contracts/utils/math/SafeCast.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L5-L5) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L6-L6), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L7-L7)


```solidity

File: contracts/Delegation/OperatorDelegator.sol

4: import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L4-L4) 


```solidity

File: contracts/Deposits/DepositQueue.sol

5: import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L5-L5) 


```solidity

File: contracts/RestakeManager.sol

4: import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";

9: import "@openzeppelin/contracts/token/ERC20/IERC20.sol";

10: import "@openzeppelin/contracts/token/ERC20/extensions/IERC20Metadata.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L4-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L9-L9), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L10-L10)


```solidity

File: contracts/Withdraw/WithdrawQueue.sol

6: import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";

9: import "@openzeppelin/contracts/token/ERC20/IERC20.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L6-L6) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L9-L9)


</details>


### [L&#x2011;20] Upgradeable contract is missing a `__gap[50]` storage variable to allow for new storage variables in later versions 
See [this](https://docs.openzeppelin.com/contracts/4.x/upgradeable#storage_gaps) link for a description of this storage variable. While some contracts may not currently be sub-classed, adding the variable now protects against forgetting to add it in the future.


*There are 13 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Bridge/L1/xRenzoBridge.sol

16: contract xRenzoBridge is


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L16-L16) 


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2.sol

11: contract RenzoOracleL2 is Initializable, OwnableUpgradeable, RenzoOracleL2StorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L11-L11) 


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

27: contract xRenzoDeposit is


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L27-L27) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20.sol

16: contract XERC20 is


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L16-L16) 


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol

11: contract OptimismMintableXERC20 is ERC165Upgradeable, XERC20, IOptimismMintableERC20 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L11-L11) 


```solidity

File: contracts/Delegation/OperatorDelegator.sol

17: contract OperatorDelegator is


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L17-L17) 


```solidity

File: contracts/Deposits/DepositQueue.sol

10: contract DepositQueue is Initializable, ReentrancyGuardUpgradeable, DepositQueueStorageV2 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L10-L10) 


```solidity

File: contracts/Oracle/RenzoOracle.sol

13: contract RenzoOracle is


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L13-L13) 


```solidity

File: contracts/Permissions/RoleManager.sol

14: contract RoleManager is IRoleManager, AccessControlUpgradeable, RoleManagerStorageV3 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L14-L14) 


```solidity

File: contracts/RestakeManager.sol

26: contract RestakeManager is Initializable, ReentrancyGuardUpgradeable, RestakeManagerStorageV2 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L26-L26) 


```solidity

File: contracts/Rewards/RewardHandler.sol

16: contract RewardHandler is Initializable, ReentrancyGuardUpgradeable, RewardHandlerStorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L16-L16) 


```solidity

File: contracts/Withdraw/WithdrawQueue.sol

11: contract WithdrawQueue is


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L11-L11) 


```solidity

File: contracts/token/EzEthToken.sol

13: contract EzEthToken is Initializable, ERC20Upgradeable, IEzEthToken, EzEthTokenStorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L13-L13) 


</details>


### [L&#x2011;21] `safeApprove()` is deprecated 
[Deprecated](https://github.com/OpenZeppelin/openzeppelin-contracts/blob/bfff03c0d2a59bcd8e2ead1da9aed9edf0080d05/contracts/token/ERC20/utils/SafeERC20.sol#L38-L45) in favor of `safeIncreaseAllowance()` and `safeDecreaseAllowance()`. If only setting the initial allowance to the value that means infinite, `safeIncreaseAllowance()` can be used instead. The function may currently work, but if a bug is found in this version of OpenZeppelin, and the version that you're forced to upgrade to no longer has this function, you'll encounter unnecessary delays in porting and testing replacement contracts.


*There are 11 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol

84:         SafeERC20.safeApprove(IERC20(_erc20), lockbox, _amount);

86:         SafeERC20.safeApprove(IERC20(xerc20), blastStandardBridge, _amount);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L84-L84) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L86-L86)


```solidity

File: contracts/Bridge/L1/xRenzoBridge.sol

181:         ezETH.safeApprove(address(xezETHLockbox), ezETHAmount);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L181-L181) 


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

369:         depositToken.safeApprove(address(connext), _amountIn);

429:         collateralToken.safeApprove(address(connext), balance);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L369-L369) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L429-L429)


```solidity

File: contracts/Delegation/OperatorDelegator.sol

164:         _token.safeApprove(address(strategyManager), _tokenAmount);

297:                     tokens[i].safeApprove(address(restakeManager.depositQueue()), bufferToFill);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L164-L164) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L297-L297)


```solidity

File: contracts/Deposits/DepositQueue.sol

142:         IERC20(_asset).safeApprove(address(withdrawQueue), _amount);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L142-L142) 


```solidity

File: contracts/RestakeManager.sol

552:             _collateralToken.safeApprove(address(depositQueue), bufferToFill);

559:         _collateralToken.safeApprove(address(operatorDelegator), _amount);

664:         _token.safeApprove(address(operatorDelegator), _amount);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L552-L552) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L559-L559), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L664-L664)


</details>


### [L&#x2011;22] Consider using descriptive `constant`s when passing zero as a function argument 
Passing zero as a function argument can sometimes result in a security issue (e.g. passing zero as the slippage parameter). Consider using a `constant` variable with a descriptive name, so it's clear that the argument is intentionally being used, and for the right reasons.


*There are 5 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Bridge/xERC20/contracts/XERC20Factory.sol

//@audit parameter number 3 starting from left
163:         _xerc20 = CREATE3.deploy(_salt, _bytecode, 0);

//@audit parameter number 3 starting from left
206:         _lockbox = payable(CREATE3.deploy(_salt, _bytecode, 0));


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L163-L163) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L206-L206)


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol

//@audit parameter number 3 starting from left
105:         _xerc20 = CREATE3.deploy(_salt, _bytecode, 0);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L105-L105) 


```solidity

File: contracts/RestakeManager.sol

//@audit parameter number 3 starting from left
474:         deposit(_collateralToken, _amount, 0);

//@audit parameter number 1 starting from left
583:         depositETH(0);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L474-L474) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L583-L583)


</details>


### [L&#x2011;23] Check of division by zero 



*There are 3 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Bridge/L2/xRenzoDeposit.sol

253:         uint256 xezETHAmount = (1e18 * amountOut) / _lastPrice;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L253-L253) 


```solidity

File: contracts/Oracle/RenzoOracle.sol

158:         uint256 redeemAmount = (_currentValueInProtocol * _ezETHBeingBurned) / _existingEzETHSupply;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L158-L158) 


```solidity

File: contracts/RateProvider/BalancerRateProvider.sol

40:         return (10 ** 18 * totalTVL) / totalSupply;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProvider.sol#L40-L40) 


</details>


### [L&#x2011;24] Privileged functions can create points of failure 
Ensure such accounts are protected and consider implementing multi sig to prevent a single point of failure 


*There are 68 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Bridge/L1/xRenzoBridge.sol

210:     function sendPrice(
211:         CCIPDestinationParam[] calldata _destinationParam,
212:         ConnextDestinationParam[] calldata _connextDestinationParam
213:     ) external payable onlyPriceFeedSender nonReentrant {

294:     function recoverNative(uint256 _amount, address _to) external onlyBridgeAdmin {

305:     function recoverERC20(address _token, uint256 _amount, address _to) external onlyBridgeAdmin {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L210-L213) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L294-L294), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L305-L305)


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2.sol

36:     function setOracleAddress(AggregatorV3Interface _oracleAddress) external onlyOwner {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L36-L36) 


```solidity

File: contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol

96:     function updateXRenzoBridgeL1(address _newXRenzoBridgeL1) external onlyOwner {

107:     function updateCCIPEthChainSelector(uint64 _newChainSelector) external onlyOwner {

117:     function unPause() external onlyOwner {

125:     function pause() external onlyOwner {

134:     function setRenzoDeposit(address _newXRenzoDeposit) external onlyOwner {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L96-L96) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L107-L107), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L117-L117), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L125-L125), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L134-L134)


```solidity

File: contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol

92:     function updateXRenzoBridgeL1(address _newXRenzoBridgeL1) external onlyOwner {

103:     function updateCCIPEthChainSelector(uint32 _newChainDomain) external onlyOwner {

113:     function unPause() external onlyOwner {

121:     function pause() external onlyOwner {

130:     function setRenzoDeposit(address _newXRenzoDeposit) external onlyOwner {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L92-L92) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L103-L103), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L113-L113), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L121-L121), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L130-L130)


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

320:     function updatePriceByOwner(uint256 price) external onlyOwner {

466:     function setAllowedBridgeSweeper(address _sweeper, bool _allowed) external onlyOwner {

478:     function recoverNative(uint256 _amount, address _to) external onlyOwner {

489:     function recoverERC20(address _token, uint256 _amount, address _to) external onlyOwner {

501:     function setOraclePriceFeed(IRenzoOracleL2 _oracle) external onlyOwner {

511:     function setReceiverPriceFeed(address _receiver) external onlyOwner {

521:     function updateBridgeFeeShare(uint256 _newShare) external onlyOwner {

532:     function updateSweepBatchSize(uint256 _newBatchSize) external onlyOwner {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L320-L320) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L466-L466), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L478-L478), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L489-L489), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L501-L501), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L511-L511), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L521-L521), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L532-L532)


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20.sol

135:     function setLimits(
136:         address _bridge,
137:         uint256 _mintingLimit,
138:         uint256 _burningLimit
139:     ) external onlyOwner {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L135-L139) 


```solidity

File: contracts/Delegation/OperatorDelegator.sol

106:     function setTokenStrategy(
107:         IERC20 _token,
108:         IStrategy _strategy
109:     ) external nonReentrant onlyOperatorDelegatorAdmin {

117:     function setDelegateAddress(
118:         address _delegateAddress,
119:         ISignatureUtils.SignatureWithExpiry memory approverSignatureAndExpiry,
120:         bytes32 approverSalt
121:     ) external nonReentrant onlyOperatorDelegatorAdmin {

132:     function setBaseGasAmountSpent(
133:         uint256 _baseGasAmountSpent
134:     ) external nonReentrant onlyOperatorDelegatorAdmin {

193:     function queueWithdrawals(
194:         IERC20[] calldata tokens,
195:         uint256[] calldata tokenAmounts
196:     ) external nonReentrant onlyNativeEthRestakeAdmin returns (bytes32) {

265:     function completeQueuedWithdrawal(
266:         IDelegationManager.Withdrawal calldata withdrawal,
267:         IERC20[] calldata tokens,
268:         uint256 middlewareTimesIndex
269:     ) external nonReentrant onlyNativeEthRestakeAdmin {

364:     function verifyWithdrawalCredentials(
365:         uint64 oracleTimestamp,
366:         BeaconChainProofs.StateRootProof calldata stateRootProof,
367:         uint40[] calldata validatorIndices,
368:         bytes[] calldata withdrawalCredentialProofs,
369:         bytes32[][] calldata validatorFields
370:     ) external onlyNativeEthRestakeAdmin {

405:     function verifyAndProcessWithdrawals(
406:         uint64 oracleTimestamp,
407:         BeaconChainProofs.StateRootProof calldata stateRootProof,
408:         BeaconChainProofs.WithdrawalProof[] calldata withdrawalProofs,
409:         bytes[] calldata validatorFieldsProofs,
410:         bytes32[][] calldata validatorFields,
411:         bytes32[][] calldata withdrawalFields
412:     ) external onlyNativeEthRestakeAdmin {

432:     function withdrawNonBeaconChainETHBalanceWei(
433:         address recipient,
434:         uint256 amountToWithdraw
435:     ) external onlyNativeEthRestakeAdmin {

446:     function recoverTokens(
447:         IERC20[] memory tokenList,
448:         uint256[] memory amountsToWithdraw,
449:         address recipient
450:     ) external onlyNativeEthRestakeAdmin {

459:     function startDelayedWithdrawUnstakedETH() external onlyNativeEthRestakeAdmin {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L106-L109) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L117-L121), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L132-L134), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L193-L196), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L265-L269), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L364-L370), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L405-L412), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L432-L435), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L446-L450), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L459-L459)


```solidity

File: contracts/Deposits/DepositQueue.sol

87:     function setWithdrawQueue(IWithdrawQueue _withdrawQueue) external onlyRestakeManagerAdmin {

93:     function setFeeConfig(
94:         address _feeAddress,
95:         uint256 _feeBasisPoints
96:     ) external onlyRestakeManagerAdmin {

112:     function setRestakeManager(IRestakeManager _restakeManager) external onlyRestakeManagerAdmin {

123:     function depositETHFromProtocol() external payable onlyRestakeManager {

134:     function fillERC20withdrawBuffer(
135:         address _asset,
136:         uint256 _amount
137:     ) external nonReentrant onlyRestakeManager {

187:     function stakeEthFromQueue(
188:         IOperatorDelegator operatorDelegator,
189:         bytes calldata pubkey,
190:         bytes calldata signature,
191:         bytes32 depositDataRoot
192:     ) external onlyNativeEthRestakeAdmin {

211:     function stakeEthFromQueueMulti(
212:         IOperatorDelegator[] calldata operatorDelegators,
213:         bytes[] calldata pubkeys,
214:         bytes[] calldata signatures,
215:         bytes32[] calldata depositDataRoots
216:     ) external onlyNativeEthRestakeAdmin nonReentrant {

254:     function sweepERC20(IERC20 token) external onlyERC20RewardsAdmin {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L87-L87) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L93-L96), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L112-L112), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L123-L123), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L134-L137), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L187-L192), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L211-L216), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L254-L254)


```solidity

File: contracts/Oracle/RenzoOracle.sol

54:     function setOracleAddress(
55:         IERC20 _token,
56:         AggregatorV3Interface _oracleAddress
57:     ) external nonReentrant onlyOracleAdmin {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L54-L57) 


```solidity

File: contracts/RestakeManager.sol

121:     function setPaused(bool _paused) external onlyDepositWithdrawPauserAdmin {

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

215:     function setMaxDepositTVL(uint256 _maxDepositTVL) external onlyRestakeManagerAdmin {

220:     function addCollateralToken(IERC20 _newCollateralToken) external onlyRestakeManagerAdmin {

244:     function removeCollateralToken(
245:         IERC20 _collateralTokenToRemove
246:     ) external onlyRestakeManagerAdmin {

620:     function stakeEthInOperatorDelegator(
621:         IOperatorDelegator operatorDelegator,
622:         bytes calldata pubkey,
623:         bytes calldata signature,
624:         bytes32 depositDataRoot
625:     ) external payable onlyDepositQueue {

647:     function depositTokenRewardsFromProtocol(
648:         IERC20 _token,
649:         uint256 _amount
650:     ) external onlyDepositQueue {

709:     function setTokenTvlLimit(IERC20 _token, uint256 _limit) external onlyRestakeManagerAdmin {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L121-L121) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L131-L134), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L160-L162), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L187-L190), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L215-L215), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L220-L220), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L244-L246), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L620-L625), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L647-L650), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L709-L709)


```solidity

File: contracts/Rewards/RewardHandler.sol

58:     function forwardRewards() external nonReentrant onlyNativeEthRestakeAdmin {

72:     function setRewardDestination(
73:         address _rewardDestination
74:     ) external nonReentrant onlyRestakeManagerAdmin {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L58-L58) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L72-L74)


```solidity

File: contracts/TimelockController.sol

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

296:     function cancel(bytes32 id) public virtual onlyRole(CANCELLER_ROLE) {

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


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L234-L241) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L259-L266), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L296-L296), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L315-L321), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L342-L348)


```solidity

File: contracts/Withdraw/WithdrawQueue.sol

106:     function updateWithdrawBufferTarget(
107:         TokenWithdrawBuffer[] calldata _newBufferTarget
108:     ) external onlyWithdrawQueueAdmin {

129:     function updateCoolDownPeriod(uint256 _newCoolDownPeriod) external onlyWithdrawQueueAdmin {

139:     function pause() external onlyWithdrawQueueAdmin {

147:     function unpause() external onlyWithdrawQueueAdmin {

182:     function fillEthWithdrawBuffer() external payable nonReentrant onlyDepositQueue {

192:     function fillERC20WithdrawBuffer(
193:         address _asset,
194:         uint256 _amount
195:     ) external nonReentrant onlyDepositQueue {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L106-L108) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L129-L129), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L139-L139), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L147-L147), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L182-L182), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L192-L195)


```solidity

File: contracts/token/EzEthToken.sol

41:     function mint(address to, uint256 amount) external onlyMinterBurner {

46:     function burn(address from, uint256 amount) external onlyMinterBurner {

51:     function setPaused(bool _paused) external onlyTokenAdmin {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L41-L41) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L46-L46), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L51-L51)


</details>


### [L&#x2011;25] Functions calling contracts/addresses with transfer hooks are missing reentrancy guards 
Even if the function follows the best practice of check-effects-interaction, not using a reentrancy guard when there may be transfer hooks will open the users of this protocol up to [read-only reentrancies](https://chainsecurity.com/curve-lp-oracle-manipulation-post-mortem/) with no way to protect against it, except by block-listing the whole protocol.


*There are 2 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol

//@audit function `_withdraw()` is not protected against reentrancy
134:             ERC20.safeTransfer(_to, _amount);

//@audit function `_deposit()` is not protected against reentrancy
147:             ERC20.safeTransferFrom(msg.sender, address(this), _amount);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L134-L134) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L147-L147)


</details>


### [L&#x2011;26] Some function should not be marked as payable 
Some function should not be marked as payable, otherwise the ETH that mistakenly sent along with the function call is locked in the contract


*There are 1 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/TimelockController.sol

342:     function executeBatch(
343:         address[] calldata targets,
344:         uint256[] calldata values,
345:         bytes[] calldata payloads,
346:         bytes32 predecessor,
347:         bytes32 salt
348:     ) public payable virtual onlyRoleOrOpenRole(EXECUTOR_ROLE) {
349:         require(targets.length == values.length, "TimelockController: length mismatch");
350:         require(targets.length == payloads.length, "TimelockController: length mismatch");
351: 
352:         bytes32 id = hashOperationBatch(targets, values, payloads, predecessor, salt);
353: 
354:         _beforeCall(id, predecessor);
355:         for (uint256 i = 0; i < targets.length; ++i) {
356:             address target = targets[i];
357:             uint256 value = values[i];
358:             bytes calldata payload = payloads[i];
359:             _execute(target, value, payload);
360:             emit CallExecuted(id, i, target, value, payload);
361:         }
362:         _afterCall(id);
363:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L342-L363) 


</details>


### [L&#x2011;27] Code does not follow the best practice of check-effects-interaction 
Code should follow the best-practice of [check-effects-interaction](https://blockchain-academy.hs-mittweida.de/courses/solidity-coding-beginners-to-intermediate/lessons/solidity-11-coding-patterns/topic/checks-effects-interactions/), where state variables are updated before any external calls are made. Doing so prevents a large class of reentrancy bugs.


*There are 1 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Bridge/xERC20/contracts/XERC20Factory.sol

//@audit the function `add()` is called before the following assignment
210:         _lockboxRegistry[_xerc20] = _lockbox;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L210-L210) 


</details>


### [L&#x2011;28] prevent re-setting a state variable with the same value 
Not only is wasteful in terms of gas, but this is especially problematic when an event is emitted and the old and new values set are the same, as listeners might not expect this kind of scenario.


*There are 13 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Bridge/L2/xRenzoDeposit.sol

310:     function updatePrice(uint256 _price, uint256 _timestamp) external override {

320:     function updatePriceByOwner(uint256 price) external onlyOwner {

466:     function setAllowedBridgeSweeper(address _sweeper, bool _allowed) external onlyOwner {

501:     function setOraclePriceFeed(IRenzoOracleL2 _oracle) external onlyOwner {

511:     function setReceiverPriceFeed(address _receiver) external onlyOwner {

521:     function updateBridgeFeeShare(uint256 _newShare) external onlyOwner {

532:     function updateSweepBatchSize(uint256 _newBatchSize) external onlyOwner {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L310-L310) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L320-L320), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L466-L466), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L501-L501), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L511-L511), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L521-L521), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L532-L532)


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20.sol

121:     function setLockbox(address _lockbox) public {

135:     function setLimits(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L121-L121) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L135-L135)


```solidity

File: contracts/RestakeManager.sol

121:     function setPaused(bool _paused) external onlyDepositWithdrawPauserAdmin {

215:     function setMaxDepositTVL(uint256 _maxDepositTVL) external onlyRestakeManagerAdmin {

709:     function setTokenTvlLimit(IERC20 _token, uint256 _limit) external onlyRestakeManagerAdmin {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L121-L121) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L215-L215), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L709-L709)


```solidity

File: contracts/token/EzEthToken.sol

51:     function setPaused(bool _paused) external onlyTokenAdmin {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L51-L51) 


</details>


### [L&#x2011;29] Use of `tx.origin` is unsafe in almost every context 
According to [Vitalik Buterin](https://ethereum.stackexchange.com/questions/196/how-do-i-make-my-dapp-serenity-proof), contracts should _not_ `assume that tx.origin will continue to be usable or meaningful`. An example of this is [EIP-3074](https://eips.ethereum.org/EIPS/eip-3074#allowing-txorigin-as-signer-1) which explicitly mentions the intention to change its semantics when it's used with new op codes.There have also been calls to [remove](https://github.com/ethereum/solidity/issues/683) `tx.origin`, and there are [security issues](solidity.readthedocs.io/en/v0.4.24/security-considerations.html#tx-origin) associated with using it for authorization. For these reasons, it's best to completely avoid the feature.Using the variable could make a contract vulnerable if an authorized account calls a malicious contract.You can impersonate a user using a third party contract.


*There are 6 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Delegation/OperatorDelegator.sol

482:         uint256 gasRefund = address(this).balance >= adminGasSpentInWei[tx.origin]

483:             ? adminGasSpentInWei[tx.origin]

485:         bool success = payable(tx.origin).send(gasRefund);

489:         adminGasSpentInWei[tx.origin] -= gasRefund;

491:         emit GasRefunded(tx.origin, gasRefund);

509:             if (adminGasSpentInWei[tx.origin] > 0) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L482-L482) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L483-L483), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L485-L485), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L489-L489), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L491-L491), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L509-L509)


</details>


### [L&#x2011;30] Missing checks in initializer function 
There are some missing checks in these functions, and this could lead to unexpected scenarios. Consider always adding a sanity check for state variables.


*There are 1 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol

//@audit _isNative,  are not checked
44:     function initialize(address _xerc20, address _erc20, bool _isNative) public initializer {
45:         XERC20 = IXERC20(_xerc20);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L44-L45) 


</details>


### [L&#x2011;31] Variables shadowing other definitions 
A variable declaration shadowing any other existing definition is error-prone. It can cause confusion for developers, potentially introduce bugs, and reduce the readability and maintainability.


*There are 11 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Bridge/xERC20/contracts/XERC20.sol

//@audit this variable is shadowing the `ERC20Upgradeable`'s stat variable `_name`
62:         string memory _name,

//@audit this variable is shadowing the `ERC20Upgradeable`'s stat variable `_symbol`
63:         string memory _symbol,

//@audit this variable is shadowing the `ERC20Upgradeable`'s stat variable `_name`
77:         string memory _name,

//@audit this variable is shadowing the `ERC20Upgradeable`'s stat variable `_symbol`
78:         string memory _symbol,


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L62-L62) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L63-L63), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L77-L77), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L78-L78)


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol

//@audit this variable is shadowing the `ERC20Upgradeable`'s stat variable `_name`
36:         string memory _name,

//@audit this variable is shadowing the `ERC20Upgradeable`'s stat variable `_symbol`
37:         string memory _symbol,


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L36-L36) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L37-L37)


```solidity

File: contracts/Delegation/OperatorDelegator.sol

//@audit this variable is shadowing the `OperatorDelegatorStorageV1`'s stat variable `delegateAddress`
29:     event DelegationAddressUpdated(address delegateAddress);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L29-L29) 


```solidity

File: contracts/Deposits/DepositQueue.sol

//@audit this variable is shadowing the `DepositQueueStorageV1`'s stat variable `feeAddress`
17:     event FeeConfigUpdated(address feeAddress, uint256 feeBasisPoints);

//@audit this variable is shadowing the `DepositQueueStorageV1`'s stat variable `feeBasisPoints`
17:     event FeeConfigUpdated(address feeAddress, uint256 feeBasisPoints);

//@audit this variable is shadowing the `DepositQueueStorageV1`'s stat variable `restakeManager`
19:     event RestakeManagerUpdated(IRestakeManager restakeManager);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L17-L17) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L17-L17), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L19-L19)


```solidity

File: contracts/Rewards/RewardHandler.sol

//@audit this variable is shadowing the `RewardHandlerStorageV1`'s stat variable `rewardDestination`
29:     event RewardDestinationUpdated(address rewardDestination);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L29-L29) 


</details>


### [L&#x2011;32] [Solidity]: Bug in Legacy Code Generation When Accessing the .selector Member on Expressions with Side Effects 
This version of solidity is vulnerable to a bug in the legacy code generation pipeline of the Solidity compiler that was found during investigation of a security report On June 26, 2023. For more details check the following [link](https://soliditylang.org/blog/2023/07/19/missing-side-effects-on-selector-access-bug/)


*There are 1 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/TimelockController.sol

4: pragma solidity ^0.8.0;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L4-L4) 


</details>


### [L&#x2011;33] Empty receive functions can cause gas issues 
In Solidity, functions that receive Ether without corresponding functionality to utilize or withdraw these funds can inadvertently lead to a permanent loss of value. This is because if someone sends Ether to the contract, they may be unable to retrieve it. To avoid this, functions receiving Ether should be accompanied by additional methods that process or allow the withdrawal of these funds. If the intent is to use the received Ether, it should trigger a separate function; if not, it should revert the transaction (for instance, via `require(msg.sender == address(weth))`). Access control checks can also prevent unintended Ether transfers, despite the slight gas cost they entail. If concerns over gas costs persist, at minimum, include a rescue function to recover unused Ether. Missteps in handling Ether in smart contracts can lead to irreversible financial losses, hence these precautions are crucial.


*There are 3 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Bridge/L1/xRenzoBridge.sol

313:     receive() external payable {}


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L313-L313) 


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

542:     receive() external payable {}


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L542-L542) 


```solidity

File: contracts/TimelockController.sol

137:     receive() external payable {}


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L137-L137) 


</details>


## Non-critical Issues

### [NC&#x2011;1] Consider using modifiers for address control 
Modifiers in Solidity can improve code readability and modularity by encapsulating repetitive checks, such as address validity checks, into a reusable construct. For example, an `onlyOwner` modifier can be used to replace repetitive `require(msg.sender == owner)` checks across several functions, reducing code redundancy and enhancing maintainability. To implement, define a modifier with the check, then apply the modifier to relevant functions.


*There are 7 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/TimelockController.sol

403:         require(msg.sender == address(this), "TimelockController: caller must be timelock");


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L403-L403) 


```solidity

File: contracts/Delegation/OperatorDelegator.sol

503:         if (msg.sender == address(eigenPod)) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L503-L503) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20.sol

108:         if (msg.sender != _user) {

122:         if (msg.sender != FACTORY) revert IXERC20_NotFactory();


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L108-L108) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L122-L122)


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Factory.sol

115:         if (XERC20(_xerc20).owner() != msg.sender) revert IXERC20Factory_NotOwner();


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L115-L115) 


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

311:         if (msg.sender != receiver) revert InvalidSender(receiver, msg.sender);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L311-L311) 


```solidity

File: contracts/Bridge/L1/xRenzoBridge.sol

148:         if (msg.sender != address(connext)) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L148-L148) 


</details>


### [NC&#x2011;2] [NatSpec] Natspec `@author` is missing from `contract` 



*There are 45 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/token/EzEthTokenStorage.sol

05: /// @title EzEthTokenStorage
06: /// @dev This contract will hold all local variables for the  Contract
07: /// When upgrading the protocol, inherit from this contract on the V2 version and change the
08: /// StorageManager to inherit from the later version.  This ensures there are no storage layout
09: /// corruptions when upgrading.
10: contract EzEthTokenStorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthTokenStorage.sol#L5-L10) 


```solidity

File: contracts/token/EzEthToken.sol

11: /// @dev This contract is the ezETH ERC20 token
12: /// Ownership of the collateral in the protocol is tracked by the ezETH token
13: contract EzEthToken is Initializable, ERC20Upgradeable, IEzEthToken, EzEthTokenStorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L11-L13) 


```solidity

File: contracts/Withdraw/WithdrawQueue.sol

11: contract WithdrawQueue is


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L11-L11) 


```solidity

File: contracts/Withdraw/WithdrawQueueStorage.sol

9: abstract contract WithdrawQueueStorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueueStorage.sol#L9-L9) 


```solidity

File: contracts/TimelockController.sol

10: /**
11:  * @dev Contract module which acts as a timelocked controller. When set as the
12:  * owner of an `Ownable` smart contract, it enforces a timelock on all
13:  * `onlyOwner` maintenance operations. This gives time for users of the
14:  * controlled contract to exit before a potentially dangerous maintenance
15:  * operation is applied.
16:  *
17:  * By default, this contract is self administered, meaning administration tasks
18:  * have to go through the timelock process. The proposer (resp executor) role
19:  * is in charge of proposing (resp executing) operations. A common use case is
20:  * to position this {TimelockController} as the owner of a smart contract, with
21:  * a multisig or a DAO as the sole proposer.
22:  *
23:  * _Available since v3.3._
24:  */


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L10-L24) 


```solidity

File: contracts/Rewards/RewardHandlerStorage.sol

6: abstract contract RewardHandlerStorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandlerStorage.sol#L6-L6) 


```solidity

File: contracts/RestakeManagerStorage.sol

15: abstract contract RestakeManagerStorageV1 is IRestakeManager {

64: abstract contract RestakeManagerStorageV2 is RestakeManagerStorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManagerStorage.sol#L15-L15) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManagerStorage.sol#L64-L64)


```solidity

File: contracts/RateProvider/BalancerRateProvider.sol

9: contract BalancerRateProvider is Initializable, IRateProvider, BalancerRateProviderStorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProvider.sol#L9-L9) 


```solidity

File: contracts/RateProvider/BalancerRateProviderStorage.sol

7: abstract contract BalancerRateProviderStorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProviderStorage.sol#L7-L7) 


```solidity

File: contracts/Permissions/RoleManager.sol

09: /// @title RoleManager
10: /// @dev This contract will track the roles and permissions in the protocol
11: /// Note: This contract is protected via a permissioned account set via the initializer.  Caution should
12: /// be used as the owner could renounce the role leaving all future actions disabled.  Additionally,
13: /// if a malicious account was able to obtain the role, they could use it to grant permissions to malicious accounts.
14: contract RoleManager is IRoleManager, AccessControlUpgradeable, RoleManagerStorageV3 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L9-L14) 


```solidity

File: contracts/Permissions/RoleManagerStorage.sol

4: /// @title RoleManagerStorage
5: /// @dev This contract will hold all local variables for the RoleManager Contract
6: /// When upgrading the protocol, inherit from this contract on the V2 version and change the
7: /// StorageManager to inherit from the later version.  This ensures there are no storage layout
8: /// corruptions when upgrading.
9: contract RoleManagerStorageV1 {

35: /// On the next version of the protocol, if new variables are added, put them in the below
36: /// contract and use this as the inheritance chain.
37: contract RoleManagerStorageV2 is RoleManagerStorageV1 {

45: contract RoleManagerStorageV3 is RoleManagerStorageV2 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManagerStorage.sol#L4-L9) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManagerStorage.sol#L35-L37), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManagerStorage.sol#L45-L45)


```solidity

File: contracts/Oracle/RenzoOracle.sol

10: /// @dev This contract will be responsible for looking up values via Chainlink
11: /// Data retrieved will be verified for liveness via a max age on the oracle lookup.
12: /// All tokens should be denominated in the same base currency and contain the same decimals on the price lookup.
13: contract RenzoOracle is


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L10-L13) 


```solidity

File: contracts/Oracle/RenzoOracleStorage.sol

8: abstract contract RenzoOracleStorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracleStorage.sol#L8-L8) 


```solidity

File: contracts/Oracle/Mantle/METHShim.sol

09: /**
10:  * @title   METHShim
11:  * @dev     The contract hard codes the decimals to 18 decimals and returns the conversion rate of 1 mETH to ETH underlying the token in the mETH protocol
12:  * @notice  This contract is a shim that implements the Chainlink AggregatorV3Interface and returns pricing from the mETH staking contract
13:  */


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L9-L13) 


```solidity

File: contracts/Oracle/Mantle/METHShimStorage.sol

7: abstract contract METHShimStorageV1 is AggregatorV3Interface {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShimStorage.sol#L7-L7) 


```solidity

File: contracts/Oracle/Binance/WBETHShimStorage.sol

7: abstract contract WBETHShimStorageV1 is AggregatorV3Interface {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShimStorage.sol#L7-L7) 


```solidity

File: contracts/Oracle/Binance/WBETHShim.sol

09: /**
10:  * @title   WBETHShim
11:  * @dev     The contract hard codes the decimals to 18 decimals and returns the conversion rate of 1 mETH to ETH underlying the token in the wBETH protocol
12:  * @notice  This contract is a shim that implements the Chainlink AggregatorV3Interface and returns pricing from the wBETH token contract
13:  */


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L9-L13) 


```solidity

File: contracts/Deposits/DepositQueueStorage.sol

9: abstract contract DepositQueueStorageV1 is IDepositQueue {

26: abstract contract DepositQueueStorageV2 is DepositQueueStorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueueStorage.sol#L9-L9) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueueStorage.sol#L26-L26)


```solidity

File: contracts/Deposits/DepositQueue.sol

10: contract DepositQueue is Initializable, ReentrancyGuardUpgradeable, DepositQueueStorageV2 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L10-L10) 


```solidity

File: contracts/Delegation/OperatorDelegator.sol

12: /// @dev This contract will be responsible for interacting with Eigenlayer
13: /// Each of these contracts deployed will be delegated to one specific operator
14: /// This contract can handle multiple ERC20 tokens, all of which will be delegated to the same operator
15: /// Each supported ERC20 token will be pointed at a single Strategy contract in EL
16: /// Only the RestakeManager should be interacting with this contract for EL interactions.
17: contract OperatorDelegator is


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L12-L17) 


```solidity

File: contracts/Delegation/OperatorDelegatorStorage.sol

11: /// @title OperatorDelegatorStorage
12: /// @dev This contract will hold all local variables for the  Contract
13: /// When upgrading the protocol, inherit from this contract on the V2 version and change the
14: /// StorageManager to inherit from the later version.  This ensures there are no storage layout
15: /// corruptions when upgrading.
16: abstract contract OperatorDelegatorStorageV1 is IOperatorDelegator {

46: abstract contract OperatorDelegatorStorageV2 is OperatorDelegatorStorageV1 {

51: abstract contract OperatorDelegatorStorageV3 is OperatorDelegatorStorageV2 {

59: abstract contract OperatorDelegatorStorageV4 is OperatorDelegatorStorageV3 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegatorStorage.sol#L11-L16) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegatorStorage.sol#L46-L46), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegatorStorage.sol#L51-L51), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegatorStorage.sol#L59-L59)


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20.sol

16: contract XERC20 is


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L16-L16) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Factory.sol

14: contract XERC20Factory is Initializable, IXERC20Factory {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L14-L14) 


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol

11: contract OptimismMintableXERC20 is ERC165Upgradeable, XERC20, IOptimismMintableERC20 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L11-L11) 


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol

14: contract OptimismMintableXERC20Factory is Initializable, XERC20Factory {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L14-L14) 


```solidity

File: contracts/Bridge/L2/xRenzoDepositStorage.sol

9: abstract contract xRenzoDepositStorageV1 is IxRenzoDeposit {

47: abstract contract xRenzoDepositStorageV2 is xRenzoDepositStorageV1 {

52: abstract contract xRenzoDepositStorageV3 is xRenzoDepositStorageV2 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L9-L9) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L47-L47), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L52-L52)


```solidity

File: contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol

10: contract ConnextReceiver is IXReceiver, Ownable, Pausable {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L10-L10) 


```solidity

File: contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol

13: /// @title CCIPReceiver - Base contract for CCIP applications that can receive messages.
14: contract Receiver is CCIPReceiver, Ownable, Pausable {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L13-L14) 


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2.sol

11: contract RenzoOracleL2 is Initializable, OwnableUpgradeable, RenzoOracleL2StorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L11-L11) 


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2Storage.sol

7: abstract contract RenzoOracleL2StorageV1 is IRenzoOracleL2 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2Storage.sol#L7-L7) 


```solidity

File: contracts/Bridge/L1/xRenzoBridge.sol

16: contract xRenzoBridge is


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L16-L16) 


```solidity

File: contracts/Bridge/L1/xRenzoBridgeStorage.sol

18: abstract contract xRenzoBridgeStorageV1 is IxRenzoBridge {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridgeStorage.sol#L18-L18) 


```solidity

File: contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol

9: interface IXERC20Registry {

17: interface L1StandardBridge {

28: /// @notice This adapter is only used for sending assets from Ethereum mainnet to Blast.
29: /// @dev Combines Lockbox deposit and Blast bridge's BridgeERC20 call to minimize user transactions.
30: contract LockboxAdapterBlast {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L9-L9) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L17-L17), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L28-L30)


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol

11: contract XERC20Lockbox is Initializable, IXERC20Lockbox {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L11-L11) 


</details>


### [NC&#x2011;3] Avoid the use of sensitive terms 
Use [alternative variants](https://www.zdnet.com/article/mysql-drops-master-slave-and-blacklist-whitelist-terminology/), e.g. allowlist/denylist instead of whitelist/blacklist


*There are 17 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/token/EzEthToken.sol

14:     /// @dev Allows only a whitelisted address to mint or burn ezETH tokens

20:     /// @dev Allows only a whitelisted address to pause or unpause the token


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L14-L14) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L20-L20)


```solidity

File: contracts/Rewards/RewardHandler.sol

17:     /// @dev Allows only a whitelisted address to trigger native ETH staking

23:     /// @dev Allows only a whitelisted address to configure the contract


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L17-L17) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L23-L23)


```solidity

File: contracts/RestakeManager.sol

70:     /// @dev Allows only a whitelisted address to configure the contract

76:     /// @dev Allows only a whitelisted address to set pause state


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L70-L70) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L76-L76)


```solidity

File: contracts/Permissions/RoleManager.sol

84:     /// @dev Determines if the specified address has permission to set whitelisted origin in xRenzoBridge


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L84-L84) 


```solidity

File: contracts/Permissions/RoleManagerStorage.sol

38:     /// @dev role for granting capability to update whitelisted origin in xRenzoBridge


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManagerStorage.sol#L38-L38) 


```solidity

File: contracts/Oracle/RenzoOracle.sol

28:     /// @dev Allows only a whitelisted address to configure the contract


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L28-L28) 


```solidity

File: contracts/Errors/Errors.sol

97: /// @dev Error when the origin address is not whitelisted


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L97-L97) 


```solidity

File: contracts/Deposits/DepositQueue.sol

43:     /// @dev Allows only a whitelisted address to configure the contract

55:     /// @dev Allows only a whitelisted address to trigger native ETH staking

61:     /// @dev Allows only a whitelisted address to trigger ERC20 rewards sweeping


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L43-L43) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L55-L55), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L61-L61)


```solidity

File: contracts/Delegation/OperatorDelegator.sol

49:     /// @dev Allows only a whitelisted address to configure the contract

61:     /// @dev Allows only a whitelisted address to configure the contract


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L49-L49) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L61-L61)


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

415:         // Verify the caller is whitelisted


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L415-L415) 


```solidity

File: contracts/Bridge/L1/xRenzoBridge.sol

134:      * @notice  WARNING: This function does NOT whitelist who can send funds from the L2 via Connext.  Users should NOT


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L134-L134) 


</details>


### [NC&#x2011;4] Variable names that consist of all capital letters should be reserved for `constant`/`immutable` variables 



*There are 4 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Bridge/xERC20/contracts/XERC20.sol

31:     address public FACTORY;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L31-L31) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol

18:     IXERC20 public XERC20;

23:     IERC20 public ERC20;

29:     bool public IS_NATIVE;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L18-L18) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L23-L23), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L29-L29)


</details>


### [NC&#x2011;5] Common functions should be refactored to a common base contract 
The functions below have the same implementation as is seen in other files. The functions should be refactored into functions of a common base contract


*There are 7 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Rewards/RewardHandler.sol

//@audit this function is already seen in `contracts/Bridge/L2/xRenzoDeposit.sol`
52:     receive() external payable nonReentrant {
53:         _forwardETH();
54:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L52-L54) 


```solidity

File: contracts/Oracle/Binance/WBETHShim.sol

//@audit this function is already seen in `contracts/Oracle/Binance/WBETHShim.sol`
29:     function decimals() external pure returns (uint8) {
30:         return 18;
31:     }

//@audit this function is already seen in `contracts/Oracle/Binance/WBETHShim.sol`
37:     function version() external pure returns (uint256) {
38:         return 1;
39:     }

//@audit this function is already seen in `contracts/Oracle/Binance/WBETHShim.sol`
42:     function getRoundData(uint80) external pure returns (uint80, int256, uint256, uint256, uint80) {
43:         revert NotImplemented();
44:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L29-L31) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L37-L39), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L42-L44)


```solidity

File: contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol

//@audit this function is already seen in `contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol`
096:     function updateXRenzoBridgeL1(address _newXRenzoBridgeL1) external onlyOwner {
097:         if (_newXRenzoBridgeL1 == address(0)) revert InvalidZeroInput();
098:         emit XRenzoBridgeL1Updated(_newXRenzoBridgeL1, xRenzoBridgeL1);
099:         xRenzoBridgeL1 = _newXRenzoBridgeL1;
100:     }

//@audit this function is already seen in `contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol`
117:     function unPause() external onlyOwner {
118:         _unpause();
119:     }

//@audit this function is already seen in `contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol`
134:     function setRenzoDeposit(address _newXRenzoDeposit) external onlyOwner {
135:         if (_newXRenzoDeposit == address(0)) revert InvalidZeroInput();
136:         emit XRenzoDepositUpdated(_newXRenzoDeposit, address(xRenzoDeposit));
137:         xRenzoDeposit = IxRenzoDeposit(_newXRenzoDeposit);
138:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L96-L100) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L117-L119), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L134-L138)


</details>


### [NC&#x2011;6] Overly complicated arithmetic 
To maintain readability in code, particularly in Solidity which can involve complex mathematical operations, it is often recommended to limit the number of arithmetic operations to a maximum of 2-3 per line. Too many operations in a single line can make the code difficult to read and understand, increase the likelihood of mistakes, and complicate the process of debugging and reviewing the code. Consider splitting such operations over more than one line, take special care when dealing with division however. Try to limit the number of arithmetic operations to a maximum of 3 per line.


*There are 1 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Delegation/OperatorDelegator.sol

341:         return
342:             podOwnerShares < 0
343:                 ? queuedShares[IS_NATIVE] + stakedButNotVerifiedEth - uint256(-podOwnerShares)
344:                 : queuedShares[IS_NATIVE] + stakedButNotVerifiedEth + uint256(podOwnerShares);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L341-L344) 


</details>


### [NC&#x2011;7] Constant redefined elsewhere 
Consider defining in only one contract so that values cannot become out of sync when only one location is updated. A [cheap way](https://medium.com/coinmonks/gas-cost-of-solidity-library-functions-dbe0cedd4678) to store constants in a single location is to create an `internal constant` in a `library`. If the variable is a local cache of another contract's value, consider making the cache variable internal or private, which will require external users to query the contract with the source of truth, so that callers don't get out of sync.


*There are 4 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Deposits/DepositQueue.sol

//@audit The same constant is already defined on file : contracts/Withdraw/WithdrawQueueStorage.sol
13:     address public constant IS_NATIVE = 0xEeeeeEeeeEeEeeEeEeEeeEEEeeeeEeeeeeeeEEeE;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L13-L13) 


```solidity

File: contracts/Delegation/OperatorDelegator.sol

//@audit The same constant is already defined on file : contracts/Withdraw/WithdrawQueueStorage.sol
26:     address public constant IS_NATIVE = 0xEeeeeEeeeEeEeeEeEeEeeEEEeeeeEeeeeeeeEEeE;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L26-L26) 


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2.sol

//@audit The same constant is already defined on file : contracts/Oracle/RenzoOracle.sol
13:     uint256 public constant MAX_TIME_WINDOW = 86400 + 60; // 24 hours + 60 seconds


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L13-L13) 


```solidity

File: contracts/Bridge/L1/xRenzoBridge.sol

//@audit The same constant is already defined on file : contracts/Bridge/L2/xRenzoDeposit.sol
61:     uint8 public constant EXPECTED_DECIMALS = 18;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L61-L61) 


</details>


### [NC&#x2011;8] Constants in comparisons should appear on the left side 



*There are 79 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Withdraw/WithdrawQueue.sol

//@audit `0`
78:             _coolDownPeriod == 0

//@audit `0`
77:             _withdrawalBufferTarget.length == 0 ||

//@audit `0`
91:                 _withdrawalBufferTarget[i].bufferAmount == 0

//@audit `0`
109:         if (_newBufferTarget.length == 0) revert InvalidZeroInput();

//@audit `0`
111:             if (_newBufferTarget[i].asset == address(0) || _newBufferTarget[i].bufferAmount == 0)

//@audit `0`
130:         if (_newCoolDownPeriod == 0) revert InvalidZeroInput();

//@audit `0`
196:         if (_asset == address(0) || _amount == 0) revert InvalidZeroInput();

//@audit `0`
211:         if (withdrawalBufferTarget[_assetOut] == 0) revert UnsupportedWithdrawAsset();

//@audit `0`
208:         if (_amount == 0 || _assetOut == address(0)) revert InvalidZeroInput();


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L78-L78) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L77-L77), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L91-L91), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L109-L109), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L111-L111), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L130-L130), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L196-L196), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L211-L211), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L208-L208)


```solidity

File: contracts/TimelockController.sol

//@audit `0`
155:         return getTimestamp(id) > 0;

//@audit `_DONE_TIMESTAMP`
162:         return getTimestamp(id) > _DONE_TIMESTAMP;

//@audit `_DONE_TIMESTAMP`
170:         return timestamp > _DONE_TIMESTAMP && timestamp <= block.timestamp;

//@audit `_DONE_TIMESTAMP`
177:         return getTimestamp(id) == _DONE_TIMESTAMP;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L155-L155) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L162-L162), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L170-L170), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L177-L177)


```solidity

File: contracts/Rewards/RewardHandler.sol

//@audit `0`
64:         if (balance == 0) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L64-L64) 


```solidity

File: contracts/RestakeManager.sol

//@audit `18`
231:         if (IERC20Metadata(address(_newCollateralToken)).decimals() != 18)

//@audit `0`
367:         if (operatorDelegators.length == 0) revert NotFound();

//@audit `1`
370:         if (operatorDelegators.length == 1) {

//@audit `1`
408:         if (operatorDelegators.length == 1) {

//@audit `0`
515:         if (collateralTokenTvlLimits[_collateralToken] != 0) {

//@audit `0`
546:         if (bufferToFill > 0) {

//@audit `0`
510:         if (maxDepositTVL != 0 && totalTVL + collateralTokenValue > maxDepositTVL) {

//@audit `0`
597:         if (maxDepositTVL != 0 && totalTVL + msg.value > maxDepositTVL) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L231-L231) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L367-L367), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L370-L370), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L408-L408), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L515-L515), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L546-L546), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L510-L510), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L597-L597)


```solidity

File: contracts/RateProvider/BalancerRateProvider.sol

//@audit `0`
37:         if (totalSupply == 0 || totalTVL == 0) revert InvalidZeroInput();

//@audit `0`
37:         if (totalSupply == 0 || totalTVL == 0) revert InvalidZeroInput();


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProvider.sol#L37-L37) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProvider.sol#L37-L37)


```solidity

File: contracts/Oracle/RenzoOracle.sol

//@audit `18`
61:         if (_oracleAddress.decimals() != 18)

//@audit `0`
77:         if (price <= 0) revert InvalidOraclePrice();

//@audit `0`
94:         if (price <= 0) revert InvalidOraclePrice();

//@audit `0`
146:         if (mintAmount == 0) revert InvalidTokenAmount();

//@audit `0`
130:         if (_currentValueInProtocol == 0 || _existingEzETHSupply == 0) {

//@audit `0`
130:         if (_currentValueInProtocol == 0 || _existingEzETHSupply == 0) {

//@audit `0`
161:         if (redeemAmount == 0) revert InvalidTokenAmount();


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L61-L61) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L77-L77), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L94-L94), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L146-L146), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L130-L130), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L130-L130), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L161-L161)


```solidity

File: contracts/Deposits/DepositQueue.sol

//@audit `0`
98:         if (_feeBasisPoints > 0) {

//@audit `10000`
103:         if (_feeBasisPoints > 10000) revert OverMaxBasisPoints();

//@audit `0`
138:         if (_amount == 0 || _asset == address(0)) revert InvalidZeroInput();

//@audit `0`
166:         if (feeAddress != address(0x0) && feeBasisPoints > 0) {

//@audit `0`
256:         if (balance > 0) {

//@audit `0`
260:             if (feeAddress != address(0x0) && feeBasisPoints > 0) {

//@audit `0`
298:         if (bufferToFill > 0) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L98-L98) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L103-L103), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L138-L138), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L166-L166), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L256-L256), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L260-L260), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L298-L298)


```solidity

File: contracts/Delegation/OperatorDelegator.sol

//@audit `0`
135:         if (_baseGasAmountSpent == 0) revert InvalidZeroInput();

//@audit `0`
147:         if (address(tokenStrategyMapping[token]) == address(0x0) || tokenAmount == 0)

//@audit `IS_NATIVE`
210:             if (address(tokens[i]) == IS_NATIVE) {

//@audit `IS_NATIVE`
284:             if (address(tokens[i]) != IS_NATIVE) {

//@audit `0`
290:                 if (bufferToFill > 0) {

//@audit `0`
307:                 if (balanceOfToken > 0) {

//@audit `0`
329:             queuedShares[address(this)] == 0

//@audit `0`
342:             podOwnerShares < 0

//@audit `0`
509:             if (adminGasSpentInWei[tx.origin] > 0) {

//@audit `0`
514:                 if (remainingAmount == 0) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L135-L135) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L147-L147), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L210-L210), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L284-L284), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L290-L290), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L307-L307), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L329-L329), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L342-L342), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L509-L509), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L514-L514)


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20.sol

//@audit `0`
330:         if (_amount == 0) revert IXERC20_INVALID_0_VALUE();

//@audit `0`
350:         if (_amount == 0) revert IXERC20_INVALID_0_VALUE();


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L330-L330) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L350-L350)


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol

//@audit `1`
86:         if (_bridgesLength < 1) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L86-L86) 


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

//@audit `EXPECTED_DECIMALS`
106:         if (decimals != EXPECTED_DECIMALS) {

//@audit `EXPECTED_DECIMALS`
110:         if (decimals != EXPECTED_DECIMALS) {

//@audit `EXPECTED_DECIMALS`
114:         if (decimals != EXPECTED_DECIMALS) {

//@audit `0`
98:             _bridgeDestinationDomain == 0 ||

//@audit `0`
97:             _swapKey == 0 ||

//@audit `0`
92:             _currentPrice == 0 ||

//@audit `0`
172:         if (msg.value == 0) {

//@audit `0`
186:         if (wrappedAmount == 0) {

//@audit `0`
209:         if (_amountIn == 0) {

//@audit `0`
240:         if (amountOut == 0) {

//@audit `0`
332:         if (_price == 0) {

//@audit `0`
385:         if (bridgeRouterFeeBps > 0) {

//@audit `0`
424:         if (balance == 0) {

//@audit `100`
522:         if (_newShare > 100) revert InvalidBridgeFeeShare(_newShare);

//@audit `32`
533:         if (_newBatchSize < 32 ether) revert InvalidSweepBatchSize(_newBatchSize);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L106-L106) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L110-L110), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L114-L114), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L98-L98), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L97-L97), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L92-L92), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L172-L172), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L186-L186), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L209-L209), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L240-L240), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L332-L332), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L385-L385), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L424-L424), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L522-L522), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L533-L533)


```solidity

File: contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol

//@audit `0`
53:         if (_xRenzoBridgeL1 == address(0) || _connextEthChainDomain == 0 || _connext == address(0))

//@audit `0`
104:         if (_newChainDomain == 0) revert InvalidZeroInput();


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L53-L53) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L104-L104)


```solidity

File: contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol

//@audit `0`
48:         if (_xRenzoBridgeL1 == address(0) || _ccipEthChainSelector == 0) revert InvalidZeroInput();

//@audit `0`
108:         if (_newChainSelector == 0) revert InvalidZeroInput();


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L48-L48) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L108-L108)


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2.sol

//@audit `18`
30:         if (_oracle.decimals() > 18) revert InvalidTokenDecimals(18, _oracle.decimals());

//@audit `18`
39:         if (_oracleAddress.decimals() > 18)

//@audit `1`
55:         if (_scaledPrice < 1 ether) revert InvalidOraclePrice();


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L30-L30) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L39-L39), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L55-L55)


```solidity

File: contracts/Bridge/L1/xRenzoBridge.sol

//@audit `EXPECTED_DECIMALS`
100:         if (decimals != EXPECTED_DECIMALS) {

//@audit `EXPECTED_DECIMALS`
104:         if (decimals != EXPECTED_DECIMALS) {

//@audit `EXPECTED_DECIMALS`
108:         if (decimals != EXPECTED_DECIMALS) {

//@audit `EXPECTED_DECIMALS`
112:         if (decimals != EXPECTED_DECIMALS) {

//@audit `0`
158:         if (_amount == 0) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L100-L100) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L104-L104), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L108-L108), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L112-L112), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L158-L158)


```solidity

File: contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol

//@audit `0`
65:         if (_amount <= 0) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L65-L65) 


</details>


### [NC&#x2011;9] [NatSpec] Natspec description is missing from `contract` 
It is recommended that Solidity contracts are fully annotated using NatSpec for all public interfaces (everything in the ABI). It is clearly stated in the Solidity official documentation. In complex projects such as Defi, the interpretation of all functions and their arguments and returns is important for code readability and auditability.[source](https://docs.soliditylang.org/en/v0.8.15/natspec-format.html)


*There are 133 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Withdraw/WithdrawQueue.sol

11: contract WithdrawQueue is

19:     event WithdrawBufferTargetUpdated(uint256 oldBufferTarget, uint256 newBufferTarget);

21:     event CoolDownPeriodUpdated(uint256 oldCoolDownPeriod, uint256 newCoolDownPeriod);

23:     event EthBufferFilled(uint256 amount);

25:     event ERC20BufferFilled(address asset, uint256 amount);

27:     event WithdrawRequestCreated(

36:     event WithdrawRequestClaimed(WithdrawRequest withdrawRequest);

50:     modifier onlyDepositQueue() {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L11-L11) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L19-L19), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L21-L21), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L23-L23), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L25-L25), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L27-L27), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L36-L36), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L50-L50)


```solidity

File: contracts/Withdraw/WithdrawQueueStorage.sol

9: abstract contract WithdrawQueueStorageV1 {

10:     address public constant IS_NATIVE = 0xEeeeeEeeeEeEeeEeEeEeeEEEeeeeEeeeeeeeEEeE;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueueStorage.sol#L9-L9) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueueStorage.sol#L10-L10)


```solidity

File: contracts/TimelockController.sol

26:     bytes32 public constant TIMELOCK_ADMIN_ROLE = keccak256("TIMELOCK_ADMIN_ROLE");

27:     bytes32 public constant PROPOSER_ROLE = keccak256("PROPOSER_ROLE");

28:     bytes32 public constant EXECUTOR_ROLE = keccak256("EXECUTOR_ROLE");

29:     bytes32 public constant CANCELLER_ROLE = keccak256("CANCELLER_ROLE");

30:     uint256 internal constant _DONE_TIMESTAMP = uint256(1);

32:     mapping(bytes32 => uint256) private _timestamps;

33:     uint256 private _minDelay;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L26-L26) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L27-L27), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L28-L28), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L29-L29), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L30-L30), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L32-L32), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L33-L33)


```solidity

File: contracts/Rewards/RewardHandlerStorage.sol

6: abstract contract RewardHandlerStorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandlerStorage.sol#L6-L6) 


```solidity

File: contracts/Rewards/RewardHandler.sol

29:     event RewardDestinationUpdated(address rewardDestination);

62:     function _forwardETH() internal {

72:     function setRewardDestination(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L29-L29) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L62-L62), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L72-L72)


```solidity

File: contracts/RestakeManagerStorage.sol

15: abstract contract RestakeManagerStorageV1 is IRestakeManager {

64: abstract contract RestakeManagerStorageV2 is RestakeManagerStorageV1 {

65:     mapping(IERC20 => uint256) public collateralTokenTvlLimits;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManagerStorage.sol#L15-L15) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManagerStorage.sol#L64-L64), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManagerStorage.sol#L65-L65)


```solidity

File: contracts/RestakeManager.sol

30:     event OperatorDelegatorAdded(IOperatorDelegator od);

31:     event OperatorDelegatorRemoved(IOperatorDelegator od);

32:     event OperatorDelegatorAllocationUpdated(IOperatorDelegator od, uint256 allocation);

34:     event CollateralTokenAdded(IERC20 token);

35:     event CollateralTokenRemoved(IERC20 token);

709:     function setTokenTvlLimit(IERC20 _token, uint256 _limit) external onlyRestakeManagerAdmin {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L30-L30) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L31-L31), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L32-L32), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L34-L34), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L35-L35), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L709-L709)


```solidity

File: contracts/RateProvider/BalancerRateProvider.sol

9: contract BalancerRateProvider is Initializable, IRateProvider, BalancerRateProviderStorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProvider.sol#L9-L9) 


```solidity

File: contracts/RateProvider/BalancerRateProviderStorage.sol

7: abstract contract BalancerRateProviderStorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProviderStorage.sol#L7-L7) 


```solidity

File: contracts/Permissions/RoleManagerStorage.sol

45: contract RoleManagerStorageV3 is RoleManagerStorageV2 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManagerStorage.sol#L45-L45) 


```solidity

File: contracts/Oracle/RenzoOracle.sol

23:     uint256 constant SCALE_FACTOR = 10 ** 18;

152:     function calculateRedeemAmount(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L23-L23) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L152-L152)


```solidity

File: contracts/Oracle/RenzoOracleStorage.sol

8: abstract contract RenzoOracleStorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracleStorage.sol#L8-L8) 


```solidity

File: contracts/Oracle/Mantle/METHShim.sol

29:     function decimals() external pure returns (uint8) {

33:     function description() external pure returns (string memory) {

37:     function version() external pure returns (uint256) {

46:     function latestRoundData()


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L29-L29) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L33-L33), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L37-L37), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L46-L46)


```solidity

File: contracts/Oracle/Mantle/METHShimStorage.sol

7: abstract contract METHShimStorageV1 is AggregatorV3Interface {

8:     IMethStaking public methStaking;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShimStorage.sol#L7-L7) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShimStorage.sol#L8-L8)


```solidity

File: contracts/Oracle/Binance/WBETHShimStorage.sol

7: abstract contract WBETHShimStorageV1 is AggregatorV3Interface {

8:     IStakedTokenV2 public wBETHToken;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShimStorage.sol#L7-L7) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShimStorage.sol#L8-L8)


```solidity

File: contracts/Oracle/Binance/WBETHShim.sol

29:     function decimals() external pure returns (uint8) {

33:     function description() external pure returns (string memory) {

37:     function version() external pure returns (uint256) {

46:     function latestRoundData()


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L29-L29) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L33-L33), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L37-L37), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L46-L46)


```solidity

File: contracts/Deposits/DepositQueueStorage.sol

9: abstract contract DepositQueueStorageV1 is IDepositQueue {

26: abstract contract DepositQueueStorageV2 is DepositQueueStorageV1 {

27:     IWithdrawQueue public withdrawQueue;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueueStorage.sol#L9-L9) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueueStorage.sol#L26-L26), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueueStorage.sol#L27-L27)


```solidity

File: contracts/Deposits/DepositQueue.sol

10: contract DepositQueue is Initializable, ReentrancyGuardUpgradeable, DepositQueueStorageV2 {

13:     address public constant IS_NATIVE = 0xEeeeeEeeeEeEeeEeEeEeeEEEeeeeEeeeeeeeEEeE;

15:     event RewardsDeposited(IERC20 token, uint256 amount);

17:     event FeeConfigUpdated(address feeAddress, uint256 feeBasisPoints);

19:     event RestakeManagerUpdated(IRestakeManager restakeManager);

21:     event ETHDepositedFromProtocol(uint256 amount);

23:     event ETHStakedFromQueue(

30:     event ProtocolFeesPaid(IERC20 token, uint256 amount, address destination);

32:     event GasRefunded(address admin, uint256 gasRefunded);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L10-L10) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L13-L13), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L15-L15), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L17-L17), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L19-L19), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L21-L21), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L23-L23), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L30-L30), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L32-L32)


```solidity

File: contracts/Delegation/OperatorDelegator.sol

24:     uint256 internal constant GWEI_TO_WEI = 1e9;

26:     address public constant IS_NATIVE = 0xEeeeeEeeeEeEeeEeEeEeeEEEeeeeEeeeeeeeEEeE;

28:     event TokenStrategyUpdated(IERC20 token, IStrategy strategy);

29:     event DelegationAddressUpdated(address delegateAddress);

30:     event RewardsForwarded(address rewardDestination, uint256 amount);

32:     event WithdrawStarted(

43:     event WithdrawCompleted(bytes32 withdrawalRoot, IStrategy[] strategies, uint256[] shares);

45:     event GasSpent(address admin, uint256 gasSpent);

46:     event GasRefunded(address admin, uint256 gasRefunded);

47:     event BaseGasAmountSpentUpdated(uint256 oldBaseGasAmountSpent, uint256 newBaseGasAmountSpent);

132:     function setBaseGasAmountSpent(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L24-L24) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L26-L26), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L28-L28), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L29-L29), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L30-L30), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L32-L32), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L43-L43), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L45-L45), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L46-L46), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L47-L47), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L132-L132)


```solidity

File: contracts/Delegation/OperatorDelegatorStorage.sol

46: abstract contract OperatorDelegatorStorageV2 is OperatorDelegatorStorageV1 {

51: abstract contract OperatorDelegatorStorageV3 is OperatorDelegatorStorageV2 {

59: abstract contract OperatorDelegatorStorageV4 is OperatorDelegatorStorageV3 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegatorStorage.sol#L46-L46) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegatorStorage.sol#L51-L51), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegatorStorage.sol#L59-L59)


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20.sol

16: contract XERC20 is


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L16-L16) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Factory.sol

14: contract XERC20Factory is Initializable, IXERC20Factory {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L14-L14) 


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol

11: contract OptimismMintableXERC20 is ERC165Upgradeable, XERC20, IOptimismMintableERC20 {

48:     function supportsInterface(

56:     function remoteToken() public view override returns (address) {

60:     function bridge() public view override returns (address) {

64:     function mint(address _to, uint256 _amount) public override(XERC20, IOptimismMintableERC20) {

68:     function burn(address _from, uint256 _amount) public override(XERC20, IOptimismMintableERC20) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L11-L11) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L48-L48), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L56-L56), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L60-L60), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L64-L64), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L68-L68)


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol

14: contract OptimismMintableXERC20Factory is Initializable, XERC20Factory {

15:     error OptimismMintableXERC20Factory_NoBridges();


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L14-L14) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L15-L15)


```solidity

File: contracts/Bridge/L2/xRenzoDepositStorage.sol

9: abstract contract xRenzoDepositStorageV1 is IxRenzoDeposit {

47: abstract contract xRenzoDepositStorageV2 is xRenzoDepositStorageV1 {

52: abstract contract xRenzoDepositStorageV3 is xRenzoDepositStorageV2 {

54:     uint256 public bridgeFeeShare;

57:     uint256 public sweepBatchSize;

60:     uint256 public bridgeFeeCollected;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L9-L9) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L47-L47), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L52-L52), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L54-L54), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L57-L57), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L60-L60)


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

42:     event PriceUpdated(uint256 price, uint256 timestamp);

43:     event Deposit(address indexed user, uint256 amountIn, uint256 amountOut);

44:     event BridgeSweeperAddressUpdated(address sweeper, bool allowed);

45:     event BridgeSwept(

51:     event OraclePriceFeedUpdated(address newOracle, address oldOracle);

52:     event ReceiverPriceFeedUpdated(address newReceiver, address oldReceiver);

53:     event SweeperBridgeFeeCollected(address sweeper, uint256 feeCollected);

54:     event BridgeFeeShareUpdated(uint256 oldBridgeFeeShare, uint256 newBridgeFeeShare);

55:     event SweepBatchSizeUpdated(uint256 oldSweepBatchSize, uint256 newSweepBatchSize);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L42-L42) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L43-L43), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L44-L44), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L45-L45), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L51-L51), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L52-L52), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L53-L53), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L54-L54), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L55-L55)


```solidity

File: contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol

10: contract ConnextReceiver is IXReceiver, Ownable, Pausable {

23:     event XRenzoBridgeL1Updated(address newBridgeAddress, address oldBridgeAddress);

24:     event ConnextEthChainDomainUpdated(uint32 newSourceChainDomain, uint32 oldSourceChainDomain);

25:     event XRenzoDepositUpdated(address newRenzoDeposit, address oldRenzoDeposit);

43:     modifier onlySource(address _originSender, uint32 _origin) {

52:     constructor(address _connext, address _xRenzoBridgeL1, uint32 _connextEthChainDomain) {

69:     function xReceive(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L10-L10) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L23-L23), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L24-L24), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L25-L25), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L43-L43), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L52-L52), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L69-L69)


```solidity

File: contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol

24:     event XRenzoBridgeL1Updated(address newBridgeAddress, address oldBridgeAddress);

25:     event CCIPEthChainSelectorUpdated(uint64 newSourceChainSelector, uint64 oldSourceChainSelector);

26:     event XRenzoDepositUpdated(address newRenzoDeposit, address oldRenzoDeposit);

43:     constructor(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L24-L24) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L25-L25), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L26-L26), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L43-L43)


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2.sol

11: contract RenzoOracleL2 is Initializable, OwnableUpgradeable, RenzoOracleL2StorageV1 {

15:     event OracleAddressUpdated(address newOracle, address oldOracle);

23:     function initialize(AggregatorV3Interface _oracle) public initializer {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L11-L11) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L15-L15), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L23-L23)


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2Storage.sol

7: abstract contract RenzoOracleL2StorageV1 is IRenzoOracleL2 {

8:     AggregatorV3Interface public oracle;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2Storage.sol#L7-L7) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2Storage.sol#L8-L8)


```solidity

File: contracts/Bridge/L1/xRenzoBridge.sol

16: contract xRenzoBridge is

43:     event ConnextMessageSent(

50:     modifier onlyBridgeAdmin() {

55:     modifier onlyPriceFeedSender() {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L16-L16) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L43-L43), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L50-L50), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L55-L55)


```solidity

File: contracts/Bridge/L1/xRenzoBridgeStorage.sol

18: abstract contract xRenzoBridgeStorageV1 is IxRenzoBridge {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridgeStorage.sol#L18-L18) 


```solidity

File: contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol

9: interface IXERC20Registry {

17: interface L1StandardBridge {

10:     function getXERC20(address erc20) external view returns (address xerc20);

12:     function getERC20(address xerc20) external view returns (address erc20);

14:     function getLockbox(address erc20) external view returns (address xerc20);

18:     function bridgeERC20To(

31:     address immutable blastStandardBridge;

32:     address immutable registry;

35:     error InvalidRemoteToken(address _remoteToken);

36:     error AmountLessThanZero();

37:     error InvalidAddress();

39:     constructor(address _blastStandardBridge, address _registry) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L9-L9) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L17-L17), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L10-L10), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L12-L12), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L14-L14), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L18-L18), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L31-L31), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L32-L32), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L35-L35), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L36-L36), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L37-L37), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L39-L39)


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol

11: contract XERC20Lockbox is Initializable, IXERC20Lockbox {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L11-L11) 


</details>


### [NC&#x2011;10] Contract does not follow the Solidity style guide's suggested layout ordering 
The [style guide](https://docs.soliditylang.org/en/v0.8.16/style-guide.html#order-of-layout) says that, within a contract, the ordering should be 1) Type declarations, 2) State variables, 3) Events, 4) Modifiers, and 5) Functions, but the contract(s) below do not follow this ordering


*There are 3 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Rewards/RewardHandler.sol

//@audit the event definition is misplaced
29:     event RewardDestinationUpdated(address rewardDestination);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L29-L29) 


```solidity

File: contracts/Oracle/RenzoOracle.sol

//@audit the event definition is misplaced
35:     event OracleAddressUpdated(IERC20 token, AggregatorV3Interface oracleAddress);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L35-L35) 


```solidity

File: contracts/Bridge/L1/xRenzoBridge.sol

//@audit the variable definition is misplaced
61:     uint8 public constant EXPECTED_DECIMALS = 18;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L61-L61) 


</details>


### [NC&#x2011;11] Control structures do not follow the Solidity Style Guide 
See the [control structures](https://docs.soliditylang.org/en/latest/style-guide.html#control-structures) section of the Solidity Style Guide


*There are 81 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/token/EzEthToken.sol

56:     function _beforeTokenTransfer(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L56-L56) 


```solidity

File: contracts/Withdraw/WithdrawQueue.sol

64:     function initialize(

106:     function updateWithdrawBufferTarget(

192:     function fillERC20WithdrawBuffer(

72:         if (

89:             if (


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L64-L64) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L106-L106), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L192-L192), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L72-L72), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L89-L89)


```solidity

File: contracts/TimelockController.sol

142:     function supportsInterface(

201:     function hashOperation(

215:     function hashOperationBatch(

234:     function schedule(

259:     function scheduleBatch(

315:     function execute(

342:     function executeBatch(

411:     function onERC721Received(

423:     function onERC1155Received(

436:     function onERC1155BatchReceived(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L142-L142) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L201-L201), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L215-L215), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L234-L234), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L259-L259), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L315-L315), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L342-L342), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L411-L411), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L423-L423), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L436-L436)


```solidity

File: contracts/Rewards/RewardHandler.sol

72:     function setRewardDestination(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L72-L72) 


```solidity

File: contracts/RestakeManager.sol

101:     function initialize(

131:     function addOperatorDelegator(

160:     function removeOperatorDelegator(

187:     function setOperatorDelegatorAllocation(

244:     function removeCollateralToken(

362:     function chooseOperatorDelegatorForDeposit(

400:     function chooseOperatorDelegatorForWithdraw(

491:     function deposit(

620:     function stakeEthInOperatorDelegator(

647:     function depositTokenRewardsFromProtocol(

377:             if (

419:             if (


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L101-L101) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L131-L131), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L160-L160), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L187-L187), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L244-L244), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L362-L362), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L400-L400), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L491-L491), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L620-L620), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L647-L647), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L377-L377), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L419-L419)


```solidity

File: contracts/RateProvider/BalancerRateProvider.sol

17:     function initialize(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProvider.sol#L17-L17) 


```solidity

File: contracts/Oracle/RenzoOracle.sol

54:     function setOracleAddress(

85:     function lookupTokenAmountFromValue(

103:     function lookupTokenValues(

123:     function calculateMintAmount(

152:     function calculateRedeemAmount(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L54-L54) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L85-L85), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L103-L103), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L123-L123), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L152-L152)


```solidity

File: contracts/Deposits/DepositQueue.sol

93:     function setFeeConfig(

134:     function fillERC20withdrawBuffer(

187:     function stakeEthFromQueue(

211:     function stakeEthFromQueueMulti(

219:         if (


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L93-L93) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L134-L134), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L187-L187), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L211-L211), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L219-L219)


```solidity

File: contracts/Delegation/OperatorDelegator.sol

74:     function initialize(

106:     function setTokenStrategy(

117:     function setDelegateAddress(

132:     function setBaseGasAmountSpent(

143:     function deposit(

193:     function queueWithdrawals(

265:     function completeQueuedWithdrawal(

349:     function stakeEth(

364:     function verifyWithdrawalCredentials(

405:     function verifyAndProcessWithdrawals(

432:     function withdrawNonBeaconChainETHBalanceWei(

446:     function recoverTokens(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L74-L74) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L106-L106), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L117-L117), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L132-L132), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L143-L143), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L193-L193), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L265-L265), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L349-L349), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L364-L364), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L405-L405), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L432-L432), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L446-L446)


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20.sol

61:     function initialize(

76:     function __XERC20_init(

135:     function setLimits(

276:     function _calculateNewCurrentLimit(

302:     function _getCurrentLimit(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L61-L61) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L76-L76), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L135-L135), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L276-L276), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L302-L302)


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Factory.sol

54:     function initialize(

74:     function deployXERC20(

105:     function deployLockbox(

135:     function _deployXERC20(

184:     function _deployLockbox(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L54-L54) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L74-L74), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L105-L105), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L135-L135), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L184-L184)


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol

35:     function initialize(

48:     function supportsInterface(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L35-L35) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L48-L48)


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol

37:     function deployOptimismMintableXERC20(

73:     function _deployOptimismMintableXERC20(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L37-L37) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L73-L73)


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

75:     function initialize(

168:     function depositETH(

204:     function deposit(

227:     function _deposit(

91:         if (

337:         if (


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L75-L75) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L168-L168), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L204-L204), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L227-L227), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L91-L91), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L337-L337)


```solidity

File: contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol

69:     function xReceive(

44:         if (


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L69-L69) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L44-L44)


```solidity

File: contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol

66:     function _ccipReceive(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L66-L66) 


```solidity

File: contracts/Bridge/L1/xRenzoBridge.sol

70:     function initialize(

139:     function xReceive(

210:     function sendPrice(

83:         if (


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L70-L70) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L139-L139), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L210-L210), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L83-L83)


```solidity

File: contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol

18:     function bridgeERC20To(

56:     function bridgeTo(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L18-L18) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L56-L56)


</details>


### [NC&#x2011;12] Custom error has no error details 
Consider adding parameters to the error to indicate which user or values caused the failure


*There are 43 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Errors/Errors.sol

5: error InvalidZeroInput();

8: error AlreadyAdded();

11: error NotFound();

14: error MaxTVLReached();

17: error NotRestakeManagerAdmin();

20: error NotDepositQueue();

23: error ContractPaused();

26: error OverMaxBasisPoints();

32: error WithdrawAlreadyCompleted();

38: error NotOperatorDelegatorAdmin();

41: error NotOracleAdmin();

44: error NotRestakeManager();

47: error NotNativeEthRestakeAdmin();

50: error DelegateAddressAlreadySet();

53: error NotERC20RewardsAdmin();

56: error TransferFailed();

59: error NotEzETHMinterBurner();

62: error NotTokenAdmin();

65: error OracleNotFound();

68: error OraclePriceExpired();

71: error MismatchedArrayLengths();

74: error NotDepositWithdrawPauser();

77: error MaxTokenTVLReached();

80: error InvalidOraclePrice();

83: error NotImplemented();

86: error InvalidTokenAmount();

92: error InsufficientOutputAmount();

95: error InvalidTokenReceived();

98: error InvalidOrigin();

104: error InvalidZeroOutput();

113: error UnauthorizedBridgeSweeper();

116: error NotBridgeAdmin();

119: error NotPriceFeedSender();

122: error UnAuthorisedCall();

125: error PriceFeedNotAvailable();

134: error NotWithdrawQueueAdmin();

137: error NotEnoughWithdrawBuffer();

140: error EarlyClaim();

143: error UnsupportedWithdrawAsset();

146: error InvalidWithdrawIndex();


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L5-L5) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L8-L8), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L11-L11), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L14-L14), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L17-L17), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L20-L20), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L23-L23), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L26-L26), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L32-L32), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L38-L38), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L41-L41), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L44-L44), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L47-L47), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L50-L50), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L53-L53), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L56-L56), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L59-L59), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L62-L62), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L65-L65), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L68-L68), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L71-L71), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L74-L74), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L77-L77), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L80-L80), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L83-L83), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L86-L86), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L92-L92), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L95-L95), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L98-L98), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L104-L104), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L113-L113), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L116-L116), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L119-L119), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L122-L122), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L125-L125), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L134-L134), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L137-L137), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L140-L140), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L143-L143), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L146-L146)


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol

15:     error OptimismMintableXERC20Factory_NoBridges();


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L15-L15) 


```solidity

File: contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol

36:     error AmountLessThanZero();

37:     error InvalidAddress();


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L36-L36) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L37-L37)


</details>


### [NC&#x2011;13] Default address(0) can be returned 
Allowing a function in Solidity to return the default address (address(0)) can be problematic as it can represent uninitialized or invalid addresses. If such an address is utilized in transfer operations or other sensitive actions, it could lead to loss of funds or unpredicted behavior. It's prudent to include checks in your functions to prevent the return of the zero address, enhancing contract security.


*There are 2 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol

57:         return l1Token;

61:         return optimismBridge;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L57-L57) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L61-L61)


</details>


### [NC&#x2011;14] Consider using `delete` rather than assigning `zero` to clear values 
The `delete` keyword more closely matches the semantics of what is being done, and draws more attention to the changing of state, which may lead to a more thorough audit of its associated logic


*There are 2 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/RestakeManager.sol

168:                 operatorDelegatorAllocations[_operatorDelegatorToRemove] = 0;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L168-L168) 


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

398:         bridgeFeeCollected = 0;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L398-L398) 


</details>


### [NC&#x2011;15] Dependence on external protocols 
External protocols should be monitored as such dependencies may introduce vulnerabilities if a vulnerability is found /introduced in the external protocol


*There are 9 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Oracle/RenzoOracleStorage.sol

5: import "@chainlink/contracts/src/v0.8/interfaces/AggregatorV3Interface.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracleStorage.sol#L5-L5) 


```solidity

File: contracts/Oracle/Mantle/METHShimStorage.sol

4: import "@chainlink/contracts/src/v0.8/interfaces/AggregatorV3Interface.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShimStorage.sol#L4-L4) 


```solidity

File: contracts/Oracle/Binance/WBETHShimStorage.sol

4: import "@chainlink/contracts/src/v0.8/interfaces/AggregatorV3Interface.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShimStorage.sol#L4-L4) 


```solidity

File: contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol

4: import { Client } from "@chainlink/contracts-ccip/src/v0.8/ccip/libraries/Client.sol";

5: import {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L4-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L5-L5)


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2Storage.sol

5: import "@chainlink/contracts/src/v0.8/interfaces/AggregatorV3Interface.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2Storage.sol#L5-L5) 


```solidity

File: contracts/Bridge/L1/xRenzoBridge.sol

13: import { Client } from "@chainlink/contracts-ccip/src/v0.8/ccip/libraries/Client.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L13-L13) 


```solidity

File: contracts/Bridge/L1/xRenzoBridgeStorage.sol

9: import {

13: import {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridgeStorage.sol#L9-L9) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridgeStorage.sol#L13-L13)


</details>


### [NC&#x2011;16] `else`-block not required 
One level of nesting can be removed by not having an `else` block when the `if`-block returns:


*There are 4 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Withdraw/WithdrawQueue.sol

157:         if (_asset != IS_NATIVE) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L157-L157) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20.sol

309:         if (_limit == _maxLimit) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L309-L309) 


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

279:         if (_amountIn < sweepBatchSize) {

292:         if (address(oracle) != address(0)) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L279-L279) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L292-L292)


</details>


### [NC&#x2011;17] Consider adding emergency-stop functionality 
In the event of a security breach or any unforeseen emergency, swiftly suspending all protocol operations becomes crucial. Having a mechanism in place to halt all functions collectively, instead of pausing individual contracts separately, substantially enhances the efficiency of mitigating ongoing attacks or vulnerabilities. This not only quickens the response time to potential threats but also reduces operational stress during these critical periods. Therefore, consider integrating a 'circuit breaker' or 'emergency stop' function into the smart contract system architecture. Such a feature would provide the capability to suspend the entire protocol instantly, which could prove invaluable during a time-sensitive crisis management situation.


*There are 1 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Withdraw/WithdrawQueue.sol

//@audit `PausableUpgradeable`
11: contract WithdrawQueue is


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L11-L11) 


</details>


### [NC&#x2011;18] Empty bytes check is missing 
When developing smart contracts in Solidity, it's crucial to validate the inputs of your functions. This includes ensuring that the bytes parameters are not empty, especially when they represent crucial data such as addresses, identifiers, or raw data that the contract needs to process.
Missing empty bytes checks can lead to unexpected behaviour in your contract.For instance, certain operations might fail, produce incorrect results, or consume unnecessary gas when performed with empty bytes.Moreover, missing input validation can potentially expose your contract to malicious activity, including exploitation of unhandled edge cases.
To mitigate these issues, always validate that bytes parameters are not empty when the logic of your contract requires it.


*There are 20 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/TimelockController.sol

//@audit  ,id are not checked
168:     function isOperationReady(bytes32 id) public view virtual returns (bool) {
169:         uint256 timestamp = getTimestamp(id);

//@audit  ,id are not checked
184:     function getTimestamp(bytes32 id) public view virtual returns (uint256) {
185:         return _timestamps[id];

//@audit  ,data ,predecessor ,salt are not checked
201:     function hashOperation(
202:         address target,
203:         uint256 value,
204:         bytes calldata data,
205:         bytes32 predecessor,
206:         bytes32 salt
207:     ) public pure virtual returns (bytes32) {

//@audit  ,predecessor ,salt are not checked
215:     function hashOperationBatch(
216:         address[] calldata targets,
217:         uint256[] calldata values,
218:         bytes[] calldata payloads,
219:         bytes32 predecessor,
220:         bytes32 salt
221:     ) public pure virtual returns (bytes32) {

//@audit  ,data ,predecessor are not checked
234:     function schedule(
235:         address target,
236:         uint256 value,
237:         bytes calldata data,
238:         bytes32 predecessor,
239:         bytes32 salt,
240:         uint256 delay
241:     ) public virtual onlyRole(PROPOSER_ROLE) {

//@audit  ,predecessor are not checked
259:     function scheduleBatch(
260:         address[] calldata targets,
261:         uint256[] calldata values,
262:         bytes[] calldata payloads,
263:         bytes32 predecessor,
264:         bytes32 salt,
265:         uint256 delay
266:     ) public virtual onlyRole(PROPOSER_ROLE) {

//@audit  ,id are not checked
283:     function _schedule(bytes32 id, uint256 delay) private {
284:         require(!isOperation(id), "TimelockController: operation already scheduled");

//@audit  ,id are not checked
296:     function cancel(bytes32 id) public virtual onlyRole(CANCELLER_ROLE) {
297:         require(isOperationPending(id), "TimelockController: operation cannot be cancelled");

//@audit  ,payload ,predecessor ,salt are not checked
315:     function execute(
316:         address target,
317:         uint256 value,
318:         bytes calldata payload,
319:         bytes32 predecessor,
320:         bytes32 salt
321:     ) public payable virtual onlyRoleOrOpenRole(EXECUTOR_ROLE) {

//@audit  ,predecessor ,salt are not checked
342:     function executeBatch(
343:         address[] calldata targets,
344:         uint256[] calldata values,
345:         bytes[] calldata payloads,
346:         bytes32 predecessor,
347:         bytes32 salt
348:     ) public payable virtual onlyRoleOrOpenRole(EXECUTOR_ROLE) {

//@audit  ,data are not checked
368:     function _execute(address target, uint256 value, bytes calldata data) internal virtual {
369:         (bool success, ) = target.call{ value: value }(data);

//@audit  ,id are not checked
376:     function _beforeCall(bytes32 id, bytes32 predecessor) private view {
377:         require(isOperationReady(id), "TimelockController: operation is not ready");

//@audit  ,id are not checked
387:     function _afterCall(bytes32 id) private {
388:         require(isOperationReady(id), "TimelockController: operation is not ready");


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L168-L169) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L184-L185), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L201-L207), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L215-L221), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L234-L241), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L259-L266), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L283-L284), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L296-L297), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L315-L321), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L342-L348), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L368-L369), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L376-L377), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L387-L388)


```solidity

File: contracts/RestakeManager.sol

//@audit  ,pubkey ,signature ,depositDataRoot are not checked
620:     function stakeEthInOperatorDelegator(
621:         IOperatorDelegator operatorDelegator,
622:         bytes calldata pubkey,
623:         bytes calldata signature,
624:         bytes32 depositDataRoot
625:     ) external payable onlyDepositQueue {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L620-L625) 


```solidity

File: contracts/Deposits/DepositQueue.sol

//@audit  ,pubkey ,signature ,depositDataRoot are not checked
187:     function stakeEthFromQueue(
188:         IOperatorDelegator operatorDelegator,
189:         bytes calldata pubkey,
190:         bytes calldata signature,
191:         bytes32 depositDataRoot
192:     ) external onlyNativeEthRestakeAdmin {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L187-L192) 


```solidity

File: contracts/Delegation/OperatorDelegator.sol

//@audit  ,approverSalt are not checked
117:     function setDelegateAddress(
118:         address _delegateAddress,
119:         ISignatureUtils.SignatureWithExpiry memory approverSignatureAndExpiry,
120:         bytes32 approverSalt
121:     ) external nonReentrant onlyOperatorDelegatorAdmin {

//@audit  ,pubkey ,signature ,depositDataRoot are not checked
349:     function stakeEth(
350:         bytes calldata pubkey,
351:         bytes calldata signature,
352:         bytes32 depositDataRoot
353:     ) external payable onlyRestakeManager {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L117-L121) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L349-L353)


```solidity

File: contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol

//@audit  ,_transferId ,_callData are not checked
69:     function xReceive(
70:         bytes32 _transferId,
71:         uint256,
72:         address,
73:         address _originSender,
74:         uint32 _origin,
75:         bytes memory _callData
76:     ) external onlySource(_originSender, _origin) whenNotPaused returns (bytes memory) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L69-L76) 


```solidity

File: contracts/Bridge/L1/xRenzoBridge.sol

//@audit  ,_transferId are not checked
139:     function xReceive(
140:         bytes32 _transferId,
141:         uint256 _amount,
142:         address _asset,
143:         address _originSender,
144:         uint32 _origin,
145:         bytes memory
146:     ) external nonReentrant returns (bytes memory) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L139-L146) 


```solidity

File: contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol

//@audit  ,_extraData are not checked
56:     function bridgeTo(
57:         address _to,
58:         address _erc20,
59:         address _remoteToken,
60:         uint256 _amount,
61:         uint32 _minGasLimit,
62:         bytes calldata _extraData
63:     ) external {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L56-L63) 


</details>


### [NC&#x2011;19] Events are missing sender information 
When an action is triggered based on a user's action, not being able to filter based on who triggered the action makes event processing a lot more cumbersome. Including the `msg.sender` the events of these types of action will make events much more useful to end users, especially when `msg.sender` is not `tx.origin`.


*There are 69 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Withdraw/WithdrawQueue.sol

113:             emit WithdrawBufferTargetUpdated(
114:                 withdrawalBufferTarget[_newBufferTarget[i].asset],
115:                 _newBufferTarget[i].bufferAmount
116:             );

131:         emit CoolDownPeriodUpdated(coolDownPeriod, _newCoolDownPeriod);

183:         emit EthBufferFilled(msg.value);

198:         emit ERC20BufferFilled(_asset, _amount);

311:         emit WithdrawRequestClaimed(_withdrawRequest);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L113-L116) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L131-L131), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L183-L183), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L198-L198), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L311-L311)


```solidity

File: contracts/TimelockController.sol

118:         emit MinDelayChange(0, minDelay);

244:         emit CallScheduled(id, 0, target, value, data, predecessor, delay);

246:             emit CallSalt(id, salt);

273:             emit CallScheduled(id, i, targets[i], values[i], payloads[i], predecessor, delay);

276:             emit CallSalt(id, salt);

300:         emit Cancelled(id);

326:         emit CallExecuted(id, 0, target, value, payload);

360:             emit CallExecuted(id, i, target, value, payload);

404:         emit MinDelayChange(_minDelay, newDelay);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L118-L118) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L244-L244), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L246-L246), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L273-L273), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L276-L276), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L300-L300), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L326-L326), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L360-L360), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L404-L404)


```solidity

File: contracts/Rewards/RewardHandler.sol

47:         emit RewardDestinationUpdated(_rewardDestination);

79:         emit RewardDestinationUpdated(_rewardDestination);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L47-L47) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L79-L79)


```solidity

File: contracts/RestakeManager.sol

151:         emit OperatorDelegatorAdded(_newOperatorDelegator);

156:         emit OperatorDelegatorAllocationUpdated(_newOperatorDelegator, _allocationBasisPoints);

169:                 emit OperatorDelegatorAllocationUpdated(_operatorDelegatorToRemove, 0);

174:                 emit OperatorDelegatorRemoved(_operatorDelegatorToRemove);

211:         emit OperatorDelegatorAllocationUpdated(_operatorDelegator, _allocationBasisPoints);

240:         emit CollateralTokenAdded(_newCollateralToken);

253:                 emit CollateralTokenRemoved(_collateralTokenToRemove);

716:         emit CollateralTokenTvlUpdated(_token, _limit);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L151-L151) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L156-L156), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L169-L169), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L174-L174), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L211-L211), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L240-L240), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L253-L253), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L716-L716)


```solidity

File: contracts/Oracle/RenzoOracle.sol

65:         emit OracleAddressUpdated(_token, _oracleAddress);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L65-L65) 


```solidity

File: contracts/Deposits/DepositQueue.sol

89:         emit WithdrawQueueUpdated(address(withdrawQueue), address(_withdrawQueue));

108:         emit FeeConfigUpdated(_feeAddress, _feeBasisPoints);

117:         emit RestakeManagerUpdated(_restakeManager);

125:         emit ETHDepositedFromProtocol(msg.value);

155:         emit FullWithdrawalETHReceived(msg.value);

182:         emit RewardsDeposited(IERC20(address(0x0)), remainingRewards);

171:             emit ProtocolFeesPaid(IERC20(address(0x0)), feeAmount, feeAddress);

202:         emit ETHStakedFromQueue(operatorDelegator, pubkey, 32 ether, address(this).balance);

236:             emit ETHStakedFromQueue(
237:                 operatorDelegators[i],
238:                 pubkeys[i],
239:                 32 ether,
240:                 address(this).balance
241:             );

275:             emit RewardsDeposited(IERC20(address(token)), balance - feeAmount);

264:                 emit ProtocolFeesPaid(token, feeAmount, feeAddress);

304:             emit BufferFilled(IS_NATIVE, bufferToFill);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L89-L89) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L108-L108), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L117-L117), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L125-L125), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L155-L155), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L182-L182), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L171-L171), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L202-L202), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L236-L241), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L275-L275), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L264-L264), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L304-L304)


```solidity

File: contracts/Delegation/OperatorDelegator.sol

113:         emit TokenStrategyUpdated(_token, _strategy);

129:         emit DelegationAddressUpdated(_delegateAddress);

136:         emit BaseGasAmountSpentUpdated(baseGasAmountSpent, _baseGasAmountSpent);

241:         emit WithdrawStarted(
242:             withdrawalRoot,
243:             address(this),
244:             delegateAddress,
245:             address(this),
246:             nonce,
247:             block.number,
248:             queuedWithdrawalParams[0].strategies,
249:             queuedWithdrawalParams[0].shares
250:         );

317:         emit WithdrawCompleted(
318:             delegationManager.calculateWithdrawalRoot(withdrawal),
319:             withdrawal.strategies,
320:             withdrawal.shares
321:         );

491:         emit GasRefunded(tx.origin, gasRefund);

523:             emit RewardsForwarded(destination, remainingAmount);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L113-L113) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L129-L129), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L136-L136), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L241-L250), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L317-L321), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L491-L491), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L523-L523)


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20.sol

125:         emit LockboxSet(_lockbox);

142:         emit BridgeLimitsSet(_mintingLimit, _burningLimit, _bridge);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L125-L125) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L142-L142)


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Factory.sol

91:         emit XERC20Deployed(_xerc20);

120:         emit LockboxDeployed(_lockbox);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L91-L91) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L120-L120)


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol

56:         emit XERC20Deployed(_xerc20);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L56-L56) 


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

358:         emit PriceUpdated(_price, _timestamp);

469:         emit BridgeSweeperAddressUpdated(_sweeper, _allowed);

502:         emit OraclePriceFeedUpdated(address(_oracle), address(oracle));

512:         emit ReceiverPriceFeedUpdated(_receiver, receiver);

523:         emit BridgeFeeShareUpdated(bridgeFeeShare, _newShare);

534:         emit SweepBatchSizeUpdated(sweepBatchSize, _newBatchSize);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L358-L358) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L469-L469), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L502-L502), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L512-L512), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L523-L523), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L534-L534)


```solidity

File: contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol

80:         emit MessageReceived(_transferId, _origin, _originSender, _price, _timestamp);

94:         emit XRenzoBridgeL1Updated(_newXRenzoBridgeL1, xRenzoBridgeL1);

105:         emit ConnextEthChainDomainUpdated(_newChainDomain, connextEthChainDomain);

132:         emit XRenzoDepositUpdated(_newXRenzoDeposit, address(xRenzoDeposit));


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L80-L80) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L94-L94), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L105-L105), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L132-L132)


```solidity

File: contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol

78:         emit MessageReceived(
79:             any2EvmMessage.messageId,
80:             _ccipSourceChainSelector,
81:             _ccipSender,
82:             _price,
83:             _timestamp
84:         );

98:         emit XRenzoBridgeL1Updated(_newXRenzoBridgeL1, xRenzoBridgeL1);

109:         emit CCIPEthChainSelectorUpdated(_newChainSelector, ccipEthChainSelector);

136:         emit XRenzoDepositUpdated(_newXRenzoDeposit, address(xRenzoDeposit));


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L78-L84) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L98-L98), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L109-L109), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L136-L136)


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2.sol

42:         emit OracleAddressUpdated(address(_oracleAddress), address(oracle));


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L42-L42) 


```solidity

File: contracts/Bridge/L1/xRenzoBridge.sol

196:         emit EzETHMinted(_transferId, _amount, _origin, _originSender, ezETHAmount);

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

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L196-L196) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L250-L257), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L275-L280)


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol

126:         emit Withdraw(_to, _amount);

151:         emit Deposit(_to, _amount);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L126-L126) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L151-L151)


</details>


### [NC&#x2011;20] Events may be emitted out of order due to reentrancy 
Ensure that events follow the best practice of check-effects-interaction, and are emitted before external calls


*There are 10 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/RestakeManager.sol

151:         emit OperatorDelegatorAdded(_newOperatorDelegator);

174:                 emit OperatorDelegatorRemoved(_operatorDelegatorToRemove);

240:         emit CollateralTokenAdded(_newCollateralToken);

253:                 emit CollateralTokenRemoved(_collateralTokenToRemove);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L151-L151) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L174-L174), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L240-L240), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L253-L253)


```solidity

File: contracts/Deposits/DepositQueue.sol

275:             emit RewardsDeposited(IERC20(address(token)), balance - feeAmount);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L275-L275) 


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

269:         emit Deposit(msg.sender, _amountIn, xezETHAmount);

405:         emit SweeperBridgeFeeCollected(msg.sender, feeCollected);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L269-L269) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L405-L405)


```solidity

File: contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol

80:         emit MessageReceived(_transferId, _origin, _originSender, _price, _timestamp);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L80-L80) 


```solidity

File: contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol

78:         emit MessageReceived(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L78-L78) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol

151:         emit Deposit(_to, _amount);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L151-L151) 


</details>


### [NC&#x2011;21] Explicitly define visibility of state variables to prevent misconceptions on what can access the variable 
Such state variables should be marked as private as this is the default visibility


*There are 6 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/RestakeManager.sol

38:     uint256 constant BASIS_POINTS = 100;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L38-L38) 


```solidity

File: contracts/Oracle/RenzoOracle.sol

20:     string constant INVALID_0_INPUT = "Invalid 0 input";

23:     uint256 constant SCALE_FACTOR = 10 ** 18;

26:     uint256 constant MAX_TIME_WINDOW = 86400 + 60; // 24 hours + 60 seconds


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L20-L20) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L23-L23), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L26-L26)


```solidity

File: contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol

31:     address immutable blastStandardBridge;

32:     address immutable registry;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L31-L31) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L32-L32)


</details>


### [NC&#x2011;22] Defining All External/Public Functions in Contract Interfaces 
It is preferable to have all the external and public function in an interface to make using them easier by developers. This helps ensure the whole API is extracted in a interface.


*There are 69 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/token/EzEthToken.sol

51:     function setPaused(bool _paused) external onlyTokenAdmin {
52:         paused = _paused;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L51-L52) 


```solidity

File: contracts/Withdraw/WithdrawQueue.sol

106:     function updateWithdrawBufferTarget(
107:         TokenWithdrawBuffer[] calldata _newBufferTarget
108:     ) external onlyWithdrawQueueAdmin {

129:     function updateCoolDownPeriod(uint256 _newCoolDownPeriod) external onlyWithdrawQueueAdmin {
130:         if (_newCoolDownPeriod == 0) revert InvalidZeroInput();

270:     function getOutstandingWithdrawRequests(address user) public view returns (uint256) {
271:         return withdrawRequests[user].length;

279:     function claim(uint256 withdrawRequestIndex) external nonReentrant {
280:         // check if provided withdrawRequest Index is valid


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L106-L108) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L129-L130), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L270-L271), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L279-L280)


```solidity

File: contracts/TimelockController.sol

154:     function isOperation(bytes32 id) public view virtual returns (bool) {
155:         return getTimestamp(id) > 0;

161:     function isOperationPending(bytes32 id) public view virtual returns (bool) {
162:         return getTimestamp(id) > _DONE_TIMESTAMP;

168:     function isOperationReady(bytes32 id) public view virtual returns (bool) {
169:         uint256 timestamp = getTimestamp(id);

176:     function isOperationDone(bytes32 id) public view virtual returns (bool) {
177:         return getTimestamp(id) == _DONE_TIMESTAMP;

184:     function getTimestamp(bytes32 id) public view virtual returns (uint256) {
185:         return _timestamps[id];

193:     function getMinDelay() public view virtual returns (uint256) {
194:         return _minDelay;

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

296:     function cancel(bytes32 id) public virtual onlyRole(CANCELLER_ROLE) {
297:         require(isOperationPending(id), "TimelockController: operation cannot be cancelled");

342:     function executeBatch(
343:         address[] calldata targets,
344:         uint256[] calldata values,
345:         bytes[] calldata payloads,
346:         bytes32 predecessor,
347:         bytes32 salt
348:     ) public payable virtual onlyRoleOrOpenRole(EXECUTOR_ROLE) {

402:     function updateDelay(uint256 newDelay) external virtual {
403:         require(msg.sender == address(this), "TimelockController: caller must be timelock");


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L154-L155) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L161-L162), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L168-L169), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L176-L177), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L184-L185), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L193-L194), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L201-L207), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L215-L221), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L234-L241), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L259-L266), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L296-L297), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L342-L348), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L402-L403)


```solidity

File: contracts/Rewards/RewardHandler.sol

58:     function forwardRewards() external nonReentrant onlyNativeEthRestakeAdmin {
59:         _forwardETH();

72:     function setRewardDestination(
73:         address _rewardDestination
74:     ) external nonReentrant onlyRestakeManagerAdmin {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L58-L59) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L72-L74)


```solidity

File: contracts/RestakeManager.sol

121:     function setPaused(bool _paused) external onlyDepositWithdrawPauserAdmin {
122:         paused = _paused;

126:     function getOperatorDelegatorsLength() external view returns (uint256) {
127:         return operatorDelegators.length;

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

215:     function setMaxDepositTVL(uint256 _maxDepositTVL) external onlyRestakeManagerAdmin {
216:         maxDepositTVL = _maxDepositTVL;

220:     function addCollateralToken(IERC20 _newCollateralToken) external onlyRestakeManagerAdmin {
221:         // Ensure it is not already in the list

244:     function removeCollateralToken(
245:         IERC20 _collateralTokenToRemove
246:     ) external onlyRestakeManagerAdmin {

266:     function getCollateralTokensLength() external view returns (uint256) {
267:         return collateralTokens.length;

362:     function chooseOperatorDelegatorForDeposit(
363:         uint256[] memory tvls,
364:         uint256 totalTVL
365:     ) public view returns (IOperatorDelegator) {

400:     function chooseOperatorDelegatorForWithdraw(
401:         uint256 tokenIndex,
402:         uint256 ezETHValue,
403:         uint256[][] memory operatorDelegatorTokenTVLs,
404:         uint256[] memory operatorDelegatorTVLs,
405:         uint256 totalTVL
406:     ) public view returns (IOperatorDelegator) {

451:     function getCollateralTokenIndex(IERC20 _collateralToken) public view returns (uint256) {
452:         // Find the token index

675:     function getTotalRewardsEarned() external view returns (uint256) {
676:         uint256 totalRewards = 0;

709:     function setTokenTvlLimit(IERC20 _token, uint256 _limit) external onlyRestakeManagerAdmin {
710:         // Verify collateral token is in the list - call will revert if not found


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L121-L122) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L126-L127), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L131-L134), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L160-L162), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L187-L190), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L215-L216), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L220-L221), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L244-L246), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L266-L267), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L362-L365), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L400-L406), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L451-L452), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L675-L676), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L709-L710)


```solidity

File: contracts/Oracle/RenzoOracle.sol

54:     function setOracleAddress(
55:         IERC20 _token,
56:         AggregatorV3Interface _oracleAddress
57:     ) external nonReentrant onlyOracleAdmin {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L54-L57) 


```solidity

File: contracts/Deposits/DepositQueue.sol

87:     function setWithdrawQueue(IWithdrawQueue _withdrawQueue) external onlyRestakeManagerAdmin {
88:         if (address(_withdrawQueue) == address(0)) revert InvalidZeroInput();

93:     function setFeeConfig(
94:         address _feeAddress,
95:         uint256 _feeBasisPoints
96:     ) external onlyRestakeManagerAdmin {

112:     function setRestakeManager(IRestakeManager _restakeManager) external onlyRestakeManagerAdmin {
113:         if (address(_restakeManager) == address(0x0)) revert InvalidZeroInput();

187:     function stakeEthFromQueue(
188:         IOperatorDelegator operatorDelegator,
189:         bytes calldata pubkey,
190:         bytes calldata signature,
191:         bytes32 depositDataRoot
192:     ) external onlyNativeEthRestakeAdmin {

211:     function stakeEthFromQueueMulti(
212:         IOperatorDelegator[] calldata operatorDelegators,
213:         bytes[] calldata pubkeys,
214:         bytes[] calldata signatures,
215:         bytes32[] calldata depositDataRoots
216:     ) external onlyNativeEthRestakeAdmin nonReentrant {

254:     function sweepERC20(IERC20 token) external onlyERC20RewardsAdmin {
255:         uint256 balance = IERC20(token).balanceOf(address(this));


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L87-L88) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L93-L96), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L112-L113), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L187-L192), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L211-L216), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L254-L255)


```solidity

File: contracts/Delegation/OperatorDelegator.sol

106:     function setTokenStrategy(
107:         IERC20 _token,
108:         IStrategy _strategy
109:     ) external nonReentrant onlyOperatorDelegatorAdmin {

117:     function setDelegateAddress(
118:         address _delegateAddress,
119:         ISignatureUtils.SignatureWithExpiry memory approverSignatureAndExpiry,
120:         bytes32 approverSalt
121:     ) external nonReentrant onlyOperatorDelegatorAdmin {

132:     function setBaseGasAmountSpent(
133:         uint256 _baseGasAmountSpent
134:     ) external nonReentrant onlyOperatorDelegatorAdmin {

172:     function getStrategyIndex(IStrategy _strategy) public view returns (uint256) {
173:         // Get the length of the strategy list for this contract

459:     function startDelayedWithdrawUnstakedETH() external onlyNativeEthRestakeAdmin {
460:         // Call the start delayed withdraw function in the EigenPodManager


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L106-L109) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L117-L121), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L132-L134), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L172-L173), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L459-L460)


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol

37:     function deployOptimismMintableXERC20(
38:         string memory _name,
39:         string memory _symbol,
40:         uint256[] memory _minterLimits,
41:         uint256[] memory _burnerLimits,
42:         address[] memory _bridges,
43:         address _proxyAdmin,
44:         address _l1Token
45:     ) public returns (address _xerc20) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L37-L45) 


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

277:     function getBridgeFeeShare(uint256 _amountIn) public view returns (uint256) {
278:         // deduct bridge Fee share

320:     function updatePriceByOwner(uint256 price) external onlyOwner {
321:         return _updatePrice(price, block.timestamp);

466:     function setAllowedBridgeSweeper(address _sweeper, bool _allowed) external onlyOwner {
467:         allowedBridgeSweepers[_sweeper] = _allowed;

478:     function recoverNative(uint256 _amount, address _to) external onlyOwner {
479:         payable(_to).transfer(_amount);

489:     function recoverERC20(address _token, uint256 _amount, address _to) external onlyOwner {
490:         IERC20(_token).safeTransfer(_to, _amount);

501:     function setOraclePriceFeed(IRenzoOracleL2 _oracle) external onlyOwner {
502:         emit OraclePriceFeedUpdated(address(_oracle), address(oracle));

511:     function setReceiverPriceFeed(address _receiver) external onlyOwner {
512:         emit ReceiverPriceFeedUpdated(_receiver, receiver);

521:     function updateBridgeFeeShare(uint256 _newShare) external onlyOwner {
522:         if (_newShare > 100) revert InvalidBridgeFeeShare(_newShare);

532:     function updateSweepBatchSize(uint256 _newBatchSize) external onlyOwner {
533:         if (_newBatchSize < 32 ether) revert InvalidSweepBatchSize(_newBatchSize);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L277-L278) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L320-L321), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L466-L467), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L478-L479), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L489-L490), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L501-L502), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L511-L512), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L521-L522), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L532-L533)


```solidity

File: contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol

92:     function updateXRenzoBridgeL1(address _newXRenzoBridgeL1) external onlyOwner {
93:         if (_newXRenzoBridgeL1 == address(0)) revert InvalidZeroInput();

103:     function updateCCIPEthChainSelector(uint32 _newChainDomain) external onlyOwner {
104:         if (_newChainDomain == 0) revert InvalidZeroInput();

113:     function unPause() external onlyOwner {
114:         _unpause();

130:     function setRenzoDeposit(address _newXRenzoDeposit) external onlyOwner {
131:         if (_newXRenzoDeposit == address(0)) revert InvalidZeroInput();


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L92-L93) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L103-L104), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L113-L114), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L130-L131)


```solidity

File: contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol

96:     function updateXRenzoBridgeL1(address _newXRenzoBridgeL1) external onlyOwner {
97:         if (_newXRenzoBridgeL1 == address(0)) revert InvalidZeroInput();

107:     function updateCCIPEthChainSelector(uint64 _newChainSelector) external onlyOwner {
108:         if (_newChainSelector == 0) revert InvalidZeroInput();

117:     function unPause() external onlyOwner {
118:         _unpause();

134:     function setRenzoDeposit(address _newXRenzoDeposit) external onlyOwner {
135:         if (_newXRenzoDeposit == address(0)) revert InvalidZeroInput();


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L96-L97) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L107-L108), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L117-L118), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L134-L135)


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2.sol

36:     function setOracleAddress(AggregatorV3Interface _oracleAddress) external onlyOwner {
37:         if (address(_oracleAddress) == address(0)) revert InvalidZeroInput();


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L36-L37) 


```solidity

File: contracts/Bridge/L1/xRenzoBridge.sol

294:     function recoverNative(uint256 _amount, address _to) external onlyBridgeAdmin {
295:         payable(_to).transfer(_amount);

305:     function recoverERC20(address _token, uint256 _amount, address _to) external onlyBridgeAdmin {
306:         IERC20(_token).safeTransfer(_to, _amount);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L294-L295) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L305-L306)


```solidity

File: contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol

56:     function bridgeTo(
57:         address _to,
58:         address _erc20,
59:         address _remoteToken,
60:         uint256 _amount,
61:         uint32 _minGasLimit,
62:         bytes calldata _extraData
63:     ) external {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L56-L63) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol

54:     function depositNative() public payable {
55:         if (!IS_NATIVE) revert IXERC20Lockbox_NotNative();


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L54-L55) 


</details>


### [NC&#x2011;23] Fixed Compiler Version Required for Non-Library/Interface Files 



*There are 8 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/token/EzEthToken.sol

//@audit `EzEthToken` 
2: pragma solidity ^0.8.9;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L2-L2) 


```solidity

File: contracts/TimelockController.sol

//@audit `TimelockController` 
4: pragma solidity ^0.8.0;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L4-L4) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20.sol

//@audit `XERC20` 
2: pragma solidity >=0.8.4 <0.9.0;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L2-L2) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Factory.sol

//@audit `XERC20Factory` 
2: pragma solidity >=0.8.4 <0.9.0;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L2-L2) 


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol

//@audit `OptimismMintableXERC20` 
2: pragma solidity >=0.8.4 <0.9.0;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L2-L2) 


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol

//@audit `OptimismMintableXERC20Factory` 
2: pragma solidity >=0.8.4 <0.9.0;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L2-L2) 


```solidity

File: contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol

//@audit `LockboxAdapterBlast` 
2: pragma solidity ^0.8.13;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L2-L2) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol

//@audit `XERC20Lockbox` 
2: pragma solidity >=0.8.4 <0.9.0;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L2-L2) 


</details>


### [NC&#x2011;24] Floating pragma should be avoided 
If you leave a floating pragma in your code (pragma solidity 0.4>=0.6. 0. ), you won't know which version was deployed to compile your code, leading to unexpected behavior


*There are 8 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/token/EzEthToken.sol

2: pragma solidity ^0.8.9;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L2-L2) 


```solidity

File: contracts/TimelockController.sol

4: pragma solidity ^0.8.0;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L4-L4) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20.sol

2: pragma solidity >=0.8.4 <0.9.0;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L2-L2) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Factory.sol

2: pragma solidity >=0.8.4 <0.9.0;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L2-L2) 


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol

2: pragma solidity >=0.8.4 <0.9.0;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L2-L2) 


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol

2: pragma solidity >=0.8.4 <0.9.0;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L2-L2) 


```solidity

File: contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol

2: pragma solidity ^0.8.13;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L2-L2) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol

2: pragma solidity >=0.8.4 <0.9.0;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L2-L2) 


</details>


### [NC&#x2011;25] Function ordering does not follow the Solidity style guide 
According to the [Solidity style guide](https://docs.soliditylang.org/en/v0.8.17/style-guide.html#order-of-functions), functions should be laid out in the following order :`constructor()`, `receive()`, `fallback()`, `external`, `public`, `internal`, `private`, but the cases below do not follow this pattern


*There are 19 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/token/EzEthToken.sol

41:     function mint(address to, uint256 amount) external onlyMinterBurner {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L41-L41) 


```solidity

File: contracts/Withdraw/WithdrawQueue.sol

182:     function fillEthWithdrawBuffer() external payable nonReentrant onlyDepositQueue {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L182-L182) 


```solidity

File: contracts/TimelockController.sol

296:     function cancel(bytes32 id) public virtual onlyRole(CANCELLER_ROLE) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L296-L296) 


```solidity

File: contracts/Rewards/RewardHandler.sol

52:     receive() external payable nonReentrant {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L52-L52) 


```solidity

File: contracts/RestakeManager.sol

121:     function setPaused(bool _paused) external onlyDepositWithdrawPauserAdmin {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L121-L121) 


```solidity

File: contracts/RateProvider/BalancerRateProvider.sol

29:     function getRate() external view returns (uint256) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProvider.sol#L29-L29) 


```solidity

File: contracts/Permissions/RoleManager.sol

32:     function isRoleManagerAdmin(address potentialAddress) external view returns (bool) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L32-L32) 


```solidity

File: contracts/Oracle/RenzoOracle.sol

54:     function setOracleAddress(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L54-L54) 


```solidity

File: contracts/Oracle/Mantle/METHShim.sol

29:     function decimals() external pure returns (uint8) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L29-L29) 


```solidity

File: contracts/Oracle/Binance/WBETHShim.sol

29:     function decimals() external pure returns (uint8) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L29-L29) 


```solidity

File: contracts/Deposits/DepositQueue.sol

87:     function setWithdrawQueue(IWithdrawQueue _withdrawQueue) external onlyRestakeManagerAdmin {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L87-L87) 


```solidity

File: contracts/Delegation/OperatorDelegator.sol

172:     function getStrategyIndex(IStrategy _strategy) public view returns (uint256) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L172-L172) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20.sol

96:     function mint(address _user, uint256 _amount) public virtual {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L96-L96) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Factory.sol

74:     function deployXERC20(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L74-L74) 


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

168:     function depositETH(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L168-L168) 


```solidity

File: contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol

96:     function updateXRenzoBridgeL1(address _newXRenzoBridgeL1) external onlyOwner {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L96-L96) 


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2.sol

36:     function setOracleAddress(AggregatorV3Interface _oracleAddress) external onlyOwner {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L36-L36) 


```solidity

File: contracts/Bridge/L1/xRenzoBridge.sol

139:     function xReceive(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L139-L139) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol

66:     function deposit(uint256 _amount) external {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L66-L66) 


</details>


### [NC&#x2011;26] `address`s shouldn't be hard-coded 
It is often better to declare `address`es as `immutable`, and assign them via constructor arguments. This allows the code to remain the same across deployments on different networks, and avoids recompilation when addresses need to change.


*There are 3 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Withdraw/WithdrawQueueStorage.sol

//@audit hardcoded address : 0xEeeeeEeeeEeEeeEeEeEeeEEEeeeeEeeeeeeeEEeE
10:     address public constant IS_NATIVE = 0xEeeeeEeeeEeEeeEeEeEeeEEEeeeeEeeeeeeeEEeE;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueueStorage.sol#L10-L10) 


```solidity

File: contracts/Deposits/DepositQueue.sol

//@audit hardcoded address : 0xEeeeeEeeeEeEeeEeEeEeeEEEeeeeEeeeeeeeEEeE
13:     address public constant IS_NATIVE = 0xEeeeeEeeeEeEeeEeEeEeeEEEeeeeEeeeeeeeEEeE;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L13-L13) 


```solidity

File: contracts/Delegation/OperatorDelegator.sol

//@audit hardcoded address : 0xEeeeeEeeeEeEeeEeEeEeeEEEeeeeEeeeeeeeEEeE
26:     address public constant IS_NATIVE = 0xEeeeeEeeeEeEeeEeEeEeeEEEeeeeEeeeeeeeEEeE;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L26-L26) 


</details>


### [NC&#x2011;27] Array indicies should be referenced via `enum`s rather than via numeric literals 
Consider using an enum instead of hardcoding an index access to make the code easier to understand.


*There are 15 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/RestakeManager.sol

//@audit `operatorDelegators`
392:         return operatorDelegators[0];

//@audit `operatorDelegators`
371:             return operatorDelegators[0];

//@audit `operatorDelegators`
413:             return operatorDelegators[0];

//@audit `operatorDelegatorTokenTVLs`
410:             if (operatorDelegatorTokenTVLs[0][tokenIndex] < ezETHValue) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L392-L392) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L371-L371), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L413-L413), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L410-L410)


```solidity

File: contracts/Delegation/OperatorDelegator.sol

//@audit `queuedWithdrawalParams`
203:         queuedWithdrawalParams[0].strategies = new IStrategy[](tokens.length);

//@audit `queuedWithdrawalParams`
204:         queuedWithdrawalParams[0].shares = new uint256[](tokens.length);

//@audit `queuedWithdrawalParams`
248:             queuedWithdrawalParams[0].strategies,

//@audit `queuedWithdrawalParams`
249:             queuedWithdrawalParams[0].shares

//@audit `queuedWithdrawalParams`
229:             queuedWithdrawalParams[0].withdrawer = address(this);

//@audit `queuedWithdrawalParams`
232:             queuedShares[address(tokens[i])] += queuedWithdrawalParams[0].shares[i];

//@audit `queuedWithdrawalParams`
221:                 queuedWithdrawalParams[0].strategies[i] = tokenStrategyMapping[tokens[i]];

//@audit `queuedWithdrawalParams`
224:                 queuedWithdrawalParams[0].shares[i] = tokenStrategyMapping[tokens[i]]

//@audit `queuedWithdrawalParams`
212:                 queuedWithdrawalParams[0].strategies[i] = eigenPodManager.beaconChainETHStrategy();

//@audit `queuedWithdrawalParams`
215:                 queuedWithdrawalParams[0].shares[i] = tokenAmounts[i];


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L203-L203) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L204-L204), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L248-L248), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L249-L249), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L229-L229), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L232-L232), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L221-L221), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L224-L224), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L212-L212), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L215-L215)


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol

//@audit `_bridges`
94:             (_name, _symbol, address(this), _l1Token, _bridges[0])


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L94-L94) 


</details>


### [NC&#x2011;28] Hardcoded string that is repeatedly used can be replaced with a constant 
For better maintainability, please consider creating and using a constant for those strings instead of hardcoding 


*There are 2 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/TimelockController.sol

//@audit `TimelockController: length mismatch` is used multiple time consider using a constant for it.
267:         require(targets.length == values.length, "TimelockController: length mismatch");

//@audit `TimelockController: operation is not ready` is used multiple time consider using a constant for it.
377:         require(isOperationReady(id), "TimelockController: operation is not ready");


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L267-L267) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L377-L377)


</details>


### [NC&#x2011;29] Duplicated `require()` checks should be refactored to a modifier or function 
The compiler will inline the function, which will avoid `JUMP` instructions usually associated with functions


*There are 3 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/TimelockController.sol

267:         require(targets.length == values.length, "TimelockController: length mismatch");

268:         require(targets.length == payloads.length, "TimelockController: length mismatch");

377:         require(isOperationReady(id), "TimelockController: operation is not ready");


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L267-L267) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L268-L268), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L377-L377)


</details>


### [NC&#x2011;30] Some if-statement can be converted to a ternary 
Improving code readability and compactness is an integral part of optimal programming practices. The use of ternary operators in place of if-else conditions is one such measure. Ternary operators allow us to write conditional statements in a more concise manner, thereby enhancing readability and simplicity. They follow the syntax `condition ? exprIfTrue : exprIfFalse`, which interprets as "if the condition is true, evaluate to `exprIfTrue`, else evaluate to `exprIfFalse`". By adopting this approach, we make our code more streamlined and intuitive, which could potentially aid in better understanding and maintenance of the codebase.


*There are 3 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Withdraw/WithdrawQueue.sol

157:         if (_asset != IS_NATIVE) {
158:             return IERC20(_asset).balanceOf(address(this)) - claimReserve[_asset];
159:         } else {
160:             return address(this).balance - claimReserve[_asset];
161:         }

302:         if (_withdrawRequest.collateralToken == IS_NATIVE) {
303:             payable(msg.sender).transfer(_withdrawRequest.amountToRedeem);
304:         } else {
305:             IERC20(_withdrawRequest.collateralToken).transfer(
306:                 msg.sender,
307:                 _withdrawRequest.amountToRedeem
308:             );
309:         }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L157-L161) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L302-L309)


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

279:         if (_amountIn < sweepBatchSize) {
280:             return (_amountIn * bridgeFeeShare) / FEE_BASIS;
281:         } else {
282:             return (sweepBatchSize * bridgeFeeShare) / FEE_BASIS;
283:         }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L279-L283) 


</details>


### [NC&#x2011;31] Imports could be organized more systematically 
The contract used interfaces should be imported first, followed by all other files. The examples below do not follow this layout.


*There are 16 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/token/EzEthToken.sol

6: import "./IEzEthToken.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L6-L6) 


```solidity

File: contracts/Withdraw/WithdrawQueue.sol

9: import "@openzeppelin/contracts/token/ERC20/IERC20.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L9-L9) 


```solidity

File: contracts/TimelockController.sol

7: import "@openzeppelin/contracts/token/ERC721/IERC721Receiver.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L7-L7) 


```solidity

File: contracts/RestakeManager.sol

8: import "@openzeppelin/contracts-upgradeable/token/ERC20/IERC20Upgradeable.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L8-L8) 


```solidity

File: contracts/RateProvider/BalancerRateProvider.sol

5: import "./IRateProvider.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProvider.sol#L5-L5) 


```solidity

File: contracts/Permissions/RoleManager.sol

5: import "./IRoleManager.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L5-L5) 


```solidity

File: contracts/Oracle/RenzoOracle.sol

5: import "../Permissions/IRoleManager.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L5-L5) 


```solidity

File: contracts/Delegation/OperatorDelegator.sol

6: import "../Permissions/IRoleManager.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L6-L6) 


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol

8: import { IOptimismMintableERC20 } from "../../interfaces/IOptimismMintableERC20.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L8-L8) 


```solidity

File: contracts/Bridge/L2/xRenzoDepositStorage.sol

6: import "../Connext/core/IConnext.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L6-L6) 


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

9: import {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L9-L9) 


```solidity

File: contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol

7: import { IxRenzoDeposit } from "../IxRenzoDeposit.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L7-L7) 


```solidity

File: contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol

10: import { IxRenzoDeposit } from "../IxRenzoDeposit.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L10-L10) 


```solidity

File: contracts/Bridge/L1/xRenzoBridgeStorage.sol

6: import "../../IRestakeManager.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridgeStorage.sol#L6-L6) 


```solidity

File: contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol

5: import { IERC20 } from "@openzeppelin/contracts/token/ERC20/IERC20.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L5-L5) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol

8: import { IXERC20Lockbox } from "../interfaces/IXERC20Lockbox.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L8-L8) 


</details>


### [NC&#x2011;32] Import declarations should import specific identifiers, rather than the whole file 
Using import declarations of the form `import {<identifier_name>} from "some/ file.sol"` avoids polluting the symbol namespace making flattened files smaller, and speeds up compilation


*There are 138 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/token/EzEthTokenStorage.sol

3: import "../Permissions/IRoleManager.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthTokenStorage.sol#L3-L3) 


```solidity

File: contracts/token/EzEthToken.sol

4: import "@openzeppelin/contracts-upgradeable/token/ERC20/ERC20Upgradeable.sol";

5: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

6: import "./IEzEthToken.sol";

7: import "../Permissions/IRoleManager.sol";

8: import "./EzEthTokenStorage.sol";

9: import "../Errors/Errors.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L4-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L5-L5), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L6-L6), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L7-L7), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L8-L8), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L9-L9)


```solidity

File: contracts/Withdraw/WithdrawQueue.sol

4: import "./WithdrawQueueStorage.sol";

5: import "../Errors/Errors.sol";

6: import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";

7: import "@openzeppelin/contracts-upgradeable/security/PausableUpgradeable.sol";

8: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";

9: import "@openzeppelin/contracts/token/ERC20/IERC20.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L4-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L5-L5), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L6-L6), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L7-L7), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L8-L8), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L9-L9)


```solidity

File: contracts/Withdraw/WithdrawQueueStorage.sol

4: import "../Permissions/IRoleManager.sol";

5: import "../Oracle/IRenzoOracle.sol";

6: import "../IRestakeManager.sol";

7: import "../token/IEzEthToken.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueueStorage.sol#L4-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueueStorage.sol#L5-L5), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueueStorage.sol#L6-L6), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueueStorage.sol#L7-L7)


```solidity

File: contracts/TimelockController.sol

6: import "@openzeppelin/contracts/access/AccessControl.sol";

7: import "@openzeppelin/contracts/token/ERC721/IERC721Receiver.sol";

8: import "@openzeppelin/contracts/token/ERC1155/IERC1155Receiver.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L6-L6) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L7-L7), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L8-L8)


```solidity

File: contracts/Rewards/RewardHandlerStorage.sol

4: import "../Permissions/IRoleManager.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandlerStorage.sol#L4-L4) 


```solidity

File: contracts/Rewards/RewardHandler.sol

4: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

5: import "./RewardHandlerStorage.sol";

6: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";

7: import "../Errors/Errors.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L4-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L5-L5), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L6-L6), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L7-L7)


```solidity

File: contracts/RestakeManagerStorage.sol

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

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManagerStorage.sol#L4-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManagerStorage.sol#L5-L5), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManagerStorage.sol#L6-L6), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManagerStorage.sol#L7-L7), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManagerStorage.sol#L8-L8), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManagerStorage.sol#L9-L9), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManagerStorage.sol#L10-L10), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManagerStorage.sol#L11-L11), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManagerStorage.sol#L12-L12), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManagerStorage.sol#L13-L13)


```solidity

File: contracts/RestakeManager.sol

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

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L4-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L5-L5), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L6-L6), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L7-L7), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L8-L8), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L9-L9), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L10-L10), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L11-L11), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L12-L12), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L13-L13), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L14-L14), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L15-L15), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L16-L16), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L17-L17)


```solidity

File: contracts/RateProvider/BalancerRateProvider.sol

4: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

5: import "./IRateProvider.sol";

6: import "../Errors/Errors.sol";

7: import "./BalancerRateProviderStorage.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProvider.sol#L4-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProvider.sol#L5-L5), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProvider.sol#L6-L6), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProvider.sol#L7-L7)


```solidity

File: contracts/RateProvider/BalancerRateProviderStorage.sol

4: import "@openzeppelin/contracts-upgradeable/token/ERC20/IERC20Upgradeable.sol";

5: import "../IRestakeManager.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProviderStorage.sol#L4-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProviderStorage.sol#L5-L5)


```solidity

File: contracts/Permissions/RoleManager.sol

4: import "@openzeppelin/contracts-upgradeable/access/AccessControlUpgradeable.sol";

5: import "./IRoleManager.sol";

6: import "./RoleManagerStorage.sol";

7: import "../Errors/Errors.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L4-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L5-L5), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L6-L6), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L7-L7)


```solidity

File: contracts/Oracle/RenzoOracle.sol

4: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";

5: import "../Permissions/IRoleManager.sol";

6: import "./RenzoOracleStorage.sol";

7: import "./IRenzoOracle.sol";

8: import "../Errors/Errors.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L4-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L5-L5), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L6-L6), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L7-L7), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L8-L8)


```solidity

File: contracts/Oracle/RenzoOracleStorage.sol

4: import "../Permissions/IRoleManager.sol";

5: import "@chainlink/contracts/src/v0.8/interfaces/AggregatorV3Interface.sol";

6: import "@openzeppelin/contracts/token/ERC20/IERC20.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracleStorage.sol#L4-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracleStorage.sol#L5-L5), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracleStorage.sol#L6-L6)


```solidity

File: contracts/Oracle/Mantle/METHShim.sol

4: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";

5: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

6: import "./METHShimStorage.sol";

7: import "../../Errors/Errors.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L4-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L5-L5), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L6-L6), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L7-L7)


```solidity

File: contracts/Oracle/Mantle/METHShimStorage.sol

4: import "@chainlink/contracts/src/v0.8/interfaces/AggregatorV3Interface.sol";

5: import "./IMethStaking.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShimStorage.sol#L4-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShimStorage.sol#L5-L5)


```solidity

File: contracts/Oracle/Binance/WBETHShimStorage.sol

4: import "@chainlink/contracts/src/v0.8/interfaces/AggregatorV3Interface.sol";

5: import "./IStakedTokenV2.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShimStorage.sol#L4-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShimStorage.sol#L5-L5)


```solidity

File: contracts/Oracle/Binance/WBETHShim.sol

4: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";

5: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

6: import "./WBETHShimStorage.sol";

7: import "../../Errors/Errors.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L4-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L5-L5), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L6-L6), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L7-L7)


```solidity

File: contracts/Deposits/DepositQueueStorage.sol

4: import "../Permissions/IRoleManager.sol";

5: import "../Withdraw/IWithdrawQueue.sol";

6: import "../IRestakeManager.sol";

7: import "./IDepositQueue.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueueStorage.sol#L4-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueueStorage.sol#L5-L5), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueueStorage.sol#L6-L6), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueueStorage.sol#L7-L7)


```solidity

File: contracts/Deposits/DepositQueue.sol

4: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

5: import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";

6: import "./DepositQueueStorage.sol";

7: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";

8: import "../Errors/Errors.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L4-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L5-L5), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L6-L6), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L7-L7), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L8-L8)


```solidity

File: contracts/Delegation/OperatorDelegator.sol

4: import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";

5: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";

6: import "../Permissions/IRoleManager.sol";

7: import "./OperatorDelegatorStorage.sol";

8: import "../EigenLayer/interfaces/IDelegationManager.sol";

9: import "../EigenLayer/interfaces/ISignatureUtils.sol";

10: import "../Errors/Errors.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L4-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L5-L5), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L6-L6), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L7-L7), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L8-L8), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L9-L9), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L10-L10)


```solidity

File: contracts/Delegation/OperatorDelegatorStorage.sol

3: import "../Permissions/IRoleManager.sol";

4: import "../EigenLayer/interfaces/IStrategy.sol";

5: import "../EigenLayer/interfaces/IStrategyManager.sol";

6: import "../EigenLayer/interfaces/IDelegationManager.sol";

7: import "../EigenLayer/interfaces/IEigenPod.sol";

8: import "./IOperatorDelegator.sol";

9: import "../IRestakeManager.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegatorStorage.sol#L3-L3) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegatorStorage.sol#L4-L4), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegatorStorage.sol#L5-L5), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegatorStorage.sol#L6-L6), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegatorStorage.sol#L7-L7), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegatorStorage.sol#L8-L8), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegatorStorage.sol#L9-L9)


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20.sol

14: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L14-L14) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Factory.sol

11: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

12: import "@openzeppelin/contracts/proxy/transparent/TransparentUpgradeableProxy.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L11-L11) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L12-L12)


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol

11: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

12: import "@openzeppelin/contracts/proxy/transparent/TransparentUpgradeableProxy.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L11-L11) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L12-L12)


```solidity

File: contracts/Bridge/L2/xRenzoDepositStorage.sol

4: import "./IxRenzoDeposit.sol";

5: import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";

6: import "../Connext/core/IConnext.sol";

7: import "./Oracle/IRenzoOracleL2.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L4-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L5-L5), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L6-L6), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L7-L7)


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

4: import "./xRenzoDepositStorage.sol";

5: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

12: import "../../Errors/Errors.sol";

13: import "../xERC20/interfaces/IXERC20.sol";

14: import "../Connext/core/IWeth.sol";

15: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";

16: import "../../RateProvider/IRateProvider.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L4-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L5-L5), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L12-L12), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L13-L13), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L14-L14), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L15-L15), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L16-L16)


```solidity

File: contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol

8: import "../../../Errors/Errors.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L8-L8) 


```solidity

File: contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol

11: import "../../../Errors/Errors.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L11-L11) 


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2.sol

4: import "./RenzoOracleL2Storage.sol";

5: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

9: import "../../../Errors/Errors.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L4-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L5-L5), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L9-L9)


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2Storage.sol

4: import "./IRenzoOracleL2.sol";

5: import "@chainlink/contracts/src/v0.8/interfaces/AggregatorV3Interface.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2Storage.sol#L4-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2Storage.sol#L5-L5)


```solidity

File: contracts/Bridge/L1/xRenzoBridge.sol

4: import "./xRenzoBridgeStorage.sol";

5: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

6: import "../../Errors/Errors.sol";

10: import "../Connext/core/IXReceiver.sol";

11: import "../Connext/core/IWeth.sol";

12: import "../xERC20/interfaces/IXERC20.sol";

14: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L4-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L5-L5), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L6-L6), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L10-L10), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L11-L11), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L12-L12), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L14-L14)


```solidity

File: contracts/Bridge/L1/xRenzoBridgeStorage.sol

4: import "./IxRenzoBridge.sol";

5: import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";

6: import "../../IRestakeManager.sol";

7: import "../xERC20/interfaces/IXERC20Lockbox.sol";

8: import "../Connext/core/IConnext.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridgeStorage.sol#L4-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridgeStorage.sol#L5-L5), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridgeStorage.sol#L6-L6), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridgeStorage.sol#L7-L7), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridgeStorage.sol#L8-L8)


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol

9: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L9-L9) 


</details>


### [NC&#x2011;33] Inconsistent spacing in comments 
Some lines use `// x` and some use `//x`. The instances below point out the usages that don't follow the majority, within each file


*There are 1 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Bridge/L2/xRenzoDeposit.sol

154:         //set sweep batch size to 32 ETH


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L154-L154) 


</details>


### [NC&#x2011;34] Inconsistent usage of `require`/`error` 
Some parts of the codebase use `require` statements, while others use custom `error`s. Consider refactoring the code to use the same approach: the following findings represent the minority of `require` vs `error`, and they show the first occurance in each file, for brevity.


*There are 12 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/TimelockController.sol

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

388:         require(isOperationReady(id), "TimelockController: operation is not ready");

403:         require(msg.sender == address(this), "TimelockController: caller must be timelock");


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L267-L267) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L268-L268), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L284-L284), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L285-L285), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L297-L297), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L349-L349), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L350-L350), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L370-L370), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L377-L377), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L378-L378), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L388-L388), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L403-L403)


</details>


### [NC&#x2011;35] Inconsistent method of specifying a floating pragma 
Some files use `>=`, some use `^` and some use `>`. The instances below are examples of the method that has the fewest instances for a specific version. Note that using `>=` without also specifying `<=` will lead to failures to compile, or external project incompatability, when the major version changes and there are breaking-changes, so `^` should be preferred regardless of the instance counts\nthe following instances represents the less used technique


*There are 5 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Bridge/xERC20/contracts/XERC20.sol

2: pragma solidity >=0.8.4 <0.9.0;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L2-L2) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Factory.sol

2: pragma solidity >=0.8.4 <0.9.0;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L2-L2) 


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol

2: pragma solidity >=0.8.4 <0.9.0;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L2-L2) 


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol

2: pragma solidity >=0.8.4 <0.9.0;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L2-L2) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol

2: pragma solidity >=0.8.4 <0.9.0;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L2-L2) 


</details>


### [NC&#x2011;36] Incorrect NatSpec Syntax 
In Solidity, just like in most other programming languages, regular comments serve to make code more understandable for developers. These are usually denoted by `//` for single line comments, or `/* ... */` for multi-line comments, and are ignored by the compiler.
On the other hand, NatSpec comments in Solidity, denoted by `///` for single - line comments, or`/** ... */` for multi - line comments, serve a different purpose.Besides aiding developer comprehension, they also form a part of the contract's interface, as they can be parsed and used by tools such as automated documentation generators or IDEs to provide users with details about the contract's functions, parameters and behavior.NatSpec comments can also be retrieved via JSON interfaces, and as such, they're included in the contract's ABI.
Thus, using`///` and `/** ... */` appropriately ensures not only proper documentation for developers, but also helps create a richer and more informative interface for users and external tools interacting with your contract.


*There are 1 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Oracle/RenzoOracle.sol

100:     // @dev Given list of tokens and balances, return total value (assumes all lookups are denomintated in same underlying currency)


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L100-L100) 


</details>


### [NC&#x2011;37] Interfaces should be indicated with an `I` prefix in the contract name 



*There are 1 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol

17: interface L1StandardBridge {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L17-L17) 


</details>


### [NC&#x2011;38] Interfaces should be defined in separate files from their usage 
The interfaces below should be defined in separate files, so that it's easier for future projects to import them, and to avoid duplication later on if they need to be used elsewhere in the project


*There are 2 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol

//@audit the interface `IXERC20Registry` is declared in this file and used in it here:
69:         address xerc20 = IXERC20Registry(registry).getXERC20(_erc20);

//@audit the interface `L1StandardBridge` is declared in this file and used in it here:
87:         L1StandardBridge(blastStandardBridge).bridgeERC20To(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L69-L69) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L87-L87)


</details>


### [NC&#x2011;39] Large numeric literals should use underscores for readability 



*There are 6 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Oracle/RenzoOracle.sol

26:     uint256 constant MAX_TIME_WINDOW = 86400 + 60; // 24 hours + 60 seconds


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L26-L26) 


```solidity

File: contracts/Deposits/DepositQueue.sol

103:         if (_feeBasisPoints > 10000) revert OverMaxBasisPoints();

167:             feeAmount = (msg.value * feeBasisPoints) / 10000;

261:                 feeAmount = (balance * feeBasisPoints) / 10000;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L103-L103) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L167-L167), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L261-L261)


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

40:     uint32 public constant FEE_BASIS = 10000;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L40-L40) 


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2.sol

13:     uint256 public constant MAX_TIME_WINDOW = 86400 + 60; // 24 hours + 60 seconds


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L13-L13) 


</details>


### [NC&#x2011;40] Long functions should be refactored into multiple, smaller, functions 



*There are 13 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Withdraw/WithdrawQueue.sol

206:     function withdraw(uint256 _amount, address _assetOut) external nonReentrant {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L206-L206) 


```solidity

File: contracts/RestakeManager.sol

274:     function calculateTVLs() public view returns (uint256[][] memory, uint256[] memory, uint256) {

400:     function chooseOperatorDelegatorForWithdraw(

473:     function deposit(IERC20 _collateralToken, uint256 _amount) external {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L274-L274) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L400-L400), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L473-L473)


```solidity

File: contracts/Delegation/OperatorDelegator.sol

193:     function queueWithdrawals(

265:     function completeQueuedWithdrawal(

481:     function _refundGas() internal returns (uint256) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L193-L193) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L265-L265), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L481-L481)


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Factory.sol

135:     function _deployXERC20(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L135-L135) 


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

75:     function initialize(

227:     function _deposit(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L75-L75) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L227-L227)


```solidity

File: contracts/Bridge/L1/xRenzoBridge.sol

70:     function initialize(

139:     function xReceive(

210:     function sendPrice(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L70-L70) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L139-L139), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L210-L210)


</details>


### [NC&#x2011;41] Long lines of code 
Usually lines in source code are limited to [80](https://softwareengineering.stackexchange.com/questions/148677/why-is-80-characters-the-standard-limit-for-code-width) characters. Today's screens are much larger so it's reasonable to stretch this in some cases. The solidity style guide recommends a maximumum line length of [120 characters](https://docs.soliditylang.org/en/v0.8.17/style-guide.html#maximum-line-length), so the lines below should be split when they reach that length.


*There are 28 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/RestakeManager.sol

270:     /// @dev This function calculates the TVLs for each operator delegator by individual token, total for each OD, and total for the protocol.


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L270-L270) 


```solidity

File: contracts/Oracle/RenzoOracle.sol

100:     // @dev Given list of tokens and balances, return total value (assumes all lookups are denomintated in same underlying currency)

121:     /// @dev Given amount of current protocol value, new value being added, and supply of ezETH, determine amount to mint

151:     // Given the amount of ezETH to burn, the supply of ezETH, and the total value in the protocol, determine amount of value to return to user


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L100-L100) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L121-L121), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L151-L151)


```solidity

File: contracts/Oracle/Mantle/METHShim.sol

11:  * @dev     The contract hard codes the decimals to 18 decimals and returns the conversion rate of 1 mETH to ETH underlying the token in the mETH protocol

12:  * @notice  This contract is a shim that implements the Chainlink AggregatorV3Interface and returns pricing from the mETH staking contract


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L11-L11) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L12-L12)


```solidity

File: contracts/Oracle/Binance/WBETHShim.sol

11:  * @dev     The contract hard codes the decimals to 18 decimals and returns the conversion rate of 1 mETH to ETH underlying the token in the wBETH protocol

12:  * @notice  This contract is a shim that implements the Chainlink AggregatorV3Interface and returns pricing from the wBETH token contract


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L11-L11) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L12-L12)


```solidity

File: contracts/Delegation/OperatorDelegator.sol

105:     /// @dev Sets the strategy for a given token - setting strategy to 0x0 removes the ability to deposit and withdraw token

140:     /// @dev Deposit tokens into the EigenLayer.  This call assumes any balance of tokens in this contract will be delegated

263:      * @param   middlewareTimesIndex  is the index in the operator that the staker who triggered the withdrawal was delegated to's middleware times array

456:      * @dev     Before the eigenpod is verified, we can sweep out any accumulated ETH from the Consensus layer validator rewards

457:      *         We also want to track the amount in the delayed withdrawal router so we can track the TVL and reward amount accurately

498:      * @dev Handle ETH sent to this contract - will get forwarded to the deposit queue for restaking as a protocol reward

499:      * @dev If msg.sender is eigenPod then forward ETH to deposit queue without taking cut (i.e. full withdrawal from beacon chain)


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L105-L105) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L140-L140), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L263-L263), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L456-L456), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L457-L457), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L498-L498), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L499-L499)


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20.sol

43:     // constructor(string memory _name, string memory _symbol, address _factory) ERC20Upgradeable(_name, _symbol) ERC20PermitUpgradeable(_name) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L43-L43) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Factory.sol

70:      * @param _proxyAdmin The address of the proxy admin - will have permission to upgrade the lockbox (should be a dedicated account or contract to manage upgrades)

100:      * @param _isNative Whether or not the base token is the native (gas) token of the chain. Eg: MATIC for polygon chain

101:      * @param _proxyAdmin The address of the proxy admin - will have permission to upgrade the lockbox (should be a dedicated account or contract to manage upgrades)

131:      * @param _proxyAdmin The address of the proxy admin - will have permission to upgrade the lockbox (should be a dedicated account or contract to manage upgrades)

180:      * @param _isNative Whether or not the base token is the native (gas) token of the chain. Eg: MATIC for polygon chain

181:      * @param _proxyAdmin The address of the proxy admin - will have permission to upgrade the lockbox (should be a dedicated account or contract to manage upgrades)


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L70-L70) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L100-L100), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L101-L101), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L131-L131), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L180-L180), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L181-L181)


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol

32:      * @param _proxyAdmin The address of the proxy admin - will have permission to upgrade the lockbox (should be a dedicated account or contract to manage upgrades)

68:      * @param _proxyAdmin The address of the proxy admin - will have permission to upgrade the lockbox (should be a dedicated account or contract to manage upgrades)


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L32-L32) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L68-L68)


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

305:      * @dev     This function will receive the price feed and timestamp from the L1 through CCIPReceiver middleware contract.

371:         // We will accept any amount of tokens out here... The caller of this function should verify the amount meets minimums


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L305-L305) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L371-L371)


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2.sol

29:         // Verify that the pricing of the oracle less than or equal 18 decimals - pricing calculations will be off otherwise

38:         // Verify that the pricing of the oracle is less than or equal to 18 decimals - pricing calculations will be off otherwise


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L29-L29) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L38-L38)


</details>


### [NC&#x2011;42] Missing event and or timelock for critical parameter change 
Events help non-contract tools to track changes, and events prevent users from being surprised by changes


*There are 3 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/token/EzEthToken.sol

51:     function setPaused(bool _paused) external onlyTokenAdmin {
52:         paused = _paused;
53:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L51-L53) 


```solidity

File: contracts/RestakeManager.sol

121:     function setPaused(bool _paused) external onlyDepositWithdrawPauserAdmin {
122:         paused = _paused;
123:     }

215:     function setMaxDepositTVL(uint256 _maxDepositTVL) external onlyRestakeManagerAdmin {
216:         maxDepositTVL = _maxDepositTVL;
217:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L121-L123) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L215-L217)


</details>


### [NC&#x2011;43] File is missing NatSpec 



*There are 4 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Oracle/Mantle/METHShimStorage.sol

0: 


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShimStorage.sol#L0-L0) 


```solidity

File: contracts/Oracle/Binance/WBETHShimStorage.sol

0: 


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShimStorage.sol#L0-L0) 


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2Storage.sol

0: 


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2Storage.sol#L0-L0) 


```solidity

File: contracts/Bridge/Connext/libraries/TokenId.sol

0: 


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/libraries/TokenId.sol#L0-L0) 


</details>


### [NC&#x2011;44] Mixed usage of `int`/`uint` with `int256`/`uint256` 
`int256`/`uint256` are the preferred type names (they're what are used for function signatures), so they should be used consistently


*There are 2 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Delegation/OperatorDelegator.sol

37:         uint nonce,

38:         uint startBlock,


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L37-L37) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L38-L38)


</details>


### [NC&#x2011;45] Consider using named mappings 
Consider using [named mappings](https://ethereum.stackexchange.com/a/145555) to make it easier to understand the purpose of each mapping


*There are 15 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Withdraw/WithdrawQueueStorage.sol

44:     mapping(address => uint256) public withdrawalBufferTarget;

47:     mapping(address => uint256) public claimReserve;

50:     mapping(address => WithdrawRequest[]) public withdrawRequests;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueueStorage.sol#L44-L44) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueueStorage.sol#L47-L47), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueueStorage.sol#L50-L50)


```solidity

File: contracts/TimelockController.sol

32:     mapping(bytes32 => uint256) private _timestamps;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L32-L32) 


```solidity

File: contracts/RestakeManagerStorage.sol

39:     mapping(bytes32 => PendingWithdrawal) public pendingWithdrawals;

46:     mapping(IOperatorDelegator => uint256) public operatorDelegatorAllocations;

65:     mapping(IERC20 => uint256) public collateralTokenTvlLimits;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManagerStorage.sol#L39-L39) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManagerStorage.sol#L46-L46), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManagerStorage.sol#L65-L65)


```solidity

File: contracts/Oracle/RenzoOracleStorage.sol

13:     mapping(IERC20 => AggregatorV3Interface) public tokenOracleLookup;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracleStorage.sol#L13-L13) 


```solidity

File: contracts/Deposits/DepositQueueStorage.sol

23:     mapping(address => uint256) public totalEarned;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueueStorage.sol#L23-L23) 


```solidity

File: contracts/Delegation/OperatorDelegatorStorage.sol

28:     mapping(IERC20 => IStrategy) public tokenStrategyMapping;

56:     mapping(address => uint256) public adminGasSpentInWei;

61:     mapping(address => uint256) public queuedShares;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegatorStorage.sol#L28-L28) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegatorStorage.sol#L56-L56), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegatorStorage.sol#L61-L61)


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20.sol

41:     mapping(address => Bridge) public bridges;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L41-L41) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Factory.sol

20:     mapping(address => address) internal _lockboxRegistry;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L20-L20) 


```solidity

File: contracts/Bridge/L2/xRenzoDepositStorage.sol

44:     mapping(address => bool) public allowedBridgeSweepers;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L44-L44) 


</details>


### [NC&#x2011;46] Consider using later versions of solidity for more cappabilities 
Consider using solidity 0.8.18 or later to benefit from multiple things including the named mappings [named mappings](https://ethereum.stackexchange.com/a/145555) to make it easier to understand the purpose of each mapping


*There are 4 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/TimelockController.sol

4: pragma solidity ^0.8.0;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L4-L4) 


```solidity

File: contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol

2: pragma solidity ^0.8.13;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L2-L2) 


```solidity

File: contracts/Bridge/Connext/libraries/LibConnextStorage.sol

2: pragma solidity ^0.8.0;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/libraries/LibConnextStorage.sol#L2-L2) 


```solidity

File: contracts/Bridge/Connext/libraries/TokenId.sol

2: pragma solidity ^0.8.0;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/libraries/TokenId.sol#L2-L2) 


</details>


### [NC&#x2011;47] The `nonReentrant` `modifier` should occur before all other modifiers 
This is a best-practice to protect against reentrancy in other modifiers


*There are 2 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Deposits/DepositQueue.sol

211:     function stakeEthFromQueueMulti(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L211-L211) 


```solidity

File: contracts/Bridge/L1/xRenzoBridge.sol

210:     function sendPrice(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L210-L210) 


</details>


### [NC&#x2011;48] Events that mark critical parameter changes should contain both the old and the new value 
This should especially be done if the new value is not required to be different from the old value


*There are 12 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Rewards/RewardHandler.sol

29:     event RewardDestinationUpdated(address rewardDestination);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L29-L29) 


```solidity

File: contracts/RestakeManager.sol

30:     event OperatorDelegatorAdded(IOperatorDelegator od);

32:     event OperatorDelegatorAllocationUpdated(IOperatorDelegator od, uint256 allocation);

34:     event CollateralTokenAdded(IERC20 token);

68:     event CollateralTokenTvlUpdated(IERC20 token, uint256 tvl);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L30-L30) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L32-L32), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L34-L34), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L68-L68)


```solidity

File: contracts/Oracle/RenzoOracle.sol

35:     event OracleAddressUpdated(IERC20 token, AggregatorV3Interface oracleAddress);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L35-L35) 


```solidity

File: contracts/Deposits/DepositQueue.sol

17:     event FeeConfigUpdated(address feeAddress, uint256 feeBasisPoints);

19:     event RestakeManagerUpdated(IRestakeManager restakeManager);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L17-L17) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L19-L19)


```solidity

File: contracts/Delegation/OperatorDelegator.sol

28:     event TokenStrategyUpdated(IERC20 token, IStrategy strategy);

29:     event DelegationAddressUpdated(address delegateAddress);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L28-L28) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L29-L29)


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

42:     event PriceUpdated(uint256 price, uint256 timestamp);

44:     event BridgeSweeperAddressUpdated(address sweeper, bool allowed);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L42-L42) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L44-L44)


</details>


### [NC&#x2011;49] Use of `override` is unnecessary 
Starting with Solidity version [0.8.8](https://docs.soliditylang.org/en/v0.8.20/contracts.html#function-overriding), using the `override` keyword when the function solely overrides an interface function, and the function doesn't exist in multiple base contracts, is unnecessary.


*There are 9 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/token/EzEthToken.sol

56:     function _beforeTokenTransfer(
57:         address from,
58:         address to,
59:         uint256 amount
60:     ) internal virtual override {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L56-L60) 


```solidity

File: contracts/TimelockController.sol

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

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L411-L416) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L423-L429), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L436-L442)


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol

56:     function remoteToken() public view override returns (address) {

60:     function bridge() public view override returns (address) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L56-L56) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L60-L60)


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

310:     function updatePrice(uint256 _price, uint256 _timestamp) external override {

456:     function getRate() external view override returns (uint256) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L310-L310) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L456-L456)


```solidity

File: contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol

66:     function _ccipReceive(
67:         Client.Any2EVMMessage memory any2EvmMessage
68:     ) internal override whenNotPaused {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L66-L68) 


</details>


### [NC&#x2011;50] `public` functions not called by the contract should be declared `external` instead 
Contracts [are allowed](https://docs.soliditylang.org/en/latest/contracts.html#function-overriding) to override their parents' functions and change the visibility from `external` to `public`.


*There are 34 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/token/EzEthToken.sol

33:     function initialize(IRoleManager _roleManager) public initializer {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L33-L33) 


```solidity

File: contracts/Withdraw/WithdrawQueue.sol

170:     function getBufferDeficit(address _asset) public view returns (uint256) {

270:     function getOutstandingWithdrawRequests(address user) public view returns (uint256) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L170-L170) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L270-L270)


```solidity

File: contracts/TimelockController.sol

234:     function schedule(

259:     function scheduleBatch(

296:     function cancel(bytes32 id) public virtual onlyRole(CANCELLER_ROLE) {

315:     function execute(

342:     function executeBatch(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L234-L234) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L259-L259), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L296-L296), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L315-L315), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L342-L342)


```solidity

File: contracts/Rewards/RewardHandler.sol

38:     function initialize(IRoleManager _roleManager, address _rewardDestination) public initializer {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L38-L38) 


```solidity

File: contracts/RestakeManager.sol

101:     function initialize(

400:     function chooseOperatorDelegatorForWithdraw(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L101-L101) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L400-L400)


```solidity

File: contracts/RateProvider/BalancerRateProvider.sol

17:     function initialize(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProvider.sol#L17-L17) 


```solidity

File: contracts/Permissions/RoleManager.sol

22:     function initialize(address roleManagerAdmin) public initializer {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L22-L22) 


```solidity

File: contracts/Oracle/RenzoOracle.sol

44:     function initialize(IRoleManager _roleManager) public initializer {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L44-L44) 


```solidity

File: contracts/Oracle/Mantle/METHShim.sol

23:     function initialize(IMethStaking _methStaking) public initializer {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L23-L23) 


```solidity

File: contracts/Oracle/Binance/WBETHShim.sol

23:     function initialize(IStakedTokenV2 _wBETHToken) public initializer {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L23-L23) 


```solidity

File: contracts/Deposits/DepositQueue.sol

74:     function initialize(IRoleManager _roleManager) public initializer {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L74-L74) 


```solidity

File: contracts/Delegation/OperatorDelegator.sol

172:     function getStrategyIndex(IStrategy _strategy) public view returns (uint256) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L172-L172) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20.sol

61:     function initialize(

96:     function mint(address _user, uint256 _amount) public virtual {

107:     function burn(address _user, uint256 _amount) public virtual {

121:     function setLockbox(address _lockbox) public {

152:     function mintingMaxLimitOf(address _bridge) public view returns (uint256 _limit) {

163:     function burningMaxLimitOf(address _bridge) public view returns (uint256 _limit) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L61-L61) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L96-L96), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L107-L107), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L121-L121), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L152-L152), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L163-L163)


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Factory.sol

54:     function initialize(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L54-L54) 


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol

35:     function initialize(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L35-L35) 


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol

37:     function deployOptimismMintableXERC20(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L37-L37) 


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

75:     function initialize(

414:     function sweep() public payable nonReentrant {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L75-L75) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L414-L414)


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2.sol

23:     function initialize(AggregatorV3Interface _oracle) public initializer {

50:     function getMintRate() public view returns (uint256, uint256) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L23-L23) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L50-L50)


```solidity

File: contracts/Bridge/L1/xRenzoBridge.sol

70:     function initialize(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L70-L70) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol

44:     function initialize(address _xerc20, address _erc20, bool _isNative) public initializer {

91:     function depositNativeTo(address _to) public payable {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L44-L44) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L91-L91)


</details>


### [NC&#x2011;51] Adding a `return` statement when the function defines a named return variable, is redundant 
Once the return variable has been assigned (or has its default value), there is no need to explicitly return it at the end of the function, since it's returned automatically.


*There are 1 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Bridge/xERC20/contracts/XERC20.sol

310:             return _limit;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L310-L310) 


</details>


### [NC&#x2011;52] Redundant inheritance specifier 
The contracts below already extend the specified contract, so there is no need to list it in the inheritance list again


*There are 13 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/token/EzEthToken.sol

//@audit `Initializable` is already inherited by `ERC20Upgradeable` 
13: contract EzEthToken is Initializable, ERC20Upgradeable, IEzEthToken, EzEthTokenStorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L13-L13) 


```solidity

File: contracts/Withdraw/WithdrawQueue.sol

//@audit `Initializable` is already inherited by `PausableUpgradeable` 
11: contract WithdrawQueue is
12:     Initializable,
13:     PausableUpgradeable,


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L11-L13) 


```solidity

File: contracts/Rewards/RewardHandler.sol

//@audit `Initializable` is already inherited by `ReentrancyGuardUpgradeable` 
16: contract RewardHandler is Initializable, ReentrancyGuardUpgradeable, RewardHandlerStorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L16-L16) 


```solidity

File: contracts/RestakeManager.sol

//@audit `Initializable` is already inherited by `ReentrancyGuardUpgradeable` 
26: contract RestakeManager is Initializable, ReentrancyGuardUpgradeable, RestakeManagerStorageV2 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L26-L26) 


```solidity

File: contracts/Oracle/RenzoOracle.sol

//@audit `Initializable` is already inherited by `ReentrancyGuardUpgradeable` 
13: contract RenzoOracle is
14:     IRenzoOracle,
15:     Initializable,
16:     ReentrancyGuardUpgradeable,


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L13-L16) 


```solidity

File: contracts/Deposits/DepositQueue.sol

//@audit `Initializable` is already inherited by `ReentrancyGuardUpgradeable` 
10: contract DepositQueue is Initializable, ReentrancyGuardUpgradeable, DepositQueueStorageV2 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L10-L10) 


```solidity

File: contracts/Delegation/OperatorDelegator.sol

//@audit `Initializable` is already inherited by `ReentrancyGuardUpgradeable` 
17: contract OperatorDelegator is
18:     Initializable,
19:     ReentrancyGuardUpgradeable,


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L17-L19) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20.sol

//@audit `Initializable` is already inherited by `ERC20Upgradeable` 
16: contract XERC20 is
17:     Initializable,
18:     ERC20Upgradeable,

//@audit `ERC20Upgradeable` is already inherited by `ERC20PermitUpgradeable` 
16: contract XERC20 is
17:     Initializable,
18:     ERC20Upgradeable,
19:     OwnableUpgradeable,
20:     IXERC20,
21:     ERC20PermitUpgradeable


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L16-L18) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L16-L21)


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol

//@audit `Initializable` is already inherited by `XERC20Factory` 
14: contract OptimismMintableXERC20Factory is Initializable, XERC20Factory {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L14-L14) 


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

//@audit `Initializable` is already inherited by `OwnableUpgradeable` 
27: contract xRenzoDeposit is
28:     Initializable,
29:     OwnableUpgradeable,


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L27-L29) 


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2.sol

//@audit `Initializable` is already inherited by `OwnableUpgradeable` 
11: contract RenzoOracleL2 is Initializable, OwnableUpgradeable, RenzoOracleL2StorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L11-L11) 


```solidity

File: contracts/Bridge/L1/xRenzoBridge.sol

//@audit `Initializable` is already inherited by `ReentrancyGuardUpgradeable` 
16: contract xRenzoBridge is
17:     IXReceiver,
18:     Initializable,
19:     ReentrancyGuardUpgradeable,


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L16-L19) 


</details>


### [NC&#x2011;53] Setters should prevent re-setting of the same value 
This especially problematic when the setter also emits the same value, which may be confusing to offline parsers


*There are 14 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/token/EzEthToken.sol

//@audit `paused` and `_paused` are never checked for the same value setting
51:     function setPaused(bool _paused) external onlyTokenAdmin {
52:         paused = _paused;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L51-L52) 


```solidity

File: contracts/Rewards/RewardHandler.sol

//@audit `rewardDestination` and `_rewardDestination` are never checked for the same value setting
72:     function setRewardDestination(
73:         address _rewardDestination
74:     ) external nonReentrant onlyRestakeManagerAdmin {
75:         if (address(_rewardDestination) == address(0x0)) revert InvalidZeroInput();
76: 
77:         rewardDestination = _rewardDestination;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L72-L77) 


```solidity

File: contracts/RestakeManager.sol

//@audit `paused` and `_paused` are never checked for the same value setting
121:     function setPaused(bool _paused) external onlyDepositWithdrawPauserAdmin {
122:         paused = _paused;

//@audit `maxDepositTVL` and `_maxDepositTVL` are never checked for the same value setting
215:     function setMaxDepositTVL(uint256 _maxDepositTVL) external onlyRestakeManagerAdmin {
216:         maxDepositTVL = _maxDepositTVL;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L121-L122) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L215-L216)


```solidity

File: contracts/Deposits/DepositQueue.sol

//@audit `withdrawQueue` and `_withdrawQueue` are never checked for the same value setting
87:     function setWithdrawQueue(IWithdrawQueue _withdrawQueue) external onlyRestakeManagerAdmin {
88:         if (address(_withdrawQueue) == address(0)) revert InvalidZeroInput();
89:         emit WithdrawQueueUpdated(address(withdrawQueue), address(_withdrawQueue));
90:         withdrawQueue = _withdrawQueue;

//@audit `feeAddress` and `_feeAddress` are never checked for the same value setting
093:     function setFeeConfig(
094:         address _feeAddress,
095:         uint256 _feeBasisPoints
096:     ) external onlyRestakeManagerAdmin {
097:         // Verify address is set if basis points are non-zero
098:         if (_feeBasisPoints > 0) {
099:             if (_feeAddress == address(0x0)) revert InvalidZeroInput();
100:         }
101: 
102:         // Verify basis points are not over 100%
103:         if (_feeBasisPoints > 10000) revert OverMaxBasisPoints();
104: 
105:         feeAddress = _feeAddress;

//@audit `feeBasisPoints` and `_feeBasisPoints` are never checked for the same value setting
093:     function setFeeConfig(
094:         address _feeAddress,
095:         uint256 _feeBasisPoints
096:     ) external onlyRestakeManagerAdmin {
097:         // Verify address is set if basis points are non-zero
098:         if (_feeBasisPoints > 0) {
099:             if (_feeAddress == address(0x0)) revert InvalidZeroInput();
100:         }
101: 
102:         // Verify basis points are not over 100%
103:         if (_feeBasisPoints > 10000) revert OverMaxBasisPoints();
104: 
105:         feeAddress = _feeAddress;
106:         feeBasisPoints = _feeBasisPoints;

//@audit `restakeManager` and `_restakeManager` are never checked for the same value setting
112:     function setRestakeManager(IRestakeManager _restakeManager) external onlyRestakeManagerAdmin {
113:         if (address(_restakeManager) == address(0x0)) revert InvalidZeroInput();
114: 
115:         restakeManager = _restakeManager;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L87-L90) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L93-L105), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L93-L106), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L112-L115)


```solidity

File: contracts/Delegation/OperatorDelegator.sol

//@audit `delegateAddress` and `_delegateAddress` are never checked for the same value setting
117:     function setDelegateAddress(
118:         address _delegateAddress,
119:         ISignatureUtils.SignatureWithExpiry memory approverSignatureAndExpiry,
120:         bytes32 approverSalt
121:     ) external nonReentrant onlyOperatorDelegatorAdmin {
122:         if (address(_delegateAddress) == address(0x0)) revert InvalidZeroInput();
123:         if (address(delegateAddress) != address(0x0)) revert DelegateAddressAlreadySet();
124: 
125:         delegateAddress = _delegateAddress;

//@audit `baseGasAmountSpent` and `_baseGasAmountSpent` are never checked for the same value setting
132:     function setBaseGasAmountSpent(
133:         uint256 _baseGasAmountSpent
134:     ) external nonReentrant onlyOperatorDelegatorAdmin {
135:         if (_baseGasAmountSpent == 0) revert InvalidZeroInput();
136:         emit BaseGasAmountSpentUpdated(baseGasAmountSpent, _baseGasAmountSpent);
137:         baseGasAmountSpent = _baseGasAmountSpent;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L117-L125) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L132-L137)


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20.sol

//@audit `lockbox` and `_lockbox` are never checked for the same value setting
121:     function setLockbox(address _lockbox) public {
122:         if (msg.sender != FACTORY) revert IXERC20_NotFactory();
123:         lockbox = _lockbox;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L121-L123) 


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

//@audit `oracle` and `_oracle` are never checked for the same value setting
501:     function setOraclePriceFeed(IRenzoOracleL2 _oracle) external onlyOwner {
502:         emit OraclePriceFeedUpdated(address(_oracle), address(oracle));
503:         oracle = _oracle;

//@audit `receiver` and `_receiver` are never checked for the same value setting
511:     function setReceiverPriceFeed(address _receiver) external onlyOwner {
512:         emit ReceiverPriceFeedUpdated(_receiver, receiver);
513:         receiver = _receiver;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L501-L503) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L511-L513)


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2.sol

//@audit `oracle` and `_oracleAddress` are never checked for the same value setting
36:     function setOracleAddress(AggregatorV3Interface _oracleAddress) external onlyOwner {
37:         if (address(_oracleAddress) == address(0)) revert InvalidZeroInput();
38:         // Verify that the pricing of the oracle is less than or equal to 18 decimals - pricing calculations will be off otherwise
39:         if (_oracleAddress.decimals() > 18)
40:             revert InvalidTokenDecimals(18, _oracleAddress.decimals());
41: 
42:         emit OracleAddressUpdated(address(_oracleAddress), address(oracle));
43:         oracle = _oracleAddress;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L36-L43) 


</details>


### [NC&#x2011;54] NatSpec `@return` argument is missing 



*There are 43 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/token/EzEthToken.sol

// @audit the @return is missing
 @dev Returns the name of the token.

// @audit the @return is missing
 @dev Returns the symbol of the token, usually a shorter version of the
 name.


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L77-L1) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L85-L1)


```solidity

File: contracts/TimelockController.sol

// @audit the @return is missing
 @dev See {IERC165-supportsInterface}.

// @audit the @return is missing
 @dev Returns whether an id correspond to a registered operation. This
 includes both Pending, Ready and Done operations.

// @audit the @return is missing
 @dev Returns whether an operation is pending or not. Note that a "pending" operation may also be "ready".

// @audit the @return is missing
 @dev Returns whether an operation is ready for execution. Note that a "ready" operation is also "pending".

// @audit the @return is missing
 @dev Returns whether an operation is done or not.

// @audit the @return is missing
 @dev Returns the timestamp at which an operation becomes ready (0 for
 unset operations, 1 for done operations).

// @audit the @return is missing
 @dev Returns the minimum delay for an operation to become valid.
 This value can be changed by executing an operation that calls `updateDelay`.

// @audit the @return is missing
 @dev Returns the identifier of an operation containing a single
 transaction.

// @audit the @return is missing
 @dev Returns the identifier of an operation containing a batch of
 transactions.

// @audit the @return is missing
 @dev See {IERC721Receiver-onERC721Received}.

// @audit the @return is missing
 @dev See {IERC1155Receiver-onERC1155Received}.

// @audit the @return is missing
 @dev See {IERC1155Receiver-onERC1155BatchReceived}.


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L142-L1) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L154-L1), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L161-L1), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L168-L1), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L176-L1), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L184-L1), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L193-L1), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L201-L1), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L215-L1), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L411-L1), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L423-L1), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L436-L1)


```solidity

File: contracts/RestakeManager.sol

// @audit the @return is missing
@dev Get the length of the operator delegators array

// @audit the @return is missing
@dev Get the length of the collateral tokens array

// @audit the @return is missing
@dev Finds the index of the collateral token in the list
 Reverts if the token is not found in the list


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L126-L1) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L266-L1), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L451-L1)


```solidity

File: contracts/RateProvider/BalancerRateProvider.sol

// @audit the @return is missing
@dev Returns the current rate of ezETH in ETH


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProvider.sol#L29-L1) 


```solidity

File: contracts/Permissions/RoleManager.sol

// @audit the @return is missing
@dev Determines if the specified address has permissions to manage RoleManager
 @param potentialAddress Address to check

// @audit the @return is missing
@dev Determines if the specified address has permission to mint or burn ezETH tokens
 @param potentialAddress Address to check

// @audit the @return is missing
@dev Determines if the specified address has permission to update config on the OperatorDelgator Contracts
 @param potentialAddress Address to check

// @audit the @return is missing
@dev Determines if the specified address has permission to update config on the Oracle Contract config
 @param potentialAddress Address to check

// @audit the @return is missing
@dev Determines if the specified address has permission to update config on the RestakeManager Contract config
 @param potentialAddress Address to check

// @audit the @return is missing
@dev Determines if the specified address has permission to update config on the Token Contract
 @param potentialAddress Address to check

// @audit the @return is missing
@dev Determines if the specified address has permission to trigger restaking of native ETH
 @param potentialAddress Address to check

// @audit the @return is missing
@dev Determines if the specified address has permission to sweep and deposit ERC20 Rewards
 @param potentialAddress Address to check

// @audit the @return is missing
@dev Determines if the specified address has permission to pause deposits and withdraws
 @param potentialAddress Address to check

// @audit the @return is missing
@dev Determines if the specified address has permission to set whitelisted origin in xRenzoBridge
 @param potentialAddress Address to check

// @audit the @return is missing
@dev Determined if the specified address has permission to send price feed of ezETH to L2
 @param potentialAddress Address to check

// @audit the @return is missing
@dev Determine if the specified address haas permission to update Withdraw Queue params
 @param potentialAddress Address to check


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L32-L1) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L38-L1), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L44-L1), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L50-L1), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L56-L1), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L62-L1), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L68-L1), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L74-L1), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L80-L1), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L86-L1), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L92-L1), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L98-L1)


```solidity

File: contracts/Oracle/RenzoOracle.sol

// @audit the @return is missing
@dev Given a single token and balance, return value of the asset in underlying currency
 The value returned will be denominated in the decimal precision of the lookup oracle
 (e.g. a value of 100 would return as 100 * 10^18)

// @audit the @return is missing
@dev Given a single token and value, return amount of tokens needed to represent that value
 Assumes the token value is already denominated in the same decimal precision as the oracle

// @audit the @return is missing
The value returned will be denominated in the decimal precision of the lookup oracle
 (e.g. a value of 100 would return as 100 * 10^18)

// @audit the @return is missing
@dev Given amount of current protocol value, new value being added, and supply of ezETH, determine amount to mint
 Values should be denominated in the same underlying currency with the same decimal precision


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L71-L1) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L85-L1), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L103-L1), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L123-L1)


```solidity

File: contracts/Oracle/Mantle/METHShim.sol

// @audit the @return is missing
@dev Historical data not available


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L42-L1) 


```solidity

File: contracts/Oracle/Binance/WBETHShim.sol

// @audit the @return is missing
@dev Historical data not available


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L42-L1) 


```solidity

File: contracts/Delegation/OperatorDelegator.sol

// @audit the @return is missing
@dev Gets the index of the specific strategy in EigenLayer in the staker's strategy list

// @audit the @return is missing
@dev Gets the underlying token amount from the amount of shares + queued withdrawal shares

// @audit the @return is missing
@dev Gets the amount of ETH staked in the EigenLayer


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L172-L1) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L327-L1), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L338-L1)


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

// @audit the @return is missing
 @notice Function returns bridge fee share for deposit
 @param _amountIn deposit amount in terms of ETH

// @audit the @return is missing
 @notice Fetch the price of ezETH from configured price feeds


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L277-L1) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L289-L1)


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2.sol

// @audit the @return is missing
 @notice Pulls the price of ezETH
 @dev reverts if price is less than 1 Ether


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L50-L1) 


```solidity

File: contracts/Bridge/L1/xRenzoBridge.sol

// @audit the @return is missing
 @notice  Accepts collateral from the bridge
 @dev     This function will take all collateral and deposit it into Renzo
          The ezETH from the deposit will be sent to the lockbox to be wrapped into xezETH
          The xezETH will be burned so that the xezETH on the L2 can be unwrapped for ezETH later
 @notice  WARNING: This function does NOT whitelist who can send funds from the L2 via Connext.  Users should NOT
          send funds directly to this contract.  A user who sends funds directly to this contract will cause
          the tokens on the L2 to become over collateralized and will be a "donation" to protocol.  Only use
          the deposit contracts on the L2 to send funds to this contract.


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L139-L1) 


</details>


### [NC&#x2011;55] Consider using `SafeTransferLib.safeTransferETH()` or `Address.sendValue()` for clearer semantic meaning 
These Functions indicate their purpose with their name more clearly than using low-level calls.


*There are 7 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/TimelockController.sol

369:         (bool success, ) = target.call{ value: value }(data);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L369-L369) 


```solidity

File: contracts/Rewards/RewardHandler.sol

68:         (bool success, ) = rewardDestination.call{ value: balance }("");


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L68-L68) 


```solidity

File: contracts/Deposits/DepositQueue.sol

286:         (bool success, ) = payable(msg.sender).call{ value: gasRefund }("");

168:             (bool success, ) = feeAddress.call{ value: feeAmount }("");


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L286-L286) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L168-L168)


```solidity

File: contracts/Delegation/OperatorDelegator.sol

520:             (bool success, ) = destination.call{ value: remainingAmount }("");


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L520-L520) 


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

403:         (bool success, ) = payable(msg.sender).call{ value: feeCollected }("");


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L403-L403) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol

131:             (bool _success, ) = payable(_to).call{ value: _amount }("");


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L131-L131) 


</details>


### [NC&#x2011;56] Polymorphic functions make security audits more time-consuming and error-prone 
The instances below point to one of two functions with the same name. Consider naming each function differently, in order to make code navigation and analysis easier.


*There are 2 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/RestakeManager.sol

491:     function deposit(

592:     function depositETH(uint256 _referralId) public payable nonReentrant notPaused {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L491-L491) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L592-L592)


</details>


### [NC&#x2011;57] Large multiples of ten should use scientific notation (e.g. `1e6`) rather than decimal literals (e.g. `1000000`), for readability 
While the compiler knows to optimize away the exponentiation, it's still better coding practice to use idioms that do not require compiler optimization, if they exist


*There are 5 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Deposits/DepositQueue.sol

//@audit `10000`
103:         if (_feeBasisPoints > 10000) revert OverMaxBasisPoints();

//@audit `10000`
167:             feeAmount = (msg.value * feeBasisPoints) / 10000;

//@audit `10000`
261:                 feeAmount = (balance * feeBasisPoints) / 10000;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L103-L103) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L167-L167), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L261-L261)


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

//@audit `10000`
40:     uint32 public constant FEE_BASIS = 10000;

//@audit `10_000`
386:             uint256 fee = (amountNextWETH * bridgeRouterFeeBps) / 10_000;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L40-L40) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L386-L386)


</details>


### [NC&#x2011;58] Consider moving `msg.sender` checks to a common authorization `modifier` 



*There are 1 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/TimelockController.sol

403:         require(msg.sender == address(this), "TimelockController: caller must be timelock");


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L403-L403) 


</details>


### [NC&#x2011;59] Empty `receive()`/`payable fallback()` function does not authorize requests 
If the intention is for the Ether to be used, the function should call another function, otherwise it should revert (e.g. `require(msg.sender == address(weth))`). Having no access control on the function means that someone may send Ether to the contract, and have no way to get anything back out, which is a loss of funds. If the concern is having to spend a small amount of gas to check the sender against an immutable address, the code should at least have a function to rescue unused Ether.


*There are 3 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/TimelockController.sol

137:     receive() external payable {}
138: 


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L137-L138) 


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

542:     receive() external payable {}
543: }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L542-L543) 


```solidity

File: contracts/Bridge/L1/xRenzoBridge.sol

313:     receive() external payable {}
314: }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L313-L314) 


</details>


### [NC&#x2011;60] State variables should have `Natspec` comments 
Consider adding some `Natspec` comments on critical state variables to explain what they are supposed to do: this will help for future code reviews.


*There are 22 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Withdraw/WithdrawQueueStorage.sol

//@audit IS_NATIVE need comments
10:     address public constant IS_NATIVE = 0xEeeeeEeeeEeEeeEeEeEeeEEEeeeeEeeeeeeeEEeE;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueueStorage.sol#L10-L10) 


```solidity

File: contracts/TimelockController.sol

//@audit TIMELOCK_ADMIN_ROLE need comments
26:     bytes32 public constant TIMELOCK_ADMIN_ROLE = keccak256("TIMELOCK_ADMIN_ROLE");

//@audit PROPOSER_ROLE need comments
27:     bytes32 public constant PROPOSER_ROLE = keccak256("PROPOSER_ROLE");

//@audit EXECUTOR_ROLE need comments
28:     bytes32 public constant EXECUTOR_ROLE = keccak256("EXECUTOR_ROLE");

//@audit CANCELLER_ROLE need comments
29:     bytes32 public constant CANCELLER_ROLE = keccak256("CANCELLER_ROLE");

//@audit _DONE_TIMESTAMP need comments
30:     uint256 internal constant _DONE_TIMESTAMP = uint256(1);

//@audit _timestamps need comments
32:     mapping(bytes32 => uint256) private _timestamps;

//@audit _minDelay need comments
33:     uint256 private _minDelay;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L26-L26) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L27-L27), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L28-L28), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L29-L29), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L30-L30), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L32-L32), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L33-L33)


```solidity

File: contracts/RestakeManagerStorage.sol

//@audit collateralTokenTvlLimits need comments
65:     mapping(IERC20 => uint256) public collateralTokenTvlLimits;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManagerStorage.sol#L65-L65) 


```solidity

File: contracts/Oracle/RenzoOracle.sol

//@audit SCALE_FACTOR need comments
23:     uint256 constant SCALE_FACTOR = 10 ** 18;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L23-L23) 


```solidity

File: contracts/Oracle/Mantle/METHShimStorage.sol

//@audit methStaking need comments
8:     IMethStaking public methStaking;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShimStorage.sol#L8-L8) 


```solidity

File: contracts/Oracle/Binance/WBETHShimStorage.sol

//@audit wBETHToken need comments
8:     IStakedTokenV2 public wBETHToken;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShimStorage.sol#L8-L8) 


```solidity

File: contracts/Deposits/DepositQueueStorage.sol

//@audit withdrawQueue need comments
27:     IWithdrawQueue public withdrawQueue;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueueStorage.sol#L27-L27) 


```solidity

File: contracts/Deposits/DepositQueue.sol

//@audit IS_NATIVE need comments
13:     address public constant IS_NATIVE = 0xEeeeeEeeeEeEeeEeEeEeeEEEeeeeEeeeeeeeEEeE;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L13-L13) 


```solidity

File: contracts/Delegation/OperatorDelegator.sol

//@audit GWEI_TO_WEI need comments
24:     uint256 internal constant GWEI_TO_WEI = 1e9;

//@audit IS_NATIVE need comments
26:     address public constant IS_NATIVE = 0xEeeeeEeeeEeEeeEeEeEeeEEEeeeeEeeeeeeeEEeE;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L24-L24) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L26-L26)


```solidity

File: contracts/Bridge/L2/xRenzoDepositStorage.sol

//@audit bridgeFeeShare need comments
54:     uint256 public bridgeFeeShare;

//@audit sweepBatchSize need comments
57:     uint256 public sweepBatchSize;

//@audit bridgeFeeCollected need comments
60:     uint256 public bridgeFeeCollected;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L54-L54) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L57-L57), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L60-L60)


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2Storage.sol

//@audit oracle need comments
8:     AggregatorV3Interface public oracle;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2Storage.sol#L8-L8) 


```solidity

File: contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol

//@audit blastStandardBridge need comments
31:     address immutable blastStandardBridge;

//@audit registry need comments
32:     address immutable registry;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L31-L31) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L32-L32)


</details>


### [NC&#x2011;61] Contracts should have full test coverage 
While 100% code coverage does not guarantee that there are no bugs, it often will catch easy-to-find bugs, and will ensure that there are fewer regressions when the code invariably has to be modified. Furthermore, in order to get full coverage, code authors will often have to re-organize their code so that it is more modular, so that each component can be tested separately, which reduces interdependencies between modules and layers, and makes for code that is easier to reason about and audit.


*There are 1 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/token/EzEthTokenStorage.sol

@audit Multiple files
1: 


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthTokenStorage.sol#L1-L1) 


</details>


### [NC&#x2011;62] Numeric values having to do with time should use time units for readability 
There are [units](https://docs.soliditylang.org/en/latest/units-and-global-variables.html#time-units) for seconds, minutes, hours, days, and weeks, and since they're defined, they should be use


*There are 2 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Oracle/RenzoOracle.sol

//@audit the value 86400,60, should use time units
26:     uint256 constant MAX_TIME_WINDOW = 86400 + 60; // 24 hours + 60 seconds


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L26-L26) 


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2.sol

//@audit the value 86400,60, should use time units
13:     uint256 public constant MAX_TIME_WINDOW = 86400 + 60; // 24 hours + 60 seconds


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L13-L13) 


</details>


### [NC&#x2011;63] [NatSpec] Natspec `@title` is missing from `contract` 



*There are 38 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/token/EzEthToken.sol

11: /// @dev This contract is the ezETH ERC20 token
12: /// Ownership of the collateral in the protocol is tracked by the ezETH token
13: contract EzEthToken is Initializable, ERC20Upgradeable, IEzEthToken, EzEthTokenStorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L11-L13) 


```solidity

File: contracts/Withdraw/WithdrawQueue.sol

11: contract WithdrawQueue is


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L11-L11) 


```solidity

File: contracts/Withdraw/WithdrawQueueStorage.sol

9: abstract contract WithdrawQueueStorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueueStorage.sol#L9-L9) 


```solidity

File: contracts/TimelockController.sol

10: /**
11:  * @dev Contract module which acts as a timelocked controller. When set as the
12:  * owner of an `Ownable` smart contract, it enforces a timelock on all
13:  * `onlyOwner` maintenance operations. This gives time for users of the
14:  * controlled contract to exit before a potentially dangerous maintenance
15:  * operation is applied.
16:  *
17:  * By default, this contract is self administered, meaning administration tasks
18:  * have to go through the timelock process. The proposer (resp executor) role
19:  * is in charge of proposing (resp executing) operations. A common use case is
20:  * to position this {TimelockController} as the owner of a smart contract, with
21:  * a multisig or a DAO as the sole proposer.
22:  *
23:  * _Available since v3.3._
24:  */


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L10-L24) 


```solidity

File: contracts/Rewards/RewardHandlerStorage.sol

6: abstract contract RewardHandlerStorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandlerStorage.sol#L6-L6) 


```solidity

File: contracts/RestakeManagerStorage.sol

15: abstract contract RestakeManagerStorageV1 is IRestakeManager {

64: abstract contract RestakeManagerStorageV2 is RestakeManagerStorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManagerStorage.sol#L15-L15) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManagerStorage.sol#L64-L64)


```solidity

File: contracts/RateProvider/BalancerRateProvider.sol

9: contract BalancerRateProvider is Initializable, IRateProvider, BalancerRateProviderStorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProvider.sol#L9-L9) 


```solidity

File: contracts/RateProvider/BalancerRateProviderStorage.sol

7: abstract contract BalancerRateProviderStorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProviderStorage.sol#L7-L7) 


```solidity

File: contracts/Permissions/RoleManagerStorage.sol

35: /// On the next version of the protocol, if new variables are added, put them in the below
36: /// contract and use this as the inheritance chain.
37: contract RoleManagerStorageV2 is RoleManagerStorageV1 {

45: contract RoleManagerStorageV3 is RoleManagerStorageV2 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManagerStorage.sol#L35-L37) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManagerStorage.sol#L45-L45)


```solidity

File: contracts/Oracle/RenzoOracle.sol

10: /// @dev This contract will be responsible for looking up values via Chainlink
11: /// Data retrieved will be verified for liveness via a max age on the oracle lookup.
12: /// All tokens should be denominated in the same base currency and contain the same decimals on the price lookup.
13: contract RenzoOracle is


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L10-L13) 


```solidity

File: contracts/Oracle/RenzoOracleStorage.sol

8: abstract contract RenzoOracleStorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracleStorage.sol#L8-L8) 


```solidity

File: contracts/Oracle/Mantle/METHShimStorage.sol

7: abstract contract METHShimStorageV1 is AggregatorV3Interface {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShimStorage.sol#L7-L7) 


```solidity

File: contracts/Oracle/Binance/WBETHShimStorage.sol

7: abstract contract WBETHShimStorageV1 is AggregatorV3Interface {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShimStorage.sol#L7-L7) 


```solidity

File: contracts/Deposits/DepositQueueStorage.sol

9: abstract contract DepositQueueStorageV1 is IDepositQueue {

26: abstract contract DepositQueueStorageV2 is DepositQueueStorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueueStorage.sol#L9-L9) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueueStorage.sol#L26-L26)


```solidity

File: contracts/Deposits/DepositQueue.sol

10: contract DepositQueue is Initializable, ReentrancyGuardUpgradeable, DepositQueueStorageV2 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L10-L10) 


```solidity

File: contracts/Delegation/OperatorDelegator.sol

12: /// @dev This contract will be responsible for interacting with Eigenlayer
13: /// Each of these contracts deployed will be delegated to one specific operator
14: /// This contract can handle multiple ERC20 tokens, all of which will be delegated to the same operator
15: /// Each supported ERC20 token will be pointed at a single Strategy contract in EL
16: /// Only the RestakeManager should be interacting with this contract for EL interactions.
17: contract OperatorDelegator is


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L12-L17) 


```solidity

File: contracts/Delegation/OperatorDelegatorStorage.sol

46: abstract contract OperatorDelegatorStorageV2 is OperatorDelegatorStorageV1 {

51: abstract contract OperatorDelegatorStorageV3 is OperatorDelegatorStorageV2 {

59: abstract contract OperatorDelegatorStorageV4 is OperatorDelegatorStorageV3 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegatorStorage.sol#L46-L46) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegatorStorage.sol#L51-L51), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegatorStorage.sol#L59-L59)


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20.sol

16: contract XERC20 is


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L16-L16) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Factory.sol

14: contract XERC20Factory is Initializable, IXERC20Factory {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L14-L14) 


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol

11: contract OptimismMintableXERC20 is ERC165Upgradeable, XERC20, IOptimismMintableERC20 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L11-L11) 


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol

14: contract OptimismMintableXERC20Factory is Initializable, XERC20Factory {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L14-L14) 


```solidity

File: contracts/Bridge/L2/xRenzoDepositStorage.sol

9: abstract contract xRenzoDepositStorageV1 is IxRenzoDeposit {

47: abstract contract xRenzoDepositStorageV2 is xRenzoDepositStorageV1 {

52: abstract contract xRenzoDepositStorageV3 is xRenzoDepositStorageV2 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L9-L9) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L47-L47), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L52-L52)


```solidity

File: contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol

10: contract ConnextReceiver is IXReceiver, Ownable, Pausable {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L10-L10) 


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2.sol

11: contract RenzoOracleL2 is Initializable, OwnableUpgradeable, RenzoOracleL2StorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L11-L11) 


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2Storage.sol

7: abstract contract RenzoOracleL2StorageV1 is IRenzoOracleL2 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2Storage.sol#L7-L7) 


```solidity

File: contracts/Bridge/L1/xRenzoBridge.sol

16: contract xRenzoBridge is


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L16-L16) 


```solidity

File: contracts/Bridge/L1/xRenzoBridgeStorage.sol

18: abstract contract xRenzoBridgeStorageV1 is IxRenzoBridge {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridgeStorage.sol#L18-L18) 


```solidity

File: contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol

9: interface IXERC20Registry {

17: interface L1StandardBridge {

28: /// @notice This adapter is only used for sending assets from Ethereum mainnet to Blast.
29: /// @dev Combines Lockbox deposit and Blast bridge's BridgeERC20 call to minimize user transactions.
30: contract LockboxAdapterBlast {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L9-L9) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L17-L17), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L28-L30)


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol

11: contract XERC20Lockbox is Initializable, IXERC20Lockbox {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L11-L11) 


</details>


### [NC&#x2011;64] Top level pragma declarations should be separated by two blank lines 



*There are 59 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/token/EzEthTokenStorage.sol

2: pragma solidity 0.8.19;
3: import "../Permissions/IRoleManager.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthTokenStorage.sol#L2-L3) 


```solidity

File: contracts/token/EzEthToken.sol

2: pragma solidity ^0.8.9;
3: 
4: import "@openzeppelin/contracts-upgradeable/token/ERC20/ERC20Upgradeable.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L2-L4) 


```solidity

File: contracts/Withdraw/WithdrawQueue.sol

2: pragma solidity 0.8.19;
3: 
4: import "./WithdrawQueueStorage.sol";

09: import "@openzeppelin/contracts/token/ERC20/IERC20.sol";
10: 
11: contract WithdrawQueue is


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L2-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L9-L11)


```solidity

File: contracts/Withdraw/WithdrawQueueStorage.sol

2: pragma solidity 0.8.19;
3: 
4: import "../Permissions/IRoleManager.sol";

7: import "../token/IEzEthToken.sol";
8: 
9: abstract contract WithdrawQueueStorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueueStorage.sol#L2-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueueStorage.sol#L7-L9)


```solidity

File: contracts/TimelockController.sol

4: pragma solidity ^0.8.0;
5: 
6: import "@openzeppelin/contracts/access/AccessControl.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L4-L6) 


```solidity

File: contracts/Rewards/RewardHandlerStorage.sol

2: pragma solidity 0.8.19;
3: 
4: import "../Permissions/IRoleManager.sol";

4: import "../Permissions/IRoleManager.sol";
5: 
6: abstract contract RewardHandlerStorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandlerStorage.sol#L2-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandlerStorage.sol#L4-L6)


```solidity

File: contracts/Rewards/RewardHandler.sol

2: pragma solidity 0.8.19;
3: 
4: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L2-L4) 


```solidity

File: contracts/RestakeManagerStorage.sol

2: pragma solidity 0.8.19;
3: 
4: import "./EigenLayer/interfaces/IStrategy.sol";

13: import "./Withdraw/IWithdrawQueue.sol";
14: 
15: abstract contract RestakeManagerStorageV1 is IRestakeManager {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManagerStorage.sol#L2-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManagerStorage.sol#L13-L15)


```solidity

File: contracts/RestakeManager.sol

2: pragma solidity 0.8.19;
3: 
4: import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L2-L4) 


```solidity

File: contracts/RateProvider/BalancerRateProvider.sol

2: pragma solidity 0.8.19;
3: 
4: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

7: import "./BalancerRateProviderStorage.sol";
8: 
9: contract BalancerRateProvider is Initializable, IRateProvider, BalancerRateProviderStorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProvider.sol#L2-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProvider.sol#L7-L9)


```solidity

File: contracts/RateProvider/BalancerRateProviderStorage.sol

2: pragma solidity 0.8.19;
3: 
4: import "@openzeppelin/contracts-upgradeable/token/ERC20/IERC20Upgradeable.sol";

5: import "../IRestakeManager.sol";
6: 
7: abstract contract BalancerRateProviderStorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProviderStorage.sol#L2-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProviderStorage.sol#L5-L7)


```solidity

File: contracts/Permissions/RoleManager.sol

2: pragma solidity 0.8.19;
3: 
4: import "@openzeppelin/contracts-upgradeable/access/AccessControlUpgradeable.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L2-L4) 


```solidity

File: contracts/Oracle/RenzoOracle.sol

2: pragma solidity 0.8.19;
3: 
4: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L2-L4) 


```solidity

File: contracts/Oracle/RenzoOracleStorage.sol

2: pragma solidity 0.8.19;
3: 
4: import "../Permissions/IRoleManager.sol";

6: import "@openzeppelin/contracts/token/ERC20/IERC20.sol";
7: 
8: abstract contract RenzoOracleStorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracleStorage.sol#L2-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracleStorage.sol#L6-L8)


```solidity

File: contracts/Oracle/Mantle/METHShim.sol

2: pragma solidity 0.8.19;
3: 
4: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L2-L4) 


```solidity

File: contracts/Oracle/Mantle/METHShimStorage.sol

2: pragma solidity 0.8.19;
3: 
4: import "@chainlink/contracts/src/v0.8/interfaces/AggregatorV3Interface.sol";

5: import "./IMethStaking.sol";
6: 
7: abstract contract METHShimStorageV1 is AggregatorV3Interface {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShimStorage.sol#L2-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShimStorage.sol#L5-L7)


```solidity

File: contracts/Oracle/Binance/WBETHShimStorage.sol

2: pragma solidity 0.8.19;
3: 
4: import "@chainlink/contracts/src/v0.8/interfaces/AggregatorV3Interface.sol";

5: import "./IStakedTokenV2.sol";
6: 
7: abstract contract WBETHShimStorageV1 is AggregatorV3Interface {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShimStorage.sol#L2-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShimStorage.sol#L5-L7)


```solidity

File: contracts/Oracle/Binance/WBETHShim.sol

2: pragma solidity 0.8.19;
3: 
4: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L2-L4) 


```solidity

File: contracts/Deposits/DepositQueueStorage.sol

2: pragma solidity 0.8.19;
3: 
4: import "../Permissions/IRoleManager.sol";

7: import "./IDepositQueue.sol";
8: 
9: abstract contract DepositQueueStorageV1 is IDepositQueue {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueueStorage.sol#L2-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueueStorage.sol#L7-L9)


```solidity

File: contracts/Deposits/DepositQueue.sol

2: pragma solidity 0.8.19;
3: 
4: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

08: import "../Errors/Errors.sol";
09: 
10: contract DepositQueue is Initializable, ReentrancyGuardUpgradeable, DepositQueueStorageV2 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L2-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L8-L10)


```solidity

File: contracts/Delegation/OperatorDelegator.sol

2: pragma solidity 0.8.19;
3: 
4: import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L2-L4) 


```solidity

File: contracts/Delegation/OperatorDelegatorStorage.sol

2: pragma solidity 0.8.19;
3: import "../Permissions/IRoleManager.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegatorStorage.sol#L2-L3) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20.sol

2: pragma solidity >=0.8.4 <0.9.0;
3: 
4: import { IXERC20 } from "../interfaces/IXERC20.sol";

14: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";
15: 
16: contract XERC20 is


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L2-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L14-L16)


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Factory.sol

2: pragma solidity >=0.8.4 <0.9.0;
3: 
4: import { IXERC20Factory } from "../interfaces/IXERC20Factory.sol";

12: import "@openzeppelin/contracts/proxy/transparent/TransparentUpgradeableProxy.sol";
13: 
14: contract XERC20Factory is Initializable, IXERC20Factory {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L2-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L12-L14)


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol

2: pragma solidity >=0.8.4 <0.9.0;
3: 
4: import {

09: import { XERC20 } from "../XERC20.sol";
10: 
11: contract OptimismMintableXERC20 is ERC165Upgradeable, XERC20, IOptimismMintableERC20 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L2-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L9-L11)


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol

2: pragma solidity >=0.8.4 <0.9.0;
3: 
4: import { OptimismMintableXERC20 } from "./OptimismMintableXERC20.sol";

12: import "@openzeppelin/contracts/proxy/transparent/TransparentUpgradeableProxy.sol";
13: 
14: contract OptimismMintableXERC20Factory is Initializable, XERC20Factory {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L2-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L12-L14)


```solidity

File: contracts/Bridge/L2/xRenzoDepositStorage.sol

2: pragma solidity 0.8.19;
3: 
4: import "./IxRenzoDeposit.sol";

7: import "./Oracle/IRenzoOracleL2.sol";
8: 
9: abstract contract xRenzoDepositStorageV1 is IxRenzoDeposit {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L2-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L7-L9)


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

2: pragma solidity 0.8.19;
3: 
4: import "./xRenzoDepositStorage.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L2-L4) 


```solidity

File: contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol

2: pragma solidity 0.8.19;
3: 
4: import { IXReceiver } from "@connext/interfaces/core/IXReceiver.sol";

08: import "../../../Errors/Errors.sol";
09: 
10: contract ConnextReceiver is IXReceiver, Ownable, Pausable {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L2-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L8-L10)


```solidity

File: contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol

2: pragma solidity 0.8.19;
3: 
4: import { Client } from "@chainlink/contracts-ccip/src/v0.8/ccip/libraries/Client.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L2-L4) 


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2.sol

2: pragma solidity 0.8.19;
3: 
4: import "./RenzoOracleL2Storage.sol";

09: import "../../../Errors/Errors.sol";
10: 
11: contract RenzoOracleL2 is Initializable, OwnableUpgradeable, RenzoOracleL2StorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L2-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L9-L11)


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2Storage.sol

2: pragma solidity 0.8.19;
3: 
4: import "./IRenzoOracleL2.sol";

5: import "@chainlink/contracts/src/v0.8/interfaces/AggregatorV3Interface.sol";
6: 
7: abstract contract RenzoOracleL2StorageV1 is IRenzoOracleL2 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2Storage.sol#L2-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2Storage.sol#L5-L7)


```solidity

File: contracts/Bridge/L1/xRenzoBridge.sol

2: pragma solidity 0.8.19;
3: 
4: import "./xRenzoBridgeStorage.sol";

14: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";
15: 
16: contract xRenzoBridge is


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L2-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L14-L16)


```solidity

File: contracts/Bridge/L1/xRenzoBridgeStorage.sol

2: pragma solidity 0.8.19;
3: 
4: import "./IxRenzoBridge.sol";

16: import { IRoleManager } from "../../Permissions/IRoleManager.sol";
17: 
18: abstract contract xRenzoBridgeStorageV1 is IxRenzoBridge {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridgeStorage.sol#L2-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridgeStorage.sol#L16-L18)


```solidity

File: contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol

2: pragma solidity ^0.8.13;
3: 
4: import { SafeERC20 } from "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";

7: import { IXERC20Lockbox } from "../../xERC20/interfaces/IXERC20Lockbox.sol";
8: 
9: interface IXERC20Registry {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L2-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L7-L9)


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol

2: pragma solidity >=0.8.4 <0.9.0;
3: 
4: import { IXERC20 } from "../interfaces/IXERC20.sol";

09: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";
10: 
11: contract XERC20Lockbox is Initializable, IXERC20Lockbox {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L2-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L9-L11)


</details>


### [NC&#x2011;65] Critical functions should be a two step procedure 
Critical functions in Solidity contracts should follow a two-step procedure to enhance security, minimize human error, and ensure proper access control. By dividing sensitive operations into distinct phases, such as initiation and confirmation, developers can introduce a safeguard against unintended actions or unauthorized access.


*There are 33 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Bridge/L2/Oracle/RenzoOracleL2.sol

36:     function setOracleAddress(AggregatorV3Interface _oracleAddress) external onlyOwner {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L36-L36) 


```solidity

File: contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol

96:     function updateXRenzoBridgeL1(address _newXRenzoBridgeL1) external onlyOwner {

107:     function updateCCIPEthChainSelector(uint64 _newChainSelector) external onlyOwner {

134:     function setRenzoDeposit(address _newXRenzoDeposit) external onlyOwner {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L96-L96) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L107-L107), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L134-L134)


```solidity

File: contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol

92:     function updateXRenzoBridgeL1(address _newXRenzoBridgeL1) external onlyOwner {

103:     function updateCCIPEthChainSelector(uint32 _newChainDomain) external onlyOwner {

130:     function setRenzoDeposit(address _newXRenzoDeposit) external onlyOwner {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L92-L92) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L103-L103), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L130-L130)


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

320:     function updatePriceByOwner(uint256 price) external onlyOwner {

466:     function setAllowedBridgeSweeper(address _sweeper, bool _allowed) external onlyOwner {

501:     function setOraclePriceFeed(IRenzoOracleL2 _oracle) external onlyOwner {

511:     function setReceiverPriceFeed(address _receiver) external onlyOwner {

521:     function updateBridgeFeeShare(uint256 _newShare) external onlyOwner {

532:     function updateSweepBatchSize(uint256 _newBatchSize) external onlyOwner {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L320-L320) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L466-L466), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L501-L501), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L511-L511), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L521-L521), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L532-L532)


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20.sol

135:     function setLimits(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L135-L135) 


```solidity

File: contracts/Delegation/OperatorDelegator.sol

106:     function setTokenStrategy(

117:     function setDelegateAddress(

132:     function setBaseGasAmountSpent(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L106-L106) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L117-L117), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L132-L132)


```solidity

File: contracts/Deposits/DepositQueue.sol

87:     function setWithdrawQueue(IWithdrawQueue _withdrawQueue) external onlyRestakeManagerAdmin {

93:     function setFeeConfig(

112:     function setRestakeManager(IRestakeManager _restakeManager) external onlyRestakeManagerAdmin {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L87-L87) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L93-L93), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L112-L112)


```solidity

File: contracts/Oracle/RenzoOracle.sol

54:     function setOracleAddress(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L54-L54) 


```solidity

File: contracts/RestakeManager.sol

121:     function setPaused(bool _paused) external onlyDepositWithdrawPauserAdmin {

131:     function addOperatorDelegator(

160:     function removeOperatorDelegator(

187:     function setOperatorDelegatorAllocation(

215:     function setMaxDepositTVL(uint256 _maxDepositTVL) external onlyRestakeManagerAdmin {

220:     function addCollateralToken(IERC20 _newCollateralToken) external onlyRestakeManagerAdmin {

244:     function removeCollateralToken(

709:     function setTokenTvlLimit(IERC20 _token, uint256 _limit) external onlyRestakeManagerAdmin {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L121-L121) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L131-L131), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L160-L160), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L187-L187), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L215-L215), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L220-L220), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L244-L244), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L709-L709)


```solidity

File: contracts/Rewards/RewardHandler.sol

72:     function setRewardDestination(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L72-L72) 


```solidity

File: contracts/Withdraw/WithdrawQueue.sol

106:     function updateWithdrawBufferTarget(

129:     function updateCoolDownPeriod(uint256 _newCoolDownPeriod) external onlyWithdrawQueueAdmin {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L106-L106) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L129-L129)


```solidity

File: contracts/token/EzEthToken.sol

51:     function setPaused(bool _paused) external onlyTokenAdmin {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L51-L51) 


</details>


### [NC&#x2011;66] Typos 
Modifiers in Solidity can improve code readability and modularity by encapsulating repetitive checks, such as address validity checks, into a reusable construct. For example, an `onlyOwner` modifier can be used to replace repetitive `require(msg.sender == owner)` checks across several functions, reducing code redundancy and enhancing maintainability. To implement, define a modifier with the check, then apply the modifier to relevant functions.


*There are 5 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Withdraw/WithdrawQueueStorage.sol

//@audit `mapiing` is misspelled
49:     /// @dev mapiing of withdraw requests array, indexed by user address


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueueStorage.sol#L49-L49) 


```solidity

File: contracts/Permissions/RoleManager.sol

//@audit `haas` is misspelled
96:     /// @dev Determine if the specified address haas permission to update Withdraw Queue params
97:     /// @param potentialAddress Address to check


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L96-L97) 


```solidity

File: contracts/Oracle/RenzoOracle.sol

//@audit `maxmimum` is misspelled
25:     /// @dev The maxmimum staleness allowed for a price feed from chainlink

//@audit `oracel` is misspelled
52:     /// @dev Sets addresses for oracle lookup.  Permission gated to oracel admins only.
53:     /// Set to address 0x0 to disable lookups for the token.


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L25-L25) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L52-L53)


```solidity

File: contracts/Deposits/DepositQueue.sol

//@audit `bufffer` is misspelled
147:     /**
148:      * @notice  accepts full withdrawal ETH from Operator Delegators
149:      * @notice  WARNING: users should not send ETH directly by this function
150:      * @dev     check and fill ETH withdraw bufffer if required
151:      */


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L147-L151) 


</details>


### [NC&#x2011;67] uint variables should have the bit size defined explicitly 
Instead of using uint to declare uint258, explicitly define uint258 to ensure there is no confusion


*There are 2 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Delegation/OperatorDelegator.sol

//@audit `nonce`
37:         uint nonce,

//@audit `startBlock`
38:         uint startBlock,


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L37-L37) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L38-L38)


</details>


### [NC&#x2011;68] Uncommented fields in a struct 
Consider adding comments for all the fields in a struct to improve the readability of the codebase.


*There are 4 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Withdraw/WithdrawQueueStorage.sol

//@audit Add explanational comments to the following items `asset`, `bufferAmount`, 
12:     struct TokenWithdrawBuffer {
13:         address asset;
14:         uint256 bufferAmount;
15:     }

//@audit Add explanational comments to the following items `collateralToken`, `withdrawRequestID`, `amountToRedeem`, `ezETHLocked`, `createdAt`, 
17:     struct WithdrawRequest {
18:         address collateralToken;
19:         uint256 withdrawRequestID;
20:         uint256 amountToRedeem;
21:         uint256 ezETHLocked;
22:         uint256 createdAt;
23:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueueStorage.sol#L12-L15) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueueStorage.sol#L17-L23)


```solidity

File: contracts/RestakeManagerStorage.sol

//@audit Add explanational comments to the following items `ezETHToBurn`, `withdrawer`, `tokenToWithdraw`, `tokenAmountToWithdraw`, `completed`, 
29:     struct PendingWithdrawal {
30:         uint256 ezETHToBurn;
31:         address withdrawer;
32:         IERC20 tokenToWithdraw;
33:         uint256 tokenAmountToWithdraw;
34:         IOperatorDelegator operatorDelegator;
35:         bool completed;
36:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManagerStorage.sol#L29-L36) 


```solidity

File: contracts/Bridge/Connext/libraries/TokenId.sol

//@audit Add explanational comments to the following items `domain`, `id`, 
09: struct TokenId {
10:     uint32 domain;
11:     bytes32 id;
12: }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/libraries/TokenId.sol#L9-L12) 


</details>


### [NC&#x2011;69] Event is missing `indexed` fields 
Index event fields make the field more quickly accessible to off-chain tools that parse events. However, note that each index field costs extra gas during emission, so it's not necessarily best to index the maximum allowed per event (three fields). Each event should use three indexed fields if there are three or more fields, and gas usage is not particularly of concern for the events in question. If there are fewer than three fields, all of the fields should be indexed.


*There are 60 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Withdraw/WithdrawQueue.sol

19:     event WithdrawBufferTargetUpdated(uint256 oldBufferTarget, uint256 newBufferTarget);

21:     event CoolDownPeriodUpdated(uint256 oldCoolDownPeriod, uint256 newCoolDownPeriod);

23:     event EthBufferFilled(uint256 amount);

25:     event ERC20BufferFilled(address asset, uint256 amount);

27:     event WithdrawRequestCreated(

36:     event WithdrawRequestClaimed(WithdrawRequest withdrawRequest);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L19-L19) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L21-L21), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L23-L23), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L25-L25), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L27-L27), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L36-L36)


```solidity

File: contracts/TimelockController.sol

38:     event CallScheduled(

51:     event CallExecuted(

62:     event CallSalt(bytes32 indexed id, bytes32 salt);

72:     event MinDelayChange(uint256 oldDuration, uint256 newDuration);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L38-L38) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L51-L51), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L62-L62), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L72-L72)


```solidity

File: contracts/Rewards/RewardHandler.sol

29:     event RewardDestinationUpdated(address rewardDestination);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L29-L29) 


```solidity

File: contracts/RestakeManager.sol

30:     event OperatorDelegatorAdded(IOperatorDelegator od);

31:     event OperatorDelegatorRemoved(IOperatorDelegator od);

32:     event OperatorDelegatorAllocationUpdated(IOperatorDelegator od, uint256 allocation);

34:     event CollateralTokenAdded(IERC20 token);

35:     event CollateralTokenRemoved(IERC20 token);

41:     event Deposit(

50:     event UserWithdrawStarted(

59:     event UserWithdrawCompleted(

68:     event CollateralTokenTvlUpdated(IERC20 token, uint256 tvl);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L30-L30) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L31-L31), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L32-L32), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L34-L34), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L35-L35), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L41-L41), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L50-L50), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L59-L59), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L68-L68)


```solidity

File: contracts/Oracle/RenzoOracle.sol

35:     event OracleAddressUpdated(IERC20 token, AggregatorV3Interface oracleAddress);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L35-L35) 


```solidity

File: contracts/Deposits/DepositQueue.sol

15:     event RewardsDeposited(IERC20 token, uint256 amount);

17:     event FeeConfigUpdated(address feeAddress, uint256 feeBasisPoints);

19:     event RestakeManagerUpdated(IRestakeManager restakeManager);

21:     event ETHDepositedFromProtocol(uint256 amount);

23:     event ETHStakedFromQueue(

30:     event ProtocolFeesPaid(IERC20 token, uint256 amount, address destination);

32:     event GasRefunded(address admin, uint256 gasRefunded);

35:     event WithdrawQueueUpdated(address oldWithdrawQueue, address newWithdrawQueue);

38:     event BufferFilled(address token, uint256 amount);

41:     event FullWithdrawalETHReceived(uint256 amount);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L15-L15) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L17-L17), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L19-L19), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L21-L21), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L23-L23), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L30-L30), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L32-L32), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L35-L35), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L38-L38), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L41-L41)


```solidity

File: contracts/Delegation/OperatorDelegator.sol

28:     event TokenStrategyUpdated(IERC20 token, IStrategy strategy);

29:     event DelegationAddressUpdated(address delegateAddress);

30:     event RewardsForwarded(address rewardDestination, uint256 amount);

32:     event WithdrawStarted(

43:     event WithdrawCompleted(bytes32 withdrawalRoot, IStrategy[] strategies, uint256[] shares);

45:     event GasSpent(address admin, uint256 gasSpent);

46:     event GasRefunded(address admin, uint256 gasRefunded);

47:     event BaseGasAmountSpentUpdated(uint256 oldBaseGasAmountSpent, uint256 newBaseGasAmountSpent);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L28-L28) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L29-L29), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L30-L30), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L32-L32), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L43-L43), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L45-L45), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L46-L46), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L47-L47)


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

42:     event PriceUpdated(uint256 price, uint256 timestamp);

43:     event Deposit(address indexed user, uint256 amountIn, uint256 amountOut);

44:     event BridgeSweeperAddressUpdated(address sweeper, bool allowed);

45:     event BridgeSwept(

51:     event OraclePriceFeedUpdated(address newOracle, address oldOracle);

52:     event ReceiverPriceFeedUpdated(address newReceiver, address oldReceiver);

53:     event SweeperBridgeFeeCollected(address sweeper, uint256 feeCollected);

54:     event BridgeFeeShareUpdated(uint256 oldBridgeFeeShare, uint256 newBridgeFeeShare);

55:     event SweepBatchSizeUpdated(uint256 oldSweepBatchSize, uint256 newSweepBatchSize);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L42-L42) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L43-L43), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L44-L44), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L45-L45), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L51-L51), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L52-L52), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L53-L53), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L54-L54), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L55-L55)


```solidity

File: contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol

23:     event XRenzoBridgeL1Updated(address newBridgeAddress, address oldBridgeAddress);

24:     event ConnextEthChainDomainUpdated(uint32 newSourceChainDomain, uint32 oldSourceChainDomain);

25:     event XRenzoDepositUpdated(address newRenzoDeposit, address oldRenzoDeposit);

35:     event MessageReceived(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L23-L23) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L24-L24), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L25-L25), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L35-L35)


```solidity

File: contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol

24:     event XRenzoBridgeL1Updated(address newBridgeAddress, address oldBridgeAddress);

25:     event CCIPEthChainSelectorUpdated(uint64 newSourceChainSelector, uint64 oldSourceChainSelector);

26:     event XRenzoDepositUpdated(address newRenzoDeposit, address oldRenzoDeposit);

35:     event MessageReceived(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L24-L24) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L25-L25), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L26-L26), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L35-L35)


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2.sol

15:     event OracleAddressUpdated(address newOracle, address oldOracle);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L15-L15) 


```solidity

File: contracts/Bridge/L1/xRenzoBridge.sol

25:     event EzETHMinted(

34:     event MessageSent(

43:     event ConnextMessageSent(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L25-L25) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L34-L34), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L43-L43)


</details>


### [NC&#x2011;70] Unused `error` definition 
Note that there may be cases where an error superficially appears to be used, but this is only because there are multiple definitions of the error in different files. In such cases, the error definition should be moved into a separate file. The instances below are the unused definitions.


*There are 3 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Errors/Errors.sol

32: error WithdrawAlreadyCompleted();

35: error NotOriginalWithdrawCaller(address expectedCaller);

98: error InvalidOrigin();


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L32-L32) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L35-L35), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L98-L98)


</details>


### [NC&#x2011;71] Unused `event` definition 
The following events are never used, consider to remove them.


*There are 2 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/RestakeManager.sol

//@audit UserWithdrawStarted is never used
50:     event UserWithdrawStarted(

//@audit UserWithdrawCompleted is never used
59:     event UserWithdrawCompleted(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L50-L50) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L59-L59)


</details>


### [NC&#x2011;72] Unused Import 
Some files/Items are imported but never used


*There are 25 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/token/EzEthToken.sol

//@audit `Errors` is not used
9: import "../Errors/Errors.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L9-L9) 


```solidity

File: contracts/Withdraw/WithdrawQueue.sol

//@audit `Errors` is not used
5: import "../Errors/Errors.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L5-L5) 


```solidity

File: contracts/Rewards/RewardHandler.sol

//@audit `Errors` is not used
7: import "../Errors/Errors.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L7-L7) 


```solidity

File: contracts/RestakeManagerStorage.sol

//@audit `IWithdrawQueue` is not used
13: import "./Withdraw/IWithdrawQueue.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManagerStorage.sol#L13-L13) 


```solidity

File: contracts/RestakeManager.sol

//@audit `IERC20Upgradeable` is not used
8: import "@openzeppelin/contracts-upgradeable/token/ERC20/IERC20Upgradeable.sol";

//@audit `IRestakeManager` is not used
16: import "./IRestakeManager.sol";

//@audit `Errors` is not used
17: import "./Errors/Errors.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L8-L8) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L16-L16), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L17-L17)


```solidity

File: contracts/RateProvider/BalancerRateProvider.sol

//@audit `Errors` is not used
6: import "../Errors/Errors.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProvider.sol#L6-L6) 


```solidity

File: contracts/Permissions/RoleManager.sol

//@audit `Errors` is not used
7: import "../Errors/Errors.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L7-L7) 


```solidity

File: contracts/Oracle/RenzoOracle.sol

//@audit `Errors` is not used
8: import "../Errors/Errors.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L8-L8) 


```solidity

File: contracts/Oracle/Mantle/METHShim.sol

//@audit `ReentrancyGuardUpgradeable` is not used
4: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";

//@audit `Errors` is not used
7: import "../../Errors/Errors.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L4-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L7-L7)


```solidity

File: contracts/Oracle/Binance/WBETHShim.sol

//@audit `ReentrancyGuardUpgradeable` is not used
4: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";

//@audit `Errors` is not used
7: import "../../Errors/Errors.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L4-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L7-L7)


```solidity

File: contracts/Deposits/DepositQueue.sol

//@audit `Errors` is not used
8: import "../Errors/Errors.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L8-L8) 


```solidity

File: contracts/Delegation/OperatorDelegator.sol

//@audit `Errors` is not used
10: import "../Errors/Errors.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L10-L10) 


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol

//@audit `XERC20Lockbox` is not used
6: import { XERC20Lockbox } from "../XERC20Lockbox.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L6-L6) 


```solidity

File: contracts/Bridge/L2/xRenzoDepositStorage.sol

//@audit `SafeERC20` is not used
5: import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L5-L5) 


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

//@audit `Errors` is not used
12: import "../../Errors/Errors.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L12-L12) 


```solidity

File: contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol

//@audit `Errors` is not used
8: import "../../../Errors/Errors.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L8-L8) 


```solidity

File: contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol

//@audit `Errors` is not used
11: import "../../../Errors/Errors.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L11-L11) 


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2.sol

//@audit `Errors` is not used
9: import "../../../Errors/Errors.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L9-L9) 


```solidity

File: contracts/Bridge/L1/xRenzoBridge.sol

//@audit `Errors` is not used
6: import "../../Errors/Errors.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L6-L6) 


```solidity

File: contracts/Bridge/L1/xRenzoBridgeStorage.sol

//@audit `SafeERC20` is not used
5: import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridgeStorage.sol#L5-L5) 


```solidity

File: contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol

//@audit `IXERC20` is not used
6: import { IXERC20 } from "../../xERC20/interfaces/IXERC20.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L6-L6) 


</details>


### [NC&#x2011;73] Unused `internal`/`private` contract variable 
If these serve no purpose, they should be safely removed


*There are 1 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Oracle/RenzoOracle.sol

//@audit the variable `INVALID_0_INPUT` is declared but never used
20:     string constant INVALID_0_INPUT = "Invalid 0 input";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L20-L20) 


</details>


### [NC&#x2011;74] Missing upgradability functionality 
At the begining of a project, there is always the need to modify of add something to the source code especialy if any vulnerability is discovered. Therefore, having such system is crusial at least at the first stages of the project


*There are 1 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/token/EzEthTokenStorage.sol

10: contract EzEthTokenStorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthTokenStorage.sol#L10-L10) 


</details>


### [NC&#x2011;75] Constants should be defined rather than using magic numbers 
Even [assembly](https://github.com/code-423n4/2022-05-opensea-seaport/blob/9d7ce4d08bf3c3010304a0476a785c70c0e90ae7/contracts/lib/TokenTransferrer.sol#L35-L39) can benefit from using readable constants instead of hex/numeric literals


*There are 32 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/RestakeManager.sol

//@audit Try to make a `constant` with `100` value
146:         if (_allocationBasisPoints > (100 * BASIS_POINTS)) revert OverMaxBasisPoints();

//@audit Try to make a `constant` with `100` value
192:         if (_allocationBasisPoints > (100 * BASIS_POINTS)) revert OverMaxBasisPoints();

//@audit Try to make a `constant` with `18` value
231:         if (IERC20Metadata(address(_newCollateralToken)).decimals() != 18)

//@audit Try to make a `constant` with `18` value
233:                 18,


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L146-L146) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L192-L192), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L231-L231), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L233-L233)


```solidity

File: contracts/RateProvider/BalancerRateProvider.sol

//@audit Try to make a `constant` with `10` value
40:         return (10 ** 18 * totalTVL) / totalSupply;

//@audit Try to make a `constant` with `18` value
40:         return (10 ** 18 * totalTVL) / totalSupply;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProvider.sol#L40-L40) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProvider.sol#L40-L40)


```solidity

File: contracts/Oracle/RenzoOracle.sol

//@audit Try to make a `constant` with `18` value
61:         if (_oracleAddress.decimals() != 18)

//@audit Try to make a `constant` with `18` value
62:             revert InvalidTokenDecimals(18, _oracleAddress.decimals());


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L61-L61) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L62-L62)


```solidity

File: contracts/Oracle/Mantle/METHShim.sol

//@audit Try to make a `constant` with `18` value
30:         return 18;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L30-L30) 


```solidity

File: contracts/Oracle/Binance/WBETHShim.sol

//@audit Try to make a `constant` with `18` value
30:         return 18;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L30-L30) 


```solidity

File: contracts/Deposits/DepositQueue.sol

//@audit Try to make a `constant` with `10000` value
103:         if (_feeBasisPoints > 10000) revert OverMaxBasisPoints();

//@audit Try to make a `constant` with `10000` value
167:             feeAmount = (msg.value * feeBasisPoints) / 10000;

//@audit Try to make a `constant` with `32` value
202:         emit ETHStakedFromQueue(operatorDelegator, pubkey, 32 ether, address(this).balance);

//@audit Try to make a `constant` with `32` value
195:         restakeManager.stakeEthInOperatorDelegator{ value: 32 ether }(

//@audit Try to make a `constant` with `32` value
239:                 32 ether,

//@audit Try to make a `constant` with `32` value
229:             restakeManager.stakeEthInOperatorDelegator{ value: 32 ether }(

//@audit Try to make a `constant` with `10000` value
261:                 feeAmount = (balance * feeBasisPoints) / 10000;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L103-L103) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L167-L167), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L202-L202), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L195-L195), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L239-L239), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L229-L229), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L261-L261)


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

//@audit Try to make a `constant` with `5` value
140:         bridgeRouterFeeBps = 5;

//@audit Try to make a `constant` with `5` value
152:         bridgeFeeShare = 5;

//@audit Try to make a `constant` with `32` value
155:         sweepBatchSize = 32 ether;

//@audit Try to make a `constant` with `10` value
338:             (_price > lastPrice && (_price - lastPrice) > (lastPrice / 10)) ||

//@audit Try to make a `constant` with `10` value
339:             (_price < lastPrice && (lastPrice - _price) > (lastPrice / 10))

//@audit Try to make a `constant` with `10_000` value
386:             uint256 fee = (amountNextWETH * bridgeRouterFeeBps) / 10_000;

//@audit Try to make a `constant` with `100` value
522:         if (_newShare > 100) revert InvalidBridgeFeeShare(_newShare);

//@audit Try to make a `constant` with `32` value
533:         if (_newBatchSize < 32 ether) revert InvalidSweepBatchSize(_newBatchSize);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L140-L140) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L152-L152), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L155-L155), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L338-L338), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L339-L339), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L386-L386), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L522-L522), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L533-L533)


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2.sol

//@audit Try to make a `constant` with `18` value
30:         if (_oracle.decimals() > 18) revert InvalidTokenDecimals(18, _oracle.decimals());

//@audit Try to make a `constant` with `18` value
30:         if (_oracle.decimals() > 18) revert InvalidTokenDecimals(18, _oracle.decimals());

//@audit Try to make a `constant` with `18` value
39:         if (_oracleAddress.decimals() > 18)

//@audit Try to make a `constant` with `18` value
40:             revert InvalidTokenDecimals(18, _oracleAddress.decimals());

//@audit Try to make a `constant` with `10` value
54:         uint256 _scaledPrice = (uint256(price)) * 10 ** (18 - oracle.decimals());

//@audit Try to make a `constant` with `18` value
54:         uint256 _scaledPrice = (uint256(price)) * 10 ** (18 - oracle.decimals());


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L30-L30) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L30-L30), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L39-L39), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L40-L40), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L54-L54), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L54-L54)


```solidity

File: contracts/Bridge/L1/xRenzoBridge.sol

//@audit Try to make a `constant` with `200_000` value
225:                     Client.EVMExtraArgsV1({ gasLimit: 200_000 })


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L225-L225) 


</details>


### [NC&#x2011;76] Use `@inheritdoc` rather than using a non-standard annotation 



*There are 4 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/TimelockController.sol

140:      * @dev See {IERC165-supportsInterface}.

409:      * @dev See {IERC721Receiver-onERC721Received}.

421:      * @dev See {IERC1155Receiver-onERC1155Received}.

434:      * @dev See {IERC1155Receiver-onERC1155BatchReceived}.


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L140-L140) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L409-L409), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L421-L421), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L434-L434)


</details>


### [NC&#x2011;77] Use the latest solidity (prior to 0.8.20 if on L2s) for deployment 
```
When deploying contracts, you should use the latest released version of Solidity.Apart from exceptional cases, only the latest version receives security fixes.
```
https://docs.soliditylang.org/en/v0.8.20/


*There are 35 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/token/EzEthTokenStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthTokenStorage.sol#L2-L2) 


```solidity

File: contracts/token/EzEthToken.sol

2: pragma solidity ^0.8.9;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L2-L2) 


```solidity

File: contracts/Withdraw/WithdrawQueue.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L2-L2) 


```solidity

File: contracts/Withdraw/WithdrawQueueStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueueStorage.sol#L2-L2) 


```solidity

File: contracts/TimelockController.sol

4: pragma solidity ^0.8.0;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L4-L4) 


```solidity

File: contracts/Rewards/RewardHandlerStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandlerStorage.sol#L2-L2) 


```solidity

File: contracts/Rewards/RewardHandler.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L2-L2) 


```solidity

File: contracts/RestakeManagerStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManagerStorage.sol#L2-L2) 


```solidity

File: contracts/RestakeManager.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L2-L2) 


```solidity

File: contracts/RateProvider/BalancerRateProvider.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProvider.sol#L2-L2) 


```solidity

File: contracts/RateProvider/BalancerRateProviderStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProviderStorage.sol#L2-L2) 


```solidity

File: contracts/Permissions/RoleManager.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L2-L2) 


```solidity

File: contracts/Permissions/RoleManagerStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManagerStorage.sol#L2-L2) 


```solidity

File: contracts/Oracle/RenzoOracle.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L2-L2) 


```solidity

File: contracts/Oracle/RenzoOracleStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracleStorage.sol#L2-L2) 


```solidity

File: contracts/Oracle/Mantle/METHShim.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L2-L2) 


```solidity

File: contracts/Oracle/Mantle/METHShimStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShimStorage.sol#L2-L2) 


```solidity

File: contracts/Oracle/Binance/WBETHShimStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShimStorage.sol#L2-L2) 


```solidity

File: contracts/Oracle/Binance/WBETHShim.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L2-L2) 


```solidity

File: contracts/Errors/Errors.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L2-L2) 


```solidity

File: contracts/Deposits/DepositQueueStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueueStorage.sol#L2-L2) 


```solidity

File: contracts/Deposits/DepositQueue.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L2-L2) 


```solidity

File: contracts/Delegation/OperatorDelegator.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L2-L2) 


```solidity

File: contracts/Delegation/OperatorDelegatorStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegatorStorage.sol#L2-L2) 


```solidity

File: contracts/Bridge/L2/xRenzoDepositStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L2-L2) 


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L2-L2) 


```solidity

File: contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L2-L2) 


```solidity

File: contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L2-L2) 


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L2-L2) 


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2Storage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2Storage.sol#L2-L2) 


```solidity

File: contracts/Bridge/L1/xRenzoBridge.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L2-L2) 


```solidity

File: contracts/Bridge/L1/xRenzoBridgeStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridgeStorage.sol#L2-L2) 


```solidity

File: contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol

2: pragma solidity ^0.8.13;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L2-L2) 


```solidity

File: contracts/Bridge/Connext/libraries/LibConnextStorage.sol

2: pragma solidity ^0.8.0;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/libraries/LibConnextStorage.sol#L2-L2) 


```solidity

File: contracts/Bridge/Connext/libraries/TokenId.sol

2: pragma solidity ^0.8.0;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/libraries/TokenId.sol#L2-L2) 


</details>


### [NC&#x2011;78] Use a single file for system wide constants 
Consider grouping all the system constants under a single file. This finding shows only the first constant for each file.


*There are 11 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Withdraw/WithdrawQueueStorage.sol

10:     address public constant IS_NATIVE = 0xEeeeeEeeeEeEeeEeEeEeeEEEeeeeEeeeeeeeEEeE;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueueStorage.sol#L10-L10) 


```solidity

File: contracts/TimelockController.sol

26:     bytes32 public constant TIMELOCK_ADMIN_ROLE = keccak256("TIMELOCK_ADMIN_ROLE");


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L26-L26) 


```solidity

File: contracts/RestakeManager.sol

38:     uint256 constant BASIS_POINTS = 100;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L38-L38) 


```solidity

File: contracts/Permissions/RoleManagerStorage.sol

11:     bytes32 public constant RX_ETH_MINTER_BURNER = keccak256("RX_ETH_MINTER_BURNER");


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManagerStorage.sol#L11-L11) 


```solidity

File: contracts/Oracle/RenzoOracle.sol

20:     string constant INVALID_0_INPUT = "Invalid 0 input";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L20-L20) 


```solidity

File: contracts/Deposits/DepositQueue.sol

13:     address public constant IS_NATIVE = 0xEeeeeEeeeEeEeeEeEeEeeEEEeeeeEeeeeeeeEEeE;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L13-L13) 


```solidity

File: contracts/Delegation/OperatorDelegator.sol

24:     uint256 internal constant GWEI_TO_WEI = 1e9;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L24-L24) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20.sol

26:     uint256 private constant _DURATION = 1 days;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L26-L26) 


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

37:     uint8 public constant EXPECTED_DECIMALS = 18;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L37-L37) 


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2.sol

13:     uint256 public constant MAX_TIME_WINDOW = 86400 + 60; // 24 hours + 60 seconds


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L13-L13) 


```solidity

File: contracts/Bridge/L1/xRenzoBridge.sol

61:     uint8 public constant EXPECTED_DECIMALS = 18;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L61-L61) 


</details>


### [NC&#x2011;79] Consider using SMTChecker 
The SMTChecker is a valuable tool for Solidity developers as it helps detect potential vulnerabilities and logical errors in the contract's code. By utilizing Satisfiability Modulo Theories (SMT) solvers, it can reason about the potential states a contract can be in, and therefore, identify conditions that could lead to undesirable behavior. This automatic formal verification can catch issues that might otherwise be missed in manual code reviews or standard testing, enhancing the overall contract's security and reliability.


*There are 40 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/token/EzEthTokenStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthTokenStorage.sol#L2-L2) 


```solidity

File: contracts/token/EzEthToken.sol

2: pragma solidity ^0.8.9;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L2-L2) 


```solidity

File: contracts/Withdraw/WithdrawQueue.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L2-L2) 


```solidity

File: contracts/Withdraw/WithdrawQueueStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueueStorage.sol#L2-L2) 


```solidity

File: contracts/TimelockController.sol

4: pragma solidity ^0.8.0;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L4-L4) 


```solidity

File: contracts/Rewards/RewardHandlerStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandlerStorage.sol#L2-L2) 


```solidity

File: contracts/Rewards/RewardHandler.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L2-L2) 


```solidity

File: contracts/RestakeManagerStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManagerStorage.sol#L2-L2) 


```solidity

File: contracts/RestakeManager.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L2-L2) 


```solidity

File: contracts/RateProvider/BalancerRateProvider.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProvider.sol#L2-L2) 


```solidity

File: contracts/RateProvider/BalancerRateProviderStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProviderStorage.sol#L2-L2) 


```solidity

File: contracts/Permissions/RoleManager.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L2-L2) 


```solidity

File: contracts/Permissions/RoleManagerStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManagerStorage.sol#L2-L2) 


```solidity

File: contracts/Oracle/RenzoOracle.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L2-L2) 


```solidity

File: contracts/Oracle/RenzoOracleStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracleStorage.sol#L2-L2) 


```solidity

File: contracts/Oracle/Mantle/METHShim.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L2-L2) 


```solidity

File: contracts/Oracle/Mantle/METHShimStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShimStorage.sol#L2-L2) 


```solidity

File: contracts/Oracle/Binance/WBETHShimStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShimStorage.sol#L2-L2) 


```solidity

File: contracts/Oracle/Binance/WBETHShim.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L2-L2) 


```solidity

File: contracts/Errors/Errors.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L2-L2) 


```solidity

File: contracts/Deposits/DepositQueueStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueueStorage.sol#L2-L2) 


```solidity

File: contracts/Deposits/DepositQueue.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L2-L2) 


```solidity

File: contracts/Delegation/OperatorDelegator.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L2-L2) 


```solidity

File: contracts/Delegation/OperatorDelegatorStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegatorStorage.sol#L2-L2) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20.sol

2: pragma solidity >=0.8.4 <0.9.0;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L2-L2) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Factory.sol

2: pragma solidity >=0.8.4 <0.9.0;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L2-L2) 


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol

2: pragma solidity >=0.8.4 <0.9.0;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L2-L2) 


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol

2: pragma solidity >=0.8.4 <0.9.0;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L2-L2) 


```solidity

File: contracts/Bridge/L2/xRenzoDepositStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L2-L2) 


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L2-L2) 


```solidity

File: contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L2-L2) 


```solidity

File: contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L2-L2) 


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L2-L2) 


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2Storage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2Storage.sol#L2-L2) 


```solidity

File: contracts/Bridge/L1/xRenzoBridge.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L2-L2) 


```solidity

File: contracts/Bridge/L1/xRenzoBridgeStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridgeStorage.sol#L2-L2) 


```solidity

File: contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol

2: pragma solidity ^0.8.13;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L2-L2) 


```solidity

File: contracts/Bridge/Connext/libraries/LibConnextStorage.sol

2: pragma solidity ^0.8.0;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/libraries/LibConnextStorage.sol#L2-L2) 


```solidity

File: contracts/Bridge/Connext/libraries/TokenId.sol

2: pragma solidity ^0.8.0;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/libraries/TokenId.sol#L2-L2) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol

2: pragma solidity >=0.8.4 <0.9.0;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L2-L2) 


</details>


### [NC&#x2011;80] Variable name must be in mixedCase 
Avoid using underscore for variable Names or parameters


*There are 1 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol

// @audit IS_NATIVE
29:     bool public IS_NATIVE;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L29-L29) 


</details>


### [NC&#x2011;81] Whitespace in Expressions 
See the [Whitespace in Expressions](https://docs.soliditylang.org/en/latest/style-guide.html#whitespace-in-expressions) section of the Solidity Style Guide


*There are 40 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Withdraw/WithdrawQueue.sol

//@audit remove the whiteSpace before the ')' char
88:         for (uint256 i = 0; i < _withdrawalBufferTarget.length; ) {
89:             if (

//@audit remove the whiteSpace before the ')' char
110:         for (uint256 i = 0; i < _newBufferTarget.length; ) {
111:             if (_newBufferTarget[i].asset == address(0) || _newBufferTarget[i].bufferAmount == 0)

//@audit remove the whiteSpace before the ',' char
217:         (, , uint256 totalTVL) = restakeManager.calculateTVLs();
218: 


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L88-L89) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L110-L111), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L217-L218)


```solidity

File: contracts/TimelockController.sol

//@audit remove the whiteSpace before the ')' char
369:         (bool success, ) = target.call{ value: value }(data);
370:         require(success, "TimelockController: underlying transaction reverted");


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L369-L370) 


```solidity

File: contracts/Rewards/RewardHandler.sol

//@audit remove the whiteSpace before the ')' char
68:         (bool success, ) = rewardDestination.call{ value: balance }("");
69:         if (!success) revert TransferFailed();


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L68-L69) 


```solidity

File: contracts/RestakeManager.sol

//@audit remove the whiteSpace before the ')' char
137:         for (uint256 i = 0; i < odLength; ) {
138:             if (address(operatorDelegators[i]) == address(_newOperatorDelegator))

//@audit remove the whiteSpace before the ')' char
165:         for (uint256 i = 0; i < odLength; ) {
166:             if (address(operatorDelegators[i]) == address(_operatorDelegatorToRemove)) {

//@audit remove the whiteSpace before the ')' char
197:         for (uint256 i = 0; i < odLength; ) {
198:             if (address(operatorDelegators[i]) == address(_operatorDelegator)) {

//@audit remove the whiteSpace before the ')' char
223:         for (uint256 i = 0; i < tokenLength; ) {
224:             if (address(collateralTokens[i]) == address(_newCollateralToken)) revert AlreadyAdded();

//@audit remove the whiteSpace before the ')' char
249:         for (uint256 i = 0; i < tokenLength; ) {
250:             if (address(collateralTokens[i]) == address(_collateralTokenToRemove)) {

//@audit remove the whiteSpace before the ')' char
289:         for (uint256 i = 0; i < odLength; ) {
290:             // Track the TVL for this OD

//@audit remove the whiteSpace before the ')' char
299:             for (uint256 j = 0; j < tokenLength; ) {
300:                 // Get the value of this token

//@audit remove the whiteSpace before the ')' char
376:         for (uint256 i = 0; i < tvlLength; ) {
377:             if (

//@audit remove the whiteSpace before the ')' char
418:         for (uint256 i = 0; i < odLength; ) {
419:             if (

//@audit remove the whiteSpace before the ')' char
435:         for (uint256 i = 0; i < odLength; ) {
436:             if (operatorDelegatorTokenTVLs[i][tokenIndex] >= ezETHValue) {

//@audit remove the whiteSpace before the ')' char
454:         for (uint256 i = 0; i < tokenLength; ) {
455:             if (collateralTokens[i] == _collateralToken) {

//@audit remove the whiteSpace before the ')' char
521:             for (uint256 i = 0; i < odLength; ) {
522:                 currentTokenTVL += operatorDelegatorTokenTVLs[i][tokenIndex];

//@audit remove the whiteSpace before the ',' char
594:         (, , uint256 totalTVL) = calculateTVLs();
595: 

//@audit remove the whiteSpace before the ')' char
629:         for (uint256 i = 0; i < odLength; ) {
630:             if (operatorDelegators[i] == operatorDelegator) {

//@audit remove the whiteSpace before the ')' char
683:         for (uint256 i = 0; i < tokenLength; ) {
684:             // Get the amount

//@audit remove the whiteSpace before the ')' char
699:         for (uint256 i = 0; i < odLength; ) {
700:             totalRewards += address(operatorDelegators[i].eigenPod()).balance;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L137-L138) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L165-L166), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L197-L198), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L223-L224), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L249-L250), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L289-L290), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L299-L300), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L376-L377), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L418-L419), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L435-L436), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L454-L455), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L521-L522), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L594-L595), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L629-L630), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L683-L684), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L699-L700)


```solidity

File: contracts/RateProvider/BalancerRateProvider.sol

//@audit remove the whiteSpace before the ',' char
31:         (, , uint256 totalTVL) = restakeManager.calculateTVLs();
32: 


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProvider.sol#L31-L32) 


```solidity

File: contracts/Oracle/RenzoOracle.sol

//@audit remove the whiteSpace before the ')' char
75:         (, int256 price, , uint256 timestamp, ) = oracle.latestRoundData();
76:         if (timestamp < block.timestamp - MAX_TIME_WINDOW) revert OraclePriceExpired();

//@audit remove the whiteSpace before the ',' char
75:         (, int256 price, , uint256 timestamp, ) = oracle.latestRoundData();
76:         if (timestamp < block.timestamp - MAX_TIME_WINDOW) revert OraclePriceExpired();

//@audit remove the whiteSpace before the ')' char
92:         (, int256 price, , uint256 timestamp, ) = oracle.latestRoundData();
93:         if (timestamp < block.timestamp - MAX_TIME_WINDOW) revert OraclePriceExpired();

//@audit remove the whiteSpace before the ',' char
92:         (, int256 price, , uint256 timestamp, ) = oracle.latestRoundData();
93:         if (timestamp < block.timestamp - MAX_TIME_WINDOW) revert OraclePriceExpired();

//@audit remove the whiteSpace before the ')' char
111:         for (uint256 i = 0; i < tokenLength; ) {
112:             totalValue += lookupTokenValue(_tokens[i], _balances[i]);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L75-L76) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L75-L76), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L92-L93), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L92-L93), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L111-L112)


```solidity

File: contracts/Deposits/DepositQueue.sol

//@audit remove the whiteSpace before the ')' char
168:             (bool success, ) = feeAddress.call{ value: feeAmount }("");
169:             if (!success) revert TransferFailed();

//@audit remove the whiteSpace before the ')' char
227:         for (uint256 i = 0; i < arrayLength; ) {
228:             // Send the ETH and the params through to the restake manager

//@audit remove the whiteSpace before the ')' char
286:         (bool success, ) = payable(msg.sender).call{ value: gasRefund }("");
287:         if (!success) revert TransferFailed();


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L168-L169) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L227-L228), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L286-L287)


```solidity

File: contracts/Delegation/OperatorDelegator.sol

//@audit remove the whiteSpace before the ')' char
209:         for (uint256 i; i < tokens.length; ) {
210:             if (address(tokens[i]) == IS_NATIVE) {

//@audit remove the whiteSpace before the ')' char
277:         for (uint256 i; i < tokens.length; ) {
278:             if (address(tokens[i]) == address(0)) revert InvalidZeroInput();

//@audit remove the whiteSpace before the ')' char
381:         for (uint256 i = 0; i < validatorFields.length; ) {
382:             uint64 validatorCurrentBalanceGwei = BeaconChainProofs.getEffectiveBalanceGwei(

//@audit remove the whiteSpace before the ')' char
520:             (bool success, ) = destination.call{ value: remainingAmount }("");
521:             if (!success) revert TransferFailed();


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L209-L210) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L277-L278), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L381-L382), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L520-L521)


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

//@audit remove the whiteSpace before the ')' char
403:         (bool success, ) = payable(msg.sender).call{ value: feeCollected }("");
404:         if (!success) revert TransferFailed();


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L403-L404) 


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2.sol

//@audit remove the whiteSpace before the ')' char
51:         (, int256 price, , uint256 timestamp, ) = oracle.latestRoundData();
52:         if (timestamp < block.timestamp - MAX_TIME_WINDOW) revert OraclePriceExpired();

//@audit remove the whiteSpace before the ',' char
51:         (, int256 price, , uint256 timestamp, ) = oracle.latestRoundData();
52:         if (timestamp < block.timestamp - MAX_TIME_WINDOW) revert OraclePriceExpired();


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L51-L52) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L51-L52)


```solidity

File: contracts/Bridge/L1/xRenzoBridge.sol

//@audit remove the whiteSpace before the ')' char
218:         for (uint256 i = 0; i < _destinationParam.length; ) {
219:             Client.EVM2AnyMessage memory evm2AnyMessage = Client.EVM2AnyMessage({

//@audit remove the whiteSpace before the ')' char
264:         for (uint256 i = 0; i < _connextDestinationParam.length; ) {
265:             connext.xcall{ value: _connextDestinationParam[i].relayerFee }(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L218-L219) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L264-L265)


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol

//@audit remove the whiteSpace before the ')' char
131:             (bool _success, ) = payable(_to).call{ value: _amount }("");
132:             if (!_success) revert IXERC20Lockbox_WithdrawFailed();


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L131-L132) 


</details>


### [NC&#x2011;82] Complex function controle flow 
Due to multiple if, loop and conditions the following functions has a very complex controle flow that could make auditing very difficult to cover all possible path\nTherefore, consider breaking down these blocks into more manageable units, by splitting things into utility functions, by reducing nesting, and by using early returns


*There are 1 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Delegation/OperatorDelegator.sol

265:     function completeQueuedWithdrawal(
266:         IDelegationManager.Withdrawal calldata withdrawal,
267:         IERC20[] calldata tokens,
268:         uint256 middlewareTimesIndex
269:     ) external nonReentrant onlyNativeEthRestakeAdmin {
270:         uint256 gasBefore = gasleft();
271:         if (tokens.length != withdrawal.strategies.length) revert MismatchedArrayLengths();
272: 
273:         // complete the queued withdrawal from EigenLayer with receiveAsToken set to true
274:         delegationManager.completeQueuedWithdrawal(withdrawal, tokens, middlewareTimesIndex, true);
275: 
276:         IWithdrawQueue withdrawQueue = restakeManager.depositQueue().withdrawQueue();
277:         for (uint256 i; i < tokens.length; ) {
278:             if (address(tokens[i]) == address(0)) revert InvalidZeroInput();
279: 
280:             // deduct queued shares for tracking TVL
281:             queuedShares[address(tokens[i])] -= withdrawal.shares[i];
282: 
283:             // check if token is not Native ETH
284:             if (address(tokens[i]) != IS_NATIVE) {
285:                 // Check the withdraw buffer and fill if below buffer target
286:                 uint256 bufferToFill = withdrawQueue.getBufferDeficit(address(tokens[i]));
287: 
288:                 // get balance of this contract
289:                 uint256 balanceOfToken = tokens[i].balanceOf(address(this));
290:                 if (bufferToFill > 0) {
291:                     bufferToFill = (balanceOfToken <= bufferToFill) ? balanceOfToken : bufferToFill;
292: 
293:                     // update amount to send to the operator Delegator
294:                     balanceOfToken -= bufferToFill;
295: 
296:                     // safe Approve for depositQueue
297:                     tokens[i].safeApprove(address(restakeManager.depositQueue()), bufferToFill);
298: 
299:                     // fill Withdraw Buffer via depositQueue
300:                     restakeManager.depositQueue().fillERC20withdrawBuffer(
301:                         address(tokens[i]),
302:                         bufferToFill
303:                     );
304:                 }
305: 
306:                 // Deposit remaining tokens back to eigenLayer
307:                 if (balanceOfToken > 0) {
308:                     _deposit(tokens[i], balanceOfToken);
309:                 }
310:             }
311:             unchecked {
312:                 ++i;
313:             }
314:         }
315: 
316:         // emits the Withdraw Completed event with withdrawalRoot
317:         emit WithdrawCompleted(
318:             delegationManager.calculateWithdrawalRoot(withdrawal),
319:             withdrawal.strategies,
320:             withdrawal.shares
321:         );
322:         // record current spent gas
323:         _recordGas(gasBefore);
324:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L265-L324) 


</details>


### [NC&#x2011;83] Consider bounding input array length 
The functions below take in an unbounded array, and make function calls for entries in the array. While the function will revert if it eventually runs out of gas, it may be a nicer user experience to `require()` that the length of the array is below some reasonable maximum, so that the user doesn't have to use up a full transaction's gas only to see that the transaction reverts.


*There are 17 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/TimelockController.sol

//@audit array name proposers
087:     constructor(
088:         uint256 minDelay,
089:         address[] memory proposers,
090:         address[] memory executors,
091:         address admin
092:     ) {
093:         _setRoleAdmin(TIMELOCK_ADMIN_ROLE, TIMELOCK_ADMIN_ROLE);
094:         _setRoleAdmin(PROPOSER_ROLE, TIMELOCK_ADMIN_ROLE);
095:         _setRoleAdmin(EXECUTOR_ROLE, TIMELOCK_ADMIN_ROLE);
096:         _setRoleAdmin(CANCELLER_ROLE, TIMELOCK_ADMIN_ROLE);
097: 
098:         // self administration
099:         _setupRole(TIMELOCK_ADMIN_ROLE, address(this));
100: 
101:         // optional admin
102:         if (admin != address(0)) {
103:             _setupRole(TIMELOCK_ADMIN_ROLE, admin);
104:         }
105: 
106:         // register proposers and cancellers
107:         for (uint256 i = 0; i < proposers.length; ++i) {
108:             _setupRole(PROPOSER_ROLE, proposers[i]);
109:             _setupRole(CANCELLER_ROLE, proposers[i]);
110:         }
111: 
112:         // register executors
113:         for (uint256 i = 0; i < executors.length; ++i) {
114:             _setupRole(EXECUTOR_ROLE, executors[i]);
115:         }
116: 
117:         _minDelay = minDelay;
118:         emit MinDelayChange(0, minDelay);
119:     }

//@audit array name executors
087:     constructor(
088:         uint256 minDelay,
089:         address[] memory proposers,
090:         address[] memory executors,
091:         address admin
092:     ) {
093:         _setRoleAdmin(TIMELOCK_ADMIN_ROLE, TIMELOCK_ADMIN_ROLE);
094:         _setRoleAdmin(PROPOSER_ROLE, TIMELOCK_ADMIN_ROLE);
095:         _setRoleAdmin(EXECUTOR_ROLE, TIMELOCK_ADMIN_ROLE);
096:         _setRoleAdmin(CANCELLER_ROLE, TIMELOCK_ADMIN_ROLE);
097: 
098:         // self administration
099:         _setupRole(TIMELOCK_ADMIN_ROLE, address(this));
100: 
101:         // optional admin
102:         if (admin != address(0)) {
103:             _setupRole(TIMELOCK_ADMIN_ROLE, admin);
104:         }
105: 
106:         // register proposers and cancellers
107:         for (uint256 i = 0; i < proposers.length; ++i) {
108:             _setupRole(PROPOSER_ROLE, proposers[i]);
109:             _setupRole(CANCELLER_ROLE, proposers[i]);
110:         }
111: 
112:         // register executors
113:         for (uint256 i = 0; i < executors.length; ++i) {
114:             _setupRole(EXECUTOR_ROLE, executors[i]);
115:         }
116: 
117:         _minDelay = minDelay;
118:         emit MinDelayChange(0, minDelay);
119:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L87-L119) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L87-L119)


```solidity

File: contracts/RestakeManager.sol

//@audit array name tvls
362:     function chooseOperatorDelegatorForDeposit(
363:         uint256[] memory tvls,
364:         uint256 totalTVL
365:     ) public view returns (IOperatorDelegator) {
366:         // Ensure OperatorDelegator list is not empty
367:         if (operatorDelegators.length == 0) revert NotFound();
368: 
369:         // If there is only one operator delegator, return it
370:         if (operatorDelegators.length == 1) {
371:             return operatorDelegators[0];
372:         }
373: 
374:         // Otherwise, find the operator delegator with TVL below the threshold
375:         uint256 tvlLength = tvls.length;
376:         for (uint256 i = 0; i < tvlLength; ) {
377:             if (
378:                 tvls[i] <
379:                 (operatorDelegatorAllocations[operatorDelegators[i]] * totalTVL) /
380:                     BASIS_POINTS /
381:                     BASIS_POINTS
382:             ) {
383:                 return operatorDelegators[i];
384:             }
385: 
386:             unchecked {
387:                 ++i;
388:             }
389:         }
390: 
391:         // Default to the first operator delegator
392:         return operatorDelegators[0];
393:     }

//@audit array name operatorDelegatorTokenTVLs
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

//@audit array name operatorDelegatorTVLs
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

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L362-L393) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L400-L447), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L400-L447)


```solidity

File: contracts/Oracle/RenzoOracle.sol

//@audit array name _tokens
103:     function lookupTokenValues(
104:         IERC20[] memory _tokens,
105:         uint256[] memory _balances
106:     ) external view returns (uint256) {
107:         if (_tokens.length != _balances.length) revert MismatchedArrayLengths();
108: 
109:         uint256 totalValue = 0;
110:         uint256 tokenLength = _tokens.length;
111:         for (uint256 i = 0; i < tokenLength; ) {
112:             totalValue += lookupTokenValue(_tokens[i], _balances[i]);
113:             unchecked {
114:                 ++i;
115:             }
116:         }
117: 
118:         return totalValue;
119:     }

//@audit array name _balances
103:     function lookupTokenValues(
104:         IERC20[] memory _tokens,
105:         uint256[] memory _balances
106:     ) external view returns (uint256) {
107:         if (_tokens.length != _balances.length) revert MismatchedArrayLengths();
108: 
109:         uint256 totalValue = 0;
110:         uint256 tokenLength = _tokens.length;
111:         for (uint256 i = 0; i < tokenLength; ) {
112:             totalValue += lookupTokenValue(_tokens[i], _balances[i]);
113:             unchecked {
114:                 ++i;
115:             }
116:         }
117: 
118:         return totalValue;
119:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L103-L119) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L103-L119)


```solidity

File: contracts/Deposits/DepositQueue.sol

//@audit array name operatorDelegators
211:     function stakeEthFromQueueMulti(
212:         IOperatorDelegator[] calldata operatorDelegators,
213:         bytes[] calldata pubkeys,
214:         bytes[] calldata signatures,
215:         bytes32[] calldata depositDataRoots
216:     ) external onlyNativeEthRestakeAdmin nonReentrant {
217:         uint256 gasBefore = gasleft();
218:         // Verify all arrays are the same length
219:         if (
220:             operatorDelegators.length != pubkeys.length ||
221:             operatorDelegators.length != signatures.length ||
222:             operatorDelegators.length != depositDataRoots.length
223:         ) revert MismatchedArrayLengths();
224: 
225:         // Iterate through the arrays and stake each one
226:         uint256 arrayLength = operatorDelegators.length;
227:         for (uint256 i = 0; i < arrayLength; ) {
228:             // Send the ETH and the params through to the restake manager
229:             restakeManager.stakeEthInOperatorDelegator{ value: 32 ether }(
230:                 operatorDelegators[i],
231:                 pubkeys[i],
232:                 signatures[i],
233:                 depositDataRoots[i]
234:             );
235: 
236:             emit ETHStakedFromQueue(
237:                 operatorDelegators[i],
238:                 pubkeys[i],
239:                 32 ether,
240:                 address(this).balance
241:             );
242: 
243:             unchecked {
244:                 ++i;
245:             }
246:         }
247: 
248:         // Refund the gas to the Admin address if enough ETH available
249:         _refundGas(gasBefore);
250:     }

//@audit array name pubkeys
211:     function stakeEthFromQueueMulti(
212:         IOperatorDelegator[] calldata operatorDelegators,
213:         bytes[] calldata pubkeys,
214:         bytes[] calldata signatures,
215:         bytes32[] calldata depositDataRoots
216:     ) external onlyNativeEthRestakeAdmin nonReentrant {
217:         uint256 gasBefore = gasleft();
218:         // Verify all arrays are the same length
219:         if (
220:             operatorDelegators.length != pubkeys.length ||
221:             operatorDelegators.length != signatures.length ||
222:             operatorDelegators.length != depositDataRoots.length
223:         ) revert MismatchedArrayLengths();
224: 
225:         // Iterate through the arrays and stake each one
226:         uint256 arrayLength = operatorDelegators.length;
227:         for (uint256 i = 0; i < arrayLength; ) {
228:             // Send the ETH and the params through to the restake manager
229:             restakeManager.stakeEthInOperatorDelegator{ value: 32 ether }(
230:                 operatorDelegators[i],
231:                 pubkeys[i],
232:                 signatures[i],
233:                 depositDataRoots[i]
234:             );
235: 
236:             emit ETHStakedFromQueue(
237:                 operatorDelegators[i],
238:                 pubkeys[i],
239:                 32 ether,
240:                 address(this).balance
241:             );
242: 
243:             unchecked {
244:                 ++i;
245:             }
246:         }
247: 
248:         // Refund the gas to the Admin address if enough ETH available
249:         _refundGas(gasBefore);
250:     }

//@audit array name signatures
211:     function stakeEthFromQueueMulti(
212:         IOperatorDelegator[] calldata operatorDelegators,
213:         bytes[] calldata pubkeys,
214:         bytes[] calldata signatures,
215:         bytes32[] calldata depositDataRoots
216:     ) external onlyNativeEthRestakeAdmin nonReentrant {
217:         uint256 gasBefore = gasleft();
218:         // Verify all arrays are the same length
219:         if (
220:             operatorDelegators.length != pubkeys.length ||
221:             operatorDelegators.length != signatures.length ||
222:             operatorDelegators.length != depositDataRoots.length
223:         ) revert MismatchedArrayLengths();
224: 
225:         // Iterate through the arrays and stake each one
226:         uint256 arrayLength = operatorDelegators.length;
227:         for (uint256 i = 0; i < arrayLength; ) {
228:             // Send the ETH and the params through to the restake manager
229:             restakeManager.stakeEthInOperatorDelegator{ value: 32 ether }(
230:                 operatorDelegators[i],
231:                 pubkeys[i],
232:                 signatures[i],
233:                 depositDataRoots[i]
234:             );
235: 
236:             emit ETHStakedFromQueue(
237:                 operatorDelegators[i],
238:                 pubkeys[i],
239:                 32 ether,
240:                 address(this).balance
241:             );
242: 
243:             unchecked {
244:                 ++i;
245:             }
246:         }
247: 
248:         // Refund the gas to the Admin address if enough ETH available
249:         _refundGas(gasBefore);
250:     }

//@audit array name depositDataRoots
211:     function stakeEthFromQueueMulti(
212:         IOperatorDelegator[] calldata operatorDelegators,
213:         bytes[] calldata pubkeys,
214:         bytes[] calldata signatures,
215:         bytes32[] calldata depositDataRoots
216:     ) external onlyNativeEthRestakeAdmin nonReentrant {
217:         uint256 gasBefore = gasleft();
218:         // Verify all arrays are the same length
219:         if (
220:             operatorDelegators.length != pubkeys.length ||
221:             operatorDelegators.length != signatures.length ||
222:             operatorDelegators.length != depositDataRoots.length
223:         ) revert MismatchedArrayLengths();
224: 
225:         // Iterate through the arrays and stake each one
226:         uint256 arrayLength = operatorDelegators.length;
227:         for (uint256 i = 0; i < arrayLength; ) {
228:             // Send the ETH and the params through to the restake manager
229:             restakeManager.stakeEthInOperatorDelegator{ value: 32 ether }(
230:                 operatorDelegators[i],
231:                 pubkeys[i],
232:                 signatures[i],
233:                 depositDataRoots[i]
234:             );
235: 
236:             emit ETHStakedFromQueue(
237:                 operatorDelegators[i],
238:                 pubkeys[i],
239:                 32 ether,
240:                 address(this).balance
241:             );
242: 
243:             unchecked {
244:                 ++i;
245:             }
246:         }
247: 
248:         // Refund the gas to the Admin address if enough ETH available
249:         _refundGas(gasBefore);
250:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L211-L250) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L211-L250), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L211-L250), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L211-L250)


```solidity

File: contracts/Delegation/OperatorDelegator.sol

//@audit array name tokens
193:     function queueWithdrawals(
194:         IERC20[] calldata tokens,
195:         uint256[] calldata tokenAmounts
196:     ) external nonReentrant onlyNativeEthRestakeAdmin returns (bytes32) {
197:         // record gas spent
198:         uint256 gasBefore = gasleft();
199:         if (tokens.length != tokenAmounts.length) revert MismatchedArrayLengths();
200:         IDelegationManager.QueuedWithdrawalParams[]
201:             memory queuedWithdrawalParams = new IDelegationManager.QueuedWithdrawalParams[](1);
202:         // set strategies legth for 0th index only
203:         queuedWithdrawalParams[0].strategies = new IStrategy[](tokens.length);
204:         queuedWithdrawalParams[0].shares = new uint256[](tokens.length);
205: 
206:         // Save the nonce before starting the withdrawal
207:         uint96 nonce = uint96(delegationManager.cumulativeWithdrawalsQueued(address(this)));
208: 
209:         for (uint256 i; i < tokens.length; ) {
210:             if (address(tokens[i]) == IS_NATIVE) {
211:                 // set beaconChainEthStrategy for ETH
212:                 queuedWithdrawalParams[0].strategies[i] = eigenPodManager.beaconChainETHStrategy();
213: 
214:                 // set shares for ETH
215:                 queuedWithdrawalParams[0].shares[i] = tokenAmounts[i];
216:             } else {
217:                 if (address(tokenStrategyMapping[tokens[i]]) == address(0))
218:                     revert InvalidZeroInput();
219: 
220:                 // set the strategy of the token
221:                 queuedWithdrawalParams[0].strategies[i] = tokenStrategyMapping[tokens[i]];
222: 
223:                 // set the equivalent shares for tokenAmount
224:                 queuedWithdrawalParams[0].shares[i] = tokenStrategyMapping[tokens[i]]
225:                     .underlyingToSharesView(tokenAmounts[i]);
226:             }
227: 
228:             // set withdrawer as this contract address
229:             queuedWithdrawalParams[0].withdrawer = address(this);
230: 
231:             // track shares of tokens withdraw for TVL
232:             queuedShares[address(tokens[i])] += queuedWithdrawalParams[0].shares[i];
233:             unchecked {
234:                 ++i;
235:             }
236:         }
237: 
238:         // queue withdrawal in EigenLayer
239:         bytes32 withdrawalRoot = delegationManager.queueWithdrawals(queuedWithdrawalParams)[0];
240:         // Emit the withdrawal started event
241:         emit WithdrawStarted(
242:             withdrawalRoot,
243:             address(this),
244:             delegateAddress,
245:             address(this),
246:             nonce,
247:             block.number,
248:             queuedWithdrawalParams[0].strategies,
249:             queuedWithdrawalParams[0].shares
250:         );
251: 
252:         // update the gas spent for RestakeAdmin
253:         _recordGas(gasBefore);
254: 
255:         return withdrawalRoot;
256:     }

//@audit array name tokenAmounts
193:     function queueWithdrawals(
194:         IERC20[] calldata tokens,
195:         uint256[] calldata tokenAmounts
196:     ) external nonReentrant onlyNativeEthRestakeAdmin returns (bytes32) {
197:         // record gas spent
198:         uint256 gasBefore = gasleft();
199:         if (tokens.length != tokenAmounts.length) revert MismatchedArrayLengths();
200:         IDelegationManager.QueuedWithdrawalParams[]
201:             memory queuedWithdrawalParams = new IDelegationManager.QueuedWithdrawalParams[](1);
202:         // set strategies legth for 0th index only
203:         queuedWithdrawalParams[0].strategies = new IStrategy[](tokens.length);
204:         queuedWithdrawalParams[0].shares = new uint256[](tokens.length);
205: 
206:         // Save the nonce before starting the withdrawal
207:         uint96 nonce = uint96(delegationManager.cumulativeWithdrawalsQueued(address(this)));
208: 
209:         for (uint256 i; i < tokens.length; ) {
210:             if (address(tokens[i]) == IS_NATIVE) {
211:                 // set beaconChainEthStrategy for ETH
212:                 queuedWithdrawalParams[0].strategies[i] = eigenPodManager.beaconChainETHStrategy();
213: 
214:                 // set shares for ETH
215:                 queuedWithdrawalParams[0].shares[i] = tokenAmounts[i];
216:             } else {
217:                 if (address(tokenStrategyMapping[tokens[i]]) == address(0))
218:                     revert InvalidZeroInput();
219: 
220:                 // set the strategy of the token
221:                 queuedWithdrawalParams[0].strategies[i] = tokenStrategyMapping[tokens[i]];
222: 
223:                 // set the equivalent shares for tokenAmount
224:                 queuedWithdrawalParams[0].shares[i] = tokenStrategyMapping[tokens[i]]
225:                     .underlyingToSharesView(tokenAmounts[i]);
226:             }
227: 
228:             // set withdrawer as this contract address
229:             queuedWithdrawalParams[0].withdrawer = address(this);
230: 
231:             // track shares of tokens withdraw for TVL
232:             queuedShares[address(tokens[i])] += queuedWithdrawalParams[0].shares[i];
233:             unchecked {
234:                 ++i;
235:             }
236:         }
237: 
238:         // queue withdrawal in EigenLayer
239:         bytes32 withdrawalRoot = delegationManager.queueWithdrawals(queuedWithdrawalParams)[0];
240:         // Emit the withdrawal started event
241:         emit WithdrawStarted(
242:             withdrawalRoot,
243:             address(this),
244:             delegateAddress,
245:             address(this),
246:             nonce,
247:             block.number,
248:             queuedWithdrawalParams[0].strategies,
249:             queuedWithdrawalParams[0].shares
250:         );
251: 
252:         // update the gas spent for RestakeAdmin
253:         _recordGas(gasBefore);
254: 
255:         return withdrawalRoot;
256:     }

//@audit array name tokens
265:     function completeQueuedWithdrawal(
266:         IDelegationManager.Withdrawal calldata withdrawal,
267:         IERC20[] calldata tokens,
268:         uint256 middlewareTimesIndex
269:     ) external nonReentrant onlyNativeEthRestakeAdmin {
270:         uint256 gasBefore = gasleft();
271:         if (tokens.length != withdrawal.strategies.length) revert MismatchedArrayLengths();
272: 
273:         // complete the queued withdrawal from EigenLayer with receiveAsToken set to true
274:         delegationManager.completeQueuedWithdrawal(withdrawal, tokens, middlewareTimesIndex, true);
275: 
276:         IWithdrawQueue withdrawQueue = restakeManager.depositQueue().withdrawQueue();
277:         for (uint256 i; i < tokens.length; ) {
278:             if (address(tokens[i]) == address(0)) revert InvalidZeroInput();
279: 
280:             // deduct queued shares for tracking TVL
281:             queuedShares[address(tokens[i])] -= withdrawal.shares[i];
282: 
283:             // check if token is not Native ETH
284:             if (address(tokens[i]) != IS_NATIVE) {
285:                 // Check the withdraw buffer and fill if below buffer target
286:                 uint256 bufferToFill = withdrawQueue.getBufferDeficit(address(tokens[i]));
287: 
288:                 // get balance of this contract
289:                 uint256 balanceOfToken = tokens[i].balanceOf(address(this));
290:                 if (bufferToFill > 0) {
291:                     bufferToFill = (balanceOfToken <= bufferToFill) ? balanceOfToken : bufferToFill;
292: 
293:                     // update amount to send to the operator Delegator
294:                     balanceOfToken -= bufferToFill;
295: 
296:                     // safe Approve for depositQueue
297:                     tokens[i].safeApprove(address(restakeManager.depositQueue()), bufferToFill);
298: 
299:                     // fill Withdraw Buffer via depositQueue
300:                     restakeManager.depositQueue().fillERC20withdrawBuffer(
301:                         address(tokens[i]),
302:                         bufferToFill
303:                     );
304:                 }
305: 
306:                 // Deposit remaining tokens back to eigenLayer
307:                 if (balanceOfToken > 0) {
308:                     _deposit(tokens[i], balanceOfToken);
309:                 }
310:             }
311:             unchecked {
312:                 ++i;
313:             }
314:         }
315: 
316:         // emits the Withdraw Completed event with withdrawalRoot
317:         emit WithdrawCompleted(
318:             delegationManager.calculateWithdrawalRoot(withdrawal),
319:             withdrawal.strategies,
320:             withdrawal.shares
321:         );
322:         // record current spent gas
323:         _recordGas(gasBefore);
324:     }

//@audit array name validatorFields
364:     function verifyWithdrawalCredentials(
365:         uint64 oracleTimestamp,
366:         BeaconChainProofs.StateRootProof calldata stateRootProof,
367:         uint40[] calldata validatorIndices,
368:         bytes[] calldata withdrawalCredentialProofs,
369:         bytes32[][] calldata validatorFields
370:     ) external onlyNativeEthRestakeAdmin {
371:         uint256 gasBefore = gasleft();
372:         eigenPod.verifyWithdrawalCredentials(
373:             oracleTimestamp,
374:             stateRootProof,
375:             validatorIndices,
376:             withdrawalCredentialProofs,
377:             validatorFields
378:         );
379: 
380:         // Decrement the staked but not verified ETH
381:         for (uint256 i = 0; i < validatorFields.length; ) {
382:             uint64 validatorCurrentBalanceGwei = BeaconChainProofs.getEffectiveBalanceGwei(
383:                 validatorFields[i]
384:             );
385:             stakedButNotVerifiedEth -= (validatorCurrentBalanceGwei * GWEI_TO_WEI);
386:             unchecked {
387:                 ++i;
388:             }
389:         }
390:         // update the gas spent for RestakeAdmin
391:         _recordGas(gasBefore);
392:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L193-L256) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L193-L256), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L265-L324), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L364-L392)


```solidity

File: contracts/Bridge/L1/xRenzoBridge.sol

//@audit array name _destinationParam
210:     function sendPrice(
211:         CCIPDestinationParam[] calldata _destinationParam,
212:         ConnextDestinationParam[] calldata _connextDestinationParam
213:     ) external payable onlyPriceFeedSender nonReentrant {
214:         // call getRate() to get the current price of ezETH
215:         uint256 exchangeRate = rateProvider.getRate();
216:         bytes memory _callData = abi.encode(exchangeRate, block.timestamp);
217:         // send price feed to renzo CCIP receivers
218:         for (uint256 i = 0; i < _destinationParam.length; ) {
219:             Client.EVM2AnyMessage memory evm2AnyMessage = Client.EVM2AnyMessage({
220:                 receiver: abi.encode(_destinationParam[i]._renzoReceiver), // ABI-encoded xRenzoDepsot contract address
221:                 data: _callData, // ABI-encoded ezETH exchange rate with Timestamp
222:                 tokenAmounts: new Client.EVMTokenAmount[](0), // Empty array indicating no tokens are being sent
223:                 extraArgs: Client._argsToBytes(
224:                     // Additional arguments, setting gas limit
225:                     Client.EVMExtraArgsV1({ gasLimit: 200_000 })
226:                 ),
227:                 // Set the feeToken  address, indicating LINK will be used for fees
228:                 feeToken: address(linkToken)
229:             });
230: 
231:             // Get the fee required to send the message
232:             uint256 fees = linkRouterClient.getFee(
233:                 _destinationParam[i].destinationChainSelector,
234:                 evm2AnyMessage
235:             );
236: 
237:             if (fees > linkToken.balanceOf(address(this)))
238:                 revert NotEnoughBalance(linkToken.balanceOf(address(this)), fees);
239: 
240:             // approve the Router to transfer LINK tokens on contract's behalf. It will spend the fees in LINK
241:             linkToken.approve(address(linkRouterClient), fees);
242: 
243:             // Send the message through the router and store the returned message ID
244:             bytes32 messageId = linkRouterClient.ccipSend(
245:                 _destinationParam[i].destinationChainSelector,
246:                 evm2AnyMessage
247:             );
248: 
249:             // Emit an event with message details
250:             emit MessageSent(
251:                 messageId,
252:                 _destinationParam[i].destinationChainSelector,
253:                 _destinationParam[i]._renzoReceiver,
254:                 exchangeRate,
255:                 address(linkToken),
256:                 fees
257:             );
258:             unchecked {
259:                 ++i;
260:             }
261:         }
262: 
263:         // send price feed to renzo connext receiver
264:         for (uint256 i = 0; i < _connextDestinationParam.length; ) {
265:             connext.xcall{ value: _connextDestinationParam[i].relayerFee }(
266:                 _connextDestinationParam[i].destinationDomainId,
267:                 _connextDestinationParam[i]._renzoReceiver,
268:                 address(0),
269:                 msg.sender,
270:                 0,
271:                 0,
272:                 _callData
273:             );
274: 
275:             emit ConnextMessageSent(
276:                 _connextDestinationParam[i].destinationDomainId,
277:                 _connextDestinationParam[i]._renzoReceiver,
278:                 exchangeRate,
279:                 _connextDestinationParam[i].relayerFee
280:             );
281: 
282:             unchecked {
283:                 ++i;
284:             }
285:         }
286:     }

//@audit array name _connextDestinationParam
210:     function sendPrice(
211:         CCIPDestinationParam[] calldata _destinationParam,
212:         ConnextDestinationParam[] calldata _connextDestinationParam
213:     ) external payable onlyPriceFeedSender nonReentrant {
214:         // call getRate() to get the current price of ezETH
215:         uint256 exchangeRate = rateProvider.getRate();
216:         bytes memory _callData = abi.encode(exchangeRate, block.timestamp);
217:         // send price feed to renzo CCIP receivers
218:         for (uint256 i = 0; i < _destinationParam.length; ) {
219:             Client.EVM2AnyMessage memory evm2AnyMessage = Client.EVM2AnyMessage({
220:                 receiver: abi.encode(_destinationParam[i]._renzoReceiver), // ABI-encoded xRenzoDepsot contract address
221:                 data: _callData, // ABI-encoded ezETH exchange rate with Timestamp
222:                 tokenAmounts: new Client.EVMTokenAmount[](0), // Empty array indicating no tokens are being sent
223:                 extraArgs: Client._argsToBytes(
224:                     // Additional arguments, setting gas limit
225:                     Client.EVMExtraArgsV1({ gasLimit: 200_000 })
226:                 ),
227:                 // Set the feeToken  address, indicating LINK will be used for fees
228:                 feeToken: address(linkToken)
229:             });
230: 
231:             // Get the fee required to send the message
232:             uint256 fees = linkRouterClient.getFee(
233:                 _destinationParam[i].destinationChainSelector,
234:                 evm2AnyMessage
235:             );
236: 
237:             if (fees > linkToken.balanceOf(address(this)))
238:                 revert NotEnoughBalance(linkToken.balanceOf(address(this)), fees);
239: 
240:             // approve the Router to transfer LINK tokens on contract's behalf. It will spend the fees in LINK
241:             linkToken.approve(address(linkRouterClient), fees);
242: 
243:             // Send the message through the router and store the returned message ID
244:             bytes32 messageId = linkRouterClient.ccipSend(
245:                 _destinationParam[i].destinationChainSelector,
246:                 evm2AnyMessage
247:             );
248: 
249:             // Emit an event with message details
250:             emit MessageSent(
251:                 messageId,
252:                 _destinationParam[i].destinationChainSelector,
253:                 _destinationParam[i]._renzoReceiver,
254:                 exchangeRate,
255:                 address(linkToken),
256:                 fees
257:             );
258:             unchecked {
259:                 ++i;
260:             }
261:         }
262: 
263:         // send price feed to renzo connext receiver
264:         for (uint256 i = 0; i < _connextDestinationParam.length; ) {
265:             connext.xcall{ value: _connextDestinationParam[i].relayerFee }(
266:                 _connextDestinationParam[i].destinationDomainId,
267:                 _connextDestinationParam[i]._renzoReceiver,
268:                 address(0),
269:                 msg.sender,
270:                 0,
271:                 0,
272:                 _callData
273:             );
274: 
275:             emit ConnextMessageSent(
276:                 _connextDestinationParam[i].destinationDomainId,
277:                 _connextDestinationParam[i]._renzoReceiver,
278:                 exchangeRate,
279:                 _connextDestinationParam[i].relayerFee
280:             );
281: 
282:             unchecked {
283:                 ++i;
284:             }
285:         }
286:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L210-L286) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L210-L286)


</details>


### [NC&#x2011;84] A function which defines named returns in it's declaration doesn't need to use return 
Remove the return statement once ensuring it is safe to do so


*There are 2 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Delegation/OperatorDelegator.sol

143:     function deposit(
144:         IERC20 token,
145:         uint256 tokenAmount
146:     ) external nonReentrant onlyRestakeManager returns (uint256 shares) {
147:         if (address(tokenStrategyMapping[token]) == address(0x0) || tokenAmount == 0)
148:             revert InvalidZeroInput();
149: 
150:         // Move the tokens into this contract
151:         token.safeTransferFrom(msg.sender, address(this), tokenAmount);
152: 
153:         return _deposit(token, tokenAmount);
154:     }

162:     function _deposit(IERC20 _token, uint256 _tokenAmount) internal returns (uint256 shares) {
163:         // Approve the strategy manager to spend the tokens
164:         _token.safeApprove(address(strategyManager), _tokenAmount);
165: 
166:         // Deposit the tokens via the strategy manager
167:         return
168:             strategyManager.depositIntoStrategy(tokenStrategyMapping[_token], _token, _tokenAmount);
169:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L143-L154) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L162-L169)


</details>


### [NC&#x2011;85] [NatSpec] Natspec `@dev` is missing from `contract` 



*There are 155 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Withdraw/WithdrawQueue.sol

11: contract WithdrawQueue is

19:     event WithdrawBufferTargetUpdated(uint256 oldBufferTarget, uint256 newBufferTarget);

21:     event CoolDownPeriodUpdated(uint256 oldCoolDownPeriod, uint256 newCoolDownPeriod);

23:     event EthBufferFilled(uint256 amount);

25:     event ERC20BufferFilled(address asset, uint256 amount);

27:     event WithdrawRequestCreated(

36:     event WithdrawRequestClaimed(WithdrawRequest withdrawRequest);

50:     modifier onlyDepositQueue() {

61:     /**
62:      * @notice  Initializes the contract with initial vars
63:      */

151:     /**
152:      * @notice  returns available to withdraw for particular asset
153:      * @param   _asset  address of asset. for ETH _asset = 0xEeeeeEeeeEeEeeEeEeEeeEEEeeeeEeeeeeeeEEeE
154:      * @return  uint256  amount available to withdraw from buffer
155:      */

201:     /**
202:      * @notice  Creates a withdraw request for user
203:      * @param   _amount  amount of ezETH to withdraw
204:      * @param   _assetOut  output token to receive on claim
205:      */

265:     /**
266:      * @notice  Returns the number of outstanding withdrawal requests of the specified user
267:      * @param   user  address of the user
268:      * @return  uint256  number of outstanding withdrawal requests
269:      */


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L11-L11) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L19-L19), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L21-L21), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L23-L23), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L25-L25), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L27-L27), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L36-L36), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L50-L50), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L61-L63), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L151-L155), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L201-L205), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L265-L269)


```solidity

File: contracts/Withdraw/WithdrawQueueStorage.sol

9: abstract contract WithdrawQueueStorageV1 {

12:     struct TokenWithdrawBuffer {

17:     struct WithdrawRequest {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueueStorage.sol#L9-L9) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueueStorage.sol#L12-L12), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueueStorage.sol#L17-L17)


```solidity

File: contracts/Rewards/RewardHandlerStorage.sol

6: abstract contract RewardHandlerStorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandlerStorage.sol#L6-L6) 


```solidity

File: contracts/Rewards/RewardHandler.sol

29:     event RewardDestinationUpdated(address rewardDestination);

62:     function _forwardETH() internal {

72:     function setRewardDestination(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L29-L29) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L62-L62), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L72-L72)


```solidity

File: contracts/RestakeManagerStorage.sol

15: abstract contract RestakeManagerStorageV1 is IRestakeManager {

64: abstract contract RestakeManagerStorageV2 is RestakeManagerStorageV1 {

29:     struct PendingWithdrawal {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManagerStorage.sol#L15-L15) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManagerStorage.sol#L64-L64), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManagerStorage.sol#L29-L29)


```solidity

File: contracts/RestakeManager.sol

30:     event OperatorDelegatorAdded(IOperatorDelegator od);

31:     event OperatorDelegatorRemoved(IOperatorDelegator od);

32:     event OperatorDelegatorAllocationUpdated(IOperatorDelegator od, uint256 allocation);

34:     event CollateralTokenAdded(IERC20 token);

35:     event CollateralTokenRemoved(IERC20 token);

709:     function setTokenTvlLimit(IERC20 _token, uint256 _limit) external onlyRestakeManagerAdmin {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L30-L30) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L31-L31), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L32-L32), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L34-L34), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L35-L35), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L709-L709)


```solidity

File: contracts/RateProvider/BalancerRateProvider.sol

9: contract BalancerRateProvider is Initializable, IRateProvider, BalancerRateProviderStorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProvider.sol#L9-L9) 


```solidity

File: contracts/RateProvider/BalancerRateProviderStorage.sol

7: abstract contract BalancerRateProviderStorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProviderStorage.sol#L7-L7) 


```solidity

File: contracts/Permissions/RoleManagerStorage.sol

35: /// On the next version of the protocol, if new variables are added, put them in the below
36: /// contract and use this as the inheritance chain.
37: contract RoleManagerStorageV2 is RoleManagerStorageV1 {

45: contract RoleManagerStorageV3 is RoleManagerStorageV2 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManagerStorage.sol#L35-L37) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManagerStorage.sol#L45-L45)


```solidity

File: contracts/Oracle/RenzoOracle.sol

101:     /// The value returned will be denominated in the decimal precision of the lookup oracle
102:     /// (e.g. a value of 100 would return as 100 * 10^18)

152:     function calculateRedeemAmount(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L101-L102) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L152-L152)


```solidity

File: contracts/Oracle/RenzoOracleStorage.sol

8: abstract contract RenzoOracleStorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracleStorage.sol#L8-L8) 


```solidity

File: contracts/Oracle/Mantle/METHShim.sol

29:     function decimals() external pure returns (uint8) {

33:     function description() external pure returns (string memory) {

37:     function version() external pure returns (uint256) {

46:     function latestRoundData()


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L29-L29) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L33-L33), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L37-L37), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L46-L46)


```solidity

File: contracts/Oracle/Mantle/METHShimStorage.sol

7: abstract contract METHShimStorageV1 is AggregatorV3Interface {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShimStorage.sol#L7-L7) 


```solidity

File: contracts/Oracle/Binance/WBETHShimStorage.sol

7: abstract contract WBETHShimStorageV1 is AggregatorV3Interface {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShimStorage.sol#L7-L7) 


```solidity

File: contracts/Oracle/Binance/WBETHShim.sol

29:     function decimals() external pure returns (uint8) {

33:     function description() external pure returns (string memory) {

37:     function version() external pure returns (uint256) {

46:     function latestRoundData()


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L29-L29) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L33-L33), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L37-L37), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L46-L46)


```solidity

File: contracts/Deposits/DepositQueueStorage.sol

9: abstract contract DepositQueueStorageV1 is IDepositQueue {

26: abstract contract DepositQueueStorageV2 is DepositQueueStorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueueStorage.sol#L9-L9) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueueStorage.sol#L26-L26)


```solidity

File: contracts/Deposits/DepositQueue.sol

10: contract DepositQueue is Initializable, ReentrancyGuardUpgradeable, DepositQueueStorageV2 {

15:     event RewardsDeposited(IERC20 token, uint256 amount);

17:     event FeeConfigUpdated(address feeAddress, uint256 feeBasisPoints);

19:     event RestakeManagerUpdated(IRestakeManager restakeManager);

21:     event ETHDepositedFromProtocol(uint256 amount);

23:     event ETHStakedFromQueue(

30:     event ProtocolFeesPaid(IERC20 token, uint256 amount, address destination);

32:     event GasRefunded(address admin, uint256 gasRefunded);

279:     /**
280:      * @notice Internal function used to refund gas to admin accounts if enough balance
281:      * @param initialGas Initial Gas available
282:      */

291:     /**
292:      * @notice  Check if WithdrawBuffer Needs to be filled
293:      */


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L10-L10) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L15-L15), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L17-L17), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L19-L19), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L21-L21), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L23-L23), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L30-L30), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L32-L32), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L279-L282), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L291-L293)


```solidity

File: contracts/Delegation/OperatorDelegator.sol

28:     event TokenStrategyUpdated(IERC20 token, IStrategy strategy);

29:     event DelegationAddressUpdated(address delegateAddress);

30:     event RewardsForwarded(address rewardDestination, uint256 amount);

32:     event WithdrawStarted(

43:     event WithdrawCompleted(bytes32 withdrawalRoot, IStrategy[] strategies, uint256[] shares);

45:     event GasSpent(address admin, uint256 gasSpent);

46:     event GasRefunded(address admin, uint256 gasRefunded);

47:     event BaseGasAmountSpentUpdated(uint256 oldBaseGasAmountSpent, uint256 newBaseGasAmountSpent);

132:     function setBaseGasAmountSpent(

156:     /**
157:      * @notice  Perform necessary checks on input data and deposits into EigenLayer
158:      * @param   _token  token interface to deposit
159:      * @param   _tokenAmount  amount of given token to deposit
160:      * @return  shares  shares for deposited amount
161:      */


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L28-L28) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L29-L29), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L30-L30), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L32-L32), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L43-L43), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L45-L45), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L46-L46), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L47-L47), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L132-L132), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L156-L161)


```solidity

File: contracts/Delegation/OperatorDelegatorStorage.sol

46: abstract contract OperatorDelegatorStorageV2 is OperatorDelegatorStorageV1 {

51: abstract contract OperatorDelegatorStorageV3 is OperatorDelegatorStorageV2 {

59: abstract contract OperatorDelegatorStorageV4 is OperatorDelegatorStorageV3 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegatorStorage.sol#L46-L46) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegatorStorage.sol#L51-L51), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegatorStorage.sol#L59-L59)


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20.sol

16: contract XERC20 is

54:     /**
55:      * @notice Constructs the initial config of the XERC20
56:      *
57:      * @param _name The name of the token
58:      * @param _symbol The symbol of the token
59:      * @param _factory The factory which deployed this contract
60:      */

69:     /**
70:      * @notice Constructs the initial config of the XERC20
71:      *
72:      * @param _name The name of the token
73:      * @param _symbol The symbol of the token
74:      * @param _factory The factory which deployed this contract
75:      */

115:     /**
116:      * @notice Sets the lockbox address
117:      *
118:      * @param _lockbox The address of the lockbox
119:      */

145:     /**
146:      * @notice Returns the max limit of a bridge
147:      *
148:      * @param _bridge the bridge we are viewing the limits of
149:      * @return _limit The limit the bridge has
150:      */

156:     /**
157:      * @notice Returns the max limit of a bridge
158:      *
159:      * @param _bridge the bridge we are viewing the limits of
160:      * @return _limit The limit the bridge has
161:      */

167:     /**
168:      * @notice Returns the current limit of a bridge
169:      *
170:      * @param _bridge the bridge we are viewing the limits of
171:      * @return _limit The limit the bridge has
172:      */

183:     /**
184:      * @notice Returns the current limit of a bridge
185:      *
186:      * @param _bridge the bridge we are viewing the limits of
187:      * @return _limit The limit the bridge has
188:      */

199:     /**
200:      * @notice Uses the limit of any bridge
201:      * @param _bridge The address of the bridge who is being changed
202:      * @param _change The change in the limit
203:      */

211:     /**
212:      * @notice Uses the limit of any bridge
213:      * @param _bridge The address of the bridge who is being changed
214:      * @param _change The change in the limit
215:      */

267:     /**
268:      * @notice Updates the current limit
269:      *
270:      * @param _limit The new limit
271:      * @param _oldLimit The old limit
272:      * @param _currentLimit The current limit
273:      * @return _newCurrentLimit The new current limit
274:      */

292:     /**
293:      * @notice Gets the current limit
294:      *
295:      * @param _currentLimit The current limit
296:      * @param _maxLimit The max limit
297:      * @param _timestamp The timestamp of the last update
298:      * @param _ratePerSecond The rate per second
299:      * @return _limit The current limit
300:      */

320:     /**
321:      * @notice Internal function for burning tokens
322:      *
323:      * @param _caller The caller address
324:      * @param _user The user address
325:      * @param _amount The amount to burn
326:      */

340:     /**
341:      * @notice Internal function for minting tokens
342:      *
343:      * @param _caller The caller address
344:      * @param _user The user address
345:      * @param _amount The amount to mint
346:      */


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L16-L16) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L54-L60), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L69-L75), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L115-L119), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L145-L150), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L156-L161), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L167-L172), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L183-L188), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L199-L203), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L211-L215), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L267-L274), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L292-L300), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L320-L326), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L340-L346)


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Factory.sol

14: contract XERC20Factory is Initializable, IXERC20Factory {

48:     /**
49:      * @notice Constructs the initial config of the XERC20
50:      *
51:      * @param _lockboxImplementation The address of the implementation contract for any new lockboxes
52:      * @param _xerc20Implementation The address of the implementation contract for any new xerc20s
53:      */


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L14-L14) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L48-L53)


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol

11: contract OptimismMintableXERC20 is ERC165Upgradeable, XERC20, IOptimismMintableERC20 {

28:     /**
29:      * @notice Constructs the initial config of the XERC20
30:      *
31:      * @param _name The name of the token
32:      * @param _symbol The symbol of the token
33:      * @param _factory The factory which deployed this contract
34:      */

48:     function supportsInterface(

56:     function remoteToken() public view override returns (address) {

60:     function bridge() public view override returns (address) {

64:     function mint(address _to, uint256 _amount) public override(XERC20, IOptimismMintableERC20) {

68:     function burn(address _from, uint256 _amount) public override(XERC20, IOptimismMintableERC20) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L11-L11) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L28-L34), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L48-L48), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L56-L56), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L60-L60), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L64-L64), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L68-L68)


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol

14: contract OptimismMintableXERC20Factory is Initializable, XERC20Factory {

15:     error OptimismMintableXERC20Factory_NoBridges();


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L14-L14) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L15-L15)


```solidity

File: contracts/Bridge/L2/xRenzoDepositStorage.sol

9: abstract contract xRenzoDepositStorageV1 is IxRenzoDeposit {

47: abstract contract xRenzoDepositStorageV2 is xRenzoDepositStorageV1 {

52: abstract contract xRenzoDepositStorageV3 is xRenzoDepositStorageV2 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L9-L9) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L47-L47), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L52-L52)


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

42:     event PriceUpdated(uint256 price, uint256 timestamp);

43:     event Deposit(address indexed user, uint256 amountIn, uint256 amountOut);

44:     event BridgeSweeperAddressUpdated(address sweeper, bool allowed);

45:     event BridgeSwept(

51:     event OraclePriceFeedUpdated(address newOracle, address oldOracle);

52:     event ReceiverPriceFeedUpdated(address newReceiver, address oldReceiver);

53:     event SweeperBridgeFeeCollected(address sweeper, uint256 feeCollected);

54:     event BridgeFeeShareUpdated(uint256 oldBridgeFeeShare, uint256 newBridgeFeeShare);

55:     event SweepBatchSizeUpdated(uint256 oldSweepBatchSize, uint256 newSweepBatchSize);

273:     /**
274:      * @notice Function returns bridge fee share for deposit
275:      * @param _amountIn deposit amount in terms of ETH
276:      */

286:     /**
287:      * @notice Fetch the price of ezETH from configured price feeds
288:      */

393:     /**
394:      * @notice This function transfer the bridge fee to sweeper address
395:      */


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L42-L42) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L43-L43), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L44-L44), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L45-L45), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L51-L51), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L52-L52), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L53-L53), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L54-L54), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L55-L55), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L273-L276), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L286-L288), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L393-L395)


```solidity

File: contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol

10: contract ConnextReceiver is IXReceiver, Ownable, Pausable {

23:     event XRenzoBridgeL1Updated(address newBridgeAddress, address oldBridgeAddress);

24:     event ConnextEthChainDomainUpdated(uint32 newSourceChainDomain, uint32 oldSourceChainDomain);

25:     event XRenzoDepositUpdated(address newRenzoDeposit, address oldRenzoDeposit);

43:     modifier onlySource(address _originSender, uint32 _origin) {

52:     constructor(address _connext, address _xRenzoBridgeL1, uint32 _connextEthChainDomain) {

69:     function xReceive(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L10-L10) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L23-L23), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L24-L24), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L25-L25), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L43-L43), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L52-L52), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L69-L69)


```solidity

File: contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol

13: /// @title CCIPReceiver - Base contract for CCIP applications that can receive messages.
14: contract Receiver is CCIPReceiver, Ownable, Pausable {

24:     event XRenzoBridgeL1Updated(address newBridgeAddress, address oldBridgeAddress);

25:     event CCIPEthChainSelectorUpdated(uint64 newSourceChainSelector, uint64 oldSourceChainSelector);

26:     event XRenzoDepositUpdated(address newRenzoDeposit, address oldRenzoDeposit);

43:     constructor(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L13-L14) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L24-L24), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L25-L25), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L26-L26), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L43-L43)


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2.sol

11: contract RenzoOracleL2 is Initializable, OwnableUpgradeable, RenzoOracleL2StorageV1 {

15:     event OracleAddressUpdated(address newOracle, address oldOracle);

23:     function initialize(AggregatorV3Interface _oracle) public initializer {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L11-L11) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L15-L15), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L23-L23)


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2Storage.sol

7: abstract contract RenzoOracleL2StorageV1 is IRenzoOracleL2 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2Storage.sol#L7-L7) 


```solidity

File: contracts/Bridge/L1/xRenzoBridge.sol

16: contract xRenzoBridge is

43:     event ConnextMessageSent(

50:     modifier onlyBridgeAdmin() {

55:     modifier onlyPriceFeedSender() {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L16-L16) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L43-L43), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L50-L50), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L55-L55)


```solidity

File: contracts/Bridge/L1/xRenzoBridgeStorage.sol

18: abstract contract xRenzoBridgeStorageV1 is IxRenzoBridge {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridgeStorage.sol#L18-L18) 


```solidity

File: contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol

9: interface IXERC20Registry {

17: interface L1StandardBridge {

10:     function getXERC20(address erc20) external view returns (address xerc20);

12:     function getERC20(address xerc20) external view returns (address erc20);

14:     function getLockbox(address erc20) external view returns (address xerc20);

18:     function bridgeERC20To(

35:     error InvalidRemoteToken(address _remoteToken);

36:     error AmountLessThanZero();

37:     error InvalidAddress();

39:     constructor(address _blastStandardBridge, address _registry) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L9-L9) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L17-L17), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L10-L10), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L12-L12), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L14-L14), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L18-L18), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L35-L35), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L36-L36), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L37-L37), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L39-L39)


```solidity

File: contracts/Bridge/Connext/libraries/LibConnextStorage.sol

38: struct TransferInfo {

64: struct ExecuteArgs {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/libraries/LibConnextStorage.sol#L38-L38) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/libraries/LibConnextStorage.sol#L64-L64)


```solidity

File: contracts/Bridge/Connext/libraries/TokenId.sol

9: struct TokenId {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/libraries/TokenId.sol#L9-L9) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol

11: contract XERC20Lockbox is Initializable, IXERC20Lockbox {

37:     /**
38:      * @notice Constructor
39:      *
40:      * @param _xerc20 The address of the XERC20 contract
41:      * @param _erc20 The address of the ERC20 contract
42:      * @param _isNative Whether the ERC20 token is the native gas token of this chain or not
43:      */

50:     /**
51:      * @notice Deposit native tokens into the lockbox
52:      */

60:     /**
61:      * @notice Deposit ERC20 tokens into the lockbox
62:      *
63:      * @param _amount The amount of tokens to deposit
64:      */

72:     /**
73:      * @notice Deposit ERC20 tokens into the lockbox, and send the XERC20 to a user
74:      *
75:      * @param _to The user to send the XERC20 to
76:      * @param _amount The amount of tokens to deposit
77:      */

85:     /**
86:      * @notice Deposit the native asset into the lockbox, and send the XERC20 to a user
87:      *
88:      * @param _to The user to send the XERC20 to
89:      */

097:     /**
098:      * @notice Withdraw ERC20 tokens from the lockbox
099:      *
100:      * @param _amount The amount of tokens to withdraw
101:      */

107:     /**
108:      * @notice Withdraw tokens from the lockbox
109:      *
110:      * @param _to The user to withdraw to
111:      * @param _amount The amount of tokens to withdraw
112:      */

118:     /**
119:      * @notice Withdraw tokens from the lockbox
120:      *
121:      * @param _to The user to withdraw to
122:      * @param _amount The amount of tokens to withdraw
123:      */

138:     /**
139:      * @notice Deposit tokens into the lockbox
140:      *
141:      * @param _to The address to send the XERC20 to
142:      * @param _amount The amount of tokens to deposit
143:      */

154:     /**
155:      * @notice Fallback function to deposit native tokens
156:      */


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L11-L11) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L37-L43), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L50-L52), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L60-L64), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L72-L77), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L85-L89), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L97-L101), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L107-L112), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L118-L123), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L138-L143), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L154-L156)


</details>


### [NC&#x2011;86] Contract should expose an `interface` 
The `contract`s should expose an `interface` so that other projects can more easily integrate with it, without having to develop their own non-standard variants.


*There are 69 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/token/EzEthToken.sol

51:     function setPaused(bool _paused) external onlyTokenAdmin {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L51-L51) 


```solidity

File: contracts/Withdraw/WithdrawQueue.sol

106:     function updateWithdrawBufferTarget(

129:     function updateCoolDownPeriod(uint256 _newCoolDownPeriod) external onlyWithdrawQueueAdmin {

270:     function getOutstandingWithdrawRequests(address user) public view returns (uint256) {

279:     function claim(uint256 withdrawRequestIndex) external nonReentrant {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L106-L106) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L129-L129), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L270-L270), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L279-L279)


```solidity

File: contracts/TimelockController.sol

154:     function isOperation(bytes32 id) public view virtual returns (bool) {

161:     function isOperationPending(bytes32 id) public view virtual returns (bool) {

168:     function isOperationReady(bytes32 id) public view virtual returns (bool) {

176:     function isOperationDone(bytes32 id) public view virtual returns (bool) {

184:     function getTimestamp(bytes32 id) public view virtual returns (uint256) {

193:     function getMinDelay() public view virtual returns (uint256) {

201:     function hashOperation(

215:     function hashOperationBatch(

234:     function schedule(

259:     function scheduleBatch(

296:     function cancel(bytes32 id) public virtual onlyRole(CANCELLER_ROLE) {

342:     function executeBatch(

402:     function updateDelay(uint256 newDelay) external virtual {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L154-L154) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L161-L161), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L168-L168), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L176-L176), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L184-L184), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L193-L193), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L201-L201), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L215-L215), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L234-L234), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L259-L259), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L296-L296), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L342-L342), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L402-L402)


```solidity

File: contracts/Rewards/RewardHandler.sol

58:     function forwardRewards() external nonReentrant onlyNativeEthRestakeAdmin {

72:     function setRewardDestination(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L58-L58) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L72-L72)


```solidity

File: contracts/RestakeManager.sol

121:     function setPaused(bool _paused) external onlyDepositWithdrawPauserAdmin {

126:     function getOperatorDelegatorsLength() external view returns (uint256) {

131:     function addOperatorDelegator(

160:     function removeOperatorDelegator(

187:     function setOperatorDelegatorAllocation(

215:     function setMaxDepositTVL(uint256 _maxDepositTVL) external onlyRestakeManagerAdmin {

220:     function addCollateralToken(IERC20 _newCollateralToken) external onlyRestakeManagerAdmin {

244:     function removeCollateralToken(

266:     function getCollateralTokensLength() external view returns (uint256) {

362:     function chooseOperatorDelegatorForDeposit(

400:     function chooseOperatorDelegatorForWithdraw(

451:     function getCollateralTokenIndex(IERC20 _collateralToken) public view returns (uint256) {

675:     function getTotalRewardsEarned() external view returns (uint256) {

709:     function setTokenTvlLimit(IERC20 _token, uint256 _limit) external onlyRestakeManagerAdmin {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L121-L121) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L126-L126), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L131-L131), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L160-L160), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L187-L187), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L215-L215), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L220-L220), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L244-L244), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L266-L266), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L362-L362), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L400-L400), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L451-L451), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L675-L675), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L709-L709)


```solidity

File: contracts/Oracle/RenzoOracle.sol

54:     function setOracleAddress(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L54-L54) 


```solidity

File: contracts/Deposits/DepositQueue.sol

87:     function setWithdrawQueue(IWithdrawQueue _withdrawQueue) external onlyRestakeManagerAdmin {

93:     function setFeeConfig(

112:     function setRestakeManager(IRestakeManager _restakeManager) external onlyRestakeManagerAdmin {

187:     function stakeEthFromQueue(

211:     function stakeEthFromQueueMulti(

254:     function sweepERC20(IERC20 token) external onlyERC20RewardsAdmin {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L87-L87) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L93-L93), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L112-L112), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L187-L187), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L211-L211), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L254-L254)


```solidity

File: contracts/Delegation/OperatorDelegator.sol

106:     function setTokenStrategy(

117:     function setDelegateAddress(

132:     function setBaseGasAmountSpent(

172:     function getStrategyIndex(IStrategy _strategy) public view returns (uint256) {

459:     function startDelayedWithdrawUnstakedETH() external onlyNativeEthRestakeAdmin {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L106-L106) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L117-L117), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L132-L132), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L172-L172), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L459-L459)


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol

37:     function deployOptimismMintableXERC20(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L37-L37) 


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

277:     function getBridgeFeeShare(uint256 _amountIn) public view returns (uint256) {

320:     function updatePriceByOwner(uint256 price) external onlyOwner {

466:     function setAllowedBridgeSweeper(address _sweeper, bool _allowed) external onlyOwner {

478:     function recoverNative(uint256 _amount, address _to) external onlyOwner {

489:     function recoverERC20(address _token, uint256 _amount, address _to) external onlyOwner {

501:     function setOraclePriceFeed(IRenzoOracleL2 _oracle) external onlyOwner {

511:     function setReceiverPriceFeed(address _receiver) external onlyOwner {

521:     function updateBridgeFeeShare(uint256 _newShare) external onlyOwner {

532:     function updateSweepBatchSize(uint256 _newBatchSize) external onlyOwner {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L277-L277) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L320-L320), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L466-L466), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L478-L478), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L489-L489), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L501-L501), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L511-L511), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L521-L521), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L532-L532)


```solidity

File: contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol

92:     function updateXRenzoBridgeL1(address _newXRenzoBridgeL1) external onlyOwner {

103:     function updateCCIPEthChainSelector(uint32 _newChainDomain) external onlyOwner {

113:     function unPause() external onlyOwner {

130:     function setRenzoDeposit(address _newXRenzoDeposit) external onlyOwner {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L92-L92) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L103-L103), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L113-L113), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L130-L130)


```solidity

File: contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol

96:     function updateXRenzoBridgeL1(address _newXRenzoBridgeL1) external onlyOwner {

107:     function updateCCIPEthChainSelector(uint64 _newChainSelector) external onlyOwner {

117:     function unPause() external onlyOwner {

134:     function setRenzoDeposit(address _newXRenzoDeposit) external onlyOwner {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L96-L96) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L107-L107), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L117-L117), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L134-L134)


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2.sol

36:     function setOracleAddress(AggregatorV3Interface _oracleAddress) external onlyOwner {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L36-L36) 


```solidity

File: contracts/Bridge/L1/xRenzoBridge.sol

294:     function recoverNative(uint256 _amount, address _to) external onlyBridgeAdmin {

305:     function recoverERC20(address _token, uint256 _amount, address _to) external onlyBridgeAdmin {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L294-L294) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L305-L305)


```solidity

File: contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol

56:     function bridgeTo(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L56-L56) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol

54:     function depositNative() public payable {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L54-L54) 


</details>


### [NC&#x2011;87] Named imports of parent contracts are missing 



*There are 68 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/token/EzEthToken.sol

//@audit `Initializable`
13: contract EzEthToken is Initializable, ERC20Upgradeable, IEzEthToken, EzEthTokenStorageV1 {

//@audit `ERC20Upgradeable`
13: contract EzEthToken is Initializable, ERC20Upgradeable, IEzEthToken, EzEthTokenStorageV1 {

//@audit `IEzEthToken`
13: contract EzEthToken is Initializable, ERC20Upgradeable, IEzEthToken, EzEthTokenStorageV1 {

//@audit `EzEthTokenStorageV1`
13: contract EzEthToken is Initializable, ERC20Upgradeable, IEzEthToken, EzEthTokenStorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L13-L13) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L13-L13), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L13-L13), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L13-L13)


```solidity

File: contracts/Withdraw/WithdrawQueue.sol

//@audit `Initializable`
12:     Initializable,

//@audit `PausableUpgradeable`
13:     PausableUpgradeable,

//@audit `ReentrancyGuardUpgradeable`
14:     ReentrancyGuardUpgradeable,

//@audit `WithdrawQueueStorageV1`
15:     WithdrawQueueStorageV1


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L12-L12) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L13-L13), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L14-L14), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L15-L15)


```solidity

File: contracts/TimelockController.sol

//@audit `AccessControl`
25: contract TimelockController is AccessControl, IERC721Receiver, IERC1155Receiver {

//@audit `IERC721Receiver`
25: contract TimelockController is AccessControl, IERC721Receiver, IERC1155Receiver {

//@audit `IERC1155Receiver`
25: contract TimelockController is AccessControl, IERC721Receiver, IERC1155Receiver {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L25-L25) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L25-L25), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L25-L25)


```solidity

File: contracts/Rewards/RewardHandler.sol

//@audit `Initializable`
16: contract RewardHandler is Initializable, ReentrancyGuardUpgradeable, RewardHandlerStorageV1 {

//@audit `ReentrancyGuardUpgradeable`
16: contract RewardHandler is Initializable, ReentrancyGuardUpgradeable, RewardHandlerStorageV1 {

//@audit `RewardHandlerStorageV1`
16: contract RewardHandler is Initializable, ReentrancyGuardUpgradeable, RewardHandlerStorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L16-L16) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L16-L16), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L16-L16)


```solidity

File: contracts/RestakeManagerStorage.sol

//@audit `IRestakeManager`
15: abstract contract RestakeManagerStorageV1 is IRestakeManager {

//@audit `RestakeManagerStorageV1`
64: abstract contract RestakeManagerStorageV2 is RestakeManagerStorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManagerStorage.sol#L15-L15) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManagerStorage.sol#L64-L64)


```solidity

File: contracts/RestakeManager.sol

//@audit `Initializable`
26: contract RestakeManager is Initializable, ReentrancyGuardUpgradeable, RestakeManagerStorageV2 {

//@audit `ReentrancyGuardUpgradeable`
26: contract RestakeManager is Initializable, ReentrancyGuardUpgradeable, RestakeManagerStorageV2 {

//@audit `RestakeManagerStorageV2`
26: contract RestakeManager is Initializable, ReentrancyGuardUpgradeable, RestakeManagerStorageV2 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L26-L26) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L26-L26), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L26-L26)


```solidity

File: contracts/RateProvider/BalancerRateProvider.sol

//@audit `Initializable`
9: contract BalancerRateProvider is Initializable, IRateProvider, BalancerRateProviderStorageV1 {

//@audit `IRateProvider`
9: contract BalancerRateProvider is Initializable, IRateProvider, BalancerRateProviderStorageV1 {

//@audit `BalancerRateProviderStorageV1`
9: contract BalancerRateProvider is Initializable, IRateProvider, BalancerRateProviderStorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProvider.sol#L9-L9) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProvider.sol#L9-L9), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProvider.sol#L9-L9)


```solidity

File: contracts/Permissions/RoleManager.sol

//@audit `IRoleManager`
14: contract RoleManager is IRoleManager, AccessControlUpgradeable, RoleManagerStorageV3 {

//@audit `AccessControlUpgradeable`
14: contract RoleManager is IRoleManager, AccessControlUpgradeable, RoleManagerStorageV3 {

//@audit `RoleManagerStorageV3`
14: contract RoleManager is IRoleManager, AccessControlUpgradeable, RoleManagerStorageV3 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L14-L14) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L14-L14), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L14-L14)


```solidity

File: contracts/Permissions/RoleManagerStorage.sol

//@audit `RoleManagerStorageV1`
37: contract RoleManagerStorageV2 is RoleManagerStorageV1 {

//@audit `RoleManagerStorageV2`
45: contract RoleManagerStorageV3 is RoleManagerStorageV2 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManagerStorage.sol#L37-L37) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManagerStorage.sol#L45-L45)


```solidity

File: contracts/Oracle/RenzoOracle.sol

//@audit `IRenzoOracle`
14:     IRenzoOracle,

//@audit `Initializable`
15:     Initializable,

//@audit `ReentrancyGuardUpgradeable`
16:     ReentrancyGuardUpgradeable,

//@audit `RenzoOracleStorageV1`
17:     RenzoOracleStorageV1


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L14-L14) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L15-L15), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L16-L16), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L17-L17)


```solidity

File: contracts/Oracle/Mantle/METHShim.sol

//@audit `Initializable`
15: contract METHShim is Initializable, METHShimStorageV1 {

//@audit `METHShimStorageV1`
15: contract METHShim is Initializable, METHShimStorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L15-L15) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L15-L15)


```solidity

File: contracts/Oracle/Mantle/METHShimStorage.sol

//@audit `AggregatorV3Interface`
7: abstract contract METHShimStorageV1 is AggregatorV3Interface {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShimStorage.sol#L7-L7) 


```solidity

File: contracts/Oracle/Binance/WBETHShimStorage.sol

//@audit `AggregatorV3Interface`
7: abstract contract WBETHShimStorageV1 is AggregatorV3Interface {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShimStorage.sol#L7-L7) 


```solidity

File: contracts/Oracle/Binance/WBETHShim.sol

//@audit `Initializable`
15: contract WBETHShim is Initializable, WBETHShimStorageV1 {

//@audit `WBETHShimStorageV1`
15: contract WBETHShim is Initializable, WBETHShimStorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L15-L15) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L15-L15)


```solidity

File: contracts/Deposits/DepositQueueStorage.sol

//@audit `IDepositQueue`
9: abstract contract DepositQueueStorageV1 is IDepositQueue {

//@audit `DepositQueueStorageV1`
26: abstract contract DepositQueueStorageV2 is DepositQueueStorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueueStorage.sol#L9-L9) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueueStorage.sol#L26-L26)


```solidity

File: contracts/Deposits/DepositQueue.sol

//@audit `Initializable`
10: contract DepositQueue is Initializable, ReentrancyGuardUpgradeable, DepositQueueStorageV2 {

//@audit `ReentrancyGuardUpgradeable`
10: contract DepositQueue is Initializable, ReentrancyGuardUpgradeable, DepositQueueStorageV2 {

//@audit `DepositQueueStorageV2`
10: contract DepositQueue is Initializable, ReentrancyGuardUpgradeable, DepositQueueStorageV2 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L10-L10) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L10-L10), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L10-L10)


```solidity

File: contracts/Delegation/OperatorDelegator.sol

//@audit `Initializable`
18:     Initializable,

//@audit `ReentrancyGuardUpgradeable`
19:     ReentrancyGuardUpgradeable,

//@audit `OperatorDelegatorStorageV4`
20:     OperatorDelegatorStorageV4


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L18-L18) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L19-L19), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L20-L20)


```solidity

File: contracts/Delegation/OperatorDelegatorStorage.sol

//@audit `IOperatorDelegator`
16: abstract contract OperatorDelegatorStorageV1 is IOperatorDelegator {

//@audit `OperatorDelegatorStorageV1`
46: abstract contract OperatorDelegatorStorageV2 is OperatorDelegatorStorageV1 {

//@audit `OperatorDelegatorStorageV2`
51: abstract contract OperatorDelegatorStorageV3 is OperatorDelegatorStorageV2 {

//@audit `OperatorDelegatorStorageV3`
59: abstract contract OperatorDelegatorStorageV4 is OperatorDelegatorStorageV3 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegatorStorage.sol#L16-L16) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegatorStorage.sol#L46-L46), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegatorStorage.sol#L51-L51), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegatorStorage.sol#L59-L59)


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20.sol

//@audit `Initializable`
17:     Initializable,


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L17-L17) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Factory.sol

//@audit `Initializable`
14: contract XERC20Factory is Initializable, IXERC20Factory {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L14-L14) 


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol

//@audit `Initializable`
14: contract OptimismMintableXERC20Factory is Initializable, XERC20Factory {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L14-L14) 


```solidity

File: contracts/Bridge/L2/xRenzoDepositStorage.sol

//@audit `IxRenzoDeposit`
9: abstract contract xRenzoDepositStorageV1 is IxRenzoDeposit {

//@audit `xRenzoDepositStorageV1`
47: abstract contract xRenzoDepositStorageV2 is xRenzoDepositStorageV1 {

//@audit `xRenzoDepositStorageV2`
52: abstract contract xRenzoDepositStorageV3 is xRenzoDepositStorageV2 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L9-L9) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L47-L47), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L52-L52)


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

//@audit `Initializable`
28:     Initializable,

//@audit `ReentrancyGuardUpgradeable`
30:     ReentrancyGuardUpgradeable,

//@audit `IRateProvider`
31:     IRateProvider,

//@audit `xRenzoDepositStorageV3`
32:     xRenzoDepositStorageV3


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L28-L28) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L30-L30), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L31-L31), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L32-L32)


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2.sol

//@audit `Initializable`
11: contract RenzoOracleL2 is Initializable, OwnableUpgradeable, RenzoOracleL2StorageV1 {

//@audit `RenzoOracleL2StorageV1`
11: contract RenzoOracleL2 is Initializable, OwnableUpgradeable, RenzoOracleL2StorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L11-L11) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L11-L11)


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2Storage.sol

//@audit `IRenzoOracleL2`
7: abstract contract RenzoOracleL2StorageV1 is IRenzoOracleL2 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2Storage.sol#L7-L7) 


```solidity

File: contracts/Bridge/L1/xRenzoBridge.sol

//@audit `IXReceiver`
17:     IXReceiver,

//@audit `Initializable`
18:     Initializable,

//@audit `ReentrancyGuardUpgradeable`
19:     ReentrancyGuardUpgradeable,

//@audit `xRenzoBridgeStorageV1`
20:     xRenzoBridgeStorageV1


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L17-L17) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L18-L18), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L19-L19), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L20-L20)


```solidity

File: contracts/Bridge/L1/xRenzoBridgeStorage.sol

//@audit `IxRenzoBridge`
18: abstract contract xRenzoBridgeStorageV1 is IxRenzoBridge {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridgeStorage.sol#L18-L18) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol

//@audit `Initializable`
11: contract XERC20Lockbox is Initializable, IXERC20Lockbox {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L11-L11) 


</details>


### [NC&#x2011;88] [NatSpec] Natspec `@notice` is missing from `contract` 



*There are 327 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/token/EzEthTokenStorage.sol

05: /// @title EzEthTokenStorage
06: /// @dev This contract will hold all local variables for the  Contract
07: /// When upgrading the protocol, inherit from this contract on the V2 version and change the
08: /// StorageManager to inherit from the later version.  This ensures there are no storage layout
09: /// corruptions when upgrading.
10: contract EzEthTokenStorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthTokenStorage.sol#L5-L10) 


```solidity

File: contracts/token/EzEthToken.sol

11: /// @dev This contract is the ezETH ERC20 token
12: /// Ownership of the collateral in the protocol is tracked by the ezETH token
13: contract EzEthToken is Initializable, ERC20Upgradeable, IEzEthToken, EzEthTokenStorageV1 {

14:     /// @dev Allows only a whitelisted address to mint or burn ezETH tokens

20:     /// @dev Allows only a whitelisted address to pause or unpause the token

26:     /// @dev Prevents implementation contract from being initialized.
27:     /// @custom:oz-upgrades-unsafe-allow constructor

32:     /// @dev Initializes the contract with initial vars

40:     /// @dev Allows minter/burner to mint new ezETH tokens to an address

45:     /// @dev Allows minter/burner to burn ezETH tokens from an address

50:     /// @dev Sets the paused flag

55:     /// @dev

74:     /**
75:      * @dev Returns the name of the token.
76:      */

81:     /**
82:      * @dev Returns the symbol of the token, usually a shorter version of the
83:      * name.
84:      */


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L11-L13) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L14-L14), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L20-L20), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L26-L27), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L32-L32), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L40-L40), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L45-L45), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L50-L50), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L55-L55), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L74-L76), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L81-L84)


```solidity

File: contracts/Withdraw/WithdrawQueue.sol

11: contract WithdrawQueue is

19:     event WithdrawBufferTargetUpdated(uint256 oldBufferTarget, uint256 newBufferTarget);

21:     event CoolDownPeriodUpdated(uint256 oldCoolDownPeriod, uint256 newCoolDownPeriod);

23:     event EthBufferFilled(uint256 amount);

25:     event ERC20BufferFilled(address asset, uint256 amount);

27:     event WithdrawRequestCreated(

36:     event WithdrawRequestClaimed(WithdrawRequest withdrawRequest);

38:     /// @dev Allows only Withdraw Queue Admin to configure the contract

44:     /// @dev Allows only RestakeManager to call the functions

50:     modifier onlyDepositQueue() {

55:     /// @dev Prevents implementation contract from being initialized.
56:     /// @custom:oz-upgrades-unsafe-allow constructor


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L11-L11) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L19-L19), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L21-L21), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L23-L23), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L25-L25), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L27-L27), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L36-L36), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L38-L38), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L44-L44), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L50-L50), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L55-L56)


```solidity

File: contracts/Withdraw/WithdrawQueueStorage.sol

9: abstract contract WithdrawQueueStorageV1 {

12:     struct TokenWithdrawBuffer {

17:     struct WithdrawRequest {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueueStorage.sol#L9-L9) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueueStorage.sol#L12-L12), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueueStorage.sol#L17-L17)


```solidity

File: contracts/TimelockController.sol

10: /**
11:  * @dev Contract module which acts as a timelocked controller. When set as the
12:  * owner of an `Ownable` smart contract, it enforces a timelock on all
13:  * `onlyOwner` maintenance operations. This gives time for users of the
14:  * controlled contract to exit before a potentially dangerous maintenance
15:  * operation is applied.
16:  *
17:  * By default, this contract is self administered, meaning administration tasks
18:  * have to go through the timelock process. The proposer (resp executor) role
19:  * is in charge of proposing (resp executing) operations. A common use case is
20:  * to position this {TimelockController} as the owner of a smart contract, with
21:  * a multisig or a DAO as the sole proposer.
22:  *
23:  * _Available since v3.3._
24:  */

35:     /**
36:      * @dev Emitted when a call is scheduled as part of operation `id`.
37:      */

48:     /**
49:      * @dev Emitted when a call is performed as part of operation `id`.
50:      */

59:     /**
60:      * @dev Emitted when new proposal is scheduled with non-zero salt.
61:      */

64:     /**
65:      * @dev Emitted when operation `id` is cancelled.
66:      */

69:     /**
70:      * @dev Emitted when the minimum delay for future operations is modified.
71:      */

74:     /**
75:      * @dev Initializes the contract with the following parameters:
76:      *
77:      * - `minDelay`: initial minimum delay for operations
78:      * - `proposers`: accounts to be granted proposer and canceller roles
79:      * - `executors`: accounts to be granted executor role
80:      * - `admin`: optional account to be granted admin role; disable with zero address
81:      *
82:      * IMPORTANT: The optional admin can aid with initial configuration of roles after deployment
83:      * without being subject to delay, but this role should be subsequently renounced in favor of
84:      * administration through timelocked proposals. Previous versions of this contract would assign
85:      * this admin to the deployer automatically and should be renounced as well.
86:      */

121:     /**
122:      * @dev Modifier to make a function callable only by a certain role. In
123:      * addition to checking the sender's role, `address(0)` 's role is also
124:      * considered. Granting a role to `address(0)` is equivalent to enabling
125:      * this role for everyone.
126:      */

134:     /**
135:      * @dev Contract might receive/hold ETH as part of the maintenance process.
136:      */

139:     /**
140:      * @dev See {IERC165-supportsInterface}.
141:      */

150:     /**
151:      * @dev Returns whether an id correspond to a registered operation. This
152:      * includes both Pending, Ready and Done operations.
153:      */

158:     /**
159:      * @dev Returns whether an operation is pending or not. Note that a "pending" operation may also be "ready".
160:      */

165:     /**
166:      * @dev Returns whether an operation is ready for execution. Note that a "ready" operation is also "pending".
167:      */

173:     /**
174:      * @dev Returns whether an operation is done or not.
175:      */

180:     /**
181:      * @dev Returns the timestamp at which an operation becomes ready (0 for
182:      * unset operations, 1 for done operations).
183:      */

188:     /**
189:      * @dev Returns the minimum delay for an operation to become valid.
190:      *
191:      * This value can be changed by executing an operation that calls `updateDelay`.
192:      */

197:     /**
198:      * @dev Returns the identifier of an operation containing a single
199:      * transaction.
200:      */

211:     /**
212:      * @dev Returns the identifier of an operation containing a batch of
213:      * transactions.
214:      */

225:     /**
226:      * @dev Schedule an operation containing a single transaction.
227:      *
228:      * Emits {CallSalt} if salt is nonzero, and {CallScheduled}.
229:      *
230:      * Requirements:
231:      *
232:      * - the caller must have the 'proposer' role.
233:      */

250:     /**
251:      * @dev Schedule an operation containing a batch of transactions.
252:      *
253:      * Emits {CallSalt} if salt is nonzero, and one {CallScheduled} event per transaction in the batch.
254:      *
255:      * Requirements:
256:      *
257:      * - the caller must have the 'proposer' role.
258:      */

280:     /**
281:      * @dev Schedule an operation that is to become valid after a given delay.
282:      */

289:     /**
290:      * @dev Cancel an operation.
291:      *
292:      * Requirements:
293:      *
294:      * - the caller must have the 'canceller' role.
295:      */

303:     /**
304:      * @dev Execute an (ready) operation containing a single transaction.
305:      *
306:      * Emits a {CallExecuted} event.
307:      *
308:      * Requirements:
309:      *
310:      * - the caller must have the 'executor' role.
311:      */

330:     /**
331:      * @dev Execute an (ready) operation containing a batch of transactions.
332:      *
333:      * Emits one {CallExecuted} event per transaction in the batch.
334:      *
335:      * Requirements:
336:      *
337:      * - the caller must have the 'executor' role.
338:      */

365:     /**
366:      * @dev Execute an operation's call.
367:      */

373:     /**
374:      * @dev Checks before execution of an operation's calls.
375:      */

384:     /**
385:      * @dev Checks after execution of an operation's calls.
386:      */

392:     /**
393:      * @dev Changes the minimum timelock duration for future operations.
394:      *
395:      * Emits a {MinDelayChange} event.
396:      *
397:      * Requirements:
398:      *
399:      * - the caller must be the timelock itself. This can only be achieved by scheduling and later executing
400:      * an operation where the timelock is the target and the data is the ABI-encoded call to this function.
401:      */

408:     /**
409:      * @dev See {IERC721Receiver-onERC721Received}.
410:      */

420:     /**
421:      * @dev See {IERC1155Receiver-onERC1155Received}.
422:      */

433:     /**
434:      * @dev See {IERC1155Receiver-onERC1155BatchReceived}.
435:      */


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L10-L24) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L35-L37), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L48-L50), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L59-L61), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L64-L66), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L69-L71), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L74-L86), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L121-L126), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L134-L136), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L139-L141), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L150-L153), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L158-L160), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L165-L167), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L173-L175), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L180-L183), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L188-L192), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L197-L200), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L211-L214), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L225-L233), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L250-L258), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L280-L282), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L289-L295), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L303-L311), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L330-L338), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L365-L367), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L373-L375), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L384-L386), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L392-L401), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L408-L410), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L420-L422), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L433-L435)


```solidity

File: contracts/Rewards/RewardHandlerStorage.sol

6: abstract contract RewardHandlerStorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandlerStorage.sol#L6-L6) 


```solidity

File: contracts/Rewards/RewardHandler.sol

17:     /// @dev Allows only a whitelisted address to trigger native ETH staking

23:     /// @dev Allows only a whitelisted address to configure the contract

29:     event RewardDestinationUpdated(address rewardDestination);

31:     /// @dev Prevents implementation contract from being initialized.
32:     /// @custom:oz-upgrades-unsafe-allow constructor

37:     /// @dev Initializes the contract with initial vars

50:     /// @dev Forwards all native ETH rewards to the DepositQueue contract
51:     /// Handle ETH sent to this contract from outside the protocol that trigger contract execution - e.g. rewards

56:     /// @dev Forwards all native ETH rewards to the DepositQueue contract
57:     /// Handle ETH sent to this contract from validator nodes that do not trigger contract execution - e.g. rewards

62:     function _forwardETH() internal {

72:     function setRewardDestination(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L17-L17) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L23-L23), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L29-L29), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L31-L32), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L37-L37), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L50-L51), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L56-L57), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L62-L62), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L72-L72)


```solidity

File: contracts/RestakeManagerStorage.sol

15: abstract contract RestakeManagerStorageV1 is IRestakeManager {

64: abstract contract RestakeManagerStorageV2 is RestakeManagerStorageV1 {

29:     struct PendingWithdrawal {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManagerStorage.sol#L15-L15) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManagerStorage.sol#L64-L64), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManagerStorage.sol#L29-L29)


```solidity

File: contracts/RestakeManager.sol

19: /**
20:  * @author  Renzo
21:  * @title   RestakeManager
22:  * @dev     This contract is the main entrypoint for external users into the protocol
23:             Users will interact with this contract to deposit and withdraw value into and from EigenLayer
24:             Ownership of deposited funds will be tracked via the ezETh token
25:  */

30:     event OperatorDelegatorAdded(IOperatorDelegator od);

31:     event OperatorDelegatorRemoved(IOperatorDelegator od);

32:     event OperatorDelegatorAllocationUpdated(IOperatorDelegator od, uint256 allocation);

34:     event CollateralTokenAdded(IERC20 token);

35:     event CollateralTokenRemoved(IERC20 token);

40:     /// @dev Event emitted when a new deposit occurs

49:     /// @dev Event emitted when a new withdraw is started

58:     /// @dev Event emitted when a new withdraw is completed

67:     /// @dev Event emitted when a token TVL Limit is updated

70:     /// @dev Allows only a whitelisted address to configure the contract

76:     /// @dev Allows only a whitelisted address to set pause state

82:     /// @dev Allows only the deposit queue to call functions

88:     /// @dev Only allows execution if contract is not paused

94:     /// @dev Prevents implementation contract from being initialized.
95:     /// @custom:oz-upgrades-unsafe-allow constructor

100:     /// @dev Initializes the contract with initial vars

120:     /// @dev Allows a restake manager admin to set the paused state of the contract

125:     /// @dev Get the length of the operator delegators array

130:     /// @dev Allows a restake manager admin to add an OperatorDelegator to the list

159:     /// @dev Allows a restake manager admin to remove an OperatorDelegator from the list

186:     /// @dev Allows restake manager admin to set an OperatorDelegator allocation

214:     /// @dev Allows a restake manager admin to set the max TVL for deposits.  If set to 0, no deposits will be enforced.

219:     /// @dev Allows restake manager to add a collateral token

243:     /// @dev Allows restake manager to remove a collateral token

265:     /// @dev Get the length of the collateral tokens array

270:     /// @dev This function calculates the TVLs for each operator delegator by individual token, total for each OD, and total for the protocol.
271:     /// @return operatorDelegatorTokenTVLs Each OD's TVL indexed by operatorDelegators array by collateralTokens array
272:     /// @return operatorDelegatorTVLs Each OD's Total TVL in order of operatorDelegators array
273:     /// @return totalTVL The total TVL across all operator delegators.

360:     /// @dev Picks the OperatorDelegator with the TVL below the threshold or returns the first one in the list
361:     /// @return The OperatorDelegator to use

395:     /// @dev Determines the OD to withdraw from
396:     /// It will try to use the OD with the TVL above the allocation threshold that has the tokens to withdraw
397:     /// If no OD is over the allocation and has tokens, it will try to find one that has the tokens to withdraw
398:     /// If no OD has the tokens to withdraw, it will revert
399:     /// @return The OperatorDelegator to use

449:     /// @dev Finds the index of the collateral token in the list
450:     /// Reverts if the token is not found in the list

618:     /// @dev Called by the deposit queue to stake ETH to a validator
619:     /// Only callable by the deposit queue

645:     /// @dev Deposit ERC20 token rewards from the Deposit Queue
646:     /// Only callable by the deposit queue

709:     function setTokenTvlLimit(IERC20 _token, uint256 _limit) external onlyRestakeManagerAdmin {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L19-L25) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L30-L30), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L31-L31), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L32-L32), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L34-L34), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L35-L35), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L40-L40), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L49-L49), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L58-L58), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L67-L67), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L70-L70), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L76-L76), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L82-L82), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L88-L88), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L94-L95), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L100-L100), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L120-L120), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L125-L125), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L130-L130), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L159-L159), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L186-L186), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L214-L214), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L219-L219), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L243-L243), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L265-L265), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L270-L273), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L360-L361), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L395-L399), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L449-L450), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L618-L619), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L645-L646), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L709-L709)


```solidity

File: contracts/RateProvider/BalancerRateProvider.sol

9: contract BalancerRateProvider is Initializable, IRateProvider, BalancerRateProviderStorageV1 {

10:     /// @dev Prevents implementation contract from being initialized.
11:     /// @custom:oz-upgrades-unsafe-allow constructor

16:     /// @dev Initializes the contract with initial vars

28:     /// @dev Returns the current rate of ezETH in ETH


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProvider.sol#L9-L9) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProvider.sol#L10-L11), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProvider.sol#L16-L16), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProvider.sol#L28-L28)


```solidity

File: contracts/RateProvider/BalancerRateProviderStorage.sol

7: abstract contract BalancerRateProviderStorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProviderStorage.sol#L7-L7) 


```solidity

File: contracts/Permissions/RoleManager.sol

09: /// @title RoleManager
10: /// @dev This contract will track the roles and permissions in the protocol
11: /// Note: This contract is protected via a permissioned account set via the initializer.  Caution should
12: /// be used as the owner could renounce the role leaving all future actions disabled.  Additionally,
13: /// if a malicious account was able to obtain the role, they could use it to grant permissions to malicious accounts.
14: contract RoleManager is IRoleManager, AccessControlUpgradeable, RoleManagerStorageV3 {

15:     /// @dev Prevents implementation contract from being initialized.
16:     /// @custom:oz-upgrades-unsafe-allow constructor

21:     /// @dev initializer to call after deployment, can only be called once

30:     /// @dev Determines if the specified address has permissions to manage RoleManager
31:     /// @param potentialAddress Address to check

36:     /// @dev Determines if the specified address has permission to mint or burn ezETH tokens
37:     /// @param potentialAddress Address to check

42:     /// @dev Determines if the specified address has permission to update config on the OperatorDelgator Contracts
43:     /// @param potentialAddress Address to check

48:     /// @dev Determines if the specified address has permission to update config on the Oracle Contract config
49:     /// @param potentialAddress Address to check

54:     /// @dev Determines if the specified address has permission to update config on the RestakeManager Contract config
55:     /// @param potentialAddress Address to check

60:     /// @dev Determines if the specified address has permission to update config on the Token Contract
61:     /// @param potentialAddress Address to check

66:     /// @dev Determines if the specified address has permission to trigger restaking of native ETH
67:     /// @param potentialAddress Address to check

72:     /// @dev Determines if the specified address has permission to sweep and deposit ERC20 Rewards
73:     /// @param potentialAddress Address to check

78:     /// @dev Determines if the specified address has permission to pause deposits and withdraws
79:     /// @param potentialAddress Address to check

84:     /// @dev Determines if the specified address has permission to set whitelisted origin in xRenzoBridge
85:     /// @param potentialAddress Address to check

90:     /// @dev Determined if the specified address has permission to send price feed of ezETH to L2
91:     /// @param potentialAddress Address to check

96:     /// @dev Determine if the specified address haas permission to update Withdraw Queue params
97:     /// @param potentialAddress Address to check


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L9-L14) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L15-L16), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L21-L21), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L30-L31), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L36-L37), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L42-L43), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L48-L49), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L54-L55), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L60-L61), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L66-L67), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L72-L73), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L78-L79), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L84-L85), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L90-L91), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L96-L97)


```solidity

File: contracts/Permissions/RoleManagerStorage.sol

4: /// @title RoleManagerStorage
5: /// @dev This contract will hold all local variables for the RoleManager Contract
6: /// When upgrading the protocol, inherit from this contract on the V2 version and change the
7: /// StorageManager to inherit from the later version.  This ensures there are no storage layout
8: /// corruptions when upgrading.
9: contract RoleManagerStorageV1 {

35: /// On the next version of the protocol, if new variables are added, put them in the below
36: /// contract and use this as the inheritance chain.
37: contract RoleManagerStorageV2 is RoleManagerStorageV1 {

45: contract RoleManagerStorageV3 is RoleManagerStorageV2 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManagerStorage.sol#L4-L9) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManagerStorage.sol#L35-L37), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManagerStorage.sol#L45-L45)


```solidity

File: contracts/Oracle/RenzoOracle.sol

10: /// @dev This contract will be responsible for looking up values via Chainlink
11: /// Data retrieved will be verified for liveness via a max age on the oracle lookup.
12: /// All tokens should be denominated in the same base currency and contain the same decimals on the price lookup.
13: contract RenzoOracle is

28:     /// @dev Allows only a whitelisted address to configure the contract

34:     /// @dev Event emitted when a token's oracle address is updated

37:     /// @dev Prevents implementation contract from being initialized.
38:     /// @custom:oz-upgrades-unsafe-allow constructor

43:     /// @dev Initializes the contract with initial vars

52:     /// @dev Sets addresses for oracle lookup.  Permission gated to oracel admins only.
53:     /// Set to address 0x0 to disable lookups for the token.

68:     /// @dev Given a single token and balance, return value of the asset in underlying currency
69:     /// The value returned will be denominated in the decimal precision of the lookup oracle
70:     /// (e.g. a value of 100 would return as 100 * 10^18)

83:     /// @dev Given a single token and value, return amount of tokens needed to represent that value
84:     /// Assumes the token value is already denominated in the same decimal precision as the oracle

101:     /// The value returned will be denominated in the decimal precision of the lookup oracle
102:     /// (e.g. a value of 100 would return as 100 * 10^18)

121:     /// @dev Given amount of current protocol value, new value being added, and supply of ezETH, determine amount to mint
122:     /// Values should be denominated in the same underlying currency with the same decimal precision

152:     function calculateRedeemAmount(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L10-L13) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L28-L28), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L34-L34), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L37-L38), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L43-L43), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L52-L53), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L68-L70), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L83-L84), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L101-L102), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L121-L122), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L152-L152)


```solidity

File: contracts/Oracle/RenzoOracleStorage.sol

8: abstract contract RenzoOracleStorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracleStorage.sol#L8-L8) 


```solidity

File: contracts/Oracle/Mantle/METHShim.sol

16:     /// @dev Prevents implementation contract from being initialized.
17:     /// @custom:oz-upgrades-unsafe-allow constructor

22:     /// @dev Initializes the contract with initial vars

29:     function decimals() external pure returns (uint8) {

33:     function description() external pure returns (string memory) {

37:     function version() external pure returns (uint256) {

41:     /// @dev Historical data not available

46:     function latestRoundData()


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L16-L17) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L22-L22), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L29-L29), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L33-L33), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L37-L37), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L41-L41), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L46-L46)


```solidity

File: contracts/Oracle/Mantle/METHShimStorage.sol

7: abstract contract METHShimStorageV1 is AggregatorV3Interface {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShimStorage.sol#L7-L7) 


```solidity

File: contracts/Oracle/Binance/WBETHShimStorage.sol

7: abstract contract WBETHShimStorageV1 is AggregatorV3Interface {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShimStorage.sol#L7-L7) 


```solidity

File: contracts/Oracle/Binance/WBETHShim.sol

16:     /// @dev Prevents implementation contract from being initialized.
17:     /// @custom:oz-upgrades-unsafe-allow constructor

22:     /// @dev Initializes the contract with initial vars

29:     function decimals() external pure returns (uint8) {

33:     function description() external pure returns (string memory) {

37:     function version() external pure returns (uint256) {

41:     /// @dev Historical data not available

46:     function latestRoundData()


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L16-L17) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L22-L22), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L29-L29), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L33-L33), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L37-L37), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L41-L41), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L46-L46)


```solidity

File: contracts/Errors/Errors.sol

4: /// @dev Error for 0x0 address inputs
5: error InvalidZeroInput();

7: /// @dev Error for already added items to a list
8: error AlreadyAdded();

10: /// @dev Error for not found items in a list
11: error NotFound();

13: /// @dev Error for hitting max TVL
14: error MaxTVLReached();

16: /// @dev Error for caller not having permissions
17: error NotRestakeManagerAdmin();

19: /// @dev Error for call not coming from deposit queue contract
20: error NotDepositQueue();

22: /// @dev Error for contract being paused
23: error ContractPaused();

25: /// @dev Error for exceeding max basis points (100%)
26: error OverMaxBasisPoints();

28: /// @dev Error for invalid token decimals for collateral tokens (must be 18)
29: error InvalidTokenDecimals(uint8 expected, uint8 actual);

31: /// @dev Error when withdraw is already completed
32: error WithdrawAlreadyCompleted();

34: /// @dev Error when a different address tries to complete withdraw
35: error NotOriginalWithdrawCaller(address expectedCaller);

37: /// @dev Error when caller does not have OD admin role
38: error NotOperatorDelegatorAdmin();

40: /// @dev Error when caller does not have Oracle Admin role
41: error NotOracleAdmin();

43: /// @dev Error when caller is not RestakeManager contract
44: error NotRestakeManager();

46: /// @dev Errror when caller does not have ETH Restake Admin role
47: error NotNativeEthRestakeAdmin();

49: /// @dev Error when delegation address was already set - cannot be set again
50: error DelegateAddressAlreadySet();

52: /// @dev Error when caller does not have ERC20 Rewards Admin role
53: error NotERC20RewardsAdmin();

55: /// @dev Error when ending ETH fails
56: error TransferFailed();

58: /// @dev Error when caller does not have ETH Minter Burner Admin role
59: error NotEzETHMinterBurner();

61: /// @dev Error when caller does not have Token Admin role
62: error NotTokenAdmin();

64: /// @dev Error when price oracle is not configured
65: error OracleNotFound();

67: /// @dev Error when price oracle data is stale
68: error OraclePriceExpired();

70: /// @dev Error when array lengths do not match
71: error MismatchedArrayLengths();

73: /// @dev Error when caller does not have Deposit Withdraw Pauser role
74: error NotDepositWithdrawPauser();

76: /// @dev Error when an individual token TVL is over the max
77: error MaxTokenTVLReached();

79: /// @dev Error when Oracle price is invalid
80: error InvalidOraclePrice();

82: /// @dev Error when calling an invalid function
83: error NotImplemented();

85: /// @dev Error when calculating token amounts is invalid
86: error InvalidTokenAmount();

88: /// @dev Error when timestamp is invalid - likely in the past
89: error InvalidTimestamp(uint256 timestamp);

91: /// @dev Error when trade does not meet minimum output amount
92: error InsufficientOutputAmount();

94: /// @dev Error when the token received over the bridge is not the one expected
95: error InvalidTokenReceived();

97: /// @dev Error when the origin address is not whitelisted
98: error InvalidOrigin();

100: /// @dev Error when the sender is not expected
101: error InvalidSender(address expectedSender, address actualSender);

103: /// @dev error when function returns 0 amount
104: error InvalidZeroOutput();

106: /// @dev error when xRenzoBridge does not have enough balance to pay for fee
107: error NotEnoughBalance(uint256 currentBalance, uint256 calculatedFees);

109: /// @dev error when source chain is not expected
110: error InvalidSourceChain(uint64 expectedCCIPChainSelector, uint64 actualCCIPChainSelector);

112: /// @dev Error when an unauthorized address tries to call the bridge function on the L2
113: error UnauthorizedBridgeSweeper();

115: /// @dev Error when caller does not have BRIDGE_ADMIN role
116: error NotBridgeAdmin();

118: /// @dev Error when caller does not have PRICE_FEED_SENDER role
119: error NotPriceFeedSender();

121: /// @dev Error for connext price Feed unauthorised call
122: error UnAuthorisedCall();

124: /// @dev Error for no price feed configured on L2
125: error PriceFeedNotAvailable();

127: /// @dev Error for invalid bridge fee share configuration
128: error InvalidBridgeFeeShare(uint256 bridgeFee);

130: /// @dev Error for invalid sweep batch size
131: error InvalidSweepBatchSize(uint256 batchSize);

133: /// @dev Error when caller does not have Withdraw Queue admin role
134: error NotWithdrawQueueAdmin();

136: /// @dev Error when caller try to withdraw more than Buffer
137: error NotEnoughWithdrawBuffer();

139: /// @dev Error when caller try to claim withdraw before cooldown period
140: error EarlyClaim();

142: /// @dev Error when caller try to withdraw for unsupported asset
143: error UnsupportedWithdrawAsset();

145: /// @dev Error when caller try to claim invalidWithdrawIndex
146: error InvalidWithdrawIndex();


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L4-L5) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L7-L8), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L10-L11), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L13-L14), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L16-L17), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L19-L20), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L22-L23), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L25-L26), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L28-L29), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L31-L32), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L34-L35), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L37-L38), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L40-L41), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L43-L44), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L46-L47), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L49-L50), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L52-L53), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L55-L56), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L58-L59), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L61-L62), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L64-L65), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L67-L68), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L70-L71), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L73-L74), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L76-L77), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L79-L80), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L82-L83), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L85-L86), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L88-L89), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L91-L92), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L94-L95), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L97-L98), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L100-L101), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L103-L104), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L106-L107), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L109-L110), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L112-L113), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L115-L116), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L118-L119), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L121-L122), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L124-L125), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L127-L128), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L130-L131), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L133-L134), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L136-L137), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L139-L140), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L142-L143), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L145-L146)


```solidity

File: contracts/Deposits/DepositQueueStorage.sol

9: abstract contract DepositQueueStorageV1 is IDepositQueue {

26: abstract contract DepositQueueStorageV2 is DepositQueueStorageV1 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueueStorage.sol#L9-L9) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueueStorage.sol#L26-L26)


```solidity

File: contracts/Deposits/DepositQueue.sol

10: contract DepositQueue is Initializable, ReentrancyGuardUpgradeable, DepositQueueStorageV2 {

15:     event RewardsDeposited(IERC20 token, uint256 amount);

17:     event FeeConfigUpdated(address feeAddress, uint256 feeBasisPoints);

19:     event RestakeManagerUpdated(IRestakeManager restakeManager);

21:     event ETHDepositedFromProtocol(uint256 amount);

23:     event ETHStakedFromQueue(

30:     event ProtocolFeesPaid(IERC20 token, uint256 amount, address destination);

32:     event GasRefunded(address admin, uint256 gasRefunded);

34:     /// @dev Event emitted when withdrawQueue is updated

37:     /// @dev Event emitted when withdrawQueue buffer is filled for specified token

40:     /// @dev Event emitted when Full Withdrawal ETH is Received from Operator Delegators

43:     /// @dev Allows only a whitelisted address to configure the contract

49:     /// @dev Allows only the RestakeManager address to call functions

55:     /// @dev Allows only a whitelisted address to trigger native ETH staking

61:     /// @dev Allows only a whitelisted address to trigger ERC20 rewards sweeping

67:     /// @dev Prevents implementation contract from being initialized.
68:     /// @custom:oz-upgrades-unsafe-allow constructor

73:     /// @dev Initializes the contract with initial vars

92:     /// @dev Sets the config for fees - if either value is set to 0 then fees are disabled

111:     /// @dev Sets the address of the RestakeManager contract

120:     /// @dev Handle ETH sent to the protocol through the RestakeManager - e.g. user deposits
121:     /// ETH will be stored here until used for a validator deposit
122:     /// Fill the ETH withdraw buffer if required

158:     /// @dev Handle ETH sent to this contract from outside the protocol - e.g. rewards
159:     /// ETH will be stored here until used for a validator deposit
160:     /// This should receive ETH from scenarios like Execution Layer Rewards and MEV from native staking
161:     /// Users should NOT send ETH directly to this contract unless they want to donate to existing ezETH holders
162:     /// Checks the ETH withdraw Queue and fills up if required

185:     /// @dev Function called by ETH Restake Admin to start the restaking process in Native ETH
186:     /// Only callable by a permissioned account

208:     /// @dev Function called by ETH Restake Admin to start the restaking process in Native ETH
209:     /// Only callable by a permissioned account
210:     /// Can stake multiple validators with 1 tx

252:     /// @dev Sweeps any accumulated ERC20 tokens in this contract to the RestakeManager
253:     /// Only callable by a permissioned account


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L10-L10) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L15-L15), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L17-L17), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L19-L19), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L21-L21), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L23-L23), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L30-L30), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L32-L32), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L34-L34), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L37-L37), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L40-L40), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L43-L43), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L49-L49), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L55-L55), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L61-L61), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L67-L68), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L73-L73), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L92-L92), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L111-L111), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L120-L122), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L158-L162), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L185-L186), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L208-L210), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L252-L253)


```solidity

File: contracts/Delegation/OperatorDelegator.sol

12: /// @dev This contract will be responsible for interacting with Eigenlayer
13: /// Each of these contracts deployed will be delegated to one specific operator
14: /// This contract can handle multiple ERC20 tokens, all of which will be delegated to the same operator
15: /// Each supported ERC20 token will be pointed at a single Strategy contract in EL
16: /// Only the RestakeManager should be interacting with this contract for EL interactions.
17: contract OperatorDelegator is

28:     event TokenStrategyUpdated(IERC20 token, IStrategy strategy);

29:     event DelegationAddressUpdated(address delegateAddress);

30:     event RewardsForwarded(address rewardDestination, uint256 amount);

32:     event WithdrawStarted(

43:     event WithdrawCompleted(bytes32 withdrawalRoot, IStrategy[] strategies, uint256[] shares);

45:     event GasSpent(address admin, uint256 gasSpent);

46:     event GasRefunded(address admin, uint256 gasRefunded);

47:     event BaseGasAmountSpentUpdated(uint256 oldBaseGasAmountSpent, uint256 newBaseGasAmountSpent);

49:     /// @dev Allows only a whitelisted address to configure the contract

55:     /// @dev Allows only the RestakeManager address to call functions

61:     /// @dev Allows only a whitelisted address to configure the contract

67:     /// @dev Prevents implementation contract from being initialized.
68:     /// @custom:oz-upgrades-unsafe-allow constructor

73:     /// @dev Initializes the contract with initial vars

099:     /// @dev Migrates the M1 pods to M2 pods by calling activateRestaking on eigenPod
100:     /// @dev Should be a permissioned call by onlyNativeEthRestakeAdmin

105:     /// @dev Sets the strategy for a given token - setting strategy to 0x0 removes the ability to deposit and withdraw token

116:     /// @dev Sets the address to delegate tokens to in EigenLayer -- THIS CAN ONLY BE SET ONCE

132:     function setBaseGasAmountSpent(

140:     /// @dev Deposit tokens into the EigenLayer.  This call assumes any balance of tokens in this contract will be delegated
141:     /// so do not directly send tokens here or they will be delegated and attributed to the next caller.
142:     /// @return shares The amount of new shares in the `strategy` created as part of the action.

171:     /// @dev Gets the index of the specific strategy in EigenLayer in the staker's strategy list

326:     /// @dev Gets the underlying token amount from the amount of shares + queued withdrawal shares

337:     /// @dev Gets the amount of ETH staked in the EigenLayer

347:     /// @dev Stake ETH in the EigenLayer
348:     /// Only the Restake Manager should call this function

361:     /// @dev Verifies the withdrawal credentials for a withdrawal
362:     /// This will allow the EigenPodManager to verify the withdrawal credentials and credit the OD with shares
363:     /// Only the native eth restake admin should call this function


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L12-L17) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L28-L28), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L29-L29), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L30-L30), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L32-L32), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L43-L43), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L45-L45), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L46-L46), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L47-L47), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L49-L49), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L55-L55), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L61-L61), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L67-L68), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L73-L73), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L99-L100), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L105-L105), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L116-L116), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L132-L132), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L140-L142), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L171-L171), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L326-L326), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L337-L337), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L347-L348), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L361-L363)


```solidity

File: contracts/Delegation/OperatorDelegatorStorage.sol

11: /// @title OperatorDelegatorStorage
12: /// @dev This contract will hold all local variables for the  Contract
13: /// When upgrading the protocol, inherit from this contract on the V2 version and change the
14: /// StorageManager to inherit from the later version.  This ensures there are no storage layout
15: /// corruptions when upgrading.
16: abstract contract OperatorDelegatorStorageV1 is IOperatorDelegator {

46: abstract contract OperatorDelegatorStorageV2 is OperatorDelegatorStorageV1 {

51: abstract contract OperatorDelegatorStorageV3 is OperatorDelegatorStorageV2 {

59: abstract contract OperatorDelegatorStorageV4 is OperatorDelegatorStorageV3 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegatorStorage.sol#L11-L16) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegatorStorage.sol#L46-L46), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegatorStorage.sol#L51-L51), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegatorStorage.sol#L59-L59)


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20.sol

16: contract XERC20 is

48:     /// @dev Prevents implementation contract from being initialized.
49:     /// @custom:oz-upgrades-unsafe-allow constructor


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L16-L16) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L48-L49)


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Factory.sol

14: contract XERC20Factory is Initializable, IXERC20Factory {

42:     /// @dev Prevents implementation contract from being initialized.
43:     /// @custom:oz-upgrades-unsafe-allow constructor


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L14-L14) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L42-L43)


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol

11: contract OptimismMintableXERC20 is ERC165Upgradeable, XERC20, IOptimismMintableERC20 {

22:     /// @dev Prevents implementation contract from being initialized.
23:     /// @custom:oz-upgrades-unsafe-allow constructor

48:     function supportsInterface(

56:     function remoteToken() public view override returns (address) {

60:     function bridge() public view override returns (address) {

64:     function mint(address _to, uint256 _amount) public override(XERC20, IOptimismMintableERC20) {

68:     function burn(address _from, uint256 _amount) public override(XERC20, IOptimismMintableERC20) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L11-L11) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L22-L23), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L48-L48), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L56-L56), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L60-L60), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L64-L64), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L68-L68)


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol

14: contract OptimismMintableXERC20Factory is Initializable, XERC20Factory {

15:     error OptimismMintableXERC20Factory_NoBridges();

17:     /// @dev Prevents implementation contract from being initialized.
18:     /// @custom:oz-upgrades-unsafe-allow constructor


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L14-L14) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L15-L15), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L17-L18)


```solidity

File: contracts/Bridge/L2/xRenzoDepositStorage.sol

9: abstract contract xRenzoDepositStorageV1 is IxRenzoDeposit {

47: abstract contract xRenzoDepositStorageV2 is xRenzoDepositStorageV1 {

52: abstract contract xRenzoDepositStorageV3 is xRenzoDepositStorageV2 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L9-L9) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L47-L47), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L52-L52)


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

42:     event PriceUpdated(uint256 price, uint256 timestamp);

43:     event Deposit(address indexed user, uint256 amountIn, uint256 amountOut);

44:     event BridgeSweeperAddressUpdated(address sweeper, bool allowed);

45:     event BridgeSwept(

51:     event OraclePriceFeedUpdated(address newOracle, address oldOracle);

52:     event ReceiverPriceFeedUpdated(address newReceiver, address oldReceiver);

53:     event SweeperBridgeFeeCollected(address sweeper, uint256 feeCollected);

54:     event BridgeFeeShareUpdated(uint256 oldBridgeFeeShare, uint256 newBridgeFeeShare);

55:     event SweepBatchSizeUpdated(uint256 oldSweepBatchSize, uint256 newSweepBatchSize);

57:     /// @dev Prevents implementation contract from being initialized.
58:     /// @custom:oz-upgrades-unsafe-allow constructor


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L42-L42) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L43-L43), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L44-L44), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L45-L45), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L51-L51), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L52-L52), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L53-L53), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L54-L54), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L55-L55), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L57-L58)


```solidity

File: contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol

10: contract ConnextReceiver is IXReceiver, Ownable, Pausable {

23:     event XRenzoBridgeL1Updated(address newBridgeAddress, address oldBridgeAddress);

24:     event ConnextEthChainDomainUpdated(uint32 newSourceChainDomain, uint32 oldSourceChainDomain);

25:     event XRenzoDepositUpdated(address newRenzoDeposit, address oldRenzoDeposit);

27:     /**
28:      *  @dev Event emitted when a message is received from another chain
29:      *  @param messageId  The unique ID of the message
30:      *  @param sourceChainDomain  The chain domain id of the source chain
31:      *  @param sender  The address of the sender from the source chain.
32:      *  @param price  The price feed received on L2.
33:      *  @param timestamp  The timestamp when price feed was sent from L1.
34:      */

43:     modifier onlySource(address _originSender, uint32 _origin) {

52:     constructor(address _connext, address _xRenzoBridgeL1, uint32 _connextEthChainDomain) {

69:     function xReceive(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L10-L10) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L23-L23), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L24-L24), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L25-L25), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L27-L34), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L43-L43), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L52-L52), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L69-L69)


```solidity

File: contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol

13: /// @title CCIPReceiver - Base contract for CCIP applications that can receive messages.
14: contract Receiver is CCIPReceiver, Ownable, Pausable {

24:     event XRenzoBridgeL1Updated(address newBridgeAddress, address oldBridgeAddress);

25:     event CCIPEthChainSelectorUpdated(uint64 newSourceChainSelector, uint64 oldSourceChainSelector);

26:     event XRenzoDepositUpdated(address newRenzoDeposit, address oldRenzoDeposit);

27:     /**
28:      *  @dev Event emitted when a message is received from another chain
29:      *  @param messageId  The unique ID of the message
30:      *  @param sourceChainSelector  The chain selector of the source chain
31:      *  @param sender  The address of the sender from the source chain.
32:      *  @param price  The price feed received on L2.
33:      *  @param timestamp  The timestamp when price feed was sent from L1.
34:      */

43:     constructor(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L13-L14) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L24-L24), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L25-L25), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L26-L26), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L27-L34), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L43-L43)


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2.sol

11: contract RenzoOracleL2 is Initializable, OwnableUpgradeable, RenzoOracleL2StorageV1 {

15:     event OracleAddressUpdated(address newOracle, address oldOracle);

17:     /// @dev Prevents implementation contract from being initialized.
18:     /// @custom:oz-upgrades-unsafe-allow constructor

23:     function initialize(AggregatorV3Interface _oracle) public initializer {

35:     /// @dev Sets addresses for oracle lookup.  Permission gated to owner only.


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L11-L11) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L15-L15), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L17-L18), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L23-L23), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L35-L35)


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2Storage.sol

7: abstract contract RenzoOracleL2StorageV1 is IRenzoOracleL2 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2Storage.sol#L7-L7) 


```solidity

File: contracts/Bridge/L1/xRenzoBridge.sol

16: contract xRenzoBridge is

24:     /// @dev Event emitted when bridge triggers ezETH mint

33:     /// @dev Event emitted when a message is sent to another chain.

43:     event ConnextMessageSent(

50:     modifier onlyBridgeAdmin() {

55:     modifier onlyPriceFeedSender() {

63:     /// @dev Prevents implementation contract from being initialized.
64:     /// @custom:oz-upgrades-unsafe-allow constructor

69:     /// @dev Initializes the contract with initial vars


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L16-L16) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L24-L24), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L33-L33), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L43-L43), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L50-L50), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L55-L55), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L63-L64), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L69-L69)


```solidity

File: contracts/Bridge/L1/xRenzoBridgeStorage.sol

18: abstract contract xRenzoBridgeStorageV1 is IxRenzoBridge {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridgeStorage.sol#L18-L18) 


```solidity

File: contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol

9: interface IXERC20Registry {

17: interface L1StandardBridge {

10:     function getXERC20(address erc20) external view returns (address xerc20);

12:     function getERC20(address xerc20) external view returns (address erc20);

14:     function getLockbox(address erc20) external view returns (address xerc20);

18:     function bridgeERC20To(

35:     error InvalidRemoteToken(address _remoteToken);

36:     error AmountLessThanZero();

37:     error InvalidAddress();

39:     constructor(address _blastStandardBridge, address _registry) {

49:     /// @dev Combines Lockbox deposit and Blast bridge's BridgeERC20To call.
50:     /// @param _to The recipient or contract address on destination.
51:     /// @param _erc20 The address of the adopted ERC20 on the origin chain.
52:     /// @param _remoteToken The address of the asset to be received on the destination chain.
53:     /// @param _amount The amount of asset to bridge.
54:     /// @param _minGasLimit Minimum amount of gas that the bridge can be relayed with.
55:     /// @param _extraData Extra data to be sent with the transaction.


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L9-L9) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L17-L17), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L10-L10), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L12-L12), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L14-L14), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L18-L18), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L35-L35), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L36-L36), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L37-L37), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L39-L39), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L49-L55)


```solidity

File: contracts/Bridge/Connext/libraries/LibConnextStorage.sol

38: struct TransferInfo {

64: struct ExecuteArgs {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/libraries/LibConnextStorage.sol#L38-L38) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/libraries/LibConnextStorage.sol#L64-L64)


```solidity

File: contracts/Bridge/Connext/libraries/TokenId.sol

9: struct TokenId {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/libraries/TokenId.sol#L9-L9) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol

11: contract XERC20Lockbox is Initializable, IXERC20Lockbox {

31:     /// @dev Prevents implementation contract from being initialized.
32:     /// @custom:oz-upgrades-unsafe-allow constructor


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L11-L11) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L31-L32)


</details>


### [NC&#x2011;89] `contract` names should use CamelCase 



*There are 6 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Bridge/L2/xRenzoDepositStorage.sol

//@audit `xRenzoDepositStorageV1` is not in CamelCase
9: abstract contract xRenzoDepositStorageV1 is IxRenzoDeposit {

//@audit `xRenzoDepositStorageV2` is not in CamelCase
47: abstract contract xRenzoDepositStorageV2 is xRenzoDepositStorageV1 {

//@audit `xRenzoDepositStorageV3` is not in CamelCase
52: abstract contract xRenzoDepositStorageV3 is xRenzoDepositStorageV2 {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L9-L9) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L47-L47), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L52-L52)


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

//@audit `xRenzoDeposit` is not in CamelCase
27: contract xRenzoDeposit is


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L27-L27) 


```solidity

File: contracts/Bridge/L1/xRenzoBridge.sol

//@audit `xRenzoBridge` is not in CamelCase
16: contract xRenzoBridge is


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L16-L16) 


```solidity

File: contracts/Bridge/L1/xRenzoBridgeStorage.sol

//@audit `xRenzoBridgeStorageV1` is not in CamelCase
18: abstract contract xRenzoBridgeStorageV1 is IxRenzoBridge {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridgeStorage.sol#L18-L18) 


</details>


### [NC&#x2011;90] Expressions for constant values should use `immutable` rather than `constant` 
While it does not save gas for some simple binary expressions because the compiler knows that developers often make this mistake, it's still best to use the right tool for the task at hand. There is a difference between `constant` variables and `immutable` variables, and they should each be used in their appropriate contexts. `constants` should be used for literal values written into the code, and `immutable` variables should be used for expressions, or values calculated in, or passed into the constructor.


*There are 19 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/TimelockController.sol

26:     bytes32 public constant TIMELOCK_ADMIN_ROLE = keccak256("TIMELOCK_ADMIN_ROLE");

27:     bytes32 public constant PROPOSER_ROLE = keccak256("PROPOSER_ROLE");

28:     bytes32 public constant EXECUTOR_ROLE = keccak256("EXECUTOR_ROLE");

29:     bytes32 public constant CANCELLER_ROLE = keccak256("CANCELLER_ROLE");

30:     uint256 internal constant _DONE_TIMESTAMP = uint256(1);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L26-L26) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L27-L27), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L28-L28), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L29-L29), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L30-L30)


```solidity

File: contracts/Permissions/RoleManagerStorage.sol

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

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManagerStorage.sol#L11-L11) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManagerStorage.sol#L14-L14), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManagerStorage.sol#L17-L17), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManagerStorage.sol#L20-L20), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManagerStorage.sol#L23-L23), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManagerStorage.sol#L26-L26), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManagerStorage.sol#L29-L29), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManagerStorage.sol#L32-L32), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManagerStorage.sol#L39-L39), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManagerStorage.sol#L42-L42), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManagerStorage.sol#L47-L47)


```solidity

File: contracts/Oracle/RenzoOracle.sol

23:     uint256 constant SCALE_FACTOR = 10 ** 18;

26:     uint256 constant MAX_TIME_WINDOW = 86400 + 60; // 24 hours + 60 seconds


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L23-L23) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L26-L26)


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2.sol

13:     uint256 public constant MAX_TIME_WINDOW = 86400 + 60; // 24 hours + 60 seconds


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L13-L13) 


</details>


### [NC&#x2011;91] Consider using `AccessControlDefaultAdminRules` rather than `AccessControl` 
These contracts inherits from the OpenZeppelin's AccessControl library. However, this library does not follow some security best practices, for example, the DEFAULT_ADMIN_ROLE is also its own admin, meaning it has permissions to grant and revoke this role [ref](https://docs.openzeppelin.com/contracts/3.x/access-control). \nConsider following security best practices and OpenZeppelin's recommendations, and use the AccessControlDefaultAdminRules extension to enforce additional security measures over this role.[ref](https://docs.openzeppelin.com/contracts/5.x/api/access#AccessControlDefaultAdminRules)


*There are 1 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/TimelockController.sol

25: contract TimelockController is AccessControl, IERC721Receiver, IERC1155Receiver {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L25-L25) 


</details>


### [NC&#x2011;92] `immutable` variable names don\'t follow the Solidity style guide 
For `immutable` variable names, each word should use all capital letters, with underscores separating each word (CONSTANT_CASE)


*There are 2 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol

31:     address immutable blastStandardBridge;

32:     address immutable registry;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L31-L31) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L32-L32)


</details>


### [NC&#x2011;93] Add inline comments for unnamed parameters 
`function func(address a, address)` -> `function func(address a, address /* b */)`


*There are 7 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/TimelockController.sol

//@audit parameter number 0 starting from left need inline comment
//@audit parameter number 1 starting from left need inline comment
//@audit parameter number 2 starting from left need inline comment
//@audit parameter number 3 starting from left need inline comment
411:     function onERC721Received(

//@audit parameter number 0 starting from left need inline comment
//@audit parameter number 1 starting from left need inline comment
//@audit parameter number 2 starting from left need inline comment
//@audit parameter number 3 starting from left need inline comment
//@audit parameter number 4 starting from left need inline comment
423:     function onERC1155Received(

//@audit parameter number 0 starting from left need inline comment
//@audit parameter number 1 starting from left need inline comment
//@audit parameter number 2 starting from left need inline comment
//@audit parameter number 3 starting from left need inline comment
//@audit parameter number 4 starting from left need inline comment
436:     function onERC1155BatchReceived(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L411-L411) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L423-L423), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L436-L436)


```solidity

File: contracts/Oracle/Mantle/METHShim.sol

//@audit parameter number 0 starting from left need inline comment
42:     function getRoundData(uint80) external pure returns (uint80, int256, uint256, uint256, uint80) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L42-L42) 


```solidity

File: contracts/Oracle/Binance/WBETHShim.sol

//@audit parameter number 0 starting from left need inline comment
42:     function getRoundData(uint80) external pure returns (uint80, int256, uint256, uint256, uint80) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L42-L42) 


```solidity

File: contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol

//@audit parameter number 1 starting from left need inline comment
//@audit parameter number 2 starting from left need inline comment
69:     function xReceive(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L69-L69) 


```solidity

File: contracts/Bridge/L1/xRenzoBridge.sol

//@audit parameter number 5 starting from left need inline comment
139:     function xReceive(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L139-L139) 


</details>


### [NC&#x2011;94] Use the latest Solidity version for better security 
Using the latest solidity version will help avoid old compiler related vulnerabilities


*There are 40 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/token/EzEthTokenStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthTokenStorage.sol#L2-L2) 


```solidity

File: contracts/token/EzEthToken.sol

2: pragma solidity ^0.8.9;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L2-L2) 


```solidity

File: contracts/Withdraw/WithdrawQueue.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L2-L2) 


```solidity

File: contracts/Withdraw/WithdrawQueueStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueueStorage.sol#L2-L2) 


```solidity

File: contracts/TimelockController.sol

4: pragma solidity ^0.8.0;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L4-L4) 


```solidity

File: contracts/Rewards/RewardHandlerStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandlerStorage.sol#L2-L2) 


```solidity

File: contracts/Rewards/RewardHandler.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L2-L2) 


```solidity

File: contracts/RestakeManagerStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManagerStorage.sol#L2-L2) 


```solidity

File: contracts/RestakeManager.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L2-L2) 


```solidity

File: contracts/RateProvider/BalancerRateProvider.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProvider.sol#L2-L2) 


```solidity

File: contracts/RateProvider/BalancerRateProviderStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProviderStorage.sol#L2-L2) 


```solidity

File: contracts/Permissions/RoleManager.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L2-L2) 


```solidity

File: contracts/Permissions/RoleManagerStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManagerStorage.sol#L2-L2) 


```solidity

File: contracts/Oracle/RenzoOracle.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L2-L2) 


```solidity

File: contracts/Oracle/RenzoOracleStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracleStorage.sol#L2-L2) 


```solidity

File: contracts/Oracle/Mantle/METHShim.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L2-L2) 


```solidity

File: contracts/Oracle/Mantle/METHShimStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShimStorage.sol#L2-L2) 


```solidity

File: contracts/Oracle/Binance/WBETHShimStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShimStorage.sol#L2-L2) 


```solidity

File: contracts/Oracle/Binance/WBETHShim.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L2-L2) 


```solidity

File: contracts/Errors/Errors.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L2-L2) 


```solidity

File: contracts/Deposits/DepositQueueStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueueStorage.sol#L2-L2) 


```solidity

File: contracts/Deposits/DepositQueue.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L2-L2) 


```solidity

File: contracts/Delegation/OperatorDelegator.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L2-L2) 


```solidity

File: contracts/Delegation/OperatorDelegatorStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegatorStorage.sol#L2-L2) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20.sol

2: pragma solidity >=0.8.4 <0.9.0;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L2-L2) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Factory.sol

2: pragma solidity >=0.8.4 <0.9.0;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L2-L2) 


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol

2: pragma solidity >=0.8.4 <0.9.0;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L2-L2) 


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol

2: pragma solidity >=0.8.4 <0.9.0;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L2-L2) 


```solidity

File: contracts/Bridge/L2/xRenzoDepositStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L2-L2) 


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L2-L2) 


```solidity

File: contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L2-L2) 


```solidity

File: contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L2-L2) 


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L2-L2) 


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2Storage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2Storage.sol#L2-L2) 


```solidity

File: contracts/Bridge/L1/xRenzoBridge.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L2-L2) 


```solidity

File: contracts/Bridge/L1/xRenzoBridgeStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridgeStorage.sol#L2-L2) 


```solidity

File: contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol

2: pragma solidity ^0.8.13;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L2-L2) 


```solidity

File: contracts/Bridge/Connext/libraries/LibConnextStorage.sol

2: pragma solidity ^0.8.0;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/libraries/LibConnextStorage.sol#L2-L2) 


```solidity

File: contracts/Bridge/Connext/libraries/TokenId.sol

2: pragma solidity ^0.8.0;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/libraries/TokenId.sol#L2-L2) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol

2: pragma solidity >=0.8.4 <0.9.0;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L2-L2) 


</details>


### [NC&#x2011;95] Consider adding formal verification proofs 
Consider using formal verification to mathematically prove that your code does what is intended, and does not have any edge cases with unexpected behavior. The solidity compiler itself has this functionality [built in](https://docs.soliditylang.org/en/latest/smtchecker.html#smtchecker-and-formal-verification)


*There are 1 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/token/EzEthTokenStorage.sol

@audit Should implement invariant tests
1: 


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthTokenStorage.sol#L1-L1) 


</details>


### [NC&#x2011;96] Missing zero address check in functions with address parameters 
Adding a zero address check for each address type parameter can prevent errors.


*There are 3 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Withdraw/WithdrawQueue.sol

//@audit user,  are not checked
270:     function getOutstandingWithdrawRequests(address user) public view returns (uint256) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L270-L270) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20.sol

//@audit _bridge,  are not checked
152:     function mintingMaxLimitOf(address _bridge) public view returns (uint256 _limit) {

//@audit _bridge,  are not checked
163:     function burningMaxLimitOf(address _bridge) public view returns (uint256 _limit) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L152-L152) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L163-L163)


</details>


### [NC&#x2011;97] Use a struct to encapsulate multiple function parameters 
If a function has too many parameters, replacing them with a struct can improve code readability and maintainability, increase reusability, and reduce the likelihood of errors when passing the parameters.


*There are 25 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Withdraw/WithdrawQueue.sol

64:     function initialize(
65:         IRoleManager _roleManager,
66:         IRestakeManager _restakeManager,
67:         IEzEthToken _ezETH,
68:         IRenzoOracle _renzoOracle,
69:         uint256 _coolDownPeriod,
70:         TokenWithdrawBuffer[] calldata _withdrawalBufferTarget
71:     ) external initializer {
72:         if (
73:             address(_roleManager) == address(0) ||
74:             address(_ezETH) == address(0) ||
75:             address(_renzoOracle) == address(0) ||
76:             address(_restakeManager) == address(0) ||
77:             _withdrawalBufferTarget.length == 0 ||
78:             _coolDownPeriod == 0
79:         ) revert InvalidZeroInput();
80: 
81:         __Pausable_init();
82: 
83:         roleManager = _roleManager;
84:         restakeManager = _restakeManager;
85:         ezETH = _ezETH;
86:         renzoOracle = _renzoOracle;
87:         coolDownPeriod = _coolDownPeriod;
88:         for (uint256 i = 0; i < _withdrawalBufferTarget.length; ) {
89:             if (
90:                 _withdrawalBufferTarget[i].asset == address(0) ||
91:                 _withdrawalBufferTarget[i].bufferAmount == 0
92:             ) revert InvalidZeroInput();
93:             withdrawalBufferTarget[_withdrawalBufferTarget[i].asset] = _withdrawalBufferTarget[i]
94:                 .bufferAmount;
95:             unchecked {
96:                 ++i;
97:             }
98:         }
99:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L64-L99) 


```solidity

File: contracts/TimelockController.sol

201:     function hashOperation(
202:         address target,
203:         uint256 value,
204:         bytes calldata data,
205:         bytes32 predecessor,
206:         bytes32 salt
207:     ) public pure virtual returns (bytes32) {
208:         return keccak256(abi.encode(target, value, data, predecessor, salt));
209:     }

215:     function hashOperationBatch(
216:         address[] calldata targets,
217:         uint256[] calldata values,
218:         bytes[] calldata payloads,
219:         bytes32 predecessor,
220:         bytes32 salt
221:     ) public pure virtual returns (bytes32) {
222:         return keccak256(abi.encode(targets, values, payloads, predecessor, salt));
223:     }

234:     function schedule(
235:         address target,
236:         uint256 value,
237:         bytes calldata data,
238:         bytes32 predecessor,
239:         bytes32 salt,
240:         uint256 delay
241:     ) public virtual onlyRole(PROPOSER_ROLE) {
242:         bytes32 id = hashOperation(target, value, data, predecessor, salt);
243:         _schedule(id, delay);
244:         emit CallScheduled(id, 0, target, value, data, predecessor, delay);
245:         if (salt != bytes32(0)) {
246:             emit CallSalt(id, salt);
247:         }
248:     }

259:     function scheduleBatch(
260:         address[] calldata targets,
261:         uint256[] calldata values,
262:         bytes[] calldata payloads,
263:         bytes32 predecessor,
264:         bytes32 salt,
265:         uint256 delay
266:     ) public virtual onlyRole(PROPOSER_ROLE) {
267:         require(targets.length == values.length, "TimelockController: length mismatch");
268:         require(targets.length == payloads.length, "TimelockController: length mismatch");
269: 
270:         bytes32 id = hashOperationBatch(targets, values, payloads, predecessor, salt);
271:         _schedule(id, delay);
272:         for (uint256 i = 0; i < targets.length; ++i) {
273:             emit CallScheduled(id, i, targets[i], values[i], payloads[i], predecessor, delay);
274:         }
275:         if (salt != bytes32(0)) {
276:             emit CallSalt(id, salt);
277:         }
278:     }

315:     function execute(
316:         address target,
317:         uint256 value,
318:         bytes calldata payload,
319:         bytes32 predecessor,
320:         bytes32 salt
321:     ) public payable virtual onlyRoleOrOpenRole(EXECUTOR_ROLE) {
322:         bytes32 id = hashOperation(target, value, payload, predecessor, salt);
323: 
324:         _beforeCall(id, predecessor);
325:         _execute(target, value, payload);
326:         emit CallExecuted(id, 0, target, value, payload);
327:         _afterCall(id);
328:     }

342:     function executeBatch(
343:         address[] calldata targets,
344:         uint256[] calldata values,
345:         bytes[] calldata payloads,
346:         bytes32 predecessor,
347:         bytes32 salt
348:     ) public payable virtual onlyRoleOrOpenRole(EXECUTOR_ROLE) {
349:         require(targets.length == values.length, "TimelockController: length mismatch");
350:         require(targets.length == payloads.length, "TimelockController: length mismatch");
351: 
352:         bytes32 id = hashOperationBatch(targets, values, payloads, predecessor, salt);
353: 
354:         _beforeCall(id, predecessor);
355:         for (uint256 i = 0; i < targets.length; ++i) {
356:             address target = targets[i];
357:             uint256 value = values[i];
358:             bytes calldata payload = payloads[i];
359:             _execute(target, value, payload);
360:             emit CallExecuted(id, i, target, value, payload);
361:         }
362:         _afterCall(id);
363:     }

423:     function onERC1155Received(
424:         address,
425:         address,
426:         uint256,
427:         uint256,
428:         bytes memory
429:     ) public virtual override returns (bytes4) {
430:         return this.onERC1155Received.selector;
431:     }

436:     function onERC1155BatchReceived(
437:         address,
438:         address,
439:         uint256[] memory,
440:         uint256[] memory,
441:         bytes memory
442:     ) public virtual override returns (bytes4) {
443:         return this.onERC1155BatchReceived.selector;
444:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L201-L209) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L215-L223), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L234-L248), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L259-L278), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L315-L328), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L342-L363), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L423-L431), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L436-L444)


```solidity

File: contracts/RestakeManager.sol

101:     function initialize(
102:         IRoleManager _roleManager,
103:         IEzEthToken _ezETH,
104:         IRenzoOracle _renzoOracle,
105:         IStrategyManager _strategyManager,
106:         IDelegationManager _delegationManager,
107:         IDepositQueue _depositQueue
108:     ) public initializer {
109:         __ReentrancyGuard_init();
110: 
111:         roleManager = _roleManager;
112:         ezETH = _ezETH;
113:         renzoOracle = _renzoOracle;
114:         strategyManager = _strategyManager;
115:         delegationManager = _delegationManager;
116:         depositQueue = _depositQueue;
117:         paused = false;
118:     }

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

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L101-L118) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L400-L447)


```solidity

File: contracts/Delegation/OperatorDelegator.sol

74:     function initialize(
75:         IRoleManager _roleManager,
76:         IStrategyManager _strategyManager,
77:         IRestakeManager _restakeManager,
78:         IDelegationManager _delegationManager,
79:         IEigenPodManager _eigenPodManager
80:     ) external initializer {
81:         if (address(_roleManager) == address(0x0)) revert InvalidZeroInput();
82:         if (address(_strategyManager) == address(0x0)) revert InvalidZeroInput();
83:         if (address(_restakeManager) == address(0x0)) revert InvalidZeroInput();
84:         if (address(_delegationManager) == address(0x0)) revert InvalidZeroInput();
85:         if (address(_eigenPodManager) == address(0x0)) revert InvalidZeroInput();
86: 
87:         __ReentrancyGuard_init();
88: 
89:         roleManager = _roleManager;
90:         strategyManager = _strategyManager;
91:         restakeManager = _restakeManager;
92:         delegationManager = _delegationManager;
93:         eigenPodManager = _eigenPodManager;
94: 
95:         // Deploy new EigenPod
96:         eigenPod = IEigenPod(eigenPodManager.createPod());
97:     }

364:     function verifyWithdrawalCredentials(
365:         uint64 oracleTimestamp,
366:         BeaconChainProofs.StateRootProof calldata stateRootProof,
367:         uint40[] calldata validatorIndices,
368:         bytes[] calldata withdrawalCredentialProofs,
369:         bytes32[][] calldata validatorFields
370:     ) external onlyNativeEthRestakeAdmin {
371:         uint256 gasBefore = gasleft();
372:         eigenPod.verifyWithdrawalCredentials(
373:             oracleTimestamp,
374:             stateRootProof,
375:             validatorIndices,
376:             withdrawalCredentialProofs,
377:             validatorFields
378:         );
379: 
380:         // Decrement the staked but not verified ETH
381:         for (uint256 i = 0; i < validatorFields.length; ) {
382:             uint64 validatorCurrentBalanceGwei = BeaconChainProofs.getEffectiveBalanceGwei(
383:                 validatorFields[i]
384:             );
385:             stakedButNotVerifiedEth -= (validatorCurrentBalanceGwei * GWEI_TO_WEI);
386:             unchecked {
387:                 ++i;
388:             }
389:         }
390:         // update the gas spent for RestakeAdmin
391:         _recordGas(gasBefore);
392:     }

405:     function verifyAndProcessWithdrawals(
406:         uint64 oracleTimestamp,
407:         BeaconChainProofs.StateRootProof calldata stateRootProof,
408:         BeaconChainProofs.WithdrawalProof[] calldata withdrawalProofs,
409:         bytes[] calldata validatorFieldsProofs,
410:         bytes32[][] calldata validatorFields,
411:         bytes32[][] calldata withdrawalFields
412:     ) external onlyNativeEthRestakeAdmin {
413:         uint256 gasBefore = gasleft();
414:         eigenPod.verifyAndProcessWithdrawals(
415:             oracleTimestamp,
416:             stateRootProof,
417:             withdrawalProofs,
418:             validatorFieldsProofs,
419:             validatorFields,
420:             withdrawalFields
421:         );
422:         // update the gas spent for RestakeAdmin
423:         _recordGas(gasBefore);
424:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L74-L97) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L364-L392), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L405-L424)


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Factory.sol

74:     function deployXERC20(
75:         string memory _name,
76:         string memory _symbol,
77:         uint256[] memory _minterLimits,
78:         uint256[] memory _burnerLimits,
79:         address[] memory _bridges,
80:         address _proxyAdmin
81:     ) external returns (address _xerc20) {
82:         _xerc20 = _deployXERC20(
83:             _name,
84:             _symbol,
85:             _minterLimits,
86:             _burnerLimits,
87:             _bridges,
88:             _proxyAdmin
89:         );
90: 
91:         emit XERC20Deployed(_xerc20);
92:     }

135:     function _deployXERC20(
136:         string memory _name,
137:         string memory _symbol,
138:         uint256[] memory _minterLimits,
139:         uint256[] memory _burnerLimits,
140:         address[] memory _bridges,
141:         address _proxyAdmin
142:     ) internal returns (address _xerc20) {
143:         uint256 _bridgesLength = _bridges.length;
144:         if (_minterLimits.length != _bridgesLength || _burnerLimits.length != _bridgesLength) {
145:             revert IXERC20Factory_InvalidLength();
146:         }
147:         bytes32 _salt = keccak256(abi.encodePacked(_name, _symbol, msg.sender));
148: 
149:         // Initialize function - sent as 3rd argument to the proxy constructor
150:         bytes memory initializeBytecode = abi.encodeCall(
151:             XERC20.initialize,
152:             (_name, _symbol, address(this))
153:         );
154: 
155:         bytes memory _creation = type(TransparentUpgradeableProxy).creationCode;
156: 
157:         // Constructor in Proxy takes (logic, admin, data)
158:         bytes memory _bytecode = abi.encodePacked(
159:             _creation,
160:             abi.encode(xerc20Implementation, _proxyAdmin, initializeBytecode)
161:         );
162: 
163:         _xerc20 = CREATE3.deploy(_salt, _bytecode, 0);
164: 
165:         EnumerableSetUpgradeable.add(_xerc20RegistryArray, _xerc20);
166: 
167:         for (uint256 _i; _i < _bridgesLength; ++_i) {
168:             XERC20(_xerc20).setLimits(_bridges[_i], _minterLimits[_i], _burnerLimits[_i]);
169:         }
170: 
171:         XERC20(_xerc20).transferOwnership(msg.sender);
172:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L74-L92) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L135-L172)


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol

35:     function initialize(
36:         string memory _name,
37:         string memory _symbol,
38:         address _factory,
39:         address _l1Token,
40:         address _optimismBridge
41:     ) public initializer {
42:         __ERC165_init();
43:         __XERC20_init(_name, _symbol, _factory);
44:         l1Token = _l1Token;
45:         optimismBridge = _optimismBridge;
46:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L35-L46) 


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol

37:     function deployOptimismMintableXERC20(
38:         string memory _name,
39:         string memory _symbol,
40:         uint256[] memory _minterLimits,
41:         uint256[] memory _burnerLimits,
42:         address[] memory _bridges,
43:         address _proxyAdmin,
44:         address _l1Token
45:     ) public returns (address _xerc20) {
46:         _xerc20 = _deployOptimismMintableXERC20(
47:             _name,
48:             _symbol,
49:             _minterLimits,
50:             _burnerLimits,
51:             _bridges,
52:             _proxyAdmin,
53:             _l1Token
54:         );
55: 
56:         emit XERC20Deployed(_xerc20);
57:     }

073:     function _deployOptimismMintableXERC20(
074:         string memory _name,
075:         string memory _symbol,
076:         uint256[] memory _minterLimits,
077:         uint256[] memory _burnerLimits,
078:         address[] memory _bridges,
079:         address _proxyAdmin,
080:         address _l1Token
081:     ) internal returns (address _xerc20) {
082:         uint256 _bridgesLength = _bridges.length;
083:         if (_minterLimits.length != _bridgesLength || _burnerLimits.length != _bridgesLength) {
084:             revert IXERC20Factory_InvalidLength();
085:         }
086:         if (_bridgesLength < 1) {
087:             revert OptimismMintableXERC20Factory_NoBridges();
088:         }
089:         bytes32 _salt = keccak256(abi.encodePacked(_name, _symbol, msg.sender));
090: 
091:         // Initialize function - sent as 3rd argument to the proxy constructor
092:         bytes memory initializeBytecode = abi.encodeCall(
093:             OptimismMintableXERC20.initialize,
094:             (_name, _symbol, address(this), _l1Token, _bridges[0])
095:         );
096: 
097:         bytes memory _creation = type(TransparentUpgradeableProxy).creationCode;
098: 
099:         // Constructor in Proxy takes (logic, admin, data)
100:         bytes memory _bytecode = abi.encodePacked(
101:             _creation,
102:             abi.encode(xerc20Implementation, _proxyAdmin, initializeBytecode)
103:         );
104: 
105:         _xerc20 = CREATE3.deploy(_salt, _bytecode, 0);
106: 
107:         EnumerableSetUpgradeable.add(_xerc20RegistryArray, _xerc20);
108: 
109:         for (uint256 _i; _i < _bridgesLength; ++_i) {
110:             OptimismMintableXERC20(_xerc20).setLimits(
111:                 _bridges[_i],
112:                 _minterLimits[_i],
113:                 _burnerLimits[_i]
114:             );
115:         }
116: 
117:         OptimismMintableXERC20(_xerc20).transferOwnership(msg.sender);
118:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L37-L57) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L73-L118)


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

075:     function initialize(
076:         uint256 _currentPrice,
077:         IERC20 _xezETH,
078:         IERC20 _depositToken,
079:         IERC20 _collateralToken,
080:         IConnext _connext,
081:         bytes32 _swapKey,
082:         address _receiver,
083:         uint32 _bridgeDestinationDomain,
084:         address _bridgeTargetAddress,
085:         IRenzoOracleL2 _oracle
086:     ) public initializer {
087:         // Initialize inherited classes
088:         __Ownable_init();
089: 
090:         // Verify valid non zero values
091:         if (
092:             _currentPrice == 0 ||
093:             address(_xezETH) == address(0) ||
094:             address(_depositToken) == address(0) ||
095:             address(_collateralToken) == address(0) ||
096:             address(_connext) == address(0) ||
097:             _swapKey == 0 ||
098:             _bridgeDestinationDomain == 0 ||
099:             _bridgeTargetAddress == address(0)
100:         ) {
101:             revert InvalidZeroInput();
102:         }
103: 
104:         // Verify all tokens have 18 decimals
105:         uint8 decimals = IERC20MetadataUpgradeable(address(_depositToken)).decimals();
106:         if (decimals != EXPECTED_DECIMALS) {
107:             revert InvalidTokenDecimals(EXPECTED_DECIMALS, decimals);
108:         }
109:         decimals = IERC20MetadataUpgradeable(address(_collateralToken)).decimals();
110:         if (decimals != EXPECTED_DECIMALS) {
111:             revert InvalidTokenDecimals(EXPECTED_DECIMALS, decimals);
112:         }
113:         decimals = IERC20MetadataUpgradeable(address(_xezETH)).decimals();
114:         if (decimals != EXPECTED_DECIMALS) {
115:             revert InvalidTokenDecimals(EXPECTED_DECIMALS, decimals);
116:         }
117: 
118:         // Initialize the price and timestamp
119:         lastPrice = _currentPrice;
120:         lastPriceTimestamp = block.timestamp;
121: 
122:         // Set xezETH address
123:         xezETH = _xezETH;
124: 
125:         // Set the depoist token
126:         depositToken = _depositToken;
127: 
128:         // Set the collateral token
129:         collateralToken = _collateralToken;
130: 
131:         // Set the connext contract
132:         connext = _connext;
133: 
134:         // Set the swap key
135:         swapKey = _swapKey;
136: 
137:         // Set receiver contract address
138:         receiver = _receiver;
139:         // Connext router fee is 5 basis points
140:         bridgeRouterFeeBps = 5;
141: 
142:         // Set the bridge destination domain
143:         bridgeDestinationDomain = _bridgeDestinationDomain;
144: 
145:         // Set the bridge target address
146:         bridgeTargetAddress = _bridgeTargetAddress;
147: 
148:         // set oracle Price Feed struct
149:         oracle = _oracle;
150: 
151:         // set bridge Fee Share 0.05% where 100 basis point = 1%
152:         bridgeFeeShare = 5;
153: 
154:         //set sweep batch size to 32 ETH
155:         sweepBatchSize = 32 ether;
156:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L75-L156) 


```solidity

File: contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol

69:     function xReceive(
70:         bytes32 _transferId,
71:         uint256,
72:         address,
73:         address _originSender,
74:         uint32 _origin,
75:         bytes memory _callData
76:     ) external onlySource(_originSender, _origin) whenNotPaused returns (bytes memory) {
77:         (uint256 _price, uint256 _timestamp) = abi.decode(_callData, (uint256, uint256));
78:         xRenzoDeposit.updatePrice(_price, _timestamp);
79: 
80:         emit MessageReceived(_transferId, _origin, _originSender, _price, _timestamp);
81:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L69-L81) 


```solidity

File: contracts/Bridge/L1/xRenzoBridge.sol

070:     function initialize(
071:         IERC20 _ezETH,
072:         IERC20 _xezETH,
073:         IRestakeManager _restakeManager,
074:         IERC20 _wETH,
075:         IXERC20Lockbox _xezETHLockbox,
076:         IConnext _connext,
077:         IRouterClient _linkRouterClient,
078:         IRateProvider _rateProvider,
079:         LinkTokenInterface _linkToken,
080:         IRoleManager _roleManager
081:     ) public initializer {
082:         // Verify non-zero addresses on inputs
083:         if (
084:             address(_ezETH) == address(0) ||
085:             address(_xezETH) == address(0) ||
086:             address(_restakeManager) == address(0) ||
087:             address(_wETH) == address(0) ||
088:             address(_xezETHLockbox) == address(0) ||
089:             address(_connext) == address(0) ||
090:             address(_linkRouterClient) == address(0) ||
091:             address(_rateProvider) == address(0) ||
092:             address(_linkToken) == address(0) ||
093:             address(_roleManager) == address(0)
094:         ) {
095:             revert InvalidZeroInput();
096:         }
097: 
098:         // Verify all tokens have 18 decimals
099:         uint8 decimals = IERC20MetadataUpgradeable(address(_ezETH)).decimals();
100:         if (decimals != EXPECTED_DECIMALS) {
101:             revert InvalidTokenDecimals(EXPECTED_DECIMALS, decimals);
102:         }
103:         decimals = IERC20MetadataUpgradeable(address(_xezETH)).decimals();
104:         if (decimals != EXPECTED_DECIMALS) {
105:             revert InvalidTokenDecimals(EXPECTED_DECIMALS, decimals);
106:         }
107:         decimals = IERC20MetadataUpgradeable(address(_wETH)).decimals();
108:         if (decimals != EXPECTED_DECIMALS) {
109:             revert InvalidTokenDecimals(EXPECTED_DECIMALS, decimals);
110:         }
111:         decimals = IERC20MetadataUpgradeable(address(_linkToken)).decimals();
112:         if (decimals != EXPECTED_DECIMALS) {
113:             revert InvalidTokenDecimals(EXPECTED_DECIMALS, decimals);
114:         }
115: 
116:         // Save off inputs
117:         ezETH = _ezETH;
118:         xezETH = _xezETH;
119:         restakeManager = _restakeManager;
120:         wETH = _wETH;
121:         xezETHLockbox = _xezETHLockbox;
122:         connext = _connext;
123:         linkRouterClient = _linkRouterClient;
124:         rateProvider = _rateProvider;
125:         linkToken = _linkToken;
126:         roleManager = _roleManager;
127:     }

139:     function xReceive(
140:         bytes32 _transferId,
141:         uint256 _amount,
142:         address _asset,
143:         address _originSender,
144:         uint32 _origin,
145:         bytes memory
146:     ) external nonReentrant returns (bytes memory) {
147:         // Only allow incoming messages from the Connext contract
148:         if (msg.sender != address(connext)) {
149:             revert InvalidSender(address(connext), msg.sender);
150:         }
151: 
152:         // Check that the token received is wETH
153:         if (_asset != address(wETH)) {
154:             revert InvalidTokenReceived();
155:         }
156: 
157:         // Check that the amount sent is greater than 0
158:         if (_amount == 0) {
159:             revert InvalidZeroInput();
160:         }
161: 
162:         // Get the balance of ETH before the withdraw
163:         uint256 ethBalanceBeforeWithdraw = address(this).balance;
164: 
165:         // Unwrap the WETH
166:         IWeth(address(wETH)).withdraw(_amount);
167: 
168:         // Get the amount of ETH
169:         uint256 ethAmount = address(this).balance - ethBalanceBeforeWithdraw;
170: 
171:         // Get the amonut of ezETH before the deposit
172:         uint256 ezETHBalanceBeforeDeposit = ezETH.balanceOf(address(this));
173: 
174:         // Deposit it into Renzo RestakeManager
175:         restakeManager.depositETH{ value: ethAmount }();
176: 
177:         // Get the amount of ezETH that was minted
178:         uint256 ezETHAmount = ezETH.balanceOf(address(this)) - ezETHBalanceBeforeDeposit;
179: 
180:         // Approve the lockbox to spend the ezETH
181:         ezETH.safeApprove(address(xezETHLockbox), ezETHAmount);
182: 
183:         // Get the xezETH balance before the deposit
184:         uint256 xezETHBalanceBeforeDeposit = xezETH.balanceOf(address(this));
185: 
186:         // Send to the lockbox to be wrapped into xezETH
187:         xezETHLockbox.deposit(ezETHAmount);
188: 
189:         // Get the amount of xezETH that was minted
190:         uint256 xezETHAmount = xezETH.balanceOf(address(this)) - xezETHBalanceBeforeDeposit;
191: 
192:         // Burn it - it was already minted on the L2
193:         IXERC20(address(xezETH)).burn(address(this), xezETHAmount);
194: 
195:         // Emit the event
196:         emit EzETHMinted(_transferId, _amount, _origin, _originSender, ezETHAmount);
197: 
198:         // Return 0 for success
199:         bytes memory returnData = new bytes(0);
200:         return returnData;
201:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L70-L127) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L139-L201)


```solidity

File: contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol

18:     function bridgeERC20To(
19:         address _localToken,
20:         address _remoteToken,
21:         address _to,
22:         uint256 _amount,
23:         uint32 _minGasLimit,
24:         bytes calldata _extraData
25:     ) external;

56:     function bridgeTo(
57:         address _to,
58:         address _erc20,
59:         address _remoteToken,
60:         uint256 _amount,
61:         uint32 _minGasLimit,
62:         bytes calldata _extraData
63:     ) external {
64:         // Sanity check
65:         if (_amount <= 0) {
66:             revert AmountLessThanZero();
67:         }
68: 
69:         address xerc20 = IXERC20Registry(registry).getXERC20(_erc20);
70:         address lockbox = IXERC20Registry(registry).getLockbox(xerc20);
71: 
72:         // Sanity check
73:         if (xerc20 == address(0) || lockbox == address(0)) {
74:             revert InvalidAddress();
75:         }
76: 
77:         // If using xERC20, the assumption is that the contract should be deployed at same address
78:         // on both networks.
79:         if (xerc20 != _remoteToken) {
80:             revert InvalidRemoteToken(_remoteToken);
81:         }
82: 
83:         SafeERC20.safeTransferFrom(IERC20(_erc20), msg.sender, address(this), _amount);
84:         SafeERC20.safeApprove(IERC20(_erc20), lockbox, _amount);
85:         IXERC20Lockbox(lockbox).deposit(_amount);
86:         SafeERC20.safeApprove(IERC20(xerc20), blastStandardBridge, _amount);
87:         L1StandardBridge(blastStandardBridge).bridgeERC20To(
88:             xerc20,
89:             _remoteToken,
90:             _to,
91:             _amount,
92:             _minGasLimit,
93:             _extraData
94:         );
95:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L18-L25) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L56-L95)


</details>


### [NC&#x2011;98] Use custom errors rather than `revert()`/`require()` strings for better readability 
Custom errors are available from solidity version 0.8.4. Custom errors are more easily processed in try-catch blocks, and are easier to re-use and maintain.


*There are 12 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/TimelockController.sol

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

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L267-L267) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L268-L268), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L284-L284), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L285-L285), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L297-L297), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L349-L349), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L350-L350), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L370-L370), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L377-L377), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L378-L381), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L388-L388), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L403-L403)


</details>


### [NC&#x2011;99] Use `@inheritdoc` for overridden functions 



*There are 15 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/token/EzEthToken.sol

55:     /// @dev

74:     /**
75:      * @dev Returns the name of the token.
76:      */

81:     /**
82:      * @dev Returns the symbol of the token, usually a shorter version of the
83:      * name.
84:      */


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L55-L55) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L74-L76), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L81-L84)


```solidity

File: contracts/TimelockController.sol

139:     /**
140:      * @dev See {IERC165-supportsInterface}.
141:      */

408:     /**
409:      * @dev See {IERC721Receiver-onERC721Received}.
410:      */

420:     /**
421:      * @dev See {IERC1155Receiver-onERC1155Received}.
422:      */

433:     /**
434:      * @dev See {IERC1155Receiver-onERC1155BatchReceived}.
435:      */


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L139-L141) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L408-L410), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L420-L422), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L433-L435)


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol

48:     function supportsInterface(

56:     function remoteToken() public view override returns (address) {

60:     function bridge() public view override returns (address) {

64:     function mint(address _to, uint256 _amount) public override(XERC20, IOptimismMintableERC20) {

68:     function burn(address _from, uint256 _amount) public override(XERC20, IOptimismMintableERC20) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L48-L48) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L56-L56), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L60-L60), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L64-L64), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L68-L68)


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

303:     /**
304:      * @notice  Updates the price feed
305:      * @dev     This function will receive the price feed and timestamp from the L1 through CCIPReceiver middleware contract.
306:      *          It should verify the origin of the call and only allow permissioned source to call.
307:      * @param   _price The price of ezETH sent via L1.
308:      * @param   _timestamp The timestamp at which L1 sent the price.
309:      */

451:     /**
452:      * @notice  Exposes the price via getRate()
453:      * @dev     This is required for a balancer pool to get the price of ezETH
454:      * @return  uint256  .
455:      */


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L303-L309) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L451-L455)


```solidity

File: contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol

60:     /**
61:      * @notice  Updates the price feed
62:      * @dev     This function will receive the price feed from the L1.
63:      *          It should verify the origin of the call and only allow permissioned source to call.
64:      * @param   any2EvmMessage ccip Message received from L1 -> L2
65:      */


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L60-L65) 


</details>


### [NC&#x2011;100] Multiple mappings with same keys can be combined into a single struct mapping for readability 
Well-organized data structures make code reviews easier, which may lead to fewer bugs. Consider combining related mappings into mappings to structs, so it's clear what data is related.


*There are 5 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Withdraw/WithdrawQueueStorage.sol

44:     mapping(address => uint256) public withdrawalBufferTarget;

47:     mapping(address => uint256) public claimReserve;

50:     mapping(address => WithdrawRequest[]) public withdrawRequests;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueueStorage.sol#L44-L44) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueueStorage.sol#L47-L47), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueueStorage.sol#L50-L50)


```solidity

File: contracts/Delegation/OperatorDelegatorStorage.sol

56:     mapping(address => uint256) public adminGasSpentInWei;

61:     mapping(address => uint256) public queuedShares;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegatorStorage.sol#L56-L56) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegatorStorage.sol#L61-L61)


</details>


### [NC&#x2011;101] constructor should emit an event 
Use events to signal significant changes to off-chain monitoring tools.


*There are 22 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/token/EzEthToken.sol

28:     constructor() {
29:         _disableInitializers();
30:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L28-L30) 


```solidity

File: contracts/Withdraw/WithdrawQueue.sol

57:     constructor() {
58:         _disableInitializers();
59:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L57-L59) 


```solidity

File: contracts/Rewards/RewardHandler.sol

33:     constructor() {
34:         _disableInitializers();
35:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L33-L35) 


```solidity

File: contracts/RestakeManager.sol

96:     constructor() {
97:         _disableInitializers();
98:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L96-L98) 


```solidity

File: contracts/RateProvider/BalancerRateProvider.sol

12:     constructor() {
13:         _disableInitializers();
14:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProvider.sol#L12-L14) 


```solidity

File: contracts/Permissions/RoleManager.sol

17:     constructor() {
18:         _disableInitializers();
19:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L17-L19) 


```solidity

File: contracts/Oracle/RenzoOracle.sol

39:     constructor() {
40:         _disableInitializers();
41:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L39-L41) 


```solidity

File: contracts/Oracle/Mantle/METHShim.sol

18:     constructor() {
19:         _disableInitializers();
20:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L18-L20) 


```solidity

File: contracts/Oracle/Binance/WBETHShim.sol

18:     constructor() {
19:         _disableInitializers();
20:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L18-L20) 


```solidity

File: contracts/Deposits/DepositQueue.sol

69:     constructor() {
70:         _disableInitializers();
71:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L69-L71) 


```solidity

File: contracts/Delegation/OperatorDelegator.sol

69:     constructor() {
70:         _disableInitializers();
71:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L69-L71) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20.sol

50:     constructor() {
51:         _disableInitializers();
52:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L50-L52) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Factory.sol

44:     constructor() {
45:         _disableInitializers();
46:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L44-L46) 


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol

24:     constructor() {
25:         _disableInitializers();
26:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L24-L26) 


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol

19:     constructor() {
20:         _disableInitializers();
21:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L19-L21) 


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

59:     constructor() {
60:         _disableInitializers();
61:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L59-L61) 


```solidity

File: contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol

52:     constructor(address _connext, address _xRenzoBridgeL1, uint32 _connextEthChainDomain) {
53:         if (_xRenzoBridgeL1 == address(0) || _connextEthChainDomain == 0 || _connext == address(0))
54:             revert InvalidZeroInput();
55: 
56:         // Set connext bridge address
57:         connext = _connext;
58: 
59:         // Set xRenzoBridge L1 contract address
60:         xRenzoBridgeL1 = _xRenzoBridgeL1;
61: 
62:         // Set connext source chain Domain Id for Ethereum L1
63:         connextEthChainDomain = _connextEthChainDomain;
64: 
65:         // Pause The contract to setup xRenzoDeposit
66:         _pause();
67:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L52-L67) 


```solidity

File: contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol

43:     constructor(
44:         address _router,
45:         address _xRenzoBridgeL1,
46:         uint64 _ccipEthChainSelector
47:     ) CCIPReceiver(_router) {
48:         if (_xRenzoBridgeL1 == address(0) || _ccipEthChainSelector == 0) revert InvalidZeroInput();
49: 
50:         // Set xRenzoBridge L1 contract address
51:         xRenzoBridgeL1 = _xRenzoBridgeL1;
52: 
53:         // Set ccip source chain selector for Ethereum L1
54:         ccipEthChainSelector = _ccipEthChainSelector;
55: 
56:         // Pause The contract to setup xRenzoDeposit
57:         _pause();
58:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L43-L58) 


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2.sol

19:     constructor() {
20:         _disableInitializers();
21:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L19-L21) 


```solidity

File: contracts/Bridge/L1/xRenzoBridge.sol

65:     constructor() {
66:         _disableInitializers();
67:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L65-L67) 


```solidity

File: contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol

39:     constructor(address _blastStandardBridge, address _registry) {
40:         // Sanity check
41:         if (_blastStandardBridge == address(0) || _registry == address(0)) {
42:             revert InvalidAddress();
43:         }
44: 
45:         blastStandardBridge = _blastStandardBridge;
46:         registry = _registry;
47:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L39-L47) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol

33:     constructor() {
34:         _disableInitializers();
35:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L33-L35) 


</details>


### [NC&#x2011;102] `error` should be named using CapWords style 
See the [Solidity Style](https://docs.soliditylang.org/en/latest/style-guide.html#struct-names) Guide for more info.


*There are 1 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol

15:     error OptimismMintableXERC20Factory_NoBridges();


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L15-L15) 


</details>


### [NC&#x2011;103] Use `ERC1155Holder` over `ERC1155Receiver` 
View OpenZeppelin's v5.0 release candidate changes [here](https://github.com/OpenZeppelin/openzeppelin-contracts/releases/tag/v5.0.0-rc.0).


*There are 1 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/TimelockController.sol

25: contract TimelockController is AccessControl, IERC721Receiver, IERC1155Receiver {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L25-L25) 


</details>


### [NC&#x2011;104] Complex functions should include comments 
Large and/or complex functions should include comments to make them easier to understand and reduce margin for error.


*There are 3 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Withdraw/WithdrawQueue.sol

64:     function initialize(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L64-L64) 


```solidity

File: contracts/TimelockController.sol

342:     function executeBatch(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L342-L342) 


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol

37:     function deployOptimismMintableXERC20(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L37-L37) 


</details>


### [NC&#x2011;105] Make use of Solidiy's `using` keyword 
The directive `using A for B` can be used to attach functions (`A`) as operators to user-defined value types or as member functions to any type (`B`). The member functions receive the object they are called on as their first parameter (like the `self` variable in Python). The operator functions receive operands as parameters.  Doing so improves readability, makes debugging easier, and promotes modularity and reusability in the code.


*There are 20 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Bridge/xERC20/contracts/XERC20Factory.sol

165:         EnumerableSetUpgradeable.add(_xerc20RegistryArray, _xerc20);

209:         EnumerableSetUpgradeable.add(_lockboxRegistryArray, _lockbox);

163:         _xerc20 = CREATE3.deploy(_salt, _bytecode, 0);

206:         _lockbox = payable(CREATE3.deploy(_salt, _bytecode, 0));


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L165-L165) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L209-L209), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L163-L163), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L206-L206)


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol

65:         XERC20.mint(_to, _amount);

69:         XERC20.burn(_from, _amount);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L65-L65) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L69-L69)


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol

107:         EnumerableSetUpgradeable.add(_xerc20RegistryArray, _xerc20);

105:         _xerc20 = CREATE3.deploy(_salt, _bytecode, 0);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L107-L107) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L105-L105)


```solidity

File: contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol

78:         xRenzoDeposit.updatePrice(_price, _timestamp);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L78-L78) 


```solidity

File: contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol

77:         xRenzoDeposit.updatePrice(_price, _timestamp);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L77-L77) 


```solidity

File: contracts/Bridge/L1/xRenzoBridge.sol

219:             Client.EVM2AnyMessage memory evm2AnyMessage = Client.EVM2AnyMessage({

223:                 extraArgs: Client._argsToBytes(

225:                     Client.EVMExtraArgsV1({ gasLimit: 200_000 })


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L219-L219) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L223-L223), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L225-L225)


```solidity

File: contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol

83:         SafeERC20.safeTransferFrom(IERC20(_erc20), msg.sender, address(this), _amount);

84:         SafeERC20.safeApprove(IERC20(_erc20), lockbox, _amount);

86:         SafeERC20.safeApprove(IERC20(xerc20), blastStandardBridge, _amount);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L83-L83) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L84-L84), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L86-L86)


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol

128:         XERC20.burn(msg.sender, _amount);

150:         XERC20.mint(_to, _amount);

134:             ERC20.safeTransfer(_to, _amount);

147:             ERC20.safeTransferFrom(msg.sender, address(this), _amount);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L128-L128) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L150-L150), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L134-L134), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L147-L147)


</details>


### [NC&#x2011;106] [Solidity]: All `verbatim` blocks are considered identical by deduplicator and can incorrectly be unified 
The block deduplicator is a step of the opcode-based optimizer which identifies equivalent assembly blocks and merges them into a single one. However, when blocks contained `verbatim`, their comparison was performed incorrectly, leading to the collapse of assembly blocks which are identical except for the contents of the ``verbatim`` items. Since `verbatim` is only available in Yul, compilation of Solidity sources is not affected. For more details check the following [link](https://blog.soliditylang.org/2023/11/08/verbatim-invalid-deduplication-bug/)


*There are 32 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/token/EzEthTokenStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthTokenStorage.sol#L2-L2) 


```solidity

File: contracts/token/EzEthToken.sol

2: pragma solidity ^0.8.9;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L2-L2) 


```solidity

File: contracts/Withdraw/WithdrawQueue.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L2-L2) 


```solidity

File: contracts/Withdraw/WithdrawQueueStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueueStorage.sol#L2-L2) 


```solidity

File: contracts/Rewards/RewardHandlerStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandlerStorage.sol#L2-L2) 


```solidity

File: contracts/Rewards/RewardHandler.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L2-L2) 


```solidity

File: contracts/RestakeManagerStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManagerStorage.sol#L2-L2) 


```solidity

File: contracts/RestakeManager.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L2-L2) 


```solidity

File: contracts/RateProvider/BalancerRateProvider.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProvider.sol#L2-L2) 


```solidity

File: contracts/RateProvider/BalancerRateProviderStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProviderStorage.sol#L2-L2) 


```solidity

File: contracts/Permissions/RoleManager.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L2-L2) 


```solidity

File: contracts/Permissions/RoleManagerStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManagerStorage.sol#L2-L2) 


```solidity

File: contracts/Oracle/RenzoOracle.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L2-L2) 


```solidity

File: contracts/Oracle/RenzoOracleStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracleStorage.sol#L2-L2) 


```solidity

File: contracts/Oracle/Mantle/METHShim.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L2-L2) 


```solidity

File: contracts/Oracle/Mantle/METHShimStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShimStorage.sol#L2-L2) 


```solidity

File: contracts/Oracle/Binance/WBETHShimStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShimStorage.sol#L2-L2) 


```solidity

File: contracts/Oracle/Binance/WBETHShim.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L2-L2) 


```solidity

File: contracts/Errors/Errors.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L2-L2) 


```solidity

File: contracts/Deposits/DepositQueueStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueueStorage.sol#L2-L2) 


```solidity

File: contracts/Deposits/DepositQueue.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L2-L2) 


```solidity

File: contracts/Delegation/OperatorDelegator.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L2-L2) 


```solidity

File: contracts/Delegation/OperatorDelegatorStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegatorStorage.sol#L2-L2) 


```solidity

File: contracts/Bridge/L2/xRenzoDepositStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L2-L2) 


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L2-L2) 


```solidity

File: contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L2-L2) 


```solidity

File: contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L2-L2) 


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L2-L2) 


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2Storage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2Storage.sol#L2-L2) 


```solidity

File: contracts/Bridge/L1/xRenzoBridge.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L2-L2) 


```solidity

File: contracts/Bridge/L1/xRenzoBridgeStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridgeStorage.sol#L2-L2) 


```solidity

File: contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol

2: pragma solidity ^0.8.13;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L2-L2) 


</details>


### [NC&#x2011;107] [NatSpec] Natspec `@param` is missing from `error` 



*There are 164 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/token/EzEthToken.sol

32:     /// @dev Initializes the contract with initial vars

40:     /// @dev Allows minter/burner to mint new ezETH tokens to an address

45:     /// @dev Allows minter/burner to burn ezETH tokens from an address

50:     /// @dev Sets the paused flag

55:     /// @dev


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L32-L32) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L40-L40), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L45-L45), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L50-L50), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L55-L55)


```solidity

File: contracts/Withdraw/WithdrawQueue.sol

19:     event WithdrawBufferTargetUpdated(uint256 oldBufferTarget, uint256 newBufferTarget);

21:     event CoolDownPeriodUpdated(uint256 oldCoolDownPeriod, uint256 newCoolDownPeriod);

23:     event EthBufferFilled(uint256 amount);

25:     event ERC20BufferFilled(address asset, uint256 amount);

27:     event WithdrawRequestCreated(

36:     event WithdrawRequestClaimed(WithdrawRequest withdrawRequest);

61:     /**
62:      * @notice  Initializes the contract with initial vars
63:      */


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L19-L19) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L21-L21), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L23-L23), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L25-L25), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L27-L27), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L36-L36), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L61-L63)


```solidity

File: contracts/Withdraw/WithdrawQueueStorage.sol

12:     struct TokenWithdrawBuffer {

17:     struct WithdrawRequest {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueueStorage.sol#L12-L12) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueueStorage.sol#L17-L17)


```solidity

File: contracts/TimelockController.sol

35:     /**
36:      * @dev Emitted when a call is scheduled as part of operation `id`.
37:      */

48:     /**
49:      * @dev Emitted when a call is performed as part of operation `id`.
50:      */

59:     /**
60:      * @dev Emitted when new proposal is scheduled with non-zero salt.
61:      */

64:     /**
65:      * @dev Emitted when operation `id` is cancelled.
66:      */

69:     /**
70:      * @dev Emitted when the minimum delay for future operations is modified.
71:      */

74:     /**
75:      * @dev Initializes the contract with the following parameters:
76:      *
77:      * - `minDelay`: initial minimum delay for operations
78:      * - `proposers`: accounts to be granted proposer and canceller roles
79:      * - `executors`: accounts to be granted executor role
80:      * - `admin`: optional account to be granted admin role; disable with zero address
81:      *
82:      * IMPORTANT: The optional admin can aid with initial configuration of roles after deployment
83:      * without being subject to delay, but this role should be subsequently renounced in favor of
84:      * administration through timelocked proposals. Previous versions of this contract would assign
85:      * this admin to the deployer automatically and should be renounced as well.
86:      */

121:     /**
122:      * @dev Modifier to make a function callable only by a certain role. In
123:      * addition to checking the sender's role, `address(0)` 's role is also
124:      * considered. Granting a role to `address(0)` is equivalent to enabling
125:      * this role for everyone.
126:      */

139:     /**
140:      * @dev See {IERC165-supportsInterface}.
141:      */

150:     /**
151:      * @dev Returns whether an id correspond to a registered operation. This
152:      * includes both Pending, Ready and Done operations.
153:      */

158:     /**
159:      * @dev Returns whether an operation is pending or not. Note that a "pending" operation may also be "ready".
160:      */

165:     /**
166:      * @dev Returns whether an operation is ready for execution. Note that a "ready" operation is also "pending".
167:      */

173:     /**
174:      * @dev Returns whether an operation is done or not.
175:      */

180:     /**
181:      * @dev Returns the timestamp at which an operation becomes ready (0 for
182:      * unset operations, 1 for done operations).
183:      */

197:     /**
198:      * @dev Returns the identifier of an operation containing a single
199:      * transaction.
200:      */

211:     /**
212:      * @dev Returns the identifier of an operation containing a batch of
213:      * transactions.
214:      */

225:     /**
226:      * @dev Schedule an operation containing a single transaction.
227:      *
228:      * Emits {CallSalt} if salt is nonzero, and {CallScheduled}.
229:      *
230:      * Requirements:
231:      *
232:      * - the caller must have the 'proposer' role.
233:      */

250:     /**
251:      * @dev Schedule an operation containing a batch of transactions.
252:      *
253:      * Emits {CallSalt} if salt is nonzero, and one {CallScheduled} event per transaction in the batch.
254:      *
255:      * Requirements:
256:      *
257:      * - the caller must have the 'proposer' role.
258:      */

280:     /**
281:      * @dev Schedule an operation that is to become valid after a given delay.
282:      */

289:     /**
290:      * @dev Cancel an operation.
291:      *
292:      * Requirements:
293:      *
294:      * - the caller must have the 'canceller' role.
295:      */

303:     /**
304:      * @dev Execute an (ready) operation containing a single transaction.
305:      *
306:      * Emits a {CallExecuted} event.
307:      *
308:      * Requirements:
309:      *
310:      * - the caller must have the 'executor' role.
311:      */

330:     /**
331:      * @dev Execute an (ready) operation containing a batch of transactions.
332:      *
333:      * Emits one {CallExecuted} event per transaction in the batch.
334:      *
335:      * Requirements:
336:      *
337:      * - the caller must have the 'executor' role.
338:      */

365:     /**
366:      * @dev Execute an operation's call.
367:      */

373:     /**
374:      * @dev Checks before execution of an operation's calls.
375:      */

384:     /**
385:      * @dev Checks after execution of an operation's calls.
386:      */

392:     /**
393:      * @dev Changes the minimum timelock duration for future operations.
394:      *
395:      * Emits a {MinDelayChange} event.
396:      *
397:      * Requirements:
398:      *
399:      * - the caller must be the timelock itself. This can only be achieved by scheduling and later executing
400:      * an operation where the timelock is the target and the data is the ABI-encoded call to this function.
401:      */

408:     /**
409:      * @dev See {IERC721Receiver-onERC721Received}.
410:      */

420:     /**
421:      * @dev See {IERC1155Receiver-onERC1155Received}.
422:      */

433:     /**
434:      * @dev See {IERC1155Receiver-onERC1155BatchReceived}.
435:      */


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L35-L37) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L48-L50), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L59-L61), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L64-L66), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L69-L71), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L74-L86), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L121-L126), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L139-L141), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L150-L153), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L158-L160), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L165-L167), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L173-L175), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L180-L183), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L197-L200), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L211-L214), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L225-L233), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L250-L258), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L280-L282), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L289-L295), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L303-L311), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L330-L338), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L365-L367), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L373-L375), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L384-L386), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L392-L401), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L408-L410), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L420-L422), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L433-L435)


```solidity

File: contracts/Rewards/RewardHandler.sol

29:     event RewardDestinationUpdated(address rewardDestination);

37:     /// @dev Initializes the contract with initial vars

72:     function setRewardDestination(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L29-L29) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L37-L37), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L72-L72)


```solidity

File: contracts/RestakeManagerStorage.sol

29:     struct PendingWithdrawal {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManagerStorage.sol#L29-L29) 


```solidity

File: contracts/RestakeManager.sol

30:     event OperatorDelegatorAdded(IOperatorDelegator od);

31:     event OperatorDelegatorRemoved(IOperatorDelegator od);

32:     event OperatorDelegatorAllocationUpdated(IOperatorDelegator od, uint256 allocation);

34:     event CollateralTokenAdded(IERC20 token);

35:     event CollateralTokenRemoved(IERC20 token);

40:     /// @dev Event emitted when a new deposit occurs

49:     /// @dev Event emitted when a new withdraw is started

58:     /// @dev Event emitted when a new withdraw is completed

67:     /// @dev Event emitted when a token TVL Limit is updated

100:     /// @dev Initializes the contract with initial vars

120:     /// @dev Allows a restake manager admin to set the paused state of the contract

130:     /// @dev Allows a restake manager admin to add an OperatorDelegator to the list

159:     /// @dev Allows a restake manager admin to remove an OperatorDelegator from the list

186:     /// @dev Allows restake manager admin to set an OperatorDelegator allocation

214:     /// @dev Allows a restake manager admin to set the max TVL for deposits.  If set to 0, no deposits will be enforced.

219:     /// @dev Allows restake manager to add a collateral token

243:     /// @dev Allows restake manager to remove a collateral token

360:     /// @dev Picks the OperatorDelegator with the TVL below the threshold or returns the first one in the list
361:     /// @return The OperatorDelegator to use

395:     /// @dev Determines the OD to withdraw from
396:     /// It will try to use the OD with the TVL above the allocation threshold that has the tokens to withdraw
397:     /// If no OD is over the allocation and has tokens, it will try to find one that has the tokens to withdraw
398:     /// If no OD has the tokens to withdraw, it will revert
399:     /// @return The OperatorDelegator to use

449:     /// @dev Finds the index of the collateral token in the list
450:     /// Reverts if the token is not found in the list

618:     /// @dev Called by the deposit queue to stake ETH to a validator
619:     /// Only callable by the deposit queue

645:     /// @dev Deposit ERC20 token rewards from the Deposit Queue
646:     /// Only callable by the deposit queue

709:     function setTokenTvlLimit(IERC20 _token, uint256 _limit) external onlyRestakeManagerAdmin {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L30-L30) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L31-L31), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L32-L32), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L34-L34), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L35-L35), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L40-L40), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L49-L49), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L58-L58), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L67-L67), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L100-L100), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L120-L120), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L130-L130), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L159-L159), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L186-L186), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L214-L214), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L219-L219), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L243-L243), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L360-L361), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L395-L399), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L449-L450), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L618-L619), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L645-L646), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L709-L709)


```solidity

File: contracts/RateProvider/BalancerRateProvider.sol

16:     /// @dev Initializes the contract with initial vars


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProvider.sol#L16-L16) 


```solidity

File: contracts/Permissions/RoleManager.sol

21:     /// @dev initializer to call after deployment, can only be called once


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L21-L21) 


```solidity

File: contracts/Oracle/RenzoOracle.sol

34:     /// @dev Event emitted when a token's oracle address is updated

43:     /// @dev Initializes the contract with initial vars

52:     /// @dev Sets addresses for oracle lookup.  Permission gated to oracel admins only.
53:     /// Set to address 0x0 to disable lookups for the token.

68:     /// @dev Given a single token and balance, return value of the asset in underlying currency
69:     /// The value returned will be denominated in the decimal precision of the lookup oracle
70:     /// (e.g. a value of 100 would return as 100 * 10^18)

83:     /// @dev Given a single token and value, return amount of tokens needed to represent that value
84:     /// Assumes the token value is already denominated in the same decimal precision as the oracle

101:     /// The value returned will be denominated in the decimal precision of the lookup oracle
102:     /// (e.g. a value of 100 would return as 100 * 10^18)

121:     /// @dev Given amount of current protocol value, new value being added, and supply of ezETH, determine amount to mint
122:     /// Values should be denominated in the same underlying currency with the same decimal precision

152:     function calculateRedeemAmount(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L34-L34) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L43-L43), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L52-L53), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L68-L70), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L83-L84), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L101-L102), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L121-L122), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L152-L152)


```solidity

File: contracts/Oracle/Mantle/METHShim.sol

22:     /// @dev Initializes the contract with initial vars

41:     /// @dev Historical data not available


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L22-L22) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L41-L41)


```solidity

File: contracts/Oracle/Binance/WBETHShim.sol

22:     /// @dev Initializes the contract with initial vars

41:     /// @dev Historical data not available


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L22-L22) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L41-L41)


```solidity

File: contracts/Errors/Errors.sol

28: /// @dev Error for invalid token decimals for collateral tokens (must be 18)
29: error InvalidTokenDecimals(uint8 expected, uint8 actual);

34: /// @dev Error when a different address tries to complete withdraw
35: error NotOriginalWithdrawCaller(address expectedCaller);

88: /// @dev Error when timestamp is invalid - likely in the past
89: error InvalidTimestamp(uint256 timestamp);

100: /// @dev Error when the sender is not expected
101: error InvalidSender(address expectedSender, address actualSender);

106: /// @dev error when xRenzoBridge does not have enough balance to pay for fee
107: error NotEnoughBalance(uint256 currentBalance, uint256 calculatedFees);

109: /// @dev error when source chain is not expected
110: error InvalidSourceChain(uint64 expectedCCIPChainSelector, uint64 actualCCIPChainSelector);

127: /// @dev Error for invalid bridge fee share configuration
128: error InvalidBridgeFeeShare(uint256 bridgeFee);

130: /// @dev Error for invalid sweep batch size
131: error InvalidSweepBatchSize(uint256 batchSize);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L28-L29) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L34-L35), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L88-L89), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L100-L101), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L106-L107), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L109-L110), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L127-L128), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L130-L131)


```solidity

File: contracts/Deposits/DepositQueue.sol

15:     event RewardsDeposited(IERC20 token, uint256 amount);

17:     event FeeConfigUpdated(address feeAddress, uint256 feeBasisPoints);

19:     event RestakeManagerUpdated(IRestakeManager restakeManager);

21:     event ETHDepositedFromProtocol(uint256 amount);

23:     event ETHStakedFromQueue(

30:     event ProtocolFeesPaid(IERC20 token, uint256 amount, address destination);

32:     event GasRefunded(address admin, uint256 gasRefunded);

34:     /// @dev Event emitted when withdrawQueue is updated

37:     /// @dev Event emitted when withdrawQueue buffer is filled for specified token

40:     /// @dev Event emitted when Full Withdrawal ETH is Received from Operator Delegators

73:     /// @dev Initializes the contract with initial vars

92:     /// @dev Sets the config for fees - if either value is set to 0 then fees are disabled

111:     /// @dev Sets the address of the RestakeManager contract

185:     /// @dev Function called by ETH Restake Admin to start the restaking process in Native ETH
186:     /// Only callable by a permissioned account

208:     /// @dev Function called by ETH Restake Admin to start the restaking process in Native ETH
209:     /// Only callable by a permissioned account
210:     /// Can stake multiple validators with 1 tx

252:     /// @dev Sweeps any accumulated ERC20 tokens in this contract to the RestakeManager
253:     /// Only callable by a permissioned account

291:     /**
292:      * @notice  Check if WithdrawBuffer Needs to be filled
293:      */


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L15-L15) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L17-L17), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L19-L19), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L21-L21), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L23-L23), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L30-L30), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L32-L32), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L34-L34), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L37-L37), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L40-L40), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L73-L73), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L92-L92), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L111-L111), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L185-L186), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L208-L210), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L252-L253), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L291-L293)


```solidity

File: contracts/Delegation/OperatorDelegator.sol

28:     event TokenStrategyUpdated(IERC20 token, IStrategy strategy);

29:     event DelegationAddressUpdated(address delegateAddress);

30:     event RewardsForwarded(address rewardDestination, uint256 amount);

32:     event WithdrawStarted(

43:     event WithdrawCompleted(bytes32 withdrawalRoot, IStrategy[] strategies, uint256[] shares);

45:     event GasSpent(address admin, uint256 gasSpent);

46:     event GasRefunded(address admin, uint256 gasRefunded);

47:     event BaseGasAmountSpentUpdated(uint256 oldBaseGasAmountSpent, uint256 newBaseGasAmountSpent);

73:     /// @dev Initializes the contract with initial vars

105:     /// @dev Sets the strategy for a given token - setting strategy to 0x0 removes the ability to deposit and withdraw token

116:     /// @dev Sets the address to delegate tokens to in EigenLayer -- THIS CAN ONLY BE SET ONCE

132:     function setBaseGasAmountSpent(

140:     /// @dev Deposit tokens into the EigenLayer.  This call assumes any balance of tokens in this contract will be delegated
141:     /// so do not directly send tokens here or they will be delegated and attributed to the next caller.
142:     /// @return shares The amount of new shares in the `strategy` created as part of the action.

171:     /// @dev Gets the index of the specific strategy in EigenLayer in the staker's strategy list

326:     /// @dev Gets the underlying token amount from the amount of shares + queued withdrawal shares

347:     /// @dev Stake ETH in the EigenLayer
348:     /// Only the Restake Manager should call this function

361:     /// @dev Verifies the withdrawal credentials for a withdrawal
362:     /// This will allow the EigenPodManager to verify the withdrawal credentials and credit the OD with shares
363:     /// Only the native eth restake admin should call this function


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L28-L28) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L29-L29), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L30-L30), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L32-L32), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L43-L43), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L45-L45), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L46-L46), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L47-L47), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L73-L73), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L105-L105), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L116-L116), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L132-L132), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L140-L142), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L171-L171), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L326-L326), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L347-L348), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L361-L363)


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol

48:     function supportsInterface(

64:     function mint(address _to, uint256 _amount) public override(XERC20, IOptimismMintableERC20) {

68:     function burn(address _from, uint256 _amount) public override(XERC20, IOptimismMintableERC20) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L48-L48) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L64-L64), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L68-L68)


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

42:     event PriceUpdated(uint256 price, uint256 timestamp);

43:     event Deposit(address indexed user, uint256 amountIn, uint256 amountOut);

44:     event BridgeSweeperAddressUpdated(address sweeper, bool allowed);

45:     event BridgeSwept(

51:     event OraclePriceFeedUpdated(address newOracle, address oldOracle);

52:     event ReceiverPriceFeedUpdated(address newReceiver, address oldReceiver);

53:     event SweeperBridgeFeeCollected(address sweeper, uint256 feeCollected);

54:     event BridgeFeeShareUpdated(uint256 oldBridgeFeeShare, uint256 newBridgeFeeShare);

55:     event SweepBatchSizeUpdated(uint256 oldSweepBatchSize, uint256 newSweepBatchSize);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L42-L42) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L43-L43), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L44-L44), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L45-L45), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L51-L51), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L52-L52), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L53-L53), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L54-L54), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L55-L55)


```solidity

File: contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol

23:     event XRenzoBridgeL1Updated(address newBridgeAddress, address oldBridgeAddress);

24:     event ConnextEthChainDomainUpdated(uint32 newSourceChainDomain, uint32 oldSourceChainDomain);

25:     event XRenzoDepositUpdated(address newRenzoDeposit, address oldRenzoDeposit);

43:     modifier onlySource(address _originSender, uint32 _origin) {

52:     constructor(address _connext, address _xRenzoBridgeL1, uint32 _connextEthChainDomain) {

69:     function xReceive(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L23-L23) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L24-L24), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L25-L25), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L43-L43), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L52-L52), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L69-L69)


```solidity

File: contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol

24:     event XRenzoBridgeL1Updated(address newBridgeAddress, address oldBridgeAddress);

25:     event CCIPEthChainSelectorUpdated(uint64 newSourceChainSelector, uint64 oldSourceChainSelector);

26:     event XRenzoDepositUpdated(address newRenzoDeposit, address oldRenzoDeposit);

43:     constructor(


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L24-L24) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L25-L25), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L26-L26), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L43-L43)


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2.sol

15:     event OracleAddressUpdated(address newOracle, address oldOracle);

23:     function initialize(AggregatorV3Interface _oracle) public initializer {

35:     /// @dev Sets addresses for oracle lookup.  Permission gated to owner only.


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L15-L15) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L23-L23), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L35-L35)


```solidity

File: contracts/Bridge/L1/xRenzoBridge.sol

24:     /// @dev Event emitted when bridge triggers ezETH mint

33:     /// @dev Event emitted when a message is sent to another chain.

43:     event ConnextMessageSent(

69:     /// @dev Initializes the contract with initial vars

129:     /**
130:      * @notice  Accepts collateral from the bridge
131:      * @dev     This function will take all collateral and deposit it into Renzo
132:      *          The ezETH from the deposit will be sent to the lockbox to be wrapped into xezETH
133:      *          The xezETH will be burned so that the xezETH on the L2 can be unwrapped for ezETH later
134:      * @notice  WARNING: This function does NOT whitelist who can send funds from the L2 via Connext.  Users should NOT
135:      *          send funds directly to this contract.  A user who sends funds directly to this contract will cause
136:      *          the tokens on the L2 to become over collateralized and will be a "donation" to protocol.  Only use
137:      *          the deposit contracts on the L2 to send funds to this contract.
138:      */


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L24-L24) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L33-L33), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L43-L43), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L69-L69), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L129-L138)


```solidity

File: contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol

10:     function getXERC20(address erc20) external view returns (address xerc20);

12:     function getERC20(address xerc20) external view returns (address erc20);

14:     function getLockbox(address erc20) external view returns (address xerc20);

18:     function bridgeERC20To(

35:     error InvalidRemoteToken(address _remoteToken);

39:     constructor(address _blastStandardBridge, address _registry) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L10-L10) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L12-L12), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L14-L14), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L18-L18), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L35-L35), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L39-L39)


```solidity

File: contracts/Bridge/Connext/libraries/LibConnextStorage.sol

38: struct TransferInfo {

64: struct ExecuteArgs {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/libraries/LibConnextStorage.sol#L38-L38) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/libraries/LibConnextStorage.sol#L64-L64)


```solidity

File: contracts/Bridge/Connext/libraries/TokenId.sol

9: struct TokenId {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/libraries/TokenId.sol#L9-L9) 


</details>


### [NC&#x2011;108] OpenZeppelin libraries should be upgraded to a newer version 
These contracts import some OpenZeppelin libraries, but they are using an old version.


*There are 104 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/token/EzEthToken.sol

4: import "@openzeppelin/contracts-upgradeable/token/ERC20/ERC20Upgradeable.sol";

5: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L4-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L5-L5)


```solidity

File: contracts/Withdraw/WithdrawQueue.sol

6: import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";

7: import "@openzeppelin/contracts-upgradeable/security/PausableUpgradeable.sol";

8: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";

9: import "@openzeppelin/contracts/token/ERC20/IERC20.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L6-L6) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L7-L7), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L8-L8), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L9-L9)


```solidity

File: contracts/TimelockController.sol

6: import "@openzeppelin/contracts/access/AccessControl.sol";

7: import "@openzeppelin/contracts/token/ERC721/IERC721Receiver.sol";

8: import "@openzeppelin/contracts/token/ERC1155/IERC1155Receiver.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L6-L6) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L7-L7), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L8-L8)


```solidity

File: contracts/Rewards/RewardHandler.sol

4: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

6: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L4-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L6-L6)


```solidity

File: contracts/RestakeManager.sol

4: import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";

5: import "@openzeppelin/contracts-upgradeable/token/ERC20/utils/SafeERC20Upgradeable.sol";

6: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

7: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";

8: import "@openzeppelin/contracts-upgradeable/token/ERC20/IERC20Upgradeable.sol";

9: import "@openzeppelin/contracts/token/ERC20/IERC20.sol";

10: import "@openzeppelin/contracts/token/ERC20/extensions/IERC20Metadata.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L4-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L5-L5), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L6-L6), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L7-L7), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L8-L8), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L9-L9), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L10-L10)


```solidity

File: contracts/RateProvider/BalancerRateProvider.sol

4: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProvider.sol#L4-L4) 


```solidity

File: contracts/RateProvider/BalancerRateProviderStorage.sol

4: import "@openzeppelin/contracts-upgradeable/token/ERC20/IERC20Upgradeable.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProviderStorage.sol#L4-L4) 


```solidity

File: contracts/Permissions/RoleManager.sol

4: import "@openzeppelin/contracts-upgradeable/access/AccessControlUpgradeable.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L4-L4) 


```solidity

File: contracts/Oracle/RenzoOracle.sol

4: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L4-L4) 


```solidity

File: contracts/Oracle/RenzoOracleStorage.sol

6: import "@openzeppelin/contracts/token/ERC20/IERC20.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracleStorage.sol#L6-L6) 


```solidity

File: contracts/Oracle/Mantle/METHShim.sol

4: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";

5: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L4-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L5-L5)


```solidity

File: contracts/Oracle/Binance/WBETHShim.sol

4: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";

5: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L4-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L5-L5)


```solidity

File: contracts/Deposits/DepositQueue.sol

4: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

5: import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";

7: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L4-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L5-L5), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L7-L7)


```solidity

File: contracts/Delegation/OperatorDelegator.sol

4: import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";

5: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L4-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L5-L5)


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20.sol

5: import {

8: import {

11: import {

14: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L5-L5) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L8-L8), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L11-L11), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L14-L14)


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Factory.sol

8: import {

11: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

12: import "@openzeppelin/contracts/proxy/transparent/TransparentUpgradeableProxy.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L8-L8) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L11-L11), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L12-L12)


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol

4: import {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L4-L4) 


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol

8: import {

11: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

12: import "@openzeppelin/contracts/proxy/transparent/TransparentUpgradeableProxy.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L8-L8) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L11-L11), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L12-L12)


```solidity

File: contracts/Bridge/L2/xRenzoDepositStorage.sol

5: import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L5-L5) 


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

5: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

6: import {

9: import {

15: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L5-L5) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L6-L6), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L9-L9), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L15-L15)


```solidity

File: contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol

5: import { Ownable } from "@openzeppelin/contracts/access/Ownable.sol";

6: import { Pausable } from "@openzeppelin/contracts/security/Pausable.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L5-L5) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L6-L6)


```solidity

File: contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol

8: import { Ownable } from "@openzeppelin/contracts/access/Ownable.sol";

9: import { Pausable } from "@openzeppelin/contracts/security/Pausable.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L8-L8) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L9-L9)


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2.sol

5: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

6: import {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L5-L5) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L6-L6)


```solidity

File: contracts/Bridge/L1/xRenzoBridge.sol

5: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

7: import {

14: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L5-L5) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L7-L7), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L14-L14)


```solidity

File: contracts/Bridge/L1/xRenzoBridgeStorage.sol

5: import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridgeStorage.sol#L5-L5) 


```solidity

File: contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol

4: import { SafeERC20 } from "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";

5: import { IERC20 } from "@openzeppelin/contracts/token/ERC20/IERC20.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L4-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L5-L5)


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol

5: import { IERC20 } from "@openzeppelin/contracts/token/ERC20/ERC20.sol";

6: import { SafeERC20 } from "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";

7: import { SafeCast } from "@openzeppelin/contracts/utils/math/SafeCast.sol";

9: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L5-L5) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L6-L6), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L7-L7), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L9-L9)


```solidity

File: contracts/token/EzEthToken.sol

4: import "@openzeppelin/contracts-upgradeable/token/ERC20/ERC20Upgradeable.sol";

5: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L4-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L5-L5)


```solidity

File: contracts/Withdraw/WithdrawQueue.sol

7: import "@openzeppelin/contracts-upgradeable/security/PausableUpgradeable.sol";

8: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L7-L7) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L8-L8)


```solidity

File: contracts/Rewards/RewardHandler.sol

4: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

6: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L4-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L6-L6)


```solidity

File: contracts/RestakeManager.sol

5: import "@openzeppelin/contracts-upgradeable/token/ERC20/utils/SafeERC20Upgradeable.sol";

6: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

7: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";

8: import "@openzeppelin/contracts-upgradeable/token/ERC20/IERC20Upgradeable.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L5-L5) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L6-L6), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L7-L7), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L8-L8)


```solidity

File: contracts/RateProvider/BalancerRateProvider.sol

4: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProvider.sol#L4-L4) 


```solidity

File: contracts/RateProvider/BalancerRateProviderStorage.sol

4: import "@openzeppelin/contracts-upgradeable/token/ERC20/IERC20Upgradeable.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProviderStorage.sol#L4-L4) 


```solidity

File: contracts/Permissions/RoleManager.sol

4: import "@openzeppelin/contracts-upgradeable/access/AccessControlUpgradeable.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L4-L4) 


```solidity

File: contracts/Oracle/RenzoOracle.sol

4: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L4-L4) 


```solidity

File: contracts/Oracle/Mantle/METHShim.sol

4: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";

5: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L4-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L5-L5)


```solidity

File: contracts/Oracle/Binance/WBETHShim.sol

4: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";

5: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L4-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L5-L5)


```solidity

File: contracts/Deposits/DepositQueue.sol

4: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

7: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L4-L4) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L7-L7)


```solidity

File: contracts/Delegation/OperatorDelegator.sol

5: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L5-L5) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20.sol

5: import {

8: import {

11: import {

14: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L5-L5) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L8-L8), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L11-L11), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L14-L14)


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Factory.sol

8: import {

11: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L8-L8) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L11-L11)


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol

4: import {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L4-L4) 


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol

8: import {

11: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L8-L8) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L11-L11)


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

5: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

6: import {

9: import {

15: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L5-L5) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L6-L6), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L9-L9), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L15-L15)


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2.sol

5: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

6: import {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L5-L5) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L6-L6)


```solidity

File: contracts/Bridge/L1/xRenzoBridge.sol

5: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";

7: import {

14: import "@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L5-L5) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L7-L7), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L14-L14)


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol

9: import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L9-L9) 


</details>


### [NC&#x2011;109] Not using the latest version of `prb-math` from dependencies 
`prb-math` is an important mathematical library The package.json configuration file says that the project is using an old version of `prb-math`.


*There are 1 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: package.json

//@audit `prb-math` version is 
1: 


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//package.json#L1-L1) 


</details>


### [NC&#x2011;110] Non constant/immutable state variables are missing a setter post deployment 
Non-constant or non-immutable state variables lacking a setter function can create inflexibility in contract operations. If there's no way to update these variables post-deployment, the contract might not adapt to changing conditions or requirements, which can be a significant drawback, especially in upgradable or long-lived contracts. To resolve this, implement setter functions guarded by appropriate access controls, like `onlyOwner` or similar modifiers, so that these variables can be updated as required while maintaining security. This enables smoother contract maintenance and feature upgrades.


*There are 82 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/token/EzEthTokenStorage.sol

12:     IRoleManager public roleManager;

15:     bool public paused;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthTokenStorage.sol#L12-L12) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthTokenStorage.sol#L15-L15)


```solidity

File: contracts/Withdraw/WithdrawQueueStorage.sol

26:     IRenzoOracle public renzoOracle;

29:     IEzEthToken public ezETH;

32:     IRoleManager public roleManager;

35:     IRestakeManager public restakeManager;

38:     uint256 public coolDownPeriod;

41:     uint256 public withdrawRequestNonce;

44:     mapping(address => uint256) public withdrawalBufferTarget;

47:     mapping(address => uint256) public claimReserve;

50:     mapping(address => WithdrawRequest[]) public withdrawRequests;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueueStorage.sol#L26-L26) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueueStorage.sol#L29-L29), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueueStorage.sol#L32-L32), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueueStorage.sol#L35-L35), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueueStorage.sol#L38-L38), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueueStorage.sol#L41-L41), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueueStorage.sol#L44-L44), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueueStorage.sol#L47-L47), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueueStorage.sol#L50-L50)


```solidity

File: contracts/Rewards/RewardHandlerStorage.sol

8:     IRoleManager public roleManager;

11:     address public rewardDestination;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandlerStorage.sol#L8-L8) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandlerStorage.sol#L11-L11)


```solidity

File: contracts/RestakeManagerStorage.sol

17:     IRoleManager public roleManager;

20:     IEzEthToken public ezETH;

23:     IStrategyManager public strategyManager;

26:     IDelegationManager public delegationManager;

39:     mapping(bytes32 => PendingWithdrawal) public pendingWithdrawals;

42:     IOperatorDelegator[] public operatorDelegators;

46:     mapping(IOperatorDelegator => uint256) public operatorDelegatorAllocations;

49:     IERC20[] public collateralTokens;

52:     IRenzoOracle public renzoOracle;

55:     bool public paused;

58:     uint256 public maxDepositTVL;

61:     IDepositQueue public depositQueue;

65:     mapping(IERC20 => uint256) public collateralTokenTvlLimits;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManagerStorage.sol#L17-L17) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManagerStorage.sol#L20-L20), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManagerStorage.sol#L23-L23), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManagerStorage.sol#L26-L26), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManagerStorage.sol#L39-L39), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManagerStorage.sol#L42-L42), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManagerStorage.sol#L46-L46), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManagerStorage.sol#L49-L49), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManagerStorage.sol#L52-L52), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManagerStorage.sol#L55-L55), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManagerStorage.sol#L58-L58), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManagerStorage.sol#L61-L61), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManagerStorage.sol#L65-L65)


```solidity

File: contracts/RateProvider/BalancerRateProviderStorage.sol

9:     IRestakeManager public restakeManager;

12:     IERC20Upgradeable public ezETHToken;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProviderStorage.sol#L9-L9) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProviderStorage.sol#L12-L12)


```solidity

File: contracts/Oracle/RenzoOracleStorage.sol

10:     IRoleManager public roleManager;

13:     mapping(IERC20 => AggregatorV3Interface) public tokenOracleLookup;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracleStorage.sol#L10-L10) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracleStorage.sol#L13-L13)


```solidity

File: contracts/Oracle/Mantle/METHShimStorage.sol

8:     IMethStaking public methStaking;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShimStorage.sol#L8-L8) 


```solidity

File: contracts/Oracle/Binance/WBETHShimStorage.sol

8:     IStakedTokenV2 public wBETHToken;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShimStorage.sol#L8-L8) 


```solidity

File: contracts/Deposits/DepositQueueStorage.sol

11:     IRoleManager public roleManager;

14:     IRestakeManager public restakeManager;

17:     address public feeAddress;

20:     uint256 public feeBasisPoints;

23:     mapping(address => uint256) public totalEarned;

27:     IWithdrawQueue public withdrawQueue;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueueStorage.sol#L11-L11) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueueStorage.sol#L14-L14), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueueStorage.sol#L17-L17), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueueStorage.sol#L20-L20), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueueStorage.sol#L23-L23), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueueStorage.sol#L27-L27)


```solidity

File: contracts/Delegation/OperatorDelegatorStorage.sol

18:     IRoleManager public roleManager;

21:     IStrategyManager public strategyManager;

24:     IRestakeManager public restakeManager;

28:     mapping(IERC20 => IStrategy) public tokenStrategyMapping;

31:     address public delegateAddress;

34:     IDelegationManager public delegationManager;

37:     IEigenPodManager public eigenPodManager;

40:     IEigenPod public eigenPod;

43:     uint256 public stakedButNotVerifiedEth;

48:     uint256 public pendingUnstakedDelayedWithdrawalAmount;

53:     uint256 public baseGasAmountSpent;

56:     mapping(address => uint256) public adminGasSpentInWei;

61:     mapping(address => uint256) public queuedShares;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegatorStorage.sol#L18-L18) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegatorStorage.sol#L21-L21), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegatorStorage.sol#L24-L24), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegatorStorage.sol#L28-L28), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegatorStorage.sol#L31-L31), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegatorStorage.sol#L34-L34), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegatorStorage.sol#L37-L37), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegatorStorage.sol#L40-L40), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegatorStorage.sol#L43-L43), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegatorStorage.sol#L48-L48), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegatorStorage.sol#L53-L53), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegatorStorage.sol#L56-L56), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegatorStorage.sol#L61-L61)


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20.sol

41:     mapping(address => Bridge) public bridges;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L41-L41) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Factory.sol

25:     EnumerableSetUpgradeable.AddressSet internal _lockboxRegistryArray;

30:     EnumerableSetUpgradeable.AddressSet internal _xerc20RegistryArray;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L25-L25) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L30-L30)


```solidity

File: contracts/Bridge/L2/xRenzoDepositStorage.sol

11:     uint256 public lastPriceTimestamp;

14:     uint256 public lastPrice;

17:     IERC20 public xezETH;

20:     IERC20 public depositToken;

23:     IERC20 public collateralToken;

26:     IConnext public connext;

29:     bytes32 public swapKey;

32:     address public receiver;

35:     uint256 public bridgeRouterFeeBps;

38:     uint32 public bridgeDestinationDomain;

41:     address public bridgeTargetAddress;

44:     mapping(address => bool) public allowedBridgeSweepers;

49:     IRenzoOracleL2 public oracle;

54:     uint256 public bridgeFeeShare;

57:     uint256 public sweepBatchSize;

60:     uint256 public bridgeFeeCollected;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L11-L11) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L14-L14), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L17-L17), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L20-L20), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L23-L23), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L26-L26), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L29-L29), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L32-L32), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L35-L35), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L38-L38), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L41-L41), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L44-L44), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L49-L49), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L54-L54), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L57-L57), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L60-L60)


```solidity

File: contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol

12:     address public connext;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L12-L12) 


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2Storage.sol

8:     AggregatorV3Interface public oracle;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2Storage.sol#L8-L8) 


```solidity

File: contracts/Bridge/L1/xRenzoBridgeStorage.sol

20:     IERC20 public xezETH;

23:     IERC20 public ezETH;

26:     IRestakeManager public restakeManager;

29:     IERC20 public wETH;

32:     IXERC20Lockbox public xezETHLockbox;

35:     IConnext public connext;

38:     IRateProvider public rateProvider;

41:     IRouterClient public linkRouterClient;

44:     LinkTokenInterface public linkToken;

47:     IRoleManager public roleManager;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridgeStorage.sol#L20-L20) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridgeStorage.sol#L23-L23), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridgeStorage.sol#L26-L26), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridgeStorage.sol#L29-L29), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridgeStorage.sol#L32-L32), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridgeStorage.sol#L35-L35), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridgeStorage.sol#L38-L38), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridgeStorage.sol#L41-L41), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridgeStorage.sol#L44-L44), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridgeStorage.sol#L47-L47)


</details>


### [NC&#x2011;111] Consider making private state variables internal to increase flexibility 
In Solidity, `private` state variables are strictly confined to the contract they are defined in and can't be accessed or modified by its derived contracts. While this offers strong encapsulation, it can limit contract extensibility and modification in inheritance chains. On the other hand, `internal` variables can be accessed and potentially overridden by child contracts, granting more flexibility in contract development and upgrades. Therefore, it's recommended to use `private` only when you explicitly want to prevent child contract access. Otherwise, prefer `internal` to maintain a balance between encapsulation and the flexibility offered by inheritance patterns in Solidity.


*There are 3 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/TimelockController.sol

32:     mapping(bytes32 => uint256) private _timestamps;

33:     uint256 private _minDelay;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L32-L32) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L33-L33)


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20.sol

26:     uint256 private constant _DURATION = 1 days;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L26-L26) 


</details>


### [NC&#x2011;112] Using Low-Level Call for Transfers 
Utilizing low-level calls like `.call{value: value}` for Ether transfers in Ethereum can be risky, as it can inadvertently allow malicious contract executions through fallback functions. To mitigate these risks and ensure safer Ether transfers, it is recommended to adopt more secure and explicit methods provided by reputable libraries such as OpenZeppelin. Functions like `Address.sendValue()` from OpenZeppelin provide a clearer and safer alternative for sending Ether, as they encapsulate necessary checks and error handling, ensuring that Ether is transferred securely and any errors are appropriately dealt with. This not only enhances the security of your smart contract but also improves code readability and maintainability, aligning with modern Solidity development practices.


*There are 7 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/TimelockController.sol

369:         (bool success, ) = target.call{ value: value }(data);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L369-L369) 


```solidity

File: contracts/Rewards/RewardHandler.sol

68:         (bool success, ) = rewardDestination.call{ value: balance }("");


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L68-L68) 


```solidity

File: contracts/Deposits/DepositQueue.sol

286:         (bool success, ) = payable(msg.sender).call{ value: gasRefund }("");

168:             (bool success, ) = feeAddress.call{ value: feeAmount }("");


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L286-L286) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L168-L168)


```solidity

File: contracts/Delegation/OperatorDelegator.sol

520:             (bool success, ) = destination.call{ value: remainingAmount }("");


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L520-L520) 


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

403:         (bool success, ) = payable(msg.sender).call{ value: feeCollected }("");


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L403-L403) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol

131:             (bool _success, ) = payable(_to).call{ value: _amount }("");


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L131-L131) 


</details>


### [NC&#x2011;113] Off-by-one timestamp error 
In Solidity, using `>=` or `<=` to compare against `block.timestamp` (alias `now`) may introduce off-by-one errors due to the fact that `block.timestamp` is only updated once per block and its value remains constant throughout the block's execution. If an operation happens at the exact second when `block.timestamp` changes, it could result in unexpected behavior. To avoid this, it's safer to use strict inequality operators (`>` or `<`). For instance, if a condition should only be met after a certain time, use `block.timestamp > time` rather than `block.timestamp >= time`. This way, potential off-by-one errors due to the exact timing of block mining are mitigated, leading to safer, more predictable contract behavior.


*There are 2 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/TimelockController.sol

170:         return timestamp > _DONE_TIMESTAMP && timestamp <= block.timestamp;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L170-L170) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20.sol

311:         } else if (_timestamp + _DURATION <= block.timestamp) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L311-L311) 


</details>


### [NC&#x2011;114] Lack of space near the operator 
Lack of space near operators in code can lead to reduced readability, making it more challenging to distinguish between different elements and understand the logic quickly. As a resolution, always include spaces around operators to ensure a clear visual separation, which promotes better maintainability and comprehension of the code.


*There are 8 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/RateProvider/BalancerRateProvider.sol

//@audit operator : /
40:         return (10 ** 18 * totalTVL) / totalSupply;

//@audit operator : *
40:         return (10 ** 18 * totalTVL) / totalSupply;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProvider.sol#L40-L40) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProvider.sol#L40-L40)


```solidity

File: contracts/Oracle/RenzoOracle.sol

//@audit operator : +
26:     uint256 constant MAX_TIME_WINDOW = 86400 + 60; // 24 hours + 60 seconds


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L26-L26) 


```solidity

File: contracts/Delegation/OperatorDelegator.sol

//@audit operator : -
343:                 ? queuedShares[IS_NATIVE] + stakedButNotVerifiedEth - uint256(-podOwnerShares)

//@audit operator : +
343:                 ? queuedShares[IS_NATIVE] + stakedButNotVerifiedEth - uint256(-podOwnerShares)


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L343-L343) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L343-L343)


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2.sol

//@audit operator : +
13:     uint256 public constant MAX_TIME_WINDOW = 86400 + 60; // 24 hours + 60 seconds

//@audit operator : *
54:         uint256 _scaledPrice = (uint256(price)) * 10 ** (18 - oracle.decimals());

//@audit operator : -
54:         uint256 _scaledPrice = (uint256(price)) * 10 ** (18 - oracle.decimals());


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L13-L13) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L54-L54), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L54-L54)


</details>


### [NC&#x2011;115] Incorrect withdraw declaration 
In Solidity, it's essential for clarity and interoperability to correctly specify return types in function declarations. If the `withdraw` function is expected to return a `bool` to indicate success or failure, its omission could lead to ambiguity or unexpected behavior when interacting with or calling this function from other contracts or off-chain systems. Missing return values can mislead developers and potentially lead to contract integrations built on incorrect assumptions. To resolve this, the function declaration for `withdraw` should be modified to explicitly include the `bool` return type, ensuring clarity and correctness in contract interactions.


*There are 2 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Withdraw/WithdrawQueue.sol

206:     function withdraw(uint256 _amount, address _assetOut) external nonReentrant {
207:         // check for 0 values
208:         if (_amount == 0 || _assetOut == address(0)) revert InvalidZeroInput();
209: 
210:         // check if provided assetOut is supported
211:         if (withdrawalBufferTarget[_assetOut] == 0) revert UnsupportedWithdrawAsset();
212: 
213:         // transfer ezETH tokens to this address
214:         IERC20(address(ezETH)).safeTransferFrom(msg.sender, address(this), _amount);
215: 
216:         // calculate totalTVL
217:         (, , uint256 totalTVL) = restakeManager.calculateTVLs();
218: 
219:         // Calculate amount to Redeem in ETH
220:         uint256 amountToRedeem = renzoOracle.calculateRedeemAmount(
221:             _amount,
222:             ezETH.totalSupply(),
223:             totalTVL
224:         );
225: 
226:         // update amount in claim asset, if claim asset is not ETH
227:         if (_assetOut != IS_NATIVE) {
228:             // Get ERC20 asset equivalent amount
229:             amountToRedeem = renzoOracle.lookupTokenAmountFromValue(
230:                 IERC20(_assetOut),
231:                 amountToRedeem
232:             );
233:         }
234: 
235:         // revert if amount to redeem is greater than withdrawBufferTarget
236:         if (amountToRedeem > getAvailableToWithdraw(_assetOut)) revert NotEnoughWithdrawBuffer();
237: 
238:         // increment the withdrawRequestNonce
239:         withdrawRequestNonce++;
240: 
241:         // add withdraw request for msg.sender
242:         withdrawRequests[msg.sender].push(
243:             WithdrawRequest(
244:                 _assetOut,
245:                 withdrawRequestNonce,
246:                 amountToRedeem,
247:                 _amount,
248:                 block.timestamp
249:             )
250:         );
251: 
252:         // add redeem amount to claimReserve of claim asset
253:         claimReserve[_assetOut] += amountToRedeem;
254: 
255:         emit WithdrawRequestCreated(
256:             withdrawRequestNonce,
257:             msg.sender,
258:             _assetOut,
259:             amountToRedeem,
260:             _amount,
261:             withdrawRequests[msg.sender].length - 1
262:         );
263:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L206-L263) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol

103:     function withdraw(uint256 _amount) external {
104:         _withdraw(msg.sender, _amount);
105:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L103-L105) 


</details>


### [NC&#x2011;116] Avoid mutating function parameters 
Function parameters in Solidity are passed by value, meaning they are essentially local copies. Mutating them can lead to confusion and errors because the changes don't persist outside the function. By keeping function parameters immutable, you ensure clarity in code behavior, preventing unintended side-effects. If you need to modify a value based on a parameter, use a local variable inside the function, leaving the original parameter unaltered. By adhering to this practice, you maintain a clear distinction between input data and the internal processing logic, improving code readability and reducing the potential for bugs.


*There are 2 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/RestakeManager.sol

//@audit the following parameters are mutated _amount,
491:     function deposit(
492:         IERC20 _collateralToken,
493:         uint256 _amount,
494:         uint256 _referralId
495:     ) public nonReentrant notPaused {
496:         // Verify collateral token is in the list - call will revert if not found
497:         uint256 tokenIndex = getCollateralTokenIndex(_collateralToken);
498: 
499:         // Get the TVLs for each operator delegator and the total TVL
500:         (
501:             uint256[][] memory operatorDelegatorTokenTVLs,
502:             uint256[] memory operatorDelegatorTVLs,
503:             uint256 totalTVL
504:         ) = calculateTVLs();
505: 
506:         // Get the value of the collateral token being deposited
507:         uint256 collateralTokenValue = renzoOracle.lookupTokenValue(_collateralToken, _amount);
508: 
509:         // Enforce TVL limit if set, 0 means the check is not enabled
510:         if (maxDepositTVL != 0 && totalTVL + collateralTokenValue > maxDepositTVL) {
511:             revert MaxTVLReached();
512:         }
513: 
514:         // Enforce individual token TVL limit if set, 0 means the check is not enabled
515:         if (collateralTokenTvlLimits[_collateralToken] != 0) {
516:             // Track the current token's TVL
517:             uint256 currentTokenTVL = 0;
518: 
519:             // For each OD, add up the token TVLs
520:             uint256 odLength = operatorDelegatorTokenTVLs.length;
521:             for (uint256 i = 0; i < odLength; ) {
522:                 currentTokenTVL += operatorDelegatorTokenTVLs[i][tokenIndex];
523:                 unchecked {
524:                     ++i;
525:                 }
526:             }
527: 
528:             // Check if it is over the limit
529:             if (currentTokenTVL + collateralTokenValue > collateralTokenTvlLimits[_collateralToken])
530:                 revert MaxTokenTVLReached();
531:         }
532: 
533:         // Determine which operator delegator to use
534:         IOperatorDelegator operatorDelegator = chooseOperatorDelegatorForDeposit(
535:             operatorDelegatorTVLs,
536:             totalTVL
537:         );
538: 
539:         // Transfer the collateral token to this address
540:         _collateralToken.safeTransferFrom(msg.sender, address(this), _amount);
541: 
542:         // Check the withdraw buffer and fill if below buffer target
543:         uint256 bufferToFill = depositQueue.withdrawQueue().getBufferDeficit(
544:             address(_collateralToken)
545:         );
546:         if (bufferToFill > 0) {
547:             bufferToFill = (_amount <= bufferToFill) ? _amount : bufferToFill;
548:             // update amount to send to the operator Delegator
549:             _amount -= bufferToFill;
550: 
551:             // safe Approve for depositQueue
552:             _collateralToken.safeApprove(address(depositQueue), bufferToFill);
553: 
554:             // fill Withdraw Buffer via depositQueue
555:             depositQueue.fillERC20withdrawBuffer(address(_collateralToken), bufferToFill);
556:         }
557: 
558:         // Approve the tokens to the operator delegator
559:         _collateralToken.safeApprove(address(operatorDelegator), _amount);
560: 
561:         // Call deposit on the operator delegator
562:         operatorDelegator.deposit(_collateralToken, _amount);
563: 
564:         // Calculate how much ezETH to mint
565:         uint256 ezETHToMint = renzoOracle.calculateMintAmount(
566:             totalTVL,
567:             collateralTokenValue,
568:             ezETH.totalSupply()
569:         );
570: 
571:         // Mint the ezETH
572:         ezETH.mint(msg.sender, ezETHToMint);
573: 
574:         // Emit the deposit event
575:         emit Deposit(msg.sender, _collateralToken, _amount, ezETHToMint, _referralId);
576:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L491-L576) 


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

//@audit the following parameters are mutated _amountIn,
227:     function _deposit(
228:         uint256 _amountIn,
229:         uint256 _minOut,
230:         uint256 _deadline
231:     ) internal returns (uint256) {
232:         // calculate bridgeFee for deposit amount
233:         uint256 bridgeFee = getBridgeFeeShare(_amountIn);
234:         // subtract from _amountIn and add to bridgeFeeCollected
235:         _amountIn -= bridgeFee;
236:         bridgeFeeCollected += bridgeFee;
237: 
238:         // Trade deposit tokens for nextWETH
239:         uint256 amountOut = _trade(_amountIn, _deadline);
240:         if (amountOut == 0) {
241:             revert InvalidZeroOutput();
242:         }
243: 
244:         // Fetch price and timestamp of ezETH from the configured price feed
245:         (uint256 _lastPrice, uint256 _lastPriceTimestamp) = getMintRate();
246: 
247:         // Verify the price is not stale
248:         if (block.timestamp > _lastPriceTimestamp + 1 days) {
249:             revert OraclePriceExpired();
250:         }
251: 
252:         // Calculate the amount of xezETH to mint - assumes 18 decimals for price and token
253:         uint256 xezETHAmount = (1e18 * amountOut) / _lastPrice;
254: 
255:         // Check that the user will get the minimum amount of xezETH
256:         if (xezETHAmount < _minOut) {
257:             revert InsufficientOutputAmount();
258:         }
259: 
260:         // Verify the deadline has not passed
261:         if (block.timestamp > _deadline) {
262:             revert InvalidTimestamp(_deadline);
263:         }
264: 
265:         // Mint xezETH to the user
266:         IXERC20(address(xezETH)).mint(msg.sender, xezETHAmount);
267: 
268:         // Emit the event and return amount minted
269:         emit Deposit(msg.sender, _amountIn, xezETHAmount);
270:         return xezETHAmount;
271:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L227-L271) 


</details>


### [NC&#x2011;117] A event should be emitted if a non immutable state variable is set in a constructor 



*There are 7 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol

57:         connext = _connext;

60:         xRenzoBridgeL1 = _xRenzoBridgeL1;

63:         connextEthChainDomain = _connextEthChainDomain;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L57-L57) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L60-L60), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L63-L63)


```solidity

File: contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol

51:         xRenzoBridgeL1 = _xRenzoBridgeL1;

54:         ccipEthChainSelector = _ccipEthChainSelector;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L51-L51) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L54-L54)


```solidity

File: contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol

45:         blastStandardBridge = _blastStandardBridge;

46:         registry = _registry;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L45-L45) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L46-L46)


</details>


### [NC&#x2011;118] Returning a struct instead of returning many variables is better 
Returning a struct from a Solidity function instead of multiple variables offers several benefits, enhancing code clarity and efficiency. Structs allow for the grouping of related data into a single entity, making the function's return values more organized and easier to manage. This approach significantly improves readability, as it encapsulates the data logically, helping developers quickly understand the returned information's structure. Additionally, it simplifies function interfaces, reducing the potential for errors when handling multiple return values. By using structs, you can also easily extend or modify the returned data without altering the function signature, facilitating smoother updates and maintenance of your smart contract code.


*There are 6 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Oracle/Mantle/METHShim.sol

42:     function getRoundData(uint80) external pure returns (uint80, int256, uint256, uint256, uint80) {
43:         revert NotImplemented();
44:     }

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
56:     {
57:         return _getMETHData();
58:     }

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
79:     {
80:         return (0, int256(methStaking.mETHToETH(1 ether)), 0, block.timestamp, 0);
81:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L42-L44) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L46-L58), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L69-L81)


```solidity

File: contracts/Oracle/Binance/WBETHShim.sol

42:     function getRoundData(uint80) external pure returns (uint80, int256, uint256, uint256, uint80) {
43:         revert NotImplemented();
44:     }

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
56:     {
57:         return _getWBETHData();
58:     }

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
79:     {
80:         return (0, int256(wBETHToken.exchangeRate()), 0, block.timestamp, 0);
81:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L42-L44) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L46-L58), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L69-L81)


</details>


### [NC&#x2011;119] [Solidity]: Order of Argument Evaluation Disrupted in Non-Expression-Split Code by Optimizer Sequences with FullInliner 
Function call arguments in Yul are evaluated right to left. This order matters when the argument expressions have side-effects, and changing it may change contract behavior. FullInliner is an optimizer step that can replace a function call with the body of that function. The transformation involves assigning argument expressions to temporary variables, which imposes an explicit evaluation order. FullInliner was written with the assumption that this order does not necessarily have to match usual argument evaluation order because the argument expressions have no side-effects. In most circumstances this assumption is true because the default optimization step sequence contains the ExpressionSplitter step. ExpressionSplitter ensures that the code is in *expression-split form*, which means that function calls cannot appear nested inside expressions, and all function call arguments have to be variables. The assumption is, however, not guaranteed to be true in general. Version 0.6.7 introduced a setting allowing users to specify an arbitrary optimization step sequence, making it possible for the FullInliner to actually encounter argument expressions with side-effects, which can result in behavior differences between optimized and unoptimized bytecode. Contracts compiled without optimization or with the default optimization sequence are not affected. To trigger the bug the user has to explicitly choose compiler settings that contain a sequence with FullInliner step not preceded by ExpressionSplitter. [Ref](https://blog.soliditylang.org/2023/07/19/full-inliner-non-expression-split-argument-evaluation-order-bug/)


*There are 35 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/token/EzEthTokenStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthTokenStorage.sol#L2-L2) 


```solidity

File: contracts/token/EzEthToken.sol

2: pragma solidity ^0.8.9;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L2-L2) 


```solidity

File: contracts/Withdraw/WithdrawQueue.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L2-L2) 


```solidity

File: contracts/Withdraw/WithdrawQueueStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueueStorage.sol#L2-L2) 


```solidity

File: contracts/TimelockController.sol

4: pragma solidity ^0.8.0;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L4-L4) 


```solidity

File: contracts/Rewards/RewardHandlerStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandlerStorage.sol#L2-L2) 


```solidity

File: contracts/Rewards/RewardHandler.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Rewards/RewardHandler.sol#L2-L2) 


```solidity

File: contracts/RestakeManagerStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManagerStorage.sol#L2-L2) 


```solidity

File: contracts/RestakeManager.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L2-L2) 


```solidity

File: contracts/RateProvider/BalancerRateProvider.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProvider.sol#L2-L2) 


```solidity

File: contracts/RateProvider/BalancerRateProviderStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProviderStorage.sol#L2-L2) 


```solidity

File: contracts/Permissions/RoleManager.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L2-L2) 


```solidity

File: contracts/Permissions/RoleManagerStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManagerStorage.sol#L2-L2) 


```solidity

File: contracts/Oracle/RenzoOracle.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L2-L2) 


```solidity

File: contracts/Oracle/RenzoOracleStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracleStorage.sol#L2-L2) 


```solidity

File: contracts/Oracle/Mantle/METHShim.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L2-L2) 


```solidity

File: contracts/Oracle/Mantle/METHShimStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShimStorage.sol#L2-L2) 


```solidity

File: contracts/Oracle/Binance/WBETHShimStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShimStorage.sol#L2-L2) 


```solidity

File: contracts/Oracle/Binance/WBETHShim.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L2-L2) 


```solidity

File: contracts/Errors/Errors.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Errors/Errors.sol#L2-L2) 


```solidity

File: contracts/Deposits/DepositQueueStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueueStorage.sol#L2-L2) 


```solidity

File: contracts/Deposits/DepositQueue.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L2-L2) 


```solidity

File: contracts/Delegation/OperatorDelegator.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L2-L2) 


```solidity

File: contracts/Delegation/OperatorDelegatorStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegatorStorage.sol#L2-L2) 


```solidity

File: contracts/Bridge/L2/xRenzoDepositStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDepositStorage.sol#L2-L2) 


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L2-L2) 


```solidity

File: contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L2-L2) 


```solidity

File: contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/CCIPReceiver.sol#L2-L2) 


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L2-L2) 


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2Storage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2Storage.sol#L2-L2) 


```solidity

File: contracts/Bridge/L1/xRenzoBridge.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L2-L2) 


```solidity

File: contracts/Bridge/L1/xRenzoBridgeStorage.sol

2: pragma solidity 0.8.19;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridgeStorage.sol#L2-L2) 


```solidity

File: contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol

2: pragma solidity ^0.8.13;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L2-L2) 


```solidity

File: contracts/Bridge/Connext/libraries/LibConnextStorage.sol

2: pragma solidity ^0.8.0;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/libraries/LibConnextStorage.sol#L2-L2) 


```solidity

File: contracts/Bridge/Connext/libraries/TokenId.sol

2: pragma solidity ^0.8.0;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/libraries/TokenId.sol#L2-L2) 


</details>


### [NC&#x2011;120] Not using the named return variables anywhere in the function is confusing 
Consider changing the variable to be an unnamed one, since the variable is never assigned, nor is it returned by name. If the optimizer is not turned on, leaving the code as it is will also waste gas for the stack variable.


*There are 6 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Oracle/Mantle/METHShim.sol

// @audit roundId
// @audit answer
// @audit startedAt
// @audit updatedAt
// @audit answeredInRound
46:     function latestRoundData()

// @audit roundId
// @audit answer
// @audit startedAt
// @audit updatedAt
// @audit answeredInRound
69:     function _getMETHData()


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L46-L46) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L69-L69)


```solidity

File: contracts/Oracle/Binance/WBETHShim.sol

// @audit roundId
// @audit answer
// @audit startedAt
// @audit updatedAt
// @audit answeredInRound
46:     function latestRoundData()

// @audit roundId
// @audit answer
// @audit startedAt
// @audit updatedAt
// @audit answeredInRound
69:     function _getWBETHData()


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L46-L46) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L69-L69)


```solidity

File: contracts/Delegation/OperatorDelegator.sol

// @audit shares
143:     function deposit(

// @audit shares
162:     function _deposit(IERC20 _token, uint256 _tokenAmount) internal returns (uint256 shares) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L143-L143) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L162-L162)


</details>


### [NC&#x2011;121] Use named return values 
Using named returns makes the code more self-documenting, makes it easier to fill out NatSpec, and in some cases can save gas. The cases below are where there currently is at most one return statement, which is ideal for named returns.


*There are 68 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/token/EzEthToken.sol

77:     function name() public view virtual override returns (string memory) {

85:     function symbol() public view virtual override returns (string memory) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L77-L77) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L85-L85)


```solidity

File: contracts/Withdraw/WithdrawQueue.sol

156:     function getAvailableToWithdraw(address _asset) public view returns (uint256) {

170:     function getBufferDeficit(address _asset) public view returns (uint256) {

270:     function getOutstandingWithdrawRequests(address user) public view returns (uint256) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L156-L156) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L170-L170), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L270-L270)


```solidity

File: contracts/TimelockController.sol

142:     function supportsInterface(
143:         bytes4 interfaceId
144:     ) public view virtual override(IERC165, AccessControl) returns (bool) {

154:     function isOperation(bytes32 id) public view virtual returns (bool) {

161:     function isOperationPending(bytes32 id) public view virtual returns (bool) {

168:     function isOperationReady(bytes32 id) public view virtual returns (bool) {

176:     function isOperationDone(bytes32 id) public view virtual returns (bool) {

184:     function getTimestamp(bytes32 id) public view virtual returns (uint256) {

193:     function getMinDelay() public view virtual returns (uint256) {

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

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L142-L144) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L154-L154), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L161-L161), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L168-L168), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L176-L176), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L184-L184), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L193-L193), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L201-L207), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L215-L221), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L411-L416), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L423-L429), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L436-L442)


```solidity

File: contracts/RestakeManager.sol

126:     function getOperatorDelegatorsLength() external view returns (uint256) {

266:     function getCollateralTokensLength() external view returns (uint256) {

274:     function calculateTVLs() public view returns (uint256[][] memory, uint256[] memory, uint256) {

362:     function chooseOperatorDelegatorForDeposit(
363:         uint256[] memory tvls,
364:         uint256 totalTVL
365:     ) public view returns (IOperatorDelegator) {

400:     function chooseOperatorDelegatorForWithdraw(
401:         uint256 tokenIndex,
402:         uint256 ezETHValue,
403:         uint256[][] memory operatorDelegatorTokenTVLs,
404:         uint256[] memory operatorDelegatorTVLs,
405:         uint256 totalTVL
406:     ) public view returns (IOperatorDelegator) {

451:     function getCollateralTokenIndex(IERC20 _collateralToken) public view returns (uint256) {

675:     function getTotalRewardsEarned() external view returns (uint256) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L126-L126) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L266-L266), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L274-L274), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L362-L365), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L400-L406), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L451-L451), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L675-L675)


```solidity

File: contracts/RateProvider/BalancerRateProvider.sol

29:     function getRate() external view returns (uint256) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RateProvider/BalancerRateProvider.sol#L29-L29) 


```solidity

File: contracts/Permissions/RoleManager.sol

32:     function isRoleManagerAdmin(address potentialAddress) external view returns (bool) {

38:     function isEzETHMinterBurner(address potentialAddress) external view returns (bool) {

44:     function isOperatorDelegatorAdmin(address potentialAddress) external view returns (bool) {

50:     function isOracleAdmin(address potentialAddress) external view returns (bool) {

56:     function isRestakeManagerAdmin(address potentialAddress) external view returns (bool) {

62:     function isTokenAdmin(address potentialAddress) external view returns (bool) {

68:     function isNativeEthRestakeAdmin(address potentialAddress) external view returns (bool) {

74:     function isERC20RewardsAdmin(address potentialAddress) external view returns (bool) {

80:     function isDepositWithdrawPauser(address potentialAddress) external view returns (bool) {

86:     function isBridgeAdmin(address potentialAddress) external view returns (bool) {

92:     function isPriceFeedSender(address potentialAddress) external view returns (bool) {

98:     function isWithdrawQueueAdmin(address potentialAddress) external view returns (bool) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L32-L32) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L38-L38), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L44-L44), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L50-L50), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L56-L56), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L62-L62), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L68-L68), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L74-L74), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L80-L80), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L86-L86), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L92-L92), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L98-L98)


```solidity

File: contracts/Oracle/RenzoOracle.sol

71:     function lookupTokenValue(IERC20 _token, uint256 _balance) public view returns (uint256) {

85:     function lookupTokenAmountFromValue(
86:         IERC20 _token,
87:         uint256 _value
88:     ) external view returns (uint256) {

103:     function lookupTokenValues(
104:         IERC20[] memory _tokens,
105:         uint256[] memory _balances
106:     ) external view returns (uint256) {

123:     function calculateMintAmount(
124:         uint256 _currentValueInProtocol,
125:         uint256 _newValueAdded,
126:         uint256 _existingEzETHSupply
127:     ) external pure returns (uint256) {

152:     function calculateRedeemAmount(
153:         uint256 _ezETHBeingBurned,
154:         uint256 _existingEzETHSupply,
155:         uint256 _currentValueInProtocol
156:     ) external pure returns (uint256) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L71-L71) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L85-L88), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L103-L106), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L123-L127), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L152-L156)


```solidity

File: contracts/Oracle/Mantle/METHShim.sol

29:     function decimals() external pure returns (uint8) {

33:     function description() external pure returns (string memory) {

37:     function version() external pure returns (uint256) {

42:     function getRoundData(uint80) external pure returns (uint80, int256, uint256, uint256, uint80) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L29-L29) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L33-L33), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L37-L37), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Mantle/METHShim.sol#L42-L42)


```solidity

File: contracts/Oracle/Binance/WBETHShim.sol

29:     function decimals() external pure returns (uint8) {

33:     function description() external pure returns (string memory) {

37:     function version() external pure returns (uint256) {

42:     function getRoundData(uint80) external pure returns (uint80, int256, uint256, uint256, uint80) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L29-L29) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L33-L33), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L37-L37), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/Binance/WBETHShim.sol#L42-L42)


```solidity

File: contracts/Delegation/OperatorDelegator.sol

172:     function getStrategyIndex(IStrategy _strategy) public view returns (uint256) {

193:     function queueWithdrawals(
194:         IERC20[] calldata tokens,
195:         uint256[] calldata tokenAmounts
196:     ) external nonReentrant onlyNativeEthRestakeAdmin returns (bytes32) {

327:     function getTokenBalanceFromStrategy(IERC20 token) external view returns (uint256) {

338:     function getStakedETHBalance() external view returns (uint256) {

481:     function _refundGas() internal returns (uint256) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L172-L172) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L193-L196), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L327-L327), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L338-L338), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L481-L481)


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol

48:     function supportsInterface(
49:         bytes4 interfaceId
50:     ) public view override(ERC165Upgradeable) returns (bool) {

56:     function remoteToken() public view override returns (address) {

60:     function bridge() public view override returns (address) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L48-L50) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L56-L56), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L60-L60)


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

168:     function depositETH(
169:         uint256 _minOut,
170:         uint256 _deadline
171:     ) external payable nonReentrant returns (uint256) {

204:     function deposit(
205:         uint256 _amountIn,
206:         uint256 _minOut,
207:         uint256 _deadline
208:     ) external nonReentrant returns (uint256) {

227:     function _deposit(
228:         uint256 _amountIn,
229:         uint256 _minOut,
230:         uint256 _deadline
231:     ) internal returns (uint256) {

277:     function getBridgeFeeShare(uint256 _amountIn) public view returns (uint256) {

289:     function getMintRate() public view returns (uint256, uint256) {

367:     function _trade(uint256 _amountIn, uint256 _deadline) internal returns (uint256) {

456:     function getRate() external view override returns (uint256) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L168-L171) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L204-L208), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L227-L231), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L277-L277), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L289-L289), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L367-L367), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L456-L456)


```solidity

File: contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol

69:     function xReceive(
70:         bytes32 _transferId,
71:         uint256,
72:         address,
73:         address _originSender,
74:         uint32 _origin,
75:         bytes memory _callData
76:     ) external onlySource(_originSender, _origin) whenNotPaused returns (bytes memory) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L69-L76) 


```solidity

File: contracts/Bridge/L2/Oracle/RenzoOracleL2.sol

50:     function getMintRate() public view returns (uint256, uint256) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L50-L50) 


```solidity

File: contracts/Bridge/L1/xRenzoBridge.sol

139:     function xReceive(
140:         bytes32 _transferId,
141:         uint256 _amount,
142:         address _asset,
143:         address _originSender,
144:         uint32 _origin,
145:         bytes memory
146:     ) external nonReentrant returns (bytes memory) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L139-L146) 


</details>


### [NC&#x2011;122] Consider moving duplicated strings to constants 



*There are 4 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/token/EzEthToken.sol

78:         return "Renzo Restaked ETH";

86:         return "ezETH";


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L78-L78) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L86-L86)


```solidity

File: contracts/TimelockController.sol

267:         require(targets.length == values.length, "TimelockController: length mismatch");

377:         require(isOperationReady(id), "TimelockController: operation is not ready");


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L267-L267) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L377-L377)


</details>


### [NC&#x2011;123] Unused `public` contract variable 
If these serve no purpose, they should be safely removed


*There are 2 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/RestakeManagerStorage.sol

//@audit the variable `pendingWithdrawals` is declared but never used
39:     mapping(bytes32 => PendingWithdrawal) public pendingWithdrawals;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManagerStorage.sol#L39-L39) 


```solidity

File: contracts/Delegation/OperatorDelegatorStorage.sol

//@audit the variable `pendingUnstakedDelayedWithdrawalAmount` is declared but never used
48:     uint256 public pendingUnstakedDelayedWithdrawalAmount;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegatorStorage.sol#L48-L48) 


</details>


### [NC&#x2011;124] Missing checks for uint state variable assignments 
Consider whether reasonable bounds checks for variables would be useful


*There are 7 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/TimelockController.sol

117:         _minDelay = minDelay;

405:         _minDelay = newDelay;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L117-L117) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L405-L405)


```solidity

File: contracts/RestakeManager.sol

216:         maxDepositTVL = _maxDepositTVL;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L216-L216) 


```solidity

File: contracts/Deposits/DepositQueue.sol

106:         feeBasisPoints = _feeBasisPoints;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L106-L106) 


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

356:         lastPriceTimestamp = _timestamp;

524:         bridgeFeeShare = _newShare;

535:         sweepBatchSize = _newBatchSize;


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L356-L356) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L524-L524), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L535-L535)


</details>


### [NC&#x2011;125] Consider adding validation of user inputs 



*There are 80 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/token/EzEthToken.sol

//@audit these parameters `to`, are not checked
41:     function mint(address to, uint256 amount) external onlyMinterBurner {

//@audit these parameters `from`, are not checked
46:     function burn(address from, uint256 amount) external onlyMinterBurner {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L41-L41) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L46-L46)


```solidity

File: contracts/Withdraw/WithdrawQueue.sol

//@audit these parameters `user`, are not checked
270:     function getOutstandingWithdrawRequests(address user) public view returns (uint256) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Withdraw/WithdrawQueue.sol#L270-L270) 


```solidity

File: contracts/TimelockController.sol

//@audit these parameters `target`, are not checked
201:     function hashOperation(
202:         address target,
203:         uint256 value,
204:         bytes calldata data,
205:         bytes32 predecessor,
206:         bytes32 salt

//@audit these parameters `targets`, are not checked
215:     function hashOperationBatch(
216:         address[] calldata targets,
217:         uint256[] calldata values,
218:         bytes[] calldata payloads,
219:         bytes32 predecessor,
220:         bytes32 salt

//@audit these parameters `target`, are not checked
234:     function schedule(
235:         address target,
236:         uint256 value,
237:         bytes calldata data,
238:         bytes32 predecessor,
239:         bytes32 salt,
240:         uint256 delay

//@audit these parameters `target`, are not checked
315:     function execute(
316:         address target,
317:         uint256 value,
318:         bytes calldata payload,
319:         bytes32 predecessor,
320:         bytes32 salt

//@audit these parameters `target`, are not checked
368:     function _execute(address target, uint256 value, bytes calldata data) internal virtual {

//@audit these parameters ``,``, are not checked
411:     function onERC721Received(
412:         address,
413:         address,
414:         uint256,
415:         bytes memory

//@audit these parameters ``,``, are not checked
423:     function onERC1155Received(
424:         address,
425:         address,
426:         uint256,
427:         uint256,
428:         bytes memory

//@audit these parameters ``,``, are not checked
436:     function onERC1155BatchReceived(
437:         address,
438:         address,
439:         uint256[] memory,
440:         uint256[] memory,
441:         bytes memory


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L201-L206) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L215-L220), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L234-L240), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L315-L320), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L368-L368), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L411-L415), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L423-L428), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L436-L441)


```solidity

File: contracts/RestakeManager.sol

//@audit these parameters `_roleManager`,`_ezETH`,`_renzoOracle`,`_strategyManager`,`_delegationManager`,`_depositQueue`, are not checked
101:     function initialize(
102:         IRoleManager _roleManager,
103:         IEzEthToken _ezETH,
104:         IRenzoOracle _renzoOracle,
105:         IStrategyManager _strategyManager,
106:         IDelegationManager _delegationManager,
107:         IDepositQueue _depositQueue

//@audit these parameters `_collateralToken`, are not checked
473:     function deposit(IERC20 _collateralToken, uint256 _amount) external {

//@audit these parameters `_token`, are not checked
647:     function depositTokenRewardsFromProtocol(
648:         IERC20 _token,
649:         uint256 _amount

//@audit these parameters `_token`, are not checked
709:     function setTokenTvlLimit(IERC20 _token, uint256 _limit) external onlyRestakeManagerAdmin {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L101-L107) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L473-L473), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L647-L649), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L709-L709)


```solidity

File: contracts/Permissions/RoleManager.sol

//@audit these parameters `potentialAddress`, are not checked
32:     function isRoleManagerAdmin(address potentialAddress) external view returns (bool) {

//@audit these parameters `potentialAddress`, are not checked
38:     function isEzETHMinterBurner(address potentialAddress) external view returns (bool) {

//@audit these parameters `potentialAddress`, are not checked
44:     function isOperatorDelegatorAdmin(address potentialAddress) external view returns (bool) {

//@audit these parameters `potentialAddress`, are not checked
50:     function isOracleAdmin(address potentialAddress) external view returns (bool) {

//@audit these parameters `potentialAddress`, are not checked
56:     function isRestakeManagerAdmin(address potentialAddress) external view returns (bool) {

//@audit these parameters `potentialAddress`, are not checked
62:     function isTokenAdmin(address potentialAddress) external view returns (bool) {

//@audit these parameters `potentialAddress`, are not checked
68:     function isNativeEthRestakeAdmin(address potentialAddress) external view returns (bool) {

//@audit these parameters `potentialAddress`, are not checked
74:     function isERC20RewardsAdmin(address potentialAddress) external view returns (bool) {

//@audit these parameters `potentialAddress`, are not checked
80:     function isDepositWithdrawPauser(address potentialAddress) external view returns (bool) {

//@audit these parameters `potentialAddress`, are not checked
86:     function isBridgeAdmin(address potentialAddress) external view returns (bool) {

//@audit these parameters `potentialAddress`, are not checked
92:     function isPriceFeedSender(address potentialAddress) external view returns (bool) {

//@audit these parameters `potentialAddress`, are not checked
98:     function isWithdrawQueueAdmin(address potentialAddress) external view returns (bool) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L32-L32) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L38-L38), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L44-L44), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L50-L50), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L56-L56), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L62-L62), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L68-L68), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L74-L74), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L80-L80), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L86-L86), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L92-L92), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L98-L98)


```solidity

File: contracts/Oracle/RenzoOracle.sol

//@audit these parameters `_token`, are not checked
71:     function lookupTokenValue(IERC20 _token, uint256 _balance) public view returns (uint256) {

//@audit these parameters `_token`, are not checked
85:     function lookupTokenAmountFromValue(
86:         IERC20 _token,
87:         uint256 _value


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L71-L71) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L85-L87)


```solidity

File: contracts/Deposits/DepositQueue.sol

//@audit these parameters `operatorDelegator`, are not checked
187:     function stakeEthFromQueue(
188:         IOperatorDelegator operatorDelegator,
189:         bytes calldata pubkey,
190:         bytes calldata signature,
191:         bytes32 depositDataRoot


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Deposits/DepositQueue.sol#L187-L191) 


```solidity

File: contracts/Delegation/OperatorDelegator.sol

//@audit these parameters `_strategy`, are not checked
106:     function setTokenStrategy(
107:         IERC20 _token,
108:         IStrategy _strategy

//@audit these parameters `_token`, are not checked
162:     function _deposit(IERC20 _token, uint256 _tokenAmount) internal returns (uint256 shares) {

//@audit these parameters `recipient`, are not checked
432:     function withdrawNonBeaconChainETHBalanceWei(
433:         address recipient,
434:         uint256 amountToWithdraw

//@audit these parameters `tokenList`,`recipient`, are not checked
446:     function recoverTokens(
447:         IERC20[] memory tokenList,
448:         uint256[] memory amountsToWithdraw,
449:         address recipient


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L106-L108) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L162-L162), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L432-L434), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L446-L449)


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20.sol

//@audit these parameters `_factory`, are not checked
61:     function initialize(
62:         string memory _name,
63:         string memory _symbol,
64:         address _factory

//@audit these parameters `_factory`, are not checked
76:     function __XERC20_init(
77:         string memory _name,
78:         string memory _symbol,
79:         address _factory

//@audit these parameters `_user`, are not checked
96:     function mint(address _user, uint256 _amount) public virtual {

//@audit these parameters `_lockbox`, are not checked
121:     function setLockbox(address _lockbox) public {

//@audit these parameters `_bridge`, are not checked
135:     function setLimits(
136:         address _bridge,
137:         uint256 _mintingLimit,
138:         uint256 _burningLimit

//@audit these parameters `_bridge`, are not checked
152:     function mintingMaxLimitOf(address _bridge) public view returns (uint256 _limit) {

//@audit these parameters `_bridge`, are not checked
163:     function burningMaxLimitOf(address _bridge) public view returns (uint256 _limit) {

//@audit these parameters `_bridge`, are not checked
174:     function mintingCurrentLimitOf(address _bridge) public view returns (uint256 _limit) {

//@audit these parameters `_bridge`, are not checked
190:     function burningCurrentLimitOf(address _bridge) public view returns (uint256 _limit) {

//@audit these parameters `_bridge`, are not checked
205:     function _useMinterLimits(address _bridge, uint256 _change) internal {

//@audit these parameters `_bridge`, are not checked
217:     function _useBurnerLimits(address _bridge, uint256 _change) internal {

//@audit these parameters `_bridge`, are not checked
230:     function _changeMinterLimit(address _bridge, uint256 _limit) internal {

//@audit these parameters `_bridge`, are not checked
252:     function _changeBurnerLimit(address _bridge, uint256 _limit) internal {

//@audit these parameters `_user`, are not checked
328:     function _burnWithCaller(address _caller, address _user, uint256 _amount) internal {

//@audit these parameters `_user`, are not checked
348:     function _mintWithCaller(address _caller, address _user, uint256 _amount) internal {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L61-L64) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L76-L79), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L96-L96), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L121-L121), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L135-L138), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L152-L152), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L163-L163), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L174-L174), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L190-L190), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L205-L205), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L217-L217), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L230-L230), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L252-L252), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L328-L328), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L348-L348)


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Factory.sol

//@audit these parameters `_lockboxImplementation`,`_xerc20Implementation`, are not checked
54:     function initialize(
55:         address _lockboxImplementation,
56:         address _xerc20Implementation

//@audit these parameters `_bridges`,`_proxyAdmin`, are not checked
74:     function deployXERC20(
75:         string memory _name,
76:         string memory _symbol,
77:         uint256[] memory _minterLimits,
78:         uint256[] memory _burnerLimits,
79:         address[] memory _bridges,
80:         address _proxyAdmin

//@audit these parameters `_proxyAdmin`, are not checked
105:     function deployLockbox(
106:         address _xerc20,
107:         address _baseToken,
108:         bool _isNative,
109:         address _proxyAdmin

//@audit these parameters `_bridges`,`_proxyAdmin`, are not checked
135:     function _deployXERC20(
136:         string memory _name,
137:         string memory _symbol,
138:         uint256[] memory _minterLimits,
139:         uint256[] memory _burnerLimits,
140:         address[] memory _bridges,
141:         address _proxyAdmin

//@audit these parameters `_xerc20`,`_baseToken`,`_proxyAdmin`, are not checked
184:     function _deployLockbox(
185:         address _xerc20,
186:         address _baseToken,
187:         bool _isNative,
188:         address _proxyAdmin


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L54-L56) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L74-L80), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L105-L109), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L135-L141), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L184-L188)


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol

//@audit these parameters `_factory`,`_l1Token`,`_optimismBridge`, are not checked
35:     function initialize(
36:         string memory _name,
37:         string memory _symbol,
38:         address _factory,
39:         address _l1Token,
40:         address _optimismBridge

//@audit these parameters `_to`, are not checked
64:     function mint(address _to, uint256 _amount) public override(XERC20, IOptimismMintableERC20) {

//@audit these parameters `_from`, are not checked
68:     function burn(address _from, uint256 _amount) public override(XERC20, IOptimismMintableERC20) {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L35-L40) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L64-L64), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L68-L68)


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol

//@audit these parameters `_bridges`,`_proxyAdmin`,`_l1Token`, are not checked
37:     function deployOptimismMintableXERC20(
38:         string memory _name,
39:         string memory _symbol,
40:         uint256[] memory _minterLimits,
41:         uint256[] memory _burnerLimits,
42:         address[] memory _bridges,
43:         address _proxyAdmin,
44:         address _l1Token

//@audit these parameters `_bridges`,`_proxyAdmin`,`_l1Token`, are not checked
73:     function _deployOptimismMintableXERC20(
74:         string memory _name,
75:         string memory _symbol,
76:         uint256[] memory _minterLimits,
77:         uint256[] memory _burnerLimits,
78:         address[] memory _bridges,
79:         address _proxyAdmin,
80:         address _l1Token


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L37-L44) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L73-L80)


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

//@audit these parameters `_receiver`,`_oracle`, are not checked
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

//@audit these parameters `_sweeper`, are not checked
466:     function setAllowedBridgeSweeper(address _sweeper, bool _allowed) external onlyOwner {

//@audit these parameters `_to`, are not checked
478:     function recoverNative(uint256 _amount, address _to) external onlyOwner {

//@audit these parameters `_token`,`_to`, are not checked
489:     function recoverERC20(address _token, uint256 _amount, address _to) external onlyOwner {

//@audit these parameters `_oracle`, are not checked
501:     function setOraclePriceFeed(IRenzoOracleL2 _oracle) external onlyOwner {

//@audit these parameters `_receiver`, are not checked
511:     function setReceiverPriceFeed(address _receiver) external onlyOwner {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L75-L85) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L466-L466), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L478-L478), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L489-L489), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L501-L501), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L511-L511)


```solidity

File: contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol

//@audit these parameters ``,`_originSender`, are not checked
69:     function xReceive(
70:         bytes32 _transferId,
71:         uint256,
72:         address,
73:         address _originSender,
74:         uint32 _origin,
75:         bytes memory _callData


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/PriceFeed/ConnextReceiver.sol#L69-L75) 


```solidity

File: contracts/Bridge/L1/xRenzoBridge.sol

//@audit these parameters `_originSender`, are not checked
139:     function xReceive(
140:         bytes32 _transferId,
141:         uint256 _amount,
142:         address _asset,
143:         address _originSender,
144:         uint32 _origin,
145:         bytes memory

//@audit these parameters `_to`, are not checked
294:     function recoverNative(uint256 _amount, address _to) external onlyBridgeAdmin {

//@audit these parameters `_token`,`_to`, are not checked
305:     function recoverERC20(address _token, uint256 _amount, address _to) external onlyBridgeAdmin {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L139-L145) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L294-L294), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L1/xRenzoBridge.sol#L305-L305)


```solidity

File: contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol

//@audit these parameters `erc20`, are not checked
10:     function getXERC20(address erc20) external view returns (address xerc20);

//@audit these parameters `xerc20`, are not checked
12:     function getERC20(address xerc20) external view returns (address erc20);

//@audit these parameters `erc20`, are not checked
14:     function getLockbox(address erc20) external view returns (address xerc20);

//@audit these parameters `_localToken`,`_remoteToken`,`_to`, are not checked
18:     function bridgeERC20To(
19:         address _localToken,
20:         address _remoteToken,
21:         address _to,
22:         uint256 _amount,
23:         uint32 _minGasLimit,
24:         bytes calldata _extraData

//@audit these parameters `_to`,`_erc20`, are not checked
56:     function bridgeTo(
57:         address _to,
58:         address _erc20,
59:         address _remoteToken,
60:         uint256 _amount,
61:         uint32 _minGasLimit,
62:         bytes calldata _extraData


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L10-L10) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L12-L12), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L14-L14), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L18-L24), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/Connext/integration/LockboxAdapterBlast.sol#L56-L62)


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol

//@audit these parameters `_xerc20`,`_erc20`, are not checked
44:     function initialize(address _xerc20, address _erc20, bool _isNative) public initializer {

//@audit these parameters `_to`, are not checked
79:     function depositTo(address _to, uint256 _amount) external {

//@audit these parameters `_to`, are not checked
91:     function depositNativeTo(address _to) public payable {

//@audit these parameters `_to`, are not checked
114:     function withdrawTo(address _to, uint256 _amount) external {

//@audit these parameters `_to`, are not checked
125:     function _withdraw(address _to, uint256 _amount) internal {

//@audit these parameters `_to`, are not checked
145:     function _deposit(address _to, uint256 _amount) internal {


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L44-L44) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L79-L79), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L91-L91), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L114-L114), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L125-L125), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L145-L145)


</details>


### [NC&#x2011;126] Consider disallowing transfers to `address(this)` 
Consider preventing a contract's tokens from being transferred/minted to the contract itself


*There are 3 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/token/EzEthToken.sol

41:     function mint(address to, uint256 amount) external onlyMinterBurner {
42:         _mint(to, amount);
43:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L41-L43) 


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20.sol

96:     function mint(address _user, uint256 _amount) public virtual {
97:         _mintWithCaller(msg.sender, _user, _amount);
98:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L96-L98) 


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol

64:     function mint(address _to, uint256 _amount) public override(XERC20, IOptimismMintableERC20) {
65:         XERC20.mint(_to, _amount);
66:     }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L64-L66) 


</details>


### [NC&#x2011;127] Unusual loop variable 
For better readability, try to use common loop counter names


*There are 2 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/Bridge/xERC20/contracts/XERC20Factory.sol

//@audit `_i` 
167:         for (uint256 _i; _i < _bridgesLength; ++_i) {
168:             XERC20(_xerc20).setLimits(_bridges[_i], _minterLimits[_i], _burnerLimits[_i]);
169:         }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L167-L169) 


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol

//@audit `_i` 
109:         for (uint256 _i; _i < _bridgesLength; ++_i) {
110:             OptimismMintableXERC20(_xerc20).setLimits(
111:                 _bridges[_i],
112:                 _minterLimits[_i],
113:                 _burnerLimits[_i]
114:             );
115:         }


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L109-L115) 


</details>


### [NC&#x2011;128] Consider using named function calls 
Named function calls in Solidity greatly improve code readability by explicitly mapping arguments to their respective parameter names. This clarity becomes critical when dealing with functions that have numerous or complex parameters, reducing potential errors due to misordered arguments. Therefore, adopting named function calls contributes to more maintainable and less error-prone code.


*There are 73 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/token/EzEthToken.sol

36:         __ERC20_init("ezETH", "Renzo Restaked ETH");

42:         _mint(to, amount);

47:         _burn(from, amount);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L36-L36) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L42-L42), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/token/EzEthToken.sol#L47-L47)


```solidity

File: contracts/TimelockController.sol

93:         _setRoleAdmin(TIMELOCK_ADMIN_ROLE, TIMELOCK_ADMIN_ROLE);

94:         _setRoleAdmin(PROPOSER_ROLE, TIMELOCK_ADMIN_ROLE);

95:         _setRoleAdmin(EXECUTOR_ROLE, TIMELOCK_ADMIN_ROLE);

96:         _setRoleAdmin(CANCELLER_ROLE, TIMELOCK_ADMIN_ROLE);

99:         _setupRole(TIMELOCK_ADMIN_ROLE, address(this));

242:         bytes32 id = hashOperation(target, value, data, predecessor, salt);

243:         _schedule(id, delay);

270:         bytes32 id = hashOperationBatch(targets, values, payloads, predecessor, salt);

271:         _schedule(id, delay);

322:         bytes32 id = hashOperation(target, value, payload, predecessor, salt);

324:         _beforeCall(id, predecessor);

325:         _execute(target, value, payload);

352:         bytes32 id = hashOperationBatch(targets, values, payloads, predecessor, salt);

354:         _beforeCall(id, predecessor);

128:         if (!hasRole(role, address(0))) {

103:             _setupRole(TIMELOCK_ADMIN_ROLE, admin);

108:             _setupRole(PROPOSER_ROLE, proposers[i]);

109:             _setupRole(CANCELLER_ROLE, proposers[i]);

114:             _setupRole(EXECUTOR_ROLE, executors[i]);

129:             _checkRole(role, _msgSender());

359:             _execute(target, value, payload);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L93-L93) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L94-L94), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L95-L95), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L96-L96), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L99-L99), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L242-L242), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L243-L243), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L270-L270), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L271-L271), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L322-L322), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L324-L324), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L325-L325), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L352-L352), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L354-L354), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L128-L128), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L103-L103), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L108-L108), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L109-L109), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L114-L114), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L129-L129), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/TimelockController.sol#L359-L359)


```solidity

File: contracts/RestakeManager.sol

474:         deposit(_collateralToken, _amount, 0);

534:         IOperatorDelegator operatorDelegator = chooseOperatorDelegatorForDeposit(
535:             operatorDelegatorTVLs,
536:             totalTVL
537:         );

655:         IOperatorDelegator operatorDelegator = chooseOperatorDelegatorForDeposit(
656:             operatorDelegatorTVLs,
657:             totalTVL
658:         );


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L474-L474) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L534-L537), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/RestakeManager.sol#L655-L658)


```solidity

File: contracts/Permissions/RoleManager.sol

27:         _grantRole(DEFAULT_ADMIN_ROLE, roleManagerAdmin);

33:         return hasRole(DEFAULT_ADMIN_ROLE, potentialAddress);

39:         return hasRole(RX_ETH_MINTER_BURNER, potentialAddress);

45:         return hasRole(OPERATOR_DELEGATOR_ADMIN, potentialAddress);

51:         return hasRole(ORACLE_ADMIN, potentialAddress);

57:         return hasRole(RESTAKE_MANAGER_ADMIN, potentialAddress);

63:         return hasRole(TOKEN_ADMIN, potentialAddress);

69:         return hasRole(NATIVE_ETH_RESTAKE_ADMIN, potentialAddress);

75:         return hasRole(ERC20_REWARD_ADMIN, potentialAddress);

81:         return hasRole(DEPOSIT_WITHDRAW_PAUSER, potentialAddress);

87:         return hasRole(BRIDGE_ADMIN, potentialAddress);

93:         return hasRole(PRICE_FEED_SENDER, potentialAddress);

99:         return hasRole(WITHDRAW_QUEUE_ADMIN, potentialAddress);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L27-L27) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L33-L33), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L39-L39), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L45-L45), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L51-L51), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L57-L57), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L63-L63), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L69-L69), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L75-L75), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L81-L81), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L87-L87), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L93-L93), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Permissions/RoleManager.sol#L99-L99)


```solidity

File: contracts/Oracle/RenzoOracle.sol

112:             totalValue += lookupTokenValue(_tokens[i], _balances[i]);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Oracle/RenzoOracle.sol#L112-L112) 


```solidity

File: contracts/Delegation/OperatorDelegator.sol

153:         return _deposit(token, tokenAmount);

308:                     _deposit(tokens[i], balanceOfToken);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L153-L153) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Delegation/OperatorDelegator.sol#L308-L308)


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20.sol

66:         __XERC20_init(_name, _symbol, _factory);

81:         __ERC20_init(_name, _symbol);

97:         _mintWithCaller(msg.sender, _user, _amount);

112:         _burnWithCaller(msg.sender, _user, _amount);

140:         _changeMinterLimit(_bridge, _mintingLimit);

141:         _changeBurnerLimit(_bridge, _burningLimit);

337:         _burn(_user, _amount);

357:         _mint(_user, _amount);

175:         _limit = _getCurrentLimit(
176:             bridges[_bridge].minterParams.currentLimit,
177:             bridges[_bridge].minterParams.maxLimit,
178:             bridges[_bridge].minterParams.timestamp,
179:             bridges[_bridge].minterParams.ratePerSecond
180:         );

191:         _limit = _getCurrentLimit(
192:             bridges[_bridge].burnerParams.currentLimit,
193:             bridges[_bridge].burnerParams.maxLimit,
194:             bridges[_bridge].burnerParams.timestamp,
195:             bridges[_bridge].burnerParams.ratePerSecond
196:         );

235:         bridges[_bridge].minterParams.currentLimit = _calculateNewCurrentLimit(
236:             _limit,
237:             _oldLimit,
238:             _currentLimit
239:         );

257:         bridges[_bridge].burnerParams.currentLimit = _calculateNewCurrentLimit(
258:             _limit,
259:             _oldLimit,
260:             _currentLimit
261:         );

109:             _spendAllowance(_user, msg.sender, _amount);

335:             _useBurnerLimits(_caller, _amount);

355:             _useMinterLimits(_caller, _amount);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L66-L66) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L81-L81), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L97-L97), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L112-L112), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L140-L140), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L141-L141), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L337-L337), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L357-L357), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L175-L180), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L191-L196), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L235-L239), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L257-L261), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L109-L109), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L335-L335), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20.sol#L355-L355)


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Factory.sol

82:         _xerc20 = _deployXERC20(
83:             _name,
84:             _symbol,
85:             _minterLimits,
86:             _burnerLimits,
87:             _bridges,
88:             _proxyAdmin
89:         );

118:         _lockbox = _deployLockbox(_xerc20, _baseToken, _isNative, _proxyAdmin);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L82-L89) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Factory.sol#L118-L118)


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol

43:         __XERC20_init(_name, _symbol, _factory);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20.sol#L43-L43) 


```solidity

File: contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol

46:         _xerc20 = _deployOptimismMintableXERC20(
47:             _name,
48:             _symbol,
49:             _minterLimits,
50:             _burnerLimits,
51:             _bridges,
52:             _proxyAdmin,
53:             _l1Token
54:         );


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/optimism/OptimismMintableXERC20Factory.sol#L46-L54) 


```solidity

File: contracts/Bridge/L2/xRenzoDeposit.sol

190:         return _deposit(wrappedAmount, _minOut, _deadline);

216:         return _deposit(_amountIn, _minOut, _deadline);

239:         uint256 amountOut = _trade(_amountIn, _deadline);

312:         _updatePrice(_price, _timestamp);

321:         return _updatePrice(price, block.timestamp);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L190-L190) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L216-L216), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L239-L239), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L312-L312), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/L2/xRenzoDeposit.sol#L321-L321)


```solidity

File: contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol

57:         _deposit(msg.sender, msg.value);

69:         _deposit(msg.sender, _amount);

82:         _deposit(_to, _amount);

94:         _deposit(_to, msg.value);

104:         _withdraw(msg.sender, _amount);

115:         _withdraw(_to, _amount);


```

[link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L57-L57) , [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L69-L69), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L82-L82), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L94-L94), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L104-L104), [link](https://github.com/code-423n4/2024-04-renzo/blob/main//contracts/Bridge/xERC20/contracts/XERC20Lockbox.sol#L115-L115)


</details>
