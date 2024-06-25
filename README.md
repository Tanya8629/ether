MY TOKEN
This Solidity program is a simple program writtened to create token in blockchain using solidity and mint and burn the the total supply of tokens and learn more about the tokens.

Description
This program is a simple contract written in Solidity, a programming language used for developing smart contracts similarly in this program we created smart contract named my token and wrote some variables inside it and then created functions to mint and burn total supply ok tokens.
Getting Started
Executing program
To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/. 

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., HelloWorld.sol). Copy and paste the following code into the file:
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
      string public token_name = "Ether";
  string public token_abbrv = "Ethereum";
  uint public total_supply = 1;

    // mapping variable here
mapping(address=> uint) public balances;
    // mint function
    function mint(address addresss, uint value) public  {
      total_supply += value;
      balances[addresss] += value;
    } 
      // burn function
      function burn(address addresss, uint value) public  {
        if(balances[addresss]>=value){
          total_supply -= value;
      balances[addresss] -= value;

        }
      
    } 

}
To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.4" (or another compatible version), and then click on the "Compile HelloWorld.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "my token" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the burn and mint function. 
Authors

License
This project is licensed under the MIT License - see the LICENSE.md file for details
