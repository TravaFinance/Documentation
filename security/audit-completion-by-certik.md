# Audit completion by Certik

## **Audit Scope**

The audit focused on the following considerations:

* Testing the smart contracts against both common and uncommon attack vectors.
* Assessing the codebase to ensure compliance with current best practices and industry standards.
* Ensuring contract logic meets the specifications and intentions of the client.
* Cross-referencing contract structure and implementation against similar smart contracts produced by industry leaders.
* Thorough line-by-line manual review of the entire codebase by industry experts

## **Findings:**

There are seven issues found in total, including 1 Minor Finding, 2 Informational Findings, and 4 Major Findings.

Firstly, one Minor and Two Informational Issues concern some coding styles and Gas Optimization. They relate to unused functions, missing zero addresses checking, and function type. We heeded the advice and resolved these issues.

Secondly, all four Major Issues are related to Centralization. The owners of the following contracts below can execute some functions without obtaining the consensus of the community:

* FactoryRegistry,
* AddressesProviderFactory
* PoolUpdateControl
* LendingPoolConfigurator&#x20;

## **Certik Recommendations for the Centralization Issue:**

Certik advised to carefully manage the governance/guardian account’s private key to avoid any potential risks of being hacked. In general, Certik strongly recommended centralized privileges or roles in the protocol to be improved via a decentralized mechanism or via smart-contract-based accounts with enhanced security practices, e.g. Multisignature wallets.

Some feasible solutions recommended by Certik that would also mitigate the potential risk include:

* Time-lock with reasonable latency, i.e. 48 hours, for awareness on privileged operations;
* Assignment of privileged roles to multi-signature wallets to prevent a single point of failure due to the private key;
* Introduction of a DAO/governance/voting module to increase transparency and user involvement.

## **Trava Solutions for the Centralization Issue**

Trava has partially resolved these issues via smart-contract-based accounts. In particular:

* Deploy a Multi-Signature wallet in BSC mainnet at the address:&#x20;

0xdF73aC573Dfd430f4C5558B8CbeD86e86145501B

* Set up the owner of the contracts and governance to the multi-signature wallet.

Although these issues are major, our approach can avoid the potential risks of centralization. Moreover, in our roadmap, we will enable DAO Functionalities in Q2–2022. The introduction of the DAO module will completely resolve the centralization issues. This approach will make our community control the process and activity of Trava Finance in the near future.
