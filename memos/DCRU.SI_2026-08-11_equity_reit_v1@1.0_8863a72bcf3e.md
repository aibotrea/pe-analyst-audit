# Specialist Memo — DCRU.SI

**Memo ID**: `DCRU.SI_2026-08-11_equity_reit_v1@1.0_8863a72bcf3e`
**Ticker**: DCRU.SI (Digital Core REIT)
**Market**: Singapore
**Sector**: Data Centre
**As of**: 2026-08-11
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
Digital Core REIT offers USD-denominated exposure to hyperscaler-tenanted data centre assets sponsored by Digital Realty Trust, a globally recognised data centre operator. The annualised total DPU yield of 7.6% at USD 0.475 per unit appears attractive in an AI-driven infrastructure cycle, but nearly half (48.9%) of the 1H26 distribution was a capital return rather than income, casting doubt on sustainable distributable income. A same-day trading halt (2026-08-11, pending unknown announcement) introduces binary event risk that cannot be resolved at the as_of date, and a concurrent Cohen & Steers substantial-unitholder interest change may reflect institutional repositioning. PGain of 70.6% from the OU Monte Carlo and positive CAPM alpha of 7.6% are supportive in isolation, but the combination of distribution coverage concerns and unresolved corporate action risk constrains conviction to Low.

## Quantitative Chain

- E(R): 0.0850
- Std dev: 0.1560
- P-gain: 0.7055
- CAPM alpha: 0.0763
- Beta: 0.3650
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1200
  - Trading halt reveals a highly dilutive equity raise (>15% of units) or adverse tenant event causing occupancy to drop below 90%; capital distribution component eliminated and income DPU cut by 30%; cap rate expands 50bps on rate shock; multiple contracts 12% from current level; DPU growth assumption revised to -5%.
- **base**: E(R)=0.0850
  - Central case as built in the quantitative chain: total annualised DPU yield of 7.6% (including 3.87% income yield), 1.0% DPU growth, flat multiple; trading halt resolves without material dilution; occupancy stable; capital distribution maintained at current proportion.
- **bull**: E(R)=0.2200
  - Trading halt precedes accretive acquisition at 6.5%+ yield funded at minimal dilution; DPU income component expands as AFFO improves, reducing capital distribution reliance; AI-driven data centre demand tightens cap rates by 25bps; multiple re-rates 10% upward; DPU growth of 4% achieved.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=fail [override_applied=-1]
- `asset_quality_concentration` — status=info
- `management_alignment` — status=info [override_applied=-1]

## Key Assumptions
- `distribution_yield` = 0.0758 (Cat A) — Annualised total DPU of USD 3.60 cents (1H26 actual of 1.80 US cents x 2) divided by closing price USD 0.475 on 2026-08-11. Source: DCRU.SI 2026-07-29 Capital Distribution announcement SGX ref SG260729CAPDMJ8R.
- `income_dpu_yield` = 0.0387 (Cat A) — Tax-exempt income component only: annualised 1.84 US cents (0.92c x 2) divided by USD 0.475. Capital distribution of 0.88c x 2 = 1.76 US cents annualised excluded as it represents a return of capital. Source: DCRU.SI 2026-07-29 Capital Distribution announcement SG260729CAPDMJ8R.
- `capital_distribution_proportion` = 0.489 (Cat A) — Capital distribution of 0.88 US cents out of total 1.80 US cents per unit for 1H26 equals 48.9% of total DPU paid as capital return rather than income. Material distribution sustainability concern. Source: DCRU.SI 2026-07-29 CACT filing SG260729CAPDMJ8R.
- `dpu_growth_assumption` = 0.01 (Cat C) — Forward DPU growth of 1.0% p.a. based on flat H1 2026 DPU vs prior period (Business Times 29 Jul 2026: H1 DPU flat at US$0.018) and structural AI and cloud demand tailwind for data centre real estate. Conservative given high capital distribution proportion and pending trading halt uncertainty. Sensitivity tested in scenarios.
- `multiple_change` = 0.0 (Cat C) — Zero multiple change assumed in base case. Justification: (1) unexplained trading halt filed 2026-08-11 SG260811OTHRWZA3 pending unknown announcement; (2) Cohen and Steers substantial unitholder interest change filed 2026-08-07 may signal institutional repositioning; (3) price range USD 0.47-0.52 over prior 90 days with no confirmed directional catalyst. Bull and bear scenarios test +/-10% multiple movement.
- `trading_halt_flag` = flagged (Cat A) — Trading halt requested with immediate effect 2026-08-11 18:00 SGT citing pending release of announcement. Nature unknown as at as_of date. Material event risk embedded in conviction gate override. Source: DCRU.SI TRAD filing 2026-08-11 SGX ref SG260811OTHRWZA3.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between USD and GBP as DCRU.SI is USD-denominated and trades on SGX. Currency basis noise is material over the 252-day window. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- Unknown pending announcement driving 2026-08-11 trading halt: could be a dilutive equity raise, acquisition at unfavourable terms, or adverse regulatory or tenant event — binary risk cannot be priced at as_of date.
- High capital distribution proportion (48.9% of 1H26 DPU is capital return) raises distributable income sustainability concerns if AFFO does not recover to support full income-only DPU.
- Cohen & Steers substantial unitholder interest change filed 2026-08-07 may signal institutional outflow pressure; combined with trading halt, liquidity and price risk is elevated.
- Annualised historical volatility of 23.0% is elevated for a data centre REIT, reflecting episodic re-rating risk and USD/SGD cross-listing noise on a USD-denominated instrument.
- IASP.L benchmark return of -4.1% annualised over 5 years reflects a challenged APAC REIT macro backdrop; rising rates or cap rate expansion could compress DCRU valuations despite strong structural demand for data centre capacity.

## Invalidation Condition
Exit the position if: (1) the pending trading halt announcement reveals a dilutive equity issuance greater than 10% of units in issue, an acquisition at a cap rate below 5.5%, or a material tenant default; (2) DPU income coverage (excluding capital distribution) falls below 0.90x AFFO for two consecutive half-year periods; (3) sponsor Digital Realty Trust reduces its ownership stake in DCRU below 25% or formally withdraws its pipeline commitment; or (4) aggregate leverage exceeds the Singapore MAS 50% limit.
