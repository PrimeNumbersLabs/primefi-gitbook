# pTokens

### pTokens: Interest-Bearing Deposit Tokens

PrimeFi issues a _pToken_ for every supported asset you supply.\
For example, a USDT deposit mints **pUSDT** to your wallet.

| Topic                 | Detail                                                                                                                                                                           |
| --------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Symbol format**     | `p<ASSET>`, e.g. `pWETH`, `pUSDC`                                                                                                                                                |
| **Lifecycle**         | <p>• <strong>Minted</strong> when you supply the underlying asset.</p><p>• <strong>Burned</strong> when you withdraw or when your collateral is liquidated.</p>                  |
| **Valuation**         | Maintains a **1:1 peg** to the underlying asset. Your pToken balance grows over time as interest accrues.                                                                        |
| **Interest accrual**  | Each reserve has a _liquidity index_. When the index increases, your pToken balance is scaled up proportionally—no action required.                                              |
| **Wallet visibility** | pTokens are standard ERC-20 tokens and appear in most wallets; you may need to add the contract address manually.                                                                |
| **Redeeming**         | Navigate to **Dashboard → Deposits → Withdraw** to convert pTokens back to the original asset. The protocol burns the pTokens and transfers the corresponding underlying amount. |
