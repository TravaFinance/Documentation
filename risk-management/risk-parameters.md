# Risk parameters

## **Loan To Value**

The maximum amount that can be borrowed for a specific mortgage is determined by the Loan To Value (LTV) ratio. For example, if the LTV is 75%, borrowers will be allowed to borrow 0.75 ETH worth of corresponding currency for every 1 ETH worth of collateral.

For a wallet, the maximum LTV is calculated as the weighted average of LTVs of collateral assets and their value. In particular, for a wallet that deposits the collateral assets that are worth in dollars $$C_1, \dots ,C_n$$,  and their LTVs corresponding to $$LTV_1,  \dots , LTV_n$$, maximum LTV is

$$
\frac{C_1 \times LTV_1  + \cdots + C_n \times  LTV_n }{C_1+\cdots+C_n}
$$

## **Liquidation Threshold**

The liquidation threshold is the percentage at which a position is defined as undercollateralised. For example, a Liquidation threshold of 80% means that if the value rises above 80% of the collateral, the position is undercollateralised and could be liquidated.

The difference between the Loan To Value and the Liquidation Threshold is a safety cushion for borrowers.

For each wallet, the liquidation threshold is calculated as the weighted average of the liquidation thresholds of the collateral assets and their value. In particular, for a wallet that deposits the collateral assets that are worth in dollars $$C_1, \dots ,C_n$$,  and their liquidation threshold, respectively, $$LT_1, \dots, LT_n$$ , the liquidation thresholds of wallet is

$$
\frac{C_1 \times LT_1 +  \cdots + C_n \times  LT_n}{C_1 +  \cdots + C_n}
$$

## **Health Factor**

For a wallet, these risk parameters enable the calculation of the health factor:

$$
H_f = \frac{C_1 \times LT_1+ \cdots + C_n \times LT_n}{B}
$$

where **** $$B$$ is total borrows (in dollars)**,** $$C_1,\dots,C_n$$ **** is  the values (in dollars) of collateral assets, and $$LT_1, \dots, LT_n$$ is their liquidation threshold, respectively. When $$H_f < 1$$ the loan may be liquidated to maintain solvency.

## Liquidation penalty

Liquidation penalty is a bonus applied to the price of collateral assets purchased by liquidators as part of the liquidation of a loan that has reached the liquidation threshold.

## **Reserve Factor**

The reserve factor allocates a share of the protocol's interests to a collector contract as reserve for the ecosystem.&#x20;

## Risk Parameters

### BSC Lending Pool

| **Reserve** | **Collateral** | **LTV** | **Threshold** | **Bonus** | **Reserve Factor** |
| ----------- | :------------: | ------- | :-----------: | :-------: | :----------------: |
| DAI         |       Yes      | 75%     |      80%      |     5%    |         10%        |
| USDC        |       Yes      | 80%     |      85%      |     5%    |         10%        |
| USDT        |       Yes      | 75%     |      80%      |     5%    |         10%        |
| ETH         |       Yes      | 80%     |     82.5%     |     5%    |         10%        |
| BNB         |       Yes      | 75%     |      80%      |     5%    |         15%        |
| BTCB        |       Yes      | 70%     |      75%      |     9%    |         20%        |
| BUSD        |       Yes      | 75%     |      80%      |     5%    |         10%        |
| AAVE        |       Yes      | 70%     |      75%      |     5%    |         10%        |
| ADA         |       Yes      | 70%     |      75%      |     5%    |         10%        |
| CAKE        |       Yes      | 70%     |      75%      |     5%    |         20%        |
| XRP         |       Yes      | 70%     |      75%      |     5%    |         20%        |
| DOGE        |       Yes      | 55%     |      60%      |     8%    |         20%        |
| DOT         |       Yes      | 70%     |      75%      |     5%    |         20%        |
| XVS         |       Yes      | 60%     |      65%      |     5%    |         20%        |
| FTM         |       Yes      | 75%     |      80%      |     5%    |         20%        |

### **FTM** Lending Pool

| **Reserve** | **Collateral** | **LTV** | **Threshold** | **Bonus** | **Reserve Factor** |
| ----------- | :------------: | ------- | :-----------: | :-------: | :----------------: |
| DAI         |       Yes      | 75%     |      80%      |     5%    |         10%        |
| USDC        |       Yes      | 80%     |      85%      |     5%    |         10%        |
| USDT        |       Yes      | 75%     |      80%      |     5%    |         10%        |
| ETH         |       Yes      | 80%     |     82.5%     |     5%    |         10%        |
| BTC         |       Yes      | 70%     |      75%      |     9%    |         20%        |
| FTM         |       Yes      | 75%     |      80%      |     5%    |         20%        |

