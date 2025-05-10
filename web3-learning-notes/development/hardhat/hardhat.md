# Hardhat

**Hardhat** is a development environment for Ethereum software that helps developers compile, test, deploy, and debug smart contracts locally.

---

## 🚀 Why Use Hardhat?

- Built-in local Ethereum node
- Fast testing and forking mainnet state
- Easy Solidity debugging and stack traces
- Great plugin ecosystem (e.g., Ethers, Waffle, OpenZeppelin)

---

## ⚙️ Getting Started

### ✅ Install

```bash
npm install --save-dev hardhat
```

### ✅ Create a project

```bash
npx hardhat
```

Choose `Create a basic sample project`.

---

## 📁 Project Structure

```
/contracts     - Solidity contracts
/scripts       - Deployment scripts
/test          - Unit tests
/hardhat.config.js - Config file
```

---

## 📦 Compile Contracts

```bash
npx hardhat compile
```

---

## 🧪 Test Contracts

Uses Mocha + Chai:

```js
const { expect } = require("chai");

describe("MyContract", function () {
  it("should return correct value", async function () {
    const contract = await ethers.deployContract("MyContract");
    expect(await contract.value()).to.equal(42);
  });
});
```

```bash
npx hardhat test
```

---

## 🚀 Deploy Contracts

### Write a script:
```js
async function main() {
  const [deployer] = await ethers.getSigners();
  const Contract = await ethers.getContractFactory("MyContract");
  const instance = await Contract.deploy();
  console.log("Contract deployed to:", instance.target);
}
main();
```

```bash
npx hardhat run scripts/deploy.js --network sepolia
```

---

## 🔧 Networks in `hardhat.config.js`

```js
module.exports = {
  solidity: "0.8.20",
  networks: {
    sepolia: {
      url: "https://sepolia.infura.io/v3/YOUR_KEY",
      accounts: [PRIVATE_KEY]
    }
  }
};
```

---

## 🛠 Useful Plugins

- `@nomicfoundation/hardhat-toolbox`
- `@openzeppelin/hardhat-upgrades`
- `hardhat-gas-reporter`
- `hardhat-deploy`

---

## 📚 Resources

- [Hardhat Docs](https://hardhat.org/)
- [Plugin Directory](https://hardhat.org/plugins/)
- [Hardhat Boilerplate](https://github.com/nomicfoundation/hardhat-boilerplate)

---

✍️ Created by [@alkhatib99](https://github.com/alkhatib99)
