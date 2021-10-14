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

This function mints USDAO stablecoins according to the ethers passed.

```bash
# @param amount of ether depositing. Unit is in ethers  

const mint = await writeContract.buyUsdao('10000')
```

### Burn - burn USDAO stablecoins

This function burns the USDAO stablecoins from the user's account and returns corresponding ethers to the user.

```bash
# @param amount of USDAO burning. Unit is in ethers  

const burn = await writeContract.sellUsdao('10000');
```

### Fund - mint Asset tokens

This function mints ASSET tokens according to the ethers passed.

```bash
# @param amount of ether depositing. Unit is in ethers  

const fund = await writeContract.buyAsset('0.1');
```

### Defund - burn Asset tokens

This function burns the Asset tokens from the user's account and returns corresponding ethers to the user.

```bash
# @param amount of Asset burning. Unit is in ethers 

const defund = await writeContract.sellAsset('10000');
```

### Transfer USDAO

Transfer USDAO stablecoin from one account to another.

```bash
# @param receiver address
# @param amount to send to. Unit is in ethers 
await writeConn.transferUsdao(address, amount)
```

### Transfer ASSET

Transfer Asset tokens from one account to another.

```bash
# @param receiver address
# @param amount to send to. Unit is in ethers 

await writeConn.transferAsset(address, amount)
```

