# PrimeFi Basics on XDC

> ⚠️ **Reminder – Not Financial Advice**\
> The following is an operational description of PrimeFi, not advice to use it.

Before we talk about strategies, it helps to understand how PrimeFi behaves at a high level.

### Core Concepts

* When you **deposit** an asset on PrimeFi (XDC, psXDC, USDC, etc.), you receive an interest‑bearing token\
  (for example, `pUSDC` or `ppsXDC`).
* **Borrowers** pay interest; **depositors** earn interest.
* Some markets are additionally incentivized with **PRFI** rewards, which boost deposit or borrow APYs.
* **psXDC** is a liquid‑staking token representing staked XDC:
  * It accrues staking rewards from masternodes.
  * When deposited into PrimeFi, psXDC can earn both staking yield and protocol incentives.
* **pLP** (Prime Liquidity Provider token):
  * Locking pLP up to a certain threshold (e.g., around 5% of your deposit’s USD value) can unlock **extra emissions** on your deposits and borrows.

### Health Factor & Liquidation

PrimeFi uses a **Health Factor (HF)** to track how safe your borrowing position is.

* **HF > 1** → Position is healthy (not liquidatable at that moment).
* **HF ≤ 1** → Position can be liquidated by others.

In practice:

* A **higher HF = more safety buffer**.
* For example, many users aim for **HF ≥ 1.7–2.5** on leveraged positions to survive normal volatility.

If collateral prices fall or borrow amounts grow (through interest), HF decreases. If it drops too much, your collateral can be liquidated at a discount to repay your debt.

### Risk Buckets

We refer to three broad categories:

* **Conservative**
  * No borrowing.
  * No liquidation risk.
  * Main risks: protocol risk, smart contract risk, asset price risk.
* **Moderate**
  * Borrowing without recursive loops.
  * Liquidation risk exists but is easier to manage if LTV is low and HF is high.
* **Aggressive**
  * Leveraged looping and more complex structures.
  * High liquidation risk, sensitive to APR changes, only for advanced users.

All strategies in the following pages sit somewhere in these three buckets.
