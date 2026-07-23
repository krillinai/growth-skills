# Activation Analysis Methods

## Primary Calculations

Use the full eligible cohort for the declared window:

```text
activation_rate
= eligible entities completing the qualifying first-value event within W
/ all eligible entities whose activation window is mature through W
```

Report numerator, denominator, absolute eligible volume, window, cutoff, and exclusions with every rate. Do not silently remove users who failed a prerequisite or encountered product friction.

Calculate time to first value from the declared start event to the first qualifying value event. Report the median and decision-relevant percentiles with the observed count, cutoff, and censoring rule. Do not report a complete-cohort time-to-value distribution while unresolved eligible entities are right-censored.

## Funnel Integrity

For each step, define eligibility independently:

```text
step_conversion_n
= entities completing step n
/ entities eligible for step n

end_to_end_activation
= entities completing the qualifying first-value event
/ entities eligible at activation start
```

Report step and end-to-end conversion together. A higher intermediate conversion can move friction downstream. Do not multiply rounded step rates when direct entity counts are available.

Step abandonment locates where progress stops; it does not establish why. Define the inactivity timeout and valid return window before classifying abandonment.

## First-Value Quality

Use a tiered definition when one binary event hides customer outcome:

```text
technical success -> usable result -> meaningful value -> retained value
```

Define only quality dimensions relevant to the customer job: success, relevance, completeness, trust, effort, repeatability, or collaboration. More clicks, prompts, output, imports, invitations, or time spent are not automatically more value.

## Retained Activation

Use a mature return opportunity and a denominator of activated entities eligible to return:

```text
retained_activation_at_R
= activated entities repeating the qualifying value event at R
/ activated entities mature and eligible to return at R
```

Keep activation rate and retained activation separate. Route deeper cohort, natural-frequency, churn, resurrection, account, or revenue retention work to `retention`.

An activation-to-retention difference may show predictive validity:

```text
activation_retention_difference
= retention of activated entities
- retention of definition-compatible non-activated entities
```

Require aligned cohort, maturity, entity, intent, source, and horizon. Treat the difference as observational unless assignment or another credible causal design supports an effect claim.

## Cohort Maturity And Comparison

Use only entities whose full activation window has elapsed by the observation cutoff. Preserve immature or right-censored windows as `unavailable` or explicitly partial. Compare cohorts at the same age and under compatible event instrumentation.

Before comparing segments or paths, align entity, product level, intent, entry state, eligibility, start event, value event, quality threshold, window, maturity, market, product version, acquisition mix, assistance, experiment exposure, and cutoff. Report composition changes as alternatives rather than automatic causes.

## Product Levels And Topologies

Keep user, workspace, account, payer, and product activation separate. For marketplaces, keep participant sides and successful interaction conditions separate. For AI products, require a successful and usable task or workflow rather than prompt, token, or output volume alone. For low-frequency products, use credible task completion, readiness, saved state, or opportunity-based downstream validation rather than forcing a habit metric.

Use external benchmarks only when the user supplies an attributable, definition-compatible source. Prefer internal historical, cohort, segment, or controlled comparisons.
