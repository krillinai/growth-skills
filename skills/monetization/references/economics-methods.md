# Monetization And Economics Methods

## Paid Conversion And Realized Price

Use a verified qualified-exposure denominator:

```text
paid_conversion
= eligible entities completing the qualifying paid event within W
/ eligible entities receiving the declared qualified offer exposure and mature through W
```

Report numerator, denominator, exposure rule, conversion event, window, cutoff, segment, and commercial terms. Keep checkout start, authorization, payment capture, contract signature, and retained paid value separate.

Measure realized price from the declared revenue basis after applicable discounts, credits, free periods, refunds, and non-standard terms. Do not treat list price or bookings as realized recurring revenue.

## Revenue And Margin

Declare whether revenue is booked, billed, collected, recognized, recurring, or transaction revenue. Keep taxes and pass-through amounts explicit.

```text
gross_margin
= (revenue - declared direct cost of service)
/ revenue

serving_contribution
= revenue
- direct service and infrastructure
- support and success
- payment and transaction cost
- incentives, refunds, and risk loss

fully_loaded_contribution
= serving_contribution
- declared variable sales and acquisition cost
```

State every included and excluded cost. Keep acquisition cost outside serving contribution when using it to calculate CAC payback; otherwise acquisition cost is subtracted twice. Use fully loaded contribution for a view that intentionally includes variable sales and acquisition cost. Do not compare margin or contribution figures with different cost boundaries.

For a marketplace or transaction model:

```text
take_rate
= declared platform transaction revenue
/ compatible gross merchandise or transaction value
```

Declare refunds, taxes, incentives, pass-through payments, chargebacks, and transaction eligibility. A higher take rate is not automatically healthier if it reduces liquidity, trust, or off-platform retention.

## CAC And Payback

```text
CAC
= attributable acquisition and sales cost
/ new paying customers from the compatible conversion cohort

payback_periods
= CAC
/ periodic new-customer serving contribution before acquisition cost
```

Match cost to conversion lag, segment, channel, and sales motion. Distinguish customer CAC from cost per lead, signup, trial, activated user, or opportunity. Use serving contribution rather than revenue for payback, include required onboarding or variable service cost, and do not subtract the same acquisition cost inside the periodic contribution denominator.

## LTV

Treat LTV as a model, not an observed fact:

```text
LTV
= expected retained serving contribution before acquisition cost over the declared horizon
- future service, support, incentive, and risk cost not already included
```

Document cohort basis, retention curve, expansion, contraction, serving-contribution boundary, horizon, discounting, censoring, uncertainty, concentration, and back-test status. Keep CAC separate when evaluating LTV:CAC; if acquisition cost is included in a fully loaded lifetime value, do not compare or subtract the same CAC again. Do not extrapolate an immature cohort as if it were mature. Do not apply a universal LTV:CAC threshold.

## Retained Revenue

```text
GRR
= (starting recurring revenue - churn - contraction)
/ starting recurring revenue

NRR
= (starting recurring revenue - churn - contraction + expansion)
/ starting recurring revenue
```

Use the same starting recurring-revenue base and period. Exclude new-customer revenue. Separate logo, user, account, product, and revenue retention; price, seat, usage, product, and geographic expansion; payment recovery; and one-time revenue. Route deeper cohort, churn, resurrection, or recurring-value work to `retention`.

## Cohort, Currency, And Comparison Rules

Preserve conversion, renewal, retention, and payback maturity. Mark immature or right-censored outcomes `unavailable` or explicitly partial. Compare cohorts at the same age under compatible offer, package, metric, price, currency, discount, contract, product, market, accounting, and cost definitions.

For multiple currencies, preserve source amounts and dates, name the FX source and conversion rule, and separate FX movement from commercial performance. Do not infer tax treatment or net revenue from gross customer payments.

Use external benchmarks only when the user supplies an attributable, definition-compatible source. Prefer internal historical, cohort, segment, offer, or controlled comparisons.
