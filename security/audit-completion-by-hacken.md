# Audit completion by Hacken

This thorough security audit checked and ensured the following imperative points as 2 main Categories (1) Code review (2) Functional.

The audit report contains all found security vulnerabilities and other issues in the reviewed code. As a result of the audit, There are no critical issues in our contracts. Besides, Hacken’s security engineers found 4 high, 4 medium, and 3 low severity issues. Overall, after the auditing process, Hacken evaluated Trava’s contracts as **Well-Secured** (the highest level of security as the assessment).

## **Severity High**

There is one issue regarding the implementation function and three issues regarding uninitialized state variables:

* Issue 1 (unimplemented function): The logic of function finalizeTranfer has commented-out unimplemented logic. We heeded the advice and resolved these issues.
* Issues 2, 3, 4 (uninitialized state variables): Some state variables are not initialized for the contract LendingPoolCollateralManager but they are being called.
  * Trava’s Response: We consider the contract LendingPoolCollateralManager as a Logic Contract where we execute our code by using delegate call from LendingPool Contract. That explains why we don’t initialize the state for that variable.
  * Following the verification, Hacken determined that these are not issues.

## **Severity Medium**

There are three Issues concerning coding styles and Gas Optimization. They relate to unused imports, Not checked contract address, and No event on lendingPoolConfigurator change. We heeded the advice and resolved these issues.

There is one Issue concerning Possible FlashLoan attack in the LendingPool contract. Despite the fact that we do not believe this attack could happen in real life, we took great care in resolving the problem.

Description: IF both of TToken and its underlyingAsset are traded on multiple DEXes and have different rates there could be a FlashLoan attack. Attackers could FlashLoan a TToken, and process withdraw, which will give then the exact same amount of the underlyingAsset, and then calling deposit, they will receive the same amount of TToken.

Having the 1-to-1 “exchange” on the LendingPool and different rates on DEXes, attackers could “play” with the market many times in one transaction until they receive enough rewards. The same would work to borrow methods. So anyone could borrow without having assets but FlashLoaning them.

The same would work to borrow methods. So anyone could borrow without having assets but FlashLoaning them.

Hacken’s Recommendation: Consider some restrictions like minting/returning assets in the next block only.

Trava’s solution: Token transfer restrictions for transferring in the same block where minting occurred.

After the verification, Hacken concluded that the issue had been resolved completely.

## **Severity Low**

There are three Issues concerning coding styles and Gas Optimization. They relate to Unused state variable, public/external function, Unused function argument. We heeded the advice and resolved these issues.
