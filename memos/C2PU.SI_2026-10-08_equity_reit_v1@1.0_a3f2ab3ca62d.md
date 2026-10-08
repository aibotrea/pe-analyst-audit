# Specialist Memo — C2PU.SI

**Memo ID**: `C2PU.SI_2026-10-08_equity_reit_v1@1.0_a3f2ab3ca62d`
**Ticker**: C2PU.SI (Parkway Life REIT)
**Market**: Singapore
**Sector**: Healthcare
**As of**: 2026-10-08
**Framework**: equity_reit_v1@1.0
**Conviction score**: 5/5 (High)
**Max position**: 12.0%

## Thesis
Parkway Life REIT is Singapore's premier healthcare REIT, underpinned by three private hospitals master-leased to IHH Healthcare on long-term CPI-linked agreements that provide exceptional income visibility and resilience. Q1 2026 DPU growth of 15.1% YoY to S$0.0442 confirms the strength of the Singapore hospital rent revision cycle, supporting a 4.0% forward DPU growth assumption that, combined with a 4.45% distribution yield at SGD 3.97, produces an E(R) of 8.45%. With annualised volatility of only 10.2% and beta of 0.22 versus IASP.L (currency-basis caveat applies), the OU Monte Carlo delivers a PGain of 88.9%, and CAPM alpha of 6.45% over a deeply negative benchmark return confirms strong standalone expected outperformance. Estimated gearing of ~35% — well within the 50% MAS limit — and the IHH Healthcare sponsor's demonstrated pipeline commitment underpin all qualitative gates, warranting a Conviction 5 (High) rating.

## Quantitative Chain

- E(R): 0.0845
- Std dev: 0.0690
- P-gain: 0.8887
- CAPM alpha: 0.0645
- Beta: 0.2211
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0400
  - Singapore CPI turns negative or hospital lease revisions are rebased downward; Japan JPY weakens materially vs SGD reducing overseas income contribution; cap rate expansion of 25-50bps compresses NAV; DPU growth stalls at 0%; MAS raises regulatory gearing limits forcing equity dilution; global risk-off episode including a hard-landing scenario causes re-rating of defensive REITs downward.
- **base**: E(R)=0.0845
  - Central case as built in chain: distribution yield 4.45%, DPU growth 4.0% driven by CPI-linked Singapore hospital lease step-ups and Japan nursing home revisions, zero multiple change, gearing stable at ~35%, occupancy effectively 100% on master-lease structure.
- **bull**: E(R)=0.1800
  - Singapore hospital rental revision exceeds CPI, DPU growth accelerates to 7%+; IHH Healthcare injects additional Japan or ASEAN healthcare assets into PLife REIT at accretive yields; SGD/JPY stabilises or strengthens; market re-rates healthcare REITs to a lower implied cap rate, driving NAV expansion; total return approaches 18%.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=pass
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0445 (Cat A) — Q1 2026 DPU of S$0.0442 annualised to S$0.1768 (×4) divided by closing price of SGD 3.97 on 2026-10-08. Source: Business Times report 2026-04-30 (Q1 DPU +15.1% YoY). PLife REIT pays semi-annually; annualised run-rate used as observed published figure.
- `dpu_growth_3yr` = 0.04 (Cat C) — Forward DPU growth of 4.0% p.a. assumed, reflecting: (i) Singapore hospital master leases linked to CPI with periodic step-ups; (ii) Japan nursing home portfolio rental revisions; (iii) conservative haircut from Q1 2026 YoY of +15.1% to normalise base effects. Sensitivity: bear case 0%, bull case 7%. Category C model assumption.
- `multiple_change` = 0.0 (Cat C) — Zero multiple change assumed for 12-month horizon. Healthcare REIT premium valuations appear stable given resilient occupancy and defensive income streams. No significant cap-rate expansion or compression assumed. Category C assumption; bear case applies +25bps cap-rate drag.
- `singapore_hospital_lease_structure` = CPI-linked master leases (Cat A) — PLife REIT's three Singapore private hospitals (Gleneagles, Mount Elizabeth Orchard, Parkway East) operate under long-term master lease agreements with IHH Healthcare, providing CPI-indexed step-up rental revisions. Well-documented in annual reports and confirmed by Q1 2026 DPU growth disclosure.
- `leverage_gearing` = 0.35 (Cat B) — Estimated aggregate leverage ratio ~35%, derived from PLife REIT's consistently reported gearing in the 35-38% range across recent half-year results. Well within Singapore MAS regulatory limit of 50%. No filed data as of as_of date available in stored filings (count=0); estimate based on last-known public disclosures and news references.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between SGD and GBP (currency basis). Treated as Category B input. CAPM alpha inherits the same noise. Beta of 0.221 reflects PLife REIT's defensive healthcare income characteristics and low correlation with the broader APAC REIT index.

## Key Risks
- SGD/JPY exchange rate depreciation: approximately 40-50% of PLife REIT's assets are Japan nursing homes; a sustained JPY weakening against SGD directly reduces DPU translated into Singapore dollars.
- Singapore hospital lease reset risk: although CPI-linked, any structural renegotiation with IHH Healthcare at lease expiry could reset rents below current run-rate, materially impacting DPU.
- Interest rate sensitivity: a resurgence in SGD rates (SORA) beyond current levels would narrow the yield spread and potentially compress valuation multiples despite the defensive income profile.
- Concentration and master-lease dependence: IHH Healthcare is effectively both the sponsor and the master lessee; any credit deterioration at IHH (leverage, regulatory fines, patient litigation) would directly impair PLife REIT's income.
- No stored filings available in the platform (count=0 for C2PU.SI): leverage, AFFO coverage, and WALE figures are estimated from public news and prior disclosures, not from a verified filing body; this represents a data-quality gap in the analysis.

## Invalidation Condition
Exit position if PLife REIT's reported aggregate leverage ratio exceeds 45% for two consecutive reporting periods, or if IHH Healthcare announces a material adverse change to any Singapore hospital master lease (rent reset, early termination, or renegotiation below CPI), or if DPU coverage drops below 1.0x AFFO for two consecutive half-years, or if annualised DPU growth turns negative on a trailing twelve-month basis, reversing the established CPI-linked step-up track record.
