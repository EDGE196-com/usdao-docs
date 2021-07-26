# Oracle Module

One of the biggest hurdles in keeping the trade fair arises through irregular oracle prices. Differences in prices in the USDAO system and the outside world may expose the whole system to unknown opportunities for exploitation and arbitrage. To overcome this issue the protocol utilizes three popular and reliable oracles -

Chainlink’s ETH/USD feed, sourcing a bunch of off-chain sources.

A Uniswap v2 TWAP \(time-weighted average price\) vs a stable coin: speciﬁcally, ETH/USDC.

Compound’s Open Oracle system, combining ETH/USD prices from providers like Coinbase.

Now even if one of the oracles stopped working or provided the wrong prices the system will continue to work properly. Using the median of the three oracles protects against malfunction by any single oracle The median value returned by the oracles is used for the system's operation.

