# Lending & Borrowing

This page gives a conceptual view of the **PrimeFi v2** lending and borrowing contracts. It is not an ABI or integration specification, and the exact reserve configuration and addresses vary by network.

## Core lifecycle

1. **Supply:** a user supplies a supported reserve and receives interest-bearing [pTokens](../lend/ptokens/README.md) representing the supplied position.
2. **Use collateral and borrow:** an eligible supplied asset can be enabled as collateral. A borrow creates the corresponding [variable-debt token](../borrow/vdtokens/README.md) balance.
3. **Accrue and monitor:** interest indexes update supplied and borrowed balances. Oracle prices and reserve risk parameters determine borrowing capacity and [health factor](../borrow/health-factor.md).
4. **Repay or withdraw:** repaying reduces debt. If debt remains, a withdrawal must leave the account within the market's collateral requirements.
5. **Liquidation:** when an account crosses the configured liquidation threshold, an eligible liquidator can repay part of its debt and receive collateral under the market's [liquidation rules](../borrow/liquidations.md).

Cross-chain borrowing, where enabled, adds Stargate liquidity or routing and LayerZero messaging to this local-market flow; see [Stargate Borrow](stargate.md). Integrators should verify the selected network, current configuration and deployed address under [Smart Contracts Addresses](../smart-contracts-addresses/README.md).

The app's **v3** family uses separate Aave v3 deployments. The XRP testnets are PrimeFi-operated, while Fathom on XDC is third-party; see the [v3 market boundary](../fathom-v3/README.md).

## Contract overview

The diagram summarizes the principal actors and calls; it intentionally omits many checks and internal interactions.

![Lending and Borrowing Contract Overview](../.gitbook/assets/lending-borrowing.drawio.svg)

