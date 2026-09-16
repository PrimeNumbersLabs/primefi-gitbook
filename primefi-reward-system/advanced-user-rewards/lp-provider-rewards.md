# LP Provider Rewards

Lenders may go one step further than earning the supply-side interest associated with their lending position.

This situation arises when a lender locks the currently required value of the network's **configured pLP staking token**. The ratio is configurable and was 5% at the time of writing. Not every LP or concentrated-liquidity position qualifies; verify the current ratio and eligible contract on the [pLP Pools](../../prime-liquidity-provider-plp/plp-pools.md) page and on-chain.

The pLP must be locked for one of the supported periods to qualify for configured PRFI emissions. Eligibility does not guarantee a particular emission amount, APR, or yield.

There are two ways to form the pLP position:

1. Borrow against lend deposit
2. Extra capital

Published lock-up periods range from 30 to 360 days. The selected period affects the applicable reward multiplier. See [Maximum APR by asset](../../prime-liquidity-provider-plp/maximum-apr-by-asset.md) for more information and verify current options in the live app.

### LP Actors

These two ways of forming a position create two types of users:

* **PrimeFi LP Provider (borrow-funded)**\
  Lender + Borrower + LP Provider\
  Refers to users who, after making a lending deposit, borrow the assets needed to create an LP position. They may receive supply-side interest on their deposit, owe borrowing costs on borrowed assets, and qualify for configured PRFI emissions while all pLP eligibility conditions remain satisfied. This does not mean they receive 100% of any borrowing-fee pool or recover all borrowing costs; net results depend on live rates, pool performance, fees, and current protocol configuration.

<figure><img src="../../.gitbook/assets/Copia de PF Whitepaper (6).jpg" alt="" width="563"><figcaption></figcaption></figure>

* **Pure LP Provider**\
  Lender + LP Provider (funds the currently required pLP ratio from their wallet without borrowing)\
  These are users who, after depositing in the protocol, add the required liquidity from their own wallet. They can qualify for configured PRFI emissions without borrowing from the protocol, provided they continue to meet the current pLP eligibility rules.

<figure><img src="../../.gitbook/assets/Copia de PF Whitepaper (7) (1).jpg" alt="" width="563"><figcaption></figcaption></figure>

