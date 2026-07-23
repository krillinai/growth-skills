---
name: growth-postmortem
description: Use when a team needs to build, audit, or refresh an evidence-bounded postmortem, retrospective, or after-action review for a completed, stopped, failed, successful, harmful, or inconclusive growth initiative, experiment, launch, campaign, market move, system change, target, forecast, or planning decision; reconstruct what was known, decided, executed, and observed; or turn outcomes into accountable learning and system changes without hindsight, blame, or causal overreach.
---

# Growth Postmortem

Turn one reviewable growth unit into a durable decision and learning record. Preserve what was knowable at the time, reconstruct events and evidence, reconcile intended and observed outcomes, separate outcome quality from decision and execution quality, bound causal claims, and govern follow-up. A postmortem improves the next decision; it is not a victory story, blame ritual, incident-response substitute, or execution authorization.

Read [postmortem-contract.md](references/postmortem-contract.md) before accepting the reviewed unit, original plan, decision, target, forecast, owner, period, evidence cutoff, state, or participants. Read [timeline-outcomes-and-evidence.md](references/timeline-outcomes-and-evidence.md) before reconstructing events, selecting evidence, reconciling outcomes, judging quality, or making causal claims. Read [decisions-learning-and-actions.md](references/decisions-learning-and-actions.md) before evaluating decisions, retaining lessons, assigning actions, transferring learning, or closing the record. Read [governance-market-transfer-and-actions.md](references/governance-market-transfer-and-actions.md) before facilitating review, using personal data, transferring across markets, correcting records, or proposing external actions. Read [output-contract.md](references/output-contract.md) before delivery. Use [playbook-sources.md](references/playbook-sources.md) for the pinned Growth Playbook basis.

## Select One Mode

| Mode | Use |
| --- | --- |
| `build` | Create a postmortem from supplied original artifacts, evidence, outcomes, changes, and attributable participant accounts |
| `audit` | Inspect an existing postmortem for lineage, selection, hindsight, blame, reconciliation, causality, learning, action, and governance failures |
| `refresh` | Version a postmortem after evidence matures, corrections arrive, actions change state, or transfer decisions change |

Name one mode and state: `draft`, `evidence-pending`, `review-ready`, `accepted`, `actions-open`, `closed`, `superseded`, or `expired`. State does not prove cause, correction, action completion, adoption, system change, or business improvement.

Route unexpected metric triage and mechanism investigation to `growth-anomaly-investigation`, causal design and experiment readout to `experiment-design`, one initiative contract and execution plan to `growth-initiative-planning`, annual or quarterly plan reconciliation to `growth-planning-cycle`, recurring decisions and action follow-up to `growth-operating-review`, and domain-specific readouts to the relevant lifecycle, channel, campaign, launch, pricing, market, or infrastructure Skill. This Skill synthesizes a bounded after-action record; it does not rerun every specialist analysis.

## Freeze The Postmortem Contract

Record postmortem ID and version, mode and state, reviewed-unit type and stable ID, original plan, decision, metric, target, forecast, budget, experiment, release, and strategy versions as applicable; accountable review owner, original decision owner, outcome owner, artifact owners, contributors and participant-account boundaries; customer and participant roles, product and business model, market and locale, scope and exclusions, planned and actual periods, original cutoffs, postmortem evidence cutoff, maturity and follow-up dates, review and acceptance dates, superseded record, privacy boundary, and external-action boundary.

Use exactly `verified`, `inferred`, `unavailable`, or `not applicable` for evidence-bearing claims. Keep reported signal, observation, actual, baseline, target, forecast, opportunity, scenario, plan, budget, attribution, association, causal estimate, recommendation, decision, approval, authorization, action, completion, verification, and result separate. Preserve source, owner, date, version, entity, definition, population, market, period, currency, accounting basis, maturity, limitations, contradictions, corrections, and lineage.

Do not invent original intent, evidence, targets, forecasts, decisions, exposure, outcomes, costs, causes, confidence, participant views, action completion, or improvement. Missing evidence remains unavailable and may keep the record `evidence-pending`.

## Preserve The Ex-Ante Record

