# Specialist Memo — CQR.AX

**Memo ID**: `CQR.AX_2026-09-08_equity_reit_v1@1.0_79b3bdc19c25`
**Ticker**: CQR.AX (Charter Hall Retail REIT)
**Market**: Australia
**Sector**: Retail/Convenience
**As of**: 2026-09-08
**Framework**: equity_reit_v1@1.0
**Conviction score**: 4/5 (Above average)
**Max position**: 8.0%

## Thesis
Charter Hall Retail REIT offers a compelling 6.55% trailing distribution yield underpinned by a necessity-based, supermarket- and Bunnings-anchored convenience retail portfolio with long weighted-average lease expiry and CPI-linked rent reviews. The FY26 annual results (August 2026) delivered a guidance upgrade, a 78.4% rise in statutory profit, and an accretive $151M Bunnings acquisition, demonstrating active capital deployment by a high-quality sponsor. With beta of 0.55 against IASP.L (currency-basis caveat applies) and a strong CAPM alpha of 10.0% against a negative market benchmark return, the risk-adjusted return profile is attractive. The OU Monte Carlo simulation returns a 12-month expected return of ~9.0% with a PGain of 76.3%, supporting an above-average conviction score of 4.

## Quantitative Chain

- E(R): 0.0905
- Std dev: 0.1256
- P-gain: 0.7630
- CAPM alpha: 0.1005
- Beta: 0.5547
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - RBA resumes rate hikes or holds higher-for-longer, compressing REIT multiples and widening cap rates by 40-50bps; DPU growth stalls at 1.0% as consumer spending weakens and specialty tenants face elevated vacancy; gearing rises toward 38% following Bunnings acquisition, triggering credit spread widening; AUD weakness amplifies imported cost inflation reducing tenant margin. Occupancy slips below 97% for the first time in three years.
- **base**: E(R)=0.0900
  - Central case as modelled: trailing yield 6.55%, DPU growth 2.5% supported by CPI-linked rent reviews and accretive Bunnings acquisition, multiple flat, gearing stable ~31-33%. RBA on hold through H1 2027; Australian convenience retail demand resilient. OU Monte Carlo sim return 8.99%, PGain 76.3%.
- **bull**: E(R)=0.2100
  - RBA cuts rates by 50-75bps in H1 2027, driving cap rate compression and positive multiple re-rating of 30-40bps; DPU growth accelerates to 3.5% as Charter Hall deploys additional necessity-retail pipeline; Morningstar Fair Value upgrade catalyses institutional re-weighting; Bunnings acquisition exceeds accretion guidance; AUD/GBP stability removes FX headwind for foreign investors.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0655 (Cat A) — Trailing distribution yield of 6.55% sourced from Kalkine market commentary dated July 2026 referencing CQR's published distributions; corroborated by AMIT Notice for Q ending 30 June 2026 filed ASX 25 August 2026. At AUD 3.88 spot price (2026-09-08), this implies ~25.3c trailing DPU. Treated as Category A as it derives from the issuer-published quarterly distribution and observed closing price.
- `dpu_growth_3yr` = 0.025 (Cat C) — Forward DPU growth assumption of 2.5% p.a. Basis: CQR's FY26 guidance upgrade post annual results (August 2026) and convenience retail portfolio anchored by Woolworths, Coles, and Bunnings (necessity-based tenants with long WALEs). $151M Bunnings acquisition (announced August 2026) is expected to be accretive. Organic growth constrained by rate headwinds and moderate Australian retail consumer environment. Sensitivity: 1.5% in bear, 3.5% in bull. Category C as it is a forward projection beyond consensus granularity.
- `multiple_change` = 0.0 (Cat C) — Assumed flat cap-rate/multiple environment over 12 months. Morningstar lifted Fair Value post FY26 results (August 2026) suggesting modest fundamental upside, but rate anxiety (Kalkine August 2026) and RBA policy uncertainty create offsetting pressure. Net assumption: 0% multiple contribution. Sensitivity tested ±50bps in scenario analysis.
- `gearing_ratio` = ~30-33% (Cat B) — No filed body available (ASX body capture parked per Phase 01 v3.3 §4). Estimate based on CQR's historical gearing range and news reference to debt refinancing in FY26 (Kalkine, August 2026 — 'FY26 Profit Rises as Refinancing Resets Debt Position'). Assumed below the 40% ASX REIT convention limit. Disclosed as Category B pending formal confirmation from annual report.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP (currency basis). Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- RBA rate trajectory: a renewed rate hiking cycle or prolonged restrictive policy would compress REIT multiples and widen cap rates, particularly impacting the Bunnings acquisition NTA.
- No formal gearing confirmation available (ASX body capture parked); if FY26 gearing post-Bunnings acquisition exceeds 38%, regulatory headroom narrows materially.
- Specialty tenant vulnerability: while anchor tenants (Woolworths, Coles, Bunnings) are resilient, discretionary specialty tenants in convenience centres face margin pressure from Australian consumer caution.
- AUD/GBP currency basis in beta estimation introduces noise into the CAPM alpha signal; true property-market beta may differ from the estimated 0.55.
- Macro data gap: APAC rates data unavailable via stored reader as of this as_of date; RBA policy assumption relies on news context rather than confirmed rate level.

## Invalidation Condition
Exit if CQR's reported gearing exceeds 38% for two consecutive reporting periods, or if annualised DPU declines by more than 5% versus FY26 declared distributions, or if occupancy falls below 97.0% for two consecutive quarters indicating structural anchor-tenant stress, or if Charter Hall Group announces a fee restructure that is dilutive to unitholder outcomes.
