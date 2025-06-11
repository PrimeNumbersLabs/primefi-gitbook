# Lend

### Lending Workflow

All procedures can be carried out from the **Dashboard**. Screens and labels may vary slightly between networks, but the underlying logic remains the same.

***

#### 1. Supplying Assets

| Step | Action                                                                                                              |
| ---- | ------------------------------------------------------------------------------------------------------------------- |
| 1    | Navigate to Markets or Dashboard.                                                                                   |
| 2    | Click **Deposit** next to the asset you want to deposit.                                                            |
| 3    | <p>Enter the amount.</p><p>• The projected APY and current utilisation are shown for reference.</p>                 |
| 4    | Confirm the on-chain transaction in your wallet.                                                                    |
| 5    | After the transaction is final, the asset appears in the **Supplied** list and starts earning interest immediately. |

***

#### 2. Borrowing

PrimeFi utilizes LayerZero messaging, allowing the asset you borrow to reside **on a different network** from your collateral.

<table><thead><tr><th>Parameter</th><th width="402">Details</th></tr></thead><tbody><tr><td><strong>Collateral</strong></td><td>Only assets marked <em>Collateral enabled</em> can be used to borrow. Collateral factors (LTV, liquidation threshold) are shown in the asset tooltip.</td></tr><tr><td><strong>Borrowable amount</strong></td><td>Calculated from your collateral value, current debt, and per-asset LTV. The UI displays a real-time <strong>Health Factor (HF);</strong> keep HF > 1 to avoid liquidation.</td></tr><tr><td><strong>Rate mode</strong></td><td><p>• <strong>Variable</strong> (default) – interest updates with pool utilisation.</p><p>• <strong>Stable</strong> – fixed at borrow time. You may switch modes later; the change applies to the whole position for that asset.</p></td></tr><tr><td><strong>Cross-chain withdrawal</strong></td><td>Select a target network in the borrow dialog. The loan principal is bridged automatically via LayerZero; no manual bridge or wrapper is required.</td></tr></tbody></table>

***

#### 3. Withdrawing or Unlocking Liquidity

| Situation                           | Action                                                                                                                                                                                                                |
| ----------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Withdraw underlying**             | In **Dashboard → Withdraw**, choose the asset and amount, then confirm the transaction. The protocol checks HF; if withdrawal would push HF ≤ 1, it is blocked.                                                       |
| **Use pTokens without withdrawing** | Your supplied balance is represented by **pTokens** (e.g. `pUSDC`). You can transfer or use these tokens in other DeFi protocols as collateral or liquidity, while the deposit continues to earn interest on PrimeFi. |
| **Insufficient pool liquidity**     | A withdrawal fails if the pool’s available liquidity is lower than the requested amount. Wait for new supplies or borrower repayments, then retry. The UI shows current liquidity in real time.                       |

***

#### 4. Monitoring & Maintenance

| Tool                  | Purpose                                                                                                                  |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| **Health Factor bar** | Turns yellow when HF < 1.1, red at HF ≤ 1.0.                                                                             |
| **Rate switch**       | In the **Borrowed** list, click the rate badge to toggle between Stable and Variable (subject to asset policy).          |
| **Repay**             | Partial or full repayment reduces debt and raises HF. Setting the amount to _Max_ repays the entire outstanding balance. |

***

#### Notes

* **Cross-chain delays:** Borrowing to another network finalizes after LayerZero confirmation; this typically takes seconds but may vary depending on the network load.
* **Liquidation buffer:** Maintain HF well above 1 to account for price volatility and accrued interest, especially when using volatile collateral.
