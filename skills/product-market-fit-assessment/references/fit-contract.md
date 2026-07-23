# Product-Market Fit Contract

## Decision Context

Capture independently:

- decision, decision date, owner, decision window, and allowed action;
- product, version, promise, category, and alternative set;
- customer or participant, segment, role, account type, use case, problem, and geography;
- beneficiary, end user, buyer, payer, procurement role, and decision maker;
- natural frequency, credible opportunity, first-value event, repeated-value event, and success quality;
- entity, eligibility, exclusion, identity, cohort start, denominator, interval, observation window, maturity, cutoff, and timezone;
- price, price metric, willingness to pay, gross margin, contribution, cost to serve, CAC, and payback;
- channel, source, marginal reach, activation quality, retention quality, saturation, and platform dependency;
- reachable market, attainable share, competitive response, cash, capacity, trust, safety, quality, and regulatory constraints;
- source artifact, owner, extraction or field date, definition version, freshness, and limitation;
- privacy purpose, consent, approved joins, access boundary, minimum cell size, and output aggregation;
- product, market, channel, model, technology, competition, or expectation changes since the prior assessment.

Version the contract when a material field changes. Compare restated compatible history or show a visible break rather than treating two fit units as one continuous claim.

## Unit Of Fit

| Product condition | Minimum useful unit | Keep separate |
| --- | --- | --- |
| Consumer | user x use case x natural frequency | low-intent acquisition, device, market, and payer where relevant |
| B2B | role x workflow x account type x payer | end user, workspace, account, buyer, renewal, and service cost |
| Collaboration | individual value x workspace adoption | invitation, seat, repeated collaboration, and account outcome |
| Marketplace | participant side x atomic market x category | supply, demand, liquidity, quality, fulfillment, and local economics |
| Multi-product | product x segment x portfolio relationship | cross-promotion, substitution, cannibalization, and retained value |
| AI | task x acceptable result quality x user or account context | prompts, completed jobs, repeat outcomes, trust, and inference cost |

Do not generalize fit to an adjacent role, segment, geography, product, price, channel, or period without revalidation.

## Evidence States

Use:

- `verified`: directly supported by an attributable inspectable source;
- `inferred`: reasoned from named evidence with the inference explicit;
- `unavailable`: necessary but not supplied or observable;
- `not applicable`: not relevant to the declared unit and decision;
- `reported signal`: attributable stakeholder statement without inspectable support; leave evidence state blank.

Public information may verify public product claims, visible pricing, distribution surfaces, stated customer language, and dated company statements. It cannot verify private customer qualification, activation, retention, survey responses, contribution, CAC, payback, segment performance, or causal mechanisms.

## Minimum Input Shapes

Use aggregates or pseudonymous records whenever possible. Depending on the decision, request only:

- stable pseudonymous entity and fit-unit fields;
- eligibility, first-value, repeated-value, cohort-start, outcome, timestamp, maturity, and source-version fields;
- qualified survey response, reason code, field date, segment, tenure, response denominator, and source;
- coded interview evidence with participant eligibility, source, date, and contradictory cases;
- plan, price, revenue, variable cost, service cost, refund, churn, contribution, CAC, and payback aggregates;
- channel, source, qualified activation, mature retention, marginal cost, and incremental evidence;
- reachable-customer assumptions, attainable-share assumptions, ranges, source, and date;
- quality, trust, support, concentration, safety, capacity, and regulatory guardrails.

Do not request raw names, email addresses, phone numbers, credentials, payment credentials, signed links, exact locations, protected attributes, private recordings, full message bodies, private documents, or unrelated histories when aggregates, pseudonymous IDs, and coded themes are sufficient.
