---
description: Managing liquidity risk through PrimeFi's borrow interest rate model
---

# Insterest Rate Model

## Interest Rates (APY) & Utilization&#x20;

PrimeFi's interest rate algorithm is finely tuned to address liquidity risk and enhance utilization. Borrow interest rates are determined based on the utilization rate, denoted as U.

U serves as an indicator of the capital availability within the pool. The interest rate model effectively handles liquidity risk in the protocol by aligning user incentives to bolster liquidity:

* During periods of ample capital availability, the model promotes low-interest rates to incentivize borrowing.
* In times of capital scarcity, higher interest rates are encouraged to stimulate debt repayments and foster additional capital supply.

## Interest Rate Model&#x20;

Liquidity risk becomes pronounced as utilization reaches higher levels, particularly when U approaches 100%. To cater to this constraint, the interest rate curve is bifurcated around an optimal utilization rate, denoted as U\_optimal. Prior to U\_optimal, the slope is gradual, while beyond it, the slope increases steeply.

The interest rate Rₜ follows the model:

$$
\text{if } U \leq U_{\text{optimal}} : \quad R_t = R_0 + \frac{U_t}{U_{\text{optimal}}} R_{\text{slope1}}
$$

$$
\text{if } U > U_{\text{optimal}} : \quad R_t = R_0 + R_{\text{slope1}} + \frac{U_t - U_{\text{optimal}}}{1 - U_{\text{optimal}}} R_{\text{slope2}}
$$

Given that these elements of the Prime Finance smart contracts draw inspiration from Aave, kindly consult their documentation for the computation of Annual Percentage Yield (APY):

[Link to Aave documentation on APY calculations](https://docs.aave.com/risk/liquidity-risk/borrow-interest-rate)
