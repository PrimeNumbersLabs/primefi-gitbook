---
description: Available on Mainnet
---

# Flash Loans

Flash loans allow a user to borrow any liquid asset in the PrimeFi pools without posting collateral, as long as the loan is opened and fully repaid within the same blockchain transaction (i.e., within one block).\
If the repayment plus a small fee does not arrive before the transaction ends, the entire operation is automatically cancelled and the chain reverts to its previous state, so the pool remains intact and depositors stay protected.

**Why Flash Loans Exist**

* **Arbitrage:** Momentarily source large liquidity to buy an asset where it is under-priced and sell where it is over-priced.
* **Collateral Swaps / Debt Restructuring:** Replace volatile collateral with a stable asset, or migrate a loan between protocols, without needing upfront capital.
* **Automated Liquidations:** Bots can cover an under-collateralised position, seize its collateral at a discount, repay the flash loan, and keep the difference, helping the protocol stay solvent.

**Operating Principles**

1. **Atomicity** – Borrow, use the funds, and repay (amount + fee) all happen in a single, indivisible transaction.
2. **No Counterparty Risk** – Because the transaction reverts if repayment fails, the pool never carries outstanding debt.
3. **Fee Structure** – A predefined premium (e.g., 0.05 %) is added to the repayment; the fee is shared between liquidity providers and the protocol treasury.
4. **Liquidity Cap** – The maximum that can be borrowed equals the pool’s unused liquidity at that moment, ensuring ordinary lenders and borrowers are never starved of funds.



**Risk & Mitigations**

| Potential Concern           | Safeguard                                                                                            |
| --------------------------- | ---------------------------------------------------------------------------------------------------- |
| **Pool Drain**              | Loans are bounded by the pool’s real-time free liquidity.                                            |
| **Smart-contract exploits** | The underlying flash-loan logic is inherited from Aave v2, which has been extensively audited.       |
| **Market manipulation**     | The single-block window gives no time to influence oracle prices or markets before repayment is due. |
| **Fee manipulation**        | Premiums are configurable only by authorised governance and are displayed to users up-front.         |

Flash loans are a specialised tool intended for developers and sophisticated users who can author smart-contract logic and understand the atomicity requirement. They add capital efficiency and arbitrage-driven price alignment to the PrimeFi ecosystem without compromising lender safety.
