# Architecture

![Figure 2: TRAVA.FINANCE'S Architecture](<../.gitbook/assets/image (5).png>)

TRAVA.FINANCE is divided into two main layers: TRAVA.FINANCE marketplace and TRAVA.FINANCE Foundation. The former uses the protocols and the cross-chain knowledge graph provided by the latter so that end-users can interact with TRAVA.FINANCE marketplace and perform their lending functionalities.

_TRAVA.FINANCE marketplace_ offers three lending roles for end-users. In other approaches, end-users can only participate in the lending business as either borrowers or lenders. In the TRAVA.FINANCE _marketplace_, pool owners may play the additional role for them to start their own lending business and obtain greater earnings. To this end, they create and maintain their own lending pool. TRAVA.FINANCE performs blockchain data analysis to help them adapt optimal pool parameters to their lending strategy.

In order for lenders, borrowers, and pool owners to perform lending business operations, TRAVA.FINANCE develops smart contracts divided into 5 groups: (1) Pool parameter optimization, (2) Cross-chain digital asset evaluation, (3) Credit score evaluation, (4) Digital asset (NFT, stoke token, etc.) auction-based pricing, and (5) Data analysis. These smart contracts are deployed on all nodes in the TRAVA.FINANCE network.

To enable cross-chain lending, _TRAVA.FINANCE_ marketplace also includes “Cross-chain Digital Asset Management” smart contracts, which interact with users’ digital assets on multiple blockchain networks. The smart contracts allow TRAVA.FINANCE to query users’ balance, aggregate their cryptos, or lock their certain amount of cryptos. These cross-chain interactions require a network of validators to participate in to collect, confirm, and verify cross-chain data.

TRAVA.FINANCE marketplace makes use of TRAVA.FINANCE foundation to communicate with other blockchain networks and implement the lending functionalities offered to end-users. TRAVA.FINANCE foundation is built on the hyper-linked datachain protocol. It uses three ToVChain's protocols, including (1) Data exchange protocol to enable interactions between TRAVA.FINANCE and other blockchain networks, (2) Data linking protocol to enrich the cross- chain knowledge graph with linked financial data collected from multiple chains, and (3) Cross- chain identification protocol to identify the same owner of multiple wallet addresses on single or multiple blockchain networks and thus facilitate fast and efficient mortgage placement. TRAVA.FINANCE foundation also uses the cross-chain knowledge graph to perform data analysis and evaluate users’ credit scores. The knowledge graph is presented in the next section.