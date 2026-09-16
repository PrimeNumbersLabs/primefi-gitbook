# Risks & Assumptions

## Collateral and Liquidation Risk

PrimeFi is designed for over-collateralized borrowing, but over-collateralization does not guarantee repayment or solvency. LTV, liquidation threshold, and liquidation bonus are configured per reserve. Fast price gaps, network congestion, unavailable liquidity, failed liquidator transactions, or an insufficient liquidation incentive can prevent liquidation from completing before a position develops bad debt. Users should maintain a Health Factor buffer rather than treat 1 as an operational target.

## Oracle Integration and Authorized Pushers

Borrow limits, Health Factor, withdrawals, and liquidations depend on the prices returned by the configured oracle. Where an oracle or adapter accepts pushed prices, its **authorised pusher roles are a critical trust boundary**. An authorised transaction proves only that a permitted key submitted the update; it does not prove that the value is economically correct.

Material oracle risks include:

* a compromised, mistaken, or misconfigured authorised pusher;
* stale, delayed, frozen, or out-of-order updates;
* missing or ineffective freshness checks;
* excessive price deviations or incorrect decimal and asset mappings;
* prices derived from markets too thin to resist manipulation; and
* low-liquidity collateral whose reported price cannot be realized at liquidation size.

These failures can inflate borrowing power, block valid borrowing or withdrawals, cause wrongful or missed liquidations, and create bad debt. Freshness limits, deviation checks, independent price sources, supply and borrow caps where implemented, monitoring, and reserve pauses can reduce risk, but users should verify deployed controls rather than assume they exist or will react in time.

Pausing is also a trade-off. A delayed pause can allow exposure to grow, while a broad or prolonged pause can restrict withdrawals, repayments, liquidations, or other risk-reducing actions depending on the deployed validation logic. Pause authority and authorised pusher keys therefore create operational and key-management risk in addition to smart-contract risk.

## Interest Rate and Liquidity Limits

All live reserves on Base, HyperEVM, and XDC use **variable-rate borrowing only**; stable-rate borrowing and switching are disabled. The two-slope utilization model changes incentives as liquidity becomes scarce, but it cannot guarantee repayments or new deposits. At high utilization, suppliers may be unable to withdraw the requested underlying, and new borrows or flash loans may fail for lack of available liquidity. A high displayed supplier rate is compensation for utilization and does not mean the underlying is immediately withdrawable.

## Reserve Factor and Administrative Parameters

The configured `reserveFactor` directs part of accrued interest to the protocol and reduces the portion contributing to supplier yield. Reserve factors, rate strategies, collateral parameters, oracle addresses, pause controls, and other settings may be changeable by authorised roles or through upgrades. Users should rely on current on-chain configuration, not examples or historical UI values, and should account for privileged-key and governance risk.

## Rewards and Eligibility

PRFI emission schedules, eligible pools, allocation points, eligibility criteria, and distribution mechanics are configurable. Accrued or displayed rewards do not guarantee future emissions, eligibility, claimability, or token value. Incorrect eligibility data, delayed updates, disqualification logic, contract underfunding, or authorised parameter changes can reduce or prevent expected rewards. PRFI price volatility and token inflation can also outweigh nominal reward rates.

## Smart-Contract, Upgrade, and Composability Risk

PrimeFi inherits and adapts **Aave v2 concepts**, but inheritance is not a safety guarantee. PrimeFi-specific modifications, deployment configuration, oracle adapters, cross-chain messaging, reward contracts, external integrations, and upgradeable proxies introduce additional code and operational paths. Bugs, malicious integrations, compromised admin keys, or unsafe upgrades can cause loss or lock funds.

Atomic operations such as flash loans guarantee only transaction-level repayment or reversion of the flash-loan leg. Flash liquidity can still amplify oracle manipulation and composability exploits when the overall transaction satisfies repayment. Audits and inherited code can reduce uncertainty but cannot eliminate smart-contract or economic risk.

Users should assess each network and reserve separately, monitor protocol communications and on-chain settings, and supply only funds they can afford to lose or have temporarily unavailable.
