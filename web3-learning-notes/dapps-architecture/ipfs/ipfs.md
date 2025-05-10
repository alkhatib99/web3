# IPFS in Web3

**IPFS (InterPlanetary File System)** is a peer-to-peer, distributed file system used for storing and sharing data in a decentralized way. It's commonly used in Web3 to host off-chain data like NFT metadata, images, and files.

---

## 🌐 Why IPFS?

- Content-addressed (uses file hash for access)
- Decentralized and censorship-resistant
- Efficient storage for static files and dApp assets

---

## 🧱 How IPFS Works

- Files are split into chunks, hashed, and stored across nodes
- Each file (or directory) is identified by a **CID (Content Identifier)**
- CIDs are immutable; any change results in a new CID

---

## 🛠 Hosting on IPFS

### Option 1: Use Pinata

[Pinata](https://www.pinata.cloud/) is a popular IPFS pinning service.

```bash
curl -X POST https://api.pinata.cloud/pinning/pinFileToIPFS \
  -H "Authorization: Bearer <JWT>" \
  -F "file=@path/to/file.png"
```

### Option 2: Use NFT.Storage

[NFT.Storage](https://nft.storage/) offers free storage for NFT data.

```bash
npx nft.storage upload ./metadata.json
```

---

## 📁 NFT Example: Metadata File

```json
{
  "name": "Chrono NFT #1",
  "description": "A time-bending digital artifact.",
  "image": "ipfs://bafybeihash/image.png"
}
```

---

## 🔗 Accessing IPFS Content

You can access content from any public IPFS gateway:

```
https://ipfs.io/ipfs/<CID>
https://gateway.pinata.cloud/ipfs/<CID>
```

---

## 🧪 IPFS with Smart Contracts

Store only the IPFS CID on-chain:

```solidity
string public tokenURI = "ipfs://Qm...Hash";
```

---

## 🧰 Useful Tools

- **Pinata**: Upload via API or UI
- **NFT.Storage**: Upload metadata/files
- **web3.storage**: Free decentralized storage with gateway access
- **Infura IPFS**: Full IPFS node support + Ethereum integration

---

## 📚 Resources

- [IPFS.io](https://ipfs.io/)
- [Pinata Docs](https://docs.pinata.cloud/)
- [NFT.Storage](https://nft.storage/)
- [web3.storage](https://web3.storage/)

---

✍️ Created by [@alkhatib99](https://github.com/alkhatib99)
