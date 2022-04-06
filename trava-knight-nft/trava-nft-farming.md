# Trava NFT Farming

Currently the users are provided with 5 vaults with minimum APR based on rarity as follows:

* Copper Vault: Adaptable minimum APR at 100%
* Silver Vault: Adaptable minimum APR at 125%
* Gold Vault: Adaptable minimum APR at 150%
* Diamond Vault: Adaptable minimum APR at 175%
* Crystal Vault: Adaptable minimum APR at 350%

|                             |            |            |          |             |             |
| --------------------------- | ---------- | ---------- | -------- | ----------- | ----------- |
| **Rarity**                  | **Copper** | **Silver** | **Gold** | **Diamond** | **Crystal** |
| **Distribution**            | 60%        | 25%        | 10%      | 4.5%        | 0.5%        |
| **Price (TRAVA)**           | 9,000      | 22,000     | 64,000   | 148,000     | 800,000     |
|   **Adaptable minimum APR** | 100%       | 125%       | 150%     | 175%        | 350%        |

Please note that APR can be changed according to NFT Marketplace conditions. We will recalculate and update the price based on the price on the market, the initial price and the data analysis extracted from our NFT Marketplace.

![](broken-reference)

**Note that** with each wallet, the maximum number of Trava Knight NFT that can be deposited in **one vault** is **one** Knight NFT. For example, if you have two Trava Knight NFTs of Gold, for example, you can only stake one of them into Gold Vault to farm and earn $TRAVA rewards.

_**With Copper, Silver and Gold Vault, if NFT owners withdraw their NFTs within 7 days, the farming rewards will decrease by 10%.**_

Knights with a higher rarity can be deposited in vaults of a lower rarity. Continuing the example above, one of your Gold Knights can be deposited in Gold vault and the other can be deposited in either Copper vault or Silver vault and earn APR corresponding to those vaults.

Furthermore, for Knight NFTs put in Farming vaults, we shall use the "Polish Mechanism”. After depositing Knight NFTs in those vaults, users must check their Knights on a regular basis through the Farming site, which is considered a polishing action. If users never check their Knights, the Glossiness of their Knights will deteriorate, and the Farming rewards will drop. So, to maintain the rewards from Knight NFTs, NFT owners must perform "polishing" action, which means check their NFTs in the vaults regularly.

## **Formula to calculate Farming rewards**

_**How to calculate the rewards for Copper, Silver and Gold Vaults?**_

Each vault has a value called _emissionPerSecond_. This is a fixed amount that all depositors will be rewarded when they deposit NFT per second. Therefore, the fewer number of people staking NFT, the more rewards each staker will get.

_**How to calculate the rewards for Diamond and Crystal Vaults?**_

The Glossiness of each NFT starts off at 100%, but it gradually decreases over time, affecting the incentives received when users deposit their NFTs in the vault. Users must complete "Polishing" acts in order to receive 100% of the rewards.

The amount of reward from NFT polishing shall be calculated using 2 parameters: _decayRate_ and _decayInterval_. Concretely, after a _decayInterval_ (a certain amount of time), if the NFT is not polished, the rewards for the next _decayInterval_ will be reduced (_decayRate_, calculated in % will decrease)

For example: _decayInterval_ = 2 days and _decayRate_ = 10% indicates that: every two days without polishing, the rewards of the next day will be reduced (due to the NFT glossiness). Hence, after 20 days, the amount of rewards for NFT will be 0.

If you stake NFT for a period _t_ = 9, the amount of incentives that you probably get is 450 Trava (On average per day you will get 450/9 = 50). However, you have forgotten to polish for 9 days. Then, the amount of rewards you receive is only 370 Trava. The amount of incentive you get is described as below:

|                   |       |       |       |       |       |       |       |       |       |
| ----------------- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- |
| **Day**           | **1** | **2** | **3** | **4** | **5** | **6** | **7** | **8** | **9** |
| **Minus Rewards** | 0%    | 0%    | 10%   | 10%   | 20%   | 20%   | 30%   | 30%   | 40%   |

|                              |       |       |       |       |       |       |       |       |       |
| ---------------------------- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- |
| **Day**                      | **1** | **2** | **3** | **4** | **5** | **6** | **7** | **8** | **9** |
| **Remaining Rewards(TRAVA)** | 50    | 50    | 45    | 45    | 40    | 40    | 35    | 35    | 30    |

The detailed calculation us as follows: (X is the rewards NFT depositor will receive after t days)

The average rewards each day NFT staker will receive:

$$
m = \frac{X}{t}
$$

Number of _decayInterval_ that depositor have to go through:

$$
n = \frac{t}{decayInterval}
$$

The result of this calculation will be rounded down.

* If n < $$1$$ , the rewards depositor will receive is: m $$*$$ t = X
* If $$1$$ **** $$\le$$ n $$\le$$ $$\frac{1}{decayInterval}$$

The percentage of minus rewards you get at the end of decayInterval period:

$$
p = ( n -  1)  *decayRate
$$

The total amount of incentives you will receive:

$$m  *[  (2 - p ) * n  *  \frac{decayInterval}{2} + (t - n * dacayInterval) *  (1 - p - decayRate) ]$$

* If $$\frac{1}{decayRate}$$< n:

The total amount of rewards you get:

$$
m * (\frac{1}{decayRate} + 1 )* \frac{decayInterval} {2}
$$

In the above example, we have _X = 450, t = 9_

We can calculate: _m = 50, n = 4, p= 0.3_

Put into the formula, we get:

$$
50 * [(2 - 0.3) * 4 * \frac{2}{2} + (9 - 4 * 2) * (1 -0.3 -0.1) ] = 370
$$
