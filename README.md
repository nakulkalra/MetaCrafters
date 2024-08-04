NFT and ERC20 Token Implementation
This repository contains two main components:

A JavaScript implementation for minting and managing NFTs (Non-Fungible Tokens).
A Solidity smart contract for creating and managing an ERC20 token.
JavaScript NFT Implementation
Assessment Requirements
Create a variable that can hold a number of NFTs. What type of variable might this be?
A suitable type for holding a number of NFTs is an array.
Create an object inside your mintNFT function that will hold the metadata for your NFTs. The metadata values will be passed to the function as parameters. When the NFT is ready, you will store it in the variable you created in step 1.
The mintNFT function takes metadata parameters and creates an NFT object, which is then stored in the NFTs array.
Your listNFTs() function will print all of your NFTs metadata to the console (i.e., console.log("Name: " + someNFT.name)).
The listNFTs function iterates over the NFTs array and logs the metadata of each NFT.
For good measure, getTotalSupply() should return the number of NFTs you have created.
The getTotalSupply function returns the length of the NFTs array.
