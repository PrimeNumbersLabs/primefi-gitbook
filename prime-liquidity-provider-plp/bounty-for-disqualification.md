---
hidden: true
---

# Bounty for Disqualification

{% hint style="warning" %}
It will be available for the final version of the protocol that will be launched on mainnet.
{% endhint %}

PrimeFi is introducing a feature for users who fulfill the 5% pLP requirement to disqualify ineligible users for a bounty, similar to operating a liquidation bot. This can be done either directly through the UI or with the assistance of searcher bots.

A "bounty" is assigned to the account, which eligible pLPs can claim as a base reward.

Watchful bounty hunters can keep track of available disqualification bounties on the Manage PrimeFi page and disqualify ineligible users by selecting "claim" and confirming the transaction.

<figure><img src="../.gitbook/assets/image (1) (1) (1).png" alt="" width="488"><figcaption></figcaption></figure>

The disqualification system serves to prevent expired pLP accounts from receiving platform fees that have been illegitimately earned and stops ineligible users from receiving $PRFI emissions that fall below the 5% pLP threshold.

Furthermore, bounty hunters are entitled to a base bounty for relocking pLP for users who have activated "auto-relock." They also receive compensation for executing auto-compounds on behalf of users who have opted for this automation.

This not only contributes to further decentralizing actions taken on the protocol but also empowers users to easily remove ineligible participants with a simple point-and-click method, benefiting both the protocol and themselves.

To reduce the risk of disqualification, it is advisable to maintain eligibility status by setting your pLP threshold above 5%.

To avoid disqualifications related to expired locked pLP, users can toggle the "auto-relock" function on the Manage page, ensuring the continuous receipt of platform fees without interruption.

\


<div align="center"><figure><img src="../.gitbook/assets/image (123).png" alt=""><figcaption></figcaption></figure></div>

Additional Information Bounty hunters are required to maintain the 5% pLP threshold status and have deposited assets to be eligible for claiming bounties.

Claimed bounties are rewarded in Vesting PRFI.

The base bounty is dynamic and depends on the demand for searcher bots and the price of $PRFI.

Bounties follow a prioritization system, allowing only one bounty per account at a time, although there are up to three types of bounties:

1. Bounty priority is given to expired lock treatment, involving the removal of expired locks from the pool or re-locking pLPs with auto-relock enabled. This prevents the account from receiving ineligibly earned platform revenue. The bounty for removing an expired lock is the base bounty.
2. The next bounty priority is preventing accounts from continuing to receive ineligibly earned PRFI emissions that fall below the 5% eligibility threshold. The bounty for emissions ineligibility equals the base bounty.
3. The last bounty priority is for auto-compounding. When an auto-compound event is triggered, the protocol delegates the transaction execution to bounty hunters. AutoCompound bounties are funded by the fee paid by the user, which will be compounded. This amount starts small and increases over time as users accrue more pending rewards for compounding.

Self-disqualification occurs when performing an on-chain action within the Dapp (deposit/claim/lock) triggers disqualification if the above parameters are detected.
