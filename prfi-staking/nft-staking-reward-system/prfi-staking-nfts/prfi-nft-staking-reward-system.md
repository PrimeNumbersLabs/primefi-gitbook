# Reward System

The published PRFI NFT staking program identifies three potential reward sources. Eligibility and actual distributions follow the current contracts, program terms, and available funding; holding or staking an NFT does not guarantee rewards.

---

## Reward Sources

### 1. Published PRFI Reward Schedule

At the time of writing, the published token-allocation schedule dedicates 10 million PRFI to the NFT staking program and configures a 100,000 PRFI monthly pool. Treat these figures as a dated program snapshot, not a permanent emission promise; check the live app and on-chain configuration for the active rate, available pool, and eligibility.

### 2. NFT Royalties

At the time of writing, the published PrimePort terms allocate 50% of a 10% secondary-sale royalty to qualifying NFT participants (equivalent to 5% of an eligible sale price). Marketplace terms, eligible sales, and distribution rules can change and should be verified against the live marketplace and contracts.

### 3. Planned PrimeFi profit sharing

A future component has been described as allocating 40% of PrimeFi lending-and-borrowing protocol profits to qualifying PRFI NFT participants.

This component is **planned and not documented as an active on-chain reward source**. Before activation, PrimeFi must publish the profit definition, exclusions, period, eligibility, distribution contract, and verifiable configuration. It creates no current entitlement or guaranteed yield.

{% hint style="info" %}
If profit sharing is activated in the future, its eligibility rules will be published separately. The live staking flow is also separate from the planned use of NFTs as lending collateral.
{% endhint %}

---

## Reward Distribution Formula

The published formula splits the configured PRFI pool for a reward period into two equal portions. Let `P` be the PRFI amount actually available for that period.

### Part 1 - Based on Total Multiplier (50%)

Each NFT's share is proportional to its total multiplier relative to the sum of all multipliers:

$$
R_{1,i} = \frac{Tx_i}{T_{total}} \times \frac{P}{2}
$$

Where:
- `Tx_i` = Total multiplier of NFT *i* (rarity + level)
- `T_total` = Sum of all NFTs' total multipliers

### Part 2 - Based on Multiplier x Stake (50%)

Each NFT's share also accounts for how much PRFI is staked:

$$
R_{2,i} = \frac{Tx_i \times t_i}{P_{total}} \times \frac{P}{2}
$$

Where:
- `t_i` = PRFI tokens staked in NFT *i*
- `P_total` = Sum of (multiplier x stake) across all NFTs

### Total Reward

$$
R_i = R_{1,i} + R_{2,i}
$$

Any separately funded royalty reward or future profit-sharing component requires its own active configuration and published terms; do not assume it is included in `P` or follows this formula.

---

## Summary

This dual approach is designed to balance reward distribution:

- **Part 1** rewards NFT quality (rarity and level).
- **Part 2** rewards staking commitment (multiplier x stake).

Both factors affect relative weighting. They do not guarantee a particular reward amount.
