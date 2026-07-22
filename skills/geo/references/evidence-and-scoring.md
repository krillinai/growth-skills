# Evidence And Scoring

## Purpose And Boundary

This reference defines the evidence ledger and the readiness score for an audit. It applies only to the audited property and the stated collection boundary. It does not measure answer visibility, search ranking, traffic, conversion, or uplift; record those observations separately in `visibility-observation.md`.

Start public-first. Each required adverse finding must identify the property, scope item, capture or export, timestamp, evidence status, and the exact observation or conclusion. Do not turn a browser observation into a crawler, provider, training, or model conclusion without evidence specific to that mechanism.

## Evidence States

Serialize `evidence_state` using exactly one of these lowercase values for each evidence item and finding conclusion: `verified`, `inferred`, `unavailable`, or `not applicable`. Public/private origin and artifact details are separate metadata, not evidence states.

| State | Meaning | Scoring treatment |
| --- | --- | --- |
| `verified` | A dated, inspectable artifact directly supports the observation. A public raw HTTP capture, rendered DOM capture, response record, dated document, observed third-party record, or attributable private export can be verified when its metadata is complete. | May support pass, partial, or fail when it meets the row rule. |
| `inferred` | A clearly labeled interpretation drawn from available evidence. | An adverse inference can receive partial only. A positive inference cannot receive pass. |
| `unavailable` | The needed artifact, source, access, or observation was not supplied or could not lawfully be obtained. | No award or automatic penalty. It stays in the coverage denominator and out of the assessed-score denominator. |
| `not applicable` | The fixed row genuinely does not apply to the stated scope. | Excluded from both denominators. |

Record `evidence_origin` separately as `public artifact` or `private export`, with artifact ID, type, URL or owner, capture/generated timestamp, method, and scope. A private export is attributable only when it identifies its owner, generated time, run or report identifier, method, and stated scope; it can support its stated aggregate only, and missing raw artifacts remain `unavailable`.

A stakeholder report or unverified monitoring claim is a `reported signal`, `unscored`; it is not an `evidence_state`. Request the relevant inspectable artifact before treating the report as verified.

An artifact is not evidence of more than it shows. A dated PDF can verify its own contents while failing to support a page claim; an `href="#"` can verify a non-resolving link while not proving the claim false. An inaccessible record, absent primary source, absent raw answer, or unobserved provider behavior is unavailable, not a negative finding by itself.

## Finding And Evidence Ledger

Only assessed adverse results, `partial` and `fail`, require a unique row-qualified finding ID. Use `<property-key>-<row-id>-<sequence>`, for example `harbor-pricing-EXT-01-001`. Do not reuse an ID for a different property, row, or assertion. A `pass` requires an evidence and point trace, but no finding. `unavailable` and `not applicable` use their separate registers and do not use a finding.

| Field | Required record |
| --- | --- |
| Finding ID | Required only for `partial` and `fail`; unique property-qualified identifier. |
| Priority | `P0` verified material blocker, `P1` material evidence or readiness gap, or `P2` bounded improvement. Priority orders action; it does not change a row maximum, evidence state, or score. |
| Property and scope item | Exact URL, record, sample member, or bounded collection item. |
| Row and result | One fixed row ID and `pass`, `partial`, `fail`, `unavailable`, or `not applicable`. A finding ID is required only for `partial` and `fail`. |
| Evidence trace | Source/export ID, type, URL or owner, capture/generated timestamp, and the exact observed fragment, response, count, or quote. |
| Evidence state | Exactly one serialized `evidence_state`: `verified`, `inferred`, `unavailable`, or `not applicable`. |
| Evidence origin | `public artifact` or `private export`, plus the required artifact metadata. |
| Conclusion and limit | What follows from the artifact and what remains unavailable or inferred. |
| Action and completion | A testable next action and completion evidence. |

Priority is not a substitute for evidence. Every prioritized finding retains its exact trace: source or export ID, artifact type, URL or owner, timestamp, observed fragment or count, evidence state, and linked fixed row. An unavailable row never uses a finding; it belongs only in the unavailable-evidence register.

Maintain an Unavailable-evidence register for every material missing artifact. It is a collection-completeness record, not a deduction list, and every unavailable row has one register entry.

| Unavailable ID | Row ID | Scope | Missing evidence | Reason unavailable | Exact request | Acquisition / verification step | Dependency | Evidence-request priority / order | Completion condition |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `UNAV-001` | `EVD-01` | `harbor-pricing`, claim A | Current source URL, publication date, methodology | Not supplied | Property owner: provide the current source URL, publication date, and methodology for claim A. | Capture the supplied artifact; inspect the claim, date, and methodology against the exact claim wording. | `EVD-01` remains unavailable; no remediation finding is created. | `ER-P0 / 1` | Requested artifact is captured and verified, or the lawful acquisition attempt and continuing unavailability are recorded. |

