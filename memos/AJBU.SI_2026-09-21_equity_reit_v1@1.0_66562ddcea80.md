# Specialist Memo — AJBU.SI

**Memo ID**: `AJBU.SI_2026-09-21_equity_reit_v1@1.0_66562ddcea80`
**Ticker**: AJBU.SI (Keppel DC REIT)
**Market**: Singapore
**Sector**: Data Centre
**As of**: 2026-09-21
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Keppel DC REIT is Singapore's largest pure-play data centre REIT, with structural demand tailwinds from AI and cloud adoption supporting a ~5.5% distribution yield at current prices of SGD 2.13. The sponsor (Keppel Ltd, Temasek-linked) has demonstrated pipeline commitment, and data centre S-REITs are reportedly powering ahead on AI and cloud growth as of mid-2026. Beta of 0.22 versus IASP.L (currency-basis caveat applies) implies relatively low co-movement with the broader APAC REIT index, consistent with the sector's idiosyncratic demand drivers. PGain of 81.6% from the OU Monte Carlo at a 12-month horizon supports a moderate conviction position, tempered by the unexplained September 2026 trading halt, ongoing substantial unitholder movements among Keppel entities, and the concentration risk inherent to a single-sector REIT.

## Quantitative Chain

- E(R): 0.0900
- Std dev: 0.0996
- P-gain: 0.8157
- CAPM alpha: 0.0702
- Beta: 0.2232
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - Trading halt catalyst revealed as material negative event (e.g. major tenant non-renewal or data centre outage). DPU cut of 15-20%, occupancy declines to 92%, cap rate expansion of 50bps compresses NAV, and gearing approaches regulatory ceiling. Rate shock scenario: SGD rates rise a further 75bps, eroding the yield spread to near zero and triggering multiple compression.
- **base**: E(R)=0.0900
  - Central case as built in the quantitative chain: distribution yield ~5.5%, DPU growth 3.5% p.a., occupancy stable at ~97%, gearing ~37%, cap rates flat. Keppel Group maintains pipeline commitment and sponsor stake.
- **bull**: E(R)=0.2200
  - AI/cloud demand accelerates further, driving occupancy above 99% and enabling above-forecast DPU growth of 6-7%. Keppel Group injects accretive new data centre assets at yields above 7%. Multiple re-rating as global rates begin declining and data centre premium valuations recover. Trading halt resolved as a non-event.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=info [override_applied=-1]
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.055 (Cat A) — Derived from filed DPU of SGD 0.02261 per unit for 71-day period (1 Jul 2026 to 9 Sep 2026), annualised to approximately SGD 0.1163 per unit, divided by closing price of SGD 2.13 on 2026-09-21. Source: AJBU.SI 2026-09-01 Cash Dividend/Distribution filing (SGX CACT).
- `dpu_growth_3yr` = 0.035 (Cat B) — Forward DPU growth of 3.5% p.a. estimated from structural tailwinds in data centre demand driven by AI and cloud adoption (corroborated by BT article 16 Aug 2026 noting data centre S-REITs powering ahead on AI/cloud growth). Assumes continued occupancy stability at ~97% and modest AUM expansion via Keppel Group pipeline. Sensitivity tested in scenario analysis.
- `multiple_change` = 0.0 (Cat C) — Assumed flat multiple change over 12-month horizon given mixed macro signals: positive data centre demand versus elevated global interest rates and IASP.L benchmark delivering negative 5-year trailing return (-5.0% p.a.). Mean reversion modest and uncertain, treated as zero. Sensitivity tested in scenario analysis.
- `trading_halt_event` = noted (Cat A) — A trading halt was placed on AJBU.SI and lifted on 2026-09-02 (SGX TRAD filing, SG260902OTHRIZ2J). Coincides with a step-down in unit price from ~SGD 2.20 to ~SGD 2.16 and subsequent further drift to SGD 2.13 by 2026-09-21. The underlying catalyst was not fully disclosed in available filing bodies; noted as a qualitative risk factor.
- `substantial_unitholder_activity` = noted (Cat A) — Multiple Form 3 (substantial unitholder change) filings by Keppel-related entities between 10 Sep and 21 Sep 2026 (SGX ANNC filings dated 2026-09-10, 2026-09-14, 2026-09-15, 2026-09-21). Indicative of internal restructuring or rebalancing within Keppel Group; not necessarily a negative signal but warrants monitoring of any reduction in effective sponsor stake.
- `leverage_ratio` = 0.37 (Cat B) — Estimated aggregate leverage of approximately 37% based on Keppel DC REIT's historical gearing range of 36-38% reported in prior financial results. Full as-of filing unavailable for body extraction. Assumed within MAS regulatory limit of 50% (with credit rating) for Singapore REITs.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between SGD and GBP. The low beta of 0.22 and low correlation (0.18) reflect significant currency basis noise in addition to the data centre sector's distinct return drivers versus the broader APAC REIT universe. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- Undisclosed catalyst behind the September 2 2026 trading halt: the filing body did not reveal the specific trigger, creating information asymmetry that warrants close monitoring of subsequent SGX announcements.
- Keppel Group restructuring risk: multiple substantial unitholder Form 3 filings (Sep 10-21 2026) suggest internal Keppel entity rebalancing; any formal reduction in sponsor stake or dilution of pipeline commitment would be a material negative.
- Higher-for-longer global interest rates compressing the yield spread: with Rf at 3.99%, the distribution yield premium is approximately 150bps, thinner than historical norms for REIT investing and vulnerable to further rate moves.
- Data centre concentration risk: a pure-play data centre REIT is exposed to specific risks including technology obsolescence, hyperscaler customer concentration, energy cost inflation, and potential oversupply in select markets.
- IASP.L benchmark delivered a negative 5-year trailing annualised return of -5.0%, reflecting a challenging macro backdrop for APAC REITs; a reversal of data centre premium valuations could compress multiples significantly.

## Invalidation Condition
Exit position if: (1) any SGX filing confirms the September 2026 trading halt was triggered by a material adverse event such as a major tenant default, unscheduled asset impairment, or regulatory sanction; (2) reported gearing rises above 45% of total assets for two consecutive reporting periods; (3) DPU coverage falls below 1.0x AFFO for two consecutive halves; or (4) Keppel Group formally announces a reduction in its aggregate stake in AJBU.SI below 20% or a material withdrawal of pipeline asset commitments.
