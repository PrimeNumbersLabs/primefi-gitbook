# Withdraw

This functionality is the reverse of making a deposit. To use it, follow the same process but through the section labelled **“Withdraw”**.

<div data-full-width="true"><figure><img src="../.gitbook/assets/image (103).png" alt=""><figcaption></figcaption></figure></div>

Select the desired amount and submit the transaction.

The transaction succeeds only if the reserve has enough available liquidity, the market is not paused for withdrawals, and all contract validations pass. If liquidity is insufficient, additional supplies or borrower repayments may make a later withdrawal possible, but availability is not guaranteed.

If you have active debt, you may still withdraw collateral that is not required to keep the position valid. The contract recalculates the position using on-chain reserve and oracle state and blocks a withdrawal that would make the Health Factor invalid.

Health Factor values and warnings in the UI are informational estimates. They are not guaranteed to appear or remain current before execution; the contract's validation at transaction time is authoritative. A withdrawal can also fail because the reserve was paused, liquidity changed, prices moved, or another validation condition changed.

<figure><img src="../.gitbook/assets/image (67).png" alt="" width="303"><figcaption></figcaption></figure>
