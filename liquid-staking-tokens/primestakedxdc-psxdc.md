# PrimeStakedXDC (psXDC)

## psXDC Deposits on the XDC Network

**PrimeFi** now supports **psXDC** as a supply and borrow asset on the **XDC Network**.\
**psXDC** is the liquid‑staking token (LST) from **PrimeStaking** that accrues XDC staking rewards while you hold it.

When you deposit psXDC on PrimeFi, you receive **ppsXDC**, PrimeFi’s interest‑bearing receipt token. **ppsXDC is a rebase token**—its balance increases automatically as rewards are distributed.

> **Important:** If you deposit psXDC into PrimeFi, you **will not** claim staking rewards directly at primestaking.xyz. Instead, the PrimeFi psXDC pool claims those rewards **on‑chain** and **redistributes** them to **ppsXDC holders** via rebases. You still earn the underlying staking yield—plus PrimeFi incentives.

***

### Contracts & roles

* **ppsXDC (receipt/rebase token):** `0x834695A5d33967f8cC27E6d15684c0aA36cA4375`\
  Add this token to your wallet to watch your rebasing balance.
* **PrimeStaking (primestaking.xyz):** liquid staking that mints **psXDC** from **XDC** and produces staking rewards.
* **PrimeFi (primefi.xyz):** lending & borrowing that mints **ppsXDC** when you supply **psXDC** and routes rewards + incentives.

***

### What you earn when you deposit psXDC

Your psXDC deposit on PrimeFi earns **three** streams of yield, all accruing to **ppsXDC holders**:

1. **LST base yield (from psXDC)**\
   The psXDC inside the PrimeFi pool continues to generate XDC staking rewards via PrimeStaking. PrimeFi **claims** those rewards and **rebases** them to ppsXDC.
2. **Extra PRFI incentive (3–4% APY, variable)**\
   An additional reward paid in **PRFI** for psXDC suppliers.
3. **Platform & pLP incentives (variable)**\
   Additional incentives are shown in the app UI. These change with program parameters and utilization.

> Live APYs are variable—always rely on the rate shown in the PrimeFi app.

***

### Why ppsXDC yield can change: Coverage Ratio

Only the **psXDC actually held by the PrimeFi pool contract** generates staking rewards for rebase. If users **borrow psXDC** out of the pool or **loop** by re‑depositing borrowed psXDC (minting more ppsXDC), then **ppsXDC supply can exceed psXDC in the pool**. That dilutes the LST component of the deposit APY.

**Coverage Ratio**

```
Coverage Ratio = (psXDC balance in the PrimeFi pool contract) / (total ppsXDC supply)
```

* **1.00** → ppsXDC captures \~100% of psXDC’s base LST yield.
* **0.85** → ppsXDC captures \~85% of psXDC’s base LST yield (diluted).

**Total Deposit APY (simplified)**

```
Total Deposit APY ≈ [Base psXDC APY × Coverage Ratio] + [PRFI APY] + [platform/pLP APY]
```

> Because looping can increase ppsXDC supply and reduce Coverage Ratio, heavy looping **lowers** the LST portion of yield for **everyone** (including the looper).
>
> Users can **borrow psXDC** and **re‑deposit** it, minting additional ppsXDC. Because borrowed psXDC is no longer held by the pool, the Coverage Ratio drops, so the **6%+ LST yield gets diluted** across more ppsXDC.

***

### Supported assets (XDC market)

As shown in the current market: **XDC, psXDC, USDC, USDT, PRFI**.\
Supply/borrow caps, APYs, and utilization are visible in the app and change over time.

***

### How deposits, rewards, and withdrawals work

1. **Deposit psXDC → receive ppsXDC**
   * Connect on **XDC Network** and approve psXDC.
   * Supplying psXDC mints **ppsXDC 1:1** (subject to the vault’s current exchange mechanics). ppsXDC is **rebase**: your balance increases as rewards are distributed.
