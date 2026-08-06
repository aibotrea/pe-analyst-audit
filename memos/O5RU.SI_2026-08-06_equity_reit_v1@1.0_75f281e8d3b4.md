# Specialist Memo — O5RU.SI

**Memo ID**: `O5RU.SI_2026-08-06_equity_reit_v1@1.0_75f281e8d3b4`
**Ticker**: O5RU.SI (AIMS APAC REIT)
**Market**: Singapore
**Sector**: Industrial/Logistics
**As of**: 2026-08-06
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
AIMS APAC REIT offers a 6.0% distribution yield backed by a diversified Singapore and Australian industrial portfolio, with a visible DPU growth pathway from the recently completed Perth Hazelmere acquisition and ongoing Singapore industrial rent reversions. The refinancing of expensive 5.375% perpetual securities with a lower-cost 4.25% structure reduces the interest burden and supports distributable income stability. Beta of 0.26 versus IASP.L (SGD/GBP currency basis caveat applies) indicates materially lower co-movement with the broader APAC REIT market, providing partial defensiveness. The OU Monte Carlo simulation at 12 months yields PGain of 79.5%, supporting a moderate conviction score of 3, tempered by one step for the imminent CEO transition and AIMS Group's mid-tier sponsor standing relative to Singapore REIT peers.

## Quantitative Chain

- E(R): 0.0850
- Std dev: 0.1025
- P-gain: 0.7952
- CAPM alpha: 0.0667
- Beta: 0.2559
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0400
  - Singapore industrial occupancy falls to 91% (from ~95% base) driven by global trade slowdown and tariff shock reducing logistics demand. DPU coverage drops below 1.0x AFFO as rising all-in debt costs (following MAS rate tightening) compress NPI margins. Perth acquisition proves dilutive at lower-than-modelled rents. Cap rates expand 30–50bps, causing NAV erosion. New CEO fails to execute strategy credibly, triggering re-rating discount. DPU growth reverses to -1% p.a.
- **base**: E(R)=0.0850
  - Central case as modelled: distribution yield 6.0%, DPU growth 2.5% from organic Singapore rent reversions plus Perth industrial contribution. Cap rates flat. Perp refinancing reduces interest cost. Gearing remains within 37–40% post-acquisition. New CEO appointment progresses without operational disruption. SGD/USD broadly stable.
- **bull**: E(R)=0.1800
  - Singapore industrial rents accelerate as data-centre and e-commerce tenants absorb supply, pushing occupancy above 97% and enabling 4%+ DPU growth. Cap rate compression of 20–30bps driven by yield-seeking institutional flows as global rates moderate. Perth acquisition adds above-consensus accretion at 6%+ NPI yield. Sustainability-linked loan refinancing reduces all-in cost by 30bps, further boosting distributable income. Multiple re-rating adds 5–8% price appreciation above income return.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=info [override_applied=-1]
- `distribution_coverage` — status=pass
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=info

## Key Assumptions
- `distribution_yield` = 0.06 (Cat A) — 1Q FY2027 DPU of 2.337 Singapore cents per unit (period 1 Apr – 30 Jun 2026) confirmed in O5RU.SI scrip distribution announcement 2026-07-30 (CACT filing). Annualised run-rate: 9.348 cents. At closing price SGD 1.557 on 2026-08-06, implied trailing distribution yield = 9.348/155.7 = 6.00%. Published issuer figure.
- `dpu_growth_3yr` = 0.025 (Cat C) — Forward DPU growth of 2.5% p.a. assumed: ~2.0% organic from Singapore industrial rent reversions (positive leasing momentum per Beansprout 2026-08-05 note on 1Q FY2027 broad-based DPU growth) plus ~0.5% incremental from completion of Perth industrial acquisition (398 Bushmead Road and 286 Stirling Crescent, Hazelmere, WA) announced O5RU.SI ANNC 2026-08-05. Partially offset by equity dilution from fund raising. Sensitivity: bear -1%, bull +1.5%. Category C model assumption.
- `multiple_change` = 0.0 (Cat C) — Assumed zero multiple expansion/contraction over 12-month horizon. Cap rates assumed broadly flat as MAS maintains policy stance and Singapore industrial demand is stable. Perp refinancing (S$250M 5.375% called 1 Sep 2026, replaced by S$100M 4.25% new perp per O5RU.SI ANNC 2026-06-26) is credit-positive but assumed already priced at current levels. Category C assumption; sensitivity tested in scenario analysis.
- `perp_refinancing` = disclosed (Cat A) — AIMS APAC REIT is redeeming S$250M 5.375% subordinated perpetual securities on 1 Sep 2026 (O5RU.SI CACT filing 2026-07-31, mandatory early redemption call option). Simultaneously issued S$100M 4.25% subordinated perpetual securities (tax ruling filed O5RU.SI ANNC 2026-06-26). Net reduction in hybrid capital cost. Positive for distributable income margin.
- `ceo_transition` = disclosed (Cat A) — CEO Russell Ng Keh Yang stepping down effective 30 Sep 2026 to pursue other interests (O5RU.SI ANNC 2026-07-24, cessation announcement). New CEO appointment announced simultaneously. Management transition introduces execution risk over near term. Applied as one-step downward gate override on conviction.
- `leverage_gearing` = within_limit (Cat B) — AIMS APAC REIT historically operates at ~34–37% aggregate leverage (derived from published annual report filings; FY2026 annual report filed O5RU.SI ANNC 2026-06-26). MAS regulatory limit for Singapore REITs is 50%. New unsecured sustainability-linked loan and syndicated facility secured May 2026 (O5RU.SI ANNC 2026-05-21) improves debt maturity profile. Perth acquisition funded partly by equity raise (O5RU.SI ANNC 2026-08-05 use of proceeds). Category B as derived from public filings; exact post-acquisition leverage not confirmed from truncated bodies.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between SGD and GBP currency basis. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- CEO transition (Russell Ng departing 30 Sep 2026): execution and strategy continuity risk during FY2027 acquisitions pipeline deployment; new leadership quality is unproven in the role.
- Interest rate sensitivity: gearing at ~34–37% with floating-rate exposure means that any MAS-led tightening or prolonged higher SGD SORA environment would compress NPI-to-DPU conversion and risk a distribution cut.
- Perth acquisition integration: cross-border industrial property in Western Australia introduces AUD/SGD FX risk and unfamiliar regulatory/leasing environment; any underperformance versus the acquisition underwrite would be dilutive.
- Perpetual securities capital structure: S$250M perp redemption reduces hybrid capital by a net S$150M; if replacement financing proves more expensive than modelled or if credit spreads widen, refinancing costs could rise.
- IASP.L benchmark currency basis: beta of 0.26 and alpha of 6.67% are computed against a GBP-denominated benchmark; FX co-movement obscures true property-market beta and may overstate or understate systematic risk.

## Invalidation Condition
Exit position if Singapore industrial portfolio occupancy falls below 92% for two consecutive quarters, or if the announced 1Q FY2027 DPU run-rate of 9.348 cents annualised is revised downward by more than 8% in any subsequent quarterly business update, or if aggregate leverage breaches 42% of deposited property value following the Perth acquisition consolidation, or if the incoming CEO announces a material strategy pivot away from industrial/logistics toward office or retail assets.
