# Borrow

{% hint style="danger" %}
Check [Market Status](../security/market-status.md). Borrowing is unavailable while the selected market is paused.
{% endhint %}

PrimeFi lets users borrow supported assets against eligible supplied collateral. Borrowing capacity depends on collateral value, each reserve's risk parameters, current debt, oracle prices, and available liquidity. If a position's Health Factor falls below `1`, it becomes eligible for liquidation; reserve liquidation thresholds are inputs used to calculate that Health Factor.

As verified on 16 September 2026, all PrimeFi v2 reserves on Base, HyperEVM, and XDC support **variable-rate borrowing only**. Stable-rate borrowing and rate switching are disabled. Variable debt accrues through each reserve's variable borrow index and is represented by vdTokens.

Before borrowing, review:

* [How to Borrow](how-to-borrow.md)
* [Borrowing Eligibility](borrowing-eligibility.md)
* [Health Factor](health-factor.md)
* [Loan Repayment](loan-repayment.md)
* [Liquidations](liquidations.md)
* [Flash Loans](flash-loans.md)
* [Interest Rate Model](interest-rate-model.md)
* [vdTokens](vdtokens/README.md)

Maintain a Health Factor buffer and verify current on-chain parameters. UI estimates can become stale as prices, interest, liquidity, and reserve state change.

