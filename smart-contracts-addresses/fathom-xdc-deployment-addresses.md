---
description: Fathom Lending (Aave v3) contract addresses on XDC mainnet — used by the v3 toggle in the PrimeFi UI.
---

# Fathom v3 (XDC) Deployment Addresses

The PrimeFi app's **v3** toggle routes calls to **Fathom Lending**, an Aave v3 fork **operated by Fathom Protocol** on XDC mainnet (chain id `50`). **PrimeFi does not operate, own, or audit these contracts.**

{% hint style="warning" %}
The canonical, always-up-to-date source for Fathom Lending addresses is Fathom's own documentation. Always cross-check before integrating: [docs.fathom.fi/lending/deployments/xdc-network](https://docs.fathom.fi/lending/deployments/xdc-network).
{% endhint %}

### Audit

* Provider: **Halborn**
* Type: Formal Verification
* Date: March 2026
* Outcome: **0 Critical / 0 High / 0 Medium / 6 Informational**
* Audited commit: `91574f41` · Remediation commit: `5072265`

### Addresses the PrimeFi UI calls on XDC mainnet

These are the entry-point contracts the PrimeFi frontend wires up for the v3 toggle. The reserve list itself is discovered at runtime by calling `Pool.getReservesList()`.

#### Core

| Contract                  | Address                                      |
| ------------------------- | -------------------------------------------- |
| **Pool**                  | `0x70d8005E3c8C7e383FE35Fa40156042F3393449F` |
| **Pool implementation**   | `0x5c756ACD4Cb26a9cA6De7abF9765cE84B5Be9322` |
| **PoolAddressesProvider** | `0x37ab83e6a9B99DA3eAF00D1afdC45f50ee7625E5` |
| **PoolConfigurator**      | `0x56f3A75C71C207a77c3b8c77a34FC89cF1a6DB66` |
| **ACLManager**            | `0xf73e7d6309A2DaDE5B698eD33dA929d2F2281526` |
| **WrappedTokenGateway**   | `0x57Ba8bAA7c3Ff6606751859f1CED9f68819C2f41` |

#### Oracles & data providers

| Contract                  | Address                                      |
| ------------------------- | -------------------------------------------- |
| **FathomOracle**          | `0x54348d953Abc4f167cbdeDe648095c1aF7DE355A` |
| **UiPoolDataProvider**    | `0x5f7001B6Dc957dC5B2F78f0BC3aFbFc1fE628A18` |
| **ProtocolDataProvider**  | `0x7fa488a5C88E9E35B0B86127Ec76B0c1F0933191` |
| **WalletBalanceProvider** | `0x7C724DEaD5012Eb4C9e2d1529cF0353e767C82Cd` |

#### Reference tokens (for orientation only — full list is on-chain)

| Symbol   | Address                                      |
| -------- | -------------------------------------------- |
| **FXD**  | `0x49d3f7543335cf38Fa10889CCFF10207e22110B5` |
| **FTHM** | `0x3279dBEfABF3C6ac29d7ff24A6c46645f3F4403c` |
| **WXDC** | `0x951857744785E80e2De051c32EE7b25f9c458C42` |

### Where PrimeFi-specific contracts apply

PrimeFi's pLP boost, MultiFeeDistribution, ChefIncentivesController, Compounder, Flik and Stargate Borrow contracts **do not exist on Fathom**. The v3 surface inside the PrimeFi UI deliberately hides those features because they have no on-chain counterpart in Fathom's deployment.

For incentive details on Fathom, refer to Fathom's documentation: [docs.fathom.fi/lending](https://docs.fathom.fi/lending/).
