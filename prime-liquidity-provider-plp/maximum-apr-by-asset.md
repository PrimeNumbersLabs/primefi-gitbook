# Maximum APR by asset

### Maximum APR by asset

<figure><img src="../.gitbook/assets/image (119).png" alt=""><figcaption></figcaption></figure>

On the Markets Page, users have the ability to assess the Maximum pLP Locking APR. Additionally, there is an asset breakdown modal that provides a detailed view of the APR for each specific asset.

<figure><img src="../.gitbook/assets/image (120).png" alt=""><figcaption></figcaption></figure>

{% hint style="warning" %}
Displayed APRs, emission rates, and lock multipliers are variable estimates, not guaranteed yield. Check the live [PrimeFi app](https://app.primefi.xyz/) and the current on-chain configuration before relying on a value.
{% endhint %}

#### Maximum Lock APR:

This is the interface's estimated maximum APR for a one-year pLP lock under the displayed assumptions.

**Formula:**

`1-month lock APR * 1-year lock multiplier (25x)`

#### 1-Month Locking APR:

This represents the interface's current estimated APR for locking pLP tokens for one month.

**Formula:**

`(Total 1 Month Lockers’ Share of Annualized Protocol Fees) / (Total 1 Month Lockers’ Share of pLP Pool Size)`

#### 1 Month Locker Share of Protocol Fees:

**Formula:**

`(1 Month Locker Share of Protocol Power) / (Total Protocol Locking Power)`

#### Total Protocol Locking Power:

This is the sum of all lockers’ shares, each adjusted by its respective multiplier.

```
= (1 Month Lockers' Share of pLP Pool Size * 1 Month Locker Multiplier (1x)) 
+ (3 Month Lockers’ Share of pLP Pool Size * 3 Month Locker Multiplier (4x))
+ (6 Month Lockers’ Share of pLP Pool Size * 6 Month Lockers’ Multiplier (10x))
+ (12 Month Lockers' Share of pLP Pool Size * 12 Month Locker Multiplier (25x))
```

***

### Per-market PRFI emissions (how the table is built)

The pLP page shows a **Per-market emissions** table that breaks the protocol's PRFI emissions down per asset. Two facts are important for reading it correctly:

#### 1. There is a single, global emission budget

The published architecture uses **one Base mainchain emission source**, not an independently configured full budget for each chain. The `rewardsPerSecond` rate lives on the Base `ChefIncentivesController`. Sidechain activity can be synchronized back to Base over LayerZero through the [Omnichain Gas Deposit Mechanism](../primefi-features/omnichain-gas-deposit-mechanism-for-incentives-synchronization.md). Correct cross-chain accounting still depends on successful message delivery, configuration, and reconciliation; users should verify actual on-chain allocations and accrued rewards.

The global rate is configurable and changes over time. Use the live pLP interface and the Base mainchain `ChefIncentivesController.rewardsPerSecond` on-chain value rather than a hard-coded documentation snapshot.

#### 2. Each pool earns a share proportional to its allocation points

Every reward pool (each pToken on the supply side and each vdToken on the borrow side) has an **allocation point** (`allocPoint`). A pool's slice of the global budget is:

```
poolEmissionsPerSec = globalRewardsPerSec
                      × poolAllocPoint
                      ÷ TOTAL allocPoint across ALL pools on ALL chains
```

> **Important:** the denominator is the allocation total summed across **all** PrimeFi v2 chains (Base + HyperEVM + XDC), not just the chain you are currently viewing. Dividing by a single chain's local total would assign the full global budget to each chain, over-counting emissions and inflating every displayed APR.

By default each non-PRFI asset is given an **equal** allocation, so within a market the listed assets emit the same PRFI/day; the PRFI pool itself is given a deliberately small allocation. Allocation points are an on-chain governance parameter and can be re-weighted per asset at any time — the UI follows whatever is configured on-chain.

#### Your PRFI / day (personalized)

When a reward-eligible wallet is connected, the table adds a **Your PRFI / day** column: each pool's emissions multiplied by your live pro-rata share of that pool (`yourBalance ÷ poolTotalSupply`). Pools where you hold no position show `—`. Sub-cent USD values are rendered as `<$0.01` rather than `$0.00`.

These emissions only flow to wallets that satisfy the currently configured pLP eligibility ratio. It was 5% at the time of writing but is adjustable; see [Sustaining Eligibility Status](sustaining-eligibility-status.md) and verify the live value.
