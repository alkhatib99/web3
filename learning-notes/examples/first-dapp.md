# Building Your First Web3 DApp

## Overview

A decentralized application (DApp) combines a frontend (e.g. Flutter) with a backend smart contract on the blockchain. It allows users to interact with decentralized systems using a wallet.

---

## Step-by-Step Guide

### 1. Plan the DApp

- Define the use case: mint NFTs, vote, transfer tokens, etc.
- Determine if it requires wallet connection, on-chain data, or both

---

### 2. Write the Smart Contract

Use Solidity with a framework like Hardhat or Foundry.

**Example: Basic NFT Mint Contract**

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

import "@openzeppelin/contracts/token/ERC721/extensions/ERC721URIStorage.sol";

contract MyNFT is ERC721URIStorage {
    uint256 public tokenId;

    constructor() ERC721("MyNFT", "MNFT") {}

    function mint(address to, string memory uri) public {
        _safeMint(to, tokenId);
        _setTokenURI(tokenId, uri);
        tokenId++;
    }
}
```

---

### 3. Deploy the Contract

Use Hardhat:

```bash
npx hardhat compile
npx hardhat run scripts/deploy.js --network sepolia
```

---

### 4. Integrate in Flutter (Web3Dart)

Install `web3dart` and connect using `http` or `websocket`:

```dart
final client = Web3Client("https://sepolia.infura.io/v3/YOUR_KEY", http.Client());
final credentials = EthPrivateKey.fromHex(privateKey);
```

Load contract:

```dart
final abiCode = await rootBundle.loadString('assets/MyNFT.json');
final contract = DeployedContract(ContractAbi.fromJson(abiCode, "MyNFT"), EthereumAddress.fromHex(contractAddress));
```

Call mint:

```dart
await client.sendTransaction(
  credentials,
  Transaction.callContract(
    contract: contract,
    function: contract.function("mint"),
    parameters: [userAddress, tokenUri],
  ),
);
```

---

## Best Practices

- Use `.env` for secrets (API keys, private keys)
- Test everything on Sepolia or Goerli before mainnet
- Validate all user input
- Handle gas errors and transaction failures gracefully

---

## Resources

- [Hardhat Docs](https://hardhat.org/)
- [Web3Dart](https://pub.dev/packages/web3dart)
- [Ethereum Sepolia Faucet](https://sepoliafaucet.com/)
- [IPFS &amp; NFT.storage](https://nft.storage/)

---

🔗 Related:

- [web3dart.md](web3dart.md)
- [minting.md](minting.md)
