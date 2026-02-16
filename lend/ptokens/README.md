# pTokens

### pTokens: Interest-Bearing Deposit Tokens

**pTokens** (interest-bearing tokens) are minted when users **deposit assets** into the protocol.\
They act both as deposit receipts and as yield-accruing instruments.

* **Primary function:** represent the user’s share of the liquidity pool.
* **Interest accrual:** the value of each pToken increases relative to its underlying asset as the pool generates yield.
* **Example:** when depositing USDC, the user receives `pUSDC`. These tokens can later be redeemed for the original deposit plus accrued interest.
* **User role:** pTokens serve as the user’s “proof of deposit” and guarantee the right to reclaim funds with interest.

👉 In short: **pTokens represent the creditor (lender) side of the protocol.**

| Topic                 | Detail                                                                                                                                                                                                                                                                                                                                                                                                                        |
| --------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Symbol format**     | `p<ASSET>`, e.g. `pWETH`, `pUSDC`                                                                                                                                                                                                                                                                                                                                                                                             |
| **Lifecycle**         | <p>• <strong>Minted</strong> when you supply the underlying asset.</p><p>• <strong>Burned</strong> when you withdraw or when your collateral is liquidated.</p>                                                                                                                                                                                                                                                               |
| **Valuation**         | <p>pTokens maintain a 1:1 peg to the underlying asset at all times. Each pToken can always be redeemed for exactly 1 unit of the underlying (e.g., 1 pUSDC = 1 USDC).</p><p>As yield accrues, <strong>your pToken balance increases automatically over time,</strong> no action required. This means the protocol <em>rebases</em> your balance to reflect accumulated interest rather than changing the value per token.</p> |
| **Interest accrual**  | PrimeFi tracks interest using an internal liquidity index for each reserve. When the index increases due to earned yield, the protocol **rebases pToken balances upward proportionally** across all holders’ wallets.                                                                                                                                                                                                         |
| **Wallet visibility** | pTokens are standard ERC-20 tokens and appear in most wallets; you may need to add the contract address manually.                                                                                                                                                                                                                                                                                                             |
| **Redeeming**         | Navigate to **Dashboard → Deposits → Withdraw** to convert pTokens back to the original asset. The protocol burns the pTokens and transfers the corresponding underlying amount.                                                                                                                                                                                                                                              |