### ETH Lending Pool

| **Reserve** | **Collateral** | **LTV** | **Threshold** | **Bonus** | **Reserve Factor** |
| ----------- | :------------: | ------- | :-----------: | :-------: | :----------------: |
| DAI         |       Yes      | 75%     |      80%      |     5%    |         20%        |
| USDC        |       Yes      | 80%     |      85%      |     5%    |         20%        |
| USDT        |       Yes      | 75%     |      80%      |     5%    |         20%        |
| ETH         |       Yes      | 80%     |     82.5%     |     5%    |         20%        |
| BTC         |       Yes      | 70%     |      75%      |     9%    |         20%        |

## **Price Discovery**

The frequency of price updates is determined by the liquidation strategy. We use a margin method, which means that prices are refreshed whenever the deviation exceeds a certain threshold. For the price feed, we rely on Chainlink's decentralized oracles.

| **Name**     | **Symbol** | **Price updated every** | **Address**                                                                                                            |
| ------------ | ---------- | :---------------------: | ---------------------------------------------------------------------------------------------------------------------- |
| Binance USD  | BUSD       |           0.5%          | [https://data.chain.link/bsc/mainnet/crypto-usd/busd-usd](https://data.chain.link/bsc/mainnet/crypto-usd/busd-usd)     |
| DAI          | DAI        |            2%           | [https://feeds.chain.link/dai-usd](https://feeds.chain.link/dai-eth)                                                   |
| USDC         | USDC       |           0.1%          | [https://data.chain.link/bsc/mainnet/crypto-usd/usdc-usd](https://data.chain.link/bsc/mainnet/crypto-usd/usdc-usd)     |
| Tether       | USDT       |           0.1%          | [https://data.chain.link/bsc/mainnet/crypto-usd/usdt-usd](https://data.chain.link/bsc/mainnet/crypto-usd/usdt-usd)     |
| Ethereum     | ETH        |           0.1%          | [https://data.chain.link/bsc/mainnet/crypto-usd/eth-usd](https://data.chain.link/bsc/mainnet/crypto-usd/eth-usd)       |
| Binance coin | BNB        |            1%           | [https://data.chain.link/bsc/mainnet/crypto-usd/bnb-usd](https://data.chain.link/bsc/mainnet/crypto-usd/bnb-usd)       |
| BTCB         | BTCB       |           0.1%          | [https://data.chain.link/bsc/mainnet/crypto-usd/btc-usd](https://data.chain.link/bsc/mainnet/crypto-usd/btc-usd)       |
| AAVE         | AAVE       |           0.2%          | https://data.chain.link/bsc/mainnet/crypto-usd/aave-usd                                                                |
| ADA          | ADA        |            1%           | [https://feeds.chain.link/ada-usd](https://feeds.chain.link/ada-usd)                                                   |
| CAKE         | CAKE       |           0.2%          | [https://data.chain.link/bsc/mainnet/crypto-usd/cake-usd](https://data.chain.link/bsc/mainnet/crypto-usd/cake-usd)     |
| XRP          | XRP        |           0.2%          | [https://data.chain.link/bsc/mainnet/crypto-usd/xrp-usd](https://data.chain.link/bsc/mainnet/crypto-usd/xrp-usd)       |
| DOGE         | DOGE       |           0.2%          | [https://data.chain.link/bsc/mainnet/crypto-usd/doge-usd](https://data.chain.link/bsc/mainnet/crypto-usd/doge-usd)     |
| DOT          | DOT        |           0.2%          | h[ttps://data.chain.link/bsc/mainnet/crypto-usd/dot-usd](https://data.chain.link/bsc/mainnet/crypto-usd/dot-usd)       |
| XVS          | XVS        |           0.3%          | [https://data.chain.link/bsc/mainnet/crypto-usd/xvs-usd](https://data.chain.link/bsc/mainnet/crypto-usd/xvs-usd)       |
| FTM          | FTM        |           0.5%          | [https://data.chain.link/fantom/mainnet/crypto-usd/ftm-usd](https://data.chain.link/fantom/mainnet/crypto-usd/ftm-usd) |
