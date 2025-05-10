# Yield Farming in DeFi

**Yield farming** is a strategy in decentralized finance (DeFi) where users earn rewards by providing liquidity to protocols. It's a core component of DeFi that enables capital efficiency and passive income.

---

## 🌾 What is Yield Farming?

- Users deposit tokens into liquidity pools or lending protocols.
- In return, they receive rewards in the form of interest, fees, or governance tokens.
- Often involves staking LP (Liquidity Provider) tokens to earn additional yield.

---

## 🧱 Common Yield Sources

| Source              | Description                                      |
|---------------------|--------------------------------------------------|
| Trading fees        | Earn a portion of fees on AMMs like Uniswap     |
| Incentive rewards   | Native tokens from protocol (e.g. SUSHI, CRV)   |
| Lending interest    | Earn interest on lent assets (e.g. Aave, Compound) |
| Staking derivatives | Earn on staked assets (e.g. stETH, rETH)        |

---

## 🔄 Yield Farming Flow

1. Provide liquidity to a DEX (e.g., ETH/USDC on Uniswap)
2. Receive LP tokens representing your share
3. Stake LP tokens in a farming contract (e.g., MasterChef)
4. Earn rewards in native tokens (e.g., CAKE, UNI)

---

## 🔧 Example: Yield Farm Contract Snippet

```solidity
function deposit(uint256 _amount) public {
    userInfo[msg.sender].amount += _amount;
    rewardDebt[msg.sender] = calculateRewards(msg.sender);
}
```

---

## ⚠️ Risks of Yield Farming

- **Impermanent loss**: Losses due to token price divergence in LP pools
- **Smart contract risk**: Bugs or exploits in farming contracts
- **Rug pulls**: Malicious developers withdraw all funds
- **High gas fees**: Especially on Ethereum mainnet

---

## 🛡 Best Practices

- Start with audited, reputable protocols
- Understand how rewards are generated
- Track your ROI vs. gas costs
- Consider using aggregators (e.g., Yearn, Beefy) for easier farming

---

## 🧰 Tools for Yield Farmers

- [Zapper.fi](https://zapper.fi/)
- [DeFiLlama](https://defillama.com/yields)
- [Yearn.finance](https://yearn.finance/)
- [Beefy Finance](https://app.beefy.finance/)

---

✍️ Created by [@alkhatib99](https://github.com/alkhatib99)
