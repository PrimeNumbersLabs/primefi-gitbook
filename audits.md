# Audits

### Audits — PrimeFi Core

PrimeFi's smart-contract suite has undergone multiple independent reviews. Each review is limited to its stated scope, code revision, assumptions, and review date.

{% hint style="warning" %}
An audit is a point-in-time assessment, not a guarantee that a deployment is secure or that later integrations and configuration changes are covered.
{% endhint %}

***

<details>

<summary><strong>⚡ Pre-Audit — Gerard Persoon (Code4rena Top Warden)</strong></summary>

| Field               | Detail                                                                     |
| ------------------- | -------------------------------------------------------------------------- |
| **Scope**           | Core Lending, pLP Locking, OFT Bridge                                      |
| **Date**            | February 2025                                                              |
| **Status**          | Review completed; consult the revision repository for its findings and reviewed code |
| **Auditor profile** | [https://code4rena.com/@gpersoon](https://code4rena.com/@gpersoon)         |
| **Revision repo**   | [https://github.com/gpersoon/PrimeFi](https://github.com/gpersoon/PrimeFi) |

</details>

***

<details>

<summary><strong>🛡 Full Audit #1 — PeckShield</strong></summary>

| Field      | Detail                                                                                                                                            |
| ---------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Scope**  | Lending markets, liquidation engine, Chainlink oracle integration                                                                                 |
| **Date**   | April 2025                                                                                                                                        |
| **Status** | Report published; findings and remediation claims should be evaluated against the report's reviewed revision and deployed code                  |
| **Report** | [https://drive.google.com/file/d/1TLig0aCVzmdpwOvYbE\_S3JX-BOYIGwVG/view](https://drive.google.com/file/d/1TLig0aCVzmdpwOvYbE_S3JX-BOYIGwVG/view) |

</details>

***

<details>

<summary><strong>🔍 Full Audit #2 — QuillAudits</strong></summary>

| Field      | Detail                                                                               |
| ---------- | ------------------------------------------------------------------------------------ |
| **Scope**  | Cross-chain messaging (LayerZero), security-admin modules                            |
| **Date**   | May 2025                                                                             |
| **Status** | Public report page available; formal sign-off has not been independently verified for this documentation |
| **Report** | [See report](https://www.quillaudits.com/leaderboard/prime-numbers/prime-numbers-v3) |

</details>

***

#### Scope and deployment mapping

The currently published audit entries do not identify exact reviewed commit hashes or provide a complete mapping from each reviewed revision to every deployed implementation and configuration.

Until that mapping is published, users and integrators should not infer that a report covers later integrations, deployments, upgrades, or configuration changes merely because a broad component category appears in its scope.

Future review completion and resulting deployment changes should be documented without treating them as a guarantee against vulnerabilities.
