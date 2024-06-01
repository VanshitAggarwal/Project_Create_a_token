# MyToken

This Solidity program is a simple Ethereum token contract that demonstrates the basic principles of token creation, minting, and burning on the Ethereum blockchain.

## Description

This project is a Solidity contract that implements an Ethereum token named MetaCrafters (MTCR). The contract includes public variables to store the token's name, abbreviation, and total supply, as well as a mapping to manage balances associated with addresses. It features a mint function to increase the token supply and a burn function to decrease it, ensuring basic checks for sufficient balance before burning tokens. This program serves as a practical introduction to token management in Solidity and can be used as a foundation for more complex projects.

## Getting Started

### Executing Program

To run this program, you can use Remix, an online Solidity IDE. Follow these steps:

1. **Visit Remix**: Go to the Remix website at [Remix Ethereum](https://remix.ethereum.org/).

2. **Create a New File**: Click on the "+" icon in the left-hand sidebar to create a new file. Save the file with a `.sol` extension (e.g., `MyToken.sol`). Copy and paste the following code into the file:

    ```solidity
    // SPDX-License-Identifier: MIT
    pragma solidity ^0.8.18;

    contract MyToken {

        // Public variables here
        string public TokenName = "MetaCrafters";
        string public TokenAbbrv = "MTCR";
        uint public TotalSupply = 0;

        // Mapping variable here
        mapping (address => uint) public Balances;

        // Mint function
        function mint(address _address, uint _value) public {
            TotalSupply += _value;
            Balances[_address] += _value;
        }

        // Burn function
        function burn(address _address, uint _value) public {
            if (Balances[_address] > _value) {
                TotalSupply -= _value;
                Balances[_address] -= _value;
            }
        }
    }
    ```

3. **Compile the Code**: Click on the "Solidity Compiler" tab in the left-hand sidebar. Ensure the "Compiler" option is set to `0.8.18` (or another compatible version), and then click on the "Compile MyToken.sol" button.

4. **Deploy the Contract**: Click on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the `MyToken` contract from the dropdown menu, and then click on the "Deploy" button.

5. **Interact with the Contract**: Once the contract is deployed, you can interact with it by calling the `mint` and `burn` functions. Click on the `MyToken` contract in the left-hand sidebar, and use the provided functions to mint and burn tokens.

## Authors

Metacrafter Vanshit Aggarwal
@VanshitAggarwal

## License

This project is licensed under the MIT License. see the [License.md](License.md) file for details.

