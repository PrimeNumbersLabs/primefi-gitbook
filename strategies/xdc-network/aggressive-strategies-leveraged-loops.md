# Aggressive Strategies (Leveraged Loops)

> ⚠️ **High Risk – Advanced Users Only**\
> The strategies on this page involve **leveraged looping**.\
> They can amplify both gains and losses and are highly sensitive to APR changes,\
> coverage ratios, and price volatility. Liquidation can happen quickly.\
> This is not financial advice. Only consider these if you fully understand the risks.

***

### 1. Looping Math (Intuition Only)

To reason about loops, it helps to define:

* `c` = target collateral ratio (LTV as a fraction, e.g. 0.6).
* `L = 1 / (1 − c)` = effective leverage on **supplied** assets.
* `B = c / (1 − c)` = effective leverage on **borrowed** assets.
* `Ydep` = deposit APY (e.g. psXDC effective APY).
* `Yb` = borrow APR on the asset you are borrowing.

**Break‑even condition** for a simple loop:

> `Ydep > c × Yb`

**Approximate net APY on equity:**

> `Ynet ≈ (L × Ydep) − (B × Yb)`

These expressions are simplified and ignore path‑dependent effects, liquidation risk, and APR volatility, but they are useful for intuition.

***

### 2. psXDC Same‑Asset Loop

**Goal:** Lever up on psXDC yield by borrowing psXDC against psXDC.

**Conceptual steps:**

1. Deposit **psXDC** as collateral.
2. Borrow **psXDC**.
3. Deposit the borrowed psXDC back into PrimeFi.
4. Repeat until you reach a target HF or desired leverage.

**Why this is often&#x20;**_**not**_**&#x20;optimal:**

* Each loop increases psXDC utilization, which may **push psXDC borrow APR up**.
* The **coverage ratio** between psXDC and underlying staked XDC can fall, reducing effective yield.
* In many realistic cases, same‑asset psXDC looping produces **negative** net APY once you factor in borrowing costs and dilution.

This kind of loop should only be considered when:

* psXDC deposit APY is **clearly higher** than `c × psXDC borrow APR`,
* You are prepared to watch HF and rates very closely, and
* You fully accept the risk of fast liquidation.

***

### 3. psXDC → Borrow XDC → Stake → psXDC (Cross‑Asset Loop)

Often more interesting than same‑asset loops when conditions are right.

**Goal:** Leverage psXDC staking yield using **XDC as the borrowed asset**.

**Conceptual steps:**

1. Deposit **psXDC** as collateral.
2. Borrow **XDC** at some target LTV.
3. Stake the borrowed XDC using PrimeStaking → receive **new psXDC**.
4. Deposit that psXDC into PrimeFi.
5. Optionally repeat (loop) several times, each time watching HF and APRs.

**When this can make sense:**

* psXDC effective APY (staking + incentives) is **significantly greater** than\
  `(collateral ratio × XDC borrow APR)`.
* XDC borrowing is relatively cheap and psXDC incentives are strong.

**Key risks:**

* XDC price volatility (big drops can rapidly compress HF).
* XDC borrow APR may spike if utilization increases.
* psXDC coverage ratio changes can reduce yield for everyone, including you.
* Complexification of your risk: more steps, more things to watch.

***

### 4. USDC + psXDC Barbell Loop

**Goal:** Combine stable capital (USDC) and leveraged psXDC yield.

**Conceptual structure:**

1. Deposit both **USDC** and **psXDC** on PrimeFi.
2. Use psXDC as the main collateral source.
3. Borrow **USDC**.
4. Convert part of borrowed USDC → XDC → psXDC and deposit it.
5. Keep the rest of borrowed USDC as **liquid safety** to repay debt fast if necessary.

This creates a “barbell”:

* One side: **leveraged psXDC yield**.
* Other side: **USDC liquidity** available to repair Health Factor or use elsewhere.

Because of the complexity and tail‑risk nature of this structure, it should be limited to a **small, high‑risk sleeve** of capital, if used at all.
