# MyToken

**MyToken Smart Contract**  
A simple Solidity smart contract for creating and managing a custom ERC20-like token with basic minting and burning functionalities.

## Description

The `MyToken` contract allows you to create a token with a specific name, abbreviation, and total supply. Users can mint new tokens to increase the total supply and burn tokens to reduce the total supply. The contract includes safety checks to ensure that only valid operations are executed.

This contract demonstrates basic Solidity features and serves as a foundation for creating more complex token systems.

## Features

- **Public Variables**: Store details about the token (Token Name, Abbreviation, Total Supply).
- **Mapping**: Track balances of addresses.
- **Mint Function**: Increases total supply and balances of specified addresses.
- **Burn Function**: Decreases total supply and balances with safety checks to prevent invalid operations.

## Getting Started

### Installing

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/nakulkalra/Metacrafters.git
   cd mytoken
   ```

2. **Open in Your IDE**: Open the cloned repository in your preferred Integrated Development Environment (IDE) that supports Solidity, such as Remix.

3. **Install Dependencies**: If you are using a local development environment, make sure to install all necessary dependencies for Solidity development, such as the Solidity compiler.

### Executing the Program

To deploy and interact with the contract, follow these steps:

1. **Compile the Contract**:
   - Open the `mytoken.sol` file in Remix or your IDE and compile it to check for any errors.

2. **Deploy the Contract**:
   - In Remix, choose the appropriate environment (e.g., JavaScript VM or Injected Web3) and click on the **Deploy** button.

3. **Interact with the Contract**:
   
   - **Mint Tokens**: Use the `mint` function to increase the supply of tokens.
     ```solidity
     // Example to mint 100 tokens to the specified address
     mint("0xYourAddressHere", 100);
     ```

   - **Burn Tokens**: Use the `burn` function to reduce the supply of tokens.
     ```solidity
     // Example to burn 50 tokens from the specified address
     burn("0xYourAddressHere", 50);
     ```

   - **Verify Balances**: Check the balance of any address using the `balances` mapping.
     ```solidity
     // Example to check the balance of an address
     uint balance = balances("0xYourAddressHere");
     ```

## Help

### Common Issues and Solutions:

1. **Insufficient Balance for Burning**:
   - The `burn` function checks if the address has sufficient balance before proceeding. Ensure that the address has enough tokens to burn.
   - You can view more details using:
     ```solidity
     balances("0xYourAddressHere");
     ```

## Authors

- **Sarth**
  - GitHub: [@nakulkalra](https://github.com/nakulkalra)
  - Email: kalranakul5@gmail.com

## License

This project is licensed under the MIT License. See the `LICENSE.md` file for more details.