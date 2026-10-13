# Specialist Memo — CHC.AX

**Memo ID**: `CHC.AX_2026-10-13_equity_reit_v1@1.0_7f956fe0382d`
**Ticker**: CHC.AX (Charter Hall Group)
**Market**: Australia
**Sector**: Diversified/Property Funds Management
**As of**: 2026-10-13
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
Charter Hall Group is a large Australian property funds manager with co-investment in its own funds. Its earnings rebounded sharply in FY26, but the security has fallen about 24% since early August 2026 to AUD 18.31. The estimated 3.0% distribution yield is below the 4.06% T-bill rate, so the return depends on growth and re-rating rather than income. The OU simulation gives a 6.9% expected return with 20% dispersion and a PGain of 63.5%, which is a Moderate base conviction of 3. Because AFFO coverage and gearing could not be verified, and volatility is high, I apply a one-step haircut to Low conviction (2), with a 3% maximum position.

## Quantitative Chain

- E(R): 0.0700
- Std dev: 0.2004
- P-gain: 0.6348
- CAPM alpha: 0.1121
- Beta: 0.9127
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.2200
  - Stagflation/rate-shock pathway: RBA tightens or higher-for-longer rates push cap rates out 50bps. Transaction and performance fees stay weak and assets under management shrink through valuation write-downs. Distribution growth is nil, and the security de-rates a further 20-25% from the AUD 18.31 level, continuing the recent downtrend. Volatility stays near 30%.
- **base**: E(R)=0.0690
  - Central case as built in the chain: yield about 3.0%, distribution growth 4%, no multiple change. Cap rates are flat and funds-management fee income is stable. The OU Monte Carlo gives a simulated return of 6.9% with a standard deviation of 20.0% and a PGain of 63.5%.
- **bull**: E(R)=0.3000
  - Rate expectations ease and Australian cap rates compress. Transaction and performance fees recover strongly, lifting distribution growth to about 8-10%. The multiple re-rates about 15-20% toward the early-August level of roughly AUD 23-24.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=info
- `management_alignment` — status=info

## Key Assumptions
- `last_price` = 18.31 (Cat A) — CHC.AX closing price of AUD 18.31 on 2026-10-13 (get_price). The stored series shows a fall of about 24% from roughly AUD 24.0 in early August 2026.
- `distribution_yield` = 0.03 (Cat B) — Estimated forward distribution of about AUD 0.55 per security divided by the AUD 18.31 price. This is an analyst estimate from recalled FY26 guidance. It was not verified against a CHC filing, because the stored filing bodies returned for this ticker were unrelated third-party ASX notices that I did not use. Treat as approximate.
- `dpu_growth_12m` = 0.04 (Cat C) — Assumed 4% growth in distribution and earnings per security. Drivers are recurring funds-management fees and a modest recovery in transaction and performance fees. It is below the 27% FY26 earnings jump reported in news because that rebound is unlikely to repeat. Sensitivity is covered in the bear and bull scenarios.
- `multiple_change` = 0.0 (Cat C) — No re-rating or de-rating assumed over 12 months. The price has already de-rated about 24% since early August 2026, so I assume no further change. A rebound to the August level would add about 25 percentage points, and a further slide would subtract a similar amount. Both are captured in the scenarios.
- `expected_return_build` = 0.07 (Cat C) — E(R) = yield 3.0% (B) + growth 4.0% (C) + multiple change 0.0% (C) = 7.0%. This is a 12-month total-return assumption.
- `risk_free_rate` = 0.0406 (Cat A) — FRED DTB3 3-month T-bill at 4.06% on 2026-10-09 (get_tbill_rate). The rate is US-denominated while CHC is AUD-denominated. The RBA policy rate was 4.35% at 2026-09-24 per BIS.
- `expected_market_return` = -0.050045 (Cat B) — Trailing annualised log return of IASP.L over 1260 trading days (about 5.17 years), from calculate_benchmark_return. GBP-denominated. A negative Rm makes CAPM alpha mechanically large and positive.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same noise. The currency-basis caveat applies to the beta of 0.913, which has a low correlation of 0.37.
- `fundamental_data_gap` = disclosed (Cat B) — The stored filings and ASX announcements for CHC.AX contained only substantial-holder and AGM-notice headlines. No CHC-specific gearing, AFFO coverage, occupancy or WALE figures were verified. The qualitative gates are therefore marked info, with a one-step conviction haircut for unverified coverage.

## Key Risks
- Rate and cap-rate risk: higher-for-longer Australian and global rates would compress valuations, reduce transaction and performance fees, and shrink assets under management.
- Earnings quality: FY26 earnings growth of 27% was driven by cyclical performance and transaction fees that may not recur. A senior leadership reshuffle was reported in August 2026, and the cause of the roughly 24% drawdown since August is not identified in the data reviewed.
- Data limitations: the CHC-specific yield, gearing and coverage inputs are unverified. The beta of 0.91 has a low correlation of 0.37 to a GBP benchmark, and the 5-year Rm of -5.0% distorts CAPM alpha.
- High volatility of 29.5% annualised, and the yield is below the risk-free rate, so the thesis relies on growth and re-rating.
- Calibration is a directional signal, not a formal vintage-controlled backtest, and some macro series beyond Rf were not used.

## Invalidation Condition
Exit if the next half-year result or trading update shows operating earnings or distribution per security guidance cut by more than 10%, or if funds under management falls materially because of valuation write-downs and fund redemptions. Also exit if look-through or balance-sheet gearing rises above about 40%, or if the security closes below roughly AUD 16.50 (about 10% below current) without a fundamental explanation.
