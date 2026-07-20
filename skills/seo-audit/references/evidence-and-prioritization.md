# Evidence and Prioritization

Use this contract for every reported audit result: diagnosed findings and unavailable-evidence limitations. Keep observations separate from conclusions, and make the next decision obvious.

## Evidence states

- **verified**: Directly observed in a fetched response, rendered page, crawl result, supplied export, measurement, or other inspectable artifact. Record the artifact, URL, scope, and relevant value.
- **inferred**: Supported by indirect observations but not confirmed at the required layer. State the reasoning and the missing check that would verify it.
- **unavailable**: The needed surface was not accessible, not supplied, or outside the available capability. State what is missing and how an owner can obtain it.

Missing access is never a negative finding. An unavailable Search Console export, log file, browser renderer, analytics property, or rank tracker does not prove that a site has an SEO problem. Report it as a limitation or verification request, not as evidence of failure.

## Rating scales

For `verified` and `inferred` findings, **impact** describes the plausible consequence if the finding is real and left unresolved.

- **critical**: Prevents discovery, crawling, rendering, indexing, or access across a business-critical property or creates an active, severe traffic risk.
- **high**: Materially affects an important template, market, conversion path, or large set of valuable URLs.
- **medium**: Meaningful but bounded effect, or an improvement whose benefit depends on other conditions.
- **low**: Limited scope, weak search consequence, or chiefly a quality and maintenance refinement.

For `verified` and `inferred` findings, **confidence** describes how strongly the available evidence supports the diagnosis.

- **high**: Reproducible direct evidence establishes the issue and its scope.
- **medium**: Evidence is credible but sampled, indirect, or missing one confirming layer.
- **low**: A plausible hypothesis that needs a targeted check or experiment.

**Effort** is a relative implementation estimate, refined by the site owner.

- **small**: Localized change with few dependencies and straightforward validation.
- **medium**: Multiple templates, teams, or validation steps, but no major rearchitecture.
- **large**: Broad migration, platform work, extensive content operations, or substantial coordination.

### Ratings when evidence is unavailable

An `unavailable` record is an audit limitation, not a diagnosed SEO finding. Use these values and no others:

- **impact**: `not-assessed`.
- **confidence**: `not-assessed`.
- **effort**: The expected cost to obtain and verify the missing evidence: `small`, `medium`, or `large`.
- **action**: A precise evidence-acquisition request, not a remediation.
- **completion condition**: The evidence is received and assessed, or the audit owner explicitly accepts the limited scope without it.

## Finding schema

```yaml
title: Brief statement of the condition and affected scope
status: verified | inferred | unavailable
evidence: Artifact, URL, observation, scope, and date; or the missing input
impact: critical | high | medium | low; not-assessed only when status is unavailable
confidence: high | medium | low; not-assessed only when status is unavailable
action: Specific next change or verification step with an owner-ready scope
completion condition: Observable result that proves the action is done
effort: small | medium | large
```

Example:

```yaml
title: Production crawl responses are unavailable for the incident window
status: unavailable
evidence: No server-log access or supplied export covers 2026-07-10 to 2026-07-12
impact: not-assessed
confidence: not-assessed
action: Request a bot-filtered response-code export for the affected directory and dates
completion condition: Export is assessed, or the incident owner accepts that crawler response history is outside scope
effort: small
```

## Prioritization

First, separate `unavailable` limitations from diagnosed findings. Render them in a limitations or evidence-needed section. Order them by audit dependency, then by evidence-acquisition effort when dependencies are equal. Never place them in the SEO remediation queue or rank them against diagnosed findings.

Order `verified` and `inferred` findings in four passes:

1. **Blockers**: verified conditions that prevent dependable crawling, rendering, indexing, or diagnosis. Resolve these before optimizing downstream signals.
2. **High-impact, high-confidence work**: changes with material reach and direct evidence. Within this group, prefer smaller effort unless dependencies dictate otherwise.
3. **Quick wins**: small-effort improvements with bounded, verified benefit that do not distract from blockers or higher-impact work.
4. **Experiments**: inferred or low-confidence opportunities. Define a hypothesis, success measure, comparison period or cohort, and rollback point before implementation.

Do not manufacture a numeric score from these labels. Explain dependencies and scope when two findings share the same ratings. Lower-confidence critical hypotheses belong in immediate verification, not in a queue of confirmed fixes.