Reconstruct what was known, inferred, unavailable, assumed, forecast, targeted, decided, rejected, approved, authorized, planned, and protected at each original decision cutoff. Link original artifacts by stable ID and version. Keep later evidence and interpretation in a separate ex-post layer.

Do not overwrite the original plan with actuals, replace the original forecast or target, backdate a mechanism, hide missed gates, remove rejected alternatives, or claim participants predicted the outcome. Build explicit bridges for later data, definition, source, method, assumption, scope, decision, and correction changes.

Assess decision quality against the information, alternatives, authority, uncertainty, reversibility, downside, and controls available at the time. A favorable outcome can follow a weak decision; an unfavorable outcome can follow a sound bounded decision.

## Reconstruct Evidence And Timeline

Define a consistent review eligibility rule that includes successful, failed, flat, harmful, inconclusive, invalid, stopped, cancelled, expired, and never-launched units as applicable. Do not review only visible wins and failures or use postmortem count and win rate as learning quality.

Version proposal, decision, approval, authorization, build, QA, eligibility, assignment, access, exposure, adoption, customer outcome, business outcome, guardrail, incident, change, rollback, recovery, correction, and follow-up separately. Distinguish event time, processing time, reporting time, and maturity.

Use original artifacts, reproducible data, direct records, and attributable accounts with their limitations. Preserve contradictory accounts and unavailable evidence. A participant statement is not independent verification; a screenshot verifies only what is visibly captured.

Freeze metric entity, eligibility, identity, numerator, denominator, event or state, source, segment, market, window, cohort, cutoff, maturity, missingness, exclusions, currency, accounting basis, and version. Missing, late, censored, suppressed, and immature are not zero.

## Reconcile Intended And Observed Outcomes

Trace inputs, activities, outputs, eligible exposure, first value, repeated or protected value, retained customer outcome, business outcome, economics, capacity, and guardrails. Tasks, shipping, launch, spend, traffic, utilization, meetings, and decks are execution evidence, not impact by themselves.

Compare compatible original baseline, target, forecast, plan, budget, and guardrails with mature actuals. Build variance and revision bridges without treating a target miss or forecast error as a cause. Preserve absolute and relative movement, numerator and denominator, maturity, uncertainty, mix, and unknown residual.

Reconcile identities and lifecycle states without duplicate customers or value. Keep accountable ownership, contribution, attribution, association, causal estimate, forecast, opportunity, portfolio effect, and realized outcome distinct. Expose overlap, interaction, cannibalization, residual, and unresolved effects.

Include incremental and ongoing media, incentive, refund, chargeback, support, sales, implementation, infrastructure, fraud, risk, compliance, maintenance, incident, migration, decommissioning, and opportunity costs as applicable. Separate revenue, gross profit, contribution, cash, capacity, and valuation. Preserve existing-customer value, quality, accessibility, trust, fairness, reliability, and harm independently.

## Evaluate Quality In Separate Layers

Review without a composite score:

1. `outcome quality`: mature customer, business, economic, and guardrail result;
2. `decision quality`: ex-ante alternatives, evidence, uncertainty, authority, reversibility, and rules;
3. `evidence quality`: definitions, coverage, maturity, validity, counterevidence, and reproducibility;
4. `execution quality`: plan adherence, adaptation, readiness, delivery, QA, and completion proof;
5. `coordination quality`: ownership, handoffs, dependencies, escalation, and communication;
6. `system quality`: data, experimentation, platform, process, resilience, and maintenance;
7. `protection quality`: customer, employee, privacy, security, accessibility, fairness, and trust controls;
8. `learning quality`: whether evidence changes a decision, reusable artifact, system, capability, or retirement rule.

Keep luck, external change, variance, and unresolved causality visible. Do not convert good results into good decisions, bad results into incompetence, or activity speed into learning velocity.

## Bound Causal Claims

Separate symptom, observation, descriptive contributor, mechanism, root-cause claim, counterfactual, and corrective action. Temporal order, rollback recovery, dashboard attribution, segment correlation, customer quote, senior belief, or forecast variance does not prove cause.

