# Create and Mint Tokens

This program allows users to mint, burn, and transfer tokens. The purpose of this program is to serve as a starting point for those who are new to ERC20 Contracts and want to get a feel for how it works.

## Description

This program is a simple contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. The contract has a three functions: mint, burn, and transfer. The owner of the token can only mint while any user can burn and transfer tokens. This also uses libraries from ERC20 to utilize its functions.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., MyToken.sol). Copy and paste the following code into the file:

```javascript
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

import "@openzeppelin/contracts/token/ERC20/ERC20.sol";
import "@openzeppelin/contracts/access/Ownable.sol";

contract Mtoken is ERC20, Ownable {
    constructor(string memory name, string memory symbol) ERC20(name, symbol) Ownable(msg.sender) {}

    // Function to mint tokens, only accessible by the owner
    function mint(uint256 amount) public onlyOwner {
        _mint(msg.sender, amount);
    }

    // Function to burn tokens, accessible by any user
    function burn(address to, uint256 amount) public {
        _burn(to, amount);
    }
}
```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.20" (or another compatible version), and then click on the "Compile MyToken.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "MyToken" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the functions mint, burn, transfer, balanceOf, totalSupply, name, symbol, and owner.

## Author

Kristine Garcia

## License

This project is licensed under the MIT License - see the LICENSE.md file for details
