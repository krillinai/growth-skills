# Postmortem Contract

## Define The Reviewable Unit

Use one bounded unit with a stable ID:

- growth initiative or portfolio bet;
- experiment or alternative evidence design;
- product, feature, migration, or market launch;
- campaign, channel, lifecycle, pricing, incentive, or partnership change;
- market entry or exit decision;
- data, metric, infrastructure, process, or organization change;
- target, forecast, budget, planning, or resource decision;
- incident only after immediate response and specialist investigation are separated.

Split units when decisions, customers, products, markets, metrics, owners, timelines, evidence, economics, or actions differ materially. Coordinate shared effects without blending them.

## Freeze Required Fields

| Field | Requirement |
| --- | --- |
| Identity | Postmortem ID, version, mode, state, reviewed-unit type and ID, and superseded record |
| Original lineage | Plan, decision, metric, target, forecast, budget, experiment, release, strategy, and approval versions as applicable |
| Accountability | Review owner, original decision owner, outcome owner, artifact owners, contributors, approvers, and participant-account boundary |
| Scope | Customer and participant roles, product, model, market, locale, included outcomes, exclusions, and non-goals |
| Time | Original decision cutoffs, planned and actual periods, event and processing time, evidence cutoff, maturity, review, follow-up, and expiry |
| Governance | Source access, privacy, employment, legal and risk handoffs, correction rights, publication, system, spend, and external-action boundaries |

Do not silently change the reviewed unit after outcomes are visible.

## Use Explicit States

| State | Meaning |
| --- | --- |
| `draft` | Scope, lineage, owners, or required evidence is incomplete |
| `evidence-pending` | Required outcomes, corrections, maturity, or specialist evidence is unavailable |
| `review-ready` | The record is complete enough for accountable interpretation and decisions |
| `accepted` | The accountable owner accepted the bounded findings and decisions, with evidence |
| `actions-open` | Accepted follow-up commitments remain unresolved |
| `closed` | Required review obligations and actions have attributable completion or expiry records |
| `superseded` | A later version replaces this record while preserving history |
| `expired` | A finding, action, transfer rule, or review period lapsed without renewal |

None of these states proves a root cause, business impact, action effectiveness, or system improvement.

## Preserve The Original Snapshot

For each original decision record:

- problem, customer state, decision, alternatives, exclusions, and owner;
- evidence, counterevidence, unavailable inputs, assumptions, and uncertainty;
- metric, baseline, target, forecast, scenario, opportunity, economics, and capacity;
- expected mechanism, outcome, maturity, guardrails, risks, and failure signals;
- approval, authorization, scope, budget, dependencies, stop, rollback, and review rules;
- artifact IDs, versions, sources, timestamps, and effective periods.

Keep later outcomes and interpretations separate. Evaluate the decision against this snapshot, not the final result.

## Select Reviews Consistently

Define the population and trigger for mandatory, sampled, or optional postmortems. Include positive, negative, flat, harmful, inconclusive, invalid, stopped, cancelled, expired, and never-launched work when the trigger applies.

Useful triggers include material customer or economic exposure, unexpected outcome, guardrail breach, irreversible commitment, large resource use, important uncertainty resolved or left unresolved, repeated failure, reusable capability change, or portfolio decision. Do not select only stories useful for celebration or blame.

## Separate Evidence And Accounts

Use `verified`, `inferred`, `unavailable`, or `not applicable` for evidence. Preserve stakeholder or participant statements as attributable accounts with date, role, scope, and limitation. Agreement among participants does not independently verify a metric, event, cause, or action.
