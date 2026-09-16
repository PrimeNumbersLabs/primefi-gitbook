# Governance

## Current control model

PrimeFi is currently operated through administrator-controlled contract roles. There is no active governance timelock, and the protocol should not be described as fully decentralized.

Depending on the contract and assigned role, authorized operators can exercise critical powers that include:

* pausing and unpausing lending markets in an emergency;
* changing oracle sources and managing authorized oracle reporters or keepers;
* changing reserve and collateral risk parameters, including loan-to-value settings;
* administering proxy contracts and upgrading protocol implementations; and
* assigning or revoking protocol roles.

These permissions enable rapid emergency response, but they also create centralization, operational, and administrator-compromise risk.

## Recommended transition

PrimeFi's governance roadmap recommends migrating critical administrative control to a properly configured multisignature wallet. That transition should include:

1. multiple independent signers and documented approval thresholds;
2. separation of routine operations from narrowly defined emergency powers;
3. a timelock for non-emergency upgrades and risk changes;
4. a public inventory of privileged roles and the contracts they control; and
5. advance notice and on-chain references for planned governance actions when operationally safe.

Until those controls are deployed and verified on-chain, users should evaluate PrimeFi under its current operator-controlled model. See [Market Status](security/market-status.md).
