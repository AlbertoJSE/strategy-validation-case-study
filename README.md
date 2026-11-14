# How I validate a trading strategy — case study

**[Read the full case study (PDF, 3 pages)](Strategy_Validation_Case_Study.pdf)**

A well-known public strategy, Larry Connors' **"Double 7"** on the S&P 500, looks excellent on the first six
years of data. With the rules fixed in advance and tested on the five years that were held back, the edge
disappears. **Verdict: rejected, no re-tuning.**

| | Trades | Win rate | Mean net return / trade | t-statistic |
|---|---|---|---|---|
| Design 2011-2016 | 69 | 75 % | +0.65 % | 3.85 |
| Validation 2017-2021 | 52 | 75 % | −0.03 % | −0.06 |

## The process

1. **Pre-registration.** Rules, costs, periods and five pass criteria are written down before any test.
2. **Held-back data.** The validation period is never used to design or tune.
3. **Random-entry control.** 2,000 runs with random entry days in the same uptrend and the same holding times:
   the strategy ranks at the 28th percentile, far below the 95th required.
4. **Cross-asset check.** Same rules on the Nasdaq 100 (positive, but one market cannot rescue a failed main test).
5. **Monte Carlo.** Bootstrap of the trade sequence to estimate bad-year outcomes and drawdowns.
6. **Realistic costs.** Spread, commission and overnight financing in every trade.

Most ideas fail. Rejecting them cleanly, before they reach a live account, is what protects capital.

## About

Alberto Jabonero, self-taught systematic trader and developer (Python, MQL5, Pine Script).
See also: [mt5-tps-sample-ea](https://github.com/AlbertoJSE/mt5-tps-sample-ea), a production-style MetaTrader 5 Expert Advisor.

*Educational case study. Not investment advice.*
