# Gas Optimization Techniques in Solidity

Optimizing gas usage helps reduce transaction costs and improve the efficiency of smart contracts — especially important for users and scalability.

---

## ⛽ Why Optimize for Gas?

- Lower costs for users
- Encourages usage and adoption
- Reduces chances of running out of gas mid-tx
- Makes smart contracts more efficient and scalable

---

## 📦 Common Optimization Techniques

### 1. **Use `uint256` over smaller types**
- Smaller types cost more when tightly packed incorrectly

```solidity
uint256 x; // preferred
```

### 2. **Short-Circuit `require()` Statements**

```solidity
require(a > 0 && b < 100, "Invalid input");
```

### 3. **Avoid Dynamic Arrays in Loops**

```solidity
for (uint i = 0; i < array.length; i++) {
    // costly if array is large
}
```

### 4. **Use `calldata` for function inputs**

```solidity
function update(string calldata name) external { ... }
```

---

## 🔁 Storage Optimization

- Access storage variables **once** per function
- Group frequently used storage variables
- Use **`mapping`** over arrays for lookups

---

## 🔧 Gas-Efficient Patterns

| Pattern               | Description                                |
|------------------------|--------------------------------------------|
| `unchecked {}`        | Skip overflow check (if safe)              |
| `immutable` variables | Set at deployment, cheaper than `constant` |
| `delete`              | Clears storage slot                        |
| `keccak256()`         | Cheaper than `sha3()`                      |

---

## 🧪 Measuring Gas

Use tools like:

- `hardhat-gas-reporter`
- `forge snapshot` (Foundry)
- Remix's gas estimation panel
- Tenderly gas profiler

---

## 🧠 Example: Before & After

### ❌ Inefficient
```solidity
uint256 result = 0;
for (uint i = 0; i < arr.length; i++) {
    result += arr[i];
}
```

### ✅ Optimized
```solidity
uint256 len = arr.length;
uint256 result = 0;
for (uint i = 0; i < len; i++) {
    result += arr[i];
}
```

---

## 📚 Resources

- [Solidity Gas Optimizations](https://0xmacro.com/blog/gas-optimization-cheat-sheet/)
- [Gas Golfing Techniques](https://mirror.xyz/blockchainbrown.eth/KpVk-8uhHbkCay6E)
- [Foundry Book - Gas Snapshots](https://book.getfoundry.sh/reference/forge/forge-snapshot.html)

---

✍️ Created by [@alkhatib99](https://github.com/alkhatib99)
