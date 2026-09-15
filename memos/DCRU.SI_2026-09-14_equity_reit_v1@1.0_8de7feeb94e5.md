# Specialist Memo — DCRU.SI

**Memo ID**: `DCRU.SI_2026-09-14_equity_reit_v1@1.0_8de7feeb94e5`
**Ticker**: DCRU.SI (Digital Core REIT)
**Market**: Singapore
**Sector**: Data Centre
**As of**: 2026-09-14
**Framework**: equity_reit_v1@1.0
**Conviction score**: 1/5 (Speculative)
**Max position**: 1.0%

## Thesis
Digital Core REIT offers exposure to the secular data centre demand theme (AI, cloud) backed by sponsor Digital Realty, a global data centre platform with deep operational capabilities. However, the REIT is mid-execution of a material portfolio repositioning — disposing of US$315.9 million in North American assets and pivoting into Singapore — which creates significant near-term income uncertainty. The annualised distribution yield of ~7.4% is superficially attractive but is meaningfully degraded by the fact that approximately 49% of the 1H26 DPU was classified as capital return rather than income, raising serious questions about AFFO coverage. With an OU Monte Carlo PGain of only 64.9% and annualised volatility of 24.4%, the risk-adjusted case for a meaningful position is weak at this stage of the repositioning; the memo assigns a Speculative conviction score of 1 pending execution evidence.

## Quantitative Chain

- E(R): 0.0640
- Std dev: 0.1656
- P-gain: 0.6487
- CAPM alpha: 0.0554
- Beta: 0.3435
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1500
  - North America asset disposal executes at distressed pricing, proceeds redeployed into Singapore assets at lower initial yields. DPU cut of 15–20% as capital distribution proportion rises further and income base shrinks. Cap rate expansion of 50bps in data centre sector on rate shock or AI demand disappointment. Occupancy pressure at legacy US facilities pre-sale depresses near-term income. Gearing may breach 45% threshold if asset values decline prior to disposal completion, triggering regulatory concern.
- **base**: E(R)=0.0630
  - Asset sale completes at announced terms (~US$315.9M). Proceeds redeployed into Singapore data centre assets at mid-to-high single digit yields by mid-2027. Annualised DPU flat at ~3.60 US cents. Capital distribution portion stabilises as Singapore portfolio income ramps. Unit buyback programme continues, providing modest NAV support. Multiple broadly flat with slight compression (-1%) on transition uncertainty.
- **bull**: E(R)=0.2200
  - Asset disposal at or above book value; Singapore data centre acquisitions immediately accretive at 6.5%+ yields. DPU recovers toward 4.0+ US cents annualised as income distribution component rises to 80%+ of total. Strong AI/cloud demand drives occupancy to 99%+ at Singapore assets. Sector re-rating on data centre growth narrative lifts P/NAV; unit buyback accretion amplified. Capital distribution proportion reduces substantially, improving distribution quality score.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=fail [override_applied=-1]
- `asset_quality_concentration` — status=info [override_applied=-1]
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0742 (Cat A) — 1H26 DPU of 1.80 US cents per unit (period 1 Jan–30 Jun 2026) annualised to 3.60 US cents. Current unit price USD 0.485 as of 2026-09-14. Yield = 0.0360 / 0.485 = 7.42%. Source: DCRU.SI SGX CACT filing 2026-07-29 (Capital Distribution) and observed closing price.
- `capital_return_component` = 0.49 (Cat A) — Of the 1.80 US cents 1H26 DPU, 0.88 US cents (48.9%) is classified as capital distribution rather than tax-exempt income distribution (0.92 US cents). This materially reduces income quality and AFFO coverage confidence. Source: DCRU.SI SGX CACT filing 2026-07-29.
- `dpu_growth` = 0.0 (Cat C) — Zero DPU growth assumed for 12-month forward period. DCRU is executing a portfolio repositioning: proposed US$315.9 million North America asset sale announced circa 12 Aug 2026, with strategic entry into Singapore market. Income disruption during transition and partial return-of-capital in distributions create downside bias; offset by asset recycling into higher-yield Singapore assets. Net assumption: flat DPU at base case. Sensitivity: -5% in bear, +5% in bull.
- `multiple_change` = -0.01 (Cat C) — Modest -1% multiple compression assumed reflecting portfolio transition uncertainty, elevated capital distribution proportion, and ongoing unit buyback program partially offset. Data centre sector tailwinds (AI/cloud demand) provide modest counterbalance. Net: slight compression in base case.
- `portfolio_repositioning` = disclosed (Cat B) — Digital Core REIT proposed disposal of US$315.9 million North America assets and strategic entry into Singapore data centres per Business Times reporting 2026-08-12 and SGX trading halt filing 2026-08-11. Magnitude of transaction is material (~estimated 30-40% of portfolio). Execution risk on deployment of proceeds is a Category B estimate.
- `unit_buyback_programme` = disclosed (Cat A) — Active unit buyback programme authorised up to 129,602,591 units from 15 April 2026. Daily purchases of 1,000,000 units observed in filings dated 2026-08-27 through 2026-09-04 (DCRU.SI SGX ANNC filings). CEO John Stewart is named signatory. Positive signal for NAV management.
- `leverage_within_sg_limit` = estimated_compliant (Cat B) — No specific gearing ratio disclosed in available filing bodies. Large asset sale (US$315.9M) if completed should reduce aggregate leverage. SG MAS limit is 45% (50% with credit rating). Estimate from context: likely below 45% post-disposal. Full financial statements for 1H26 are referenced but body not available for numerical extraction.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between USD and GBP, since DCRU distributes and trades in USD while IASP.L is priced in GBP. This is a currency and IASP basis issue. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- Distribution quality risk: ~49% of 1H26 DPU is capital return (not AFFO income); if the income component does not recover post-repositioning, DPU may need to be cut materially to sustainable levels.
- Execution risk on North America asset disposal: the US$315.9M transaction may face pricing, regulatory or closing delays; proceeds redeployment into Singapore assets may take 12–18 months, creating a distribution gap.
- Data centre sector concentration and customer credit: single-sector focus and potential high hyperscaler tenant concentration means any large customer non-renewal or default would be severely dilutive to income.
- Interest rate sensitivity: DCRU's USD-denominated portfolio carries basis risk versus SGD listing currency; higher-for-longer US rates compress yield spreads and raise refinancing costs on variable-rate debt.
- Regulatory and tax risk: the US Section 1446 withholding tax notices (filed 2026-06-30 and 2026-07-29) indicate ongoing US tax complexity for Singapore unitholders; changes in US REIT tax treatment could affect distributions.

## Invalidation Condition
Exit signal triggered if any of the following occur: (1) DPU cut of more than 15% from the annualised 3.60 US cents base (i.e. annualised DPU falls below ~3.06 US cents) confirmed in two consecutive semi-annual periods; (2) capital distribution proportion remains above 40% of total DPU for two consecutive periods without a credible timeline to income recovery; (3) the announced US$315.9 million North America asset disposal fails to close or closes at more than 10% below announced consideration; (4) aggregate leverage breaches the 45% MAS regulatory limit; or (5) Digital Realty materially reduces its sponsorship commitment to DCRU, including withdrawal of pipeline assets or sale of its sponsor stake below 30%.
