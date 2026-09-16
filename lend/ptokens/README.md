# pTokens

### pTokens: Interest-Bearing Deposit Tokens

**pTokens** (interest-bearing tokens) are minted when users **deposit assets** into the protocol.\
They are the protocol's accounting tokens for supplied positions and accrued interest.

* **Primary function:** record the holder's underlying-denominated claim against a specific reserve.
* **Interest accrual:** PrimeFi stores a scaled balance and applies the reserve's liquidity index. As the index rises, the externally reported pToken balance—and therefore the accounted claim—rises.
* **Example:** supplying USDC mints `pUSDC`. A later withdrawal burns the applicable pUSDC amount and requests USDC from the reserve.
* **Important limitation:** pToken accounting does not guarantee immediate redemption, solvency, or a secondary-market price.

👉 In short: **pTokens represent the creditor (lender) side of the protocol.**

| Topic | Detail |
| --- | --- |
| **Symbol format** | `p<ASSET>`, for example `pWETH` or `pUSDC`. |
| **Lifecycle** | <p>• <strong>Minted</strong> when underlying is supplied.</p><p>• <strong>Burned</strong> when underlying is withdrawn.</p><p>• During liquidation, pTokens may be transferred or burned depending on the liquidation path.</p> |
| **Accounting denomination** | Protocol accounting expresses pToken balances in units of the underlying asset. This convention does not promise immediate conversion into underlying or guarantee that a pToken trades at the same price as the underlying on external markets. |
| **Interest accrual** | Each reserve has a liquidity index. The contract multiplies the holder's internal scaled balance by the current index when reporting the pToken balance. This is why the displayed balance can grow without a separate interest payment or a changing “price per pToken” claim. |
| **Wallet visibility** | pTokens are ERC-20 tokens and may appear in compatible wallets; the contract address may need to be added manually. Transfers can be subject to protocol validation when the tokens are used as collateral. |
| **Withdrawing underlying** | Navigate to **Dashboard → Deposits → Withdraw** to request the underlying. Execution depends on available reserve liquidity, reserve solvency, pause state, the user's collateral and Health Factor, and all other contract validations at transaction time. |
