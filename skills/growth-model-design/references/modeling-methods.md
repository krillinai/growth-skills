# Growth Model Methods

## Business-Specific Topologies

| Condition | Required distinctions |
| --- | --- |
| Consumer subscription | user value, habit or natural frequency, free and paid states, subscription revenue, churn, refunds, contribution, and organic or paid inputs |
| Sales-led B2B | lead, opportunity, buyer, user, workspace, account, contract, implementation, renewal, retained ARR, rep capacity, ramp, service load, and cash timing |
| Usage-based product or API | account, workload, accepted useful outcome, metered usage, price metric, variable cost, reliability, retained workload, and concentration |
| Marketplace | participant side, atomic market, availability, request, match, completion, quality, utilization, incentives, retained supply and demand, local contribution, and safety |
| Advertising product | audience value, creator or supply value, advertiser demand, inventory, quality, auction, revenue, user retention, concentration, and trust |
| AI product | task, accepted result, correction, human review, latency, safety, repeated success, inference cost, willingness to pay, model version, drift, and consent |

Use a graph or state model when entities can skip, repeat, reverse, branch, or participate in overlapping mechanisms. Do not force every business through one linear lifecycle.

## Compatibility Gate

Before combining coefficients, require compatible:

- entity, identity, eligibility, and denominator;
- customer segment, role, payer, product, market, and channel;
- event and outcome definitions plus version;
- period, cohort start, cohort age, window, lag, maturity, cutoff, and timezone;
- attribution and incrementality basis;
- currency, accounting policy, cost scope, and cash timing;
- capacity and guardrail definitions;
- source freshness and model version.

When the gate fails, preserve observations separately and return the harmonized definition or data specification needed for calculation.

## Customer Stock And Flow

For an opening active population where retained and churned are mutually exclusive and exhaustive:

    opening active = retained opening + churned opening

    ending active
    = retained opening
    + new retained
    + resurrected
    + other verified inflows
    - other verified outflows

    net change
    = new retained
    + resurrected
    + other inflows
    - churned opening
    - other outflows

Do not subtract `churned opening` again from `retained opening`; it was already removed when the opening population split. If `retained` means something else, rename and define it before calculating.

## Revenue Stock And Flow

Under one currency, period, population, and revenue policy:

    ending recurring revenue
    = opening recurring revenue
    + new revenue
    + expansion revenue
    - contraction revenue
    - churned revenue
    + other verified adjustments

Reconcile opening revenue to retained, contracted, and churned components when those views are used. Keep bookings, billings, recognized revenue, cash, GMV, platform-attributed revenue, gross margin, contribution, and LTV distinct.

## Transition Decomposition

For one compatible mature cohort:

    new retained customers
    = qualified reach
    x acquisition conversion
    x activation-to-value rate
    x retained quality

Show each factor's numerator, denominator, entity, window, cohort age, source, and uncertainty. The equation decomposes an observed or assumed result; it does not establish incrementality or causality.

## Loops And Reinvestment

Include a loop only when a qualified output or retained resource becomes a later qualified input and produces value again. Map eligibility, output, next input, recipient or system response, realized value, retained quality or matured economics, cycle time, re-entry, overlap, decay, saturation, and guardrails.

For paid or sales-capacity reinvestment, include contribution, payback, cash availability, budget or hiring decision, marginal demand, operational capacity, lag, retained cohort quality, and later contribution. Revenue, ROAS, pipeline, content, data, invitations, or headcount alone do not prove a loop.

Route detailed closure, K-factor, referral, marketplace, content, data, or reinvestment-loop work to `growth-loop-design`.

## Four Connected Fits

Audit all four as linked model assumptions:

| Fit | Decision question | Failure evidence |
| --- | --- | --- |
| Market-Product Fit | Does the product solve an important problem for a defined market under the required conditions? | Weak first or repeated value, churn, workaround dependence, or exceptional manual rescue |
| Product-Channel Fit | Does the product and promise match how qualified customers discover, evaluate, adopt, and share it? | Reach without retained value, activation mismatch, or channel-driven product distortion |
| Channel-Model Fit | Can marginal channel economics and operating effort support the price, contribution, cash, and payback model? | CAC, sales effort, incentives, service cost, or payback exceeds retained value |
| Model-Market Fit | Can reachable demand, price, frequency, retention, economics, and capacity support the intended scale? | Strong local execution but an insufficient, saturated, concentrated, or uneconomic market |

Do not score the Fits as an independent checklist. Record the relevant nodes, edges, evidence, counterevidence, uncertainty, and decision implication for each. A change to customer, product, channel, price, package, route, geography, or intended scale can weaken several Fits and requires a new model version.

Moving upmarket is not a price-only scenario. Revalidate user, buyer, payer, problem, promise, product requirements, security, procurement, channel, sales cycle, implementation, support, retention, expansion, contribution, cash timing, capacity, and all four Fits.

## Scenario And Sensitivity

1. Freeze a versioned baseline with sources and reconciliation.
2. Name the decision outcome and guardrails.
3. Change one assumption or a declared coherent bundle.
4. Use supplied ranges or justify inferred ranges; never invent benchmarks.
5. Apply lags, maturation, saturation, capacity, cost, and cash timing.
6. Report absolute outcome, delta, sensitivity, downside, and unresolved interactions.
7. Keep observed baseline, scenario, forecast, target, and causal effect in separate fields.

Use one-at-a-time sensitivity for interpretability, then test material interactions. Historical coefficients may decay under mix, product, channel, competition, technology, or market change.

## Constraint Selection

Evaluate each candidate against:

- effect on the declared retained customer, durable value, contribution, cash, or other outcome;
- local and system sensitivity, including downstream quality and economics;
- evidence strength and compatible maturity;
- team control and time to learn;
- operational, financial, and organizational capacity;
- trust, safety, quality, fairness, regulatory, platform, and environmental risk;
- interaction with other constraints and risk of moving the bottleneck.

Select one primary model constraint only when evidence distinguishes it. Otherwise return ranked alternatives and the smallest discriminating evidence plan. Route broad triage, prioritization, 30-day action selection, and enterprise execution routing to `growth-diagnosis`.
