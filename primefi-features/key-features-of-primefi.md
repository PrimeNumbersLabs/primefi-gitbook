# Key Features of PrimeFi

PrimeFi combines lending markets, cross-chain workflows and token incentives in one interface. The interface also exposes markets with different operators, so users should confirm the selected version and market before transacting.

## Lending markets

* **PrimeFi v2:** PrimeFi-operated, over-collateralised lending and borrowing markets on Base, HyperEVM and XDC.
* **PrimeFi XRP testnets:** PrimeFi-operated Aave v3 markets on Flare Coston2 and XRPL EVM Testnet. Tokens and rewards in these markets are test-only. See [XRP Testnet Markets](../xrp-testnet-markets/README.md).
* **Fathom on XDC:** a third-party market operated by Fathom Protocol and surfaced in the app's v3 family. PrimeFi does not operate the Fathom contracts. See [v3 Markets and Fathom on XDC](../fathom-v3/README.md).

Collateral factors, borrowing limits, interest rates and liquidation thresholds are configured per market and reserve. A position's health factor can change as prices, debt and interest change; interface warnings cannot prevent liquidation.

## Cross-chain functionality and dependencies

Where enabled, PrimeFi's cross-chain borrowing and incentives synchronization use **Stargate** for cross-chain liquidity or routing and **LayerZero** for messaging. PRFI also uses LayerZero's Omnichain Fungible Token standard for supported cross-chain transfers.

These workflows depend on external protocols and infrastructure as well as the source and destination chains. They can be affected by message delivery, available liquidity, configuration, smart-contract failures or network disruption. Cross-chain functionality should not be treated as bridge-free or risk-free.

Some PrimeFi v2 workflows require a user-funded gas balance to pay destination-chain messaging costs. Availability and required amounts depend on the selected chain and action.

## Incentives and pLP

PrimeFi v2 can provide PRFI incentives, pLP boosts, locking and vesting where those modules are enabled. These features are not automatically available in every market and do not apply to third-party Fathom contracts or to the XRP testnet markets unless explicitly stated.

## NFT status

**PRFI NFT staking is live** and lets NFT holders stake PRFI under the current staking rules. Start with the [PRFI Staking overview](../prfi-staking/README.md).

Using NFTs as collateral in the lending market, NFT-backed borrowing and an integrated collateral marketplace are **planned features**, not currently available lending functions. Treat them as unavailable until a supported deployment and contract addresses are announced.

## Controls, audits and risk

Pause, upgrade and configuration capabilities are controlled by the operator and administrative roles for the selected market. This creates operator and upgrade risk; the responsible operator is Prime Numbers Labs for PrimeFi markets and Fathom Protocol for the Fathom market.

Published [audits](../audits.md) are point-in-time reviews of specified code and scope. They do not guarantee that contracts, integrations or deployments are free of vulnerabilities. Check [Market Status](../security/market-status.md), verify contract addresses and understand liquidation, oracle, cross-chain and administrative risks before using a market.

{% hint style="warning" %}
Supplying, borrowing, staking and cross-chain transfers can result in partial or total loss. Verify the active market, operator, network and contract addresses before approving a transaction.
{% endhint %}