For each candidate mechanism record affected population, expected onset and lag, supporting and contradictory evidence, alternatives, confounding, concurrent changes, selection, interference, maturity, causal status, and next discriminating evidence. Use `descriptive`, `associated`, `causally supported`, `contradicted`, `invalid`, or `unresolved` only when the evidence warrants it.

For experiments, preserve assignment, exposure, intent-to-treat population, sample ratio, power, peeking, multiplicity, metric amendments, maturity, guardrails, interference, and analysis version. A positive point estimate from an invalid or inconclusive design is not conclusive learning.

## Convert Evidence Into Durable Learning

For each learning state observation, interpretation, evidence and counterevidence, boundary, decision implication, owner, target artifact or system, transfer condition, failure signal, expiry, and review. A lesson is durable only when it changes or preserves a bounded decision, standard, template, metric, experiment design, initiative, training artifact, platform, portfolio rule, interface, maintenance obligation, or retirement choice.

Classify follow-up as `preserve`, `correct`, `prevent`, `detect`, `mitigate`, `investigate`, `experiment`, `reuse`, `standardize`, `retire`, or `route`. Record decision, artifact or operating state, accountable owner, dependencies, capacity, approval, due or maturity date, evidence, completion proof, guardrails, priority, stop, rollback, escalation, expiry, and residual obligation.

Do not end with generic advice, assign actions to everyone, or carry actions forever. Route open actions and repeated-mistake or reuse review to `growth-operating-review`. A handoff does not mean the action occurred.

## Audit Or Refresh

In `audit`, inspect scope and selection, original artifact lineage, hindsight edits, evidence coverage, metric and maturity contracts, timeline, outcome and economic reconciliation, duplicate impact, quality layers, causal language, blame and privacy, learning adoption, actions, residual obligations, market transfer, and external-action claims.

In `refresh`, preserve the prior record and add mature outcomes, corrections, newly available sources, changed causal status, action states, transfer evidence, and superseded learning by version. Record who changed what, why, from which evidence, which earlier statements remain valid, and which downstream decisions require reopening. Do not silently repair the narrative.

## Handle Markets, People, And Actions

Treat every market as a new customer, product, channel, platform, metric, baseline, exposure, evidence, calendar, economic, operating, causal, remedy, owner, and approval boundary. Translation and currency conversion do not validate transfer.

For mainland China, distinguish market, legal entity, language, locale, product, platform, app distribution, identity, payment, invoice, data, consent, content, advertising, holidays, support, staffing, costs, lead times, and locally accountable review. Use current direct sources and local expertise. Do not make legal, tax, regulatory, provider-availability, accounting, causal, approval, or performance conclusions.

Use aggregate, redacted, pseudonymous, minimum-necessary evidence. Use accountable roles rather than unnecessary names. Do not expose credentials, private messages, payment details, health or financial data, protected traits, precise locations, employee reviews, compensation, performance ratings, raw identities, or full histories. Do not rank individuals for consequential customer or employment decisions.

## Deliver In Order

Follow [output-contract.md](references/output-contract.md). Deliver the postmortem contract; original-state snapshot; evidence and timeline; planned-versus-actual customer, business, economic, capacity, guardrail, and obligation reconciliation; quality review; causal ledger; learning and action register; governance, market, privacy, handoffs, pinned sources, external actions, and completion record.

## External-Action Boundary

Create and read local artifacts only. Do not access authenticated analytics, data, experiment, project, planning, CRM, billing, advertising, product, cloud, support, HR, finance, procurement, or communication systems; export or join personal data; correct metrics, targets, forecasts, dashboards, data, or records; assign work; pause or roll back; contact people; publish; send; spend; procure; deploy; or claim correction, action completion, adoption, system improvement, or business impact without separate task-level authorization and controls.

## Completion Gate

Confirm the output passes [output-contract.md](references/output-contract.md); the eligible unit and original versions are frozen; ex-ante and ex-post evidence remain separate; outcomes, costs, capacity, guardrails, and obligations reconcile; result and decision quality are distinct; causal language matches evidence; contradictory, negative, harmful, invalid, and inconclusive evidence remains visible; learning changes a bounded decision or artifact; actions have owners and proof; blame and sensitive data are excluded; market transfer is revalidated; specialist work is routed; and no external action occurred.
