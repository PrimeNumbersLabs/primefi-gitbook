# Omnichain Lending & Borrowing

PrimeFi lets you **open a borrow on one network** and **receive the borrowed asset on another**, without manual bridging.\
Under the hood, PrimeFi uses **LayerZero messaging** and **Stargate liquidity**:

* **Accounting stays on the origin chain** (your collateral, debt, interest accrual, health factor, and potential liquidation live there).
* **Delivery happens on the destination chain** (the asset you borrow is sent to your wallet on the target network via **Stargate**).

This design removes cross-chain friction while keeping a **single, consistent risk model** (prices, LTVs, liquidations) anchored to the origin chain.

***

### Key properties

* **One position, many networks**: supply collateral on chain **A**, receive the loan on chain **B**.
* **Origin-anchored risk**: health factor, interest, and liquidation live on the **origin chain** where you opened the position.
* **Bridging handled for you**: the borrowed asset is **bridged by Stargate** to the destination chain, no manual bridge or wallet hop needed.
* **Unified pricing**: Chainlink price feeds drive LTV and HF on the **origin chain**.
* **Omnichain incentives**: actions from any network are synchronized to Base (PrimeFi’s incentives home chain) so rewards remain consistent.

***

### Repay from any network

You can repay on the **origin chain** directly, or repay **cross-chain**:

* **Repay on origin**: send USDC on HyperEVM and call `repay()`.
* **Repay from destination** (e.g., you hold USDC on Base): call **Repay Cross-Chain**.
  * PrimeFi routes the USDC back to **HyperEVM via Stargate** and posts a LayerZero message so your **debt is reduced on the origin chain**.

Interest and HF always update on the **origin**.

***

### Liquidations

If your **health factor falls below 1**, a liquidator acts on the **origin chain**:

* Seizure and close-out occur **only on the origin** against your posted collateral.
* The physical location of the borrowed asset (e.g., Base) is irrelevant to liquidation logic.

This keeps the risk model **simple and predictable**.

***

### Fees & gas

* **Protocol fees/interest**: accrue on the **origin chain**.
* **Cross-chain fees**: the borrow transaction includes **LayerZero** and **Stargate** fees (quoted pre-trade).
* **Omnichain Gas Deposit**: used for **incentive synchronization** when you act on non-Base networks (not required to execute the borrow itself).
* **Claims**: lender rewards are claimable weekly from any network; **pLP claims after vesting execute on Base** and need a small amount of **ETH on Base**.

***

### Safeguards & parameters

* **Slippage protection**: `minAmountOut` and `deadline` guard the Stargate leg on delivery.
* **Idempotency & retries**: cross-chain messages are **nonce-tracked** and **retryable** if a destination step temporarily fails.
* **Rate limits & caps**: per-asset **daily borrow caps** and **per-route limits** can be enforced.
* **Pause per market**: individual assets/paths can be paused if volatility or oracle anomalies are detected.
* **Oracles**: Chainlink price feeds secure LTV and HF on the **origin**.



***

### What changes versus a classic bridge?

* You **do not** manually bridge assets or manage two legs.
* Borrow is **one action** on the origin; PrimeFi handles **delivery**.
* Risk, rates, and liquidation remain **coherent and local** to the origin chain.
