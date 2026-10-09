# Specialist Memo — WPR.AX

**Memo ID**: `WPR.AX_2026-10-09_equity_reit_v1@1.0_ad05f2f4342b`
**Ticker**: WPR.AX (Waypoint REIT)
**Market**: Australia
**Sector**: Petrol Station / Triple-Net Retail
**As of**: 2026-10-09
**Framework**: equity_reit_v1@1.0
**Conviction score**: 4/5 (Above average)
**Max position**: 8.0%

## Thesis
Waypoint REIT offers a compelling ~7.2% distribution yield at the current AUD 2.12 price, supported by approximately 400 petrol station and convenience retail properties leased predominantly to Viva Energy under long-term triple-net agreements providing highly defensive, CPI-linked income. The ~16% price correction from August 2026 highs has created an apparent discount to NTA, with modest multiple reversion potential as the Australian rate cycle turns. Beta of 0.53 versus IASP.L (currency-basis caveat applies) is consistent with the low-volatility, bond-like characteristics of the long-WALE triple-net lease structure. The Ornstein-Uhlenbeck Monte Carlo simulation yields a PGain of 77.9% and CAPM alpha of 9.5%, supporting an above-average conviction rating at a maximum 8% position size.

## Quantitative Chain

- E(R): 0.0870
- Std dev: 0.1127
- P-gain: 0.7786
- CAPM alpha: 0.0950
- Beta: 0.5294
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - DPU growth falls to 0% as CPI-linked rent reviews stall; RBA holds rates elevated compressing yield spreads; Viva Energy faces credit stress or lease renegotiation; cap rate expansion of 30–40bps drives NTA decline; AUD weakens amplifying benchmark underperformance; price drifts toward AUD 1.80.
- **base**: E(R)=0.0870
  - Distribution yield 7.22% at AUD 2.12, DPU growth 1.0% via CPI-linked rents, +0.5% modest multiple reversion toward NTA, occupancy ~100% (triple-net), gearing ~37% within AU convention, RBA holds at 4.35%.
- **bull**: E(R)=0.2000
  - RBA pivots to rate cuts; cap rate compression lifts NTA; DPU growth 2.0% on above-CPI rent reviews; multiple reversion from AUD 2.12 toward NTA ~AUD 2.55 delivers material capital gain; institutional re-accumulation driven by yield spread normalisation.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=pass
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0722 (Cat A) — Annualised DPU estimated at ~AUD 0.153 based on Kalkine-reported ~6.87–6.89% yield at mid-July 2026 price ~AUD 2.22, implying DPU ~AUD 0.153. Applied to ASX closing price AUD 2.12 (2026-10-09) yields 7.22%. 1H2026 results announcement (ASX 2026-08-26, headline '1H2026 Results') confirms distributable earnings up 0.9% vs prior period, consistent with stable DPU.
- `dpu_growth_forward` = 0.01 (Cat C) — Forward DPU growth of 1.0% p.a. assumed based on 0.9% distributable earnings growth in 1H2026 (ASX announcement 2026-08-26) and CPI-linked rent reviews embedded in Viva Energy triple-net leases. Sensitivity tested at 0% (bear) and 2.0% (bull) in scenario analysis.
- `multiple_change` = 0.005 (Cat C) — Modest +0.5% multiple reversion in base case. WPR price declined ~16% from AUD ~2.52 (August 2026 peak) to AUD 2.12 as of 2026-10-09, creating an apparent discount to NTA. Partial mean-reversion assumed over 12 months. Zero assumed in bear; +1.5% in bull.
- `rba_cash_rate` = 0.0435 (Cat A) — RBA cash rate 4.35% per BIS WS_CBPOL_AU, observation date 2026-09-24 (15 days prior to as_of). Contextual input for AUD yield spreads and cap rate sensitivity.
- `tenant_concentration` = high (Cat A) — Waypoint REIT's ~400+ petrol station and convenience retail sites are predominantly leased to Viva Energy Group under long-term triple-net leases (~90%+ of income). Structural concentration publicly disclosed. WALE typically >10 years per WPR periodic ASX reports.
- `gearing_ratio` = 0.37 (Cat B) — Gearing estimated ~35–38% based on WPR historical disclosures and sector norms for long-WALE Australian REITs; within the AU REIT convention of <40%. Full 1H2026 financial report body not available from filing pipeline (ASX body capture pending for 2026-08-26 periodic report). Disclosed as Category B estimate.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP currency and iasp benchmark basis. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- Prolonged RBA higher-for-longer policy (current 4.35%) compressing the yield spread between WPR's distribution and the risk-free rate, sustaining the price discount to NTA.
- Viva Energy tenant credit deterioration or lease renegotiation risk given ~90%+ income concentration in a single tenant — the dominant structural risk for this REIT.
- Energy transition acceleration: rising EV adoption could structurally impair petrol station asset valuations and Viva Energy's covenant strength over a 5–10 year horizon, despite near-term triple-net contractual protection.
- Cap rate expansion driven by rising Australian long bond yields reducing NTA per unit and undermining the multiple-reversion component of the base case return.
- IASP.L currency-basis noise: beta and CAPM alpha computed against a GBP-denominated benchmark absorb AUD/GBP FX movements, reducing precision of CAPM-derived signals — both classified Category B.

## Invalidation Condition
Exit or reduce position materially if any of the following are observed: WPR gearing breaches 40% (AU REIT convention) for two consecutive reporting periods; Viva Energy announces a material lease renegotiation, early termination notice, or suffers a credit rating downgrade to sub-investment grade; distributable earnings per unit decline more than 5% year-on-year for two consecutive half-year periods indicating DPU coverage below 1.0x AFFO; or the RBA cash rate rises above 5.0% with no corresponding uplift in contracted rental income, sustaining yield spread compression below 200 basis points versus the 10-year Australian government bond rate.
