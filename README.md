# MyToken



## Description

This program is a simple contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. The contract has two function mint and burn to create and destroy nfts respectively.

## Getting Started
1. Create public variables that store the details about the coin (Token Name, Token Abbrv., Total Supply)
2. Create a mapping of addresses to balances (address => uint)
3. Crate a Mint function that takes two parameters: an address and a value. 
The function then increases the total supply by that number and increases the balance 
of the “sender” address by that amount
4. Create a Burn function, which works the opposite of the mint function, as it will destroy tokens. 
It will take an address and value just like the mint functions. It will then deduct the value from the total supply 
and from the balance of the “sender”.
5. Lastly,  burn function  have conditionals to make sure the balance of "sender" is greater than or equal 
to the amount that is supposed to be burned.



### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., HelloWorld.sol). Copy and paste the following code into the file:

```javascript
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;


contract MyToken {

    // public variables here
    string public Token_name = "Rengoku";
    string public Abbrv = "RGK";
    uint public total_supply = 0;

    // mapping variable here
    mapping(address => uint) public balances;

    // mint function
    function mint(address _address,uint _value) public{
      total_supply += _value;
      balances[_address] += _value;
    }

    // burn function
    function burn(address _address,uint _value) public{
        if (balances[_address] >= _value){
            total_supply -= _value;
            balances[_address] -= _value;
        }
      
    }
}


```
### Mint Function
```javascript

 function mint(address _address,uint _value) public{
      total_supply += _value;
      balances[_address] += _value;
    }

```
### Burn Function
```javascript

  function burn(address _address,uint _value) public{
        if (balances[_address] >= _value){
            total_supply -= _value;
            balances[_address] -= _value;
        }
      

```




To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18" (or another compatible version), and then click on the "Compile HelloWorld.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "HelloWorld" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the burn and mint function. Pass a valid address and value as parameters for both the mint and burn function.
After transaction check the balances and totalsupply getting changed.
## Authors

Amitesh Singh


## License

This project is licensed under the MIT License - see the LICENSE.md file for details
