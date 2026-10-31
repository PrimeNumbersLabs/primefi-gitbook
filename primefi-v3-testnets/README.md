---
description: >-
  PrimeFi v3 runs on Aave v3.7 with PRFI rewards on every chain. Try it with
  free test tokens on Base Sepolia, Ethereum Sepolia, Arbitrum Sepolia, XDC
  Apothem and HyperEVM testnet.
---

# PrimeFi v3 Testnets

PrimeFi v3 is the next generation of PrimeFi's money markets, built on **Aave v3.7**. Before it launches on mainnet, five testnet markets let you try every feature with free test tokens:

| Market | Chain ID | Gas token | Previews | Reserves | Prices |
| ------ | -------- | --------- | -------- | -------- | ------ |
| **Base Sepolia v3** | `84532` | ETH | Base | ETH, USDC, cbBTC | Chainlink |
| **Ethereum Sepolia v3** | `11155111` | ETH | Base | ETH, USDC, cbBTC | Chainlink |
| **Arbitrum Sepolia v3** | `421614` | ETH | Base | ETH, USDC, cbBTC | Chainlink |
| **XDC Apothem v3** | `51` | XDC | XDC | XDC, USDC | Mainnet prices |
| **HyperEVM Testnet v3** | `998` | HYPE | HyperEVM | HYPE, USDC, USDT0, UETH, UBTC | Mainnet prices |

Each testnet market mirrors the mainnet market it previews: the same assets, risk parameters, interest rates and E-Mode categories. Only the supply and borrow caps are higher, so testers don't fill them.

{% hint style="info" %}
These markets are **testnets**. Test tokens and test PRFI have no value, and testnet balances do not carry over to mainnet.
{% endhint %}

### What's new in v3

| | PrimeFi v2 | PrimeFi v3 |
| --- | ---------- | ---------- |
| Lending engine | Aave v2 fork | Aave v3.7 |
| PRFI rewards | Synced to Base by cross-chain message | Earned and claimed on each chain |
| Prepaid gas on HyperEVM / XDC | Required | **Not needed** |
| Eligibility for PRFI | Locked pLP worth 5% of deposits | Same rule, per v3 market |

v3 also brings **E-Mode** categories (higher borrowing power for correlated assets, such as two stablecoins) and **Multiply**, which loops a position to the leverage you choose in one transaction.

### Start testing

