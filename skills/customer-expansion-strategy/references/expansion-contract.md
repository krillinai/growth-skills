# Customer Expansion Contract

## Decision And Customer Hierarchy

Capture independently:

- expansion decision, owner, decision date, horizon, review cadence, and permitted action;
- market, language, locale, legal entity, product, business model, package, contract, and version;
- customer, account, workspace, team, business unit, user, beneficiary, champion, administrator, buyer, approver, payer, security, procurement, and support hierarchy;
- original value scope, value event, natural interval, cohort, retained use, reliability, incidents, implementation, support, satisfaction, renewal, contraction, and contribution;
- expansion type, adjacent participant or job, candidate scope, need, fit, prerequisites, exclusions, product readiness, authority, security, procurement, budget, timing, and receiving-unit capacity;
- eligibility, signal, exposure, acceptance, provision, invitation, activation, first value, repeat value, retention, renewal, contract, billing, downgrade, contraction, churn, and reversal states;
- price, package, entitlement, limit, discount, currency, tax, payment, invoice, cost, margin, contribution, and cash timing;
- product, success, sales, support, engineering, data, finance, security, legal, privacy, and operations owners;
- original-scope, new-scope, total-customer, commercial, quality, trust, support, cannibalization, concentration, and risk outcomes;
- source artifact, owner, date, evidence state, freshness, limitation, and requested external action.

Version the contract when the customer entity, original scope, expansion type, value event, eligibility, signal, product, entitlement, price, contract, market, or outcome definition changes materially.

## Evidence States

Use:

- `verified`: directly supported by an attributable inspectable artifact;
- `inferred`: reasoned from named evidence with the inference explicit;
- `unavailable`: required but not supplied or observable;
- `not applicable`: outside the scoped expansion decision;
- `reported signal`: attributable stakeholder statement without inspectable support; leave evidence state blank.

Public evidence may verify visible products, features, packages, prices, roles, case claims, terms, and dated company statements. It cannot verify private customer identity, health, usage, expansion, authority, readiness, security, support, contracts, NRR, contribution, or causal impact.

## Expansion State Chain

Keep these distinct:

```text
eligible existing customer with retained core value
-> adjacent need observed
-> qualified and authorized opportunity
-> offer or product path actually exposed
-> accepted and provisioned
-> new scope activated
-> first value reached
-> repeated governed value
-> original scope remains healthy
-> retained total-customer and commercial value
```

Define entity, role, source, timestamp, identity, eligibility, deduplication, numerator, denominator, window, version, owner, and reconciliation for every decision-critical state. A signal, invitation, demo, opportunity, quote, signature, invoice, attach, provision, feature event, or billable unit is not retained expansion value.

## Privacy Boundary

Prefer aggregate, redacted, or pseudonymous account, role, value-state, exposure, adoption, retention, commercial, capacity, and risk evidence. Exclude names, raw emails, phone numbers, compensation, credentials, payment credentials, tax IDs, private messages, exact locations, protected attributes, unnecessary organization graphs, executive relationships, and unrelated histories.

Document purpose, authority or consent, joins, access, retention, minimum cell size, role and hierarchy inference risk, output aggregation, correction, appeal, and deletion. Do not enrich, score, route, contact, or expose named users or accounts as part of analysis.
