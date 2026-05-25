---
description: Vest earned PRFI emissions, or Flik them into pLP without paying the early-exit penalty.
---

# Vesting tab

The **Vesting** tab is where the PRFI you earned from the lending markets (as boosted emissions) sits during its 90-day maturation period. You can let it vest in full, exit early with a penalty, or Flik it into a new pLP lock.

### Top stats

| Stat                       | What it means                                                                                |
| -------------------------- | -------------------------------------------------------------------------------------------- |
| **Earned PRFI**            | Cumulative PRFI emissions you've earned and started vesting.                                 |
| **Currently vesting**      | PRFI still inside the 90-day vesting window.                                                 |
| **Ready to claim**         | PRFI that has fully matured and can be withdrawn at 100%.                                    |
| **Lifetime penalties**     | Total PRFI lost over time by exercising "Exit Early" on partially-vested batches.            |

### Overview

For participants in PrimeFi's money markets, opting to vest PRFI is a way to convert protocol emissions into long-term protocol-aligned tokens. By depositing assets and meeting pLP eligibility, users earn an APY on their assets **plus** additional yield through PRFI emissions.

The vesting of PRFI follows a structured approach: a **linearly decreasing penalty for early withdrawal**, starting at **90% and dropping to 25%** over a 90-day window. This structure encourages users to commit to the full vesting duration, ensuring they can fully reap the benefits of earned PRFI.

<figure><img src="../../.gitbook/assets/PF Whitepaper (2) (1).jpg" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
This tab is only meaningful for users who meet the pLP eligibility requirements. If you aren't eligible yet, head over to the **Boost** tab to start.
{% endhint %}

### Initiating PRFI Vesting

To fully vest PRFI and unlock its full value, a **90-day maturation period** is required.

1. **Starting the vesting process** — go to the Vesting tab and locate the **Vesting Overview** section.
2. **Eligibility** — if you haven't met the pLP requirements, the **Start vesting** button is disabled.
3. **Activation** — eligible users click **Start vesting** and confirm the transaction in their wallet.

<figure><img src="../../.gitbook/assets/Vesting (2).jpg" alt=""><figcaption></figcaption></figure>

After activation, the **Vesting Overview** panel exposes diverse management functions for monitoring your vesting process.

### Flik vesting PRFI into pLP

Once PRFI is in the vesting phase, you can **Flik it directly into a locked pLP position without paying the exit penalty**, starting to earn platform revenue and re-qualifying for further PRFI emissions immediately.

Within the **"currently vesting"** section, choose **Flik into pLP**.

<figure><img src="../../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

The Flik-with-vesting-PRFI modal appears:

<figure><img src="../../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

The PRFI and paired-asset input fields are auto-populated. Fliking from vesting can only be done **for the entire vesting amount**, so the paired asset (borrowed or pulled from your wallet) is calculated automatically to match the LP ratio.

After clicking continue, choose the lock duration and corresponding multiplier, then confirm. Verify the Fliking information is accurate and click **Flik into pLP** to sign the necessary transactions.

### Early exit

Exiting early triggers a linear-schedule penalty to receive PRFI immediately. Vests can be exited collectively for the penalty displayed under the **Exit Early** button.

<figure><img src="../../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

Alternatively, exit individual vests with their own penalty by clicking the right arrow beside each one.

<figure><img src="../../.gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure>

### Vest to maturity

PRFI that has completed the 90-day maturation can be withdrawn in full from the **vested** panel on the Vesting tab.

<figure><img src="../../.gitbook/assets/Vested (1).jpg" alt=""><figcaption></figcaption></figure>

### Additional notes

* Exiting a vest early triggers a **25%–90% penalty** based on a linear schedule of elapsed time.
* The penalty paid is distributed **90% to the PrimeFi Treasury** and **10% burned**.
* Initiating **Exit Early** from the **Currently vesting** panel exits all separate vesting periods at once, applying the corresponding penalty per batch.
* Alternatively, you can **Exit Early** from individual vests using the per-row menu.
* **Flik into pLP** from this panel includes all separate vesting periods.
