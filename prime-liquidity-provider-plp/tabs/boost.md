---
description: Activate PRFI emissions on your deposits and borrows by locking pLP.
---

# Boost & Locks tab

The **Boost & Locks** tab is the entry point to the pLP system. It shows the gap between your current locked pLP value and the **5% threshold** required to start earning PRFI emissions on your deposits and borrows in the markets, and it is where you create, view and manage your locks.

{% hint style="info" %}
The pLP page is organised into **two** tabs: **Boost & Locks** (this page — eligibility, the emissions table, and lock management/calendar) and **Rewards & Vesting** (claiming platform fees, PRFI vesting, and protocol stats). Earlier versions of the app split these into four separate tabs.
{% endhint %}

### What you see on this tab

* **Boost progress bar** — how close you are to qualifying for emissions on your current open positions.
* **Required pLP** — the USD value of pLP you still need to lock to reach 5% of your collateral.
* **Flik into pLP** — one-click action that takes some of your supplied collateral, pairs it with PRFI, and locks the resulting pLP for you.
* **Emissions table** — each market's slice of the single global PRFI budget, broken down per asset, plus a personalized **Your PRFI / day** column when an eligible wallet is connected. See [Maximum APR by asset → Per-market PRFI emissions](../maximum-apr-by-asset.md) for exactly how these numbers are derived.
* **Your locks & lock-expiry calendar** — every active lock, its multiplier and unlock date, with relock / withdraw and auto-relock controls.

### Eligibility model

To activate PRFI emissions for both deposits and loans, you must lock a minimum of **5% of your deposit's USD value in pLP tokens** on the relevant chain.

{% hint style="info" %}
PRFI emissions on the lending markets are streamed by the `ChefIncentivesController` contract. Emissions are only active on chains where the chef is currently funded — at the moment that's primarily **Base**. The Boost tab will show an explicit "Emissions inactive" banner on chains where the chef isn't streaming, so the eligibility check doesn't silently look broken.
{% endhint %}

For the full pLP eligibility model and how it composes with multipliers, see:

* [pLP Overview](../plp-overview.md)
* [Sustaining Eligibility Status](../sustaining-eligibility-status.md)
* [Bounty for Disqualification](../bounty-for-disqualification.md)

### Building your pLP position

Two ways to get pLP and qualify:

1. **Flik into pLP** — borrow the paired asset (HYPE / ETH / XDC) atomically against your deposit and lock the resulting pLP. See [Flik Positions](../ways-of-building-the-position/flik.md).
2. **Manual** — generate pLP on Uniswap / HyperSwap / PrjX yourself and lock it. See [Manual Positions](../ways-of-building-the-position/manual.md).
