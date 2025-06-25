# Key Features of PrimeFi

### PrimeFi: Key Feature Summary

<table><thead><tr><th>Area</th><th width="468">Description</th></tr></thead><tbody><tr><td><strong>Omnichain lending (LayerZero)</strong></td><td>Liquidity supplied on one EVM network can be borrowed against on another. Cross-chain messages are sent through LayerZero; no wrapped assets or third-party bridges are involved.</td></tr><tr><td><strong>PRFI as an OFT</strong></td><td>PRFI follows LayerZero’s <em>Omnichain Fungible Token</em> standard. A single canonical supply is tracked while tokens move natively between chains via Stargate-LayerZero.</td></tr><tr><td><strong>NFT collateral &#x26; marketplace</strong> (post-mainnet launch)</td><td>Selected NFT collections—including PrimeOrbs—can be pledged as collateral. Floor-price or oracle valuations set loan-to-value limits, and an internal market handles trading or collateral liquidation.</td></tr><tr><td><strong>Over-collateralised risk model</strong></td><td>Every position must maintain <strong>Health Factor ≥ 1</strong>. Oracle price feeds and interest-index updates recalculate HF on each transaction; the UI surfaces warnings before liquidation thresholds are reached.</td></tr><tr><td><strong>Security controls</strong></td><td>Core money-market code inherits audited Aave v2 contracts. New modules (cross-chain messaging, incentives, NFT logic) undergo independent audits and are covered by a live Immunefi bug-bounty programme. Upgrades use UUPS proxies with timelocks and an emergency pause guardian.</td></tr><tr><td><strong>Documentation &#x26; community tooling</strong></td><td>Self-service resources include step-by-step courses, an AI documentation assistant, and a public forum for support and governance discussions.</td></tr></tbody></table>

{% hint style="warning" %}
The integration of NFTs will occur after the main features of the protocol are launched on the Mainnet.
{% endhint %}





