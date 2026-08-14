# Specialist Memo — CLW.AX

**Memo ID**: `CLW.AX_2026-08-14_equity_reit_v1@1.0_2e610d9107b5`
**Ticker**: CLW.AX (Charter Hall Long WALE REIT)
**Market**: Australia
**Sector**: Diversified Long WALE / Essential Services
**As of**: 2026-08-14
**Framework**: equity_reit_v1@1.0
**Conviction score**: 4/5 (Above average)
**Max position**: 8.0%

## Thesis
Charter Hall Long WALE REIT offers a compelling risk-adjusted yield of ~7.1% at current prices of AUD 3.58, representing a ~24% discount to NTA of AUD 4.71, with income underpinned by long WALE leases (historically 12+ years) to government and essential-services tenants. FY26 operating EPS of 25.5 cents demonstrates 2% earnings growth, supported by fixed and CPI-linked rent reviews that provide organic income visibility in the near term. The completed $2B refinancing removes near-term debt maturity risk while beta of 0.62 versus IASP.L (currency-basis caveat applies) implies moderate systematic risk relative to the APAC REIT benchmark. OU Monte Carlo simulation yields a PGain of 78.2% and CAPM alpha of 10.3% over a 12-month horizon, supporting an above-average conviction rating, subject to monitoring of RBA rate trajectory and distribution coverage metrics.

## Quantitative Chain

- E(R): 0.0910
- Std dev: 0.1163
- P-gain: 0.7816
- CAPM alpha: 0.1033
- Beta: 0.6166
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0500
  - RBA reaccelerates tightening or rates remain higher for longer, pushing cap rates wider and compressing NTA further toward AUD 4.20; distribution flat (0% growth) as tenant stress emerges in non-government segment; gearing rises above 40% AU convention threshold if asset values fall; discount to NTA widens beyond 30%; potential for distribution cut if interest coverage deteriorates. Rate-shock scenario: 25bps+ upward repricing of Australian long-term rates is the primary bear-case driver.
- **base**: E(R)=0.0910
  - Central case as built in quantitative chain: distribution yield 7.12%, DPU growth 2.0% p.a., multiple change neutral (0%), gearing stable at ~38%, occupancy >99%, long WALE provides income visibility. RBA eases modestly, providing mild tailwind to sector valuations but insufficient for significant multiple re-rating.
- **bull**: E(R)=0.2000
  - RBA cuts accelerate (>75bps), compressing cap rates and narrowing discount to NTA toward AUD 4.40-4.50 (partial mean reversion from 24% discount); DPU growth accelerates to 3%+ as CPI-linked rent reviews contribute; sponsor Charter Hall injects accretive pipeline assets at 6%+ initial yields; multiple expansion of ~8-10% from discount-to-NTA compression.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0712 (Cat A) — FY26 operating EPS of 25.5 cents per unit (Kalkine, 12 Aug 2026, citing CLW FY26 Full Year Results ASX announcement 12 Aug 2026). Closing price AUD 3.58 on 2026-08-14 (observed). Implied trailing yield = 0.255 / 3.58 = 7.12%. CLW distributes substantially all operating earnings; distribution approximated as equal to operating EPS.
- `dpu_growth_3yr` = 0.02 (Cat C) — FY26 reported 2% growth in operating earnings (Investing.com/GuruFocus earnings call summaries, 12-13 Aug 2026). CLW's portfolio is underpinned by long WALE leases (~12+ years) with fixed and CPI-linked rent reviews providing organic growth visibility. Forward growth assumption of 2.0% p.a. is consistent with FY26 realised growth and conservative given limited near-term AUM expansion signalled. Sensitivity: bull case assumes 3%, bear case assumes 0%.
- `multiple_change` = 0.0 (Cat C) — CLW trades at a significant discount to NTA of AUD 4.71 (Kalkine, 12 Aug 2026, citing CLW FY26 results). Discount to NTA is ~24% (3.58 vs 4.71). While this creates potential mean-reversion upside, persistent rate headwinds in Australia and sector-wide compression of REIT multiples justify a neutral (0%) multiple change assumption in the base case. Bull case assumes partial NTA convergence; bear case assumes further discount widening.
- `nta_per_unit` = 4.71 (Cat A) — NTA of AUD 4.71 per unit as reported in CLW FY26 Full Year Results, ASX announcement 12 Aug 2026 (Kalkine citation confirmed by Market Index).
- `leverage_gearing` = 0.38 (Cat B) — CLW completed a $2B debt refinancing programme in FY26 (Investing.com FY26 slides summary, 13 Aug 2026). Historical gearing for CLW has run in the 36-40% range. Estimated at ~38% look-through gearing, within the Australian REIT convention of <40%. Category B as derived from headline disclosure without explicit balance-sheet breakdown in available data.
- `occupancy_wale` = high_occupancy_long_wale (Cat B) — CLW's portfolio is characterised by long WALE leases (historically 12+ years) with government, social infrastructure, and corporate tenants (BP, Coles, Telstra, government entities). Portfolio resilience noted in FY26 results (Kalkine, 13 Aug 2026: 'Portfolio Resilience and Capital Management Progress'). Occupancy assumed >99% given essential services / government tenant base.
- `rba_cash_rate` = 0.04 (Cat C) — RBA stored APAC rates returned no data for AU as of 2026-08-14. Assumed RBA cash rate of approximately 4.0% based on publicly known easing trajectory from 4.35% peak. Used as contextual input only; does not enter CAPM chain (US T-bill rate used for Rf).
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same currency and iasp basis noise.

## Key Risks
- Higher-for-longer Australian interest rates widening cap rates and further compressing NTA below AUD 4.71, extending the persistent discount-to-NTA and reducing mark-to-market returns.
- Distribution coverage at approximately 1.0x OEPS leaves no margin of safety; any earnings miss or interest cost increase could force a distribution cut, triggering a further derating.
- Concentration risk in long-duration leases means limited re-leasing upside in a rising rental market; if market rents rise sharply, CLW's fixed rent reviews limit participation.
- Gearing near the 38-40% AU convention limit limits acquisition capacity; sponsor pipeline deployment is constrained if equity is not available at acceptable dilution levels.
- Currency basis in the IASP.L beta calculation absorbs AUD/GBP FX co-movement; the computed alpha of 10.3% inherits this noise and may overstate true excess return. Phase 2 calibration is directional only — formal backtest validation pending Phase 5.

## Invalidation Condition
Exit the position if: (1) CLW's reported gearing rises above 40.0% for two consecutive semi-annual reporting periods, breaching the Australian REIT convention threshold; (2) DPU is formally cut or guided lower by management, indicating distribution coverage below 1.0x operating earnings for two consecutive periods; (3) WALE falls materially below 10 years due to lease terminations or major tenant defaults; or (4) Charter Hall Group formally reduces or withdraws pipeline commitments to CLW.
