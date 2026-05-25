---
description: PrimeFi's eligibility and incentive engine — lock pLP to unlock PRFI emissions and earn protocol fees.
---

# Prime Liquidity Provider (pLP)

**Prime Liquidity Provider (pLP)** is PrimeFi's mechanism for aligning long-term participants with the protocol. Lock pLP tokens (PRFI paired with the chain's base asset — ETH, HYPE, or XDC) to:

* Activate **PRFI emissions** on your money-market deposits and borrows.
* Receive a share of **protocol revenue** (borrowing interest, liquidation premiums, flash-loan fees).
* Stack a duration **multiplier** (up to 25x) on both of the above.

### The pLP page in the app

`/plp` is organised into four tabs. Each maps to one of the user-facing surfaces of the pLP system:

| Tab                                | What you do there                                                                                  |
| ---------------------------------- | -------------------------------------------------------------------------------------------------- |
| [Boost](tabs/boost.md)             | See your eligibility gap, Flik into pLP, simulate emissions, decide how much pLP to lock.          |
| [Locks](tabs/locks.md)             | Create / view / relock your pLP locks, toggle auto-relock, monitor your average multiplier.        |
| [Vesting](tabs/vesting.md)         | Manage the 90-day vesting of earned PRFI emissions, exit early, or Flik vesting PRFI back into pLP.|
| [Rewards](tabs/rewards.md)         | Claim platform fees, review your activity log, enable auto-compound.                               |

{% hint style="info" %}
The `/manage-prime` URL from earlier versions of the app now permanently redirects to `/plp`. All Manage PrimeFi functionality lives inside the four pLP tabs above.
{% endhint %}

### Concepts

* [pLP Overview](plp-overview.md) — what pLP is and why locking it is the eligibility check
* [Maximum APR by asset](maximum-apr-by-asset.md)
* [pLP Pools](plp-pools.md)
* [Sustaining Eligibility Status](sustaining-eligibility-status.md)
* [Bounty for Disqualification](bounty-for-disqualification.md)

### Ways of building a pLP position

* [Manual Positions](ways-of-building-the-position/manual.md) — bring your own LP tokens (Uniswap / PrjX / HyperSwap)
* [Flik Positions](ways-of-building-the-position/flik.md) — atomic borrow-and-lock from inside the app
