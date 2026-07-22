# Evidence And Scoring

## Purpose And Boundary

This reference defines the evidence ledger and the readiness score for an audit. It applies only to the audited property and the stated collection boundary. It does not measure answer visibility, search ranking, traffic, conversion, or uplift; record those observations separately in `visibility-observation.md`.

Start public-first. Each required adverse finding must identify the property, scope item, capture or export, timestamp, evidence status, and the exact observation or conclusion. Do not turn a browser observation into a crawler, provider, training, or model conclusion without evidence specific to that mechanism.

## Evidence States

Serialize `evidence_state` using exactly one of these lowercase values for each evidence item and finding conclusion: `verified`, `inferred`, `unavailable`, or `not applicable`. Public/private origin and artifact details are separate metadata, not evidence states.

| State | Meaning | Scoring treatment |
| --- | --- | --- |
| `verified` | A dated, inspectable artifact directly supports the observation. A public raw HTTP capture, rendered DOM capture, response record, dated document, observed third-party record, or attributable private export can be verified when its metadata is complete. | May support pass, partial, or fail when it meets the row rule. |
| `inferred` | A clearly labeled interpretation drawn from available evidence. | Unscored as a property result; it cannot assign pass, partial, or fail. Missing evidence required for an objective result makes the row unavailable. |
| `unavailable` | The needed artifact, source, access, or observation was not supplied or could not lawfully be obtained. | No award or automatic penalty. It stays in the coverage denominator and out of the assessed-score denominator. |
| `not applicable` | The fixed row genuinely does not apply to the stated scope. | Excluded from both denominators. |

Record `evidence_origin` separately as `public artifact` or `private export`, with artifact ID, type, URL or owner, capture/generated timestamp, method, and scope. A private export is attributable only when it identifies its owner, generated time, run or report identifier, method, and stated scope; it can support its stated aggregate only, and missing raw artifacts remain `unavailable`.

A stakeholder report or unverified monitoring claim is a `reported signal`, `unscored`; it is not an `evidence_state`. Request the relevant inspectable artifact before treating the report as verified.

An artifact is not evidence of more than it shows. A dated PDF can verify its own contents while failing to support a page claim. For citation resolution, distinguish a retrievable target from missing support: an actionable source URL that is actually requested and returns a verified terminal broken/non-resolving result, such as `404`, fails the required link-resolution property. A missing link, blank target, placeholder such as `href="#"`, blocked or inaccessible target, or source that was not retrieved provides no inspectable supporting-source evidence; classify the required source property `unavailable` with no finding. Neither case proves the underlying claim false.

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
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `UNAV-001` | `EVD-01` | `harbor-pricing`, claim A | Current source URL, publication date, methodology | Not supplied | Property owner: provide the current source URL, publication date, and methodology for claim A. | Capture the supplied artifact; inspect the claim, date, and methodology against the exact claim wording. | `EVD-01` remains unavailable; no remediation finding is created. | `ER-P0 / 1` | Requested artifact is captured and verified, or the lawful acquisition attempt and continuing unavailability are recorded. |
| `UNAV-002` | `MEA-01` | `harbor-pricing`, page audit | Attributable panel, change artifact, or measurement record with conditions and denominators | Not supplied | Audit owner: provide a dated attributable measurement artifact for this page-audit scope, including method, conditions, observations, and denominators. | Capture the artifact; verify attribution, scope, conditions, observation records, counts, and denominators. | `MEA-01` remains unavailable; no remediation finding is created. | `ER-P1 / 2` | A scope-matched measurement artifact is captured and verified, or the lawful acquisition attempt and continuing unavailability are recorded. |

`Evidence-request priority / order` sequences collection work only, for example `ER-P0 / 1` before `ER-P1 / 2`. It is separate from remediation finding priority (`P0`/`P1`/`P2`), never creates a finding, and has no score effect. A report may sequence an evidence request before any dependent finding: collect and verify the requested artifact first, then assess the dependent row if evidence becomes available. Do not merge the unavailable-evidence register with the finding ledger or the not-applicable register.

Maintain a required Not-applicable register for every excluded row. An in-scope GEO audit cannot mark a readiness row not applicable; `not applicable` is allowed only when the entire request is routed out of GEO audit scope and no readiness score is produced.

| N/A ID | Row ID | Scope | Objective routing evidence | Reason | Completion condition |
| --- | --- | --- | --- | --- | --- |
| `NA-001` | `ACC-01` | Out-of-scope request | Exact request and routing decision | No GEO property, page, site, visibility panel, or incident is in scope | Routing is recorded and no readiness score is emitted |

The not-applicable register is separate from the finding ledger and unavailable-evidence register. Create one entry for each excluded fixed row; never use N/A to avoid collecting missing evidence or to shrink an in-scope denominator.

### Collection Completeness

Before collection, declare the exact required units for every row: URLs or records for `ACC-01` and `EXT-01`, material claims and their sources for `EVD-01`, entity facts and comparison records for `ENT-01`, and measurement artifacts and conditions for `MEA-01`. Report `collected / required` for each row and list every unit by stable ID.

`collected` counts a unit only when its dated artifact is inspectable and sufficient to assign the unit an objective pass or fail. A verified defect counts as collected; a missing, inaccessible, uninspectable, or underspecified unit does not. If `collected < required`, at least one required property is unavailable and the whole row is `unavailable`. A bounded sample remains a sample: do not promote it to site-wide completeness, change the required count after inspection, silently omit members, or substitute a broader conclusion for missing collection evidence.

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

