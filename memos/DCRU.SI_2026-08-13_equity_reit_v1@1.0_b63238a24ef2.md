# Specialist Memo — DCRU.SI

**Memo ID**: `DCRU.SI_2026-08-13_equity_reit_v1@1.0_b63238a24ef2`
**Ticker**: DCRU.SI (Digital Core REIT)
**Market**: Singapore
**Sector**: Data Centre
**As of**: 2026-08-13
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
Digital Core REIT offers exposure to the secular data centre demand theme driven by AI and cloud infrastructure build-out, underpinned by a strong global sponsor in Digital Realty Trust. However, the portfolio is in active transition: the announced disposal of ~US$315.9M of North American assets and redeployment into Singapore and Osaka data centres introduces a meaningful near-term income gap and execution risk. H1 2026 distributions are only 51% covered by tax-exempt income, with the remainder returned as capital — a structural sustainability concern that triggered a qualitative gate override. At a closing price of USD 0.505 and an annualised income DPU yield of ~3.64%, the income-only yield spread over the 3.72% T-bill rate is minimal, limiting the margin of safety. An OU Monte Carlo PGain of 66% and CAPM alpha of 5.8% are directionally positive but insufficient to offset near-term DPU uncertainty at current valuations.

## Quantitative Chain

- E(R): 0.0664
- Std dev: 0.1592
- P-gain: 0.6600
- CAPM alpha: 0.0576
- Beta: 0.3548
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1200
  - North America asset disposal proceeds are redeployed at sub-optimal yields or redeployment is delayed, compressing income DPU toward 1.5c annualised. Capital distribution component ceases post-disposal. DPU coverage falls further below 1.0x, prompting a formal DPU cut. Cap rate expansion of 50bps in Singapore/Osaka data centres on rising rates. Unit price corrects 15-20% on income uncertainty. Leverage temporarily breaches 45% MAS regulatory guidance during transition.
- **base**: E(R)=0.0660
  - Central case as built in quantitative chain: income DPU yield 3.64%, 2.0% DPU growth, +1.0% multiple re-rating. Portfolio transaction completes in H2 2026 with Singapore and Osaka assets generating steady NNN lease income from 2027. Capital distribution component phases out but income DPU recovers as new assets contribute. Occupancy remains high on long-term lease structure.
- **bull**: E(R)=0.2200
  - Singapore and Osaka data centres acquired at accretive yields (>6%) with long-tenor NNN leases to investment-grade hyperscaler tenants. DPU recovers to 3.6c annualised (income + capital combined) and market reclassifies capital return as sustainable, lifting yield multiple. AI/cloud demand drives rental reversion on lease renewals. Multiple re-rating +3.0%. Sponsor Digital Realty injects additional pipeline assets at NAV-accretive prices.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=fail [override_applied=-1]
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0364 (Cat A) — H1 2026 income distribution of 0.92 US cents per unit (tax-exempt component only; source: DCRU.SI 2026-07-29 CACT capital distribution announcement). Annualised income DPU = 1.84 US cents. Yield calculated on closing price of USD 0.505 (2026-08-13). Capital return component of 0.88c per unit per half excluded as non-recurring.
- `capital_return_component` = 0.0088 (Cat A) — H1 2026 capital distribution component = 0.88 US cents per unit, annualised to 1.76c. Sourced from DCRU.SI 2026-07-29 CACT filing. Treated as non-recurring and excluded from sustainable yield calculation; included separately in scenario analysis bull case.
- `dpu_growth_3yr` = 0.02 (Cat C) — Forward DPU growth assumption of 2.0% p.a. reflecting AI/cloud demand tailwinds for data centre assets partially offset by near-term DPU dilution risk from the portfolio transition (disposal of North America assets ~US$315.9M and redeployment into Singapore and Osaka). Sensitivity: bear case applies 0% growth, bull applies 4%.
- `multiple_change` = 0.01 (Cat C) — Modest multiple re-rating assumption of +1.0% over 12 months. DCRU trades at a material discount to global data centre REIT peers post-restructuring. Successful execution of Singapore/Osaka entry could compress the discount. Sensitivity: bear case applies -2.0%, bull +3.0%.
- `portfolio_transaction` = disclosed (Cat B) — On 2026-08-12 DCRU.SI announced a portfolio transaction: disposal of North American assets for ~US$315.9M proceeds and redeployment into Singapore and Osaka data centres. Transaction introduces short-term income gap and redeployment risk. Headline sourced from DCRU.SI 2026-08-12 ANNC (SGX filing SG260812OTHRGKAJ); full attachment PDFs not parsed — body contains headline only.
- `distribution_coverage_concern` = disclosed (Cat B) — H1 2026 DPU of 1.80c comprised 0.92c tax-exempt income and 0.88c capital return. Capital distribution (49% of total) implies income AFFO coverage of the total declared DPU is below 1.0x on a like-for-like basis. This raises DPU sustainability concerns and triggered a -1 gate override on distribution_coverage. Sourced from DCRU.SI 2026-07-29 CACT filing.
- `unit_buyback` = disclosed (Cat A) — Active unit buy-back programme in place since 15 April 2026, authorised up to 129,602,591 units. On 2026-08-13, 201,800 units purchased and cancelled. Sourced from DCRU.SI 2026-08-13 ANNC (daily buy-back notice). Unitholder-aligned capital management.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between USD and GBP (DCRU.SI trades and distributes in USD). Treated as Category B input. CAPM alpha inherits the same currency and IASP noise.

## Key Risks
- Portfolio transition risk: redeployment of US$315.9M North America disposal proceeds into Singapore and Osaka assets may be delayed or completed at sub-optimal yields, prolonging the income gap and compressing DPU
- DPU sustainability: H1 2026 capital distribution component (0.88c of 1.80c) is non-recurring; income-only DPU coverage appears below 1.0x AFFO on total declared basis, raising the risk of a formal distribution cut if income redeployment is delayed
- Higher-for-longer US rates compressing data centre cap rate multiples and widening DCRU's cost of debt, given the REIT's USD-denominated balance sheet
- Elevated annualised volatility of 23.4% reflects the uncertainty embedded in the portfolio restructuring and the thinly-traded nature of the stock relative to global data centre REIT peers
- Regulatory and MAS leverage compliance during the transitional period between asset disposal settlement and acquisition completion; leverage could temporarily spike above 40-45%

## Invalidation Condition
Exit if the Singapore and Osaka acquisition yields are confirmed below 5.0% (implying no accretion over the disposal cap rate), or if DCRU announces a formal DPU cut to annualised income DPU below 1.5 US cents per unit for two consecutive reporting periods, or if MAS issues a regulatory breach notice on aggregate leverage exceeding 50% during the transitional redeployment period, or if Digital Realty Trust materially reduces its stated pipeline commitment to DCRU.
