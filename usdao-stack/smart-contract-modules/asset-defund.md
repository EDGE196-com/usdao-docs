# ASSET DEFUND

Here we determine how much ETH a defunder currently gets back for fumIn FUM, accounting for adjustment and sliding prices.

So, to begin with, just like our \_fundAsset function, we first fetch the latest data like ethUsdPrice, bidAskAdjustment, etc from loadState function and refresh these values using the latest Oracle prices returned.

### Calculating output ether from DeFund

We calculate the adjusted ETH/USD price and asset sell price as we did in fund operation. Let’s call them adjustedEthUsdPrice0 and assetSellPrice0 respectively.

We first calculate how much ether we would get if the Asset sell price is assetSellPrice0. We call that output as lowerBoundEthQty1,

$$
lowerBoundEthQty1 = ether in pool - (amount of Asset tokens to burn * assetSellPrice0)
$$

The shrink factor after this defund operation can be calculated as,

![](../../.gitbook/assets/capture%20%289%29.jpg)

lowerBoundEthShrinkFactor1 is not the true shrink factor since this was calculated using lowerBoundEthQty1. But lowerBoundEthQty1 is not the actual ether that will be returned to the defunder.

Anyways, using lowerBoundEthShrinkFactor1 we can calculate \(yet again fictitious\) adjusted ETH/USD price, adjustedEthUsdPrice1. adjustedEthUsdPrice1 is the resultant adjusted ETH/USD price after the defund operation if the shrink factor was lowerBoundEthShrinkFactor1.

![](../../.gitbook/assets/capture%20%286%29.jpg)

From adjustedEthUsdPrice1, we can calculate the resultant debtRatio2 we'll end up at after the defund operation, and from debtRatio2, a resulting netFumDelta2 we can hold fixed during the calculation:

Now we calculate the dollar value of total ethers in pool to later calculate the debt ratio,

![](../../.gitbook/assets/capture%20%285%29.jpg)

If total supply of USDAO is 0, the debt ratio = 0. 

If ethPoolValueInUsd is 0, the debt ratio is max int value.

Else if ethPoolValueInUsd is greater than 0, the debt ratio is the quotient of USDAO total supply and ethPoolValueInUsd.

So, if ethPoolValueInUsd &gt; 0

![](../../.gitbook/assets/capture%20%282%29.jpg)

Let this be called debtRatio1. We choose the minimum debt ratio between debtRatio1 and MAX\_DEBT\_RATIO \(80%\). Let this be called debtRatio2.

**So, debtRatio2 = min\(debtRatio1, MAX\_DEBT\_RATIO\)**

So,

![](../../.gitbook/assets/capture%20%287%29.jpg)

#### Using our formula to calculate adjChangeFactor

![](../../.gitbook/assets/capture%20%284%29.jpg)

And adjShrinkFactor tells us the adjustedEthUsdPrice2 we'll end the operation at, from which we can also calculate the instantaneous Asset sell price we'll end the operation at, just as we calculated our ending assetBuyPrice1 in assetFromFund\(\). Let this instantaneous Asset sell price be called assetSellPrice2.

Now since we know both the x and y, our average Asset Sell Price is

$$
avgAssetSellPrice = (assetSellPrice0 + assetSellPrice2) / 2
$$

And consecutively the ether to return as output

$$
ethOut = assetIn * avgAssetSellPrice
$$

A defund fee is deducted and the rest ether is returned to the defunder burning his Asset tokens simultaneously. The new bidAskAdjustment is adjusted as per the new adjShrinkFactor.

$$
bidAskAdjustment = bidAskAdjustment * adjShrinkFactor
$$

Finally, all the state variables like new Asset sell price, ethers in the pool, and others are updated.

