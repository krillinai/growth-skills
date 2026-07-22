# Evidence And Scoring

## Purpose And Boundary

This reference defines the evidence ledger and the readiness score for an audit. It applies only to the audited property and the stated collection boundary. It does not measure answer visibility, search ranking, traffic, conversion, or uplift; record those observations separately in `visibility-observation.md`.

Start public-first. A finding must identify the property, scope item, capture or export, timestamp, evidence status, and the exact observation or conclusion. Do not turn a browser observation into a crawler, provider, training, or model conclusion without evidence specific to that mechanism.

## Evidence States

Use one of these states for each evidence item and each finding conclusion.

| State | Meaning | Scoring treatment |
| --- | --- | --- |
| Verified public | A dated, inspectable public artifact directly supports the observation: for example, a raw HTTP capture, rendered DOM capture, response record, dated public document, or observed public third-party record. | May support pass, partial, or fail when it meets the row rule. |
| Attributable private | A private export identifies its owner, generated time, run or report identifier, method, and stated scope. | May support the stated aggregate only; missing raw artifacts remain unavailable. |
| Inferred | A clearly labeled interpretation drawn from available evidence. | An adverse inference can receive partial only. A positive inference cannot receive pass. |
| Unavailable | The needed artifact, source, access, or observation was not supplied or could not lawfully be obtained. | No award or automatic penalty. It stays in the coverage denominator and out of the assessed-score denominator. |
| Not applicable | The fixed row genuinely does not apply to the stated scope. | Excluded from both denominators. |
| Reported signal, unscored | A stakeholder report or unverified monitoring claim without an inspectable supporting artifact. | Do not score it; request the relevant evidence. |

An artifact is not evidence of more than it shows. A dated PDF can verify its own contents while failing to support a page claim; an `href="#"` can verify a non-resolving link while not proving the claim false. An inaccessible record, absent primary source, absent raw answer, or unobserved provider behavior is unavailable, not a negative finding by itself.

## Finding And Evidence Ledger

Every scored pass, partial, or fail needs a unique property-qualified finding ID. Use `<property-key>-<row-id>-<sequence>`, for example `harbor-pricing-EXT-01-001`. Do not reuse an ID for a different property, check, or assertion.

| Field | Required record |
| --- | --- |
| Finding ID | Unique property-qualified identifier. |
| Priority | `P0` verified material blocker, `P1` material evidence or readiness gap, or `P2` bounded improvement. Priority orders action; it does not change a row maximum, evidence state, or score. |
| Property and scope item | Exact URL, record, sample member, or bounded collection item. |
| Row and result | One fixed row ID and `pass`, `partial`, `fail`, `unavailable`, or `not_applicable`. |
| Evidence trace | Source/export ID, type, URL or owner, capture/generated timestamp, and the exact observed fragment, response, count, or quote. |
| Evidence state | One state from the evidence table. |
| Conclusion and limit | What follows from the artifact and what remains unavailable or inferred. |
| Action and completion | A testable next action and completion evidence. |

Priority is not a substitute for evidence. Every prioritized finding retains its exact trace: source or export ID, artifact type, URL or owner, timestamp, observed fragment or count, evidence state, and linked fixed row. An unavailable item can be prioritized for collection while remaining unscored.

Maintain an Unavailable-evidence register for every material missing artifact. It is a collection-completeness record, not a deduction list.

| Unavailable ID | Property and scope | Needed primary evidence | Why unavailable | Requested or lawful next step | Linked finding ID |
| --- | --- | --- | --- | --- | --- |
| `UNAV-001` | `harbor-pricing`, claim A | Current source URL, publication date, methodology | Not supplied | Request source from property owner | `harbor-pricing-EVD-01-001` |

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
| Pass | Sufficient verified public or attributable private evidence directly satisfies the atomic row. |
| Partial | Verified evidence shows a partial condition; or a clearly adverse inference warrants a conservative partial result. |
| Fail | Verified evidence directly shows the row condition is not met. Link the exact finding ID. |
| Unavailable | Required evidence is unavailable. Record `0` earned for display but do not assess its maximum or call it a deduction. |
| Not applicable | The row does not apply to the bounded scope. Exclude it from all applicable maximum. |

A positive inference cannot receive pass. An inference cannot convert unknown model behavior, currentness, causality, or outcomes into verified fact. Findings must be exact: a verified delivery defect may support `EXT-01`; an unavailable source supports an unavailable `EVD-01`, not a fail.

## Calculation And Presentation

For each property, show the five fixed rows, row result, earned points, maximum, linked finding ID or unavailable-register ID, and collection completeness. Do not emit a readiness percentage when no applicable row has assessed evidence; show `Not scored`.

```text
all applicable maximum = sum(maximum for pass, partial, fail, unavailable)
assessed applicable maximum = sum(maximum for pass, partial, fail)
earned = sum(row maximum * result fraction for pass, partial, fail)
score = earned / assessed applicable maximum * 100
coverage = assessed applicable maximum / all applicable maximum * 100
```

`unavailable evidence: 0 earned and no automatic penalty`. It remains in `all applicable maximum`, is excluded from `assessed applicable maximum`, and therefore reduces evidence coverage without changing the assessed readiness score. `not_applicable` is excluded from both denominators. Round displayed percentages to two decimals only after calculation.

Example fixed-row trace:

| Row | Result | Earned / maximum | Exact trace |
| --- | --- | ---: | --- |
| ACC-01 | pass | 20 / 20 | `harbor-pricing-ACC-01-001` |
| EXT-01 | partial | 12.5 / 25 | `harbor-pricing-EXT-01-001` |
| EVD-01 | unavailable | 0 / 25 | `UNAV-001` -> `harbor-pricing-EVD-01-001` |
| ENT-01 | fail | 0 / 20 | `harbor-pricing-ENT-01-001` |
| MEA-01 | not_applicable | 0 / 10 | Scope record |

For this example: all applicable maximum = 90; assessed applicable maximum = 65; assessed earned = 32.5; evidence coverage = 65 / 90 * 100 = 72.22%; readiness score = 32.5 / 65 * 100 = 50.00%.

Report unavailable primary sources, private analytics, model crawls, third-party validation, and answer panels explicitly rather than filling the gap with a score, rank, causal explanation, or projected uplift.
