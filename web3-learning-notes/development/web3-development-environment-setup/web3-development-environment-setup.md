# 🧰 Web3 Development Environment Setup (EVM-Based)

This guide walks you through setting up a Web3 dev environment for building decentralized apps (dApps) on Ethereum or EVM-compatible chains using Solidity, Hardhat, MetaMask, and Alchemy.

---

## 🔧 Tools Used

| Tool     | Purpose                                  |
| -------- | ---------------------------------------- |
| Node.js  | JavaScript runtime (required by Hardhat) |
| Hardhat  | Ethereum dev environment and compiler    |
| MetaMask | Wallet for signing transactions          |
| Alchemy  | Node provider to connect to Ethereum     |
| VS Code  | Recommended IDE                          |

---

## ✅ Step 1: Install Node.js & npm

Download and install Node.js (LTS version): [https://nodejs.org](https://nodejs.org)

Check installation:

```bash
node -v
npm -v
```

## ✅ Step 2: Initialize Project

```bash
mkdir my-web3-app
cd my-web3-app
npm init -y
```

## ✅ Step 3: Install Hardhat

```bash
npm install --save-dev hardhat
npx hardhat
```

Choose:

```CSS

> Create a basic sample project
```

It generates:

* contracts/ - Smart contracts

* scripts/ - Deployment scripts

* hardhat.config.js - Configuration

## ✅ Step 4: Set Up MetaMask

1. Install MetaMask: [https://metamask.io/](https://metamask.io/)
2. Create a wallet and back up your seed phrase
3. Add a test network (e.g., Goerli or Polygon Mumbai)

## ✅ Step 5: Get Test ETH

Use a faucet to receive testnet tokens:

* Goerli: [https://goerlifaucet.com/](https://goerlifaucet.com/)
* Mumbai: [https://mumbaifaucet.com/](https://mumbaifaucet.com/)

Paste your MetaMask address to receive test ETH.

## ✅ Step 6: Create Alchemy Account

1. Sign up at [Alchemy](https://www.alchemy.com/)
2. Create a new app:

   1. Chain: Ethereum or Polygon
   2. Network: Goerli, Mumbai, etc.
3. Copy the HTTPS RPC URL

## ✅ Step 7: Configure Hardhat for Alchemy

Install dependencies:

```bash
 npm install @nomiclabs/hardhat-ethers ethers dotenv
```

Create .env:

```env
ALCHEMY_URL= https://eth-goerli.alchemyapi.io/v2/YOUR_API_KEY
PRIVATE_KEY=YOUR_WALLET_PRIVATE_KEY
```

Update hardhat.config.js:

```js
 require("@nomiclabs/hardhat-ethers");
require("dotenv").config();

module.exports = {
  solidity: "0.8.18",
  networks: {
    goerli: {
      url: process.env.ALCHEMY_URL,
      accounts: [process.env.PRIVATE_KEY],
    }
  }
};
```
