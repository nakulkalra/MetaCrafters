# NFT and ERC20 Token Implementation

This repository contains two main components:
1. A JavaScript implementation for minting and managing NFTs (Non-Fungible Tokens).
2. A Solidity smart contract for creating and managing an ERC20 token.

## JavaScript NFT Implementation

### Assessment Requirements
1. **Create a variable that can hold a number of NFTs. What type of variable might this be?**
   - A suitable type for holding a number of NFTs is an array.
   
2. **Create an object inside your `mintNFT` function that will hold the metadata for your NFTs. The metadata values will be passed to the function as parameters. When the NFT is ready, you will store it in the variable you created in step 1.**
   - The `mintNFT` function takes metadata parameters and creates an NFT object, which is then stored in the NFTs array.
   
3. **Your `listNFTs()` function will print all of your NFTs metadata to the console (i.e., `console.log("Name: " + someNFT.name)`).**
   - The `listNFTs` function iterates over the NFTs array and logs the metadata of each NFT.
   
4. **For good measure, `getTotalSupply()` should return the number of NFTs you have created.**
   - The `getTotalSupply` function returns the length of the NFTs array.

### Code Implementation

```javascript
// Create a variable to hold your NFTs
const NFTs = [];

// This function will take in some values as parameters, create an
// NFT object using the parameters passed to it for its metadata, 
// and store it in the variable above.
function mintNFT(name, eyecolor, shirttype, bling) {
    const NFT = {
        "name": name,
        "eyecolor": eyecolor,
        "shirttype": shirttype,
        "bling": bling
    };
    NFTs.push(NFT);
    console.log("Minted: " + name);
}

// Create a "loop" that will go through an "array" of NFTs
// and print their metadata with console.log()
function listNFTs() {
    for (let i = 0; i < NFTs.length; i++) {
        console.log(NFTs[i]);
    }
}

// Print the total number of NFTs we have minted to the console
function getTotalSupply() {
    console.log(`Total Supplies are: ${NFTs.length}`);
}

// Call your functions below this line
mintNFT("Nakul", "Brown", "Hoodie", "Silver chain");
mintNFT("Aditya", "Black", "Shirt", "Gold chain");
mintNFT("Armaan", "Grey", "Polo", "Pendant");

listNFTs();
getTotalSupply();
```

## Solidity ERC20 Token Implementation

### Assessment Requirements
1. **Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply).**
   - Public variables `tokenName`, `tokenAbbrv`, and `totalSupply` store the token details.
   
2. **Your contract will have a mapping of addresses to balances (address => uint).**
   - A mapping `balances` stores the balance of each address.
   
3. **You will have a mint function that takes two parameters: an address and a value. The function then increases the total supply by that number and increases the balance of the “sender” address by that amount.**
   - The `mint` function increases the total supply and the balance of the given address.
   
4. **Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. It will take an address and value just like the mint functions. It will then deduct the value from the total supply and from the balance of the “sender”.**
   - The `burn` function decreases the total supply and the balance of the given address, ensuring the balance is sufficient.
   
5. **Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal to the amount that is supposed to be burned.**
   - The `burn` function includes a check to ensure the balance is sufficient before burning tokens.

### Code Implementation

```solidity
// SPDX-License-Identifier: MIT
pragma solidity 0.8.26;

contract MyToken {

    // Public variables here
    string public tokenName = "Nakul";
    string public tokenAbbrv = "NK";
    uint public totalSupply = 0;

    // Mapping variable here
    mapping(address => uint) public balances;

    // Mint function
    function mint(address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }

    // Burn function
    function burn(address _address, uint _value) public {
        require(balances[_address] >= _value, "Insufficient balance to burn");
        totalSupply -= _value;
        balances[_address] -= _value;
    }
}
```

## Conclusion

This repository demonstrates the implementation of an NFT management system in JavaScript and an ERC20 token contract in Solidity. The JavaScript code allows minting, listing, and getting the total supply of NFTs, while the Solidity contract provides minting and burning functionalities for an ERC20 token.
