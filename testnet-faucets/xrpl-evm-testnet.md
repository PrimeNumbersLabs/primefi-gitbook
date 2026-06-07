---
description: Get test XRP for gas and mint test reserves on the XRPL EVM testnet market.
---

# XRPL EVM Testnet faucet

To test the [XRPL EVM XRP market](../xrp-testnet-markets/xrpl-evm-testnet.md) you need test **XRP** for gas first, then the mintable reserve tokens.

{% hint style="info" %}
**Supported wallets:** connect with **MetaMask** or **Rabby**. Bifrost and Xaman do not support the XRPL EVM testnet yet, so they cannot connect here.
{% endhint %}

### Step 1: Get XRP (gas)

Claim test XRP from the official XRPL EVM faucet (supports Testnet and Devnet). Paste your wallet address and claim up to 90 test XRP.

{% embed url="https://faucet.xrplevm.org/" %}
XRPL EVM Faucet
{% endembed %}

Already holding XRP on the XRP Ledger testnet? Bridge it into the sidechain with Squid:

{% embed url="https://testnet.xrpl.squidrouter.com/" %}
Squid Testnet Bridge
{% endembed %}

### Step 2: Mint test reserves

In the PrimeFi app, switch to **v3 → XRPL EVM Testnet**, connect your wallet, and click **Get test tokens** above the markets table. Mint any single token, or **Mint all** at once:

| Token | Amount per mint |
| ----- | --------------- |
| USDC  | 100,000 |
| USDT  | 100,000 |
| RLUSD | 100,000 |
| WBTC  | 10 |
| WETH  | 100 |

{% hint style="info" %}
XRP is the native gas token here, so you supply it directly (or its wrapped form, WXRP). The stablecoins and wrapped assets above are mintable test mocks.
{% endhint %}

Once funded, head to the dashboard and start supplying or borrowing.
