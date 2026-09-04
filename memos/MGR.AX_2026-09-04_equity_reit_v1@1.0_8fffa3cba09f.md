# Specialist Memo — MGR.AX

**Memo ID**: `MGR.AX_2026-09-04_equity_reit_v1@1.0_8fffa3cba09f`
**Ticker**: MGR.AX (Mirvac Group)
**Market**: Australia
**Sector**: Diversified/Office-Industrial-Retail-Residential
**As of**: 2026-09-04
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
Mirvac Group offers a diversified Australian REIT exposure combining office, industrial, retail, and residential segments at a material discount (~30%) to estimated NTA of AUD 2.60, with an indicative distribution yield of approximately 5.6% at the current price of AUD 1.835. The OU Monte Carlo simulation (10,000 iterations, 12-month horizon) returns a simulated expected return of 7.5% with a PGain of 68.8%, supporting a modest long position. However, conviction is limited to Low (score 2) reflecting the 22.6% annualised volatility — among the higher readings for A-REIT diversified peers — and a one-step qualitative override for mixed asset quality, specifically structural CBD office headwinds and the residential earnings cyclicality that adds income uncertainty. CAPM alpha of 10.3% versus IASP.L is encouraging but inherits substantial currency-basis noise from the AUD/GBP translation.

## Quantitative Chain

- E(R): 0.0760
- Std dev: 0.1534
- P-gain: 0.6882
- CAPM alpha: 0.1027
- Beta: 0.7644
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - Office occupancy deteriorates to below 90% across core Sydney/Melbourne CBD assets as hybrid work structurally reduces demand; CBD cap rates expand 50bps; residential settlements disappoint materially as housing market softens and construction cost inflation persists; DPU cut by 10-15% as AFFO coverage falls below 1.0x; gearing rises toward 36% on asset write-downs; AUD depreciates, compressing IASP.L-relative returns. Multiple re-rating of -5% on NTA discount widening.
- **base**: E(R)=0.0760
  - Central case as built in quantitative chain: DPU growth of 2.0% p.a., occupancy stable across office (~92%) and industrial (~97%), cap rates flat, gearing ~30%, no material multiple change. RBA cash rate at ~3.50% provides a manageable cost-of-debt environment. Residential segment contributes modest earnings with lumpy but positive settlement activity.
- **bull**: E(R)=0.1950
  - RBA eases further to ~3.0%, compressing cap rates and boosting asset valuations; office demand recovers as corporates mandate return-to-office, lifting occupancy toward 95% and enabling rental growth of 3-4%; residential pipeline monetises at improved margins; NTA discount narrows by ~10% as diversified REIT re-rates toward peers; DPU growth of 4.0%; gearing falls below 27% from non-core asset disposals at book value or above.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=info [override_applied=-1]
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.056 (Cat A) — Trailing DPU yield derived from estimated FY2026 DPU of approximately AUD 10.3 cents per security (consistent with Mirvac's published guidance range and recent annual distribution history) divided by last close price of AUD 1.835 on 2026-09-04. Published DPU is an issuer-disclosed figure; yield calculation is a Category A observable. ASX filing bodies for MGR.AX were unavailable due to pipeline cross-contamination; figure relies on last-known public guidance.
- `dpu_growth_3yr` = 0.02 (Cat C) — Forward DPU growth assumption of 2.0% p.a. reflects modest organic NOI growth from office and industrial sub-portfolios, partially offset by structural headwinds in CBD office demand and lumpy residential settlement earnings. Sensitivity tested in scenario analysis: bear uses 0%, bull uses 4%. No consensus forward DPU series was retrievable via news or filing search at as_of date; figure is an analyst model assumption.
- `multiple_change` = 0.0 (Cat C) — Base case assumes zero multiple change (price-to-NTA discount remains approximately 30% below estimated NTA of AUD 2.55-2.65). The persistent discount is considered structural, reflecting the development/residential segment complexity and office cycle headwinds. No NTA re-rating assumed absent a catalyst. Sensitivity: bull case assumes 3% positive multiple contribution from office recovery; bear assumes further 5% compression.
- `nta_estimate` = 2.6 (Cat B) — NTA per security estimated at approximately AUD 2.60 based on Mirvac's published balance sheet and historical NTA disclosures. Represents analyst derivation from last-reported figures; exact as_of date value not confirmable from available filing extracts due to pipeline cross-contamination. Implies ~30% discount to NTA at current price.
- `gearing_estimate` = 0.3 (Cat B) — Gearing estimated at approximately 30% look-through LVR based on Mirvac's historical reported range of 28-33%. Regulatory convention for Australian REITs is <40% by market convention; estimated gearing is comfortably within this limit. Specific FY2026 end balance sheet not confirmed from retrieved filings.
- `rba_cash_rate` = 0.035 (Cat A) — RBA cash rate target estimated at approximately 3.50% as of September 2026, reflecting the easing cycle that commenced in 2025. Live APAC rates tool returned empty for AU at as_of date; figure based on last publicly available RBA rate schedule. Used as macro context, not in CAPM calculation (US T-bill Rf used for CAPM per methodology).
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same currency and iasp noise. Users should interpret beta and alpha as directional indicators, not precise CAPM coefficients.

## Key Risks
- Structural decline in CBD office demand driven by hybrid and remote work adoption, depressing occupancy and rental reversion across Mirvac's ~40% office weighting and triggering cap rate expansion and NTA write-downs.
- Residential development cycle risk: settlement delays, construction cost inflation, and buyer defaults in a higher-rate environment could materially impair residential earnings and stress AFFO coverage of distributions.
- RBA policy reversal or higher-for-longer rates compressing the yield spread versus the 3.75% US T-bill proxy and AUD risk-free alternatives, reducing relative attractiveness of the ~5.6% distribution yield.
- AUD/GBP and AUD/USD currency movements introducing noise into benchmark-relative metrics (beta 0.76 vs IASP.L carries FX basis risk); a material AUD depreciation could affect capital costs on offshore-linked debt.
- Macro signal gaps: FRED macro series (FEDFUNDS, credit spreads) were absent at as_of date; calibration is directional only and subject to Phase 5 vintage discipline improvements.

## Invalidation Condition
Exit or materially reduce position if Mirvac reports two consecutive half-year periods of office occupancy below 90% across the core portfolio, or if DPU is cut by more than 10% from the FY2026 base, signalling AFFO coverage below 1.0x, or if gearing exceeds 36% LVR on asset write-downs without a credible de-gearing plan communicated to the market, or if the RBA unexpectedly reverses easing and raises the cash rate above 4.5% within the 12-month horizon.
