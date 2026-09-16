---
description: (example)
---

# End-to-end workflow

#### Scenario

You have **ETH collateral on HyperEVM** and want to **borrow USDC on Base**.

#### What you do (single flow)

1. In PrimeFi (still on **HyperEVM**), choose:
   * **Borrow asset**: USDC
   * **Destination chain**: Base
   * **Amount**: e.g., 5,000 USDC
2. Confirm the transaction on **HyperEVM**.\
   Review the variable borrow rate, Health Factor estimate, protocol fee, and quoted Stargate/LayerZero messaging cost before signing.

#### What happens on-chain

1. **Origin checks (HyperEVM)**
   * LendingPool validates your **health factor**, LTV, reserve state, borrowing configuration, and available liquidity.
   * Your **variable debt** is minted on HyperEVM for the borrowed amount.
2. **Cross-chain delivery**
   * `StargateBorrow` deducts any configured cross-chain borrow fee.
   * It asks Stargate for the expected received amount and uses that quote as `minAmountLD`.
   * It quotes the native messaging fee and calls the configured Stargate router's `sendToken`.
3. **Destination delivery (Base)**
   * If messaging and destination execution succeed, Stargate delivers the quoted USDC amount to your wallet on Base.
   * Your **collateral and debt remain on HyperEVM**.

Result after successful delivery: you hold USDC on Base while your debt accrues on HyperEVM against your origin-chain collateral.

> PrimeFi submits the Stargate delivery leg from the origin transaction. This reduces manual steps but does not guarantee delivery or remove messaging, liquidity, configuration, or destination-execution risk.
