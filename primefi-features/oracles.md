# Oracles

PrimeFi leverages decentralized oracle networks to ensure that price data is **secure, reliable, and tamper-resistant**. In most chains, **DataStreams** deliver continuous updates with low latency, while **DataFeeds** provide historical precision and compatibility. For key ecosystem tokens (e.g. PRFI, HYPE), we employ **DataLink**, which offers a dedicated oracle channel.

On **XDC**, all price data is sourced via **eOracles / ePRICE feeds**, which integrate with the AggregatorV3Interface. [EO Docs](https://docs.eo.app/docs/eprice/feeds-addresses/price-feed-addresses/xdc-network)

***

### Comparative Overview by Network & Assets

#### 1. Base Network

| Asset | Oracle Type           | Notes                                                          |
| ----- | --------------------- | -------------------------------------------------------------- |
| cbBTC | DataStream / DataFeed | Flexible usage depending on latency or historical requirements |
| USDC  | DataStream / DataFeed | Continuous feed or fallback feed as needed                     |
| ETH   | DataStream / DataFeed | Redundancy through feed fallback                               |
| PRFI  | DataLink              | Dedicated channel for PRFI-USD                                 |

#### 2. HyperEVM

| Asset | Oracle Type           | Notes                              |
| ----- | --------------------- | ---------------------------------- |
| HYPE  | DataLink              | Specialized oracle for HYPE-USD    |
| UETH  | DataStream / DataFeed | Similar logic to ETH               |
| PRFI  | DataLink              | Consistent with Base network usage |
| USDT0 | DataStream / DataFeed | Stream first, feed as fallback     |
| UBTC  | DataStream / DataFeed | Equivalent to cbBTC in HyperEVM    |

#### 3. XDC Network

_All oracles on XDC use **eOracles / ePRICE feeds**._

| Asset | Oracle Type           | Notes                                 |
| ----- | --------------------- | ------------------------------------- |
| XDC   | eOracle / ePRICE Feed | Price via eOracles                    |
| pxXDC | eOracle / ePRICE Feed | Synthetic / pegged derivative on XDC  |
| USDC  | eOracle / ePRICE Feed | Stablecoin feed via eOracle           |
| USDT0 | eOracle / ePRICE Feed | ePRICE feed for USDT0                 |
| PRFI  | eOracle / ePRICE Feed | Treated as standard asset feed in XDC |

***

### Technical Rationale

* **DataStreams** → Ideal for low-latency continuous updates (real-time trading).
* **DataFeeds** → Offer dependable historical data and broad compatibility.
* **DataLink** → Reserved for strategic tokens needing dedicated oracle infrastructure.
* **eOracles / ePRICE feeds (XDC only)** → Provide on-chain price feeds in the XDC ecosystem, integrated via AggregatorV3Interface. [EO Docs](https://docs.eo.app/docs/eprice/feeds-addresses/price-feed-addresses/xdc-network)

By combining these methods appropriately per network and asset, PrimeFi ensures the optimal balance of **performance, reliability, and accuracy**.
