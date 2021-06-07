---
description: ERC-20 Governance and Profit Share Token
---

# Oh! Token

The `OhToken` is a standard ERC-20 token that is used by the protocol for Governance and Profit Share.

* `name` - Oh! Finance Token
* `symbol` - OH
* `decimals` - 18
* `totalSupply` - 100,000,000

The Oh! Finance Token supports calling the `permit()` function \(EIP-2612 Compliant\) for signature-based approvals.

## Governance

Oh! Finance Tokens represent voting rights in the protocol governance module. Each token transfer stores a checkpoint which can be referenced on-chain to determine a user's voting power at any given block.

Users can delegate their votes to a trusted party or self-delegate to participate in protocol voting.

{% hint style="info" %}
More information can be found on governance in the [Oh! Governance](oh-governance/) section.
{% endhint %}

## Profit Share

Oh! Finance Tokens are used as a proxy for protocol revenue. A percentage of total profit generated from all Indexes are redistributed to Oh! Finance Token holders through an on-chain buyback & burn mechanism.

{% hint style="info" %}
More information can be found on the buyback & burn mechanism in the [Oh! Manager](oh-yield-index/oh-manager.md) section.
{% endhint %}

