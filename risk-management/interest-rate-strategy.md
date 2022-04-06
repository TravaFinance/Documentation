---
description: This section describes the lending pool's interest rate parameters.
---

# Interest Rate Strategy

The interest rate strategy of Trava pool is designed to control liquidity risk while also maximizing utilization. The Utilisation Rate determines the borrow interest rates.&#x20;

Each token in each Pool has a utilization rate $$U_t$$  at each time  $$t$$, which is defined by the ratio $$U_t = L_t/A_t$$where  $$L_t$$ represents total borrows and $$A_t$$ represents total liquidity. This ratio regulates how much of a deposited token is used in the market.

When this ratio approaches 100%, there will be a scarcity of tokens in the Pool. The borrower will be unable to borrow at this time, and the lender will be unable to withdraw funds from the Pool. To avoid this, interest rate and risk parameters must be calculated in precise detail for each token.

## **Interest Rate Model**

Interest Rate Model tends to be a cost-effective way for the Pool to run itself. The parameters of the pool will aid in the adjustment of borrow and deposit rates to a balanced and reasonable point.

In practice, numerous models are used: linear rate, non-linear rate, and kinked rate. The kinked rate model is used in the Trava protocol. As with the non-linear model, such models have the virtue of significantly shifting the incentives for borrowers and lenders beyond some usage level. In contrast to non-linear models without a kink, they also introduce a point of abrupt change in the interest rate, beyond which interest rates begin to sharply rise.

The kinked model is based on several parameters and is described as follows. Firstly, the ratio optimal utilization rate $$U_\text{optimal}$$ is a parameter that determines the best-fit utilization rate for the protocol. It varies from token to token and depends on the risk and volatility of the token. For example, it could be 80% for stable tokens like DAI, or just 65% for unstable coins like LINK.

Next, the interest rate is a function that varies based on utilization rate. Three parameters are used to define this function: (1) Initial rate $$R_0$$, (2)  the constant $$R_\text{slope1}$$  is used when  $$U_t < U_\text{optimal}$$,  and  (3)  the constant $$R_\text{slope2}$$ is used when $$U_t \geq U_\text{optimal}$$.&#x20;

Specifically, the interest rate $$R_t$$ is defined by:

* If $$U_t <U_\text{optimal}$$  then     $$R_t = R_0 + \frac{U_t}{U_\text{optimal}} \times  R_\text{slope1}$$&#x20;
* If $$U_t \geq	 U_\text{optimal}$$ then $$R_t= R_0 + R_\text{slope1} + \frac{ U_t - U_\text{optimal}}{1 -U_\text{optimal}} \times R_\text{slope2}$$

The interest rates have a kink in them: they sharply change at a certain point. A variety of protocols use interest rates like this, including Aave and Compound. As users mint, redeem, borrow, repay, or liquidate tokens, the interest rate changes with the utilization rate  $$U_t$$ . As a result, it's also known as a variable interest rate. ****&#x20;

#### Interest rate parameters in Trava protocol

| **Token** | **Uoptimal** | **Base** | **Slope1** | **Slope2** |
| --------- | ------------ | -------- | ---------- | ---------- |
| DAI       | 80%          | 0%       | 4%         | 75%        |
| USDC      | 90%          | 0%       | 4%         | 60%        |
| USDT      | 90%          | 0%       | 4%         | 60%        |
| ETH       | 65%          | 0%       | 8%         | 100%       |
| BNB       | 65%          | 0%       | 10%        | 100%       |
| BUSD      | 80%          | 0%       | 4%         | 100%       |
| BTCB      | 65%          | 0%       | 7%         | 100%       |
| AAVE      | 65%          | 0%       | 7%         | 100%       |
| ADA       | 65%          | 0%       | 8%         | 100%       |
| CAKE      | 65%          | 0%       | 8%         | 100%       |
| XRP       | 65%          | 0%       | 8%         | 100%       |
| DOGE      | 60%          | 0%       | 8%         | 150%       |
| DOT       | 65%          | 0%       | 8%         | 100%       |
| XVS       | 65%          | 0%       | 7%         | 100%       |
| FTM       | 65%          | 0%       | 8%         | 100%       |

## **Borrow rate**

The borrow rate is calculated using the current interest rate$$R_t$$(per year)  and is updated every second.  That is, borrowers will be charged interest that changes every second. He must pay more interest if the Utilisation Rate is higher, and vice versa. Mathematically, at each time t, the Borrow rate (per second)  is $$B_t = R_t/Y$$  where $$Y= 31536000$$ is the number of seconds in a year. If the user is currently borrowing $$T_t$$ tokens then the interest payable is $$T_t \times B_t$$ . The interest payable is accrued to the loan in the next second, that is $$T_{t+1}=T_t(1+B_t)$$ .

## **Deposit rate**

Deposit rate and Borrow rate are closely linked. Precisely, at each time $$t$$, deposit rate  $$D_t$$ is determined based on  Utilization Rate $$U_t$$ and borrow rate $$B_t$$ and reserve factor $$r$$. Precisely, deposit rate is defined by $$D_t = U_t \times B_t\times  (1-r)$$.

In terms of probability, $$U_t$$ is probability that each token is borrowed, thus $$D_t$$ is the average value of interest earned from each token deposited into the Pool.&#x20;

For deposit, the calculation of interest is updated after each operation deposit, withdraw, borrow, repay. In particular, if a user is currently depositing $$T_t$$ tokens, after a period of time $$\Delta{t}$$ (in seconds) he will receive an interest of $$T_t \times  D_t \times \Delta{t},$$ and this interest is accrued to the deposited token, i.e. after time $$\Delta{t}$$ he have $$T_{t+\Delta{t}} = T_t \times  (1 + D_t \times \Delta{t}).$$
