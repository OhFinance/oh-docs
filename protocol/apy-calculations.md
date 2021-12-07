# APY Calculations

Providing APY estimates is one of the most-requested and important pieces of information to our users. For the sake of transparency, this documentation outlays how our APYs are being calculated, and what an APY value means in our DeFi context.

### Basic Assumption & Disclaimer

There are a myriad of inputs one could add into APY calculations (_e.g._, changing liquidity over time, entry and exits, intermittently called Finance and Rebalance functions, changes in underlying asset prices and platforms, gas fees, etc.).

In order to present the most honest data and avoid speculative inputs, only OH Virtual Price values are used, which are based on **actual** data **** from **** on-chain historical values.

Our APYs are calculated according to the formulas below. These are estimates based on **previous and current** information about OH, not future-looking predictive calculations. Stated simply: our APY values are backwards-looking estimates of historical performance on the platform. Past performance neither guarantees nor predicts the future performance of the platform.&#x20;

### Annual Percentage Return (APR) Calculations <a href="#historical-average-beans-per-season" id="historical-average-beans-per-season"></a>

The primary datapoint underpinning our APR calculations is the on-chain `virtualPrice` value of the `OH Bank` smart contract(s).&#x20;

Notably, APR does not take into account recurring re-compounding of interest earned, unlike APY. APY is what we report, which is detailed in the next section, but APR is an input to our APY calculations.

The formula used to calculate APR is below. APR is defined as the growth of the virutalPirce over a window of time, expanded out to a 365-day year at constant similar performance. A sliding historical time window is used for APR calculation. Shorter time windows generally give a better picture of nearer-to-real-time current performance, whereas longer time windows are less noisy and generally give a better picture of longer-term performance.&#x20;

$$
APR_{n} = ((vp_{recent}/vp_{past})-1)*(n/365)
$$

_n : Number of Days in Sliding Window_\
_vp : Bank Contract virtualPrice at a given point in time, on either the recent front-end of the sliding window or the past back-end of the sliding window_\
_APR : APR calculated over n days, extrapolated to 365-days of returns assuming constant performance_&#x20;

### APY Calculations

Annual Percentage Yield (APY) is what we report to OH users as a more accurate representation of our returns. This is because we regularly (daily) compound any interest or rewards earned on our underlying platforms and re-invest them.

The formula used to calculate APY is below - at the time of writing, we report APY values over a 1-day, 7-day, and 30-day sliding time period. APY values are re-calculated approximately 24-times per day (every 1 hour).

$$
APY_n = (1+\frac{APR_n}{p})^p -1
$$

_n : number of days in sliding APR time window_\
_APR\_n : Annual Percentage Return calculated over an n-day time period_\
_p : Number of times re-compounding occurs during 1 year. OH compounds approximately once per day, so p=365._

APYs are presented on our platform as a percentage value, which multiplies the output of the above APY formula by 100.
