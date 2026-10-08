# Specialist Memo — SCG.AX

**Memo ID**: `SCG.AX_2026-10-08_equity_reit_v1@1.0_fee9d68f68d6`
**Ticker**: SCG.AX (Scentre Group)
**Market**: Australia
**Sector**: Retail/Shopping Centres
**As of**: 2026-10-08
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Scentre Group offers investors concentrated exposure to Australia's highest-quality dominant Westfield shopping centres, supported by a 5.14% distribution yield backed by resilient specialty retail sales productivity and near-full (~99%) occupancy across its 42-centre portfolio. The internally managed structure eliminates external manager fee drag and aligns management incentives directly with unitholder outcomes. Beta of 0.73 versus IASP.L (currency-basis caveat: AUD/GBP) reflects moderate systemic sensitivity; OU Monte Carlo PGain of ~70% at 12 months provides moderate conviction given the still-elevated RBA cash rate of 4.35% constraining cap-rate compression and limiting upside multiple expansion. The October 2026 US$750M senior notes pricing demonstrates continued capital markets access but also confirms ongoing leverage extension in a higher-cost debt environment.

## Quantitative Chain

- E(R): 0.0664
- Std dev: 0.1258
- P-gain: 0.6996
- CAPM alpha: 0.0930
- Beta: 0.7251
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - RBA fails to cut rates; AUD financing costs remain elevated, cap rates expand 30-50bps compressing NTA. Retail spending weakens materially under consumer-led recession, specialty-sales productivity declines, DPU coverage falls below 1.0x. US$750M senior notes refinancing costs weigh on distributable income. Occupancy dips to ~97.5% from ~99%.
- **base**: E(R)=0.0664
  - Central case as built in chain: 5.14% distribution yield, 2.0% DPU growth from CPI escalation and Westfield Mt Gravatt JV accretion, -0.5% multiple headwind from stable-but-elevated RBA rate. Occupancy maintained ~99%, specialty sales productivity steady.
- **bull**: E(R)=0.1800
  - RBA delivers 75bps+ of rate cuts by mid-2027, cap rates compress 20-30bps and NTA re-rates upward. Consumer spending accelerates, specialty sales productivity rises, DPU growth upgrades to 3.5%+. Additional Westfield asset JV transactions (beyond Mt Gravatt) recycle capital at accretive yields. Multiple expansion contributes 3-4% above yield.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=pass
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0514 (Cat A) — Trailing DPU yield of 5.14% cited in published market data as of September 2026 (Kalkine, 9 Sep 2026 headline: 'SCG Dividend Watch: Scentre Group's 5.14% Yield'). Current price AUD 3.44, Category A observable closing price.
- `dpu_growth_3yr` = 0.02 (Cat C) — Forward DPU growth assumption of 2.0% p.a.: ~1.5% organic from CPI-linked and fixed rental escalation across Westfield portfolio leases, plus ~0.5% from ART JV capital recycling accretion (Westfield Mt Gravatt transaction satisfied per ASX 26 Aug 2026 announcement). Sensitivity tested in scenario analysis.
- `multiple_change` = -0.005 (Cat C) — Slight cap-rate headwind (-0.5%) assumed given RBA cash rate of 4.35% (BIS data, observation 24 Sep 2026) keeping financing costs elevated. No material cap rate compression expected at 12-month horizon; Australian retail property market stable but not re-rating.
- `rba_cash_rate` = 0.0435 (Cat A) — RBA policy rate 4.35% per BIS WS_CBPOL series, observation date 2026-09-24, age 14 days. Represents the risk-free borrowing environment for Australian REITs.
- `scg_senior_notes` = disclosed (Cat A) — Scentre Group priced US$750 million of senior notes on 2026-10-08 (ASX announcement, price-sensitive: false). Adds to gross debt but consistent with SCG's established offshore MTN programme; gearing assumed to remain within AU REIT convention of <40%.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input due to currency basis between the AUD-denominated SCG.AX and the GBP IASP.L index. CAPM alpha inherits the same noise.

## Key Risks
- Higher-for-longer RBA cash rate (currently 4.35%) preventing meaningful cap-rate compression and constraining NTA recovery and total return upside
- Australian consumer spending weakness reducing specialty retail sales productivity across Westfield centres, increasing lease renegotiation risk at expiry
- Refinancing cost escalation from US$750M senior notes (priced October 2026) and other offshore debt tranches compressing distributable income
- Concentration risk: top-3 assets (Westfield Sydney, Bondi Junction, Parramatta) represent disproportionate portfolio value in Sydney metro, creating geographic and demand-cycle concentration
- IASP.L benchmark currency basis in beta calculation introduces noise into CAPM alpha estimate; actual AUD-denominated outperformance may differ materially from the computed 9.3% alpha

## Invalidation Condition
Exit position if portfolio occupancy falls below 97% for two consecutive reporting periods, or if SCG announces DPU distribution coverage falling below 1.0x AFFO for any half-year period, or if gearing (look-through) exceeds 38% of total assets following the US$750M senior note issuance and any subsequent debt capital markets activity, or if RBA raises rates above 5.0% signalling a renewed tightening cycle materially worsening the cap-rate and refinancing environment.
