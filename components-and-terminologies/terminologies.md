# Terminologies

## Terminologies used

## Terminologies used

## USDAO Terminologies

### USDAO Pool <a href="#reserve-pool" id="reserve-pool"></a>

The Ether that is deposited during the minting operation of either USDAO or ASSET token is deposited into the USDAO smart contract, also known as, the reserve pool. The reserve pool is the backbone of the whole system as it determines the health of the economy of the system. It helps determine the price of the ASSET token as well as determine the debt ratio.

### Mint Price <a href="#mint-price" id="mint-price"></a>

Mint price is the price at which USDAO stable coin is minted against Ether. It is relatively pegged to 1 US dollar worth of Ether. The current price at the time of minting one dollar's worth of ether, determined by the median ETH/USD price returned from the oracles.

The mint price is not subjected to any major fluctuations as its base price is fixed to 1 US dollar. This is intentional and is important to discourage any arbitraging opportunities.

### Burn Price <a href="#burn-price" id="burn-price"></a>

Burn price is the price at which the user withdraws back his Ether against the stable coins. Equivalent to the minting price the burn price is decided by the current ETH/USD prices returned from the oracles. The current price at the time of burning one dollar's worth of ether, determined by the median ETH/USD price returned from the oracles.&#x20;

### Fund Price

Fund Price Fund price is the price at which the ASSET token is available to be minted against Ether. Unlike USDAO mint price, fund price is not pegged to any constant value. Its price can vary and is proportional to the current ETH/USD price.

### Defund Price <a href="#defund-price" id="defund-price"></a>

Defund price is exactly the reverse of the fund price. It is the price at which investors can get their Ether back by redeeming the Asset tokens back to the system.

### Debt Ratio <a href="#debt-ratio" id="debt-ratio"></a>

In its simplest mathematical representation, the debt ratio is the ratio of the total number of stablecoins out in the market to the US dollar value of the reserve pool i.e.

### **𝐷𝑒𝑏𝑡 𝑟𝑎𝑡𝑖𝑜 = 𝑡𝑜𝑡𝑎𝑙 𝑈𝑆𝐷𝐴𝑂 𝑠𝑡𝑎𝑏𝑙𝑒𝑐𝑜𝑖𝑛𝑠 𝑖𝑛 𝑡ℎ𝑒 𝑚𝑎𝑟𝑘𝑒𝑡 / 𝑈𝑆𝐷 𝑣𝑎𝑙𝑢𝑒 𝑜𝑓 𝑡ℎ𝑒 𝑟𝑒𝑠𝑒𝑟𝑣𝑒 𝑝𝑜𝑜𝑙**

The debt ratio signiﬁes the ratio of the amount of buy and sell activities of USDAO stablecoin in the market at that point of time. In other words, if the debt ratio is, let’s say, 50% that is equivalent to say that for every 100 US dollars' worth of Ether present in the system there are 50  stablecoins (worth 50 USD) out in the market. This also means that should each token be burnt right now for Ether the system has us client collateral in the pool to pay everybody back.

The debt ratio of 100% or above is an alarming situation for the system because it means the system does not have enough Ether to return to users in case of 100% USDAO token withdrawal. Hence at this stage, the users receive Ether which is in proportion to the number of tokens they are withdrawing and the amount of Ether available in the pool.

As an example, let’s consider a situation where 1 Ether is 1 USD. Let’s suppose there are a total of 100 USDAO tokens in the market. Now let’s assume a person owns 50 of them and he wants to burn 50 USDAO tokens. If the debt ratio is below 100%, he shall receive Ethers worth 50 USD. But if the

debt ratio is above 100% and only 80 USD worth of Ether is present in the pool then the price of each USDAO reduces to 80 USD/100 USDAO i.e., 0.8 USD per USDAO. So, the user shall get about 40 USD worth of Ether after the burn.

In such situations, the debt ratio then must be brought down below by funding the reserve pool by minting ASSET tokens. The community should be proactive by participating in funding the USDAO Pool through governance to keep the debt ratio below 100%.

### MAX Debt Ratio <a href="#max-debt-ratio" id="max-debt-ratio"></a>

When the debt ratio goes above 80% the defund of ASSET is disabled until the debt ratio falls below 80%. This is important to prevent funders from emptying the pool completely so as to protect the financial interests of USDAO users. Hence, the 80% debt ratio is the Max Debt Ratio of the system for ASSET token holders.

### Oracles <a href="#oracles" id="oracles"></a>

An oracle is a reliable source of ETH/USD price. Our system currently fetches the ETH/USD price from three oracles - Chainlink, Uniswap V2, and Compound oracle. These oracles are an indispensable part of the whole system as it determines the mint, burn, fund, and defund prices. The debt ratio is also determined by the prices returned by the oracles. The reason to use three oracles is to protect the system against any malfunction or inaccuracy in any individual oracle. The system calculates the median price returned by these three oracles, which is further used in operations like mint, burn, etc.&#x20;

For more check out

{% content-ref url="../usdao-stack/smart-contract-modules/oracle-module.md" %}
[oracle-module.md](../usdao-stack/smart-contract-modules/oracle-module.md)
{% endcontent-ref %}

