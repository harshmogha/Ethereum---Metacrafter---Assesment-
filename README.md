# MyToken Smart Contract

This Solidity program is a simple token contract that demonstrates the basic functionality of creating, minting, and burning tokens. The purpose of this program is to serve as a starting point for those who are new to Solidity and want to get a feel for how token contracts work.

## Description

This program is a simple contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. The contract defines a custom token with the following features:
1. Public variables to store the details about the token (Token Name, Token Abbreviation, Total Supply).
2. A mapping of addresses to balances.
3. A mint function to create new tokens and assign them to an address.
4. A burn function to destroy tokens from an address, ensuring the address has enough balance to burn.

The program serves as a simple and straightforward introduction to Solidity token contracts and can be used as a stepping stone for more complex projects in the future.

## Getting Started

### Executing the Program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at [https://remix.ethereum.org/](https://remix.ethereum.org/).

#### Steps to Deploy the Contract:

1. **Create a New File**:
   - On the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar.
   - Save the file with a `.sol` extension (e.g., `MyToken.sol`).

2. **Copy and Paste the Code**:
   ```solidity
   // SPDX-License-Identifier: MIT
   pragma solidity 0.8.18;

   contract MyToken {
       string public tokenName = "Harsh";
       string public tokenAbbrv = "MTK";
       uint256 public totalSupply;

       mapping(address => uint256) public balances;

       function mint(address _to, uint256 _value) public {
           totalSupply += _value;
           balances[_to] += _value;
       }

       function burn(address _from, uint256 _value) public {
           require(balances[_from] >= _value, "Insufficient balance to burn");
           totalSupply -= _value;
           balances[_from] -= _value;
       }
   }
   ```

3. **Compile the Code**:
   - Click on the "Solidity Compiler" tab in the left-hand sidebar.
   - Make sure the "Compiler" option is set to "0.8.18" (or another compatible version).
   - Click on the "Compile MyToken.sol" button.

4. **Deploy the Contract**:
   - Click on the "Deploy & Run Transactions" tab in the left-hand sidebar.
   - Select the "MyToken" contract from the dropdown menu.
   - Click on the "Deploy" button.

5. **Interact with the Contract**:
   - Once the contract is deployed, you can interact with it by calling the mint and burn functions.
   - To mint tokens, input the address and value, then click on the "mint" function.
   - To burn tokens, input the address and value, then click on the "burn" function.

This will allow you to create and destroy tokens, updating the total supply and balances accordingly.
