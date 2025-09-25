# Omnichain Gas Deposit Mechanism for Incentives Synchronization

#### Abstract

Incentive distribution across multiple blockchains requires a unified accounting system. To address this, PrimeFi introduces an **Omnichain Gas Deposit Mechanism** that allows users to seamlessly synchronize their activity on sidechains (e.g., HyperEVM) with the **Mainchain Incentives Controller** (e.g., Base). This design ensures that all user actions, such as deposits, borrows, transfers, and repayments, are consistently reflected in the global rewards calculation, independent of the originating chain.

#### Motivation

As DeFi ecosystems become increasingly multichain, sidechains and rollups provide scalability and cost efficiency, yet incentive programs must remain **globally coherent**. Without cross-chain aggregation, rewards distribution risks becoming fragmented, undermining fairness and efficiency. Our mechanism addresses this gap by enabling users to prefund the cost of cross-chain execution through a dedicated gas deposit, ensuring reliable and timely synchronization of incentive, related activity.

#### System Overview

1. **User Action on Sidechain**
   * A user performs an action (deposit, borrow, transfer, repay) on the Sidechain Incentives Controller (e.g., HyperEVM).
   * This action must be registered on the Mainchain Incentives Controller (e.g., Base) to update the global rewards ledger.
2. **Gas Deposit for Omnichain Execution**
   * The user deposits a small amount of gas into the protocol.
   * This reserve is dedicated to omnichain message delivery, guaranteeing that sidechain actions can be transmitted and executed on the mainchain.
3. **Omnichain Message Relay**
   * The protocol packages the user’s action into a cross-chain message.
   * Using the deposited gas, the message is relayed from the sidechain to the mainchain.
   * The Mainchain Incentives Controller executes the mirrored action, updating the global rewards state.
4. **Global Rewards Consistency**
   * Regardless of the originating chain, the mainchain maintains the **single source of truth** for rewards.
   * Users benefit from a unified and fair incentive program across all supported networks.

#### Key Benefits

* **User-Friendly Participation:** Users only need to deposit gas once; the protocol automates the complexity of cross-chain execution.
* **Fair Rewards Distribution:** All user actions, regardless of chain, are accounted for in the global rewards ledger.
* **Scalability:** High-volume activity occurs on sidechains, while the mainchain preserves a consolidated and lightweight reward state.
* **Security:** By centralizing reward accounting on the mainchain, the system prevents inconsistencies or double-counting across chains.

#### Example Flow

* Alice deposits a small amount of gas into the omnichain mechanism.
* She provides liquidity on HyperEVM.
* The protocol relays her deposit action to the Mainchain Incentives Controller on Base.
* The mainchain updates Alice’s rewards balance in the global ledger.
* Alice’s contribution is now recognized in parity with users across all supported chains.

#### Conclusion

The **Omnichain Gas Deposit Mechanism** is a cornerstone of PrimeFi’s multichain architecture. It ensures that user actions on sidechains are faithfully represented in the global rewards system, combining the **scalability of sidechains** with the **consistency of a mainchain-based incentive model**.
