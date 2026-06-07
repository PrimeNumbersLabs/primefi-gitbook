---
description: PrimeFi's XRP money market on the XRPL EVM Sidechain testnet (chain 1449000).
---

# XRPL EVM Testnet

The XRPL EVM market is PrimeFi's XRP lending market on the **XRPL EVM Sidechain testnet** (chain `1449000`). The XRPL EVM Sidechain is an EVM-compatible chain where **XRP is the native gas token**, bridged 1:1 from the XRP Ledger. You supply XRP directly as collateral and borrow against it.

| | |
| - | - |
| **Chain ID** | `1449000` |
| **Gas token** | XRP |
| **Oracle** | **Band Protocol** |
| **Stack** | PrimeFi v3 (Aave v3) |
| **Explorer** | [explorer.testnet.xrplevm.org](https://explorer.testnet.xrplevm.org) |

### Reserves

* **XRP / WXRP** — native XRP (and its wrapped form) — your primary collateral
* **USDC** — mintable test mock
* **USDT** — mintable test mock
* **RLUSD** (Ripple USD), priced live by Band Protocol — mintable test mock
* **WBTC** — mintable test mock
* **WETH** — mintable test mock

The non-native reserves are mintable test mocks dispensed by the in-app **Get test tokens** button. WXRP is obtained by wrapping the native XRP you receive from the gas faucet.

### Get started

1. Switch to **v3 → XRPL EVM Testnet** in the app (see the [section overview](README.md)).
2. Claim test **XRP** for gas from the [XRPL EVM faucet](https://faucet.xrplevm.org/) (up to 90 XRP).
3. (Optional) Bridge test XRP from the XRPL testnet via [Squid testnet](https://testnet.xrpl.squidrouter.com/).
4. Mint USDC/USDT/RLUSD/WBTC/WETH with the in-app **Get test tokens** button.
5. Supply XRP (or any reserve) and borrow against it.

Full faucet walkthrough: [Testnet Faucets → XRPL EVM Testnet](../testnet-faucets/xrpl-evm-testnet.md).
