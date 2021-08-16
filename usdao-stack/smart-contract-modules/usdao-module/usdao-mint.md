# USDAO Mint

### Fetch Latest Oracle Price

Fetch fresh oracle price, update time and previousbidAskAdjustment. If the new update time is different from the previous time stored, update the price.

### Calculate bidAskAdjustment

If the price has changed, a new bidAskAdjustment is calculated. bidAskAdjustment is used to separate buy and sell prices. If buys are happening more than sells thenbidAskadjustment helps buy price to rise up while sell price remains close to the median price. If bidAskAdjustment &gt; WAD \(or 1\) buys are happening more else sales are more.

$$
bidAdkAdjustment=max(1, old buy price / new midprice):
$$

### Calculate Output USDAO For Deposited Ether

Now we calculate how much USDAO we will get for the ether deposited. First, we calculate the adjusted ETH/USD price. Let’s assume we had 100 ethers before the mint operation. We deposit 5 ether for minting USDAO. As we are increasing the ether volume by 5% the price for USDAOshall also increases by 5% i.e user will actually buy USDAO for We calculate the adjusted ETH/USD price after the ether is deposited.

$$
Adjusted ETH/USD price=Oracle price *bidAdkAdjustment
$$

Now we calculate how much USDAO we can receive for1 USD worth of ether based on our new adjusted ETH/USD price.

$$
USDAO buy price=WAD / (Adjusted ETH/USD price)
$$

The above change in the buy price was based on the price returned by oracle and the number of latest mints that happened. Now we again aectthe above USDAO buy price, this time, based on the amount of change we’re making in the eth pool.

$$
EthPool1 = EthPool0 + EtheDeposited
$$

Where, 

EthPool0 = Ethers in the pool before the mint

EthPool1 = Ethers in the pool before mint + Ether deposited for mint

EtheDeposited = Ether deposited

$$
OneOverEthGrowthFactor = EthPool0 / EthPool1
$$

Ideally, it should always be &lt; 1

$$
AdjShinkFactor = Sqrt(OneOverEthGrowthFactor)
$$

$$
Average USDAO buy price = USDAO buy price / AdjShinkFactor
$$

Since adjShrinkFactor is generally less than 1 \(like0.75\) in mints so dividingusmBuyPrice0 by adjShrinkFactor should basically increase the mint price marginally.

$$
Number of USDAO minted = EtheDeposited / Average USDAObuy price
$$

USDAO is minted to the address that deposited ether. Meanwhile, bidAskAdjustment is updated as per the new adjShrinkFactor.

$$
New bidAdkAdjustment = bidAdkAdjustment * AdjShinkFactor
$$

The mint fee is calculated and stored to be withdrawn later.

$$
usdaoTaxFee = (USDAO minted * Mint Fee) / WAD
$$

$$
saveUSDAOMintFee = saveUSDAOMintFee + usdaoTaxFee;
$$



