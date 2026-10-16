# Specialist Memo — INA.AX

**Memo ID**: `INA.AX_2026-10-16_equity_reit_v1@1.0_6d3be90b4544`
**Ticker**: INA.AX (Ingenia Communities Group)
**Market**: Australia
**Sector**: Residential / Land-Lease Communities & Holiday Parks
**As of**: 2026-10-16
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
INA is an internally managed Australian land-lease communities and holiday-park operator whose price has just reset from about 4.58 to 3.96 after a series of Warburg Pincus indicative offers (up to A$5.25 cash) apparently lapsed. At 3.96 the stock carries little takeover premium, offering a roughly 3.7% yield plus about 5% assumed growth, for a 12-month OU Monte Carlo return of about 8.6%. High volatility (33.5%, inflated by bid-related jumps) limits PGain to about 65%, which supports only moderate conviction. A prior private-equity valuation range well above the current price gives some residual re-bid optionality, but I have not underwritten it in the base case. Beta of 0.69 versus IASP.L (currency-basis caveat applies) and a CAPM alpha flattered by a negative benchmark return make alpha a weak supporting input.

## Quantitative Chain

- E(R): 0.0870
- Std dev: 0.2276
- P-gain: 0.6471
- CAPM alpha: 0.1088
- Beta: 0.6869
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.2000
  - The takeover floor is gone for good and the stock de-rates toward pre-bid levels of about 4.1 or lower. Higher-for-longer AU and US rates (stagflation-style pathway) widen cap rates and discount rates. Development settlements slow and FY27 earnings growth is about 0%. Distribution coverage tightens and gearing drifts toward or above the 40% AU convention. Unitholders also bear the opportunity cost of the lapsed offer.
- **base**: E(R)=0.0860
  - Central case as built in the chain: a 3.7% distribution yield, about 5% growth in earnings and distributions on development settlements and rental growth, and no net multiple change. The takeover premium is not re-priced and gearing and coverage stay within targets.
- **bull**: E(R)=0.3000
  - Warburg Pincus or another bidder returns with a binding proposal near the previously reported A$5.05-5.25 range, or the board delivers a re-rating through capital management. Together with a 3.7% yield and 5% growth, this gives roughly a 25% price gain on 3.96 plus distributions.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=info
- `management_alignment` — status=info

## Key Assumptions
- `last_price` = 3.96 (Cat A) — INA.AX close 2026-10-16 (get_price, AUD). It fell from 4.58 on 2026-10-14 to 3.96, about -13.5% in two sessions, after the 2026-10-14 'Pause in Trading' and 'Update on Further Revised Non-Binding Indicative Offer' ASX announcements. The pre-announcement run-up from about 4.17 in mid-September reflected a takeover premium.
- `distribution_yield` = 0.037 (Cat B) — Approximate forward cash distribution of about 14-15 cents per security divided by the 3.96 price. The distribution figure comes from my recollection of recent FY25/FY26 guidance and could NOT be verified from tool outputs. The stored filing bodies returned for INA.AX were mismatched to unrelated issuers and were discarded. Treat as a derived estimate with a data-gap caveat.
- `distribution_growth` = 0.05 (Cat C) — Assumed 5% per-security earnings and distribution growth over 12 months. Headlines (Kalkine, 2026-10-16) describe an above-guidance FY26 and modest FY27 guidance growth. The basis is the development settlement pipeline plus rental growth in the land-lease communities, with no unit-count dilution. Sensitivity: each 1pt of growth moves E(R) by 1pt, and the bear case assumes growth near 0%.
- `multiple_change` = 0.0 (Cat C) — Assumed zero net re-rating over 12 months. The takeover premium appears to have been removed from the price, so I do not underwrite an offer-driven rerating. A re-bid is an upside tail captured only in the bull case. A further de-rating on higher AU rates is captured in the bear case.
- `expected_return_build` = 0.087 (Cat C) — E(R) = yield 3.7% (B) + growth 5.0% (C) + multiple change 0.0% (C) = 8.7%. This is the base_return input to the OU Monte Carlo.
- `risk_free_rate_dtb3` = 0.041 (Cat A) — FRED DTB3 3-month T-bill 4.10% observed 2026-10-15 (get_tbill_rate). It is a USD rate used as the Rf per methodology, so there is a further currency mismatch versus an AUD asset.
- `expected_market_return` = -0.0504 (Cat B) — Trailing 5.17-year annualised log return of IASP.L (calculate_benchmark_return, 1260 trading-day lookback). GBP-denominated, so it absorbs FX co-movement. The negative Rm mechanically inflates CAPM alpha, so alpha is treated as a weak supporting input only.
- `historical_volatility_context` = 0.3349 (Cat A) — 252-day annualised volatility from stored prices. It is inflated by the takeover-bid jump and gap-down in September-October 2026, so it overstates fundamental volatility. It is used unadjusted per methodology, which makes PGain conservative.
- `takeover_event_status` = unresolved_inferred_lapse (Cat C) — News headlines show repeated Warburg Pincus non-binding proposals: a rejected A$1.9B bid (about 2026-09-06), a rejected A$5.05 bid (2026-09-21), and a further revised A$5.25 cash proposal (2026-09-28). ASX titles on 2026-10-14 are 'Pause in Trading' and 'Update on Further Revised Non-Binding Indicative Offer'. The 13.5% price fall over 15-16 October suggests the proposal was withdrawn or lapsed. This is an inference only, because the announcement body text was not retrievable and no news article confirming the outcome was found.
- `filing_body_data_gap` = disclosed (Cat B) — The 8 stored INA.AX filing rows had bodies that were off-topic and belonged to unrelated issuers (e.g. Imugene, Russell Investments ETF, Lycopodium). They were ignored as parsing or pipeline mismatches. Gearing, coverage, WALE and concentration could not be verified from issuer filings, and the gates below are marked 'info' for that reason.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- Event and takeover risk: the price just fell about 13.5% in two sessions on an apparently lapsed bid. The outcome could not be confirmed from filings or news, so further downside toward pre-bid levels or a swing on a re-bid is possible.
- Data gaps: the stored filing bodies were mismatched to unrelated issuers, so gearing, distribution coverage, WALE, concentration and the yield input could not be verified. The qualitative gates are 'info' rather than 'pass' and the yield is a Category B estimate that may be wrong.
- Rate and cap-rate risk: higher-for-longer AU and US rates would compress valuations and the spread of the yield over a 4.10% T-bill.
- Development and settlement risk: earnings depend partly on development margins and home-sale settlements, which are cyclical and sensitive to housing-market sentiment.
- Statistical caveats: volatility is inflated by takeover jumps, and beta and expected market return rest on a GBP benchmark with low correlation (0.24). The negative 5-year Rm flatters CAPM alpha. The USD T-bill used as Rf is mismatched to an AUD asset, and the OU Monte Carlo is a model output, not a forecast.

## Invalidation Condition
Exit or avoid if verified filings show gearing above 40% or distribution coverage below 1.0x AFFO for two consecutive reporting periods. Also exit if FY27 guidance is cut so that earnings growth turns negative, or if the price breaks decisively below about 3.60 without a corporate explanation, which would signal that the post-bid de-rating is continuing. Conversely, a confirmed permanent withdrawal of all bidder interest combined with a deteriorating development pipeline would invalidate the thesis.
