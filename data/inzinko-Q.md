## L1- Lack Of Check Of an Operator Delegator Having Tokens and part of the TotalTVL Before  Removal

When `onlyRestakeManagerAdmin` Is About to Remove Operator Delegators from the List, their is no check to verify that the OD that is about to be removed has tokens being staked in motion or tokens Meant For Gas Refunds inside that might be currently contributing to the Total TVL.

```solidity
function removeOperatorDelegator(
        IOperatorDelegator _operatorDelegatorToRemove
    ) external onlyRestakeManagerAdmin {
        // Remove it from the list
        uint256 odLength = operatorDelegators.length;
        for (uint256 i = 0; i < odLength; ) {
            if (address(operatorDelegators[i]) == address(_operatorDelegatorToRemove)) {
                // Clear the allocation
                operatorDelegatorAllocations[_operatorDelegatorToRemove] = 0;
...more code
```

 A check that will assert that the OD that is about to be removed does not have tokens/collaterals, that backs users ezETH mints.

##### Mitigation
A Simple Check by using the index of the Operator Delegator Should be used to access the token Tvls of the OD from an already existing system as shown below

```solidity
        // Get the TVLs for each operator delegator and the total TVL
        (uint256[][] memory operatorDelegatorTokenTVLs,,) = calculateTVLs();

```
By Utilizing the Index of the the Operator And running a Loop of every collateral token including Native ETH, the protocol can know exactly if they are still tokens in use, to prevent scenarios Described Earlier

## L2- Lack Of Check of New MaxDepositTVL can lead to Temporary DOS

When Passing in a new parameter for the changing of the maxDepositTVL, to a new value, a check has to be implemented to make sure that the new value is not lesser than the Total TVL that is currently in the protocol, 
```solidity

    /// 
    function setMaxDepositTVL(uint256 _maxDepositTVL) external onlyRestakeManagerAdmin {
        maxDepositTVL = _maxDepositTVL;
    }
```

But that check is not actually implemented, which will lead to a situation where during a call to `deposit` and `depositETH` they will be a revert happening as shown below 

```solidity
 function depositETH(uint256 _referralId) public payable nonReentrant notPaused {
        // Get the total TVL
        (, , uint256 totalTVL) = calculateTVLs();
        // Enforce TVL limit if set
        if (maxDepositTVL != 0 && totalTVL + msg.value > maxDepositTVL) {
            revert MaxTVLReached();
        }
...more code
```
Here If the new maxDeposit TVL is lower than the totalTVL, then this will lead to reverts until the value is changed again, in other words a temporary DOS will occur

This is the Same as the `deposit` function. A check like that if the maxDepositTvl will always result in a DOS if the value is already less than or equal to the totalTVL, not considering the new value that is to be added during deposits 

##### Mitigation
```solidity
        // Get the TVLs for each operator delegator and the total TVL
        (,,totalTVL) = calculateTVLs();

        if ( totalTVL > _maxDepositTVL ) {
       revert InvalidValue()
}

```

## L3- `setPaused` is Called By a wrong admin diffrent from the natspec

In the natspec of the `setPaused` function of the `RestakeManager`, the natspec of the function says it can only be called by the restake manager admin but in the implementation, it can actually be only called by onlyDepositWithdrawPauserAdmin as shown in the function below + the natspec

```solidity
 /// @dev Allows a restake manager admin to set the paused state of the contract
    function setPaused(bool _paused) external onlyDepositWithdrawPauserAdmin {
        paused = _paused;
        //@audit Natspec Says Restake manger should be the accessor but the Modifier Says Different things
    }
```
Both admin Roles Are different, and shown below in their own modifiers 

```solidity
 /// @dev Allows only a whitelisted address to configure the contract
    modifier onlyRestakeManagerAdmin() {
        if (!roleManager.isRestakeManagerAdmin(msg.sender)) revert NotRestakeManagerAdmin();
        _;
    }

    /// @dev Allows only a whitelisted address to set pause state
    modifier onlyDepositWithdrawPauserAdmin() {
        if (!roleManager.isDepositWithdrawPauser(msg.sender)) revert NotDepositWithdrawPauser();
        _;
    }
```

## L4- Lack of Check to verify that a removed collateral token is being used actively in the  protocol

When tokens are being removed from the list of Collateral token with the `removeCollateralToken` function, a check that try to assert that the token that is being removed is not actively being used as collateral for users minted ezETH, which could lead to a situation where ezETH is not fully backed fully as when tokens are removed they are not used to calculate totalTVL anymore, so any token in the system in ignored. The affected code is shown below 

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
```
A check should be placed right before the token is removed to loop to find and make sure that the token is not being used anywhere in the protocol