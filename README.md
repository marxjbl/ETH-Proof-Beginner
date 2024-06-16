## Overview

**MyToken** is a simple Ethereum-based token implemented as a smart contract using Solidity. This contract demonstrates the fundamental concepts of token creation, minting, and burning on the Ethereum blockchain. 

## Features

1. **Public Variables**: 
    - `tokenName` - The name of the token.
    - `tokenAbbrv` - The abbreviation of the token.
    - `totalSupply` - The total supply of the token.

2. **Address Balances**: 
    - A mapping of addresses to their respective token balances.

3. **Mint Function**: 
    - Increases the total supply of tokens.
    - Increases the balance of the specified address.

4. **Burn Function**: 
    - Decreases the total supply of tokens.
    - Decreases the balance of the specified address.
    - Ensures the balance of the address is sufficient before burning tokens.

## Contract Details

The contract is written in Solidity version `0.8.18` and is licensed under the MIT License.

## Functions

### Public Variables

- `string public tokenName = "ETH Beginner";`
- `string public tokenAbbrv = "ETHBGNR";`
- `uint public totalSupply = 0;`

### Mapping

- `mapping(address => uint) public balances;`

### Mint Function

The `mint` function increases the total supply of tokens and the balance of a specified address.

```solidity
function mint(address _address, uint _value) public {
    totalSupply += _value;
    balances[_address] += _value;
}
Burn Function
The burn function decreases the total supply of tokens and the balance of a specified address, with a check to ensure the address has sufficient balance.

solidity
Copy code
function burn(address _address, uint _value) public {
    if (balances[_address] >= _value) {
        totalSupply -= _value;
        balances[_address] -= _value;
    }
}
Usage
To interact with this contract, you can use tools like Remix, Truffle, or any Ethereum development framework that supports Solidity. Below are the steps to deploy and interact with the contract using Remix:

Deploy the Contract:

Copy the contract code into Remix.
Compile the contract using the Solidity compiler version 0.8.18.
Deploy the contract to an Ethereum test network or local blockchain.
Interact with the Contract:

Use the deployed contract instance to call the mint and burn functions.
Example: To mint 100 tokens to an address, call mint("0xYourAddress", 100).
Example: To burn 50 tokens from an address, call burn("0xYourAddress", 50).
