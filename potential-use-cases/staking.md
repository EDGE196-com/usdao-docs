# Staking

Staking is the act of locking cryptocurrencies to receive rewards. It involves holding funds in a cryptocurrency wallet to support the security and operations of a blockchain network. Simple, staking is the act of locking cryptocurrency to receive rewards. Since every single USDAO token is a debt on the system we have to reduce the reward as the debt ratio rises to minimise the debt. This is the relationship between Debt ratio and Staking interest rate.

## Staking Business Overview

1\. User Balance: User will get his available USDAO balance.

2\. Total Staked Amount: User will able to get total staked amount. When the user stake’s USDAO then stake amount will be added in total staked amount and then user will claim staked amount after that the stake amount will be subtracted from total staked amount.

3\. Staking Approval: When user stake desired USDAO amount for particular time period first time then he needs to give approval to stake his/her USDAO balance. So he/she will get one approval on meta-mask pop-up after confirming that he/she can stake USDAO successfully. After first stake he don’t have to give approval but once USDAO balance got refresh(means new USDAO added) then if he/she stake added USDAO from Updated USDAO balance then system will ask for approval again.

3\. Staking without auto stake : User will click on stake button , user’s stake amount will be locked in contract and stake amount will be transferred to staking contract.

Reward – reward calculation for staking 6% on locked amount till end validity and 0.2% will be deducted on locked amount + staking platform fee as a platform fee.

4\. Auto Stake: User will stake USDAO with auto-stake. user’s stake amount will be locked in contract and stake amount will be transferred to staking contract.

Auto Stake Reward: reward calculation for staking 6% on locked amount until user will claim and 0.2% will be deducted on locked amount + staking platform fee as a platform fee.

5\. Multi staking : User can stake more than one time. He/She will get stakeId for his stake.

6\. Reward history : List of staking with detail and claim button.

7\. Claim : Claim button will be enable when end validity will match with current time stamp.

Insight : When user will claim his USDAO, then sum of next seven days claimed principal amount will be transferred from buffer pool to reserve pool and reserve pool will pay claimed amount to the user.

8\. Buffer pool : When user will stake USDAO then that amount will be locked in staking contract and locked amount will be transferred in buffer pool.

9\. Reserve pool : while claiming 0.1% of buffer pool will be transferred to reserve pool until reserve pool>claimed amount. Then reserve pool will pay total claimed amount to the user.

10\. Accumulated fee :All staking platform fee will be accumulated in buffer pool which is 0.2 % of claimed amount.

12\. TVL : Total locked USDAO on platform.

13\. Pool rotation : If buffer pool + reserve pool < claimed amount then user have to wait for seven day, So here we will set how many week we need to check in pool until buffer pool + reserve poll > claimed amount or buffer pool> claimed amount.
