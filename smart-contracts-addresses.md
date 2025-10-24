# Smart Contracts Addresses

## HyperEVM Deployment Addresses

> (Environment: HyperEVM)

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

* "Diamond" controller: `incentivesControllerDiamond` centralizes incentive facets.
* Prefix legend: `p` = interest-bearing (aToken equivalent), `vd` = variable debt token.
* Ensure no address collisions when migrating or exporting these values.

***

## Base Mainnet Deployment Addresses

> (Environment: Base mainnet)

### Core Protocol

| Component                            | Address                                    |
| ------------------------------------ | ------------------------------------------ |
| LendingPool                          | 0x8a619D8E3BfAb54F7C30Ef39Ce16c53429c739C3 |
| LendingPoolAddressesProvider         | 0xBC2adF6bEE6E8468f9E60DFC017D4E2Ce682be0C |
| LendingPoolAddressesProviderRegistry | 0xBfeE735e3868f8990787CCEAA4B920C9Ed162b07 |
| WETH Gateway                         | 0x065fd3ba477c85503BFac48be7D1a2fcAdA02847 |
| PoolHelper                           | 0x69A3c30A85aA1E22791466a08819c1080f0Aab7f |
| Base Asset (WETH)                    | 0x4200000000000000000000000000000000000006 |
| Wrapped Base Debt Token              | 0xaaE0D3C0b4aa454cEb5b5346ba1E95a86395D656 |

### Token & Yield Management

| Component      | Address                                    |
| -------------- | ------------------------------------------ |
| PRFI Token     | 0x7BBCf1B600565AE023a1806ef637Af4739dE3255 |
| Compounder     | 0xb16aECAfA1310a1c51F66EbDF6Fb753BFa76450E |
| Looper         | 0x515fBd7124a782818bA6719E48e94c489BA769F4 |
| Price Provider | 0x04EDBF3904789d80B0C991e0B66577F2208A2bE6 |

### Oracles & Data

| Component                   | Address                                    |
| --------------------------- | ------------------------------------------ |
| Aave Protocol Data Provider | 0x7b7Cd09465ff2cab67360D5CD24A3Cc3ad0C856a |
| Aave Oracle                 | 0x2Bd11f0f5e36411D7587d8a8969f9db6C7022973 |
| Lending Rate Oracle         | 0xd719084151F1F47B7dcB937bB33845656580b79d |
| Data Stream Consumer        | 0x163A1e3cd4726F3C92EB005A942308029C27f64B |

### Incentives, Fees & Governance

| Component                       | Address                                    |
| ------------------------------- | ------------------------------------------ |
| Incentives Controller (Diamond) | 0x0c7558F634B3465fF7637500D5a710731393c8F2 |
| Eligibility Data Provider       | 0xE8DF0d0CbA73403Ca89e07E6dECa9252E1Af4084 |
| Middle Fee Distribution         | 0x7f2EBfB68BE75E56bB6c14C504BB0a0c0b6EB8df |
| Multi Fee Distribution          | 0x5b6D95545750f1bb1812F5c564d9a401D3DeBd80 |
| Bounty Manager                  | 0x95d7A59C230D184F16B497c3c1bb834CA397C241 |
| DAO Treasury                    | 0xF2e2A49631927108086268c68C559c63c3C8f73d |
| Staking Token                   | 0x87B417AF600312df37F551a05ae14bCC3d55bC36 |

### Cross-Chain / Messaging

| Component           | Address                                    |
| ------------------- | ------------------------------------------ |
| Stargate Borrow     | 0x944963ff76C7618EdbF926469A3f77a78D461D65 |
| Stargate Router\[0] | 0x27a16dc786820B16E5c9028b75B99F6f604b5d26 |
| Stargate Router\[1] | 0xdc181Bd607330aeeBEF6ea62e03e5e1Fb4B6F7C7 |

### Utility & Operational Helpers

| Component                       | Address                                    |
| ------------------------------- | ------------------------------------------ |
| Wallet Balance Provider         | 0x33cd734739c6DeD500fD080d476D93135cB813Ef |
| UI Pool Data Provider           | 0x1B2164d254c7fa14901d54fB1043fB228eacb8F6 |
| Stable & Variable Tokens Helper | 0xfEBC15460a5Af7bd5C0f2D6746AAb00c9531747D |
| aTokens & Rates Helper          | 0xeB3ba9f55eC6FA6395d64300EE2bB75F50E9E8e5 |
| Multicall3                      | 0xC7C567e10656eB2F4B1024757263a587Ac1942ad |
| LP Locker List                  | 0x7d08E488FA39E7f29701c90EB49cC766857895a8 |
| FLIK                            | 0x76C6452E7C4711ee986b4911243Ea20d8B28f506 |

### Token Addresses

#### Underlying Tokens

| Symbol | Address                                    |
| ------ | ------------------------------------------ |
| USDC   | 0x833589fCD6eDb6E08f4c7C32D4f71b54bdA02913 |
| WETH   | 0x4200000000000000000000000000000000000006 |
| CBBTC  | 0xcbB7C0000aB88B473b1f5aFd9ef808440eed33Bf |

#### Interest-Bearing pTokens

| Symbol | Address                                    |
| ------ | ------------------------------------------ |
| pUSDC  | 0xB9a14B24C6E669D24E76dab65f7c4dc52f68741C |
| pWETH  | 0x2a50Be4Df06202A239384e828D6e67F9F2fA954e |
| pcbBTC | 0x1fF5E0037B478547715a4CE337d9fcFF86A30401 |
| pPRFI  | 0x834695A5d33967f8cC27E6d15684c0aA36cA4375 |

#### Variable Debt vdTokens

| Symbol  | Address                                    |
| ------- | ------------------------------------------ |
| vdUSDC  | 0xDBEd51F298901987651FaF1dAed8Bb575942d406 |
| vdWETH  | 0xaaE0D3C0b4aa454cEb5b5346ba1E95a86395D656 |
| vdcbBTC | 0xC12bdD620A54149Df6B73Fad9726d387402a9066 |
| vdPRFI  | 0x47C4d740016411Bb8f5c9D9bDb3f866c9b46e0A4 |

### Notes

* Diamond architecture in `incentivesControllerDiamond` centralizes incentive facets.
* Prefix legend: `p` = interest-bearing token, `vd` = variable debt token, `cbBTC` = bridged/compound Bitcoin variant.
* Multiple Stargate Routers indicate multi-path or versioned routing support.
* Always verify addresses against official deployment logs before interacting in production scripts.
