# Growth Model Output Contract

## Required Order

Return:

1. mode, decision, owner, horizon, model ID, version, status, and action boundary;
2. model scope and business-specific topology;
3. node, edge, stock-flow, capacity, and guardrail registers;
4. evidence, definition, compatibility, causal-status, and limitation ledger;
5. equation and reconciliation register;
6. baseline and scenario comparison with ranges, lags, sensitivity, and downside;
7. primary model constraint or discriminating evidence plan plus alternatives;
8. 30-day validation plan and model-update triggers;
9. adjacent-Skill handoffs and pinned Growth Playbook sources.

## Model Map

Use a compact text graph plus registers. Do not rely on a decorative arrow diagram alone.

| Node | Entity and state | Stock or flow | Customer or business value | Unit | Source and evidence | Capacity or guardrail |
| --- | --- | --- | --- | --- | --- | --- |

| Edge | From -> to | Event and join | Numerator / denominator | Window, lag, cohort, maturity | Causal status | Cost, quality, uncertainty, alternatives |
| --- | --- | --- | --- | --- | --- | --- |

## Equation Register

| Equation | Purpose | Unit | Formula | Substituted values | Result | Source and version | Reconciliation difference | Limitation |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |

Show every unit and definition. A zero denominator is `unavailable`. Preserve missing values, ranges, incompatible observations, and unexplained reconciliation differences rather than forcing closure.

## Scenario Register

| Scenario | Changed assumption | Baseline | Range or scenario value | Lag and maturity | Outcome | Delta | Guardrail effect | Sensitivity | Decision use |
| --- | --- | ---: | ---: | --- | ---: | ---: | --- | --- | --- |

Label baseline observations, scenario assumptions, forecasts, targets, and causal estimates distinctly. Do not label a scenario as an expected forecast without a separately specified, calibrated, and back-tested forecasting model.

## Constraint Record

| Candidate | Outcome effect | Sensitivity | Evidence | Control and learning speed | Economics and capacity | Guardrail risk | Verdict |
| --- | --- | --- | --- | --- | --- | --- | --- |

State one primary constraint only when evidence distinguishes it. Otherwise state `unresolved` and give the smallest evidence task that would change the ranking.

## Validation Plan

| Evidence or model task | Assumption tested | Metric or artifact | Owner | Due or maturity date | Decision rule | Stop rule | Completion proof | Route |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |

Do not turn the model deliverable into production instrumentation, dashboards, forecasts, pricing, product, channel, staffing, or experiment execution. Route specialist work and record required permissions, privacy review, approvals, monitoring, rollback, and audit controls.