1. Open the [PrimeFi app](https://app.primefi.xyz/) and connect your wallet.
2. Open the market selector, choose **Browse all markets** and pick a market marked **Testnet** (for example **Base Sepolia v3**). The app asks your wallet to switch to, and if needed add, the network.
3. Get gas for that network from its faucet (below).
4. On the dashboard, click **Get test tokens** and mint test assets, test PRFI and test pLP.
5. Supply and borrow, try **Multiply** on an asset page, and lock pLP to earn PRFI.

### Getting test tokens

Every testnet wallet needs **gas** (the network's native token) and **test assets** (from the in-app faucet).

| Network | Gas faucet |
| ------- | ---------- |
| Base Sepolia | [Coinbase Developer Platform faucet](https://portal.cdp.coinbase.com/products/faucet) |
| Ethereum Sepolia | [Google Cloud Web3 faucet](https://cloud.google.com/application/web3/faucet/ethereum/sepolia) |
| Arbitrum Sepolia | [Alchemy faucet](https://www.alchemy.com/faucets/arbitrum-sepolia) |
| XDC Apothem | [Apothem faucet](https://faucet.apothem.network) |
| HyperEVM testnet | [Hyperliquid testnet faucet](https://app.hyperliquid-testnet.xyz/drip), then move HYPE from HyperCore to HyperEVM |

**Get test tokens** mints the test assets. Mint any single token, or **Mint all** at once:

| Token | Amount per mint | Testnets |
| ----- | --------------- | -------- |
| USDC | 10,000 | All five |
| cbBTC | 0.1 | Base Sepolia, Ethereum Sepolia, Arbitrum Sepolia |
| USDT0 | 10,000 | HyperEVM testnet |
| UETH | 3 | HyperEVM testnet |
| UBTC | 0.1 | HyperEVM testnet |
| PRFI (test) | 100,000 | All five |
| pLP (test) | 1,000 | All five |

{% hint style="success" %}
**Get test tokens** sits on the dashboard: next to **Explore markets** before your first deposit, then in the header of the **Deposits** card. ETH, XDC and HYPE are the networks' own tokens: supply them straight from your gas balance.
{% endhint %}

### Earning PRFI on v3

Every v3 testnet reserve emits test PRFI to eligible suppliers and borrowers. The rule is the same as on v2: **the pLP you lock on that chain must be worth at least 5% of your deposits in the v3 market**. A 10% price tolerance applies, so the app asks for 4.5%.

1. Supply to the market.
2. Mint test pLP with **Get test tokens**. A test pLP is worth about $1, so one mint (1,000 pLP) covers up to about $22,000 of deposits.
3. Click **Lock pLP** in the **PRFI rewards** card. Test pLP locks for 30 days.
4. Once your lock qualifies, the card offers **Start earning**: one transaction starts your PRFI right away. Otherwise it starts at the next eligibility refresh, which runs about every 20 minutes.
5. Click **Claim** whenever you like. On testnets PRFI goes straight to your wallet; on mainnet it will vest in MultiFeeDistribution, like v2 emissions.

{% hint style="warning" %}
Eligibility is re-checked as prices move, deposits grow and locks expire. The card warns you when your lock no longer covers your deposits and shows how much more pLP to lock. Keep a buffer above 5% to stay eligible.
{% endhint %}

Example: Ana supplies 10,000 USDC on Base Sepolia v3. She needs at least $450 of locked pLP; she mints 1,000 test pLP, locks it and starts earning.

### Prices on the testnets

* **Base Sepolia, Ethereum Sepolia and Arbitrum Sepolia** use Chainlink's testnet price feeds.
* **XDC Apothem and HyperEVM testnet** have no Chainlink feeds. Their test price feeds follow the mainnet prices of the production markets: a keeper copies a price whenever it moves more than 0.5%, and at least once a day.
* **Test PRFI** is priced at $0.10 on every testnet.

### Contract addresses

| Testnet | Pool | Looper (Multiply) |
| ------- | ---- | ----------------- |
| Base Sepolia | `0xD4CF6C0ecF9bA903169dd261e6eCcefD2239D308` | `0x7FE837e74f7C4e9c53aAd8Fe7ea346b34F3BC783` |
| Ethereum Sepolia | `0xe9639AfDd49A6dE783467b8d83eA5f938585C8A3` | `0xbb10bdf249805dF47e716F98252fe08eE15833a7` |
| Arbitrum Sepolia | `0x0a6192C5F3BA8555763220b3DB496644AcbcB1cb` | `0xF8e9a9c3D94acEeE2e38bf73b660a29D3baA8079` |
| XDC Apothem | `0x1c80B0a1bE3f784d99d9B1eff9489c900937eff6` | `0xF8e9a9c3D94acEeE2e38bf73b660a29D3baA8079` |
| HyperEVM testnet | `0x5D1CE9d5bBcFf19CC8aA67487C1956B2f4ceD550` | `0xfFc119CE83D48DfFbA6E0b645a4Cb84E83944449` |

The contracts' source code is verified on [Sourcify](https://sourcify.dev/), and explorers that read from it show the code.

The **Testnet status** page in the app (sidebar, in v3) shows every testnet price with how long ago it was updated, and when the keepers last ran.

### Feedback

Found a bug, or something unclear? Click the **Feedback** tab on the right edge of the app: pick Bug, Idea or Question and describe what happened. The app sends the page and market you're on, and your wallet address unless you untick it. Add a Telegram handle or email if you'd like a reply.
