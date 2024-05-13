 # [L-01] - EzETHToken initialized with wrong name and symbol 

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/token/EzEthToken.sol#L36

```solidity
    function initialize(IRoleManager _roleManager) public initializer {
        if (address(_roleManager) == address(0x0)) revert InvalidZeroInput();

        __ERC20_init("ezETH", "Renzo Restaked ETH"); //@audit: name and symbol are mixed up. token is intitalized wrongly. symbol is used as name and name is used as symbol 
        roleManager = _roleManager;
    }
```

the `__ERC20_init()` function has the `name` and `symbol` parameters as seen [here](https://github.com/OpenZeppelin/openzeppelin-contracts-upgradeable/blob/683b6729cd061ceecf0ebdc29b00a01930fcc8e7/contracts/token/ERC20/ERC20Upgradeable.sol#L58). but in the code, ` ezETH` which is the token symbol is placed as input for parameter `name_` and `Renzo Restaked ETH` which is token name is used as input for the parameter `symbol_`. 


## Recommended Mitigation
use `Renzo Restaked ETH` ezETH as input for parameter `name_` and use `ezETH` as input for parameter `symbol_` 


# [L-02] - Can enforce eth direct transfer to be from only WETH contract and revert for users. 

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L134C1-L137C80

```solidity
     * @notice  WARNING: This function does NOT whitelist who can send funds from the L2 via Connext.  Users should NOT
     *          send funds directly to this contract.  A user who sends funds directly to this contract will cause
     *          the tokens on the L2 to become over collateralized and will be a "donation" to protocol.  Only use
     *          the deposit contracts on the L2 to send funds to this contract.
    function xReceive(
```

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L309C1-L313C34
```solidity
    /**
     * @notice Fallback function to handle ETH sent to the contract from unwrapping WETH
     * @dev Warning: users should not send ETH directly to this contract!
     */
    receive() external payable {}
```

The warnings above says that "users should not send ETH directly to this contract!" else the eth sent will become a "donation" to the protocol and the fallback should only be used for unwrapping WETH. But still to prevent/totally eliminate user error, mistakes etc a strict check can be put in the fallback logic to reject eth transfers made by addresses that are not the registered WETH contract. Something like the logic below should do. 

```solidity
    receive() external payable {
        //@audit: to enforce the warning you can do something like
        if (msg.sender != address(wETH)) revert();
    }
```

This will eliminate all posibilities of users making any erroreous use of the contract and "donating" to the protocol like the warnings above specifies. 

## Recommended Mitigation
modify the fallback to be like below
```solidity
    receive() external payable {
        //@audit: to enforce the warning you can do something like
        if (msg.sender != address(wETH)) revert();
    }
```


# [L-03] -  xRenzoBridge ConnextMessageSent events are not distinct, they have no distinct identifier

messages sent via connext's xcall() function all have a `transferID` value which is returned on sucessful execution of a cross chain message send request. This `transferID` is unique for every message sent via connext. The xRenzoBridge event `ConnextMessageSent` is emitted on every sucessful message request via connext but it's parameters are not unique enough. 

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L275C1-L280C15

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L1/xRenzoBridge.sol#L43C1-L48C7
```solidity
    event ConnextMessageSent(
        uint32 indexed destinationChainDomain, // The chain domain Id of the destination chain.
        address receiver, // The address of the receiver on the destination chain.
        uint256 exchangeRate, // The exchange rate sent.
        uint256 fees // The fees paid for sending the Connext message.
    );
```

destinationChainDomain, receiver, exchangeRate, fees can be the same for two events. i.e if two transactions are made at the same time, bot events can have same value for timestamp,  destinationChainDomain, receiver, exchangeRate and fees. 

It is better to inclued the `transferID` value which is returned by the [xcall()](https://github.com/connext/monorepo/blob/8338d6506c609f9383d81133c3cb40cfb9e44392/packages/deployments/contracts/contracts/core/connext/facets/BridgeFacet.sol#L299C1-L307C59) fcn in the event parameters as well. This will make each event unique to each connext message and allow for easier identification/relationship between each message and their `ConnextMessageSent` events. For example, say relayer fee for the message is not enough for execution on L2, the `transfer ID` is used to to increase/bump up the fee paid as seen here --> https://docs.connext.network/developers/guides/estimating-fees#bumping-relayer-fees 
Ignoring the `transferID` value makes it harder to track the failing message and troubleshoot any issues or add more relayer fees as in this case. 

I also noticed that `xRenzoDeposit.sweep()` fcn has same issue, it does a connext xcall and doesnt save or emit the transferID too. see [here](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L434)

## Recommended Mitigation
modify the `ConnextMessageSent` event to be like below

```solidity
    event ConnextMessageSent(
   bytes32 transferID //id of the connext cross chain message. 
        uint32 indexed destinationChainDomain, // The chain domain Id of the destination chain.
        address receiver, // The address of the receiver on the destination chain.
        uint256 exchangeRate, // The exchange rate sent.
        uint256 fees // The fees paid for sending the Connext message.
    );
```

# [L-04] -  OperatorDelegator.setTokenStrategy()  should check that each strategy address being set is whitelisted for deposit in eigenlayer strategy manager

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L106C1-L115C1
```solidity
    /// @dev Sets the strategy for a given token - setting strategy to 0x0 removes the ability to deposit and withdraw token
    function setTokenStrategy(
        IERC20 _token,
        IStrategy _strategy
    ) external nonReentrant onlyOperatorDelegatorAdmin {
        if (address(_token) == address(0x0)) revert InvalidZeroInput();

        tokenStrategyMapping[_token] = _strategy; `strategyIsWhitelistedForDeposit` mapping first.
        emit TokenStrategyUpdated(_token, _strategy);
    }
```
`setTokenStrategy()` updateds the `tokenStrategyMapping` for each token to a strategy but it doesnt confirm that the strategy is whitelisted for deposits by the eigenlayer strategy manager. In cases where an unwhitelisted strategy is updated into storage the `deposit()` function will fail because             [strategyManager.depositIntoStrategy(tokenStrategyMapping[_token], _token, _tokenAmount)](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Delegation/OperatorDelegator.sol#L168) will not recognise the strategy address as it is not whitelisted for deposit. 

`setTokenStrategy()` should confirm if a strategy is whitelisted for deposit by calling the eigenlayer public mapping [strategyIsWhitelistedForDeposit](https://github.com/Layr-Labs/eigenlayer-contracts/blob/ef2ea4a7459884f381057aa9bbcd29c7148cfb63/src/contracts/core/StrategyManagerStorage.sol#L60) and checking that it indeed returns true. 

## Recommended Mitigation
modify the `setTokenStrategy()`fcn to be like below

```solidity
    function setTokenStrategy(
        IERC20 _token,
        IStrategy _strategy
    ) external nonReentrant onlyOperatorDelegatorAdmin {
        if (address(_token) == address(0x0)) revert InvalidZeroInput();
        if(strategyManager.strategyIsWhitelistedForDeposit(_strategy) != true) revert stategyNotWhitelisted()

        tokenStrategyMapping[_token] = _strategy; //@audit this mapping can be updated with a straategy that is not whitelisted for deposit in eigenlayer. it should check if the straegy is whitelisted by calling `strategyIsWhitelistedForDeposit` mapping first.
        emit TokenStrategyUpdated(_token, _strategy);
    }
```


# [L-05] - using tx.gasprice in gas refunds calc can open protocol up to the possibily of rogue admin accounts stealing ether

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L283C1-L290C1
```solidity
    function _refundGas(uint256 initialGas) internal {
        uint256 gasUsed = (initialGas - gasleft()) * tx.gasprice;
        uint256 gasRefund = address(this).balance >= gasUsed ? gasUsed : address(this).balance;
        (bool success, ) = payable(msg.sender).call{ value: gasRefund }("");
        if (!success) revert TransferFailed();
        emit GasRefunded(msg.sender, gasRefund);
    }
```

post EIP1559, tx.gasprice is calculated as the block base fee plus the sender's priority fee. a malicious caller can use a high priority fee to inflate the value of tx.gasprice and manipulate the gas refunds calculations. This will cause the amount to be refunded to be higher and it will be deducted from the ether balance of the contract. 

in depositQueue.sol, `_refundGas()` is used by admin functions [stakeEthFromQueue()](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L205) and [stakeEthFromQueueMulti()](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Deposits/DepositQueue.sol#L249). Although these functions are admin functions and access is restricted. It is important to note this vuln as it could possibly cause loss of user funds in rare scenario case when admin address is compromisd. 

## Recommended Mitigation 
use oracles to fetch gas price or cap the priority fee 



# [L-06] - External calls in an un-bounded for-loop which calls chainlink oracle price feed may result to OOG if array length is too long

note: i add this because this specific function is not convered in the 4naly3er report. 

https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L103C1-L119C6
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

there is an unbounded loop here which will go on for as many iterations as the token array length. the external call to the chainlink api is in the [lookupTokenValue()](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Oracle/RenzoOracle.sol#L75) call. If array is too long this will revert with OOG. 

## Recommended Mitigation 
Consider limiting the max length of the parameter arrays supplied to the function. 


# [L-07] - different conditions for price answer expiry in RenzoOracleL2 and xRenzoDeposit can cause confusion


[RenzoOracleL2.getMintRate()](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L50) is used by xRenzoDeposit.getMintRate to get the ezETH price at the time of deposit. it checks that the price is not yet stale by comparing the  chainlink answer time with its hardcoded [MAX_TIME_WINDOW](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/Oracle/RenzoOracleL2.sol#L13) which is `86400 + 60`  or  `24 hrs + 60 secs`. 

In xRenzoDeposit.deposit() which also uses RenzoOracleL2.getMintRate() in its [xRenzoDeposit.getMintRate()](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L289) logic, it then [compares the result returned by xRenzoDeposit.getMintRate() with `1 days`](https://github.com/code-423n4/2024-04-renzo/blob/519e518f2d8dec9acf6482b84a181e403070d22d/contracts/Bridge/L2/xRenzoDeposit.sol#L248). `1 days` and `86400 + 60` are not the same and this difference can cause issues for external intgrators which may begin to send in deposits earlier than they should, simply because they believed the staleness check in xRenzoDeposit.getMintRate() and RenzoOracleL2.getMintRate() to be accurate. 

for example, user calls xRenzoDeposit.getMintRate() and gets back data which is checked to be fresh (not stale) by the xRenzoDeposit.getMintRate() logic. User thinks data is okay because there was no reverts and then proceeds to call xRenzoDeposit.deposit(). xRenzoDeposit.deposit() then reverts because its timestamp comparison with `1 days` fails while xRenzoDeposit.getMintRate() is a success because the returned chainlink timestamp is still within the accepted range of `86400 + 60`. 

For clarity sake, it is better to use same conditions for staleness check across all logic, especially logic of contracts with  inter related  functions (functions that call the other). 


## Recommended Mitigation 
use same conditions for staleness check across affected functions. 