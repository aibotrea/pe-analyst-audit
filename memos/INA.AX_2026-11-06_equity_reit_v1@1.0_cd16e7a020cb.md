# Specialist Memo — INA.AX

**Memo ID**: `INA.AX_2026-11-06_equity_reit_v1@1.0_cd16e7a020cb`
**Ticker**: INA.AX (Ingenia Communities Group)
**Market**: Australia
**Sector**: Residential (Manufactured Housing/Land Lease and Rental Communities)
**As of**: 2026-11-06
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
INA offers Australian land-lease and rental community exposure with structural demand from ageing demographics, but trailing yield is low (about 2.3%) so total return depends on growth and re-rating. The OU Monte Carlo gives a simulated 12-month return of about 5.2% with 24.7% standard deviation, which implies a PGain of 58% and moderate conviction. CAPM alpha of 6.7% is flattered by a negative 5-year IASP.L return and a currency-basis-noisy beta of 0.63 (correlation 0.21). The stock rallied about 35% in two months and event-driven headlines are present but unverified, so I give no takeover premium in E(R) and hold sizing at the moderate 5% cap.

## Quantitative Chain

- E(R): 0.0530
- Std dev: 0.2470
- P-gain: 0.5831
- CAPM alpha: 0.0671
- Beta: 0.6287
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.2500
  - Any takeover interest lapses or proves unrelated to INA, and the recent rally fully unwinds towards the 4.0 AUD September level. Higher-for-longer rates in a stagflation-type regime lift cap rates and weigh on land-lease multiples. Home settlement volumes weaken, and development margins and distribution growth fall to about 2%.
- **base**: E(R)=0.0530
  - Central case as built in the chain: yield 2.3%, growth 6%, 3% de-rating, no bid premium, volatility around 36% historical and 25% simulated.
- **bull**: E(R)=0.3000
  - A credible change-of-control proposal emerges or the recent proposals are confirmed to concern INA, with a premium of 25% or more. Alternatively, strong settlements and rental growth lift distribution growth to 9%+ and the multiple expands.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=info

## Key Assumptions
- `last_price` = 5.24 (Cat A) — Latest close on 2026-11-06 from get_price (AUD). The stock rose about 35% from the early-September low of 3.85, with elevated volume in late October and November.
- `distribution_yield` = 0.023 (Cat B) — Estimated trailing distribution of roughly 12 cents per security on a 5.24 AUD price. This is my own estimate from recollection of recent published DPS. It could not be verified against an INA filing, because the stored filing bodies returned for INA.AX were from unrelated issuers and I ignored them.
- `dpu_growth_12m` = 0.06 (Cat C) — Assumed 6% forward distribution/earnings growth from development settlements, rental-community expansion and rent escalators. It goes beyond published consensus and is not sourced from filings. The scenario analysis tests it.
- `multiple_change` = -0.03 (Cat C) — Assumed 3% de-rating or mean reversion after the sharp 2-month run-up. No takeover premium is included in E(R). If the takeover-related headlines prove relevant and a bid completes, this assumption would be wrong on the upside.
- `expected_return_build` = 0.053 (Cat C) — E(R) = yield 2.3% + growth 6.0% + multiple change -3.0% = 5.3%. It is a sum of B and C components, so it is classified C.
- `risk_free_rate` = 0.04 (Cat A) — FRED DTB3 3-month T-bill at 4.0% on 2026-11-05. This is a US rate used as the model risk-free per the methodology, not an AUD rate.
- `expected_market_return` = -0.046088 (Cat B) — Trailing annualised log return of IASP.L over 1260 trading days (5.18 years observed) from calculate_benchmark_return. This is a derived statistic, and the 5-year window is negative, so CAPM required return is below the risk-free rate.
- `announcement_feed_integrity` = flagged (Cat B) — ASX headlines tagged to INA on 2026-11-05/06 mention a Warburg Pincus proposal, an AVID matching right and a Flagstone JV implementation deed. The attached filing bodies belong to other issuers (Forte Energy, Terramin, Breville, Brambles, Peet and others). The headlines may be mis-attributed or may relate to a different issuer such as Peet. I treated them as unverified and did not rely on them for E(R).
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same noise. This is a currency-basis caveat on a low-correlation (0.21) beta of 0.63.

## Key Risks
- Event and feed risk: the takeover-related ASX headlines tagged to INA are unverified, and the attached filing bodies were for unrelated issuers. Price may unwind sharply if no bid materialises, or the stock may be restricted if a scheme process is real.
- High realised volatility of 36% and a 35% rally in two months, with large daily swings such as the mid-October drop of about 14% over 2 days, widen the return distribution.
- Fundamental data gap: distribution coverage, gearing (AU convention below 40%), occupancy and sponsor details could not be verified from INA filings. Gates are therefore marked info rather than pass.
- Rates and cap-rate risk: higher-for-longer rates, or a stagflation-type shock, could compress valuations and development margins in residential-linked real estate.
- Methodology limitation: beta against GBP-denominated IASP.L has low correlation, and the negative 5-year benchmark return distorts CAPM alpha. This analysis is a directional signal rather than a formal backtest.

## Invalidation Condition
Exit if INA reports gearing above 40% or distribution coverage below 1.0x AFFO at the next half-year result, if home settlement volumes or development margins fall materially below guidance for two consecutive periods, or if the price falls below about 4.0 AUD, the pre-rally level, with no confirmed corporate action to support it. Also exit if the takeover headlines are confirmed as unrelated to INA and the stock retraces the October rally.
