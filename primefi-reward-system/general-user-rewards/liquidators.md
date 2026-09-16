# Liquidators

Liquidation is permissionless: a user, bot, or smart contract may submit a liquidation for a position that meets the on-chain requirements. There is no separate liquidator role to obtain.

## Rewards for liquidators

Liquidators repay an allowed amount of debt and receive collateral valued at the repayment amount plus the liquidator's share of the selected collateral reserve's configured liquidation bonus. The contract sends the other share of that bonus to the protocol.

The percentage is **not fixed across PrimeFi**. Liquidation parameters are set per reserve:

* A reserve with a 15% total bonus yields a 7.5% liquidator share and a 7.5% protocol share.
* The psXDC reserve has a 7.5% total bonus, yielding 3.75% to the liquidator and 3.75% to the protocol.

Liquidators should check the current on-chain configuration and account for close-factor limits, gas, slippage, liquidity, oracle movement, and transaction failure.

<figure><img src="../../.gitbook/assets/Copia de PF Whitepaper (5).jpg" alt="" width="563"><figcaption></figcaption></figure>

### Example

Assume Bob supplies 10 ETH, borrows USDT worth 5 ETH, and his Health Factor later falls below 1. Also assume the ETH collateral reserve has a 15% total bonus and the applicable close-factor logic permits repayment of half the debt.

A liquidator who repays USDT worth 2.5 ETH receives ETH worth `2.5 × (1 + 7.5%) = 2.6875 ETH`; the protocol receives ETH worth `2.5 × 7.5% = 0.1875 ETH`. This example applies only to a reserve with that configuration and does not establish a universal liquidator reward.