2. **Rewards distribution**
   * The pool contract **claims psXDC staking rewards** from PrimeStaking and re‑distributes them to **ppsXDC holders** via rebase.
   * **PRFI incentives** and **platform/pLP incentives** are added on top (see the Rewards panel in the UI for your accrued amounts).
3. **Withdraw**\
   Redeem ppsXDC to withdraw psXDC (subject to pool liquidity). Because ppsXDC rebases, you don’t need to claim the LST portion—your **ppsXDC balance grows** over time and you redeem more psXDC.

_Wallet tip:_ Some wallets refresh rebase balances only on activity. If your ppsXDC display looks stale, a tiny self‑transfer can refresh it. Gas is paid in **XDC**.

***

### Borrowing, looping, and strategies

PrimeFi is a **lending & borrowing** protocol. You can deposit psXDC, borrow against it, and optionally **loop** (lever up) by re‑depositing what you borrow. This increases your exposure to deposit APY but also increases **borrow costs** and **liquidation risk**. Because psXDC is intended to be \~1:1 with XDC, same‑asset loops reduce price risk but **do not remove** interest‑rate or depeg risk.

> **Critical:** Looping often **lowers** the LST portion of your deposit APY for everyone by pushing down the **Coverage Ratio** (see above). It can also make **borrow APR** spike when utilization is high. Always check live rates.

#### Common loop patterns

**A) psXDC → borrow psXDC → re‑deposit (same‑asset loop)**

1. Deposit psXDC.
2. Borrow psXDC against it.
3. Re‑deposit the borrowed psXDC to mint more ppsXDC.
4. Repeat until you reach your target health factor/risk.

* **Pros:** Simple; minimizes price basis mismatch.
* **Cons:** Pushes Coverage Ratio down (diluting everyone’s LST yield, including yours) and exposes you to **psXDC borrow APR** spikes. If psXDC briefly trades away from its intended peg, you can face unexpected PnL or collateral value changes.

**B) psXDC → borrow XDC → stake to psXDC → deposit (cross‑asset loop)**

1. Deposit psXDC.
2. Borrow **XDC**.
3. Stake the borrowed XDC at **PrimeStaking** to mint psXDC.
4. Deposit the new psXDC back into PrimeFi.

* **Pros:** May be attractive if **XDC borrow APR** is lower than **psXDC borrow APR**.
* **Cons:** Adds **staking/unstaking frictions**, extra transactions and gas, and potential **timing/price basis** risk between XDC and psXDC. Still reduces Coverage Ratio once the added psXDC is re‑deposited.

***

### Loop math & break‑even&#x20;

Let:

```
c    = collateral factor / target LTV (e.g., 70% = 0.70)
L    = 1 / (1 - c)                  # supply leverage
B    = c / (1 - c)                  # borrow leverage
Ydep = (Base psXDC APY × Coverage Ratio) + PRFI APY + platform/pLP APY − frictions
Yb   = borrow APR on the asset you borrow (psXDC or XDC)
```

**Break‑even condition**

```
Looping is profitable  ⇔  Ydep > (c × Yb)
```

**Approximate net APY on your equity**

```
Ynet ≈ (L × Ydep) − (B × Yb)
```

***

### Worked examples (illustrative only)

**Example 1 — Same‑asset loop (psXDC → psXDC)**

Assumptions:

* `c = 70%` → `L = 3.33×`, `B = 2.33×`
* Base psXDC APY `= 6.0%`
* Coverage Ratio `= 0.85`
* PRFI APY `= 3.5%`
* platform/pLP APY `= 1.0%`
* psXDC borrow APR `Yb = 16.0%`

Calculations:

```
Ydep = (6.0% × 0.85) + 3.5% + 1.0% = 9.6%
Break-even: c × Yb = 0.70 × 16.0% = 11.2%  → not met
Ynet ≈ (3.33 × 9.6%) − (2.33 × 16.0%) = 32.0% − 37.3% ≈ −5.3%  (unprofitable)
```

**Takeaway:** With high psXDC borrow APR and diluted Coverage Ratio, looping loses versus a simple deposit.

***

**Example 2 — Cross‑asset loop (psXDC → borrow XDC → stake to psXDC → deposit)**

