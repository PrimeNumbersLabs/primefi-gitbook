---
description: Recent additions and improvements to the PrimeFi app.
---

# What's new

A roundup of the latest user-facing changes in the PrimeFi app.

{% hint style="success" %}
**Market status — 16 September 2026:** PrimeFi v2 markets on HyperEVM, Base, and XDC are operational. Read [Market Status](security/market-status.md) before interacting with a market.
{% endhint %}

### psXDC markets on Base and HyperEVM

**psXDC** — PrimeStaking's liquid-staking XDC token — is configured as a reserve on the **Base** and **HyperEVM** v2 markets, in addition to XDC. It moves between chains as a LayerZero OFT and is configured with 20% LTV on Base and HyperEVM. See [PrimeStakedXDC (psXDC)](liquid-staking-tokens/primestakedxdc-psxdc.md) for current mechanics, risks, and addresses.

### Single-signature "Claim All" for PRFI NFTs

On the PRFI NFT staking screen, **Claim All** now batches every claimable NFT into a **single transaction** (via the Multicall3 aggregator) instead of one wallet prompt per NFT. Claimable amounts are also shown accurately.

### Personalized pLP emissions view

The pLP **Boost & Locks** tab now shows:

* a personalized **"Your PRFI / day"** column in the per-market emissions table, based on your actual position, and
* a **"Rewards earned to date"** lifetime card summarizing your cumulative PRFI.

These build on the corrected single-global-budget emissions model — see [Maximum APR by asset](prime-liquidity-provider-plp/maximum-apr-by-asset.md) and the [Boost & Locks tab](prime-liquidity-provider-plp/tabs/boost.md).

### Network-first onboarding

New users get a **network-first market chooser**: pick a network, and the app switches (and adds) the chain for you.
