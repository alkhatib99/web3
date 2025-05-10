# Minting NFTs

## What is Minting?

Minting is the process of creating a new NFT on the blockchain by executing a smart contract function that assigns ownership, metadata, and token ID to a user.

## Minting Workflow

### 1. Prepare Metadata

- Upload image/media to IPFS
- Create a JSON metadata file with:

```json
{
  "name": "Your NFT",
  "description": "A cool NFT minted via DApp",
  "image": "ipfs://<CID>/nft.png"
}
```

- Upload metadata JSON to IPFS

### 2. Call Smart Contract

Use a smart contract function like:

```solidity
function mintNFT(address recipient, string memory tokenURI) public returns (uint256)
```

### 3. Save Transaction Details

Track:

- `tokenId`
- `txHash`
- `tokenURI`

## Minting from Flutter with Web3Dart

```dart
final credentials = EthPrivateKey.fromHex(privateKey);
await contract.send(
  'mintNFT',
  [recipientAddress, metadataUri],
  sender: credentials.address,
);
```

## Best Practices

- Always validate user input before minting
- Use a testnet like Sepolia during development
- Compress image files to reduce upload time
- Estimate gas and display it before user confirms

## Types of Minting

- **Lazy Minting**: Metadata exists off-chain until purchase
- **On-Chain Minting**: Everything recorded during minting
- **Batch Minting**: ERC-1155 style for multiple tokens

## Common Pitfalls

- Metadata not pinned or expires from IPFS
- Gas spikes making minting costly
- Forgetting to set approval for marketplace listing

---

🔗 Related:

- [nfts.md](nfts.md)
- [first-dapp.md](first-dapp.md)