Assumptions:

* `c = 70%` → `L = 3.33×`, `B = 2.33×`
* Base psXDC APY `= 6.0%`
* Coverage Ratio `= 0.92` after adding new psXDC
* PRFI APY `= 3.5%`, platform/pLP APY `= 1.0%`, frictions `= 0.5%`
* **XDC** borrow APR `Yb = 9.0%`

Calculations:

```
Ydep = (6.0% × 0.92) + 3.5% + 1.0% − 0.5% = 9.5%
Break-even: c × Yb = 0.70 × 9.0% = 6.3%  → met
Ynet ≈ (3.33 × 9.5%) − (2.33 × 9.0%) = 31.7% − 21.0% ≈ +10.7%  (profitable under these inputs)
```

**Takeaway:** When **XDC borrow APR** is materially below psXDC’s and frictions are small, a cross‑asset loop can work. Small changes in borrow APR or incentives can erase this edge—stress‑test before levering up.

***

### Practical looping tips

* **Keep a safety buffer.** Health factor can fall from price moves, parameter changes, or rising borrow APRs.
* **Watch Coverage Ratio.** The **Deposit APY in the app already reflects** Coverage Ratio and incentives—use it as your ground truth.
* **Borrow APR is dynamic.** Utilization spikes can push APR higher and flip a positive spread negative.
* **Mind frictions.** Cross‑asset loops add transactions, gas, staking time, and potential slippage/peg risk.
* **Stress‑test.** If `borrow APR +5–10%` or `incentives −2–3%`, do you stay positive? If not, de‑leverage.

***

### Step‑by‑step: deposit psXDC and earn

1. Connect wallet on **XDC Network** and hold psXDC (+ a small amount of XDC for gas).
2. Approve and **supply psXDC** in the PrimeFi psXDC market.
3. Receive **ppsXDC** (rebase). Optionally add `0x834695A5d33967f8cC27E6d15684c0aA36cA4375` to your wallet.
4. Monitor the **Deposit APY** (LST effective yield + PRFI + platform/pLP).
5. **Claim PRFI/platform rewards** from the app as they accrue (ppsXDC rebases automatically).
6. **Withdraw** by redeeming ppsXDC for psXDC (subject to pool liquidity).

***

### FAQ

**Does ppsXDC supply sometimes exceed psXDC in the pool?**\
Yes. Borrowers can re‑deposit psXDC and mint **more ppsXDC** while the borrowed psXDC leaves the pool. This reduces **Coverage Ratio** and dilutes the LST component.

**Why is psXDC deposit APY sometimes below \~6%?**\
Because **Coverage Ratio < 1** when psXDC is heavily borrowed/looped; the base LST yield is spread across more ppsXDC.

**Why is my ppsXDC balance increasing without claims?**\
ppsXDC is a **rebase** token. Staking rewards from PrimeStaking and pool incentives are applied as **supply increases** to ppsXDC.

**Do PRFI incentives compound into ppsXDC?**\
No. PRFI is a separate incentive you claim in the app. The LST portion compounds via **ppsXDC rebases**.

**Can I withdraw anytime?**\
Yes—subject to **pool liquidity**. High utilization may require waiting for liquidity to free up or repaying borrows.

***

### Risks & disclaimers

APYs/APRs are **variable** and depend on utilization, incentives, and market conditions. Risks include interest‑rate risk (borrow APR spikes), liquidation risk, psXDC/XDC peg deviations, incentive program changes, and liquidity constraints on withdrawal. Nothing here is financial advice.

***

### TL;DR

* Deposit **psXDC** → receive **ppsXDC** (rebase).
* PrimeFi claims psXDC staking rewards and **distributes them to ppsXDC holders**.
* You also earn **PRFI (3–4% APY)** + **platform/pLP** incentives.
* **ppsXDC can exceed psXDC in the pool** due to borrowing/looping, which **dilutes** the LST portion (Coverage Ratio ↓).
* Looping only makes sense when **Deposit APY > (collateral factor × borrow APR)**, and it increases risk.
