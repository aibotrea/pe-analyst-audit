# Specialist Memo — DCRU.SI

**Memo ID**: `DCRU.SI_2026-08-14_equity_reit_v1@1.0_50115bfbbe48`
**Ticker**: DCRU.SI (Digital Core REIT)
**Market**: Singapore
**Sector**: Data Centre
**As of**: 2026-08-14
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Digital Core REIT (DCRU.SI) offers pure-play exposure to hyperscale data centres across North America, Europe, and Asia Pacific, sponsored by Digital Realty Trust. At a closing price of US$0.515, the annualised DPU of ~US$0.036 implies a distribution yield of approximately 7.0%, providing a meaningful spread of ~330bps over the 3.71% 3-month T-bill rate. Beta of 0.35 versus IASP.L (currency-basis caveat applies) indicates relatively contained co-movement with the broader APAC REIT universe. The OU Monte Carlo produces a simulated 12-month return of 8.9% with a PGain of 71.2%, and CAPM alpha of 8.1% reflects strong risk-adjusted outperformance relative to the current negative benchmark return environment. Conviction is held at Moderate (3/5) rather than Above Average due to the unresolved portfolio transaction announced 2026-08-12 (attachment-only filing, details unknown), elevated historical volatility of 23.5%, and USD-denominated income sensitivity to USD/SGD and global rate movements.

## Quantitative Chain

- E(R): 0.0900
- Std dev: 0.1597
- P-gain: 0.7119
- CAPM alpha: 0.0813
- Beta: 0.3541
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - Portfolio transaction proves dilutive (equity placement below NAV or highly leveraged acquisition); gearing rises to 43-44%; DPU cut by 15-20% from tenant non-renewal at a major data centre; cap rate expansion of 50bps on weaker sentiment; USD rate cuts delayed; yield spread narrows and total return turns negative. Includes rate-shock scenario where US 10-year rises above 5%, compressing data centre REIT multiples globally.
- **base**: E(R)=0.0900
  - Central case as built in quantitative chain: annualised DPU ~US$0.036, distribution yield 6.99%, DPU growth 1.5%, multiple change +0.5%, gearing stable ~37%, portfolio transaction neutral to mildly accretive, occupancy maintained above 95%.
- **bull**: E(R)=0.2200
  - Portfolio transaction is an accretive disposal at above-NAV pricing, proceeds used for buybacks or debt reduction; DPU growth accelerates to 3-4% driven by hyperscaler AI demand driving new leases; USD rate cuts materialise in H2 2026 reducing interest costs; multiple re-rates toward 8x P/FFO from current depressed levels; Cohen & Steers increases its position.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=info [override_applied=-1]
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0699 (Cat A) — Annualised DPU of US$0.036 (2x H1 2026 DPU of US$0.018 per unit, sourced from Business Times report referencing DCRU.SI 2026-07-29 H1 results) divided by closing price of US$0.515 on 2026-08-14. H1 DPU confirmed flat year-on-year.
- `dpu_growth_3yr` = 0.015 (Cat C) — Forward DPU growth of 1.5% p.a. reflects data centre demand tailwinds (AI/cloud hyperscaler leasing) partially offset by elevated USD interest costs on floating-rate debt. H1 2026 DPU was flat (US$0.018 vs US$0.018 in H1 2025), so organic growth is assumed to inflect modestly from 2H 2026. Unit buyback programme (mandate authorised 129.6 million units from 15-Apr-2026, active daily as of 2026-08-13/14 filings DCRU.SI ANNC) provides per-unit DPU accretion offsetting flat absolute distributable income. Sensitivity: 0% to 3% range tested in scenario analysis.
- `multiple_change` = 0.005 (Cat C) — Modest positive multiple re-rating (+0.5%) assumed from (1) portfolio transaction announced 2026-08-12 (DCRU.SI ANNC SG260812OTHRGKAJ — details not available due to PDF attachments), (2) active unit buyback reducing unit count, and (3) Cohen & Steers (substantial unitholder) increasing interest per 2026-08-07 filing. Range: -1.0% to +2.0% tested in scenarios. Portfolio transaction could be dilutive or accretive — outcome unknown.
- `portfolio_transaction_risk` = unresolved (Cat B) — Portfolio transaction announced 2026-08-12 with trading halt (2026-08-11 to 2026-08-12); halt lifted 2026-08-12 13:00. Attachment bodies not captured (PDF attachments only). Transaction nature — acquisition, disposal, or swap — unknown. Price rose ~5% on announcement day (from ~$0.475 to ~$0.500). Treated as Category B elevated risk factor; conviction overridden -1 step.
- `leverage_ratio` = 0.37 (Cat B) — Estimated aggregate leverage ~37% based on prior filings and Beansprout commentary (Apr 2026) citing stable distributable income. Digital Core REIT has historically operated below the Singapore 45% MAS aggregate leverage limit. Estimate not confirmed from H1 2026 results filing body (filing body captured is the script/remarks attachment only, not the results announcement itself). Category B due to estimation.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between USD and GBP. DCRU.SI trades in USD (Singapore-listed but USD-denominated). Currency basis between USD and GBP creates noise in the beta estimate. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- Portfolio transaction announced 2026-08-12 (DCRU.SI ANNC SG260812OTHRGKAJ) has unknown financial terms; potential equity issuance or debt increase could be dilutive to DPU and NAV.
- Elevated historical volatility (23.5% annualised, 252-day) reflects prior tenant concentration risk episodes; single data centre tenant vacancies can cause large DPU step-downs.
- USD interest rate sensitivity: DCRU.SI distributes in USD and carries USD-denominated floating-rate debt; a higher-for-longer rate environment compresses distributable income and widens the cap rate.
- Negative IASP.L benchmark return (-4.3% annualised over 5 years) signals broad APAC REIT headwinds; DCRU.SI is not immune to sector-level valuation compression.
- Cohen & Steers substantial unitholder position change (filed 2026-08-07) introduces institutional flow risk if the position is being reduced rather than increased.

## Invalidation Condition
Exit if: (1) the portfolio transaction announced 2026-08-12 involves equity issuance at a price below NAV per unit or increases gearing above 42% (approaching the 45% MAS limit); (2) DPU coverage falls below 1.0x AFFO for two consecutive reporting periods; (3) occupancy across the portfolio drops below 90% for two consecutive quarters; or (4) Digital Realty Trust (sponsor) materially reduces its stake or withdraws pipeline asset commitments to DCRU.SI.
