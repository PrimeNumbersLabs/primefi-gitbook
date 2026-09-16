# pLP Pools

PrimeFi supports two liquidity-pool types per network. Only one of them is eligible for **pLP** rewards.

### Pool types

* **v2 pool (eligible for pLP):**\
  This is the pool used by pLP. Create your position with **Flik** or add liquidity manually. pLP emissions are distributed **only** to v2 LP tokens.
* **DEX v3 / v4 pools (concentrated liquidity; unrelated to the PrimeFi app's v2/v3 market selector):**\
  For active LPs who want custom price ranges. These positions **do not** qualify for pLP emissions and earn **swap fees only**.

> Always verify pool addresses **inside the PrimeFi app** before adding liquidity.

***

### Mainnet pools (live)

External DEX pools can remain live independently of PrimeFi lending-market status. A PrimeFi pause may still disable Flik, borrowing, or other protocol-assisted pLP workflows. Check [Market Status](../security/market-status.md) before using those features.

#### Base

* **PRFI-ETH v2 (Flik pool, pLP-eligible)**\
  Uniswap: [https://app.uniswap.org/explore/pools/base/0x87b417af600312df37f551a05ae14bcc3d55bc36](https://app.uniswap.org/explore/pools/base/0x87b417af600312df37f551a05ae14bcc3d55bc36)\
  Dexscreener: [https://dexscreener.com/base/0x87b417af600312df37f551a05ae14bcc3d55bc36](https://dexscreener.com/base/0x87b417af600312df37f551a05ae14bcc3d55bc36)

#### HyperEVM

* **PRFI-WHYPE configured pLP staking token (pLP-eligible):** `0x981F145a71Da6DF4A7cBe892807782c9CC9a5515`\
  [HyperEVMScan](https://hyperevmscan.io/address/0x981F145a71Da6DF4A7cBe892807782c9CC9a5515)\
  [Dexscreener](https://dexscreener.com/hyperevm/0x981f145a71da6df4a7cbe892807782c9cc9a5515)

The concentrated PrjX pool at `0xfae262d0384b3e1c58abe28ce8ac5678af874354` is **not** the configured pLP staking token and does not qualify for pLP emissions.

#### **XDC Network**

* PRFI-WXDC v2 Xswap (pLP-eligible)\
  Geckoterminal: [https://www.geckoterminal.com/es/xdc/pools/0xffa04f091128fb89d3b1ecd0149dc677dfae1c69](https://www.geckoterminal.com/es/xdc/pools/0xffa04f091128fb89d3b1ecd0149dc677dfae1c69)

***

### Notes & risk

* **pLP rewards apply only to the v2 pool** on each network.
* Concentrated LP (v3/v4) requires **range management** and is subject to **impermanent loss**.
* Additional networks (e.g., Ethereum, Arbitrum, BNB Chain) may be added in future releases; official pool links will be published before going live.
