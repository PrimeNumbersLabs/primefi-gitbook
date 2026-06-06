---
description: >-
  PrimeFi's XRP money markets are live on testnet — Flare Coston2 and the XRPL
  EVM testnet. Connect, mint test tokens, and try supplying/borrowing today.
---

# XRP Testnet Markets

PrimeFi is bringing lending & borrowing to **XRP** through two Aave v3 markets that are **live now on testnet**:

| Market | Chain ID | Gas token | Oracle | Rewards |
| ------ | -------- | --------- | ------ | ------- |
| **Flare Coston2** | `114` | C2FLR | Flare FTSO | **rFLR** (live emissions) |
| **XRPL EVM Testnet** | `1449000` | XRP | Band Protocol | — |

Both are operated by **Prime Numbers Labs**, the same team behind PrimeFi v2. They let XRP holders put their XRP to work — supply it as collateral and borrow against it without selling.

{% hint style="info" %}
These markets are in **testnet phase**. Balances, rewards, and prices are test-only. Use the in-app faucet and the public gas faucets below to get test funds — no real value is at risk.
{% endhint %}

### These markets are "v3" in the app

The PrimeFi app header has a **v2 / v3** toggle. The XRP markets live under **v3** (the Aave v3 stack). Unlike the third-party [Fathom v3 (XDC)](../fathom-v3/README.md) market, **the XRP markets are PrimeFi's own** — we operate the pool, oracle and rewards.

### How they compare to PrimeFi v2

| Feature | PrimeFi v2 (Base / HyperEVM / XDC) | XRP markets (v3) |
| ------- | ---------------------------------- | ---------------- |
| Underlying protocol | PrimeFi (Aave v2 fork + omnichain layer) | PrimeFi (Aave v3 stack) |
| Core actions (supply / borrow / repay / withdraw) | Yes | Yes |
| E-Mode (correlated assets) | Yes | Yes — XRP-correlated category on Flare |
| External reward emissions | PRFI (where the chef is active) | **rFLR on Flare Coston2**; none on XRPL EVM yet |
| pLP boost / PRFI emissions / locked pLP | Yes | **No** (v3 has no pLP layer) |
| Prime Points / Flik / Prepaid Gas | Yes | No |
| Phase | Production | **Testnet** |

### How to open an XRP market

1. Open the [PrimeFi app](https://app.primefi.xyz/).
2. Click the **v3** pill in the top-right header.
3. Pick **Flare Coston2** or **XRPL EVM Testnet** from the market chooser — the app will prompt your wallet to switch (and add) the network.
4. Grab gas + test tokens (see [Testnet Faucets](../testnet-faucets/README.md)) and start supplying.

### Per-market guides

* [Flare Coston2](flare-coston2.md)
* [XRPL EVM Testnet](xrpl-evm-testnet.md)
