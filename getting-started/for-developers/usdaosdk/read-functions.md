---
description: List of read-only function in USDAO stablecoin.
---

# Read functions

## Import readUtil from the sdk

readUtil contains all the read functions in the usm.sol contract:

```
import { readUtil } from 'usdao';
```

{% hint style="info" %}
Functions in readUtil module contains read-only functions that do not cost any fee. 
{% endhint %}

Let's dive into various read-only functions provided by the readUtil module.

### Initialise a Infura connection

{% code title="Initialise Infura connection" %}
```bash
# returns read functions
const readConn  = new infuraUtil(provider_url="Infura URL here)
```
{% endcode %}

### Read USDAO stablecoin balance

This function returns the current USDAO balance of a user.

```bash
# @param contract name - usm
# @param user address - address to get balance of
await readConn.balanceOf('usm', '0x00000useraddress0000000')
```

### Read Asset token balance

This function returns the current Asset token balance of the user.

```bash
# @param contract name - fum
# @param user address - address to get balance of
await readConn.balanceOf('fum', '0x00000useraddress0000000')
```

### Read Ether balance

This function returns the current Ether balance of the user.

```bash
await readConn.balaceOfEther()
```

### ETH to USDAO conversion rate

How much USDAO will be minted on providing this amount of Ether.

```bash
# @param - usmView
# @param - eth
# @param - usm
# @param - value -- amount of Ether (in ETH units) being passed 
await readConn.conversionOfEther('usmView', 'eth', 'usm', value);
```

### USDAO to ETH conversion rate

How much ETH will be returned by burning this amount of USDAO.

```bash
# @param - usmView
# @param - eth
# @param - usm
# @param - value -- amount of USDAO being burnt
await readConn.conversionOfEther('usmView', 'usm', 'eth', value)
```

### ETH to ASSET conversion rate

How much Asset token will be minted on providing this amount of Ether.

```bash
# @param - usmView
# @param - eth
# @param - asset
# @param - value -- amount of Ether (in ETH unit) being passed
await readConn.conversionOfEther('usmView', 'eth', 'asset', value)
```

### ASSET to ETH conversion rate

How much ETH will be returned on burning this amount of Asset tokens.

```bash
- usmView
# @param - eth
# @param - asset
# @param - value -- amount of Asset tokens being burned
await readConn.conversionOfEther('usmView', 'asset', 'eth', value)
```

### Get Debt Ratio

Returns the current debt ratio of the system.

```bash
await readConn.getDebtRatio()
```

### Get bidAskAdjustmentRatio

Returns the current bidAskAdjustment ratio. Check USDAO documentation for more details.

```bash
await bidAskAdjustment()
```

### Current Trade Price

Returns the current trade price for mint/burn of USDAO and Asset tokens

```bash
# @param - usm (usm.sol contract name reference)
await readConn.latestPrice('usm')
```

### Total Ether deposited in the system

Returns the total ETH pool value of the system.

```bash
await readConn.getEthPool()
```

### Get Chain id

Returns chain id of the network according to the metamask.

```bash
await readConn.getChainId()
```

### Get logged in user address

Returns the connected users address.

```bash
await readConn.userAddress()
```

### Get collateral

Returns the collateral value for the usdao contract.

```bash
await readConn.getCollateral()
```

### Get ETH Buffer

Returns the ether left if all the USDAO is burned.

```bash
await readConn.getEthBuffer()
```

### Get total supply

Returns the total supply of USDAO or Asset

```bash
@param token -- usm or fum
await readConn.totalSupply(token)
```

