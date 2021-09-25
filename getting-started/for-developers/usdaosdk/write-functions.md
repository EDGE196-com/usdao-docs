---
description: List of functions that creates a transaction and write into blockchain.
---

# Write functions

## Import writeUtil from the sdk

writeUtil contains all the transaction functions in the USDAO stablecoin smart contracts:

```
import { writeUtil } from 'usdao';
```

{% hint style="info" %}
The functions listed here invokes transactions and thus are payable.
{% endhint %}

This class is for initialising transaction involving functions.

{% code title="Initialise the writeUtil module" %}
```bash
# returns write functions
var writeContract  = new writeUtil(provider_url="Infura URL here)
```
{% endcode %}

### Mint - mint USDAO stablecoins

This function mints USDAO stablecoins according to the Ethers passed and based on current trade price at that time.

```bash
# @param token name: usm
# @param amount of ether depositing 
# @param event: buy

const mint = await writeContract.transaction('usm', '.1', 'buy');
```

### Burn - burn USDAO stablecoins

This function burns the USDAO stablecoins from the user's account and returns corresponding Ethers to the user.

```bash
# @param token name: usm
# @param amount of USDAO burning 
# @param event: sell

const burn = await writeContract.transaction('usm', '10000', 'sell');
```

### Fund - mint Asset tokens

This function mints ASSET tokens according to the Ethers passed and based on current trade price at that time.

```bash
# @param token name: fum
# @param amount of ether depositing 
# @param event: buy

const fund = await writeContract.transaction('fum', '.1', 'buy');
```

### Defund - burn Asset tokens

This function burns the Asset tokens from the user's account and returns corresponding Ethers to the user.

```bash
# @param token name: usm
# @param amount of Asset burning 
# @param event: sell

const defund = await writeContract.transaction('usm', '10000', 'sell');
```

### Transfer USDAO

Transfer USDAO stablecoin from one account to another.

```bash
# @param token name
# @param receiver address
# @param amount to send to 
await writeConn.sendToAddress('usm', address, amount)
```

### Transfer ASSET

Transfer Asset tokens from one account to another.

```bash
# @param token name
# @param receiver address
# @param amount to send to 
await writeConn.sendToAddress('fum', address, amount)
```



