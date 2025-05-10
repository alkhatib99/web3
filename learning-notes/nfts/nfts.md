# NFTs (Non-Fungible Tokens)

## What is an NFT?

An NFT is a unique digital asset stored on the blockchain that proves ownership and authenticity of a specific item, such as art, music, or collectibles. NFTs are **non-fungible**, meaning each token is distinct and not interchangeable with others.

## Common NFT Standards

- **ERC-721**: Most common NFT standard, each token has a unique ID.
- **ERC-1155**: Multi-token standard supporting both fungible and non-fungible assets.

## Components of an NFT

- **Token ID**: Unique identifier
- **Owner Address**: Ethereum address that owns the token
- **Metadata URI**: JSON file containing `name`, `description`, `image`, and attributes

Example metadata:

```json
{
  "name": "CryptoTiger",
  "description": "A rare NFT tiger living on-chain.",
  "image": "ipfs://bafybeidxxx/cryptotiger.png",
  "attributes": [
    {"trait_type": "Eyes", "value": "Laser"},
    {"trait_type": "Background", "value": "Jungle"}
  ]
}
```

## Popular Use Cases

- Digital Art & Collectibles
- Gaming Assets
- Music & Film Rights
- Memberships & Access Passes

## Storage Options

- **IPFS**: Preferred for decentralization
- **Arweave**: Long-term archival storage
- **Centralized**: Fast but not decentralized (not recommended)

## Best Practices

- Store media on IPFS or Arweave, not centralized servers
- Include clear metadata schema
- Always verify smart contract source on explorers
- Be aware of gas costs during minting & transferring

## NFT Marketplaces

- [OpenSea](https://opensea.io/)
- [Blur](https://blur.io/)
- [Rarible](https://rarible.com/)
- [Zora](https://zora.co/)

---

🔗 Related:

- [minting.md](minting.md)
- [blockchain.md](blockchain.md)
