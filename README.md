# Create a Token

This is a solidity program to create a token of our own which is named as "KeshavCoin" demonstrating the use of different functions for adding coin and deducing from the the available total balance in the account . The name of the contract can be anything according to the user's choice. This is a simple contract to display the total available balance on the given address after adding or burning the coin from the available balance using different functions such as, mint function and burn function.  

## Description

This program is a simple contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. The program consists of two functions namely mint function and burn function. Mint function takes two parameters: an address and a value.The function then increases the total supply by that number and increases the balance of the "account" address by that amount. Then we have the "burn function" that works just opposite of the mint function as it destroys the tokens. This fuction also takes two parameters: an address and a value. It deducts the value from the total supply 
and from the balance of the “sender”.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/. Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., SolidityAssessment.sol). Copy and paste the following code into the file:
```javascript
// SPDX-License-Identifier: UNLICENSED
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

contract KeshavCoin {

    // public variables here
    string public CoinName = 'K-Bitcoin';
    string public CoinAbbrv = 'Bitcoin';
    uint public totalCoinSupply = 0;

    // mapping variable here
    mapping(address => uint) public Total_balance;

    // mint function
    function mint (address coin_address, uint coin_value) public {
        totalCoinSupply += coin_value;
        Total_balance[coin_address] += coin_value;
        
    } 

    // burn function
    function burn (address coin_address, uint coin_value) public {
       if(Total_balance[coin_address] >= coin_value){
           totalCoinSupply -= coin_value;
           Total_balance[coin_address] -= coin_value;
        } 
    }
}

```
## INSTRUCTIONS TO RUN THE PROGRAM

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18" (or another compatible version), and then click on the "Compile SolidityAssessment.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "KeshavCoin-SolidityAssessment.sol" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the mint and burn function. Click on the "KeshavCoin" contract in the left-hand sidebar, and then click on the "mint" function to increase the total supply by entering the account address in "coin_address" by copying it from the account section at the top in the left-hand side and also enter the amount to be added in the "coin_value". Finally, click on the "transact" button to execute the function. After the successfull execution of the function you can check the "totalCoinSupply" to check the balance after the addition of the tokens. Follow the same procedure to execute the "burn function" for deducing the token amount.


## Author

KESHAV KUMAR

keshavkumaraster@gmail.com
