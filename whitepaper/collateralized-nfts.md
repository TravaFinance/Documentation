# Collateralized NFTs

NFT has become an increasingly popular way to buy and sell digital artwork. They are non-fungible, which naturally means that they are illiquid. Bringing liquidity to the NFT space would unlock a myriad of possibilities. As of May 2021, there have been no lending projects that make use of NFT as collaterals, because unlike a fungible currency or common stock, NFT value is difficult to determine. TRAVA.FINANCE adds more flexibility to the illiquid world of NFT and allows NFT owners to earn an ROI without selling it.

TRAVA.FINANCE offers an innovative feature that prices NFTs based on auctions. After the auction, borrowers can use their NFTs as collateral. TRAVA.FINANCE auction mechanism is divided into two modes: auction-to-sell and auction-for-buy-right. The difference between two modes is the ownership of the digital asset after the auction. In the auction-to-sell mode, as soon as the auction ends and the auction winner pays the fee, he/she will immediately receive the auctioned NFT. Meanwhile, in the auction-for-buy-right mode, the winner cannot immediately buy the digital asset. After a certain amount of time specified in the auction, if the NFT owners cannot repay the loan, the auction winner can buy it at a low price. Otherwise, they get a considerable interest if the NFT owners repay the loan and get their NFT back.

The auction process is as follows:

1. The NFT owner opens an auction session; she sets (i) the legal crypto used in the auction, (ii) the initial price for her NFT, (iii) the countdown time for the auction session, (iv) the mode for her auction (i.e., _auction-to-sell or auction-for-buy-right_), and other auction terms.
2. TRAVA.FINANCE users, who are interested in the NFT, can join in the auction session. To encourage users to participate in auctions, at the end of the auction, TRAVA.FINANCE randomly selects several bidders and rewards them with TRAVA tokens extracted from the auction fees.\
   To guarantee that the bidders make their payment when they win the auction, TRAVA.FINANCE locks a number of their TRAVA tokens as soon as they join in the auction session and make a bid. When the auction finishes, they will immediately get their tokens back if they are not the winner. In case they are the winners, they can get their tokens back only if they pay for the auctioning NFT before the deadline.
3. In the _auction-to-sell_ mode, the auction winner will pay the owner the whole auction price to get the NFT.
4. In the _auction-for-buy-right_ mode, the auction winners have to pay a part of the auction price. We name the quotient of the amount the winners have to pay over the auction price "_auction-paid ratio_”. The auction-paid ratio is calculated from the creditworthiness of the lender, borrower, NFT, and the auction terms.\
   The NFT owners can use the cryptos paid by the auction winner as collateral for their loans. Once they repay their loan including the interest to the auction winners, they can get the NFT back. Otherwise, they will lose their NFT to the auction winners. These rules are all defined in the auction smart contract.

TRAVA.FINANCE provides benefits for all participants as described below.

* **NFT owners** can determine their NFT value based on the bid prices given by the auction participants. The value can be much greater than their initial expectation. They can either directly sell their NFT or use their NFT as collateral and earn profit without losing it. TRAVA.FINANCE thus increases the liquidity of NFTs and opens up a unique and exciting NFTFi marketplace.
* Based on the given number of auction bids, **bidders** have a corresponding chance to win the reward at the end of the auction session. This rewarding mechanism provides incentives for users to actively make a bid in the auction.
* **Auction winners** can get their desired NFT at a price lower than their bidding price (once NFT owners cannot repay the loan) or they can receive considerable interest from their loan to NFT owners (once NFT owners repay the loans and get their NFT back).
* The credit scores of **NFT owners, auction winners, bidders,** and **NFTs** can be improved after auctions.

The auction mechanism for NFT can also be applied to any type of digital asset. In our road map, TRAVA.FINANCE will implement this auction feature for various types of digital assets (e.g., stock token, smart contract).
