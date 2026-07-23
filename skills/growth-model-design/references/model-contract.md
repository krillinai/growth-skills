# Growth Model Contract

## Decision And Scope

Capture independently:

- decision, decision date, owner, action, horizon, scenario set, and update cadence;
- model ID, version, effective period, prior version, and version-change reason;
- product, promise, business model, customer or participant, segment, role, account type, use case, payer, geography, market, language, and locale;
- natural frequency, first-value event, repeated-value event, durable customer outcome, durable business outcome, and guardrails;
- entity, eligibility, exclusion, identity, deduplication, join, cohort, maturity, cutoff, timezone, and late-arrival rules;
- opening stocks, inflows, transitions, outflows, ending stocks, re-entry, and mutually exclusive reconciliation rules;
- currency, price, revenue policy, contribution scope, cost timing, cash timing, and capacity unit;
- channel, platform, attribution, incrementality, saturation, competition, trust, safety, quality, regulation, and external dependencies;
- source artifact, owner, extraction date, definition version, freshness, uncertainty, and limitation;
- privacy purpose, approved joins, access boundary, minimum cell size, retention policy, and output aggregation;
- requested external actions and their separate authorization state.

## Node Contract

| Field | Requirement |
| --- | --- |
| Node ID | Stable semantic identifier, not a chart position |
| Entity and state | User, account, workspace, lead, opportunity, order, subscription, participant, revenue, cash, capacity, or another explicit unit |
| Eligibility | Population allowed to enter the state |
| Value meaning | Customer or business outcome represented, if any |
| Stock or flow | Snapshot stock, period inflow, transition, outflow, accumulated resource, or external input |
| Unit | Count, currency, time, capacity, quality, rate, or another declared unit |
| Grain and time | Segment, market, product, cohort, period, cutoff, and timezone |
| Evidence | Source, version, state, causal status, and uncertainty |

Do not combine customer counts, event rows, accounts, orders, revenue, cash, margin, and capacity in one node or rate without explicit conversion and join rules.

## Edge Contract

For each directed relationship, record:

- source node and destination node;
- source and destination entities plus join key;
- qualifying event or mechanism;
- numerator, denominator, eligibility, and exclusions;
- observation window, lag, natural interval, cohort age, maturity, cutoff, and timezone;
- segment, market, channel, product, and model version;
- transition value, cost, quality, capacity demand, and guardrails;
- source artifacts and evidence state;
- causal status: `scenario assumption`, `descriptive association`, `mechanism-supported`, `causally identified`, or `unavailable`;
- competing explanations, interference, saturation, and external dependencies;
- owner and evidence needed to update the edge.

Arrows encode a hypothesis unless evidence supports a stronger status. A diagram layout, sequence, correlation, attribution model, or stakeholder belief is not causal identification.

## Model Status

Use one status:

- `hypothesis`: topology or material edges rely on assumptions or unavailable evidence;
- `partially evidenced`: several compatible nodes and edges are observed, but a material link, economic condition, capacity, or guardrail is unresolved;
- `decision-useful`: definitions, evidence, uncertainty, and sensitivity are sufficient for the named decision, even if every edge is not causally identified;
- `stale`: material scope, definition, coefficient, environment, or decision changes make the prior version unsafe for the current decision.

Status is decision-specific. A model useful for instrumentation may be insufficient for budgeting, staffing, market entry, or forecasting.

## Evidence And Privacy

Use `verified`, `inferred`, `unavailable`, or `not applicable`. Use `reported signal` only for an attributable stakeholder statement without inspectable support.

Prefer compatible aggregates or pseudonymous records containing only model-required entities, states, events, timestamps, cohorts, dimensions, outcome values, costs, capacity, quality, source versions, and cutoffs. Exclude direct identifiers, credentials, raw private payloads, exact locations, protected attributes, private recordings, and unrelated history when they are unnecessary.
