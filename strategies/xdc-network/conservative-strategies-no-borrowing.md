# Conservative Strategies (No Borrowing)

> ⚠️ **Reminder – Not Financial Advice**\
> These examples describe _how_ one could use PrimeFi conservatively.\
> They are not recommendations or guarantees of safety.

Conservative strategies **do not use borrowing**.\
You cannot be liquidated because you are not taking debt.\
Main risks are protocol risk, smart contract risk, and asset price risk.

***

### 1. “Set‑and‑Forget” psXDC Yield Stack

**Goal:** Capture XDC staking yield plus protocol incentives without leverage.

**Assets used:** XDC → psXDC

**Conceptual steps:**

1. Stake XDC using **PrimeStaking** (or equivalent) to receive **psXDC**.
2. Deposit psXDC into **PrimeFi** and receive interest‑bearing `ppsXDC`.
3. Optionally lock **pLP** (PrimeFi’s liquidity token) so your psXDC deposit qualifies for **PRFI incentives**, if available.

**Return drivers (qualitative):**

* XDC staking yield embedded in psXDC.
* PrimeFi deposit APY (if any) from borrowers.
* PRFI emissions and/or pLP‑related rewards.

**Risks:**

* XDC price volatility (you are long XDC).
* PrimeFi protocol and smart contract risk.

***

### 2. USDC “Parking Lot”

**Goal:** Park stablecoin liquidity with relatively low volatility risk.

**Assets used:** USDC

**Conceptual steps:**

1. Deposit **USDC** into PrimeFi.
2. Optionally lock some **pLP** to boost deposit APY if the UI shows meaningful extra rewards.

**Return drivers:**

* Base USDC deposit APY (interest from borrowers).
* PRFI + pLP incentives, depending on current configuration.

**Risks:**

* USDC de‑peg risk (generally low but non‑zero).
* PrimeFi protocol risk and smart contract risk.

***

### 3. 50/50 Treasury Base (psXDC + USDC)

**Goal:** Blend yield (psXDC) with stability (USDC) without borrowing.

**Assets used:** psXDC, USDC

**Conceptual steps:**

1. Allocate a fraction of your holdings to **psXDC** for yield.
2. Allocate the remaining fraction to **USDC** for stability / dry powder.
3. Deposit both into PrimeFi as suppliers.
4. Use one **pLP** position (if desired) to activate emissions on both assets.

**Why this can be useful:**

* psXDC side captures staking yield and any additional incentives.
* USDC side stabilizes the treasury and can be redeployed quickly.
* Still no liquidation risk, because no borrowing is used.
