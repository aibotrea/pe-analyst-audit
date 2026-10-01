# Specialist Memo — CQE.AX

**Memo ID**: `CQE.AX_2026-09-30_equity_reit_v1@1.0_776de0176acd`
**Ticker**: CQE.AX (Charter Hall Social Infrastructure REIT)
**Market**: Australia
**Sector**: Social Infrastructure / Healthcare & Education
**As of**: 2026-09-30
**Framework**: equity_reit_v1@1.0
**Conviction score**: 4/5 (Above average)
**Max position**: 8.0%

## Thesis
Charter Hall Social Infrastructure REIT (CQE) offers a structurally defensive income stream underpinned by long-dated, CPI-linked leases across childcare, early education, and community healthcare assets — sectors benefiting from Australian government policy support and demographic demand. The trailing distribution yield of ~6.49% at AUD 2.30 provides a material spread over the RBA cash rate (4.35%) and 3-month T-bill (4.07%), compensating investors for elevated near-term rate risk. Guidance was lifted in September 2026, signalling management confidence in DPU sustainability despite the unit price pullback from August highs. The CAPM alpha of ~10.1% versus a deeply negative IASP.L benchmark return underscores CQE's idiosyncratic income quality, and the OU Monte Carlo PGain of 70.1% supports an above-average conviction score of 4 at a 12-month horizon.

## Quantitative Chain

- E(R): 0.0850
- Std dev: 0.1597
- P-gain: 0.7011
- CAPM alpha: 0.1013
- Beta: 0.6446
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - RBA holds rates at 4.35% or hikes further, driving cap-rate expansion of 50bps+; unit price falls toward AUD 1.90–2.00 range. DPU guidance retracted as childcare operator tenants face government funding cuts or occupancy declines. Gearing creeps toward 38–40% requiring equity raising at discount. Distribution coverage falls below 1.0x AFFO. AUD weakens further versus USD, suppressing foreign investor demand. This scenario also captures a stagflation/rate-shock pathway where both rents and valuations are pressured simultaneously.
- **base**: E(R)=0.0850
  - Central case as modelled: distribution yield ~6.49%, DPU growth 2.0% p.a. via CPI-linked rent escalators, zero cap-rate movement, RBA on hold. Guidance lift sustained through FY27. Occupancy stable at ~99% (social infrastructure assets structurally near-full). Gearing within 30–35% range.
- **bull**: E(R)=0.2200
  - RBA begins easing cycle in Q1 2027 (25–50bps cut), compressing cap rates and re-rating listed social infrastructure REITs. Unit price recovers toward NTA of AUD 2.80+. Charter Hall activates pipeline acquisitions accretive at 6%+ initial yield, growing DPU by 3–4%. Tenant mix broadens further into government-anchored healthcare. Multiple expansion drives 12–15% price appreciation on top of 6.5% income return.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0649 (Cat A) — Trailing annualised distribution yield of ~6.49% referenced in multiple Kalkine/news sources dated July–September 2026 for CQE.AX at prevailing unit prices. A distribution announcement was filed on 2026-09-17 (ASX: CQE, DISTRIBUTION ANNOUNCEMENT, price-sensitive). Yield is observed/published market data at AUD 2.30 close.
- `dpu_growth_3yr` = 0.02 (Cat C) — Forward DPU growth of 2.0% p.a. assumed on the basis of: (i) CPI-linked lease structures typical of social infrastructure portfolios, (ii) September 2026 news headline confirming guidance lift for CQE ('Lifts Guidance as Its Tenant Mix Broadens'), and (iii) conservative assumption given elevated RBA cash rate environment (4.35% as of 2026-09-17). Sensitivity tested in scenario analysis. Category C as this is a forward estimate beyond one consensus data point.
- `multiple_change` = 0.0 (Cat C) — Zero cap-rate / multiple change assumed in the base case. CQE has de-rated from AUD ~2.77 (early August 2026) to AUD 2.30 at 30 September 2026, suggesting cap-rate pressure from elevated Australian rates (RBA 4.35%). No meaningful multiple expansion expected until RBA easing cycle becomes visible. Sensitivity tested in scenarios.
- `rba_policy_rate` = 0.0435 (Cat A) — RBA cash rate 4.35% as of observation date 2026-09-17 (age 13 days), sourced from BIS WS_CBPOL series BIS_CBPOL_AU via stored APAC rates.
- `filing_body_data_gap` = disclosed (Cat B) — ASX filing bodies returned by get_stored_filings for CQE.AX contained mismatched content from other issuers (ALI, PM1, OZZ, CBA) — pipeline noise. Filing bodies could not be used to directly confirm AFFO coverage, gearing ratio, or NTA. Fundamental assumptions sourced from news/headline data and publicly known Charter Hall REIT characteristics. This is disclosed as a data limitation.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. currency and iasp basis acknowledged. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- Higher-for-longer RBA cash rate compressing yield spreads and continuing to pressure unit price via cap-rate expansion; the AUD 2.77 to AUD 2.30 drawdown in August–September 2026 illustrates this sensitivity.
- Government childcare funding policy changes (e.g. CCS restructuring) that could impair tenant viability or reduce occupancy, directly impacting CQE's rental income stream.
- Filing pipeline data limitation: ASX filing bodies for CQE returned mismatched issuer content; AFFO coverage and precise NTA/gearing could not be independently verified from filings — a key risk if actual financial metrics diverge from public news reporting.
- AUD/GBP and AUD/USD currency movements amplifying the IASP.L beta estimate noise, making CAPM alpha an unreliable precision input (Category B caveat applies throughout).
- Phase 2 calibration is directional only; vintage discipline and formal backtest reconciliation are pending Phase 5 — the conviction score should be interpreted as a point-in-time signal, not a validated backtested outcome.

## Invalidation Condition
Exit or reduce position materially if: (1) CQE announces a formal distribution guidance cut or DPU coverage falls below 1.0x AFFO for two consecutive reporting periods; (2) gearing exceeds 38% and management signals equity issuance at a discount to NAV to reduce leverage; (3) the Australian federal government announces a significant reduction in childcare subsidy (CCS) funding directly impairing tenant cashflow viability; or (4) unit price closes below AUD 1.95 on sustained volume, signalling fundamental re-rating beyond rate-driven technical pressure.
