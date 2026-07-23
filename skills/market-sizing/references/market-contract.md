# Market Contract

Freeze this contract before calculation. Split the market whenever one row cannot describe the customer, job, product, geography, period, value, source, or decision being combined.

## Decision Boundary

| Field | Required definition |
| --- | --- |
| Decision | Choice informed, owner, deadline, threshold, and actions not authorized |
| Market | Customer job, trigger, category, alternatives, geography, language, locale, industry, and period |
| Product | Product, service, edition, bundle, platform, version, current availability, and non-goals |
| Customer | Beneficiary, user, buyer, payer, account, organization, household, and role hierarchy |
| Demand | Eligible entity, opportunity, frequency, quantity, use, purchase, payment, repeat, and retention |
| Economics | Price metric, realized value, spend, GMV, revenue, contribution, currency, tax, and accounting basis |
| Layers | Universe, total demand, serviceable, reachable, qualified, attainable, and excluded demand |
| Evidence | Source cutoff, model version, uncertainty, refresh, and review date |
| Action | Local analysis allowed now and separately authorized operating action |

## Entity Hierarchy

Keep person, household, employee, user, seat, device, workspace, organization, account, buyer, payer, contract, subscription, order, item, transaction, supplier, seller, and legal entity distinct. Define identity, hierarchy, shared and multiple roles, merge, split, duplicate, inactive, unknown, and cross-border states.

Choose one demand unit and one economic unit per calculation. A market can require several compatible views, but do not add them as one customer count.

## Layer Contract

For each layer record inclusion, exclusion, entity, job, trigger, product, market, time, frequency, value, source, method, assumptions, overlap, uncertainty, owner, and decision use.

- `bounded universe`: widest explicitly scoped population or activity;
- `total demand`: units with the defined job or opportunity, whether or not currently served;
- `serviceable demand`: units the current product and operating system can serve;
- `reachable demand`: serviceable units accessible through current authorized mechanisms;
- `qualified demand`: reachable units with fit, readiness, and viable economics;
- `attainable scenario`: conditional captured demand under explicit time, capacity, competition, and execution assumptions.

Map TAM, SAM, SOM, or internal labels to these definitions. Never infer the mapping from the acronym.

## Evidence Ledger

Every row includes exact claim or value, entity, layer, source and publisher, original URL or artifact, upstream lineage, method, sample or population, year, publication and capture dates, geography, category, unit, currency, coverage, exclusions, revisions, evidence state, limitation, contradiction, and next check.

Use only `verified`, `inferred`, `unavailable`, or `not applicable`. `Reported signal` can identify an attributable unsupported statement but is not an evidence state. A paywalled, blocked, removed, derivative, stale, or inaccessible source remains visible rather than becoming zero or fabricated evidence.

## Compatibility Gate

Before combining, align customer and economic units, job, category, product, geography, language, period, currency, tax, accounting, price basis, demand frequency, source population, method, coverage, and market layer. Preserve overlap, nesting, substitution, multi-homing, and unknown residuals.

If incompatibility changes meaning, keep separate estimates or create an explicit bridge. Do not average unlike proxies or convert all quantities to customers.
