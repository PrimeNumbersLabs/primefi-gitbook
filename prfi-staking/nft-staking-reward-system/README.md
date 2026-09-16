# Staking Reward System

The live PRFI Staking Reward System lets users deposit PRFI tokens into NFTs and participate in reward mechanisms tied to each NFT's rarity and level. This token-in-NFT staking system is separate from the planned use of NFTs as lending collateral.

---

## Core Concept

Users stake PRFI tokens into their NFTs. The NFT acts as a staking vehicle whose reward weighting reflects:

- The **amount staked**
- The NFT's **rarity tier** (base multiplier)
- The NFT's **level** (added multiplier)

The published design uses monthly reward periods. Actual eligibility, timing, and claimable amounts follow the current app and on-chain configuration.

---

## Features

| Feature | Description |
| --- | --- |
| **Token-to-NFT Staking** | Deposit PRFI into NFTs to participate in rewards weighted by rarity and level. |
| **Level Progression** | NFTs progress through levels 1–20 as stake increases, boosting the added multiplier. |
| **Reward Accumulation** | Qualifying NFTs may accrue PRFI from currently funded reward sources under the active configuration. |
| **Omnichain Support** | NFTs can be bridged between Base and other supported chains via LayerZero. |
| **Merge System** | Combine two same-rarity NFTs into a higher-rarity NFT. |

---

## Planned PrimeFi profit sharing

A future component has been described as allocating 40% of PrimeFi lending-and-borrowing protocol profits to qualifying PRFI NFT participants. It is **planned and not documented here as active**. Before activation, PrimeFi must publish the precise profit definition, exclusions, period, eligibility, distribution contract, and verifiable on-chain configuration. No current entitlement, payout, APR, or yield is implied.

---

## Benefits

- **Active staking utility** - NFTs can be used to participate in the configured staking program.
- **Weighted participation** - Any available rewards are weighted by staking input, level, and rarity.
- **Inspectable contracts** - Deployed on-chain logic and configuration can be reviewed, subject to proxy, operator, and upgrade risk.
- **Upgradeable architecture** - Uses Diamond Standard / EIP-2535 components; upgradeability is an administrative trust boundary, not a security guarantee.

---

## Technical Architecture

The staking system is built on a **modular, upgradeable architecture (EIP-2535 Diamond Standard)** with cross-chain capabilities powered by LayerZero:

| Component | Purpose |
| --- | --- |
| `ERC721Facet` | NFT logic: minting, burning, bridging, metadata |
| `StakerFacet` | Staking engine: stake, merge, lock, rewards, claiming |
| `AdminFacet` | Configuration, pausing, access control |
| `GetterFacet` | Read-only data for frontend and integrations |
