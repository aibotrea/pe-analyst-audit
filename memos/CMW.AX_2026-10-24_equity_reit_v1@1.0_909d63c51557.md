# Specialist Memo — CMW.AX

**Memo ID**: `CMW.AX_2026-10-24_equity_reit_v1@1.0_909d63c51557`
**Ticker**: CMW.AX (Cromwell Property Group)
**Market**: Australia
**Sector**: Diversified/Office (Funds Management)
**As of**: 2026-10-24
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
CMW offers a high forward distribution yield of about 9.4% on a 3.1c planned FY27 distribution at an AUD 0.33 price, and FY26 FFO grew about 5% with AUM of AUD 4.7B. The quantitative chain gives E(R) of about 7%, OU-simulated return of 6.9% and PGain of about 65%. That is supported by CAPM alpha of 8.8% (beta 0.67, currency-basis caveat applies), but the alpha is inflated by the negative IASP.L 5-year return. Volatility is high at 27% and the price has fallen about 24% since August. I could not verify gearing, coverage or sponsor details from issuer filings, so I applied a one-step downward override for distribution coverage. Conviction is Low with a small position cap.

## Quantitative Chain

- E(R): 0.0700
- Std dev: 0.1845
- P-gain: 0.6461
- CAPM alpha: 0.0877
- Beta: 0.6697
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.2200
  - Stagflation or higher-for-longer rate pathway lifts AU cap rates by 50bps or more. Office valuations fall and gearing moves above the 40% convention. The 3.1c distribution is cut or coverage drops below 1.0x AFFO. The security de-rates a further 25-30% as the 11-week selloff continues, partly offset by the income received.
- **base**: E(R)=0.0700
  - Central case as built in the chain. The 3.1c distribution is paid with flat DPU, so yield is about 9.4%. The multiple drag is about -2.4% and cap rates are stable. There are no major equity raisings.
- **bull**: E(R)=0.2600
  - Asset sales are completed at or near book value and debt is reduced. The funds management platform grows, with AUM growing from AUD 4.7B. The distribution is maintained and the security re-rates 15% or more toward NAV as the yield stays near 9%.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=info
- `management_alignment` — status=info

## Key Assumptions
- `price` = 0.33 (Cat A) — Latest close on 2026-10-23 of AUD 0.33. The stored series shows a fall from about AUD 0.435 in early August 2026, roughly -24% in about 11 weeks.
- `distribution_yield` = 0.094 (Cat B) — Planned FY27 distribution of 3.1 cents per security, taken from a Kalkine headline dated 2026-10-15 (secondary source, not the issuer filing). Divided by the AUD 0.33 price this gives about 9.4%. It is a forward, not trailing, yield. The issuer's distribution announcement body could not be verified.
- `dpu_growth` = 0.0 (Cat C) — Assumes flat DPU at the planned 3.1c. No growth is assumed beyond the plan, because AUM growth to AUD 4.7B and FFO +5% in FY26 are not tied to distribution growth. Sensitivity is covered in the bear and bull scenarios.
- `multiple_change` = -0.024 (Cat C) — Assumed -2.4% price drag over 12 months, reflecting continued de-rating momentum and the OU model's mean-reversion framing. It nets the forward yield of 9.4% down to E(R) of 7.0%. Sensitivity: each 5% of re-rating or de-rating moves E(R) by 5 points.
- `expected_return_build` = 0.07 (Cat C) — E(R) = yield 9.4% + growth 0.0% + multiple change -2.4%, which is about 7.0%. It is a 12-month total return before transaction costs.
- `risk_free_rate` = 0.0404 (Cat A) — FRED DTB3 3-month US T-bill at 4.04% on 2026-10-22, from get_tbill_rate. This is a USD rate, used as the platform's standard Rf, and carries a mismatch against AUD cash rates.
- `expected_market_return` = -0.0463 (Cat B) — Trailing annualised log return of IASP.L over 1260 trading days, from calculate_benchmark_return. It is negative, so CAPM required return is below Rf. The window and GBP basis make this a noisy hurdle.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.
- `filing_data_gap` = disclosed (Cat B) — The stored ASX filing bodies tagged to CMW.AX (filing dates 2026-08-26 to 2026-10-14) contain text from unrelated issuers, for example an ETF distribution notice, Life360, Sky Metals and Chalice. They were discarded as mis-attributed. Gearing, AFFO coverage, occupancy, WALE and sponsor commitments could not be sourced from issuer filings. The qualitative gates rest on headlines only.

## Key Risks
- Distribution sustainability: the high yield could signal market doubt about AFFO coverage or a further cut, and coverage and payout could not be verified from filings.
- Balance-sheet and refinancing risk: gearing and covenant headroom are unverified, and Australian office valuation declines or higher-for-longer rates could force asset sales at a discount or an equity raise.
- Persistent negative price momentum (-24% in about 11 weeks) and 27% annualised volatility, with low correlation (0.29) to IASP.L, so beta and alpha are noisy because of the currency basis.
- Data-quality limitation: the stored filing bodies for CMW.AX are mis-attributed to other issuers, the distribution figure comes from a secondary news headline, and the Rf is a USD T-bill rate against an AUD security. The negative 5-year benchmark return distorts CAPM alpha.
- Macro and structural risk: stagflation or a rate shock would hit leveraged office and diversified property, and funds-management earnings depend on third-party capital flows.

## Invalidation Condition
Exit if Cromwell announces a distribution cut below the planned 3.1c per security, reports AFFO coverage below 1.0x for two consecutive half-years, or shows gearing above 40% with covenant pressure or a discounted equity raising. Also exit if the security closes below about AUD 0.27, roughly 18% under the current price, without a credible balance-sheet repair plan or evidence that asset sales are being done at book value.
