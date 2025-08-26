# Liquidations

Liquidation is a procedure triggered when a borrower's Health Factor falls to 1 or below, as their collateral value fails to adequately cover their loan or debt value. This scenario may arise from a decline in the value of the collateralized asset or an increase in the borrowed debt.

<figure><img src="../.gitbook/assets/image (135).png" alt=""><figcaption></figcaption></figure>

To mitigate the risk of liquidation, you can either repay outstanding loans or deposit additional collateral to increase your Health Factor.

## Liquidators

Liquidators are adept DeFi users who employ automated systems, such as bots, to monitor collateralized positions. These bots interact with the protocol's L2Pool contract and initiate a liquidationCall().

This process allows liquidators to pay off a portion of the debt and receive discounted collateral as a liquidation bonus.

The incentive structure encourages third parties to participate in maintaining the protocol's health, ensuring that borrows across the protocol maintain sufficient collateralization.

## In a liquidation scenario

* Bob deposits 10 ETH and borrows 5 ETH worth of DAI
* If Bob’s Health Factor drops below 1, his loan will be eligible for liquidation
* A liquidator can liquidate up to 50% of a single borrowed amount (in this case, 2.5 ETH worth of DAI)
* In return, the liquidator can claim a single collateral, which is ETH, at a 7.5% bonus
* The liquidator claims 2.5 + 0.1875 ETH for repaying Bob's bad debt (2.5 ETH worth of DAI)
* 0.1875 ETH is claimed by the protocol at a 7.5% bonus (15% total penalty)
* After liquidation, Bob has 7.125 ETH (10-2.5-0.1875-0.1875 ETH) of supplied ETH collateral and 2.5 ETH worth of DAI borrowed.

## Liquidation Penalty & Risk Parameters

The total liquidation penalty is 15%, with half (7.5%) allocated as a bonus to liquidators and the other half directed to the PrimeFi Treasury. This allocation allows the company to fund new initiatives without the need to sell PRFI tokens on the open market.

Each asset within PrimeFi l has specific risk-related values that influence their supply and borrowing dynamics.

<figure><img src="../.gitbook/assets/Copia de PF Whitepaper.jpg" alt=""><figcaption><p>Final information available on mainnet.</p></figcaption></figure>
