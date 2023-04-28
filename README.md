# Create a Token

This assessment basically contains a solidity smart contract to create our own token. We have used mint and burn function for that.

## Description

The code structure contains three public variables(tokenname, tokenAbbrv and totalSupply) and two functions mint and burn. Initially the total supply we have set to zero. By using the mint function we can mint as many tokens as we pass in value argument from an address. By burn function we can delete the number of tokens we pass in value argument of burn function.

### Executing program

All we need to do to run the smart contract is to paste the complete code in remixIDE, compile the code, deploy and that's it. All functionalities will work.

```
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
    string public tokenname = "PRIYA"; 
    string public tokenAbbrv = "PRI"; 
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
```

## License

This project is licensed under the MIT License - see the LICENSE.md file for details
