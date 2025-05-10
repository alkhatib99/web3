# ERC-20 Token Standard

**ERC-20** is the most widely used standard for creating fungible tokens on Ethereum. It defines a set of rules that all Ethereum tokens must follow to be compatible with wallets, exchanges, and dApps.

---

## 🧠 Key Properties

- Fungible (1 token = 1 token)
- Fixed or mintable supply
- Transferable and trackable on-chain
- Compatible with DeFi, wallets, bridges, and DEXs

---

## 📦 Standard Interface

ERC-20 tokens must implement the following functions:

```solidity
function totalSupply() external view returns (uint256);
function balanceOf(address account) external view returns (uint256);
function transfer(address recipient, uint256 amount) external returns (bool);
function allowance(address owner, address spender) external view returns (uint256);
function approve(address spender, uint256 amount) external returns (bool);
function transferFrom(address sender, address recipient, uint256 amount) external returns (bool);
```

Events:
```solidity
event Transfer(address indexed from, address indexed to, uint256 value);
event Approval(address indexed owner, address indexed spender, uint256 value);
```

---

## 🔨 Example: Simple ERC-20 Token

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

import "@openzeppelin/contracts/token/ERC20/ERC20.sol";

contract MyToken is ERC20 {
    constructor() ERC20("My Token", "MTK") {
        _mint(msg.sender, 1000000 * 10 ** decimals());
    }
}
```

---

## 🚀 Deployment (with Hardhat)

```bash
npx hardhat run scripts/deploy.js --network sepolia
```

### `scripts/deploy.js` Example:

```js
async function main() {
  const [deployer] = await ethers.getSigners();
  const Token = await ethers.getContractFactory("MyToken");
  const token = await Token.deploy();
  console.log("Deployed to:", token.target);
}
```

---

## 🔧 Interacting via Web3

```js
const token = new ethers.Contract(tokenAddress, abi, signer);
await token.transfer(recipient, amount);
await token.approve(spender, amount);
await token.transferFrom(owner, recipient, amount);
```

---

## 🛡 Best Practices

- Use **OpenZeppelin Contracts**
- Avoid minting from external addresses (use roles)
- Set decimals wisely (commonly 18)
- Consider adding EIP-2612 (permit) for gasless approvals

---

## 📚 Resources

- [ERC-20 Spec](https://eips.ethereum.org/EIPS/eip-20)
- [OpenZeppelin Docs](https://docs.openzeppelin.com/contracts/)
- [Ethers.js ERC-20 Usage](https://docs.ethers.org/v6/api/contract/example/#erc20)

---

✍️ Created by [@alkhatib99](https://github.com/alkhatib99)
