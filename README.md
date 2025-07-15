<h1 align="center">
  🔁 Solana Volume BOT
</h1>
<p align="center">
  <b>A stealth volume simulator for the Raydium DEX powered by the Solana blockchain</b><br>
  <i>Distribute, swap, and simulate real-time activity across hundreds of wallets — fully automated.</i>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Solana-Compatible-00ffcc?style=for-the-badge&logo=solana&logoColor=000000" />
  <img src="https://img.shields.io/badge/Jupiter-V6-blueviolet?style=for-the-badge&logo=swap" />
  <img src="https://img.shields.io/badge/Volume%20Bot-v2.0-orange?style=for-the-badge" />
</p>

---

## ⚠️ Previous Version Drawbacks

- 🔁 **Repetitive Wallet Use**  
  Recycled wallets made bot activity obvious on DEX trackers like DexScreener.

- 🧍‍♂️ **No Maker Footprint Growth**  
  Simulated volume didn’t reflect a rise in pool participants.

- 💰 **Token Stashing Without Sell-off**  
  Tokens weren’t liquidated before collection, resulting in locked liquidity.

- ⚖️ **Buy-Sell Symmetry = Sell Pressure**  
  Equal buying/selling led to lingering sell pressure.

---

## 🚀 What's New

- 🔄 **Fresh Wallet Generation**  
  After each volume cycle, SOL is sent to a brand-new wallet.

- 📈 **Increased Maker Count**  
  Each transaction is done from a different wallet, boosting perceived activity.

- 💸 **Auto Token Sell Before Fund Gathering**  
  Leftover tokens are sold for SOL, and the rent is reclaimed.

- 🟢 **Asymmetric Volume (More Buys)**  
  Two randomized buys followed by a delayed sell simulate bullish demand.

---

## ⚙️ Features Overview

- ✅ Multi-wallet SOL Distribution  
- ✅ Configurable Buy/Sell Frequency and Timing  
- ✅ Integrated with **Jupiter V6** Aggregator for optimal swap routing  
- ✅ Real-time parallelized execution (up to 20 wallets at once)  
- ✅ Clean gather command to sweep funds post-operation

---

## 📁 Environment Variables

Rename `.env.copy` to `.env` and fill out the following:

```env
PRIVATE_KEY=                 # Main wallet private key
RPC_ENDPOINT=                # Solana RPC URL
RPC_WEBSOCKET_ENDPOINT=      # Solana WebSocket URL

# === Buy Settings ===
DISTRIBUTE_INTERVAL_MAX=50
DISTRIBUTE_INTERVAL_MIN=30

BUY_UPPER_PERCENT=50         # Max % of SOL used to buy
BUY_LOWER_PERCENT=30         # Min % of SOL used to buy

BUY_INTERVAL_MAX=10          # Max wait (seconds) between buys
BUY_INTERVAL_MIN=0           # Min wait (seconds) between buys

SELL_INTERVAL_MAX=10         # Max wait before selling
SELL_INTERVAL_MIN=0          # Min wait before selling

DISTRIBUTE_WALLET_NUM=2      # Number of concurrent wallets (Max: 20)
SOL_AMOUNT_TO_DISTRIBUTE=0.001

SLIPPAGE=50                  # Slippage tolerance in percent

TOKEN_MINT=7MFX5LySd9CdaD8irWnLLKanpDw6gxbBuhEg3qCHWc4C   # Token to trade

# === Optional JITO Mode ===
JITO_MODE=false
JITO_FEE=0.0001
