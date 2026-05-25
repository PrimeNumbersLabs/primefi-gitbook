---
description: What the v3 toggle in the PrimeFi app actually is, and where to get support.
---

# Fathom v3 (XDC)

The PrimeFi app header has a **v2 / v3** toggle. This page explains what **v3** means.

### TL;DR

* **v2 = PrimeFi.** Operated by Prime Numbers Labs on Base, HyperEVM and XDC. This is the protocol the rest of this documentation describes.
* **v3 = Fathom Lending.** A separate, third-party Aave v3 fork operated by **Fathom Protocol** on the XDC network. PrimeFi surfaces it inside our app as a convenience so users can access both markets from one interface, but **PrimeFi does not operate, custody or take responsibility for the v3 contracts**.

{% hint style="info" %}
For anything related to Fathom v3 (supply, borrow, collateral, health factor, liquidations, oracle questions, contract addresses, audits, support tickets), please use the official **Fathom Lending** documentation and support channels — not PrimeFi's.
{% endhint %}

### Fathom Lending — official resources

| What you need                        | Where to go                                                                                                                                            |
| ------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Lending docs (root)**              | [docs.fathom.fi/lending](https://docs.fathom.fi/lending/)                                                                                              |
| **XDC deployment & contract list**   | [docs.fathom.fi/lending/deployments/xdc-network](https://docs.fathom.fi/lending/deployments/xdc-network)                                               |
| **How to supply / borrow / repay**   | [docs.fathom.fi/lending/user-guides/supply-borrow-repay-and-withdraw-asset](https://docs.fathom.fi/lending/user-guides/supply-borrow-repay-and-withdraw-asset) |
| **FXD stablecoin (related product)** | [docs.fathom.fi/fxd-stablecoin](https://docs.fathom.fi/fxd-stablecoin/)                                                                                |
| **Fathom dApp**                      | [app.fathom.fi](https://app.fathom.fi/)                                                                                                                |

### What's different between v2 and v3 inside the PrimeFi UI

| Feature                                | PrimeFi (v2)                                | Fathom (v3)                                                                            |
| -------------------------------------- | ------------------------------------------- | -------------------------------------------------------------------------------------- |
| Chains                                 | Base, HyperEVM, XDC                         | XDC only                                                                               |
| Underlying protocol                    | PrimeFi (Aave v2 fork + omnichain layer)    | Fathom Lending (Aave v3 fork)                                                          |
| Reserves                               | USDC, USDT, ETH, HYPE, WBTC, XDC, PSXDC, PRFI etc. | FXD, FTHM, WXDC and other Fathom reserves                                              |
| pLP boost / PRFI emissions             | Yes (where chef is active — currently Base) | **No** — Fathom has its own incentive model                                            |
| Cross-chain borrow (Stargate)          | Yes                                         | No                                                                                     |
| Auto-compound / vesting / locked pLP   | Yes                                         | No                                                                                     |
| Prime Points eligibility               | Yes                                         | No                                                                                     |
| Smart contract operator                | Prime Numbers Labs                          | Fathom Protocol                                                                        |
| Audits                                 | See [Audits](../audits.md)                  | Halborn Formal Verification (March 2026) — see Fathom docs                             |

### How to switch versions

Open the PrimeFi app, look at the header on the top right, and click the **v2 / v3** pill. The app will:

1. Update the active market and reserves list.
2. Switch your wallet to the appropriate chain (XDC for v3).
3. Hide PrimeFi-specific surfaces that don't apply to Fathom (pLP tabs, Prime Points, Flik, Prepaid Gas).

If you're on a PrimeFi-only page like `/plp` or `/prime-points` when you toggle to v3, the app will bounce you to the Dashboard.

### Contract addresses

* **PrimeFi v2 contracts** are documented under [Smart Contracts Addresses](../smart-contracts-addresses/README.md).
* **Fathom v3 contracts** are listed in the [Fathom XDC deployment doc](../smart-contracts-addresses/fathom-xdc-deployment-addresses.md), with the canonical source being [Fathom's own deployment page](https://docs.fathom.fi/lending/deployments/xdc-network).
