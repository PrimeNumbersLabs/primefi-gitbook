---
description: PrimeFi's XRP money market on the Flare Coston2 testnet (chain 114).
---

# Flare Coston2

The Flare Coston2 market is PrimeFi's XRP lending market running on Flare's **Coston2 testnet** (chain `114`). XRP enters the Flare ecosystem as **FXRP** (FAssets-minted XRP), which you supply as collateral to borrow against — without selling your XRP.

| | |
| - | - |
| **Chain ID** | `114` |
| **Gas token** | C2FLR (Coston2 Flare) |
| **Oracle** | Flare **FTSO** (native price feeds) |
| **Rewards** | **rFLR** emissions via the Aave v3 RewardsController |
| **Stack** | PrimeFi v3 (Aave v3) |
| **Explorer** | [coston2.testnet.flarescan.com](https://coston2.testnet.flarescan.com) |

### Reserves

All non-native reserves are mintable test mocks dispensed by the in-app **Get test tokens** button:

* **FXRP** — testnet stand-in for FAssets-minted XRP (your primary collateral)
* **RLUSD** — Ripple USD stablecoin
* **stXRP** — staked-XRP representation
* **FBTC** — wrapped BTC variant
* **USDT0** — USD₮0 stablecoin
* **WBTC**
* **WETH**

{% hint style="info" %}
On **mainnet**, FXRP is minted from real XRP via Flare **FAssets** — see [How FXRP works](https://dev.flare.network/fassets/overview). On Coston2 it's a mintable mock you get from the in-app faucet.
{% endhint %}

### Rewards (rFLR)

Supplying and borrowing on Coston2 earns **rFLR**, streamed by the Aave v3 RewardsController. The app reads the live emission rate from the on-chain incentive data provider, so the reward APRs you see in the markets table and asset pages are **live on-chain values**, not estimates.

### E-Mode

The market ships an **XRP-correlated E-Mode category** so XRP-pegged assets can be used together at higher capital efficiency (higher LTV / liquidation threshold) when borrowing within the correlated group.

### Get started

1. Switch to **v3 → Flare Coston2** in the app (see the [section overview](README.md)).
2. Claim **C2FLR** for gas from the [Coston2 faucet](https://faucet.flare.network/coston2).
3. Mint reserves with the in-app **Get test tokens** button.
4. Supply FXRP (or any reserve) and borrow against it.

Full faucet walkthrough: [Testnet Faucets → Flare Coston2](../testnet-faucets/flare-coston2.md).
