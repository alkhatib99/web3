# Ethers.js

**Ethers.js** is a lightweight JavaScript library for interacting with the Ethereum blockchain. It's designed to be small, simple, and secure — ideal for frontend apps and Node.js backends.

---

## 🔧 Why Use Ethers.js?

- Modular and tree-shakeable
- Easy wallet and provider handling
- Native support for ENS, HD wallets, ABI encoding/decoding
- Fully TypeScript-compatible

---

## 🚀 Getting Started

### ✅ Installation

```bash
npm install ethers
```

### ✅ Import

```javascript
import { ethers } from "ethers";
```

---

## 📡 Connect to Ethereum

```javascript
const provider = new ethers.JsonRpcProvider("https://mainnet.infura.io/v3/YOUR_API_KEY");
const blockNumber = await provider.getBlockNumber();
```

---

## 👛 Wallets

### Create a random wallet

```javascript
const wallet = ethers.Wallet.createRandom();
console.log(wallet.address);
```

### Load from private key

```javascript
const wallet = new ethers.Wallet(PRIVATE_KEY, provider);
```

---

## 📝 Interact with Smart Contracts

### Setup Contract Instance

```javascript
const contract = new ethers.Contract(CONTRACT_ADDRESS, ABI, wallet);
```

### Read from contract

```javascript
const name = await contract.name();
```

### Write to contract (state change)

```javascript
const tx = await contract.transfer(toAddress, amount);
await tx.wait();
```

---

## 🔐 Signing Messages

```javascript
const signedMessage = await wallet.signMessage("Hello Web3");
```

Useful for "Sign-In With Ethereum" (SIWE) authentication flows.

---

## 🔥 Gas Fees and EIP-1559

```javascript
const feeData = await provider.getFeeData();
console.log(feeData.maxFeePerGas.toString());
```

---

## 🛠 Useful Tools

| Function                | Description                        |
|-------------------------|------------------------------------|
| `parseEther()`          | Convert ETH → wei                  |
| `formatEther()`         | Convert wei → ETH                  |
| `getBalance(address)`   | Get ETH balance                    |
| `estimateGas()`         | Estimate gas cost of a call        |
| `getTransactionReceipt()`| Get status and logs               |

---

## 🧪 Resources

- [Ethers.js Docs](https://docs.ethers.org/)
- [Etherscan API](https://docs.etherscan.io/)
- [Infura RPC Docs](https://docs.infura.io/)

---

✍️ Created by [@alkhatib99](https://github.com/alkhatib99)
