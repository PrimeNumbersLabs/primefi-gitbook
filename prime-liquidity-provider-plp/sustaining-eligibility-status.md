# Sustaining Eligibility Status

{% hint style="warning" %}
At the time of writing, the required pLP-to-deposit ratio is configured at **5%**. This is an adjustable protocol parameter; verify the current requirement in the app and on-chain.
{% endhint %}

Being a risk asset, pricing volatility can cause users to fluctuate in and out of eligibility.

Example:

* Under a 5% configuration, Boris holds $5 worth of pLP on **HyperEVM (PRFI/HYPE)** and has $100 in USDT deposits, meeting the current example requirement. On **Base**, the pLP pair is **PRFI/ETH**, not PRFI/HYPE.
* If market movements reduce the pLP position below $5 while the deposit value remains $100, Boris falls below that example threshold and becomes ineligible.

{% hint style="info" %}
The protocol must consistently assess the eligibility status to ascertain which users are included and which are excluded.
{% endhint %}

Once eligible, banners at the top of each page will display "Emissions active."

<figure><img src="../.gitbook/assets/image (122).png" alt=""><figcaption></figcaption></figure>

Should you lose eligibility, a notification reading "boost inactive" will be visible at the top of each page. It will also indicate the amount of pLP needed to restore eligibility.

Click "Flik into pLP" and follow the prompts to restore eligibility for configured PRFI emissions.

<figure><img src="../.gitbook/assets/image (121).png" alt=""><figcaption></figcaption></figure>

{% hint style="warning" %}
To enhance the chances of staying eligible for PRFI emissions, money market participants may want to maintain a buffer zone above the 5% threshold to accommodate potential volatility.
{% endhint %}

### Example:

Assuming the requirement remains configured at 5%, Bob deposits $1,000 USDT and needs $50 of eligible pLP to qualify.

Choosing to stay cautious amid potential volatility, Bob opts to lock $60 in pLP (6% of the deposit, or one percentage point above the 5% threshold) to improve his eligibility buffer. Price movements can still cause the ratio to fall below the requirement.

Furthermore, users can enhance their chances of preserving eligibility status by enabling auto-compound and auto-relock features from the Manage PrimeFi page.
