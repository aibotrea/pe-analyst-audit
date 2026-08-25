# Specialist Memo — SCG.AX

**Memo ID**: `SCG.AX_2026-08-25_equity_reit_v1@1.0_abb5bee9ed3e`
**Ticker**: SCG.AX (Scentre Group)
**Market**: Australia
**Sector**: Retail/Shopping Centres
**As of**: 2026-08-25
**Framework**: equity_reit_v1@1.0
**Conviction score**: 4/5 (Above average)
**Max position**: 8.0%

## Thesis
Scentre Group is Australia's dominant retail REIT, operating 42 Westfield-branded super-regional shopping centres with near-full occupancy and a structurally advantaged portfolio of irreplaceable urban assets. H1 2026 results delivered earnings growth and a guidance upgrade, and the A$240M Bondi upgrade represents a high-conviction capital deployment into one of Australia's highest-traffic retail destinations. At AUD 3.58 — down ~9% from recent highs — the stock offers a forward distribution yield of approximately 4.9% with 3-4% DPU growth visibility, supporting a blended E(R) of ~7.9%. Beta of 0.71 versus IASP.L (currency-basis caveat applies) and a PGain of 73.9% from the OU Monte Carlo support an above-average conviction score at a 12-month horizon.

## Quantitative Chain

- E(R): 0.0790
- Std dev: 0.1225
- P-gain: 0.7390
- CAPM alpha: 0.0995
- Beta: 0.7078
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - RBA holds rates higher for longer, pushing Australian 10-year yields to 5%+ and compressing REIT multiples; retail discretionary spending weakens materially as household mortgage buffers exhaust; DPU coverage drops toward 1.0x as rent reviews stall; cap rates expand 35-50bps; occupancy slips below 97% due to specialty tenant failures; Bondi upgrade faces cost overruns. DPU flat or cut; total return negative.
- **base**: E(R)=0.0790
  - Central case as built in chain: forward DPU yield 4.9%, DPU growth 3.5% driven by specialty rent escalation and Bondi NOI contribution, modest -0.5% multiple compression. Occupancy stable at ~99%, gearing ~32%, RBA on gradual easing trajectory. H1 2026 guidance upgrade sustained through FY2026.
- **bull**: E(R)=0.1900
  - RBA delivers two or more rate cuts, re-rating retail REIT multiples; Bondi upgrade and Mt Gravatt JV proceeds are redeployed accretively; DPU growth accelerates to 5.5%; specialty sales continue strong momentum with international tourism recovery; cap rate compression of 15-20bps; stock re-rates toward AUD 4.20+.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.049 (Cat B) — Forward full-year DPU estimated at ~AUD 17.5 cents based on H1 2026 guidance upgrade (Motley Fool 24 Aug 2026: 'half year earnings climb and guidance gets a boost'; ASX DISTRIBUTION ANNOUNCEMENT SCG 2026-08-24). Divided by closing price AUD 3.58 on 2026-08-25 = 4.89%. Classified Category B as forward DPU is derived from headline guidance, not a published audited figure.
- `dpu_growth_3yr` = 0.035 (Cat C) — 3-year forward DPU growth assumption of 3.5% p.a. based on: (1) speciality sales and customer traffic growth reported in Westfield centres through 2026 (news: 'sales rise and more visitors for Westfield in 2026'); (2) A$240M Bondi upgrade adding incremental NOI from 2027; (3) CPI-linked rent escalations in lease structures typical of SCG's portfolio. Sensitivity: bear case 0%, bull case 5.5%. Category C — model assumption beyond consensus horizon.
- `multiple_change` = -0.005 (Cat C) — Modest -0.5% cap-rate-implied multiple compression applied reflecting: (i) stock has declined ~8-9% from AUD 3.93 peak in late July 2026 to AUD 3.58 at as_of, suggesting some near-term sentiment headwind; (ii) Australian retail REITs trade on stable to mildly compressing implied cap rates in a higher-for-longer RBA rate environment. Sensitivity tested in scenario analysis.
- `leverage_gearing` = 0.32 (Cat B) — SCG gearing estimated at approximately 32% based on publicly known balance sheet profile consistent with SCG's historical reporting (FY2025 gearing ~30-33%). Well within Australian A-REIT convention of <40%. No leverage covenant breach signals observed in H1 2026 announcement headlines. Filing body capture for SCG returned cross-contaminated content (unrelated ASX entities); exact H1 2026 figure not confirmable from stored filings — disclosed as gap.
- `occupancy` = 0.99 (Cat B) — SCG's Westfield portfolio has sustained ~99% occupancy across its 42 Australian and NZ centres in recent periods. 2026 news confirms continued sales and visitor growth, consistent with maintained occupancy. Filing body capture was cross-contaminated; exact H1 2026 figure not confirmable from stored filings.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP (currency basis). Treated as Category B input. CAPM alpha inherits the same noise. IASP.L 5-year annualised return of -4.4% reflects GBP-AUD cross-currency drag in addition to underlying APAC REIT fundamentals.
- `filing_body_contamination_disclosure` = disclosed (Cat B) — All 8 stored filing bodies retrieved for SCG.AX contained content from unrelated ASX entities (AEV, MEK, L1G, BRE, ALV, GOOD, WOA). This is a known pipeline issue where body capture misaligned document keys. SCG-specific financial detail (exact H1 2026 DPU quantum, gearing ratio, AFFO coverage) was therefore sourced from ASX headline metadata and news searches rather than filing body text. Material assumptions are disclosed as Category B/C accordingly.

## Key Risks
- RBA higher-for-longer risk: sustained elevated Australian rates compress REIT multiples and widen the risk-free rate spread, reducing valuation support for distribution-yield instruments
- Retail structural headwinds: ongoing e-commerce penetration growth could reduce specialty tenant demand and re-leasing spreads, particularly if discretionary spending weakens as household mortgage buffers erode
- Construction and execution risk on the A$240M Bondi upgrade, including cost overruns and temporary disruption to rental income during works
- Cap rate expansion risk if global bond yields re-accelerate, given SCG's long-duration asset profile and ~AUD 24B+ portfolio valuation sensitivity
- Filing body capture failure: H1 2026 financial details (exact DPU, gearing, AFFO coverage) could not be confirmed from stored filing bodies due to pipeline content contamination; assumptions rely on headline and news proxies

## Invalidation Condition
Exit position if: (1) SCG reports two consecutive half-year periods of DPU coverage below 1.0x AFFO, signalling distribution is unsustainable from operating cash flow; or (2) gearing rises above 38% of total assets on a reported basis, approaching the Australian A-REIT regulatory convention limit; or (3) occupancy falls below 96% for two consecutive reporting periods, indicating material specialty tenant deterioration in the Westfield portfolio; or (4) the Bondi upgrade is abandoned or materially delayed beyond 2028 delivery.
