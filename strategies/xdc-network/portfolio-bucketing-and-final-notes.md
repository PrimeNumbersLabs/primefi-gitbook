# Portfolio Bucketing & Final Notes

> ⚠️ **Non-Financial Advice**\
> This section provides a _framework_ for thinking about risk allocation.\
> It is not a recommendation or allocation plan.

For larger holders or entities, it can be helpful to think in terms of **risk buckets**.

***

### 1. Core Treasury (Low Risk)

Focus on **non‑leveraged** positions from the Conservative page:

* psXDC “set‑and‑forget” yield stack.
* USDC “parking lot.”
* 50/50 psXDC + USDC base.

Characteristics:

* No liquidation risk (no borrowing).
* Yields mainly from staking, borrow interest, and protocol incentives.
* Main risks: protocol/contract risk and underlying asset volatility.

***

### 2. Structured Yield (Medium Risk)

Borrowing strategies with **no recursive looping**:

* psXDC collateral → borrow USDC (stay long XDC).
* USDC collateral → borrow XDC → stake to psXDC.
* psXDC collateral → borrow XDC for operations.

Characteristics:

* Liquidation risk exists but is manageable if Health Factor is kept high (e.g. ≥ 2.0).
* Yields come from spreads between psXDC yield and borrow APRs, plus incentives.
* Requires periodic monitoring and risk management.

***

### 3. Degen Sleeve (High Risk)

Only for small, high‑risk capital allocations:

* psXDC → borrow XDC → stake → psXDC loop when math is clearly favorable.
* USDC + psXDC barbell loops and other complex structures.
* Possibly automated liquidation strategies.

Characteristics:

* High tail risk and sensitivity to market conditions.
* Suitable only for advanced users who can monitor positions and systems closely.
* Should be sized such that a **complete loss** would not threaten overall solvency.

***

### 4. Final Reminder

All strategies described across these pages are **examples**, not recommendations.

Before implementing any position:

* Check **live APRs**, utilization, and risk parameters in the PrimeFi UI.
* Stress test your assumptions (e.g., sudden XDC drawdown, APR changes, de‑peg scenarios).
* Decide in advance:
  * How much you are willing to lose in worst‑case scenarios.
  * What Health Factor you consider your “panic line” for reducing risk.

> 🧠 **Always do your own research.**\
> DeFi can be powerful, but it is never risk‑free.
