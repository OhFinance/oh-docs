---
description: Yield & Revenue Management
---

# Oh! Manager

The `OhManager` contract is the entry point for protocol investment control and revenue management. The Manager contains data about all on-chain Banks, Strategies, Liquidators, and whitelisted Smart Contracts.

Banks are managed by calling any of the following functions:

* `finance()` - Invest all available underlying in the next Strategy queued for the Bank
* `financeAll()` - Invest all available underlying on the Bank evenly across all Strategies
* `rebalance()` - Withdraw all underlying, then invest all available underlying on the Bank evenly across all Strategies

{% hint style="info" %}
Only EOAs (Externally Owned Addresses, i.e. end-users) and whitelisted Smart Contracts can call protocol management functions to prevent attacks
{% endhint %}

## Management Fee

Any user can call the above functions and be rewarded with **2%** of the total profit generated from the transaction, the `managementFee`.

## **Buyback & Burn**

The Manager accrues **20%** of total profit generated during Bank management as a fee to buyback & burn Oh! Tokens, the `buybackFee`. Any user can trigger the `buyback()` function to use accrued revenue to buyback & burn Oh! Tokens.
