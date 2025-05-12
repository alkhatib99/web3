# Solana Sniping Bot

This bot automates the purchase of new Solana tokens for early entry access.

\nStarting by completing the Token Sniper module, this project will:
\n- monitor SOL events (via Raydium, Mint)
- execute transactions with priority and slippage settings
\n\nFolder structure includes:\n- src/tokens/monitor.py  - Raydium/pool tracker logic
- src/tokens/executor.py - Transaction execution\n- src/utils/             - logging, RPC helpers\n- config/               - wallet, rpc urls, slippage settings\n- roadmap.md - Roadmap for the Token Sniper project
\n\nThis is the first step in the web3/project.
\nSoon to be extended with NFT Sniping.