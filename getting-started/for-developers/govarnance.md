---
description: Governance SDK Functions.
---

# Govarnance

### Initialize Governance

This will initialize the Governance functions and methods. Returns the provider, signer and network for the wallet connected.

```text
await initiateGovernance(`infuraUrl`)
```

* Governace Address And Abi

This will return the governance contract address and abi from the contract.

```text
await govAddressAndAbi()
```

* Comp Address And Abi

This will return the Comp contract address and abi from the contract.

```text
await compAddressAndAbi()
```

* USM Address And Abi

  This will return the Usm contract address and abi from the contract.

  ```text
  await usmAddressAndAbi()
  ```



* Make Contract

Creates and returns the contract for the given address, and abi.  
address: string, abi: abi\[\]

```text
await makeContract(address, abi)
```

* Load Proposals

Loads the governance proposals for the given ids.  
ids: number\[\]

```text
await loadProposals()
```

* Load Proposals State

Loads the governane proposal state for the given ids.  
ids: number\[\]

```text
await loadProposalStates()
```

* Load Fees

Returns the burn fee, mint fee, transaction fee, transfer fee, defund fee.

```text
await loadFees()
```

* Create Proposal

Creates and returns a governance proposal for the passed targets, values, signature, calldata and description.  
targets: string, values: number, signature: string, description: string

```text
await createProposal(targets, values, signature, calldatas, description)
```

* Fetch Delegate Votes

Fetches and returns the delegated votes.

```text
await fetchDelegateVotes()
```

* Create Delegate

Delegate votes to a given address.

```text
await createDelegate(`delegateAddress`)
```

