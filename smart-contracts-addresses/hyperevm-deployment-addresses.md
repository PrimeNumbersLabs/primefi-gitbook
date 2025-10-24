# HyperEVM Deployment Addresses

### Core Protocol

| Component                            | Address                                    |
| ------------------------------------ | ------------------------------------------ |
| LendingPool                          | 0xb339448E13E273f6F46e3390e0932Ab7fF9F113F |
| LendingPoolAddressesProvider         | 0x07093CA1E6c8c03Ff77dea07532F738d88De1D75 |
| LendingPoolAddressesProviderRegistry | 0x69A3c30A85aA1E22791466a08819c1080f0Aab7f |
| WETH Gateway                         | 0xac57f0D2f8ef17B8D26189Ba0Db353361374b2Ca |
| PoolHelper                           | 0x58933Fab624Ed4e6B7eb9e64Cb470bB61bE4de6d |
| Base Asset Wrapped (placeholder)     | 0x5555555555555555555555555555555555555555 |
| Wrapped Base Debt Token              | 0x9601C465c3c404465d968a2dda10FD807f2B2d5C |

### Token & Asset Managers

| Component      | Address                                    |
| -------------- | ------------------------------------------ |
| PRFI Token     | 0x7BBCf1B600565AE023a1806ef637Af4739dE3255 |
| Compounder     | 0xb0241128b4E66Ea783f12DcB2b73Ff19d8789E0e |
| Looper         | 0x1853D7da8986A3C20F9Ab51759e9a3967c5f89e8 |
| Price Provider | 0x198C93ebd82e9285376F43e2A98B8D58969Ad850 |

### Oracles

| Component                   | Address                                    |
| --------------------------- | ------------------------------------------ |
| Aave Protocol Data Provider | 0x3Bc108Ca0202739FC65bf453A255E5c49Ba6544a |
| Aave Oracle                 | 0x8Bd82c5f94d2CAFF3F980f0137f16aDD71E98dfb |
| Lending Rate Oracle         | 0x7169Bf0CCfb949D2Fa78A8BDaEe0410fBd617632 |
| Data Stream Consumer        | 0x04EDBF3904789d80B0C991e0B66577F2208A2bE6 |

### Incentives, Fees & Distribution

| Component                       | Address                                    |
| ------------------------------- | ------------------------------------------ |
| Incentives Controller (Diamond) | 0x95d7A59C230D184F16B497c3c1bb834CA397C241 |
| Eligibility Data Provider       | 0xB3Dd71A3Ef63B7BecEfbC68A87352Fcc4507BA97 |
| Middle Fee Distribution         | 0x1B2164d254c7fa14901d54fB1043fB228eacb8F6 |
| Multi Fee Distribution          | 0x33cd734739c6DeD500fD080d476D93135cB813Ef |
| Dao Treasury                    | 0xF2e2A49631927108086268c68C559c63c3C8f73d |
| Bounty Manager                  | 0x24498eb51a72D7CCa8e005e81Ed3c2E70f390778 |
| Staking Token                   | 0x981F145a71Da6DF4A7cBe892807782c9CC9a5515 |

### Cross-Chain / Messaging

| Component       | Address                                    |
| --------------- | ------------------------------------------ |
| Stargate Borrow | 0xB380637652CAfBb37e08ECafc015FfcB800618d0 |
| Stargate Router | 0xb88339CB7199b77E23DB6E890353E22632Ba630f |

### Utility & View Helpers

| Component                       | Address                                    |
| ------------------------------- | ------------------------------------------ |
| Wallet Balance Provider         | 0xa911aFd7dB4226cEe8073cDa2Da668B4CB918af9 |
| UI Pool Data Provider           | 0x7d08E488FA39E7f29701c90EB49cC766857895a8 |
| Stable & Variable Tokens Helper | 0xAb008ABd38aC3fB371D8C442d48E10225cd46DB6 |
| aTokens & Rates Helper          | 0x8C6357575Bbe7157612ba763Dd5CBdBDFABf83e8 |
| Multicall3                      | 0x5EB7Ed8e58E7eD4509612F3e9CcB5433ee822dc9 |
| LP Locker List                  | 0x6584BFE4d784BB8f1fd81D569a2202ce6F2F42Ad |
| FLIK                            | 0x4483564436120D7FbbaC8a346Ae0bbad4c8F219b |

### Token Addresses

#### Underlying Tokens

| Symbol | Address                                    |
| ------ | ------------------------------------------ |
| USDC   | 0xb88339CB7199b77E23DB6E890353E22632Ba630f |
| USDT0  | 0xB8CE59FC3717ada4C02eaDF9682A9e934F625ebb |
| WHYPE  | 0x5555555555555555555555555555555555555555 |
| UETH   | 0xBe6727B535545C67d5cAa73dEa54865B92CF7907 |
| UBTC   | 0x9fdbda0a5e284c32744d2f17ee5c74b284993463 |

#### Interest-Bearing pTokens

{% embed url="https://docs.primefi.xyz/lend/ptokens/contract-addresses" %}

#### Variable Debt vdTokens

{% embed url="https://docs.primefi.xyz/borrow/vdtokens/contract-addresses" %}

### Notes

* HyperEVM deployment leverages the EVM-compatible layer of the Hyperliquid ecosystem, with native access to its orderbooks and data infrastructure. [Messari+1](https://messari.io/copilot/share/understanding-hyperevm-852f32fb-bb9e-4aae-9eea-e2981faafe79?utm_source=chatgpt.com)
* The protocol on HyperEVM uses its own oracle and feed architecture tailored for Hyperliquid’s liquidity environment (not simply a copy of Base or other network feeds).
* **Prefix legend:**
  * `p` → interest-bearing token
  * `vd` → variable debt token
* Ensure there are **no address collisions** when migrating or exporting values across networks — each network uses a distinct deployment namespace.

