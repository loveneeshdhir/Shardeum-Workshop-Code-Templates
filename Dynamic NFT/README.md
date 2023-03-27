<h1>Understanding the Code</h1>
  
- This smart contract that creates a dynamic NFT (non-fungible token) that can be minted by users and its existence is dependent on the price of SHM.

- The contract imports the ERC721.sol contract from the OpenZeppelin library, which is used to create the NFT.

- It defines an interface called ISupraSValueFeed, which specifies a method checkPrice that takes a string representing a market pair (in this case "eth_usdt") and returns the price of the pair as an int256 and a timestamp as a uint256.

- The contract inherits from ERC721 and has a state variable called tokenIds that starts at 1 and will be incremented by the mint function every time a new NFT is minted.

- The contract also has a state variable called sValueFeed, which represents the external price feed contract that provides the current ETH/USD price.

- The contract has a constructor that sets the sValueFeed contract address to any address that we input. In this case the address is 0x5aEDe09489Bb40CC28c6e98A42159f99992154bd

- The mint function takes a uint256 parameter called number and allows users to mint that many new NFTs. It loops through from 0 to the number provided and mints a new NFT for the user with a unique tokenId, then increments the tokenId variable by the number provided.

- The checkPrice function takes a uint256 parameter called _tokenId and checks if the token exists by making sure it is less than or equal to the current tokenIds variable. It then calls the checkPrice function on the external price feed contract and gets the current ETH/USD price. It then checks if the current price is lower than the previous price stored in the contract. If it is, it burns (deletes) the NFT with the given _tokenId. If not, it does nothing.
