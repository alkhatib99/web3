# Foundry

**Foundry** is a blazing fast, developer-focused toolkit for Ethereum smart contract development written in Rust. It includes a compiler, testing framework, deployment tools, and scripting engine.

---

## ⚡ Why Foundry?

- Extremely fast testing and compilation
- Write tests in Solidity
- Built-in support for forking mainnet and gas reporting
- CLI-first, ideal for power users

---

## 📦 Installing Foundry

### ✅ Using Foundryup

```bash
curl -L https://foundry.paradigm.xyz | bash
foundryup
```

This installs:
- `forge`: for compiling, testing, deploying
- `cast`: for RPC interactions and scripting

---

## 📁 Project Structure

```bash
forge init my-foundry-app
cd my-foundry-app
```

```
/src       - Your contracts
/test      - Solidity tests
/script    - Deployment and interaction scripts
```

---

## 🧪 Writing Tests in Solidity

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

import "forge-std/Test.sol";

contract CounterTest is Test {
    Counter public counter;

    function setUp() public {
        counter = new Counter();
    }

    function testIncrement() public {
        counter.increment();
        assertEq(counter.count(), 1);
    }
}
```

```bash
forge test
```

---

## 🔧 Config: `foundry.toml`

```toml
[profile.default]
src = 'src'
out = 'out'
libs = ['lib']
remappings = ['@openzeppelin=lib/openzeppelin-contracts']
```

---

## 🔥 Forking Mainnet

```bash
forge test --fork-url https://eth-mainnet.alchemyapi.io/v2/YOUR_KEY
```

---

## 📜 Cast – Interact with Contracts

```bash
cast call 0xContractAddress "balanceOf(address)(uint256)" 0xYourAddress \
  --rpc-url https://mainnet.infura.io/v3/YOUR_KEY
```

---

## 🚀 Deploying with Forge

```solidity
// script/Deploy.s.sol
contract Deploy is Script {
    function run() external {
        vm.broadcast();
        new MyContract();
    }
}
```

```bash
forge script script/Deploy.s.sol --rpc-url <URL> --broadcast --private-key <KEY>
```

---

## 📚 Resources

- [Foundry Book](https://book.getfoundry.sh/)
- [Foundry GitHub](https://github.com/foundry-rs/foundry)
- [Paradigm Docs](https://docs.paradigm.xyz/)

---

✍️ Created by [@alkhatib99](https://github.com/alkhatib99)
