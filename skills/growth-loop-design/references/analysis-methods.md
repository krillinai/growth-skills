# Analysis Methods

Analyze the loop as a graph of value-producing states and transitions. A referral sequence is one possible shape, not the universal model.

## Contents

- [Dependency Order](#dependency-order)
- [Generic Node Model](#generic-node-model)
- [Calculation Rules](#calculation-rules)
- [Time, Decay, And Saturation](#time-decay-and-saturation)
- [Collaboration And Referral Loops](#collaboration-and-referral-loops)
- [Content And UGC Loops](#content-and-ugc-loops)
- [Marketplace And Network Loops](#marketplace-and-network-loops)
- [Paid Reinvestment And Sales-Capacity Loops](#paid-reinvestment-and-sales-capacity-loops)
- [Data And Product-Improvement Loops](#data-and-product-improvement-loops)
- [Segmentation And Reconciliation](#segmentation-and-reconciliation)
- [Attribution And Causality](#attribution-and-causality)

## Dependency Order

```text
decision and qualified outcome
-> current customer or system value
-> entities, eligibility, identity, and maturity
-> value-producing action and output
-> qualified next input and receiving value
-> activation, retained quality, or matured economics
-> subsequent participation and cycle time
-> saturation, risk, and causal evidence
```

When an upstream dependency is unavailable, continue with supported observations but do not assign a stronger verdict or dependent metric.

## Generic Node Model

Map:

1. eligible source;
2. participating source;
3. value-producing action;
4. transferable output or reinvestable resource;
5. qualified next input;
6. recipient or system response;
7. realized value or activation;
8. retained quality or matured economics;
9. next-cycle participation.

For every edge, specify the source entity, destination entity, event, eligibility, numerator, denominator, delay, cohort, maturity, quality, cost, owner, and evidence. Preserve branching, repeat use, re-entry, overlapping loops, and outside channels. Use a graph or state model if the mechanism does not follow one ordered path.

## Calculation Rules

Show counts beside rates. Use only compatible entities, eligibility, identity, cohorts, windows, and maturity.

| Measure | Formula | Boundary |
| --- | --- | --- |
| Eligible-source rate | `eligible sources / declared active source population` | Active population needs its own value and time definition |
| Participation rate | `participating sources / eligible sources` | Participation can rise through coercion or low-quality rewards |
| Output rate | `qualified outputs / participating sources` | Define qualification before counting volume |
| Qualified-input rate | `qualified next inputs / outputs` | Deduplicate overlap and invalid or unreachable inputs |
| Response rate | `receiving entities responding / qualified next inputs` | A view, open, click, or install is not automatically value |
| Realized-value rate | `receiving entities reaching declared value / eligible responding entities` | Freeze the value event and maturation window |
| Retained-quality rate | `mature realized-value entities retained at R / mature realized-value entities` | Use the product's natural interval and preserve censoring |
| Next-cycle participation yield | `qualified later-cycle participants / qualified current-cycle participants` | Requires attributable linkage and complete cycle maturity |
| Loop-sourced outcome share | `qualified outcomes assigned to the loop / compatible total qualified outcomes` | Attribution share is not incrementality |
| Marginal contribution | `incremental or marginal revenue - refunds - cost of goods - declared variable and loop costs` | State all included costs and causal limits |

When a denominator is zero, return `unavailable`. Preserve zero events as observed zeroes only when instrumentation, eligibility, and observation are valid.

### Propagation Decomposition

For one compatible cohort, a descriptive propagation chain can be written as:

```text
participants
x outputs per participant
x qualified inputs per output
x response per qualified input
x realized value per response
x retained quality per realized-value entity
x next participation per retained entity
```

Prefer the directly observed next-cycle participant yield when linkage is trustworthy. Do not multiply averages from different cohorts, markets, windows, maturity states, or entity levels into a synthetic coefficient.

`K`, viral factor, and retention-adjusted propagation are descriptive only under their declared definitions. Do not require `K > 1`. A lower-yield loop can make a meaningful contribution alongside other channels; a value above one can coexist with low retention, overlap, slow cycles, poor economics, spam, or fraud.

## Time, Decay, And Saturation

Report the distribution of time to output, next input, realized value, retention, and full re-entry. Include median and another declared percentile when row-level evidence supports them; do not hide slow or censored units behind one average.

Compare equally mature cycle cohorts. Check whether participation, output quality, response, value, retention, contribution, or time changes by cycle number, source tenure, recipient relationship, market, network unit, incentive exposure, content age, channel, or volume band.

Saturation and decay are observed patterns, not universal thresholds. Candidate signals include repeated exposure, recipient overlap, shrinking eligible pools, content staleness, local supply congestion, declining match quality, rising marginal cost, longer cycle time, or lower retained quality. Preserve seasonality, mix, measurement, and platform changes as alternatives.

## Collaboration And Referral Loops

Map sender value before the prompt; recipient relevance; payload, artifact, role, context, and permissions; delivery; recipient response; first collaborative value; retained recipient and account value; and later collaboration or referral.

Useful measures include eligible sender rate, participation, qualified recipients, deliverability, recipient realized value, time to collaborative value, active roles, repeat multi-user workflows, retained account value, complaints, permission errors, overlap, abuse, and incremental contribution.

Gross invitations, seats, signups, codes, or attributed conversions do not establish closure. Separate organic word of mouth from prompted or rewarded referral, and sender value from recipient value.

## Content And UGC Loops

Map demand or topic input; contributor eligibility and motivation; creation or assisted creation; acceptance and quality; publication or reuse; discovery; recipient value; activation and retention; refresh or new demand; and later contribution.

Measure contributor participation, accepted useful outputs, originality, provenance, moderation, indexability where applicable, qualified discovery, recipient realized value, retained demand, refresh cost, decay, complaints, removals, and platform concentration.

Content volume, impressions, indexed pages, mentions, shares, or AI output are not loop health. Require usefulness, recipient value, retention, creator incentives, correction paths, and dependency risk.

## Marketplace And Network Loops

Define the network unit and core interaction before using aggregate supply or demand. The unit may be geographic, categorical, professional, organizational, workflow-based, or time-bound.

Map the hard side, availability, relevance, matching, response, transaction or interaction success, quality, repeat behavior, cross-side retention, reputation or data reinforcement, and next supply or demand input. Segment by network unit.

Measure local density, availability, time to match, match and completion quality, repeat use, cross-side retention, unique supply, multi-homing, contribution, concentration, congestion, disintermediation, trust, and interference. Aggregate participant count does not prove liquidity, network effects, or defense. Added participation can reduce value.

## Paid Reinvestment And Sales-Capacity Loops

Map qualified demand, acquisition cost, activation, matured customer quality, refund-adjusted revenue, contribution, payback, cash availability, operating capacity, reinvestment decision, marginal demand, and the later qualified cohort.

Use marginal rather than blended economics for expansion decisions. State cost scope, maturation, cash timing, attribution, incrementality, capacity, saturation, and channel concentration. Revenue, platform ROAS, pipeline, bookings, or average CAC alone do not establish a reinvestment loop.

For sales capacity, include ramp time, qualified pipeline, win quality, delivery capacity, retained account value, contribution, hiring and management cost, and the delay before additional capacity creates another qualified outcome.

## Data And Product-Improvement Loops

Map permissioned interaction data; coverage and representativeness; processing or learning; observable product improvement; exposure; customer value; adoption or retention response; and later permissioned data. Keep product-performance feedback separate from acquisition unless it actually creates a qualified growth input.

Check consent, minimization, access, retention, bias, missing populations, feedback amplification, drift, gaming, explainability, human override, safety, trust, and whether a competitor can reproduce the value. Data volume, model activity, or personalization does not prove improvement or a defensible loop.

## Segmentation And Reconciliation

Maintain one canonical total view alongside decision-relevant segments. Common splits include source value state, recipient relationship, loop family, payload, market, network unit, workflow, incentive exposure, acquisition source, account size, creator type, content age, and cycle number.

Reconcile source-to-output, output-to-input, input-to-response, response-to-value, value-to-retention, and retention-to-next-participation counts. Explain residuals from invalid outputs, overlap, delivery failure, identity loss, late events, deduplication, fraud, refunds, off-platform behavior, and censoring instead of silently dropping them.

## Attribution And Causality

Attribution can describe assigned loop-sourced outcomes. It cannot show what would have happened without the mechanism. Only call an effect incremental when a credible counterfactual design supports it. Preserve assignment through activation, retention, contribution, abuse, and trust readouts; do not stop at immediate participation.
