---
description: Claim platform fees, vest PRFI, view activity history, and configure auto-compound.
---

# Rewards & Vesting tab

The **Rewards & Vesting** tab is where you actually receive value back from your locked pLP — the protocol's share of borrowing interest, liquidation premiums and flash-loan fees, paid out as a basket of pTokens — and where you manage your PRFI vesting.

{% hint style="info" %}
This tab combines what earlier versions of the app split across separate **Rewards** and **Vesting** tabs. Lock management lives on the [Boost & Locks tab](boost.md).
{% endhint %}

### What you can do on this tab

* **Claim All** — sweep all claimable platform fees in **a single transaction** (batched, so you only sign once even when claiming many positions).
* **Lifetime PRFI earned** — a running total of all PRFI you have earned to date (ready-to-vest + currently vesting + ready-to-claim).
* **Vesting** — start vesting earned PRFI, track maturation, and claim matured PRFI (see [Vesting tab](vesting.md) for the full mechanism).
* **Activity log** — chronological record of every interaction with the protocol (deposit, borrow, withdraw, repay, relock, disqualification).
* **Auto-compound** — automatically reinvest your claimable platform revenue into pLP.
* **Protocol stats** — global protocol fees, your share, your historical payouts.

### Protocol fees (Claim All)

Locked pLP contributes utility to the protocol, so the protocol shares a portion of borrowing-driven revenue with lockers.

<figure><img src="../../.gitbook/assets/image (136).png" alt=""><figcaption></figcaption></figure>

After choosing **Claim All** and confirming the transaction, the obtained fees are reflected as **pTokens** in your wallet.

<figure><img src="../../.gitbook/assets/image (16).png" alt="" width="522"><figcaption></figcaption></figure>

Convert them back to their underlying asset or continue contributing utility to the money market by leaving them deposited. If you opt to convert back to the original asset, go to your deposits on the Dashboard and follow the withdrawal flow.

<figure><img src="../../.gitbook/assets/image (126).png" alt=""><figcaption></figcaption></figure>

Borrowers settle loans by utilising their deposited collateral. As they contribute this utility to the PrimeFi ecosystem, their interaction with the protocol is distributed to pLP lockers. Once claimed, your share materialises as a slice of the protocol's pToken inventory.

{% hint style="info" %}
pTokens are interest-bearing tokens denoted as `pXXXX` in your wallet (e.g., `pWETH` for WETH).
{% endhint %}

### Auto-compound

Auto-compound your platform fees into pLP to enhance the growth of your position over time. Compounding takes place daily on a global schedule and can substantially boost pLP holdings over time.

#### How to enable Auto-compound

On the Rewards tab, locate the pLP overview section, choose your default lock duration, and confirm the transaction in your wallet.

<figure><img src="../../.gitbook/assets/image (128).png" alt=""><figcaption></figcaption></figure>

Then, in the platform-revenue console, toggle **Auto-compound** on and confirm the transaction in your wallet. To disable, toggle it off and confirm.

{% hint style="success" %}
Global auto-compounds run daily and are staggered to spread load. A **3% fee** is charged per compounding event.
{% endhint %}

Prefer manual control? Choose a default lock duration and click **Compound to earn XX%**, then confirm the transaction in your wallet — that compounds your current claimable balance once, without enabling the recurring auto job.

### Activity Log

The Activity Log records every interaction by your address with timestamps in UTC for **traceability, auditability and consistency** in asset management within the protocol.

Recorded event types:

* **Deposit** — collateral or liquidity added into the corresponding smart contracts.
* **Borrow** — debt opened by taking a borrowing position.
* **Withdraw / Withdrawn** — request and effective settlement of previously deposited assets.
* **Repay** — payment that reduces or fully settles outstanding debt.
* **Relocked** — re-locking of pLP to extend the lock period.
* **Disqualified** — status assigned when a position fails to meet protocol parameters (e.g., insufficient collateral, expired lock).

<figure><img src="../../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

Usability enhancements available on this surface:

* **CSV Export** — download your complete activity history as a CSV file for record-keeping, reconciliation with external systems and off-platform analysis.
* **Pagination** — navigate long histories efficiently without performance loss.

The availability of this structured record supports **data integrity**, **on-chain and off-chain audit processes**, and **advanced position management** for active users.
