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
   * Optional safety params: **minAmountOut**, **slippage bps**, **deadline**
2. Confirm the transaction on **HyperEVM**.\
   The UI quotes **interest + LayerZero/Stargate fees** before you sign.

#### What happens on-chain

1. **Origin checks (HyperEVM)**
   * LendingPool validates your **health factor**, LTV and caps.
   * Your **variable debt** is minted on HyperEVM for the borrowed amount.
2. **Cross-chain messaging**
   * PrimeFi’s **Borrow OApp** sends a LayerZero message with borrow details.
   * In parallel, a **Stargate** instruction moves 5,000 USDC liquidity to **Base**.
3. **Destination delivery (Base)**
   * Stargate **delivers 5,000 USDC** to your wallet on Base.
   * Your **collateral and debt remain on HyperEVM**.

Result: you now **hold USDC on Base** while your **debt accrues on HyperEVM** against your ETH collateral.

> Tip: You don’t need to switch networks during the borrow. PrimeFi handles the bridge leg via Stargate.
