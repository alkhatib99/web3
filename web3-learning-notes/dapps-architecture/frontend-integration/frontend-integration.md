# Frontend Integration in Web3

Integrating Web3 functionality into a frontend allows users to interact with smart contracts, sign messages, and manage tokens directly from their browser or mobile app.

---

## 🛠️ Frontend Tech Stack

| Layer         | Tools/Libraries                            |
|---------------|--------------------------------------------|
| UI Framework  | React, Next.js, Flutter                    |
| Wallet Connect| Web3Modal, RainbowKit, WalletConnect SDK  |
| Web3 Library  | ethers.js, web3.js, web3dart (Flutter)     |
| Backend/RPC   | Alchemy, Infura, custom RPC endpoints      |

---

## 🌐 Connecting Wallets

### React Example (with ethers.js)

```javascript
import { ethers } from "ethers";

async function connectWallet() {
  if (!window.ethereum) throw new Error("No crypto wallet found");

  const provider = new ethers.BrowserProvider(window.ethereum);
  const signer = await provider.getSigner();
  const address = await signer.getAddress();

  console.log("Connected address:", address);
}
```

### Flutter Example (web3dart)

```dart
final client = Web3Client("https://sepolia.infura.io/v3/YOUR_KEY", httpClient);
final credentials = EthPrivateKey.fromHex(privateKey);
final address = await credentials.extractAddress();
```

---

## 🧠 Typical Frontend ↔ Smart Contract Flow

1. Load ABI and contract address
2. Connect to wallet
3. Read from contract using `call`
4. Send transactions using `sendTransaction`
5. Wait for confirmation and update UI

---

## 📜 Example: Reading from a Contract

```js
const contract = new ethers.Contract(contractAddress, abi, provider);
const value = await contract.totalSupply();
```

---

## 🔐 Example: Sending a Transaction

```js
const contract = new ethers.Contract(contractAddress, abi, signer);
const tx = await contract.mint("0xRecipient", tokenId);
await tx.wait();
```

---

## 🧰 UI Toolkits

- **RainbowKit**: Wallet UX for React
- **Web3Modal**: Multi-wallet connection popups
- **Flutter Web3 UI**: Custom UI with GetX, Provider, Bloc

---

## 🔐 Security Tips

- Always validate contract addresses and ABIs
- Use environment variables for sensitive keys
- Confirm user wallet chain ID before executing

---

## 📚 Resources

- [web3modal.com](https://web3modal.com/)
- [RainbowKit Docs](https://www.rainbowkit.com/)
- [Flutter + web3dart](https://pub.dev/packages/web3dart)
- [Ethers.js](https://docs.ethers.org/)

---

✍️ Created by [@alkhatib99](https://github.com/alkhatib99)
