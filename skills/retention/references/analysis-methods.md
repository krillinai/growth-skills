# Retention Analysis Methods

## Retention Definitions

Choose one primary definition for the decision:

| Definition | Calculation boundary |
| --- | --- |
| Bounded or exact | Value event occurs in the named age period or interval |
| Rolling | Value event occurs at or after the named age, through a declared cutoff |
| Bracket | Value event occurs inside a declared range of ages or intervals |
| Opportunity | Value event occurs when the entity had a verified opportunity |
| Survival | Time until a declared lapse or churn event, preserving censoring |

Never combine bounded and rolling series under one label. Do not treat an entity without an opportunity as a failed opportunity-retention case.

## Cohort Maturity

For each age, use only entities that could have reached that age by the observation cutoff. Preserve incomplete right-censored periods as `unavailable` or explicitly partial. Compare cohorts at the same age, not merely on the same calendar date.

```text
retention_at_age_t
= entities completing the value event at age t
/ eligible original-cohort entities mature through age t
```

Report numerator and denominator with every rate.

## Growth Accounting

Use mutually exclusive states for the current period:

- `new`: first value-bearing activity occurs now;
- `retained`: value-bearing activity occurs in both the prior and current valid periods;
- `resurrected`: value-bearing activity occurs now after at least one inactive valid period;
- `churned` or `lapsed`: previously active but inactive now under the declared rule.

Reconcile both views:

```text
ending_active = retained + new + resurrected
ending_active = starting_active - churned + new + resurrected
```

Do not subtract churn twice. Keep resurrection separate from new and continuous retention.

## User, Account, Product, And Revenue

Do not collapse levels. Report user retention, account or logo retention, product retention, and recurring-revenue retention independently.

```text
GRR = (starting recurring revenue - churn - contraction) / starting recurring revenue
NRR = (starting recurring revenue - churn - contraction + expansion) / starting recurring revenue
```

Require the same starting revenue base and period. Exclude new-customer revenue from NRR unless the supplied definition explicitly says otherwise and is labeled nonstandard.

## Comparison Rules

Before comparing segments or periods, align entity, cohort start, value event, interval, maturity, market, product version, acquisition mix, experiment exposure, and observation cutoff. Report seasonality and mix changes as alternatives rather than automatic causes.

Use external benchmarks only when the user supplies an attributable, definition-compatible source. Prefer internal historical, cohort, segment, or controlled comparisons.
