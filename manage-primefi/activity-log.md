# Activity Log

The **Manage** functionality in PrimeFi incorporates an **Activity Log** designed to ensure traceability, auditability, and consistency in asset management within the protocol. Each interaction executed by the user is recorded with a **timestamp in UTC format**, providing a verifiable and chronologically ordered history of operations.

The **Activity Log** includes the following event types:

* **Deposit:** Addition of collateral or liquidity into the corresponding smart contracts.
* **Borrow:** Debt creation through the opening of borrowing positions.
* **Withdraw / Withdrawn:** Request and effective settlement of asset withdrawals previously deposited.
* **Repay:** Execution of payments that reduce or fully settle outstanding debt obligations within the protocol.
* **Relocked:** Re-locking of assets to extend their immobilization period or reinforce collateralization.
* **Disqualified:** Status assigned to operations that fail to meet the parameters defined by the protocol (e.g., insufficient collateral).

<figure><img src="../.gitbook/assets/Activity Log.jpg" alt=""><figcaption></figcaption></figure>

The availability of this structured record ensures **data integrity**, facilitates both **on-chain and off-chain audit processes**, and provides users with the tools required for **advanced position management**. Within the broader context of protocol governance and security, this control layer constitutes a key element in ensuring **both individual and systemic financial accountability** in PrimeFi.
