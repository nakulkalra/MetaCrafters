# MyToken

This Solidity program is a simple implementation of a token contract that demonstrates how to mint and burn tokens on the Ethereum blockchain. The contract provides basic functionality for managing token supply and balances.

## Description

The `MyToken` contract contains:
- Public variables to store details about the token such as the **token name**, **token abbreviation**, and **total supply**.
- A mapping to track the balances of addresses.
- A `mint` function to add tokens to an address and increase the total supply.
- A `burn` function to remove tokens from an address and decrease the total supply. It ensures that tokens can only be burned if the balance of the address is sufficient.

This contract serves as a foundation for understanding how tokens work and can be expanded for more complex token systems.

## Requirements

1. Public variables that store the details about the token (Token Name, Token Abbreviation, Total Supply).
2. A mapping from addresses to balances (`address => uint`).
3. A `mint` function to increase both the total supply and the balance of the specified address.
4. A `burn` function to decrease both the total supply and the balance of the specified address. The burn function includes conditionals to ensure that the sender's balance is greater than or equal to the value being burned.

## Getting Started

### Executing the program

To run this contract, you can use Remix, an online Solidity IDE.

1. Go to the Remix website at [Remix IDE](https://remix.ethereum.org/).
2. Create a new file with a `.sol` extension (e.g., `MyToken.sol`).
3. Copy and paste the following code into the file:

```solidity
// SPDX-License-Identifier: MIT
pragma solidity 0.8.26;

contract MyToken {

    // public variables here
    string public tokenName = "Nakul";
    string public tokenAbbrv = "NK";
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
        if (balances[_address] >= _value) {
            totalSupply -= _value;
            balances[_address] -= _value;
        }
    }
}
```

4. To compile the contract, select the **Solidity Compiler** tab on the left-hand sidebar and ensure the compiler version is set to `0.8.26`.
5. Click **Compile MyToken.sol** to compile the contract.
6. Once compiled, navigate to the **Deploy & Run Transactions** tab and deploy the contract.
7. After deployment, you can interact with the `mint` and `burn` functions to manage the token supply.

## Authors

- Nakul

## License

This project is licensed under the MIT License. See the `LICENSE.md` file for more details.