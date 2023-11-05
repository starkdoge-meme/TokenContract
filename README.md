![Tests](https://github.com/gaetbout/starknet-erc20-lazy-initialization/actions/workflows/tests.yml/badge.svg)  [![Twitter URL](https://img.shields.io/twitter/url.svg?label=Follow%20%40gaetbout&style=social&url=https%3A%2F%2Ftwitter.com%2Fgaetbout)](https://twitter.com/gaetbout)

# starknet-erc20-lazy-initialization
## 🪂 Description
Open now your wallet on ~~Goerli~~ Mainnet and add this token:  
**0x06321571ce6f884a184e6c5872dfb2b833201c5a4707c1bce0bfb62f252192ee**.  
You should see a balance of 1.000 GAET s.  
Deploy a new wallet and add the token again... It also has 1.000 GAETs.  
Every existing wallet or wallet that will ever exist will have 1.000 GAETs. Wait whaaaaaat?  
But how, why, again what?  
  
This is the biggest airdrop ever. Every address existing or that will exist will have 1.000 tokens of this token.  
I didn't run a computer to send this token to every possible address I just modifid the default implementation of an ERC20 contract to make it lazy initialized.  
Note that it could also be used as a testnet (or even mainnet) token to avoid user to have to mint the tokens.  
[Link to the deployed contract](https://starkscan.co/contract/0x07fE495Ecc5549978c73fF9b544B0c6CE84AeB60405AcDeb9Befc603C80dA0e0)  

## 🤔 But how?
First I started by copying [the default ERC20 of OpenZeppelin (at this date)](https://github.com/OpenZeppelin/cairo-contracts/blob/cairo-1/src/openzeppelin/token/erc20.cairo). Then I just had to adapt two methods.  

### ⚖️ balanceOf
Because this is the entry point of an ERC20 to read the balance of a user (how unexpected, right?), this is where we have to make our first little modification.  

 
### 📤 _transfer

This is the same as written by OpenZeppelin with some adjustemnts:  
 1. Checking that the UINT256 is valid (no modification)
 2. Checking that the sender is valid (no modification)
 3. Checking that the receiver is valid (no modification)


## 🌡️ Tests

*Prerequisite: Having asdf scarb installed https://docs.swmansion.com/scarb/download#install-via-asdf*  

```  
For more  details check the Actions tab of this GitHub repository. 

## 📖 Ressources
 - [The original article](https://kf106.medium.com/how-i-created-the-worlds-largest-airdrop-of-all-time-b33b153857c4)
 - [The deployed contract on Etherum](https://etherscan.io/address/0xe7c4F86Ab703343b055433ceE05252158cbb305B#code)
 - [Lazy initialization](https://en.wikipedia.org/wiki/Lazy_initialization)
 - [Some (very) helpful video](https://youtu.be/CcVf_e2DIQU)

## 📄 License

**starknet-erc20-lazy-initialization** is released under the [MIT](https://en.wikipedia.org/wiki/MIT_License).




