---
description: 'Sample codes for mint, burn, fund and defund operations using USDAO SDK.'
---

# Examples

## Invoke the sdk

Import the writeUtil module from the sdk:

```
import { writeUtil } from "usdao-sdk"
const util = new writeUtil("infura_url")
```

{% hint style="info" %}
The functions involving transactions such as mint, burn are stored under writeUtil module of the sdk.
{% endhint %}

Below is the list of important transaction functions provided by the sdk

### Mint USDAO

```bash
# Mint 10 USDAO

const mintUsdao = async(amount: number) => util.transaction('usm', amount, 'buy')

await mintUsdao(10)
```

### Burn USDAO

```bash
# Burn 10 USDAO

const burnUsdao = async(amount: number) => util.transaction('usm', amount, 'sell')

await burnUsdao(10)
```

### Transfer USDAO

```bash
# Transfer 10 USDAO to an address

const transferUsdao = async(address: string, amount: number) => util.sendToAddress('usm', address, amount)

await transferUsdao("xxxxxxxxxxx", 10)
```

### Mint Asset Tokens

```bash
# Mint 10 Asset tokens

const fundAsset = async(amount: number) => util.transaction('fum', amount, 'buy')

await fundAsset(10)
```

### Burn Asset Tokens

```bash
# Burn 10 Asset tokens

const defundAsset = async(amount: number) => util.transaction('fum', amount, 'sell')

await defundAsset(10)
```

### Transfer Asset Tokens

```bash
# Transfer 10 Asset to an address

const transferAsset = async(address: string, amount: number) => util.sendToAddress('fum', address, amount)

await transferAsset("xxxxxxxxxxx", 10)
```

