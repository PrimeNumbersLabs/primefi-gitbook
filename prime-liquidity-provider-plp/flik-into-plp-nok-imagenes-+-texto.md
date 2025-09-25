---
hidden: true
---

# Flik into pLP nok imagenes + texto

## What is Fliking?

Imagine you have tBNB and want to enter the PRFI-tBNB pool. The traditional process for doing so is quite cumbersome.

Initially, you need to provide PRFI and tBNB in the correct ratios, which requires four separate transactions.

_**Fliking**_ simplifies this process by allowing you to complete it with a single click.

## Which assets can be Hopped?

Currently, we have the Flik option available only from the BNB Testnet Chain, which supports the following assets:

* BNB
* USDT

In the future of Prime Finance, the assets available to create your position with one click will increase, as will the supported networks.

Prior to the launch of the protocol on Mainnet, the assets that will be available for the Flik process, depending on the network, will be revealed.

(PEDIR A INES QUE HAGA EL CUADRO)

## How It Operates?

When you use _**Flik**_ with one of these assets, the system automatically converts it to tBNB behind the scenes. This tBNB is then combined with PRFI to create and lock the LP.

This feature is designed to give you increased flexibility with the protocol, making it easier and more efficient to earn and lock LP.

## How to Flik via Prime Finance UI:

1. Begin by connecting your wallet to Prime Finance.
2. While there are several sections on the platform to flikp into pLP, for this tutorial, we'll select the Markets page.
3. To hop into LP, ensure you have one of our supported assets in your wallet. If you plan to borrow against your collateral, the Flik wizard accommodates that too.
4. Additionally, make sure you have the native gas token of the supported chain you're using—ETH for Arbitrum and BNB for BNB Chain—to cover transaction fees.

{% hint style="info" %}
There is a minimum amount of $5 USD worth of pLP required to initiate a Flik.
{% endhint %}

<figure><img src="../.gitbook/assets/image (10) (1).png" alt="" width="375"><figcaption></figcaption></figure>

1. Choose your Flik source. Prime Finance enables you to Hopp with supported assets from your wallet. Alternatively, you can borrow directly from the money market if you have deposited collateral. Prioritize your health factor and the risk of liquidation before opting for borrowing. Fliking will ensure your health factor is never reduced below 1.1.
2. Enter your desired amount. To swiftly fulfill the 5% eligibility requirement for PRFI emissions, utilize the Meet eligibility button on the Hopp wizard for an auto-fill option. Of course, manual input is also available for the amount.

(IMAGENES)

3. (Optional) Enhance with PRFI. If you aim to amplify the pLP you're constructing, you have the option to include PRFI in the mix. The system will automatically compute and populate the amount of the primary asset needed to form the pair. You can either provide PRFI directly from your wallet or utilize vesting PRFI without facing any early-exit penalties. This step is entirely voluntary but has the potential to augment the value of the pLP you're hopping and locking.

(IMAGEN)

4. (Optional) Customize Slippage. If you have a particular preference for slippage tolerance, navigate to the "Slippage" option in the Hopp wizard. The default setting is 5%. Adjust this percentage to align with your risk tolerance. If the price undergoes unfavorable changes beyond this percentage, your transaction will automatically revert.
5. Choose your Flik duration. The longer you lock, the higher the multiplier for your share of platform fees.

(IMAGENES)

## ~~APR Calculations~~

Let's review how the locking APR is calculated for a locking duration of 1 month:

**Example: 1 month locking APR:**\
\- Definition: Current locking APR for 1 month\
\- Calculation: (Total 1 Month Lockers’ Share of Annualized Protocol Fees) / (Total 1 Month Lockers’ Share of pLP Pool Size)\
\
**1 Month Locker Share of Protocol Fees:**\
\*\*-\*\*Calculation: (1 Month Locker Share of Protocol Power / Total Protocol Locking Power)\
\
**Total Protocol Locking Power:**\
&#xNAN;**-** Calculation: (1 Month Lockers Share of pLP Pool Size \* 1 Month Locker Multiplier (currently 1x)) + (3 Month Lockers’ Share of pLP Pool Size \* 3 Month Locker Multipler (currently 4x)) + (6 month Lockers’ Share of pLP Pool Size \* 6 month Lockers’ Multiplier (currently 10x)) + (12 month Lockers Share of pLP Pool Size \* 12 Month Locker Multipler)) = Total Protocol Locking Power\
\
**Your New Annual Rewards:**\
&#xNAN;**-** Definition: User projected annual rewards, in USD terms, based on both PRFI rewards and Protocol fees:\
-Calculation: (Projected user daily PRFI rewards \* 365) + (Projected user daily protocol fees \* 365)\
\
(IMAGEN)

## ~~Confirm Your Hopp~~

In this concluding step, users can verify their final hopping details.

In the provided example, 21 ETH is utilized from the wallet to hop into cLP, and the chosen locking duration is also displayed.

## Transaction Completion

Once the transaction is finalized, you'll become a participant in the liquidity pool and start receiving platform fees!

A friendly reminder that fliking into pLP will lock your LP tokens for the specified time period (one to twelve months) and can be unlocked after that duration. You can check your lock expirations from the Manage Prime Finance page.

## ~~Slippage and Other Considerations~~

To manage slippage, click the icon at the top right. Then, input your slippage tolerance and the maximum percentage you're willing to lose. Setting your maximum tolerance for slippage safeguards you up to that amount. When you hit "Confirm" to execute a Flik, an error may prompt you to reload the page or increase your slippage tolerance.

Keep in mind that providing liquidity carries some risk, as the value of your LPs may fluctuate, and impermanent loss is possible. ~~Balancer explains the reduced impermanent loss in their Medium article, which also applies to Prime Finance's pLP on Arbitrum.~~
