# Specialist Memo — CHC.AX

**Memo ID**: `CHC.AX_2026-08-08_equity_reit_v1@1.0_7b54d9637cda`
**Ticker**: CHC.AX (Charter Hall Group)
**Market**: Australia
**Sector**: Diversified
**As of**: 2026-08-08
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
Charter Hall Group is Australia's largest listed diversified property funds manager, with ~AUD 90bn+ in assets under management across office, industrial, retail and social infrastructure. The group upgraded its FY26 operating EPS guidance in May 2026 and secured a new AUD 1.2bn institutional mandate in April 2026, demonstrating AUM growth momentum as the RBA easing cycle supports transaction volumes. A distribution yield of approximately 3.2% combined with ~4% earnings growth yields an estimated total return of ~7.7%, supported by a strong CAPM alpha of 10.7% versus the negative-returning IASP.L benchmark. However, the OU Monte Carlo simulation delivers a PGain of only 0.66 given the elevated 27.2% annualised volatility, and an executive leadership transition announced in August 2026 introduces organisational uncertainty that warrants a -1 gate override, reducing conviction to Low (Score 2).

## Quantitative Chain

- E(R): 0.0770
- Std dev: 0.1848
- P-gain: 0.6598
- CAPM alpha: 0.1072
- Beta: 0.8895
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1200
  - Leadership transition triggers key-person departures and AUM redemptions of 10-15%; OEPS declines 5-8% in FY27; RBA pauses easing and global risk-off compresses property manager multiples; cap rate expansion of 25-50bps across CHC-managed funds impairs co-investment book values; distribution cut to preserve balance sheet flexibility. Bear case also captures tail risk of a global credit event that freezes unlisted property redemptions.
- **base**: E(R)=0.0770
  - Central case as built in chain: distribution yield 3.2%, OEPS growth 4.0%, multiple change +0.5%; AUM grows modestly via new mandates; leadership transition is orderly with no material client impact; RBA easing supports asset valuations; occupancy across managed funds stable.
- **bull**: E(R)=0.2200
  - New CEO accelerates AUM growth strategy; additional institutional mandates secured beyond the AUD 1.2bn April 2026 win; OEPS upgraded again in FY27 with performance fees recovering; RBA cuts accelerate, compressing cap rates and boosting valuations across CHC-managed funds; multiple re-rating toward prior peak of 20x+ OEPS.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=info [override_applied=-1]
- `distribution_coverage` — status=pass
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=info

## Key Assumptions
- `distribution_yield` = 0.032 (Cat B) — Estimated trailing distribution yield of ~3.2% derived from publicly known half-yearly distribution cadence (~AUD 0.38-0.40 per half, implying ~AUD 0.76-0.80 pa) at current price of AUD 23.90. Distribution announcement for H1 FY26 filed 2026-06-22 (CHC.AX DISTRIBUTION ANNOUNCEMENT) but body capture failed (body_unavailable=True); yield derived from price and historically observed payout pattern. Category B due to derivation.
- `dpu_growth_3yr` = 0.04 (Cat C) — Forward operating EPS and distribution growth of 4.0% pa assumed based on: (1) ASX filing 2026-05-24 'Further upgrade to FY26 OEPS guidance' (price_sensitive, body_unavailable) indicating earnings momentum above prior guidance; (2) ASX filing 2026-04-08 'New $1.2 billion Institutional Mandate' — AUM expansion drives management fee income; (3) Rate cycle easing in Australia supporting asset valuations and transaction volumes. Sensitivity: bear case applies -2%, bull case applies +6%.
- `multiple_change` = 0.005 (Cat C) — Assumed +0.5% multiple expansion contribution from improving capital markets conditions and RBA easing cycle supporting listed property manager valuations. CHC trades at a premium to NTA given its funds management franchise value. Neutral to slightly positive given strong AUM pipeline but leadership transition risk (Aug 2026) introduces uncertainty.
- `rba_cash_rate` = unavailable (Cat C) — get_stored_apac_rates and get_apac_rates returned no AU rate data as of 2026-08-08. RBA cash rate assumed in the 3.75-4.25% range based on publicly known easing trajectory. This assumption informs spread analysis only; quantitative chain uses US T-bill Rf as proxy per framework convention.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same currency and IASP noise. The high beta of 0.889 may partly reflect AUD/GBP correlation rather than pure APAC property beta.
- `filing_body_gap` = disclosed (Cat C) — Seven of eight retrieved CHC.AX ASX filings have body_unavailable=True (Phase 01 v3.3 §4 — ASX body capture parked). Key affected filings: distribution announcement 2026-06-22, OEPS upgrade 2026-05-24, $1.2bn mandate 2026-04-08. Distribution yield, coverage and leverage assumptions rely on publicly known patterns and headline text only, not verified filing bodies. This introduces Category C uncertainty into the distribution yield and coverage gate.
- `leadership_transition` = disclosed (Cat A) — ASX filing 2026-08-02 'Executive Leadership Transition' (COMPANY ADMINISTRATION, price_sensitive=False) confirms management change at Charter Hall Group. The filing body returned content from an unrelated issuer (Dateline Resources Limited, DTR) — a pipeline mis-match — and is treated as body_unavailable for CHC purposes. Leadership change is recorded as observed fact from headline. Contributes to -1 gate override on sponsor_quality/management_alignment gate.

## Key Risks
- Executive leadership transition (announced 2026-08-02) could disrupt AUM growth strategy, client relationships, and capital allocation discipline during a critical phase of the RBA easing cycle.
- High annualised volatility (27.2%) reflects CHC's dual exposure to both property asset values and capital-markets-sensitive funds management earnings, amplifying drawdown risk in risk-off environments.
- AUM redemption risk: if institutional allocators reduce unlisted property allocations (e.g. due to global rate volatility or liquidity concerns), management fee income and performance fees could fall sharply.
- ASX filing body unavailability for seven of eight recent CHC.AX filings means distribution coverage, gearing ratios, and OEPS guidance quantum could not be independently verified from primary sources — assumptions carry elevated Category C uncertainty.
- IASP.L benchmark returned -3.9% annualised over 5 years (currency-basis caveat applies); persistently negative benchmark returns make CAPM alpha calculation less reliable as a conviction signal.

## Invalidation Condition
Exit position if CHC.AX reports two consecutive half-years of flat or declining operating EPS (OEPS) without a credible recovery plan, or if total AUM falls below AUD 75bn signalling net redemptions, or if the incoming executive leadership announces a material strategic pivot such as balance sheet expansion beyond 35% gearing or disposal of co-investment stakes at a discount to book value exceeding 10%.
