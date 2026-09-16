# Omnichain Gas Deposit for Incentive Synchronization

## Purpose

PrimeFi's reward architecture can mirror eligible activity from a sidechain incentives controller to the Base mainchain incentives controller. Cross-chain message delivery requires native gas on the sending side.

The omnichain gas-deposit mechanism lets a user prefund expected messaging costs. It funds relay attempts; it does **not** guarantee delivery, ordering, completeness, timeliness, or reward eligibility.

## Intended flow

1. A user performs an eligible action on a supported sidechain market.
2. The relevant controller prepares a LayerZero message representing the reward-accounting update.
3. Available prepaid gas funds the message-delivery attempt.
4. If LayerZero delivers and the destination call succeeds, the Base controller applies the corresponding accounting update.

Actual behavior depends on the deployed controller version, peer configuration, available gas, LayerZero endpoint behavior, destination execution, pause state, and reward-program configuration.

## Failure and reconciliation risk

Synchronization can be delayed or fail because of:

* insufficient prepaid gas;
* incorrect peer, endpoint, or chain configuration;
* source or destination pauses;
* network congestion or messaging outages;
* destination execution failure;
* duplicate, delayed, or out-of-order operational events; or
* unsupported actions or inactive reward pools.

Users should not assume that every lending action immediately creates a Base reward update. A failed or delayed message may require retry or operator reconciliation, depending on the deployed contracts and upstream messaging system.

## Costs and user checks

Before an action that uses synchronization:

* check whether the selected market and reward program are active;
* review the quoted or requested gas deposit;
* maintain enough native gas for the local transaction;
* verify the transaction destination and network; and
* confirm the resulting reward state rather than relying only on a submitted message.

Unused-balance withdrawal, retry, refund, and reconciliation behavior must be verified against the currently deployed controller and app. They are not guaranteed by this overview.

## Relationship to lending

This mechanism concerns **reward-accounting synchronization**. It does not secure the lending position, replace oracle checks, or execute the cross-chain borrow-delivery leg. Lending collateral, debt, Health Factor, and liquidation remain governed by the origin market's contracts and oracle configuration.

See [Omnichain Lending & Borrowing](omnichain-lending-and-borrowing/README.md), [Market Status](../security/market-status.md), and [Risks & Assumptions](../know-your-algorithm/risks-and-assumptions.md).
