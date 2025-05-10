# Transactions in Web3

A transaction is a signed data package sent from one account to another on the blockchain. It’s the core operation that enables transfers, smart contract calls, and on-chain state changes.

---

## 🔄 What Happens in a Transaction?

1. User initiates a transaction from a wallet.
2. Transaction includes sender, receiver, value, gas info, and data.
3. It is signed using the sender’s private key.
4. The transaction is broadcast to the network and picked up by a validator.
5. Once validated and added to a block, it becomes immutable.

---

## 🧱 Basic Transaction Fields

| Field         | Description                                    |
|---------------|------------------------------------------------|
| `nonce`       | Counter of how many txs sent from an account   |
| `to`          | Recipient address (EOA or contract)            |
| `value`       | Amount of ETH to send (in wei)                 |
| `data`        | Input data (for contract calls)                |
| `gasLimit`    | Max gas allowed for the transaction            |
| `gasPrice`    | Price per gas unit (legacy)                    |
| `maxFeePerGas`| EIP-1559 field for dynamic fee                 |
| `signature`   | Signed hash from sender's private key          |

---

## ⚡ Transaction Types

### 1. **ETH Transfer**
Simple payment between EOAs.
```js
eth_sendTransaction({
  from: "0xYourAddress",
  to: "0xReceiver",
  value: "0x2386f26fc10000" // 0.01 ETH
});
```

### 2. **Smart Contract Call**
Used to interact with contracts (e.g., `transfer()`, `mint()`).

### 3. **Contract Deployment**
`to` is left blank; contract bytecode is included in `data`.

---

## 🔥 EIP-1559 Fee Model

Modern gas model introduced in Ethereum London Upgrade.

```plaintext
maxFeePerGas = baseFee + priorityFee
```

- `baseFee` is burned
- `priorityFee` goes to validator

---

## 🛡 Transaction Status

| Status         | Meaning                          |
|----------------|----------------------------------|
| Pending        | In mempool, not yet confirmed    |
| Confirmed      | Mined and added to a block       |
| Failed         | Reverted or out of gas           |

Use [Etherscan](https://etherscan.io/) to track transaction hashes.

---

## 🧪 Simulating Transactions

- **Remix IDE** – Local test environment
- **Tenderly / Etherscan** – Simulate on real networks
- **Hardhat** – Run local node and scripts

---

## 📚 Resources

- [ethereum.org: Transactions](https://ethereum.org/en/developers/docs/transactions/)
- [EIP-1559](https://eips.ethereum.org/EIPS/eip-1559)
- [Ethers.js docs](https://docs.ethers.org/)

---

✍️ Created by [@alkhatib99](https://github.com/alkhatib99)
