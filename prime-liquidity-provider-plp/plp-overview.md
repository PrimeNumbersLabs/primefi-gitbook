# pLP Overview



Below, you can see **natural market rates** highlighted in red, and **PRFI emissions** directly underneath, in blue/purple. Users that simply deposit but don't add value to the protocol will continue to earn natural market rates, but will not be eligible for PRFI emissions.

<figure><img src="../.gitbook/assets/image (92).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
In order to initiate PRFI emissions for both deposits and loans, you must lock a minimum of 5% of your deposit's USD value in pLP tokens.
{% endhint %}

### Prime Liquidity Provider (pLP) <a href="#id-42a6" id="id-42a6"></a>

* **What is it?**

Liquidity pools are fundamental to many DeFi protocols, enabling users to contribute liquidity in the form of paired assets (such as PRNT & BNB) in exchange for a share of the pool’s potential yield. pLP tokens can be locked through the protocol to activate PRNT emissions in the money market, receive protocol revenue.

#### How it works?

Example 1: Depositing $100,000 USDT without any locked pLP tokens earns you the basic APY but doesn't qualify for additional PRFI emissions.

Example 2: Deposit $10,000 USDT and lock $500 in pLP tokens to meet the 5% threshold, making you eligible for PRFI emissions.

The requirement to lock liquidity tokens in pLP form benefits the PrimeFi money market in several ways:

1. Long-Term Participation: Locking pLP tokens commits users to a specific period, increasing the likelihood of them maintaining their deposited collateral.
2. PRFI Emissions Activation: This commitment enables PRNT emissions, rewarding those invested in the protocol's long-term vision.
3. Attracting New Users: These dynamics enhance the PrimeFi money market's appeal to potential liquidity providers, fostering growth and development.

This strategic cycle not only sustains long-term liquidity but also attracts new inflows, creating a mutually beneficial scenario for individual users and the protocol as a whole.



### Maximum APR by asset

On the Markets Page, users have the ability to assess the Maximum pLP Locking APR. Additionally, there is an asset breakdown modal that provides a detailed view of the APR for each specific asset.\
\


<figure><img src="../.gitbook/assets/image (74).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (75).png" alt=""><figcaption></figcaption></figure>

#### Maximum Lock APR:&#x20;

This is determined as the highest APR achievable when pLP is locked for a one-year period.&#x20;

**Formula:**&#x20;

`1-month lock APR * 1-year lock multiplier (25x)`

#### 1-Month Locking APR:&#x20;

This represents the current APR for locking your pLP tokens for a one-month period.&#x20;

**Formula:**&#x20;

`(Total 1 Month Lockers’ Share of Annualized Protocol Fees) / (Total 1 Month Lockers’ Share of pLP Pool Size)`

#### 1 Month Locker Share of Protocol Fees:&#x20;

**Formula:**&#x20;

`(1 Month Locker Share of Protocol Power) / (Total Protocol Locking Power)`

#### Total Protocol Locking Power:&#x20;

This is the sum of all lockers’ shares, each adjusted by its respective multiplier.

```
= (1 Month Lockers' Share of pLP Pool Size * 1 Month Locker Multiplier (1x)) 
+ (3 Month Lockers’ Share of pLP Pool Size * 3 Month Locker Multiplier (4x))
+ (6 Month Lockers’ Share of pLP Pool Size * 6 Month Lockers’ Multiplier (10x))
+ (12 Month Lockers' Share of pLP Pool Size * 12 Month Locker Multiplier)
```