### Required Properties And Objective Tests

Declare every required property below for the bounded audit scope. A property passes or fails only from dated, inspectable evidence; missing evidence makes the property unavailable.

| Row | Required properties | Property pass criteria | Property fail criteria | Objective N/A rule |
| --- | --- | --- | --- | --- |
| ACC-01 | For every in-scope URL, record, or product condition: final response/outcome; content availability; and observed authentication, paywall, CAPTCHA, robots, or other mechanism-specific access restriction. | The required unit is lawfully reachable under the stated condition, returns the expected usable artifact, and has no observed restriction that blocks the specifically audited retrieval mechanism. | The captured response or product state verifies that the required unit is missing, unusable, denied, or blocked for the specifically audited mechanism. A directive is evidence only for the mechanism it governs. | Only when the entire request is routed out of GEO audit scope. |
| EXT-01 | For every in-scope page or record: raw representation; rendered representation when rendering is part of delivery; material headings, claims, facts, links, and structured text; and raw/rendered parity for those material elements. | Every required material element is present, readable, and extractable in each required representation, and material raw/rendered content is consistent. | A captured required representation omits, obscures, corrupts, or makes a required material element non-extractable, or verifies a material raw/rendered mismatch. | Only when the entire request is routed out of GEO audit scope. |
| EVD-01 | For every declared material claim: exact claim wording; source link or source identifier; source artifact and date; and source support for the claim's subject, magnitude, time period, and methodology. | The claim has an actionable, resolvable, inspectable source that directly supports every required claim component and is current for the stated use. | The inspected source contradicts or does not support one or more required claim components; or an actionable source target is requested and returns a verified terminal broken/non-resolving result. A missing, blank, placeholder, blocked, inaccessible, or uninspected source is unavailable, not fail, and creates no finding. | Only when the entire request is routed out of GEO audit scope. |
| ENT-01 | Declare the required entity facts before inspection, including applicable name, canonical domain, product identity, address, phone, and locale identifiers; capture the owned canonical record and every required comparison record. | Each inspected required fact in every required comparison record matches the owned canonical fact. ENT-01 passes only when all inspected required entity facts are consistent and collection is complete. | A captured comparison record verifies a mismatch for a required fact. All required facts mismatching yields fail; a mix of matches and mismatches yields partial. An absent or inaccessible required comparison record is unavailable, never fail. | Only when the entire request is routed out of GEO audit scope. |
| MEA-01 | For every page, site, visibility, or incident audit: an attributable panel, change artifact, or measurement record; complete platform/product/model/exposure/search/query/market/language/login/time conditions where relevant; planned and actual repetitions or observations; outcomes, counts, and denominators; and matched baseline/comparison controls when change is claimed. | Every required measurement artifact and condition is present, attributable, inspectable, and internally consistent; a claimed comparison is matched on all required controls. | Supplied measurement evidence verifies an invalid condition, denominator, attribution, repetition record, or unmatched comparison. If no panel, change, or measurement evidence is supplied, MEA-01 is unavailable, not fail or N/A. | Only when the entire request is routed out of GEO audit scope. MEA-01 is applicable to every in-scope page, site, visibility, and incident audit. |

### Deterministic Row Aggregation

Apply these rules in order to each fixed row; do not use judgment to choose a different result.

1. If the request is wholly out of GEO scope and the row has a required N/A-register entry, the row is `not applicable`.
2. Otherwise, if any required property is unavailable or `collected < required`, the whole row is `unavailable`, regardless of other observed passes or fails.
3. With complete collection, all required properties pass means row `pass`.
4. With complete collection, all required properties fail means row `fail`.
5. With complete collection, a mix of property passes and fails means row `partial`.

Assign property pass or fail only from verified evidence. An inference cannot assign a property result or change the deterministic aggregate; when evidence required for an objective result is missing, the property and whole row are unavailable. Never reweight properties within a row.

### Row Results

Use `pass / partial / fail` as `100 / 50 / 0` percent of the row maximum.

| Result | When allowed |
| --- | --- |
| Pass | Complete collection and all required properties pass. Evidence and point trace required; no finding. |
| Partial | Complete collection and required properties contain a mix of verified passes and fails. Link the exact adverse finding ID. |
| Fail | Complete collection and all required properties fail from verified evidence. Link the exact adverse finding ID. |
| Unavailable | Any required property is unavailable or `collected < required`. Record `0` earned for display but do not assess its maximum or create a finding. |
| `not applicable` | The entire request is objectively out of GEO scope and the row has a required N/A-register entry. Exclude it from both denominators and do not create a finding. |

An inference cannot convert unknown model behavior, currentness, causality, or outcomes into a property result. Findings must be exact: a verified delivery defect may support `EXT-01`; an unavailable source supports an unavailable `EVD-01`, not a fail.

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
| MEA-01 | unavailable | 0 / 10 | `UNAV-002` -> `MEA-01`; no finding |

For this in-scope page example: all applicable maximum = 100; assessed applicable maximum = 65; assessed earned = 32.5; evidence coverage = 65 / 100 * 100 = 65.00%; readiness score = 32.5 / 65 * 100 = 50.00%.

Report unavailable primary sources, private analytics, model crawls, third-party validation, and answer panels explicitly rather than filling the gap with a score, rank, causal explanation, or projected uplift.
