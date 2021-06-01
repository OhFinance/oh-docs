---
description: Tokenized Yield Index
---

# Oh! Bank

The `OhBank` is the main protocol yield-generating contract. Each Bank manages a set of Strategies that interact with individual DeFi protocols, creating a DeFi Yield Index.

Each Bank is an ERC-20 token, which represents the holder's percentage ownership of all underlying tokens controlled by the Bank and it's Strategies. Users deposit an`underlying` token \(i.e. USDC\) to the Bank to receive Bank shares \(i.e. Oh! USDC\) that automatically accrue interest.

The exchange rate of underlying tokens to Bank shares is given by the following formula:

```text
share_price = (total_underlying_deposited + total_yield_generated) / total_shares
```

Users can call the following functions to interact with each Bank:

* `deposit()` - Deposit a given amount of underlying tokens to receive equivalent Bank shares
* `depositFor()` - Deposit a given amount of underlying tokens from the caller for a given recipient
* `depositWithPermit()` - Deposit a given amount of underlying tokens from the caller for a given recipient for EIP-2612 Compliant tokens \(tokens that support the `permit()` function\)
* `withdraw()` - Withdraw a given amount of Bank shares to receive equivalent underlying tokens

The Bank supports calling the `permit()` function \(EIP-2612 Compliant\) and upgradeability via standardized proxy storage \(EIP-1967 Compliant\).

{% hint style="info" %}
Only EOAs \(Externally Owned Addresses, i.e. end-users\) and whitelisted Smart Contracts can call Bank functions to prevent attacks.
{% endhint %}

