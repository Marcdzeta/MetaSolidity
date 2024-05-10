# Mytoken.sol 
Solidity is an object-oriented, high-level language for implementing smart contracts. Smart contracts are programs that govern the behavior of accounts within the Ethereum state.

## Description
Good day! Im Marc and we are to diccuss the solidity in metacrafters. So, here is the requirments for our assessment in solidity.

## Getting Started
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

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
    string public tokenName = "Crafters";
    string public tokenAbrrv = "CRFT";
    uint public totalSupply = 0;

    // mapping variable here
    mapping(address => uint) public balances;


    // mint function
    function mint (address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
      }

        // burn function
        function burn (address _address, uint _value) public {
        if (balances[_address] >= _value) {
            totalSupply -= _value;
            balances[_address] -= _value;
        }
    }
}

## Executing Program
To run this program, you can use Remix, an online solidity IDE. To get started, go to remix website at https://remix.ethereum.org. Once you are on the remix website, Create a new file
by clicking on the "+" icon in the left hand sidebar. Save the file with a .sol extension. Example, Crafter.sol. then copy the given code in the assessment.

## Author
Marc Danniel Mariazeta
61902476@ntc.edu.ph

## License
This project is licensed under the MIT License -  see the LICENSE file for details 

