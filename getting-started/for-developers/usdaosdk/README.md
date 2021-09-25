---
description: Trading SDK functions.
---

# USDAO SDK

### Install from npm

```text
npm i usdao
```

### Import usdao

Import functions for USDAO, Asset, Stake and Governance

```text
import { infuraUtil, writeUtil } from 'usdao';
```

### Infura Util

This class is for initializing read only functions.

```text
# returns read functions
var infura  = new infuraUtil(provider_url="Infura URL here)

#get balance
const usmBalance = await infura.balanceOf('usm');
```

* Get Chain id

Returns the chain Id for the network that is connected.

```text
await infura.getChainId()
```



* Get User Address

Returns the connected users address.

```text
await infura.userAddress()
```

* Token Balance

Returns the balance of the contract token passed. Tokens =&gt; \(usdao, asset, governarAlpha, daogov, usdaoView\)

```text
await infura.balanceof(token)
```

* Ether Balance

Returns the ether balance for the connected wallet.

```text
await infura.balaceOfEther()
```

* Staked Amount

Returns the staked balance of the contract token passed. Tokens =&gt; \(usdao, asset, governarAlpha, daogov, usdaoView\)

```text
await infura.stakedAmount(token)
```

* Latest Price

Returns the latest price of the contract token passed. Tokens =&gt; \(usdao, asset, governarAlpha, daogov, usdaoView\)

```text
await infura.latestPrice(token)
```

* Get Debt Ratio

Returns the debt ratio for the usdao contract.

```text
await infura.getDebtRatio()
```

* Get Collateral

Returns the collateral value for the usdao contract.

```text
await infura.getCollateral()
```

* Get Eth Buffer

Returns the eth buffer for the specified usdao contract.

```text
await infura.getEthBuffer()
```

* Get Total Supply

Returns the total supply value. token: string

```text
await infura.totalSupply(token)
```

#### Write Util

This class is for initialising transaction involving functions.

```text
# returns write functions
var writeContract  = new writeUtil(provider_url="Infura URL here)
```

Invoke buy, sell of USDAO and Asset token.

```text
# Mint, burn, Fund, Defunnd

@param token name: usm, fum
@param amount of depositing ether (for buying USDAO or Asset) or token (buring USDAO or Asset)
@param event: buy or sell

const trDetails = await writeContract.transaction('usm', '.1', 'buy');
```



