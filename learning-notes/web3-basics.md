## 📘 Web3 Basics – Learning Notes

---

### ✅ **What is Web3?**

Web3 is the decentralized internet — the next generation of the web that uses blockchain technology to give users more control over data, identity, and digital assets.

* **Web1 (Read)** : Static websites, no user interaction.
* **Web2 (Read-Write)** : Interactive, user-generated content, social media, centralized control.
* **Web3 (Read-Write-Own)** : Decentralized, peer-to-peer, trustless, blockchain-powered.

---

### 🔗 **1. Blockchain Fundamentals**

* A **blockchain** is a distributed ledger that records transactions in blocks linked chronologically.
* Each block contains a cryptographic hash of the previous block.
* It’s  **immutable** ,  **transparent** , and **trustless** (no need for middlemen).

#### Examples of Blockchains:

| Blockchain | Language | Consensus            | Use Case                    |
| ---------- | -------- | -------------------- | --------------------------- |
| Ethereum   | Solidity | Proof of Stake (PoS) | Smart contracts, DeFi, NFTs |
| Solana     | Rust     | Proof of History     | High-speed apps             |
| Polygon    | Solidity | PoS (Layer 2)        | Scalable Ethereum dApps     |
| Bitcoin    | Script   | Proof of Work (PoW)  | Currency only               |

---

### 💡 **2. Smart Contracts**

* **Smart Contracts** are self-executing code stored on the blockchain.
* They define logic for token transfers, games, finance, etc.
* Written mostly in **Solidity** (EVM chains) or **Rust** (Solana).

**Example (Solidity):**

<pre class="overflow-visible!" data-start="1658" data-end="1764"><div class="contain-inline-size rounded-md border-[0.5px] border-token-border-medium relative bg-token-sidebar-surface-primary"><div class="flex items-center text-token-text-secondary px-4 py-2 text-xs font-sans justify-between h-9 bg-token-sidebar-surface-primary dark:bg-token-main-surface-secondary select-none rounded-t-[5px]">solidity</div><div class="sticky top-9"><div class="absolute end-0 bottom-0 flex h-9 items-center pe-2"><div class="bg-token-sidebar-surface-primary text-token-text-secondary dark:bg-token-main-surface-secondary flex items-center rounded-sm px-2 font-sans text-xs"><span class="" data-state="closed"><button class="flex gap-1 items-center select-none px-4 py-1" aria-label="Copy"><svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" class="icon-xs"><path fill-rule="evenodd" clip-rule="evenodd" d="M7 5C7 3.34315 8.34315 2 10 2H19C20.6569 2 22 3.34315 22 5V14C22 15.6569 20.6569 17 19 17H17V19C17 20.6569 15.6569 22 14 22H5C3.34315 22 2 20.6569 2 19V10C2 8.34315 3.34315 7 5 7H7V5ZM9 7H14C15.6569 7 17 8.34315 17 10V15H19C19.5523 15 20 14.5523 20 14V5C20 4.44772 19.5523 4 19 4H10C9.44772 4 9 4.44772 9 5V7ZM5 9C4.44772 9 4 9.44772 4 10V19C4 19.5523 4.44772 20 5 20H14C14.5523 20 15 19.5523 15 19V10C15 9.44772 14.5523 9 14 9H5Z" fill="currentColor"></path></svg>Copy</button></span><span class="" data-state="closed"><button class="flex items-center gap-1 px-4 py-1 select-none"><svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" class="icon-xs"><path d="M2.5 5.5C4.3 5.2 5.2 4 5.5 2.5C5.8 4 6.7 5.2 8.5 5.5C6.7 5.8 5.8 7 5.5 8.5C5.2 7 4.3 5.8 2.5 5.5Z" fill="currentColor" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round"></path><path d="M5.66282 16.5231L5.18413 19.3952C5.12203 19.7678 5.09098 19.9541 5.14876 20.0888C5.19933 20.2067 5.29328 20.3007 5.41118 20.3512C5.54589 20.409 5.73218 20.378 6.10476 20.3159L8.97693 19.8372C9.72813 19.712 10.1037 19.6494 10.4542 19.521C10.7652 19.407 11.0608 19.2549 11.3343 19.068C11.6425 18.8575 11.9118 18.5882 12.4503 18.0497L20 10.5C21.3807 9.11929 21.3807 6.88071 20 5.5C18.6193 4.11929 16.3807 4.11929 15 5.5L7.45026 13.0497C6.91175 13.5882 6.6425 13.8575 6.43197 14.1657C6.24513 14.4392 6.09299 14.7348 5.97903 15.0458C5.85062 15.3963 5.78802 15.7719 5.66282 16.5231Z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"></path><path d="M14.5 7L18.5 11" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"></path></svg>Edit</button></span></div></div></div><div class="overflow-y-auto p-4" dir="ltr"><code class="whitespace-pre! language-solidity"><span>pragma solidity ^0.8.0;

