# Account Abstraction

**Account Abstraction (AA)** is a design pattern that aims to unify externally owned accounts (EOAs) and smart contract accounts, enabling flexible and programmable wallet behavior.

---

## 🔐 Why Account Abstraction?

- EOAs are limited (must hold private key, can't verify logic)
- Smart contract wallets offer better UX and security
- AA allows wallets to define their own logic (validation, gas, auth)

---

## 🧠 Key Concepts

| Concept           | Description                                                |
|-------------------|------------------------------------------------------------|
| UserOperation     | Customizable transaction format sent to an entry point     |
| EntryPoint        | Contract that handles validation and execution             |
| Paymasters        | Contracts that pay gas on behalf of the user               |
| Bundlers          | Batch and send UserOps to the chain                        |

---

## 🔧 ERC-4337: The AA Standard

- Implements AA **without requiring Ethereum protocol changes**
- Introduced `UserOperation` object instead of raw transactions
- Enables **gasless txs**, **social recovery**, and **multi-sig UX**

---

## ✨ Features Enabled by AA

- Biometric or social login (no seed phrases)
- Multi-signature wallets for individuals
- Session keys (temporary auth for games)
- Gas sponsored transactions (dApps pay gas)
- Logic-based validation (time-locked txs)

---

## 🧪 Ecosystem Tools

| Tool         | Description                            |
|--------------|----------------------------------------|
| Biconomy     | Plug-and-play AA wallet infra          |
| Stackup      | SDKs and bundler network for AA        |
| Safe Core    | Modular smart contract wallet infra    |
| ZeroDev      | Developer platform for AA apps         |

---

## 🚀 Developer Flow (ERC-4337)

1. Build a smart wallet contract
2. Encode a `UserOperation` with data
3. Send to bundler → EntryPoint
4. Bundler sends a single tx with many ops

---

## 📚 Resources

- [ERC-4337 Spec](https://eips.ethereum.org/EIPS/eip-4337)
- [Biconomy Docs](https://docs.biconomy.io/)
- [Stackup Docs](https://docs.stackup.sh/)
- [ZeroDev](https://docs.zerodev.app/)

---

✍️ Created by [@alkhatib99](https://github.com/alkhatib99)
