# Acquisition Contract

## Decision And Scope

Capture independently:

- acquisition decision, owner, decision date, horizon, review cadence, budget or capacity boundary, and permitted action;
- product, business model, stage, market, language, locale, currency, device, app or web surface, and product version;
- customer or account entity, best-fit hypothesis, problem, job, intent, trigger, alternatives, qualification, and exclusions;
- promise, proof, offer, message version, channel family, mechanism, external owner, source taxonomy, campaign, partner, and creative lineage;
- eligible reach, exposure or response, arrival, destination, entry state, identity, deduplication, new-versus-returning status, and qualified customer rule;
- first value, activation, retention, revenue, contribution, refund, support, complaint, trust, and risk outcomes;
- attribution rule, lookback, view-through, overlap, organic classification, counterfactual, assignment, interference, and incrementality status;
- cohort start, observation and maturation windows, cutoff, timezone, source latency, eligibility, denominator, and product version;
- media, creative, agency, incentive, tooling, sales, partner, implementation, support, fraud, refund, discount, and operating costs;
- gross margin, retained contribution, incremental CAC, marginal CAC, payback, cash timing, capacity, and uncertainty;
- qualified remaining demand, frequency, saturation, decay, fatigue, cannibalization, concentration, platform or partner dependency, policy, and recovery;
- source artifact, owner, extraction date, evidence state, freshness, limitation, and requested external action.

Version the contract when the customer, intent, mechanism, source taxonomy, offer, entry path, identity, attribution, cost scope, counterfactual, market, product, or decision horizon changes materially.

## Evidence States

Use:

- `verified`: directly supported by an attributable inspectable artifact;
- `inferred`: reasoned from named evidence with the inference explicit;
- `unavailable`: required but not supplied or observable;
- `not applicable`: outside the scoped decision;
- `reported signal`: attributable stakeholder statement without inspectable support; leave evidence state blank.

Public evidence may verify visible ads, pages, offers, rankings, content, app-store listings, partners, referral mechanics, public terms, and dated company claims. It cannot verify private spend, targeting, exposure, identity, attribution quality, incrementality, CAC, cohort quality, contribution, contracts, saturation, platform access, or control operation.

## Source State Chain

Keep distinct where applicable:

```text
eligible demand
-> qualified exposure or response
-> attributable arrival
-> reconciled new qualified customer
-> first value
-> retained value
-> retained contribution
-> incremental customer and contribution estimate
```

Define entity, source, timestamp, identity, eligibility, deduplication, numerator, denominator, window, version, owner, and reconciliation for every decision-critical state. A send, impression, click, lead, signup, install, platform conversion, or attributed sale is not automatically a new, retained, or incremental customer.

## Minimum Evidence And Privacy

Prefer aggregate or pseudonymous source cohorts, exposure, arrival, activation, retention, contribution, cost, risk, and experiment records. Exclude names, raw emails, phone numbers, credentials, payment credentials, tax IDs, raw messages, exact locations, unnecessary protected attributes, complete device graphs, unrelated browsing, and private notes when aggregate evidence is sufficient.

Document purpose, authority or consent, allowed joins, access, retention, minimum cell size, output aggregation, correction, deletion, and prohibited uses. Do not enrich, upload, contact, or score named people as part of strategy analysis.
