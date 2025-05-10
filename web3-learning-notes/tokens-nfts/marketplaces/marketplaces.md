# NFT Marketplaces in Web3

NFT marketplaces are platforms that allow users to **buy, sell, and trade** NFTs. They rely on smart contracts to facilitate ownership transfers, bidding, and listing.

---

## 🏪 Popular Marketplaces

| Name        | Network       | Highlights                             |
|-------------|---------------|----------------------------------------|
| OpenSea     | Ethereum, Polygon, Arbitrum | Largest NFT marketplace         |
| Blur        | Ethereum       | Pro trader UI, real-time bidding      |
| LooksRare   | Ethereum       | Community-driven with rewards         |
| Magic Eden  | Solana, Polygon | Gaming and multi-chain support       |
| Rarible     | Ethereum, Tezos | Multi-chain, creator royalties       |

---

## 📦 Listing an NFT (OpenSea Example)

1. Mint NFT (via smart contract or UI)
2. Approve OpenSea proxy to transfer your token
3. Sign a listing order (off-chain)
4. Buyer matches the order → executes sale

---

## 🔧 Example: Approve and List

```js
const nft = new ethers.Contract(nftAddress, abi, signer);
await nft.setApprovalForAll(openseaProxyAddress, true);
```

---

## ⚖️ Royalties

ERC-721 doesn't enforce royalties. Marketplaces use custom logic or EIP-2981:

```solidity
function royaltyInfo(uint256 tokenId, uint256 salePrice) external view returns (address, uint256);
```

---

## 🛠 Building Your Own Marketplace

Key features:

- `listItem(tokenId, price)`
- `buyItem(tokenId)`
- `cancelListing(tokenId)`
- Uses `transferFrom()` to handle sale
- Optional: support for bidding, auction, or lazy minting

---

## 🧪 Simple Marketplace Solidity Snippet

```solidity
function buy(uint256 tokenId) external payable {
    require(msg.value >= listings[tokenId].price, "Insufficient ETH");
    address seller = listings[tokenId].owner;
    nft.transferFrom(seller, msg.sender, tokenId);
    payable(seller).transfer(msg.value);
}
```

---

## 📚 Resources

- [OpenSea Docs](https://docs.opensea.io/)
- [LooksRare Docs](https://docs.looksrare.org/)
- [EIP-2981 Royalty Standard](https://eips.ethereum.org/EIPS/eip-2981)
- [Build an NFT Marketplace (Blog)](https://blog.openzeppelin.com/building-an-nft-marketplace/)

---

✍️ Created by [@alkhatib99](https://github.com/alkhatib99)
