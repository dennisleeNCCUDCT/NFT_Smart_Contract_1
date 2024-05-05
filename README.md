# Sample Hardhat Project

This project demonstrates a basic Hardhat use case. It comes with a sample contract, a test for that contract, and a Hardhat Ignition module that deploys that contract.

Try running some of the following tasks:

```shell
npx hardhat help
npx hardhat test
REPORT_GAS=true npx hardhat test
npx hardhat node
npx hardhat ignition deploy ./ignition/modules/Lock.js
```

# DennisLeeNFTMarketplace

This smart contract is built on Ethereum using Solidity ^0.8.4, and it leverages the OpenZeppelin contracts for standard functionality. The contract serves as an NFT marketplace where users can mint, buy, and sell NFTs securely.

## Features

- **NFT Minting**: Users can mint their own NFTs by specifying a URI that points to their NFT data.
- **Marketplace**: Users can list their NFTs for sale at a specified price, and others can purchase these NFTs through the contract.
- **Resale**: Owners of NFTs can resell their NFTs on the marketplace.
- **Query Functions**: Users can fetch all available items for sale, items they have purchased, and items they have listed.

## Contract Setup

### Prerequisites

- `@openzeppelin/contracts`: Used for robust ERC721 implementation and utilities like counters.
- Solidity version 0.8.4 or higher.
- Hardhat for local blockchain environment and console logging.

### Imports

The contract uses several imports to leverage existing tools and standards:

````solidity
import "@openzeppelin/contracts/utils/Counters.sol";
import "@openzeppelin/contracts/token/ERC721/extensions/ERC721URIStorage.sol";
import "@openzeppelin/contracts/token/ERC721/ERC721.sol";
import "hardhat/console.sol";



Below is a GitHub README template detailing the DennisLeeNFTMarketplace Solidity smart contract.

markdown
Copy code
# DennisLeeNFTMarketplace

This smart contract is built on Ethereum using Solidity ^0.8.4, and it leverages the OpenZeppelin contracts for standard functionality. The contract serves as an NFT marketplace where users can mint, buy, and sell NFTs securely.

## Features

- **NFT Minting**: Users can mint their own NFTs by specifying a URI that points to their NFT data.
- **Marketplace**: Users can list their NFTs for sale at a specified price, and others can purchase these NFTs through the contract.
- **Resale**: Owners of NFTs can resell their NFTs on the marketplace.
- **Query Functions**: Users can fetch all available items for sale, items they have purchased, and items they have listed.

## Contract Setup

### Prerequisites

- `@openzeppelin/contracts`: Used for robust ERC721 implementation and utilities like counters.
- Solidity version 0.8.4 or higher.
- Hardhat for local blockchain environment and console logging.

### Imports

The contract uses several imports to leverage existing tools and standards:

```solidity
import "@openzeppelin/contracts/utils/Counters.sol";
import "@openzeppelin/contracts/token/ERC721/extensions/ERC721URIStorage.sol";
import "@openzeppelin/contracts/token/ERC721/ERC721.sol";
import "hardhat/console.sol";
Contract Declaration
DennisLeeNFTMarketplace is derived from ERC721URIStorage, which itself extends ERC721, thereby providing functionality to set and retrieve URIs for tokens.

Key Functions
Constructor
Sets the contract name and symbol, and initializes the contract owner as the message sender.

solidity
Copy code
constructor() ERC721("Dennislee graduation project", "Dennis :3") {
    owner = payable(msg.sender);
}
Minting and Listing NFTs
createToken(string memory tokenURI, uint256 price): Mints a new token with the specified tokenURI and lists it for sale at the given price.
createMarketItem(uint256 tokenId, uint256 price): Internal function to create a market item.
Transaction Functions
resellToken(uint256 tokenId, uint256 price): Allows a user to list an already purchased NFT for sale again.
createMarketSale(uint256 tokenId): Facilitates the sale of an NFT, transferring ownership and funds.
Query Functions
fetchMarketItems(): Returns all unsold market items.
fetchMyNFTs(): Returns all NFTs owned by the caller.
fetchItemsListed(): Returns all NFTs listed by the caller.
Administrative Functions
updateListingPrice(uint256 _listingPrice): Allows the contract owner to update the listing price for placing an item for sale.
Events
MarketItemCreated: Emitted when a new market item is created, providing details about the item and its sale status.
Modifiers
onlyOwner: Ensures that only the contract owner can perform specific actions (e.g., updating the listing price).
Deployment
To deploy this contract, you will need to set up a Solidity development environment, preferably with Hardhat, and deploy to the Ethereum network using tools like Truffle or Hardhat.
````
