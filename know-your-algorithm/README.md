---
description: PrimeFi Lending & Rewards Mechanics
---

# Know Your Algorithm

### Introduction

PrimeFi is a decentralized finance platform for lending and over-collateralized borrowing with additional reward incentives. Its core money-market architecture explicitly inherits and adapts **Aave v2 concepts**, including the `LendingPool`, reserve indexes, interest-bearing deposit tokens, variable debt tokens, health-factor validation, and liquidation flow. PrimeFi's deployments, configuration, oracle integrations, cross-chain features, and rewards contracts remain distinct and must be assessed on their own. This documentation explains the principal lending, borrowing, interest, and reward mechanics.\
\
**Algorithm Overview**

**Lending & Borrowing:** Depositors receive **pTokens**, PrimeFi's interest-bearing deposit tokens, and borrowers can take loans against eligible collateral within configured limits. Every live reserve on Base, HyperEVM, and XDC has stable borrowing disabled, so user debt is **variable-rate debt** represented by vdTokens. The variable rate changes with reserve utilization and configuration. Deposit, borrow, repay, and withdraw actions update reserve state and indexes. If a borrower's Health Factor falls below 1, the position becomes eligible for liquidation; liquidation reduces risk but does not guarantee protocol solvency.

**Interest Rate Model:** PrimeFi's variable borrow rates are determined algorithmically by the utilization ratio (U) of each reserve, following the Aave v2 two-slope concept. There is an **optimal utilization (U\<sub>optimal\</sub>)** target. When utilization is below this threshold, the variable borrow rate increases gradually; above it, the rate increases more steeply. In formula terms: if _U ≤ U\<sub>optimal\</sub>_ then _R\<sub>borrow\</sub> = R\<sub>0\</sub> + (U/U\<sub>optimal\</sub>)_×_Slope1_; if _U > U\<sub>optimal\</sub>_ then _R\<sub>borrow\</sub> = R\<sub>0\</sub> + Slope1 + ((U – U\<sub>optimal\</sub>)/(1 – U\<sub>optimal\</sub>))_×_Slope2_. Here R\<sub>0\</sub> is the configured base rate when U=0, and Slope1/2 are configured parameters for the curve. Higher rates can encourage repayment or new supply, but they do not guarantee that liquidity will become available. Although inherited contracts may retain stable-rate types or fields, stable borrowing and rate switching are disabled in all live Base, HyperEVM, and XDC reserves.

**Yield Distribution:** Lenders earn interest from borrowers’ payments. The **liquidity rate** (deposit APY) is derived from the borrow rates after accounting for a reserve factor (protocol fee). The smart contracts compute this each time a reserve’s state updates: essentially, lenders receive the weighted average borrow rate multiplied by the utilization, minus a cut for the protocol treasury. In code, the liquidity rate is calculated as:

> _LiquidityRate = OverallBorrowRate × Utilization × (1 – ReserveFactor)_,

For live variable-only reserves, the overall borrow rate is driven by variable debt. The reserve factor determines how much accrued interest is directed to the protocol; the remainder contributes to supplier yield. Actual realized yield depends on utilization, debt repayment, reserve state, and contract execution.

**Rewards Mechanism:** Beyond interest, PrimeFi introduces a **PRFI token** rewards system to incentivize activity. The reward algorithm is implemented in a **ChefIncentivesController** contract. It treats each interest-bearing token (and potentially debt token) as a “pool” in a reward farm. Users accrue PRFI rewards proportional to their participation (e.g. the amount they have deposited or borrowed in each pool) and the allocation weight of that pool. PrimeFi’s reward controller emits PRFI at a fixed rate (which can be adjusted over time in emission schedules) and tracks, for each pool, an **accumulated reward per share** value. Whenever a user’s balance changes (deposit, withdraw, borrow, repay), the contract updates the pool’s accounting and the user’s pending rewards based on the formula:

> **pendingReward = user.amount × pool.accRewardPerShare – user.rewardDebt**&#x20;

This accounts for rewards relative to the user's recorded share when the relevant state is updated. Rewards are not guaranteed yield: PRFI emissions, eligible pools, allocation weights, eligibility rules, and claim mechanics are configurable and can change. Users claim accrued PRFI through the applicable rewards distributor contracts.

**Advanced Incentives:** PrimeFi’s reward system includes additional mechanics for qualifying long-term participants. PRFI NFT staking is live under its configured reward rules. A separate future revenue-share concept has been described as allocating 40% of PrimeFi lending-and-borrowing protocol profits to qualifying PRFI NFT participants, but it must be treated as **planned and inactive** until PrimeFi publishes an activation notice, precise revenue definition, exclusions, distribution contract, and verifiable on-chain configuration. It does not create a current entitlement or guaranteed yield. PrimeFi also provides an optional **Compounder** workflow where enabled; users should verify current fees, slippage settings, eligibility, and supported integrations before using it.
