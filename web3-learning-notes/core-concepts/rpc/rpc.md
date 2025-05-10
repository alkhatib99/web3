# RPC in Web3

RPC (Remote Procedure Call) is a protocol used to interact with blockchain nodes. In Web3, dApps use RPC endpoints to read blockchain data and broadcast transactions.

---

## 🌐 What is a JSON-RPC?

Ethereum exposes a set of **JSON-RPC methods** that allow you to:
- Query blockchain state
- Fetch account balances or contract storage
- Send signed transactions
- Call contract methods

All requests are JSON formatted and sent via HTTP(s) or WebSocket.

---

## 🧠 Common JSON-RPC Methods

| Method               | Description                                 |
|----------------------|---------------------------------------------|
| `eth_blockNumber`    | Returns latest block number                 |
| `eth_getBalance`     | Returns ETH balance of address              |
| `eth_call`           | Executes contract read (view/pure)          |
| `eth_sendRawTransaction` | Broadcasts a signed transaction         |
| `eth_getTransactionReceipt` | Returns tx receipt (gas used, status) |
| `net_version`        | Returns current chain ID                    |

---

## 🔧 Using RPC in Practice

```bash
curl -X POST https://mainnet.infura.io/v3/YOUR_API_KEY \
  -H "Content-Type: application/json" \
  -d '{
    "jsonrpc":"2.0",
    "method":"eth_blockNumber",
    "params":[],
    "id":1
  }'
```

---

## 📡 Popular Public RPC Providers

| Provider      | Website                        | Notes                          |
|---------------|--------------------------------|--------------------------------|
| Infura        | infura.io                      | Widely used, free tier         |
| Alchemy       | alchemy.com                    | Performance monitoring         |
| QuickNode     | quicknode.com                  | Multi-chain support            |
| Chainstack    | chainstack.com                 | Dev-focused, fast RPC nodes    |
| Flashbots RPC | docs.flashbots.net             | For MEV-safe transactions      |

---

## ⚠️ Best Practices

- **Avoid using default public RPCs in production**
- Use **rate-limited keys** to avoid being throttled
- Protect your keys with `.env` and secrets management
- Consider **WebSocket** for real-time updates

---

## 🧪 For Developers

- `ethers.js` and `web3dart` abstract JSON-RPC behind the scenes
- You can switch RPC endpoints to connect to different networks or L2s

```javascript
const provider = new ethers.JsonRpcProvider("https://sepolia.infura.io/v3/YOUR_KEY");
```

---

## 📚 Resources

- [Ethereum JSON-RPC Docs](https://ethereum.org/en/developers/docs/apis/json-rpc/)
- [Infura Docs](https://docs.infura.io/)
- [Alchemy Docs](https://docs.alchemy.com/)

---

✍️ Created by [@alkhatib99](https://github.com/alkhatib99)
