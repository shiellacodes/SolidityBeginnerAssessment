# SolidityBeginnerAssessment
The main purpose of this contract is to facilitate the creation, distribution, and destruction of a custom cryptocurrency token on the Ethereum blockchain. It allows for basic token management, making it suitable for simple projects or educational purposes in understanding token standards and smart contracts.

## Description
This program is a simple contract using Solidity, a programming language for developing smart contracts on the Ethereum blockchain. The MyToken smart contract implements a custom ERC20-like token, facilitating cryptocurrency creation and management for various applications. It features essential functions like minting and burning, enabling dynamic supply management based on user interaction. Public variables provide transparency regarding the token's name, abbreviation, and total supply, while a mapping structure efficiently tracks individual user balances. The mint function allows for the allocation of new tokens, supporting use cases such as rewards and crowdfunding, whereas the burn function enables users to voluntarily reduce their holdings, helping to regulate supply and enhance token scarcity.

## Getting Started

### Executing program

Executing program
To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.
Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., MyToken.sol). Copy and paste the following code into the file:
```javascript
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;
contract MyToken {

    // public variables here
    string public tokenName = "Meta";
    string public tokenAbbrv = "MTA";
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
To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18" (or another compatible version), and then click on the "Compile MyToken.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "MyToken" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you need to copy the account address, as you will require it to call the mint and burn functions. The mint function allows you to create (increase) the number of tokens, while the burn function destroys (decreases) the tokens. Additionally, the balance tracking mechanism is employed to keep track of the token balances for each address, ensuring accurate records of each user's holdings.



## Authors

202010956@fit.edu.ph
Shiella Marie P. Umali


## License

This project is licensed under the [NAME HERE] License - see the LICENSE.md file for details