contract HelloWorld {
    string public message = "Hello Web3";
}
</span></code></div></div></pre>

---

### 🔐 **3. Web3 Wallets**

* Wallets hold private/public keys, allowing users to interact with dApps and sign transactions.

#### Common Wallets:

* **MetaMask** (browser & mobile)
* **WalletConnect** (connect to mobile wallets)
* **Phantom** (for Solana)
* **Trust Wallet**

#### Key Features:

* Public address: like an email (shared)
* Private key / seed phrase: secret, for signing (never shared)

---

### 🌐 **4. dApps (Decentralized Applications)**

* Built on top of smart contracts.
* Interact via wallets (e.g., MetaMask).
* Frontend built with standard tech (React, Flutter, etc.), backend runs on blockchain.

---

### 💸 **5. Tokens**

#### 🪙 **Fungible Tokens (ERC-20)**

* Same value and interchangeable (like ETH, USDC).
* Standard interface for DeFi, payments.

#### 🎨 **Non-Fungible Tokens (NFTs – ERC-721, ERC-1155)**

* Unique assets (art, collectibles, in-game items).
* Metadata stored on-chain or IPFS.

---

### 🧱 **6. Protocol Standards**

* **ERC-20** – Fungible tokens
* **ERC-721** – NFTs
* **ERC-1155** – Semi-fungible (batch minting/mixed assets)
* **ENS** – Ethereum Name Service (like DNS for wallets)

---

### 📊 **7. DeFi (Decentralized Finance)**

* Financial services without intermediaries.
* Use smart contracts for:
  * Lending/borrowing (Aave, Compound)
  * Trading (Uniswap, SushiSwap)
  * Yield farming, staking

---

### 👥 **8. DAOs (Decentralized Autonomous Organizations)**

* Code-governed organizations
* Decisions made via token-holder voting
* Examples: MakerDAO, ENS DAO

---

### 📁 **9. Decentralized Storage**

Used to store off-chain data (e.g., NFT images, app files).

#### Solutions:

* **IPFS** : InterPlanetary File System
* **Arweave** : Permanent storage
* **Filecoin** : Incentivized IPFS

---

### 📡 **10. Web3 Infrastructure**

| Component      | Purpose                | Examples                             |
| -------------- | ---------------------- | ------------------------------------ |
| Node Providers | Access blockchain data | Alchemy, Infura, QuickNode           |
| Indexing       | Query blockchain data  | The Graph, Moralis                   |
| Oracles        | Connect off-chain data | Chainlink, Band Protocol             |
| Identity/Auth  | Login with wallet      | Web3Auth, SIWE (Sign-In w/ Ethereum) |

---

### 🛠️ **11. Developer Tools & Libraries**

| Tool                | Use Case                       |
| ------------------- | ------------------------------ |
| **Remix IDE** | Online Solidity IDE            |
| **Hardhat**   | Local development & deployment |
| **Foundry**   | Rust-based smart contract tool |
| **Ethers.js** | Interact with Ethereum via JS  |
| **Web3.js**   | JS library for Ethereum        |
| **web3dart**  | Flutter-based Web3 interaction |

---

### 📚 **12. Learn More**

* [ethereum.org/learn]()
* [solana.com/learn]()
* [CryptoZombies.io](https://cryptozombies.io) – Gamified Solidity learning
* [Buildspace](https://buildspace.so) – Project-based learning
* [Alchemy University]() – Full Web3 bootcamp (free)
