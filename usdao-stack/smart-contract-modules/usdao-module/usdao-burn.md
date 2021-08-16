# USDAO Burn

### Fetch The Latest Oracle Price

Fetch fresh oracle price, update time, and previous bidAskAdjustment. If the new update time is different from the previous time stored, update the price.

### Calculate bidAskAdjustment

$$
bidAdkAdjustment = min(1, old sell price / new mid price)
$$

### Calculate Output Ether For Deposited USDAO

We calculate the adjusted ETH/USD price after the USDAO is burnt.

Adjusted ETH/USD price,

$$
adjustedEthUsdPrice0 = Oracle price * bidAdkAdjustment
$$

Based on the new adjusted ETH/USD price the new sell price is calculated.

USDAO Sell Price,

$$
USDAOSellPrice0 = WAD / adjustedEthUsdPrice0
$$

But if the debt ratio is above 100%, the USDAO sell price rather is

$$
USDAOSellPrice0 = Total Ether in ETH Pool / Total USDAO supply
$$

Now we calculate the exponent which is the product of the amount of USDAO to burn and sell price \(per Wei\).

$$
Exponent = Amount of USDAO * (USDAOSellPrice0 / ETHPool)
$$

\(usmSellPrice0 / ethPool\) gets the sell price per wei

$$
ETHPool 1 = Total Ether in ETH Pool / eExponent
$$

The Output Ether hence is,

$$
Ether Out = Total Ether in ETH Pool - ETHPool1
$$

This ether is sent to the user who burnt his USDAO. Since there has been a change in the ETH pool, the adjacent growth factor, adjGrowthFactor is calculated. adjGrowthFactor represents the change in the mid price and the bidAskAdjustment.

$$
adjGrowthFactor = (Old Eth pool value / New Eth pool value i.e
ETHPool1)2
$$

bidAskAdjustment is then updated by multiplying it with adjGrowthFactor.

$$
New bidAskAdjustment = bidAskAdjustment * adjGrowthFactor
$$



