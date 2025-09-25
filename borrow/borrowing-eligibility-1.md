# Cross-Chain Collateral & Omnichain Loans

PrimeFi’s lending engine is **omnichain by design**. Thanks to LayerZero messaging, you can:

* **Deposit collateral on any supported network**\
  — HyperEVM & Base. (Arbitrum & BNB Chain comming soon).
* **Borrow into a different network**\
  — without manually bridging the collateral.

**How it works (high-level)**

1. When you supply an asset (e.g., ETH on Arbitrum) PrimeFi records that collateral in a **global position ledger** that is synced across chains via LayerZero.
2. When you request a loan elsewhere (e.g., USDC on Hyperliquid) the protocol checks your unified LTV and health factor in real time, approves the borrow, and updates the same global position, so your risk profile is consistent no matter where you move liquidity.

<figure><img src="../.gitbook/assets/image (112).png" alt=""><figcaption></figcaption></figure>

{% hint style="success" %}
## **Transfer from Base Network to HyperEVM**
{% endhint %}

**Why it matters**

* **Capital efficiency** – Unlock borrowing power where you need it while your assets stay where they already are.
* **Lower gas & fewer steps** – A single cross-chain message replaces multiple bridge + approval transactions.
