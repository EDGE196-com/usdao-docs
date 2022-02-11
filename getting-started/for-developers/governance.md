---
description: Governance SDK Functions.
---

# Governance

### Developers: Governance Functions

This section outlines how to initialize and use governance functions inside of the USDAO protocol.&#x20;

### Initialize Governance

This will initialize the Governance functions and methods. Returns the provider, signer, and network for the wallet connected.

```
await initiateGovernance(`infuraUrl`)
```

* **Governace Address And Abi**

This will return the governance contract address and abi from the contract.

```
await govAddressAndAbi()
```

* **DAOGOV Address And Abi**

This will return the DAOGOV contract address and abi from the contract.

```
await daogovAddressAndAbi()
```

*   **USDAO Address And Abi**

    This will return the USDAO contract address and abi from the contract.

    ```
    await usdaoAddressAndAbi()
    ```
* **Make Contract**

Creates and returns the contract for the given address, and abi.\
address: string, abi: abi\[]

```
await makeContract(address, abi)
```

* **Load Proposals**

Loads the governance proposals for the given ids.\
ids: number\[]

```
await loadProposals()
```

* **Load Proposals State**

Loads the governane proposal state for the given ids.\
ids: number\[]

```
await loadProposalStates()
```

* **Load Fees**

Returns the burn fee, mint fee, transaction fee, transfer fee, defund fee.

```
await loadFees()
```

* **Create Proposal**

Creates and returns a governance proposal for the passed targets, values, signature, calldata and description.\
targets: string, values: number, signature: string, description: string

```
await createProposal(targets, values, signature, calldatas, description)
```

* **Fetch Delegate Votes**

Fetches and returns the delegated votes.

```
await fetchDelegateVotes()
```

* **Create Delegate**

Delegate votes to a given address.

```
await createDelegate(`delegateAddress`)
```
