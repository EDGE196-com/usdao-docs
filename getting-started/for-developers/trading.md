---
description: Trading SDK functions.
---

# Trading

### Infura Util

This class is for initializing trading-sdk.

```text
new infuraUtil(`infura_url`)
```

* Get Chain id

Returns the chain Id for the network that is connected.

```text
await infura.getChainId()
```

* Read Contract Function

Returns the contract for the particular token passed. Tokens =&gt; \(usm, fum, governarAlpha, comp, usmView\)

```text
await infura.readContractFunction(token)
```

* Get User Address

Returns the connected users address.

```text
await userAddress()
```

* Token Balance

Returns the balance of the contract token passed. Tokens =&gt; \(usm, fum, governarAlpha, comp, usmView\)

```text
await balanceof(token)
```

* Ether Balance

Returns the ether balance for the connected wallet.

```text
await balaceOfEther()
```

* Staked Amount

Returns the staked balance of the contract token passed. Tokens =&gt; \(usm, fum, governarAlpha, comp, usmView\)

```text
await stakedAmount(token)
```

* Latest Price

Returns the latest price of the contract token passed. Tokens =&gt; \(usm, fum, governarAlpha, comp, usmView\)

```text
await latestPrice(token)
```

* Get Debt Ratio

Returns the debt ratio for the usm contract.

```text
await getDebtRatio()
```

* Get Collateral

Returns the collateral value for the usm contract.

```text
await getCollateral()
```

* Get Eth Buffer

Returns the eth buffer for the specified usm contract.

```text
await getEthBuffer()
```

* Get Total Supply

Returns the total supply value. token: string

```text
await totalSupply(token)
```

#### Write Util



This class is for initialising trading-sdk. infuraLink: string

```text
new writeUtil(infuraLink)
```

* Get Address

Returns the current address of the signer.

```text
await getAddress()
```

* Get Chain Id

Returns the chain id of the current network.

```text
await getChainId()
```

* Write Contract

Returns the Dai contract. token: string

```text
await writeConUtil(token)
```

