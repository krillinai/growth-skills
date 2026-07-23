# Activation Diagnosis And Design

## Diagnostic Sequence

1. Verify the contract, instrumentation, cohort maturity, and denominator.
2. Separate user intent and entry states before reading aggregate conversion.
3. Locate the largest decision-relevant loss, delay, quality failure, or unsupported prerequisite.
4. Compare acquisition promise, prerequisites, path steps, errors, permissions, waiting, assistance, first-value quality, and downstream repeated value.
5. Separate observed facts, reported signals, inferred mechanisms, and unavailable evidence.
6. Select one mechanism only when it changes the next decision.

Useful mechanism categories include promise or intent mismatch, ineligible or mixed entry states, missing data or authority, unnecessary setup, necessary setup removed too early, blank-state burden, import or integration failure, reliability or latency failure, permission or trust friction, low-quality first result, collaboration or marketplace dependency, human-assistance dependency, and measurement error. Categories may coexist; do not assign one without evidence.

## Product Topology Checks

| Topology | Activation boundary |
| --- | --- |
| Consumer or habit | Deliver a recognizable first outcome and a credible next natural opportunity |
| B2B or collaborative | Separate user, workspace, account, administrator, and payer value |
| Marketplace or network | Require relevant supply, match, interaction, transaction, or recipient value where the job depends on another side |
| AI product | Require successful, useful, verifiable task completion with quality, retries, latency, cost, and trust boundaries |
| Low-frequency or episodic | Use meaningful completion, readiness, saved state, or opportunity-based validation |
| Assisted product | Attribute human work, customer participation, knowledge transfer, independent repetition, support burden, and margin |

## Intervention Patterns

Choose a pattern only when it addresses the supported mechanism:

| Pattern | Main validation risk |
| --- | --- |
| Template | Faster setup may constrain the real use case or create irrelevant content |
| Example data | Demonstrated value may not transfer to customer data |
| Import or migration | Mapping, permission, waiting, and data-quality failures may increase |
| Default | A common choice may be wrong for a decision-relevant segment |
| Progressive setup | Deferred prerequisites may create hidden downstream failure |
| Guided path | Checklist completion may replace first value |
| Human assistance | Custom labor may hide a product that cannot deliver repeatable value |
| Reliability recovery | Recovery may improve completion without restoring trust or durable value |

Do not remove setup merely to improve completion when it protects result quality, trust, safety, or downstream readiness. Do not add reminders, education, or copy changes before establishing that comprehension or memory is the supported barrier.

## Intervention Record

Every intervention must state:

- supported mechanism and evidence;
- eligible entity, entry state, intent, and customer job;
- intervention and responsible owner;
- qualifying first-value event and quality threshold;
- activation window and downstream validation horizon;
- immediate diagnostic, activation outcome, and retained-activation outcome;
- error, support, trust, privacy, accessibility, economic, and customer-harm guardrails;
- randomization unit or alternative evidence design;
- decision rule and follow-up action;
- dependencies and external-action authorization still required.

Read outcomes at three horizons: immediate path movement, meaningful first value, and downstream repeated value. Preserve original assignment, eligibility, and denominator through the downstream readout. A shorter flow is not a win if quality, readiness, trust, support, economics, or retained value worsens.

## Prioritization And Handoffs

Prioritize by decision relevance, evidence strength, eligible reach, mechanism control, expected learning, time to mature, reversibility, customer risk, support burden, and economic exposure. These are judgment dimensions, not an invented numeric score.

Route broad cross-lifecycle constraint selection to `growth-diagnosis`; recurring-value, cohort-retention, churn, or resurrection analysis to `retention`; product or onboarding copy to `copywriting`; lifecycle-message eligibility and copy to `lifecycle-marketing`; and causal design to an experiment capability. A handoff is not authorization to access accounts, change product behavior, launch a test, or contact users.
