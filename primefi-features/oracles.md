# Oracles

This page describes the lending price sources currently configured for PrimeFi v2. Oracle systems reduce reliance on any single market venue, but they introduce integration, freshness, access-control, and operational risks.

{% hint style="warning" %}
See [Market Status](../security/market-status.md) for current availability. Oracle configuration can change; verify the live source, freshness, and risk parameters on-chain.
{% endhint %}

## HyperEVM

The active HyperEVM Data Streams path uses consumer [`0x113CA34C26ebb6f2e23B43ce5316d0fc03dFcce3`](https://hyperevmscan.io/address/0x113CA34C26ebb6f2e23B43ce5316d0fc03dFcce3). Asset-specific middleware reads prices from that consumer for the lending oracle.

| Lending price path | Active middleware |
| ------------------ | ----------------- |
| WHYPE / HYPE-USD | `0xEB30d7A22d8A3F9dDdE69262e3717E2aC293D24C` |
| UETH / ETH-USD | `0xF5e79f9ca2b30695AE9601ADfCd86dff7be42e25` |
| UBTC / BTC-USD | `0x1bD0185230131300FCB288730725693c33F7FdF1` |
| USDC / USD | `0x9231bfeb7541F6c34Bb57BC6a0172D42Ffb31AEd` |
| USDT0 / USD | `0x7f5D3d3B983786ec27ab5C136fc00E5CB38d12aC` |
| psXDC / XDC-USD | `0x2AD1fF28DD8C620AFD517691458182577f03AFF6` |

The consumer restricts report submission to approved keepers and rejects reports that fail its time-validity checks.

PRFI uses a separate owner-controlled price source rather than this Data Streams consumer. Its collateral loan-to-value ratio is currently `0`, so it cannot support new borrowing capacity.

## Base

Base uses native Chainlink Data Feeds for USDC, WETH, and cbBTC.

| Lending price path | Active source |
| ------------------ | ------------- |
| USDC / USD | Native Chainlink Data Feed |
| WETH / ETH-USD | Native Chainlink Data Feed |
| cbBTC / BTC-USD | Native Chainlink Data Feed |
| psXDC / XDC-USD | Consumer `0xB27eAf8270b6039B791a687A575c224a771eFeD7`, exposed through middleware `0x5760fa2cD1e47f8437bF6EFE930518966be649B1` |

PRFI uses a separate owner-controlled price source and has collateral LTV `0`.

## XDC

XDC uses **Plugin/GoPlugin aggregators funded in PLI** for its principal market price paths. It does **not** use eOracle/ePRICE for the current lending prices.

| Price path | Active Plugin/GoPlugin aggregator |
| ---------- | --------------------------------- |
| USDC / USD | `0xe5c7E623Aca88aCf0fe050BEE4F29B9deDedb9E2` |
| USDT / USD | `0x708307Fc1038fc922363bc3aeC4E3E2F93d25B33` |
| XDC / USD | `0x0b41e008E66c98788a25c952ff1a8c0cb2290f8C` |

PRFI uses a custom price source. The XDC `dataStreamConsumer` listed on the deployment-address page is not used by current lending prices.

## Integration guidance

Oracle configuration can change through protocol administration. Before integrating, verify the source configured in the network's lending oracle, the source contract, its latest update, and the current [market status](../security/market-status.md) on-chain.
