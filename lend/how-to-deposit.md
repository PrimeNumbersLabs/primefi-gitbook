# How to Deposit?

{% hint style="danger" %}
Check [Market Status](../security/market-status.md) first. Deposits cannot be made while a market is paused.
{% endhint %}

1. Open **Markets** and select the network you intend to use: Base, HyperEVM, or XDC.
2. Confirm that your wallet is connected to the same network and that the selected market is operational.
3. Choose the asset and select **Deposit**.
4. Enter the amount. Review the live supply rate, available liquidity, collateral setting, and transaction details.

For example, after selecting USDC, enter the amount and press **Deposit USDC**.

<figure><img src="../.gitbook/assets/image (99).png" alt=""><figcaption></figcaption></figure>



If the lending pool does not have sufficient token allowance, the app first asks for an **Approve** transaction. This approval authorizes the specified contract to transfer up to the displayed allowance; verify the spender and amount in your wallet before confirming.

After approval confirms, select **Confirm Deposit** and review the supply transaction. A successful supply mints the corresponding pToken, which represents your accounting claim on the reserve and accrues interest according to the reserve's liquidity index. Withdrawals remain subject to available liquidity, market status, and protocol risk.

<figure><img src="../.gitbook/assets/image (100).png" alt=""><figcaption></figcaption></figure>
