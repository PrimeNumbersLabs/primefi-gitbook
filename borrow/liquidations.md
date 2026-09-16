# Liquidations

Liquidation becomes available when a borrower's Health Factor falls below 1, meaning the oracle-valued collateral no longer satisfies the configured liquidation threshold for the debt. This can result from collateral price declines, debt-asset price increases, or accrued variable interest.

<figure><img src="../.gitbook/assets/image (135).png" alt=""><figcaption></figcaption></figure>

Repaying debt or supplying additional eligible collateral can improve Health Factor, but execution, oracle movement, reserve liquidity, and pause state can affect whether a protective transaction succeeds in time.

## Liquidators

Liquidators may be users, bots, or smart contracts that monitor collateralized positions. PrimeFi v2 liquidations call `liquidationCall()` on the **LendingPool** contract—not an `L2Pool`.

The liquidator repays an allowed portion of the borrower's debt and receives collateral valued at the repaid amount plus the liquidator's share of the configured liquidation bonus. The contract directs the other share of that bonus to the protocol.

Liquidation eligibility and amounts are checked on-chain. Liquidators still face failed-transaction, gas, slippage, liquidity, oracle, and collateral-price risk.

## Example: reserve with a 15% total bonus

Assume the selected collateral reserve has a **15% total liquidation bonus** and the contract splits that bonus equally: **7.5% to the liquidator and 7.5% to the protocol**. Also assume the applicable close-factor logic permits repayment of 50% of this debt.

* Bob supplies 10 ETH and borrows DAI worth 5 ETH.
* After Bob's Health Factor falls below 1, a liquidator repays DAI worth 2.5 ETH.
* The liquidator receives ETH worth `2.5 × (1 + 7.5%) = 2.6875 ETH`.
* The protocol receives ETH worth `2.5 × 7.5% = 0.1875 ETH`.
* Total collateral removed is `2.5 × (1 + 15%) = 2.875 ETH`, leaving 7.125 ETH of supplied collateral and DAI debt worth 2.5 ETH, before subsequent price or interest changes.

This is an illustration, not a protocol-wide fixed percentage.

## Liquidation Penalty & Risk Parameters

Risk parameters are configured **per reserve**, including LTV, liquidation threshold, and liquidation bonus. The contract splits the selected collateral reserve's configured bonus between the liquidator and the protocol, so the liquidator's percentage depends on that reserve.

For example:

* A reserve configured with a 15% total bonus produces a 7.5% liquidator share and a 7.5% protocol share.
* The psXDC reserve's 7.5% total bonus produces a 3.75% liquidator share and a 3.75% protocol share.

Check the current on-chain configuration for the specific collateral reserve before estimating liquidation proceeds. Other limits, including close-factor logic and available collateral, also apply.

<figure><img src="../.gitbook/assets/PF-WP (5).jpg" alt=""><figcaption></figcaption></figure>
