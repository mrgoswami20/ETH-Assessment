# ETH-Assessment

This Solidity program is a simple "Create a token" program that demonstrates the basic syntax and functionality of the Solidity programming language. This contract is a simple implementation of a custom token called MyToken. It allows minting new tokens, burning existing tokens, and tracking balances of token holders.

## Description
MyToken

MyToken is a simple ERC20-compatible token contract implemented in Solidity. It represents a token called "Polygon" with the abbreviation "MATIC". The contract allows token minting and burning, and provides functionality to track token balances for different addresses.

Public Variables

- `tokenName`: A public string variable representing the name of the token.
- `tokenAbbrv`: A public string variable representing the abbreviation or symbol of the token.
- `totalSupply`: A public uint variable representing the total supply of the token.

Mapping Variable

- `balances`: A mapping variable that associates addresses with their corresponding token balances. It allows users to query token balances for specific addresses.

Functions

- `mint`: A function that mints new tokens and assigns them to a specified address. The total supply and the balance of the given address are increased by the minted amount.
- `burn`: A function that burns (destroys) a specified amount of tokens owned by a given address. If the address has a sufficient balance, the total supply and the balance of the address are reduced by the burned amount.

This contract can be used as a starting point for creating and managing custom tokens on the Ethereum blockchain. It provides the basic functionality required for token issuance, transfers, and balance tracking. Feel free to use and modify this contract as needed for your own token projects.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the left-hand sidebar. Save the file with a .sol extension (e.g., myToken.sol). Copy and paste the following code into the file:

```javascript
// SPDX-License-Identifier: MIT
pragma solidity >=0.8.18;

/*
       REQUIREMENTS
    1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
    2. Your contract will have a mapping of addresses to balances (address => uint)
    3. You will have a mint function that takes two parameters: an address and a value. 
       The function then increases the total supply by that number and increases the balance 
       of the “sender” address by that amount
    4. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. 
       It will take an address and value just like the mint functions. It will then deduct the value from the total supply 
       and from the balance of the “sender”.
    5. Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal 
       to the amount that is supposed to be burned.
*/

contract MyToken {

    // public variables here
    string public tokenName = "Polygon";
    string public tokenAbbrv = "MATIC";
    uint public totalSupply = 0;

    // mapping variable here
    mapping(address => uint) public balances;

    // mint function
    function mint(address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }

    // burn function
    function burn(address _address, uint _value) public {
        if(balances[_address] >= _value){
            totalSupply -= _value;
            balances[_address] -= _value;
        }
    }

}

```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to graater than 0.8.18, and then click on the "Compile myToken.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "myToken" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the the following functions: mint function, burn function and also can check variables values like balances, tokenName, tokenAbbrv, totalSupply. To track token balances of address or token minting and burning you have to write or copy paste sender account.

## Authors

Rohit kumar goswami


## License

This project is licensed under the MIT License
