# Trade-up Mechanism

The Trade-Up Mechanism allows NFT owners to combine multiple identical Armoury NFTs of the same rarity and the same type into a single higher rarity Armoury NFT of the same type. For example, multiple Silver Helmets can be traded up to a Gold Helmet. The idea of Trade-Up Mechanism is that NFT owners will be given a great opportunity to take advantage of their unused NFTs and then level up them to the higher rarity. With higher rarity, NFT owners can assemble items into Knight NFTs of higher rarity and farm them for a higher APR, allowing them to gain bigger profits. Moreover, the high rarity of the NFT will bring its owner a huge advantage in Auction mechanism in the future. In the meantime, our Trade-up Mechanism will help us solve the problem of redundancy of idle NFTs as we issue more chests.

4 Armoury NFTs of the same rarity and type will be assembled into a single NFT of higher rarity and the same type. The success rate of trading up will be based on a base rate, and increase with EXP.

* Success: A new NFT with higher rarity will be minted and transferred to the wallet of the user. In the meantime, four ingredient Armoury NFTs will be burnt. Furthermore, regardless of how much EXP the four burned NFTs had gained, the EXP of the new NFT will be 0.
* Failure: Users will only receive back three out of four ingredient NFTs, with the lowest EXP NFT being burned.

In our Trade-up Mechanism, each rarity has a failure rate called _baseFailureRate_ and a failure time threshold called _timeBase_. Moreover, the failure rate will be determined by the total EXP of all Armoury NFTs which are selected to do trade-up, this EXP is referred to as _collectiveEXP_. The EXP of selected Armoury NFTs is inversely proportional to the failure rate, which means that the higher the total EXP of selected NFTs, the lower the failure rate. If all 4 NFT pieces don't have any experience point, the failure rate is equal to the base failure rate.

|                  |                     |                   |                    |                       |
| ---------------- | ------------------- | ----------------- | ------------------ | --------------------- |
| **Trade-up**     | **Copper → Silver** | **Silver → Gold** | **Gold → Diamond** | **Diamond → Crystal** |
| **Failure Rate** | 50%                 | 60%               | 70%                | 80%                   |
| **Time Base**    | 8 days              | 20 days           | 64 days            | 200 days              |

$$
collectiveEXP = exp(nft1) + exp(nft2) + exp(nft3) + exp(nft4)
$$

The formula for failure rate will be calculated as belows:

![](https://lh4.googleusercontent.com/QUDvqth-MV9kvugfdEn72t80\_GR2IJLX3jwkfnA-d75rLNonSFTUX3KQcTVRWgfk\_SZspbG1-933WrYb15oj-WpRnoz7Iv4b44KiLHXMU4x6EvfxVh8oo\_TPfwFKXd3Teza0S-pV)

Where,

* _RFP: Relative Fail Percent_
* _b: Base Failure Rate_
* _x: Collective Experience of Ingredients_
* _t: Time Base of Rarity_

_If x = 0 then RFP = b_

_If x < t then RFP = b \* k, k > 50%_

_If x = t then RFP = b \* 0.5_

_If x > t then RFP = b \* k, k < 50%_

For example: All 4 NFTs are Diamond Weapons and have different EXP, respectively:

* NFT 1: 1000000 EXP
* NFT 2: 2000000 EXP
* NFT 3: 3500000 EXP
* NFT 4: 2500000 EXP

\=> x = 1000000 + 2000000 + 1500000 + 500000 = 9000000 EXP

&#x20;t = 200\*24\*60\*60 = 17280000

![](https://lh6.googleusercontent.com/arN08L9qbiztXp5NaaeIyeYKQUk1DDtRt3sABkFLZDFJci3c5DdRcNqzJUldeWTXf6oLSKvfVgvd\_jo\_IRlhZsBIEM\_IFEDpvTTs8i4xZGa6jlz0grATbQFqB1XWOT0fJYu\_gmFu)

Therefore, the failure rate of Trade-Up will decrease to 52.74%, meaning you will have a 47.26% chance of successfully trading up if your collective experience of your ingredient NFTs are like above.

Note that, due to the nature of the blockchain development language, the displayed result may vary very slightly around the exact computed value.

If you are in the failure rate, your NFT 1 with 1000000 EXP (the lowest EXP) will be burned and you will only receive the rest of your ingredient NFTs (NFT2, NFT3 and NFT4).
