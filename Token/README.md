# ERC-20 Token

Creation of an ERC-20 standard Ethereum token.

## Erc-20

ERC-20 is the standard interface that allows the implementation of a standard API for tokens within Smart Contracts. 

For more information about Solidity Language and the ERC-20 Standard, see the following links:

- [Solidity](https://solidity.readthedocs.io/en/v0.6.8/) 
- [ERC-20](https://ethereum.org/it/developers/docs/standards/tokens/erc-20/)

### Contract

The contract inherits the functions present in the standard interface _IERC20_ which contains all the functions 
with the relative declarations and the empty body; the latter is initialized and compiled in the contract that inherits it.

### Constructor

The `constructor` sets the` name`, `symbol`,` decimals` and `totalSupply` of the token and the balance of the msg.sender.

### Balance

The `balanceOf` view function returns the balance of an` account` address.

### Transfer and Transfer From

The `transfer` function is called from one account and transfers a certain `amount` of token, to another `recipient` address.

The `transferFrom` function allows an account other than the owner to transfer the `amount`, a certain number of tokens, from a 
given `sender` address to another` recipient`.

Both functions trigger the `Transfer` event.

### Approve

The `approve` function allows a `spender` account to use a certain `amount` of tokens via the` owner` approval.

### Allowance

The `allowance` view function returns the value that the `spender` address is allowed to spend via the `owner` permission.

## Erc-20 imports

### IERC20 

The contract inherits the functions present in the standard interface _IERC20_ which contains all the functions with their relative
statements and the empty body; the latter is initialized and compiled in the contract that inherits it.

### Ownable

The Ownable Agreement provides a basic access control mechanism, where there is an account (one owner) who can be granted exclusive 
access to specific functions.

This module is used through inheritance; it will make available the `onlyOwner` modifier, which can be applied to functions to limit their use to the owner.

By default, the `owner` will be the one who distributes the contract and the address can be changed with the `transferOwnership` method.

### Context

The Context contract provides information about the current execution context: 
sender of the transaction and its data.

# Sale Contract 

Creation of a smart contract for the purchase and sale of tokens.

### Contract

The contract imports the ERC-20 token.

### Constructor

The `constructor` sets the `admin`, `tokenContract` which is the interaction with the token contract, `tokenPrice` which is the price of the token established during the deployment phase.

### buyTokens

The `buyTokens` payable function allows the purchase of a certain `_numberOfTokens` and triggers the Sell event.

### endSale

The `endSale` function returns all unsold tokens to the contract admin and can only be called by the contract admin.

### Requirements for using the repository

Contract compilation, tests and deployment can be performed with the help of the *Truffle* framework.

- [Node.js](https://nodejs.org/download/release/latest-v10.x/)
- [Truffle](https://www.trufflesuite.com/truffle)

## Usage

Run the following command from the terminal:

```sh
npm install
npm install -g truffle
```
All dependencies related to the project and Truffle will be installed globally.

### Compile contracts

Using the following command:

```sh
truffle compile
```
Contract information in JSON format (such as ABI, address, ...) will be available in the `build / contracts /` directory.


### Run tests on Truffle
 
It's possible to test the files in the `/ test` directory by running the command:

```sh
truffle test
```

### Run migration and deploy contracts

Command for migrate:

```sh
truffle migrate --reset --network development // mainnet, rinkeby, polygon, mumbai...
```

After the migration, you will be able to view the deployer and contract address.
