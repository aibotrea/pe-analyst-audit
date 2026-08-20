# Specialist Memo — RGN.AX

**Memo ID**: `RGN.AX_2026-08-20_equity_reit_v1@1.0_92d4f3bf492d`
**Ticker**: RGN.AX (Region Group)
**Market**: Australia
**Sector**: Retail
**As of**: 2026-08-20
**Framework**: equity_reit_v1@1.0
**Conviction score**: 4/5 (Above average)
**Max position**: 8.0%

## Thesis
Region Group (RGN.AX) is an Australian essential-retail REIT owning approximately 100 neighbourhood and sub-regional shopping centres anchored by Woolworths and Coles, offering highly defensive, non-discretionary income. At AUD 2.27, the unit trades at a meaningful discount to estimated NTA (~AUD 2.40-2.50) following a post-FY26 results de-rating of ~6%, despite FY26 EPS growth, creating a potential re-rating catalyst over the 12-month horizon. A trailing distribution yield of ~6.5% — 279bps above the 3-month T-bill rate of 3.71% — combined with 2.5% CPI-linked DPU growth underpins an E(R) of 9.0% and a CAPM alpha of 8.8% versus a negative IASP.L benchmark return (currency-basis caveat applies). The OU Monte Carlo PGain of 82.0% supports an Above Average conviction rating, consistent with the defensive earnings profile and RBA easing tailwind.

## Quantitative Chain

- E(R): 0.0900
- Std dev: 0.0978
- P-gain: 0.8201
- CAPM alpha: 0.0882
- Beta: 0.4379
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - Distribution yield compresses as RBA pauses easing, cap rates expand 25-50bps. DPU growth stalls at 0% due to anchor-tenant renegotiations or higher vacancy in specialty tenants. Gearing rises toward 38% following asset revaluations. Multiple further de-rates as market prices in a higher-for-longer AUD rate environment. Macro tail risk: renewed inflation forcing RBA to reverse cuts, compressing the yield spread and triggering a sector-wide re-rating. Bear total return approximately -6%.
- **base**: E(R)=0.0900
  - Central case as built in quantitative chain: distribution yield 6.5%, DPU growth 2.5% from CPI-linked escalations, zero multiple change. Occupancy stable at ~99%, gearing ~32%, RBA continues gradual easing. OU Monte Carlo sim return 8.95%, PGain 82%.
- **bull**: E(R)=0.2000
  - RBA easing accelerates, compressing cap rates 20-30bps and re-rating the sector. NTA discount narrows as unit price recovers from post-FY26 de-rating (AUD 2.27 toward NTA estimate ~AUD 2.45-2.50). DPU growth beats at 3.5%+ driven by stronger specialty rent reversion and anchor lease renewals at higher rents. Portfolio occupancy holds at 99%+. Multiple expansion contributes an additional 5-8% to total return, lifting bull case to ~20%.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=info
- `distribution_coverage` — status=pass
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.065 (Cat B) — Trailing DPU estimated at ~AUD 14.8c per unit against closing price of AUD 2.27 (2026-08-20), implying a yield of ~6.5%. DPU figure derived from FY25 published DPU of ~14.4c and FY26 EPS/FFO growth signals from news headlines (RGN.AX FY26 Results Announcement 2026-08-17 and 'Do Region Group Higher EPS Figures Hint At A Deeper Earnings Quality Shift?' 2026-08-20). Filed body content was unavailable for RGN.AX FY26 Results Announcement due to ASX filing body pipeline mismatch; DPU classified Category B accordingly.
- `dpu_growth_3yr` = 0.025 (Cat C) — Forward DPU growth assumption of 2.5% pa: ~1.5% from CPI-linked rental escalations (non-discretionary neighbourhood/sub-regional retail anchored by Woolworths/Coles) plus ~1.0% from occupancy stability and rental reversion at lease renewals. Sensitivity tested in scenario analysis. RBA easing cycle supports conditions for sustained rent growth.
- `multiple_change` = 0.0 (Cat C) — Zero multiple-change assumption over 12-month horizon. RGN.AX traded at ~AUD 2.42 pre-FY26 results and de-rated to AUD 2.27 post-announcement (approximately -6% over 2026-08-17 to 2026-08-20 per stored price series). Unit price estimated at a modest discount to NTA (~AUD 2.40-2.50 estimate). Flat multiple assumed as the post-results de-rating is treated as already incorporated. Sensitivity: bull case assumes partial NTA discount recovery.
- `gearing_ratio` = 0.32 (Cat B) — Region Group has historically maintained balance-sheet gearing in the 30-33% range, comfortably within the Australian A-REIT convention of <40%. Derived from prior annual reports and news coverage of the 'essential retail model'; FY26 Annual Report body was unavailable due to ASX filing pipeline mismatch. Classified Category B pending formal confirmation from FY26 Appendix 4E filing.
- `occupancy_rate` = 0.99 (Cat B) — Region Group's neighbourhood and sub-regional centres anchored by Woolworths/Coles have consistently reported portfolio occupancy of ~99%, supported by essential non-discretionary tenants. Derived from prior reporting and Kalkine news coverage (2026-08-20: 'Region Group Essential Retail Model Is Building Long-Term Income Visibility'). FY26 body unavailable — classified Category B.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input due to currency basis noise. CAPM alpha inherits the same noise. The IASP.L benchmark is the FTSE EPRA/NAREIT Asia Developed index ETF quoted in GBP; AUD/GBP movements over the 252-day estimation window contribute to measured beta of 0.44.

## Key Risks
- Higher-for-longer AUD interest rates compressing the yield spread versus the RBA cash rate and T-bill, reversing valuation re-rating.
- Anchor-tenant renegotiation risk: Woolworths or Coles renegotiating lease terms at materially lower rents at renewal, given their substantial bargaining leverage as anchor tenants.
- Post-results share price weakness and market scepticism (shares slipped ~6% over 2026-08-17 to 2026-08-20 despite positive FY26 EPS growth) may reflect undisclosed earnings quality concerns warranting monitoring.
- Cap rate expansion driven by global base rate rises or a deterioration in Australian retail property fundamentals compressing NTA and triggering loan covenant pressure at higher gearing.
- IASP.L currency-basis noise in beta and CAPM alpha computations: AUD/GBP FX co-movement is embedded in the 0.44 beta estimate, making CAPM-derived required returns a Category B signal only.

## Invalidation Condition
Exit position if portfolio occupancy falls below 95% for two consecutive reporting periods, or if annualised DPU declines more than 5% from FY26 levels signalling coverage deterioration, or if balance-sheet gearing breaches 38% following asset revaluations, or if either Woolworths or Coles formally provides notice of non-renewal on more than 10% of anchor leases by GLA — any of these would materially impair the essential-retail income thesis underpinning the 6.5% yield and 2.5% DPU growth assumption.
