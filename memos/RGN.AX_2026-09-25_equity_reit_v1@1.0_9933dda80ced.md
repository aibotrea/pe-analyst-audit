# Specialist Memo — RGN.AX

**Memo ID**: `RGN.AX_2026-09-25_equity_reit_v1@1.0_9933dda80ced`
**Ticker**: RGN.AX (Region RE Limited)
**Market**: Australia
**Sector**: Retail/Sub-Regional & Neighbourhood Centres
**As of**: 2026-09-25
**Framework**: equity_reit_v1@1.0
**Conviction score**: 4/5 (Above average)
**Max position**: 8.0%

## Thesis
Region RE Limited offers defensive Australian retail real estate exposure anchored by non-discretionary tenants (Woolworths, Coles, Aldi) across sub-regional and neighbourhood centres, providing a durable income base at a 6.0% distribution yield versus a 4.08% T-bill rate. The internally managed structure eliminates external fee drag, aligning management with unitholder outcomes, while an active on-market buy-back programme signals balance sheet confidence and provides a technical floor. Beta of 0.43 against IASP.L (currency-basis caveat applies) reflects lower co-movement with the broader APAC REIT universe, consistent with the defensive, domestic-income-oriented profile. The OU Monte Carlo simulation yields a 12-month simulated return of 7.46% with a PGain of 77.8%, and a CAPM alpha of 7.27% (against a negative IASP.L benchmark return) supports above-average conviction in this income-oriented, low-volatility position.

## Quantitative Chain

- E(R): 0.0750
- Std dev: 0.0976
- P-gain: 0.7775
- CAPM alpha: 0.0727
- Beta: 0.4326
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - RBA reverses easing stance due to resurgent inflation; cap rates expand 50bps compressing NTA; specialty occupancy falls below 95% as consumer spending retreats; DPU coverage drops to 0.95x AFFO forcing distribution cut; buy-back suspended to preserve liquidity. AUD weakness amplifies IASP.L basis noise further.
- **base**: E(R)=0.0750
  - Central case as built in chain: distribution yield 6.0%, DPU growth 1.5%, cap rates flat, occupancy stable at ~98% for anchor tenants, on-market buy-back continues providing price support, RBA cash rate declining moderately through FY2027.
- **bull**: E(R)=0.1750
  - RBA accelerates easing cycle; cap rate compression of 25-30bps drives NTA uplift; DPU growth reaches 3.0% on back of specialty rent reversions; strategic asset recycling accretive at 6%+ yield; buy-back programme meaningfully reduces unit count, boosting per-unit metrics. Market re-rates internally managed structure at premium.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.06 (Cat B) — Trailing distribution yield derived from closing price of AUD 2.18 (2026-09-25) and estimated FY2026 DPU of ~AUD 0.131, consistent with RGN's published historical payout profile of 13-14 cpu. Classified Category B as DPU is management-guided and not yet formally filed for FY2026 at as_of date.
- `dpu_growth_rate` = 0.015 (Cat C) — Forward DPU growth of 1.5% p.a. assumed based on: (1) non-discretionary anchor tenant profile (Woolworths, Coles, Aldi) providing resilient base rents; (2) RBA easing cycle supporting consumer spending in trade areas; (3) sub-regional centres historically delivering 1-2% specialty rent growth. Sensitivity tested: bear case 0%, bull case 3.0%. Category C as this is a model assumption beyond available published guidance.
- `multiple_change` = 0.0 (Cat C) — Net multiple/cap-rate change assumed neutral in base case. RGN price retraced from AUD 2.43 (Jul 2026) to AUD 2.18 (Sep 2026), suggesting some cap rate pressure is already priced in. No further compression or expansion modelled in base case. Category C — inherently model-dependent.
- `gearing_ratio` = 0.325 (Cat B) — Estimated gearing of ~32.5% based on RGN's historical leverage profile as a sub-regional retail REIT. Active on-market buy-back programme (multiple ASX notifications August-September 2026) indicates balance sheet headroom. Within AU REIT convention of <40%. Category B as precise current figure derived from historical filings rather than a freshly filed FY2026 balance sheet.
- `on_market_buyback` = active (Cat A) — Multiple ASX ISSUED CAPITAL announcements (2026-09-07, 2026-09-06, 2026-09-03) confirming active on-market buy-back notifications for RGN. Observed public ASX regulatory filings. Category A.
- `internal_management_structure` = internally_managed (Cat A) — Region RE Limited (formerly SCA Property Group) is internally managed. No external responsible entity fee drag. Observed from publicly available corporate structure disclosures. Category A.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP (currency basis). Treated as Category B input. CAPM alpha inherits the same noise. IASP.L 5-year annualised return of -4.81% reflects GBP/AUD FX headwinds over the measurement window and should not be interpreted as a pure property market signal.

## Key Risks
- Higher-for-longer RBA rates compressing the yield spread over cash and triggering cap rate expansion that erodes NTA and total return.
- Structural shift in retail foot traffic if major anchor tenants (Woolworths, Coles) renegotiate leases or reduce footprints during renewals, reducing rental income visibility.
- AUD/GBP currency basis noise embedded in the IASP.L beta calculation may overstate or understate true property-market co-movement, creating CAPM alpha measurement error.
- Limited filing body data available at as_of date means distribution coverage ratio (AFFO) could not be independently verified from recent filings; DPU sustainability risk is therefore classified as 'info' rather than confirmed 'pass'.
- On-market buy-back, while supportive, consumes capital that could otherwise be deployed into accretive acquisitions; if buy-back is suspended, a valuation support mechanism is removed.

## Invalidation Condition
Exit position if: (1) anchor tenant occupancy falls below 95% for two consecutive reporting periods; (2) DPU coverage drops below 1.0x AFFO as reported in a filed distribution statement; (3) gearing exceeds 38% of total assets breaching the 40% AU convention threshold; or (4) management announces suspension of the buy-back programme concurrent with a strategic review implying balance sheet stress or dilutive equity issuance.
