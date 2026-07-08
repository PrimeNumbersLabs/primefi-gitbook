---
description: Recent additions and improvements to the PrimeFi app.
---

# What's new

A roundup of the latest user-facing changes in the PrimeFi app.

### psXDC markets on Base and HyperEVM

**psXDC** — PrimeStaking's liquid-staking XDC token — can now be supplied and borrowed on the **Base** and **HyperEVM** v2 markets, in addition to XDC. psXDC moves between chains natively as a LayerZero OFT, so you can bridge it from XDC and use it as collateral (20% LTV) where you need liquidity. See [PrimeStakedXDC (psXDC)](liquid-staking-tokens/primestakedxdc-psxdc.md) for details and addresses.

### XRP money markets (testnet)

PrimeFi now has **XRP lending markets live on testnet** — Flare Coston2 and the XRPL EVM testnet — accessible from the app's **v3** toggle. Supply XRP (as FXRP on Flare, or native XRP on XRPL EVM) and borrow against it. See [XRP Testnet Markets](xrp-testnet-markets/README.md) and [Testnet Faucets](testnet-faucets/README.md).

### Self-serve testnet faucet

The XRP market screens now include a **Get test tokens** button. Connect, switch to the market's chain, and mint any reserve (or **Mint all**) in a click — each freshly minted token is offered to your wallet so it shows up right away. Details in [Testnet Faucets](testnet-faucets/README.md).

### Live on-chain reward APRs

Reward APRs on the v3 markets (e.g. **rFLR** on Flare Coston2) are now read **live from on-chain** incentive data, so the numbers in the markets table and asset pages reflect actual emission rates rather than estimates.

### Single-signature "Claim All" for PRFI NFTs

On the PRFI NFT staking screen, **Claim All** now batches every claimable NFT into a **single transaction** (via the Multicall3 aggregator) instead of one wallet prompt per NFT. Claimable amounts are also shown accurately.

### Personalized pLP emissions view

The pLP **Boost & Locks** tab now shows:

* a personalized **"Your PRFI / day"** column in the per-market emissions table, based on your actual position, and
* a **"Rewards earned to date"** lifetime card summarizing your cumulative PRFI.

These build on the corrected single-global-budget emissions model — see [Maximum APR by asset](prime-liquidity-provider-plp/maximum-apr-by-asset.md) and the [Boost & Locks tab](prime-liquidity-provider-plp/tabs/boost.md).

### Network-first onboarding

New users get a **network-first market chooser**: pick a network, and the app switches (and adds) the chain for you. The XRP testnet markets are surfaced by default during the testnet phase, and v3-specific surfaces are explained inline.
