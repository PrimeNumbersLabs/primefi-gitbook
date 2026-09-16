---
description: Flash-loan mechanics; availability depends on market status and reserve liquidity.
---

# Flash Loans

{% hint style="danger" %}
Check [Market Status](../security/market-status.md). Flash loans are unavailable while the relevant lending market is paused.
{% endhint %}

Flash loans allow a caller to borrow available liquidity without posting collateral, provided the principal and configured premium are returned before the same transaction finishes. If repayment fails, the transaction reverts.

Atomic repayment protects the flash-loan leg from becoming unsecured debt. It does not make the caller's strategy, integrated protocols, oracle inputs, or the reserve itself risk-free.

## Why Flash Loans Exist

* **Arbitrage:** Momentarily source large liquidity to buy an asset where it is under-priced and sell where it is over-priced.
* **Collateral swaps and debt restructuring:** Replace collateral or migrate debt between supported protocols without providing the full capital up front.
* **Automated Liquidations:** Bots can cover an under-collateralised position, seize its collateral at a discount, repay the flash loan, and keep the difference, helping the protocol stay solvent.

## Operating Principles

1. **Atomicity** – Borrow, use the funds, and repay (amount + fee) all happen in a single, indivisible transaction.
2. **Repayment enforcement** – A successful flash loan leaves no outstanding flash-loan principal. This protection does not cover losses caused through another protocol action or vulnerability in the same transaction.
3. **Fee structure** – A configured premium is added to the repayment and distributed according to the deployment's current configuration. Callers should read the on-chain parameters rather than assume a fixed fee.
4. **Liquidity bound** – The requested amount cannot exceed the reserve's available liquidity at execution time. Flash-loan demand still uses that liquidity during the transaction and can compete with other transactions.

## Risks and Controls

| Concern | What atomicity does—and does not—protect |
| --- | --- |
| **Failed repayment** | The entire transaction reverts if the principal and premium are not returned. |
| **Oracle or market manipulation** | A single transaction can borrow, trade, alter manipulable market state, call an oracle-dependent action, and repay. Flash liquidity can therefore amplify oracle, pricing, and composability exploits, especially in low-liquidity markets. |
| **Smart-contract and integration risk** | PrimeFi inherits Aave v2 concepts, but inherited code, PrimeFi-specific changes, callbacks, and external integrations can still contain vulnerabilities. Atomic repayment does not undo losses in a vulnerable protocol if the overall transaction succeeds. |
| **Liquidity and execution risk** | Capacity is limited by available reserve liquidity and can change before execution. Transactions may fail or be affected by slippage, ordering, or MEV. |
| **Administrative parameters** | Premiums and related controls are configurable by authorised roles. Users and integrators should verify current on-chain settings. |

Flash loans are intended for developers and sophisticated users who can evaluate smart-contract, oracle, liquidity, and transaction-ordering risk. Their atomic repayment property is narrow and should not be treated as a general safety guarantee.