`Evidence-request priority / order` sequences collection work only, for example `ER-P0 / 1` before `ER-P1 / 2`. It is separate from remediation finding priority (`P0`/`P1`/`P2`), never creates a finding, and has no score effect. A report may sequence an evidence request before any dependent finding: collect and verify the requested artifact first, then assess the dependent row if evidence becomes available. Do not merge the unavailable-evidence register with the finding ledger or the not-applicable register.

Maintain a Not-applicable register for each excluded row, recording the property and scope, fixed row, rationale, and evidence state `not applicable`. It is separate from the finding ledger and unavailable-evidence register.

For a collection such as a supplied page sample, claim set, or observed directory list, record `collected / required`, the fixed collection boundary, and each unavailable member. A bounded sample remains a sample: incomplete or unavailable collection evidence cannot be promoted to site-wide verified truth. Aggregate a property only after all applicable fixed rows and required collection members are recorded; do not average selected rows, silently omit members, or substitute a broader claim for missing collection evidence.

## Fixed Readiness Card

The readiness card has exactly five atomic rows. Each row has one fixed maximum, and the card has no optional, bonus, benchmark, or reweighted rows.

| Card dimension | Row ID | Atomic row | Maximum |
| --- | --- | --- | ---: |
| Access & Eligibility | ACC-01 | The in-scope public property is accessibly captured and eligible for the stated audit mechanism. | 20 |
| Extractability | EXT-01 | Material in-scope content is present and extractable in the evidenced delivery representation. | 25 |
| Evidence & Citationworthiness | EVD-01 | Material claims have a traceable, adequate primary source or an explicitly bounded observed source. | 25 |
| Entity & Source Consistency | ENT-01 | Observed owned identity and actually observed source records are consistent, or a verified mismatch is traced. | 20 |
| Measurement & Experimentation | MEA-01 | An attributable, controlled measurement or experiment artifact exists for the stated scope. | 10 |
| Total |  |  | 100 |

Do not split an atomic row into subweights, borrow unused points from another row, add points for optional formats, or deduct a benchmark score for an absent optional artifact. The same five row IDs and maxima apply to every property. A modifier can constrain scope but cannot change the card.

### Row Results

Use `pass / partial / fail` as `100 / 50 / 0` percent of the row maximum.

| Result | When allowed |
| --- | --- |
| Pass | Sufficient `evidence_state=verified`, with documented public-artifact or private-export origin metadata, directly satisfies the atomic row. |
| Partial | `evidence_state=verified` shows a partial condition; or a clearly adverse inference warrants a conservative partial result. |
| Fail | `evidence_state=verified` directly shows the row condition is not met. Link the exact finding ID. |
| Unavailable | Required `evidence_state=unavailable`. Record `0` earned for display but do not assess its maximum or call it a deduction. |
| `not applicable` | The row does not apply to the bounded scope. Exclude it from all applicable maximum. Its `evidence_state` is `not applicable`. |

A positive inference cannot receive pass. An inference cannot convert unknown model behavior, currentness, causality, or outcomes into verified fact. Findings must be exact: a verified delivery defect may support `EXT-01`; an unavailable source supports an unavailable `EVD-01`, not a fail.

## Calculation And Presentation

For each property, show the five fixed rows, row result, earned points, maximum, and collection completeness. Show an evidence and point trace for `pass`; a required finding ID for `partial` and `fail`; an unavailable-register ID for `unavailable`; and a not-applicable-register ID for `not applicable`. Do not emit a readiness percentage when no applicable row has assessed evidence; show `Not scored`.

```text
all applicable maximum = sum(maximum for pass, partial, fail, unavailable)
assessed applicable maximum = sum(maximum for pass, partial, fail)
earned = sum(row maximum * result fraction for pass, partial, fail)
score = earned / assessed applicable maximum * 100
coverage = assessed applicable maximum / all applicable maximum * 100
```

`unavailable evidence: 0 earned and no automatic penalty`. It remains in `all applicable maximum`, is excluded from `assessed applicable maximum`, and therefore reduces evidence coverage without changing the assessed readiness score. `not applicable` is excluded from both denominators. Round displayed percentages to two decimals only after calculation.

Example fixed-row trace:

| Row | Result | Earned / maximum | Exact trace |
| --- | --- | ---: | --- |
| ACC-01 | pass | 20 / 20 | `SRC-ACC-01`: verified evidence and point trace; no finding |
| EXT-01 | partial | 12.5 / 25 | `harbor-pricing-EXT-01-001` |
| EVD-01 | unavailable | 0 / 25 | `UNAV-001` -> `EVD-01`; no finding |
| ENT-01 | fail | 0 / 20 | `harbor-pricing-ENT-01-001` |
| MEA-01 | not applicable | 0 / 10 | `NA-001` scope record; no finding |

For this example: all applicable maximum = 90; assessed applicable maximum = 65; assessed earned = 32.5; evidence coverage = 65 / 90 * 100 = 72.22%; readiness score = 32.5 / 65 * 100 = 50.00%.

Report unavailable primary sources, private analytics, model crawls, third-party validation, and answer panels explicitly rather than filling the gap with a score, rank, causal explanation, or projected uplift.
