# MyToken Smart Contract

This Solidity smart contract implements a simple token system with mint and burn functionalities. The token is named "Nakul" (NK), and the contract manages balances and total supply through public variables and mappings.

## Features

1. **Public Variables**:
    - `tokenName`: Stores the name of the token ("Nakul").
    - `tokenAbbrv`: Stores the token abbreviation ("NK").
    - `totalSupply`: Tracks the total supply of tokens.

2. **Address to Balance Mapping**:
    - `balances`: Maps addresses to their token balances (`mapping(address => uint)`).

3. **Mint Function**:
    - Increases the total supply of tokens.
    - Adds the specified amount of tokens to the balance of the specified address.
    - Parameters: `_address` (address to mint tokens to), `_value` (number of tokens to mint).

4. **Burn Function**:
    - Decreases the total supply of tokens.
    - Removes the specified amount of tokens from the balance of the specified address.
    - Ensures that the balance of the address is sufficient to burn the requested amount of tokens.
    - Parameters: `_address` (address to burn tokens from), `_value` (number of tokens to burn).

## Contract Details

- **Token Name**: Nakul (NK)
- **Total Supply**: Initially 0, increases with `mint`, decreases with `burn`.
- **Balance Mapping**: Tracks balances for each address.

### Example Usage

1. **Minting Tokens**:
   - To mint tokens, call `mint(_address, _value)` where `_address` is the address to which tokens will be added, and `_value` is the number of tokens to mint.

2. **Burning Tokens**:
   - To burn tokens, call `burn(_address, _value)` where `_address` is the address from which tokens will be subtracted, and `_value` is the number of tokens to burn.
   - The function will only execute if the `_address` has a balance greater than or equal to `_value`.

## License

This project is licensed under the MIT License.