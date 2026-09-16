# Lend

{% hint style="danger" %}
Check [Market Status](../security/market-status.md) before interacting. Supplying, borrowing, repaying, and withdrawing can be unavailable while a market is paused.
{% endhint %}

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

<table><thead><tr><th>Parameter</th><th width="402">Details</th></tr></thead><tbody><tr><td><strong>Collateral</strong></td><td>Only assets marked <em>Collateral enabled</em> can be used to borrow. Collateral factors (LTV, liquidation threshold) are shown in the asset tooltip.</td></tr><tr><td><strong>Borrowable amount</strong></td><td>Calculated from your collateral value, current debt, and per-asset LTV. The UI displays an estimated <strong>Health Factor (HF)</strong>; maintain a buffer above 1 because prices and accrued interest can change before execution.</td></tr><tr><td><strong>Rate mode</strong></td><td><strong>Variable only.</strong> Every live reserve on Base, HyperEVM, and XDC has stable-rate borrowing disabled. The variable rate changes with reserve utilisation and configuration; users cannot select or switch to a stable rate in these markets.</td></tr><tr><td><strong>Cross-chain borrow delivery</strong></td><td>Where enabled, select a destination network in the borrow dialog. PrimeFi uses LayerZero messaging and Stargate liquidity for the delivery leg. This removes a separate manual bridge step but does not remove bridge, messaging, liquidity, or execution risk.</td></tr></tbody></table>

***

#### 3. Withdrawing or Unlocking Liquidity

| Situation                           | Action                                                                                                                                                                                                                |
| ----------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Withdraw underlying**             | In **Dashboard → Withdraw**, choose the asset and amount, then confirm the transaction. The contract validates the latest position state and blocks a collateral withdrawal that would make the Health Factor invalid. |
| **Use pTokens without withdrawing** | Your supplied position is represented by **pTokens** (for example, `pUSDC`). They may be transferable or supported by other DeFi integrations, but transfer validation, collateral effects, and third-party risks apply. The interest-bearing claim follows the pToken holder. |
| **Liquidity or market constraints** | A withdrawal can fail if the reserve lacks available liquidity, is paused, or another on-chain validation fails. UI values are informational and can change before the transaction executes. |

***

#### 4. Monitoring & Maintenance

| Tool                  | Purpose                                                                                                                  |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| **Health Factor display** | Provides an estimate based on the UI's latest data. On-chain validation and oracle state at execution determine whether an action succeeds. |
| **Variable-rate display** | Shows the current variable borrow rate. Stable-rate selection and switching are disabled in live Base, HyperEVM, and XDC reserves. |
| **Repay**             | Partial or full repayment reduces debt and generally raises HF. Setting the amount to _Max_ requests repayment of the entire outstanding variable debt, subject to wallet balance, allowance, and transaction execution. |

***

#### Notes

* **Cross-chain delays:** Borrowing to another network finalizes after LayerZero confirmation; this typically takes seconds but may vary depending on the network load.
* **Liquidation buffer:** Maintain HF well above 1 to account for price volatility and accrued interest, especially when using volatile collateral.
