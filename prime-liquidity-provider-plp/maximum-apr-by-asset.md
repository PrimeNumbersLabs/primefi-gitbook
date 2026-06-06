# Maximum APR by asset

### Maximum APR by asset

<figure><img src="../.gitbook/assets/image (119).png" alt=""><figcaption></figcaption></figure>

On the Markets Page, users have the ability to assess the Maximum pLP Locking APR. Additionally, there is an asset breakdown modal that provides a detailed view of the APR for each specific asset.

<figure><img src="../.gitbook/assets/image (120).png" alt=""><figcaption></figcaption></figure>

#### Maximum Lock APR:

This is determined as the highest APR achievable when pLP is locked for a one-year period.

**Formula:**

`1-month lock APR * 1-year lock multiplier (25x)`

#### 1-Month Locking APR:

This represents the current APR for locking your pLP tokens for a one-month period.

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

PRFI emissions are **one protocol-wide budget**, not a separate budget per chain. The `rewardsPerSecond` rate lives on the **Base mainchain** `ChefIncentivesController`. Activity on the sidechains (HyperEVM, XDC) is synchronized back to Base over LayerZero through the [Omnichain Gas Deposit Mechanism](../primefi-features/omnichain-gas-deposit-mechanism-for-incentives-synchronization.md), so the mainchain holds the **single source of truth** and the budget is **never duplicated per chain**.

At the current rate this global budget is ≈ **0.1614 PRFI/sec (~13.9K PRFI/day)**, shared across every market on every chain.

#### 2. Each pool earns a share proportional to its allocation points

Every reward pool (each pToken on the supply side and each vdToken on the borrow side) has an **allocation point** (`allocPoint`). A pool's slice of the global budget is:

```
poolEmissionsPerSec = globalRewardsPerSec
                      × poolAllocPoint
                      ÷ TOTAL allocPoint across ALL pools on ALL chains
```

> **Important:** the denominator is the allocation total summed across **all** PrimeFi v2 chains (Base + HyperEVM + XDC), not just the chain you are currently viewing. Dividing by a single chain's local total would imply that chain alone distributes the entire 13.9K PRFI/day, over-counting the one global budget several times over and inflating every displayed APR.

By default each non-PRFI asset is given an **equal** allocation, so within a market the listed assets emit the same PRFI/day; the PRFI pool itself is given a deliberately small allocation. Allocation points are an on-chain governance parameter and can be re-weighted per asset at any time — the UI follows whatever is configured on-chain.

#### Your PRFI / day (personalized)

When a reward-eligible wallet is connected, the table adds a **Your PRFI / day** column: each pool's emissions multiplied by your live pro-rata share of that pool (`yourBalance ÷ poolTotalSupply`). Pools where you hold no position show `—`. Sub-cent USD values are rendered as `<$0.01` rather than `$0.00`.

Remember that these emissions only flow to wallets that maintain pLP eligibility (a locked pLP value ≥ 5% of deposits); see [Sustaining Eligibility Status](sustaining-eligibility-status.md).
