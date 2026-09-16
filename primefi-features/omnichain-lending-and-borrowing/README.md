# Omnichain Lending & Borrowing

{% hint style="danger" %}
Check [Market Status](../../security/market-status.md) before interacting. Cross-chain configuration does not imply that the origin or destination market is currently available.
{% endhint %}

PrimeFi lets you **open a borrow on one network** and **receive the borrowed asset on another**, without manual bridging.\
Under the hood, PrimeFi uses **LayerZero messaging** and **Stargate liquidity**:

* **Accounting stays on the origin chain** (your collateral, debt, interest accrual, health factor, and potential liquidation live there).
* **Delivery happens on the destination chain** (the asset you borrow is sent to your wallet on the target network via **Stargate**).

This design removes cross-chain friction while keeping a **single, consistent risk model** (prices, LTVs, liquidations) anchored to the origin chain.

***

### Key properties

* **One position, many networks**: supply collateral on chain **A**, receive the loan on chain **B**.
* **Origin-anchored risk**: health factor, interest, and liquidation live on the **origin chain** where you opened the position.
* **Bridging handled for you**: the borrowed asset is **bridged by Stargate** to the destination chain, no manual bridge or wallet hop needed.
* **Origin-chain pricing**: the configured oracle sources drive LTV and HF on the **origin chain**.
* **Omnichain incentives**: where enabled and successfully delivered, sidechain activity is synchronized to Base for reward accounting. Delayed or failed messages may require retry or reconciliation.

***

### Repay on the origin network



* **Repay on origin**: send USDC on HyperEVM and call `repay()`.

Interest and HF always update on the **origin**.

***

### Liquidations

If your **health factor falls below 1**, a liquidator acts on the **origin chain**:

* Seizure and close-out occur **only on the origin** against your posted collateral.
* The physical location of the borrowed asset (e.g., Base) is irrelevant to liquidation logic.

This keeps position accounting on the origin chain, but liquidation still depends on correct oracle data, available liquidity, transaction execution, and market status.

***

### Fees & gas

* **Protocol fees/interest**: accrue on the **origin chain**.
* **Cross-chain fees**: the borrow transaction includes **LayerZero** and **Stargate** fees (quoted pre-trade).
* **Omnichain Gas Deposit**: used for **incentive synchronization** when you act on non-Base networks (not required to execute the borrow itself).
* **Reward claims**: availability, timing, execution chain, and gas requirements depend on the active reward configuration. Check the current app and on-chain contracts.

***

### Deployed controls and limitations

* **Origin validation**: the origin LendingPool validates reserve state, collateral, debt, and Health Factor before creating the borrow.
* **Stargate amount protection**: the deployed cross-chain flow uses a quote-derived minimum amount for the Stargate delivery. Do not assume a separate PrimeFi deadline control unless it is present in the submitted transaction.
* **Delivery and retries**: message delivery, ordering, and retry behavior depend on LayerZero and Stargate. The current PrimeFi `StargateBorrow` contract does not provide a separate documented daily route cap, custom nonce/retry ledger, or path-level pause.
* **Market pause**: PrimeFi can pause a lending market through its pool controls. A market pause is broader than a route-specific switch and can restrict risk-reducing actions.
* **Oracles**: LTV and HF depend on the oracle sources and integration controls configured on the **origin** chain. See [Oracles](../oracles.md) for current sources and risks.



***

### What changes versus a classic bridge?

* You **do not** manually bridge assets or manage two legs.
* Borrow is **one action** on the origin; PrimeFi handles **delivery**.
* Risk, rates, and liquidation remain **coherent and local** to the origin chain.
