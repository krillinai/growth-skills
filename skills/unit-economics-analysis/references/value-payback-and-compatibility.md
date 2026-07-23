# Value, Payback, And Compatibility

Connect acquisition cost to compatible retained value. Do not replace a value model with a ratio shortcut.

## Value Bridge

Reconcile price and quantity through discounts, credits, refunds, payment fees, tax, bad debt, hosting, support, fulfillment, servicing, incentives, expansion, contraction, churn, and other variable costs to the chosen value basis.

| Basis | Meaning |
| --- | --- |
| Revenue | Recognized customer revenue under a declared accounting policy |
| Gross profit | Revenue less declared cost of revenue |
| Contribution | Revenue less declared variable and decision-relevant costs |
| Cash | Dated inflows less dated acquisition and servicing outflows |

Keep GMV, bookings, billings, invoices, cash, revenue, gross profit, and contribution separate.

## LTV Handoff

Route survival, repeat purchase, retention curves, tail methods, expansion and contraction forecasts, censoring, calibration, and full LTV estimation to `ltv-analysis`. Accept the output only with entity, cohort, original denominator, value basis, market, currency, horizon, maturity, model version, assumptions, uncertainty, calibration, and owner.

Revenue LTV cannot support a contribution LTV:CAC claim. Forecast LTV is not observed value. ARPU divided by churn is not universal and does not justify an infinite horizon or permanent plateau.

## Payback

Build period-by-period cumulative curves from one cohort:

```text
cumulative contribution(t) = sum compatible contribution through mature period t
cumulative net cash(t) = sum compatible customer cash inflows - acquisition and servicing cash outflows through t
```

Accounting payback is the first mature period where cumulative contribution covers allocated acquisition cost. Cash payback is the first mature period where cumulative net cash reaches the declared break-even boundary. Return `not reached`, `not yet mature`, or a range when appropriate.

Signed value, bookings, invoices, recognized revenue, contribution, and cash occur at different times. Include commission, onboarding, refund, chargeback, bad-debt, renewal, and recognition timing.

## Compatibility Matrix

Align entity, cohort, product, offer, price, segment, market, channel, currency, acquisition period, value horizon, maturity, cost scope, attribution or incrementality, value basis, discounting, observed or forecast state, uncertainty, source, and version before calculating LTV:CAC or comparing payback.

Show each mismatch. Do not average ratios; aggregate compatible absolute costs and values first, then calculate a clearly labeled portfolio view.

## Sensitivity And Break-Even

Test acquisition cost, conversion, retention, expansion, contraction, price, margin, servicing cost, refunds, horizon, discounting, cash timing, saturation, and capacity within evidence-supported ranges. Show which inputs change the decision, where ranks reverse, and when uncertainty makes choices indistinguishable.
