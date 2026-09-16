# Technical Overview

The PRFI NFT staking system uses an upgradeable Diamond Standard (EIP-2535) architecture with LayerZero-related components. Deployed facets, supported chains, peers, permissions, and reward parameters can change through authorized administration and must be verified on-chain.

## Architecture

The published design organizes functionality into facets behind a Diamond proxy:

| Facet | Intended responsibility |
| --- | --- |
| `ERC721Facet` | NFT ownership, minting, burning, metadata, and configured cross-chain functions |
| `StakerFacet` | PRFI staking, locks, levels, merging, reward accounting, and claims |
| `AdminFacet` | Authorized configuration, pause, and access-control functions |
| `GetterFacet` | Read-only state used by interfaces and integrations |

The exact deployed facet addresses and selectors are the authoritative source for available functions. Upgradeability creates administrator and implementation risk.

## Staking and weighting

Where enabled, a user can stake PRFI through an NFT. The published weighting model can use:

* the amount of PRFI staked;
* the NFT's configured rarity multiplier; and
* its configured level or added multiplier.

Any reward pool, period, split formula, threshold, multiplier, or eligibility rule is configuration-dependent. See [Reward System](../../../prfi-staking/nft-staking-reward-system/prfi-staking-nfts/prfi-nft-staking-reward-system.md) for the currently documented model and verify live state before calculating rewards.

Staking or meeting a published threshold does not guarantee a distribution, APR, or market value.

## Cross-chain functionality

The architecture contains LayerZero-based cross-chain components. Cross-chain NFT transfer or remote actions are available only for configured and trusted peers on supported networks.

Do not assume that:

* every staking or claim action is available from every chain;
* metadata or reward state is synchronously replicated;
* a submitted message has completed successfully; or
* LayerZero delivery removes endpoint, peer, configuration, or execution risk.

Verify the selected chain, destination, peer configuration, fees, and resulting ownership/state after any cross-chain action.

## Withdrawals, redemption, and merging

The published system includes partial withdrawal, burn-to-redeem, and same-rarity merge concepts. Fees, lock restrictions, thresholds, reserved IDs, and resulting multipliers are governed by the deployed facets and current configuration.

Values such as a 20% withdrawal fee, level 20 maximum, or the `41,490 PRFI` threshold are dated program parameters—not immutable properties. Confirm them in the current app and on-chain before acting.

## Reward funding

Live rewards require tokens to be funded and notified to the responsible distribution contracts. A planned PrimeFi profit-sharing concept is not an active reward source unless a specific activation notice, revenue definition, distribution contract, and verifiable on-chain configuration are published.

## Security and trust assumptions

| Control or property | Scope and limitation |
| --- | --- |
| **Diamond architecture** | Allows facet replacement or extension; authorized upgrades can change behavior. |
| **Reentrancy controls** | Can reduce specific callback risks but do not prevent every reentrancy or integration vulnerability. |
| **Pause controls** | Authorized roles may restrict functions during emergencies; pause powers also create operational and key-management risk. |
| **Trusted peers** | Restrict accepted cross-chain counterparts when correctly configured; incorrect configuration remains a risk. |
| **On-chain state** | Contract state and events can be inspected, but interpretation depends on implementation, proxy, configuration, and external dependencies. |

Audits and inherited libraries are point-in-time inputs, not guarantees. Verify the active Diamond, facets, owner/admin roles, peers, and parameters before integrating.
