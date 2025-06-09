---
description: PrimeFi Lending & Rewards Mechanics
---

# Know Your Algorithm

### Introduction

PrimeFi is a decentralized finance platform that offers lending and borrowing services, modeled after Aave’s protocols, with additional reward incentives. Users can deposit cryptocurrency assets to earn yield and use deposits as collateral to borrow other assets. PrimeFi’s smart contracts implement algorithmic interest rate models (inspired by Aave) and a custom rewards distribution mechanism to incentivize participation. This documentation explains the core algorithms underlying PrimeFi’s lending and borrowing system, as well as its rewards mechanics, including how interest rates are determined, how yields are distributed, and the roles of the key contracts involved.\
\
**Algorithm Overview**

**Lending & Borrowing:** PrimeFi’s lending algorithm uses an over-collateralized model similar to Aave. Depositors receive **aTokens** (interest-bearing tokens) representing their stake, and borrowers can take loans against deposited collateral within defined limits. Interest rates are dynamic and adjust based on pool utilization. The system supports both **stable-rate** and **variable-rate** loans, allowing borrowers to lock in a rate or use a floating rate. Key on-chain logic ensures that each action (deposit, borrow, repay, withdraw) updates the reserve’s state and interest indices, maintaining an accurate accrual of interest over time. If a borrower’s collateral value falls too low (health factor drops below 1), the protocol flags the position for liquidation to protect solvency.

**Interest Rate Model:** PrimeFi’s interest rates are determined algorithmically by the utilization ratio (U) of each asset pool, mirroring Aave’s two-slope model. There is an **optimal utilization (U\<sub>optimal\</sub>)** target. When utilization is below this optimal threshold, the borrow rate increases gradually; when above, the rate steepens significantly. In formula terms: if _U ≤ U\<sub>optimal\</sub>_ then _R\<sub>borrow\</sub> = R\<sub>0\</sub> + (U/U\<sub>optimal\</sub>)_×_Slope1_; if _U > U\<sub>optimal\</sub>_ then _R\<sub>borrow\</sub> = R\<sub>0\</sub> + Slope1 + ((U – U\<sub>optimal\</sub>)/(1 – U\<sub>optimal\</sub>))_×_Slope2_. Here R\<sub>0\</sub> is the base rate when U=0, and Slope1/2 are configured parameters for the interest curve. This design keeps interest low when liquidity is ample (encouraging borrowing) and raises rates sharply as pools near full utilization (encouraging repayment and new deposits). Borrowers can choose stable rates (fixed based on a reference rate plus adjustments) or variable rates (floating with utilization), and can swap between them, with on-chain validation to prevent rate arbitrage abuse.

**Yield Distribution:** Lenders earn interest from borrowers’ payments. The **liquidity rate** (deposit APY) is derived from the borrow rates after accounting for a reserve factor (protocol fee). The smart contracts compute this each time a reserve’s state updates: essentially, lenders receive the weighted average borrow rate multiplied by the utilization, minus a cut for the protocol treasury. In code, the liquidity rate is calculated as:

> _LiquidityRate = OverallBorrowRate × Utilization × (1 – ReserveFactor)_,

Meaning nearly all interest paid by borrowers flows to depositors, while a small portion (the reserve factor) is set aside as protocol revenue.

**Rewards Mechanism:** Beyond interest, PrimeFi introduces a **PRFI token** rewards system to incentivize activity. The reward algorithm is implemented in a **ChefIncentivesController** contract. It treats each interest-bearing token (and potentially debt token) as a “pool” in a reward farm. Users accrue PRFI rewards proportional to their participation (e.g. the amount they have deposited or borrowed in each pool) and the allocation weight of that pool. PrimeFi’s reward controller emits PRFI at a fixed rate (which can be adjusted over time in emission schedules) and tracks, for each pool, an **accumulated reward per share** value. Whenever a user’s balance changes (deposit, withdraw, borrow, repay), the contract updates the pool’s accounting and the user’s pending rewards based on the formula:

> **pendingReward = user.amount × pool.accRewardPerShare – user.rewardDebt**&#x20;

This ensures that each user earns rewards in real-time relative to their share of the pool’s liquidity. Rewards are not drawn from lender interest; instead, PRFI emissions are configured by the protocol (and can follow a schedule of rewards-per-second). Users can claim accumulated PRFI via the rewards distributor contracts.

**Advanced Incentives:** PrimeFi’s reward system includes additional mechanics to encourage long-term engagement and ecosystem participation. For example, **Prime Numbers NFTs integration** allows PRFI holders who stake tokens alongside Prime NFTs to receive a share of platform profits (40% of PrimeFi’s profit is shared with these stakers). The protocol uses an eligibility checker on-chain to enforce that only qualified users (e.g. those meeting certain staking or NFT criteria) receive the full rewards. Addresses that do not meet requirements can be flagged by a **BountyManager** and disqualified from reward accrual until they become eligible, ensuring that the profit-sharing benefits long-term supporters. (Notably, the fees shared with NFT holders come from the platform’s own income, not by reducing lender yields.) PrimeFi also provides an optional **Compounder** tool that automatically claims and reinvests rewards into the lending pool, optimizing users' yields over time.
