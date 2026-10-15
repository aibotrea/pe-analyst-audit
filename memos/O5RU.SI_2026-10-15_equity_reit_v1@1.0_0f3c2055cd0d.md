# Specialist Memo — O5RU.SI

**Memo ID**: `O5RU.SI_2026-10-15_equity_reit_v1@1.0_0f3c2055cd0d`
**Ticker**: O5RU.SI (AIMS APAC REIT)
**Market**: Singapore
**Sector**: Industrial/Logistics
**As of**: 2026-10-15
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
AIMS APAC REIT offers Singapore industrial and commercial property exposure with a forward yield I estimate at about 7.0%, which is roughly 290bps above the 4.1% T-bill rate. 1H FY2027 net property income rose to S$75.9M from S$68.4M, and the manager is expanding via the Perth acquisition and a larger debt programme. The 12-month OU Monte Carlo gives an expected return of about 8% and a PGain of 77%, which supports a base conviction of 4. I cut it one step to 3 because the sponsor has a limited record of capital support, the CEO and CFO have just changed, and I could not verify gearing or distribution coverage. Beta of 0.29 versus IASP.L (currency-basis caveat applies) is based on a weak 0.22 correlation, so the CAPM alpha is of limited reliability.

## Quantitative Chain

- E(R): 0.0800
- Std dev: 0.1074
- P-gain: 0.7705
- CAPM alpha: 0.0656
- Beta: 0.2939
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0700
  - Stagflation or higher-for-longer rate pathway: SGD rates and cap rates rise by about 25-50bps, the yield multiple de-rates by 7-8%, and refinancing costs squeeze DPU with coverage below 1.0x AFFO. DPU declines about 3%. The new CEO and CFO team stumbles on capital management, and the acquisition programme is slowed or funded dilutively.
- **base**: E(R)=0.0800
  - Central case as built in the chain: about 7.0% yield, 1.5% DPU growth from recent NPI gains and the Perth acquisition, and a -0.5% multiple drift. Cap rates and occupancy are broadly stable, and OU Monte Carlo output is 7.95% with 10.7% standard deviation.
- **bull**: E(R)=0.1900
  - The debt programme expansion is used for accretive acquisitions, NPI growth of about 10% carries through to about 4% DPU growth, and the yield spread over the T-bill compresses as SGD rates ease. The unit price re-rates by about 7%.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=fail [override_applied=-1]
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=info
- `management_alignment` — status=info

## Key Assumptions
- `last_close_price` = 1.4 (Cat A) — O5RU.SI stored close on 2026-10-15 (SGD 1.40); the stock drifted from about SGD 1.44 to 1.40 over the prior month.
- `distribution_yield` = 0.07 (Cat B) — Forward distribution yield of about 7.0% is my own estimate for SGD 1.40, based on recent semi-annual payout history. The 1H FY2027 results filing (O5RU.SI 2026-10-15 ANNC) gave only a headline in the body I could read, with the PDF attachments not parsed. The interim distribution notice (O5RU.SI 2026-10-15 CACT) shows a declared rate of SGD 0.0016 for 01/07/2026-30/09/2026. I could not reconcile that figure to total DPU, so the yield is not confirmed from the filing.
- `dpu_growth` = 0.015 (Cat C) — Assumed 1.5% annual DPU growth. It rests on the reported 1H net property income of S$75.9M versus S$68.4M a year earlier (news headline, 2026-10-15) and on the A$42.7M Perth freehold industrial acquisition (news, 2026-07-09), net of a higher funding cost. I am haircutting the NPI growth because I cannot confirm how much of it is acquisition-driven or flows through to DPU. Sensitivity is shown in the bear and bull cases.
- `multiple_change` = -0.005 (Cat C) — Assumed -0.5% from a small yield-multiple drift. The 4.1% T-bill rate is elevated and the unit price has been weak. Cap-rate and yield spread are assumed broadly flat, with a small drag for the management transition.
- `expected_return_build` = 0.08 (Cat B) — E(R) is roughly 7.0% yield plus 1.5% growth less 0.5% multiple change, which is about 8.0% and is rounded to 8.0%. The result is entirely dependent on the unverified yield assumption.
- `risk_free_rate` = 0.041 (Cat A) — FRED DTB3 3-month T-bill at 4.10% on 2026-10-14, converted from percent to decimal.
- `expected_market_return` = -0.0495 (Cat B) — Trailing 5.17-year annualised log return of IASP.L (1260 trading days), as returned by calculate_benchmark_return. Because it is negative, CAPM required return is low and alpha is flattered.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between SGD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.
- `beta_low_correlation` = 0.294 (Cat B) — Beta of 0.294 over 252 observations with correlation of only 0.22 to IASP.L. This is a weak statistical relationship, so the CAPM alpha is of limited reliability.
- `gearing_data_gap` = not_verified (Cat C) — No gearing, AFFO coverage, occupancy or WALE figures could be extracted. The 1H FY2027 results body had only attachment titles, the SGX live API returned 403, and the news search for DPU, gearing and occupancy returned nothing. The qualitative gates for leverage and coverage are therefore marked info rather than pass.
- `debt_programme` = 2000000000.0 (Cat A) — O5RU.SI 2026-09-18 ANNC: the multicurrency debt issuance programme limit was raised from S$750M to S$2,000M, which gives more funding flexibility. It is not a statement of drawn debt.
- `management_transition` = CEO and CFO change (Cat A) — O5RU.SI 2026-10-01 ANNC: Lim Joo Lee, previously responsible for finance, capital markets and investor relations, became CEO on 1 October 2026, replacing Russell Ng. A related announcement the same day covers CEO and CFO appointments.

## Key Risks
- Yield, coverage and gearing data were not verified: the 1H FY2027 results body had no figures, the SGX live API returned 403, and the news search found no DPU or gearing data. The 7.0% yield is my estimate, and if the actual yield is lower the expected return and PGain fall.
- Management transition: a new CEO from 1 October 2026 and a CFO change, with execution risk on capital management and the acquisition programme.
- Higher-for-longer rates: with a 4.1% T-bill, refinancing costs and cap-rate expansion could compress DPU and valuations, and a larger debt programme raises leverage risk if used aggressively.
- Sponsor depth: AIMS has a thinner pipeline and capital-injection record than larger Singapore REIT sponsors, so there is limited external growth support and potentially thinner liquidity.
- Benchmark and calibration limitations: IASP.L is GBP-denominated, beta correlation is only 0.22, the 5-year benchmark return is negative (-4.9%), and this analysis is a directional signal rather than a formal backtest.

## Invalidation Condition
Exit if DPU coverage by AFFO falls below 1.0x or reported distributions are cut for two consecutive half-year periods, if aggregate leverage rises toward the 50% Singapore regulatory ceiling, or if occupancy falls materially (below about 90%). Also exit if the new CEO and CFO team funds acquisitions dilutively or the units trade through a persistent yield above 8.5% without an offsetting improvement in NPI growth.
