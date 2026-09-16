---
description: How the v3 market family separates PrimeFi-operated XRP testnets from third-party Fathom on XDC.
---

# v3 Markets and Fathom on XDC

The PrimeFi app header has a **v2 / v3** switch. It selects a market family; **v3 is not the name of a single protocol or operator**.

### TL;DR

* **PrimeFi v2** markets on Base, HyperEVM and XDC are operated by **Prime Numbers Labs**.
* The **v3 market family** contains two different kinds of markets:
  * PrimeFi-operated XRP testnets on **Flare Coston2** and **XRPL EVM Testnet**.
  * **Fathom Lending** on XDC mainnet, a separate third-party Aave v3 deployment operated by **Fathom Protocol**.
* The selected market determines who operates the contracts and where users should request support. Do not infer the operator from the **v3** label alone.

{% hint style="warning" %}
**XDC has two separate markets in the PrimeFi interface:** PrimeFi v2 on XDC and third-party Fathom in the v3 family. A wallet connected to XDC could be viewing either one. Before supplying, borrowing or integrating, verify the selected version, market name and contract address.
{% endhint %}

### Operator and support boundary

| Selected market | Network and phase | Contract operator | Documentation and support |
| --- | --- | --- | --- |
| **PrimeFi v2** | Base, HyperEVM or XDC | Prime Numbers Labs | PrimeFi documentation and support |
| **XRP testnet markets (v3)** | Flare Coston2 or XRPL EVM Testnet | Prime Numbers Labs | [XRP Testnet Markets](../xrp-testnet-markets/README.md) and PrimeFi support |
| **Fathom Lending (v3)** | XDC mainnet | Fathom Protocol | Fathom documentation and support |

When **Fathom Lending** is selected, PrimeFi supplies the interface only. PrimeFi does not operate or custody the Fathom market contracts. Questions about Fathom supplies, borrows, collateral, liquidations, oracles, audits and transactions should go to Fathom.

### Fathom Lending official resources

| What you need | Where to go |
| --- | --- |
| **Lending docs** | [docs.fathom.fi/lending](https://docs.fathom.fi/lending/) |
| **XDC deployment and contracts** | [docs.fathom.fi/lending/deployments/xdc-network](https://docs.fathom.fi/lending/deployments/xdc-network) |
| **Supply, borrow, repay and withdraw guide** | [Fathom user guide](https://docs.fathom.fi/lending/user-guides/supply-borrow-repay-and-withdraw-asset) |
| **FXD stablecoin** | [docs.fathom.fi/fxd-stablecoin](https://docs.fathom.fi/fxd-stablecoin/) |
| **Fathom app** | [app.fathom.fi](https://app.fathom.fi/) |

### How to switch versions

Open the PrimeFi app and use the **v2 / v3** control in the header:

1. Select **v3**, then choose the intended market.
2. Approve the wallet prompt for the chain required by that market: XDC for Fathom, Flare Coston2 for that XRP testnet, or XRPL EVM Testnet for that XRP testnet.
3. Confirm the market name and reserves shown before transacting.

The interface hides PrimeFi-specific features that do not apply to the selected v3 market. If a user switches while on a v2-only page, the app may redirect to the Dashboard.

### Contract addresses

* **PrimeFi v2 contracts** are documented under [Smart Contracts Addresses](../smart-contracts-addresses/README.md).
* **PrimeFi-operated XRP testnet markets** are described under [XRP Testnet Markets](../xrp-testnet-markets/README.md).
* **Fathom on XDC contracts** are listed in the [Fathom XDC deployment page](../smart-contracts-addresses/fathom-xdc-deployment-addresses.md). Fathom's [deployment documentation](https://docs.fathom.fi/lending/deployments/xdc-network) is the canonical source.
