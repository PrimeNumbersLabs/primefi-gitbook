---
description: How utilization influences PrimeFi's variable borrow and supply rates.
---

# Interest Rate Model

## Variable rates and utilization

PrimeFi configures an interest-rate strategy for each reserve. The strategy uses reserve utilization, denoted by `U`, to calculate the variable borrow rate and the liquidity rate applied to suppliers.

As of 16 September 2026, every live PrimeFi v2 reserve on Base, HyperEVM, and XDC has stable-rate borrowing disabled.

* When utilization is below the configured optimal level, the variable borrow rate increases along a lower slope.
* Above the optimal level, the rate increases along a steeper slope.

Higher rates can encourage repayment or additional supply, but they do not guarantee that reserve liquidity will return. At high utilization, withdrawals and new borrows can remain constrained.

## Two-slope model

For a reserve with optimal utilization `U_optimal`, base rate `R₀`, and configured slopes:

$$
\text{if } U \leq U_{\text{optimal}} : \quad R_t = R_0 + \frac{U_t}{U_{\text{optimal}}} R_{\text{slope1}}
$$

$$
\text{if } U > U_{\text{optimal}} : \quad R_t = R_0 + R_{\text{slope1}} + \frac{U_t - U_{\text{optimal}}}{1 - U_{\text{optimal}}} R_{\text{slope2}}
$$

Actual rates depend on the deployed strategy and current reserve state. Check the live app and on-chain configuration rather than relying on example parameters.

PrimeFi's model inherits Aave v2 concepts. For background on the two-slope model, see Aave's current [Interest Rate Strategy documentation](https://aave.com/docs/aave-v3/smart-contracts/interest-rate-strategy); PrimeFi's deployed implementation and parameters remain distinct and should be read on-chain.
