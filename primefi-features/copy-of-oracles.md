---
hidden: true
---

# Copy of Oracles

PrimeFi relies on **Chainlink** as its decentralized oracle network of choice, providing highly secure, reliable, and tamper-resistant data.

The vast majority of price pairs in PrimeFi are powered by **Chainlink DataStreams**, ensuring low-latency updates, continuous reliability, and robust performance across both Base and Arbitrum instances.\
In specific cases, **DataFeeds** are used, and for PRFI-USD, a dedicated **DataLink** is integrated.

#### Supported Pairs

| Asset        | Oracle Type           |
| ------------ | --------------------- |
| **BTC-USD**  | DataStream / DataFeed |
| **ETH-USD**  | DataStream / DataFeed |
| **HYPE-USD** | DataStream            |
| **USDT-USD** | DataStream / DataFeed |
| **USDC-USD** | DataStream / DataFeed |
| **PRFI-USD** | DataLink              |
| **XDC-USD**  | DataStream            |

#### Why Chainlink?

* **DataStreams** (used in most cases) deliver continuous, low-latency market data, which is critical for maintaining protocol integrity.
* **DataFeeds** provide additional reliability where historical precision or broader compatibility is required.
* **DataLink** is specifically used for PRFI-USD, reflecting the token’s unique role within the Prime Numbers Labs ecosystem.

By combining these Chainlink services, PrimeFi minimizes risks of stale or manipulated price data, ensuring healthy loan positions, cross-collateralization, liquidations, and other core protocol functions.
