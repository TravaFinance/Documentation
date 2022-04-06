# Trava Credit Score

## **Where can I see my credit score?**

Go to [https://scoring.trava.finance/credit-score/orai](https://scoring.trava.finance/credit-score/orai) and connect your wallet, you will see your credit score right on the screen.

## **What is users’ credit score?**

In the financial sector, a credit score is a value that represents the creditworthiness of an individual; the higher the score, the better a borrower looks to potential lenders. Credit score evaluation is a distinctive technique that differentiates TRAVA.FINANCE and other decentralized lending approaches. TRAVA.FINANCE aggregates and analyzes all transactions of blockchain objects (e.g., user, wallet address, digital asset) on multiple networks. TRAVA.FINANCE then establishes links among them and evaluates their credit score in the most objective and transparent manner.

## **What benefits does credit score brings to users?**

\-For borrowers, the primary benefit is that they can borrow with a "preferential interest rate" if their credit score is high. They can also receive higher loan-to-value-ratio compared to other users

For lenders, who have high credit scores easily become LPs of different pools. Moreover, when they create a pool, their pool will have a higher credit score because the pool creator's credit score is also a criterion for the pool scoring. Especially, pool owners can rate borrowers’ credit and eliminate fraudulent accounts to increase capital efficiency and reduce the risk of bad debt.

## **How Credit scores for wallet addresses are calculated?**

To evaluate credit scores for wallet addresses, TRAVA credit scoring model will take into account 5 factors:

1. Total asset: represents the financial strength of the address.
2. Transaction history: TRAVA aggregates all transactions of a wallet address across all platforms to calculate various parameters such as (i) transaction amount, (ii) number of liquidations, etc.
3. Loans ratio: represents the debt position of an account, including the Loan-to-balance ratio and Loan-to-investment ratio.
4. Circulating asset: represents how active users are in the crypto market, contains (i) investment-to-total-asset ratio and (ii) ROE.
5. The last parameter is the trustworthiness of possessing assets. At present, TRAVA evaluates two types of digital assets: (i) token and NFT.

Each above parameter is normalized to the range of \[0, 1000], using a standardized score function that converts z-scores to the range. The z-score is calculated from the mean and the standard deviation from every corresponding parameter of all accounts. To be more specific, you can read this function in TRAVA whitepaper.

## **How the user's credit score will be updated?**

Our system has both periodic updates and instant updates. The instant update occurs when users actively make transactions such as deposit, withdraw, repay... Or when users view their credit score on our app. In case a user has not viewed their credit score and had no transactions for a long time, their credit score is still updated periodically and automatically, which can be weekly or monthly. We are still trying to optimize it.

## **Which objects does Trava evaluate credit score for?**

At the moment, Trava has been evaluating the credit scores for 3 types of Objects: Wallet addresses (users), tokens, and NFTs.

## **How to increase my credit score?**

To improve the credit score of your wallet, you would need to take into account our five parameters, i.e., Total asset, Transaction history, Loans ratios, Circulating assets, and Trustworthiness of possessing assets. For instance, you should increase your wallet balance with prestige coins and tokens, perform more transactions and become more active in the crypto market, maintaining good Loan-to-balance and Loan-to-investment ratios, supply more liquidity to lending pools, trade on lending DApps to earn as much profit as you can, avoid collateral liquidation while borrowing, and possess at least $1000 valuable token (e.g., Bitcoin, Ether, or BNB).

Besides, you need to be credible users for a long time. It is because to avoid fraud, TRAVA calculates some credit score parameters based on their average values in the last k days, where k depends on the volatility of the crypto market. Moreover, some parameters are assessed based on the “standardized score” function, which calculates the mean and the standard deviation of all accounts’ parameters. Thus, trying to be the best at some criteria would improve your credit score too.

## **Why did my credit score decrease?**

The reasons why your credit score drops might be: You have bad transactions such as borrowing liquidations, your balance decrease, your borrowing rate is higher, you are not active enough, etc...You can read our white paper to understand how the credit score mechanism functions. [https://docs.trava.finance/whitepaper/credit-score-evaluation](https://docs.trava.finance/whitepaper/credit-score-evaluation)
