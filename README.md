# MyToken Smart Contract

## Overview

**MyToken** is a simple Ethereum-based token implemented as a smart contract using Solidity. This contract demonstrates the fundamental concepts of token creation, minting, and burning on the Ethereum blockchain. 

## Description

MyToken is a basic Solidity smart contract that showcases the creation and management of tokens on Ethereum. It includes functions for minting new tokens and burning existing ones, along with public variables to store token details and a mapping to track token balances for addresses.

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
    totalSupply += _value;              // increases the value by "_value"
    balances[_address] += _value;       // increases the balance by "_value"
}
```

### Burn Function
The `burn` function decreases the total supply of tokens and the balance of a specified address, with a check to ensure the address has sufficient balance.

```solidity
function burn (address _address, uint _value) public {
    if (balances[_address] >= _value){  // to make sure that balance of account is greater than or equal to the amount that is supposd to be burned
        totalSupply -= _value;          // decreases the value by "_value"
        balances[_address] -= _value;   // decreases the value by "_value"
    }
}
```

## Getting Started

### Installing

To use this contract, you can download the source code from the GitHub repository or clone it using Git. No modifications are needed to the files or folders for basic usage.

### Executing Program

To run and interact with the contract, follow these steps:

1. Deploy the contract to an Ethereum test network or local blockchain using a development environment like Remix or Truffle.
2. Interact with the deployed contract using its address.
3. Use the provided functions (`mint` and `burn`) to manage token supply and balances.
