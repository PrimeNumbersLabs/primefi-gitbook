---
description: Welcome to PrimeFi, the omnichain lending and borrowing DeFi protocol.
---

# Introducing PrimeFi

{% hint style="success" %}
**Current market status (16 September 2026): PrimeFi v2 markets on HyperEVM, Base, and XDC are operational.** See [Market Status](security/market-status.md).
{% endhint %}

PrimeFi is an omnichain platform designed to streamline borrowing and lending across supported networks. LayerZero messaging supports cross-chain workflows, but smart contracts, oracles, liquidity, cross-chain messaging, and operational controls all involve risk.

Prime Numbers Labs operates PrimeFi v2 markets on HyperEVM, Base, and XDC.

### Why PrimeFi?

| Advantage                   | What it means for you                                                                                                 |
| --------------------------- | --------------------------------------------------------------------------------------------------------------------- |
| **True Omnichain**          | Operates natively on Base, HyperEVM and XDC, with more chains coming soon.                                            |
| **Deposit ≠ Loan**          | Use your collateral where you hold it and receive liquidity where you need it.                                        |
| **Security Practices**      | Point-in-time smart-contract reviews and LayerZero messaging are part of the protocol's security approach; they do not eliminate protocol or cross-chain risk. |
| **Configured Incentives**   | Eligible positions may receive PRFI emissions only where the relevant pool is enabled and funded. Liquidators receive the selected reserve's configured collateral bonus, not an automatic PRFI payment. |
| **PRFI NFT Staking**        | Qualifying users can stake PRFI inside NFTs on Base and participate in currently funded staking rewards under the active rules. See [PRFI NFTs](prfi-staking/nft-staking-reward-system/prfi-staking-nfts/README.md). |
| **Prime Numbers Ecosystem** | Integrations with PrimeStaking and PrimePort provide additional staking, liquidity, and NFT workflows.                |

### Two protocol versions in the app

Inside the PrimeFi app you'll see a **v2 / v3** toggle in the header:

* **v2 — PrimeFi** (Base, HyperEVM, XDC). Prime Numbers Labs operates these Aave v2-based markets. pLP boosts, PRFI emissions and cross-chain delivery are available only where enabled and funded.
* **v3 — Aave v3 market family.** This selector includes both **PrimeFi-operated XRP testnets** (Flare Coston2 and XRPL EVM) and **Fathom Lending on XDC mainnet**, a third-party market operated by Fathom Protocol. The responsible operator, contracts, incentives, and support channel depend on the selected market.

See [XRP Testnet Markets](xrp-testnet-markets/README.md) for PrimeFi-operated testnets and [Fathom v3 (XDC)](fathom-v3/README.md) for the third-party Fathom market.

{% hint style="warning" %}
On XDC, PrimeFi v2 and Fathom v3 use different contracts despite sharing chain ID `50`. Confirm the selected market and operator before signing a transaction.
{% endhint %}
