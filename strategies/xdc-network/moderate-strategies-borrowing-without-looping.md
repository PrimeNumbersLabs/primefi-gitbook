# Moderate Strategies (Borrowing Without Looping)

> ⚠️ **Important – Borrowing Introduces Liquidation Risk**\
> These strategies use **debt**. If the value of your collateral falls or borrow APRs rise,\
> your Health Factor can drop and your position can be liquidated.\
> This is not financial advice; use at your own risk.

Moderate strategies involve **borrowing once** (or a few times) but do **not** recursively loop collateral and debt.

***

### 1. Borrow USDC Against psXDC (Stay Long XDC)

**Goal:** Obtain USDC liquidity without selling XDC, while earning psXDC yield.

**Assets:** psXDC as collateral, USDC as debt

**Conceptual steps:**

1. Stake XDC → receive **psXDC**.
2. Deposit psXDC into PrimeFi as collateral.
3. Borrow **USDC** against psXDC:
   * Target a conservative **LTV** so that **Health Factor ≥ \~2.0** (or higher for more safety).
4. Use borrowed USDC for off‑protocol needs or other on‑chain strategies.

**Economic intuition:**

* psXDC collateral earns staking yield and protocol incentives.
* You pay USDC borrow APR on your debt.
* Rough “carry” on your equity ≈\
  `psXDC effective APY − (LTV × USDC borrow APR)`

**Risks:**

* XDC price drops → psXDC value falls → HF decreases → possible liquidation.
* USDC borrow APR may spike during high utilization.
* Protocol and smart contract risk.

***

### 2. USDC Collateral → Borrow XDC → Stake to psXDC

**Goal:** Increase XDC exposure while keeping USDC as base collateral.

**Assets:** USDC as collateral; XDC and psXDC on the position side.

**Conceptual steps:**

1. Deposit **USDC** as collateral on PrimeFi.
2. Borrow **XDC** at a conservative LTV (HF ≥ \~2.0 recommended).
3. Stake borrowed XDC via PrimeStaking → receive **psXDC**.
4. Optional: deposit psXDC back into PrimeFi to earn yield.

**Interpretation:**

* You are effectively **long XDC and short USDC**, with psXDC yield on the XDC side.
* Profitable if XDC holds or goes up and psXDC yield exceeds XDC borrow costs over your time horizon.

**Risks:**

* XDC price can fall quickly, pushing HF toward liquidation.
* XDC borrow APR can change over time.
* Protocol and smart contract risk.

***

### 3. psXDC Collateral → Borrow XDC for Operations

**Goal:** Unlock XDC gas/liquidity without selling long‑term psXDC holdings.

**Assets:** psXDC as collateral, XDC as debt.

**Conceptual steps:**

1. Deposit **psXDC** as collateral on PrimeFi.
2. Borrow **XDC** up to a moderate LTV.
3. Use borrowed XDC to:
   * Pay gas and operational expenses,
   * Provide liquidity on DEXes,
   * Hedge, or
   * Partially unwind XDC exposure.

Because psXDC and XDC prices are closely linked, collateral and debt move together, which can make HF somewhat more stable—but you are still exposed to volatility and must manage risk.
