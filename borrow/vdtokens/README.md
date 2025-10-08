# vdTokens

### Variable Debt vdTokens

**vdTokens** (variable debt tokens) are minted when users **borrow assets** from the protocol.\
They track the user’s debt balance, including both principal and accrued variable interest.

* **Primary function:** represent the outstanding amount owed by the user to the protocol.
* **Interest accrual:** the vdToken balance increases dynamically as variable interest is applied to the borrowed amount.
* **Example:** when borrowing USDC, the user receives `vdUSDC`. The balance of these tokens grows until the loan is repaid.
* **User role:** vdTokens serve as the user’s “proof of debt” and must be repaid to close the borrowing position.

👉 In short: **vdTokens represent the debtor (borrower) side of the protocol.**



| Topic             | Detail                                                                                                                                                               |
| ----------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Symbol format     | vd, e.g. vdWETH, vdUSDC                                                                                                                                              |
| Lifecycle         | <p>• Minted when you borrow the underlying asset.<br>• Burned when you repay the loan (partially or fully).</p>                                                      |
| Valuation         | Maintains a 1:1 peg to the borrowed asset. Your vdToken balance increases over time as variable interest accrues.                                                    |
| Interest accrual  | Each reserve has a variable debt index. When the index increases, your vdToken balance scales up proportionally, no user action required.                            |
| Wallet visibility | vdTokens are standard ERC-20 tokens and can appear in most wallets; you may need to add the contract address manually.                                               |
| Repayment         | Navigate to **Dashboard → Borrowings → Repay** to reduce or close your debt. The protocol burns the vdTokens and decreases the outstanding loan balance accordingly. |
