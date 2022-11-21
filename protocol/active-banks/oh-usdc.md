---
description: USDC Risk-Optimized Yield Index
---

# Oh! USDC

## Token

* `name` - Oh! USDC
* `symbol` - Oh! USDC
* `decimals` - 6
* `underlying` - USD Coin (USDC)

## Strategies

`OhAaveV2Strategy` - Lend USDC to AaveV2, earn APY in aUSDC and stkAAVE, unwrap stkAAVE

* `underlying` - USDC
* `derivative` - aUSDC
* `reward` - AAVE

`OhCompoundStrategy` - Lend USDC to Compound, earn APY in cUSDC and COMP

* `underlying` - USDC
* `derivative` - cUSDC
* `reward` - COMP

`OhCurve3PoolStrategy` - Add USDC liquidity to Curve 3Pool, earn APY in 3CRV and CRV

* `underlying` - USDC
* `derivative` - 3CRV
* `reward` - CRV

`OH!-tomatic` - Collateralize USDC and borrow MOVR from Moonwell, add USDC-MOVR liquidity to Solarbeam, earn APY in SOLAR, MOVR, and MFAM

* `underlying` - USDC
* `derivative` - USDC-MOVR SLP (Solarbeam)
* `reward` - SOLAR
* `secondaryReward` - MFAM
