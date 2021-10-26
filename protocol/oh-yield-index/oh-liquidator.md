---
description: Token Swap Management
---

# Oh! Liquidator

The `OhLiquidator` contract maps tokens to decentralized exchanges (i.e. Uniswap or Sushiswap) for liquidation.

Liquidators are used by the protocol in the following ways:

* Strategies compound interest by liquidating a reward token to the desired underlying
* Manager liquidates protocol revenue into Oh! Finance Tokens, then burns them

Additional Liquidators can be deployed and added to `OhManager` via Governance to support new strategies and liquidation methods.
