---
description: 'Sample codes for mint, burn, fund and defund operations using USDAO SDK.'
---

# Examples

## Invoke the sdk

Import the writeUtil module from the sdk:

```
import { writeUtil } from "usdao"
const sdk = new writeUtil("infura_url")
```

{% hint style="info" %}
The functions involving transactions such as mint, burn are stored under writeUtil module of the sdk.
{% endhint %}

Below is the list of important transaction functions provided by the sdk

### Mint USDAO

```bash
# Mint USDAO

const mintUsdao = async(amount: number) => sdk.transaction('usm', amount, 'buy')

# Mint USDAO worth 10 ETH
await mintUsdao(10)
```

### Burn USDAO

```bash
# Burn 10 USDAO

const burnUsdao = async(amount: number) => sdk.transaction('usm', amount, 'sell')

# Burn 10 USDAO
await burnUsdao(10)
```

### Transfer USDAO

```bash
# Transfer 10 USDAO to an address

const transferUsdao = async(address: string, amount: number) => sdk.sendToAddress('usm', address, amount)

await transferUsdao("xxxxxxxxxxx", 10)
```

### Mint Asset Tokens

```bash
# Mint 10 Asset tokens

const fundAsset = async(amount: number) => sdk.transaction('fum', amount, 'buy')

# Mint Asset tokens worth 10 ETH
await fundAsset(10)
```

### Burn Asset Tokens

```bash
# Burn 10 Asset tokens

const defundAsset = async(amount: number) => sdk.transaction('fum', amount, 'sell')

# Burn 10 Asset tokens
await defundAsset(10)
```

### Transfer Asset Tokens

```bash
# Transfer 10 Asset to an address

const transferAsset = async(address: string, amount: number) => sdk.sendToAddress('fum', address, amount)

await transferAsset("xxxxxxxxxxx", 10)
```

