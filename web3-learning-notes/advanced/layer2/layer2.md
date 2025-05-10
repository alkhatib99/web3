# Layer 2 Scaling Solutions

Layer 2 (L2) refers to blockchain scaling frameworks built on top of Layer 1 (e.g., Ethereum) to improve transaction speed, reduce gas fees, and increase throughput without sacrificing decentralization or security.

---

## ⚙️ Why Layer 2?

- Ethereum mainnet (L1) has limited TPS (~15/sec)
- High congestion → high gas fees
- L2 offloads computation & batching of transactions

---

## 🧠 Layer 2 Categories

### 1. **Rollups**
Bundle multiple txs into one, then post proof to Ethereum.

| Type           | Description                                     |
|----------------|-------------------------------------------------|
| Optimistic     | Assume valid, challenge period (e.g., Arbitrum) |
| ZK Rollups     | Use validity proofs (e.g., zkSync, Starknet)    |

### 2. **Sidechains**
Independent chains with their own consensus (e.g., Polygon PoS)

### 3. **State Channels**
Off-chain txs between parties, settled on-chain later (e.g., Raiden)

### 4. **Validium**
Similar to ZK rollups but with off-chain data availability

---

## 🚀 Major Layer 2 Solutions

| Name         | Type        | Key Feature                         |
|--------------|-------------|-------------------------------------|
| Arbitrum     | Optimistic  | EVM-compatible, high adoption       |
| Optimism     | Optimistic  | Simple migration from Ethereum      |
| zkSync Era   | ZK Rollup   | Native account abstraction          |
| Starknet     | ZK Rollup   | Uses Cairo language, powerful proofs|
| Polygon zkEVM| ZK Rollup   | EVM-compatible with low cost        |
| Base         | Optimistic  | Built by Coinbase, part of OP Stack|

---

## 🔄 Bridging to L2

Use bridges to move assets from L1 → L2:

```plaintext
1. Connect wallet
2. Approve token for bridge
3. Initiate deposit
4. Wait for confirmation/finality
```

Popular bridges:
- [Hop Protocol](https://hop.exchange/)
- [Orbiter Finance](https://www.orbiter.finance/)
- [Polygon Bridge](https://wallet.polygon.technology/bridge)

---

## 🛡 L2 Security Model

- Inherits security from L1
- Rollup contracts live on Ethereum
- Fraud proofs or validity proofs enforce trust

---

## 📚 Resources

- [l2beat.com](https://l2beat.com/)
- [Optimism Docs](https://docs.optimism.io/)
- [Arbitrum Docs](https://developer.arbitrum.io/)
- [zkSync Docs](https://era.zksync.io/)

---

✍️ Created by [@alkhatib99](https://github.com/alkhatib99)
