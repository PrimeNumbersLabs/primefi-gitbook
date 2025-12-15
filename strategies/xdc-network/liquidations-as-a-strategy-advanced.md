# Liquidations as a Strategy (Advanced)

> ⚠️ **Professional-Level Risk**\
> Acting as a liquidator is a specialized role.\
> Mistakes can lead to losses due to slippage, gas costs, or bugs.\
> This section is descriptive, not a recommendation.

Many lending protocols, including PrimeFi‑style designs, reward **liquidators** with a **bonus**.\
When a borrower’s Health Factor falls below 1.0:

* The position becomes eligible for liquidation.
* A liquidator can repay a part of the borrower’s debt.
* In return, the liquidator receives collateral at a **discount** (the “liquidation bonus”).

### How a Liquidation Strategy Could Look

**Conceptual steps:**

1. Maintain a reserve of **USDC and/or XDC** (or whatever assets are commonly borrowed).
2. Monitor PrimeFi positions programmatically:
   * Watch Health Factor values approaching 1.0.
   * Scan for sudden drops in collateral prices or market-wide volatility.
3. When a position becomes liquidatable:
   * Submit a liquidation transaction that repays part of the debt.
   * Receive collateral at a discount if the transaction succeeds.
4. Manage the acquired collateral:
   * Hold it, trade it, or redeploy it, depending on your objectives.

### Why Only Advanced Users Should Consider This

* Timing and gas costs matter; opportunities can vanish quickly.
* If many liquidators compete, MEV and priority fees become important.
* Bad parameter choices (e.g., wrong amount repaid, wrong asset routing) can turn a “profitable” liquidation into a loss.

In short, liquidation is a form of **market making in protocol risk**, not a passive yield strategy.
