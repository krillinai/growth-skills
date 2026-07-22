# Page And Site Audit

## Boundary

Use this workflow for `page` and `site` modes, including a focused modifier. It is a diagnostic inspection, not authorization to rewrite content, publish files, change Schema or robots controls, or modify the site. Start with public artifacts. Private analytics, logs, Search Console, CMS access, and paid tools can strengthen an audit but are optional; when absent, record the applicable evidence as `unavailable`, continue the public audit, and do not create a failure or deduction.

Apply the evidence states, five fixed rows, collection rules, and scoring arithmetic in `evidence-and-scoring.md`. Observed answer visibility belongs in `visibility-observation.md`, never in the readiness score.

## Declare The Inspection

Before fetching, record:

- primary mode, focused modifier if any, property/domain, exact URL boundary, market and language when relevant, capture date and time, and supplied artifacts;
- retrieval mechanism for each capture, including user agent when known, login state, redirects, and whether the artifact is supplied or collected during the audit;
- the required units for `ACC-01`, `EXT-01`, `EVD-01`, `ENT-01`, and `MEA-01`, each with a stable ID and `collected / required` target;
- exclusions and unavailable access. Do not expand a one-page request into a site crawl or inspect URLs outside an explicitly supplied deterministic sample.

Keep requests bounded. Use ordinary HTTP and a browser renderer only where rendering is part of delivery. Respect authentication, paywalls, CAPTCHAs, rate limits, robots controls, product terms, and applicable law. Never bypass a control. A failed lawful retrieval is an observed result for that exact mechanism, not proof about every crawler or product.

## Page Capture

For each in-scope URL, preserve separate dated artifacts for:

1. The raw request and response: requested URL, redirect chain, final URL, status, relevant headers, content type, robots directives observed in headers or page markup, and raw response body.
2. The rendered representation when required: renderer and viewport, timestamp, final URL, visible DOM text, material links, and any access or rendering error.
3. A material-element inventory: title, canonical identity, headings, core body content, claims, prices or availability, tables, lists, evidence links, entity facts, and structured data actually observed.
4. A raw/rendered parity trace for every material element. State `raw only`, `rendered only`, `both and consistent`, `both but different`, or `unavailable`.

Raw and rendered observations are independently `verified` when their captures are inspectable. A rendered-only claim is verified as page content, not as a supported claim and not as proof that an unspecified crawler receives it. Route a captured access denial under `ACC-01` as described below. When that denial or an uncaptured representation leaves the body, rendered DOM, material elements, or claim sources uninspectable, the dependent `EXT-01` and `EVD-01` properties are `unavailable` and require unavailable-register entries; do not treat inaccessible content as an extractability or evidence defect.

## Representative Site Sampling

A site audit uses a declared, bounded sample rather than implying a complete crawl. Prefer a supplied deterministic sample. Otherwise, build the smallest reproducible sample from a dated public inventory such as a sitemap or navigable URL set, then freeze it before inspection.

Represent distinct public functions and templates that exist in the inventory, such as home, product or service, pricing, documentation, editorial, integration, customer evidence, and legal. Record why each URL represents its stratum. Do not add unlisted URLs after seeing results, silently replace failures, or claim a template exists without inventory evidence.

Report:

- inventory source, inventory size if known, sample rule, chosen URLs, exclusions, capture date, and `fetched / selected`;
- every selected URL, including redirects, errors, and unavailable captures;
- page-level observations and sample-level counts with denominators;
- conclusions as true only of the sampled URLs. Any site-wide explanation is `inferred` and must name the complete crawl, server log, sitemap reconciliation, or other evidence needed to verify it.

If one required sample member is unavailable, the relevant collection row is unavailable. Preserve verified defects on captured members as observations, but do not turn them into a scored row result by dropping the unavailable member.

## Five-Dimension Inspection

### Access & Eligibility (`ACC-01`, 20)

For every declared URL or mechanism, inspect the final outcome, usable content, redirects, status, authentication/paywall/CAPTCHA state, and controls applicable to that mechanism. Record robots rules exactly, including user-agent and path scope. Use `platform-notes.md` for current provider distinctions.

For a declared access unit, a dated capture that verifies a mechanism-specific denial, such as HTTP 403, a CAPTCHA gate, or an authentication/paywall block, supplies an objective failing property: record the exact mechanism and condition, assign `ACC-01` using the fixed-row aggregation rules, and create the required unique finding for a partial or fail row. An attempt with no inspectable response or product state is `unavailable`, not fail. Never bypass the block or infer the concealed body. The verified access result does not make dependent content available: if the body or required rendered representation cannot be inspected, route `EXT-01`, `EVD-01`, and any other content-dependent property to their unavailable-evidence registers with the lawful access/artifact request and verification step.

Do not infer search indexing, model training, automated search/browse retrieval, or a user-triggered fetch from a generic robots rule, one public search result, or another bot's behavior. A dated search result verifies indexing only for the observed URL and search product. Provider fetch behavior or training remains unavailable without mechanism-specific evidence.

Completion: every declared unit has a dated capture sufficient to apply the objective `ACC-01` property test, and any recommended access change has a new lawful capture for the same mechanism showing the intended result. Recommendation is not implementation.

### Extractability (`EXT-01`, 25)

Compare required raw and rendered representations. Trace whether material headings, claims, facts, links, tables, lists, and relationships remain readable and retain their meaning when extracted. Inspect semantic associations such as heading-to-section, label-to-value, table headers, link purpose, and contextual independence. Record omissions, corruption, concealment, or material raw/rendered differences exactly.

Do not prescribe a fixed passage length, an AI-only page, or special formatting as a requirement. Schema and semantic HTML may aid machine-readable interpretation, but their presence does not prove citation, ranking, or visibility.

Completion: every material element in every declared representation has a parity/extractability result; a recommended remediation is complete only when a fresh raw/rendered capture under the same conditions verifies that the affected element is present, extractable, and contextually accurate.

### Evidence & Citationworthiness (`EVD-01`, 25)

Inventory each material quantitative, comparative, performance, safety, legal, or attribution-sensitive claim using its exact wording. Capture its link or source identifier, source artifact and date, and whether that source supports the claim's subject, magnitude, period, population, method, and limitations. Inspect named authors or responsible organizations and whether a purported primary source resolves.

An unsupported claim visible on a page is verified content with unavailable support. It is not substantiated and, without an inspected source, is not a failed claim. Confident language, popularity, Schema, or repetition by another page is not primary evidence. External research and benchmarks are context only and never create a score deduction or promised uplift.

Completion: every declared material claim has a current inspectable source that directly supports all required components, or remains in the unavailable-evidence register with the exact artifact request. A content recommendation is complete only after the revised claim/source pairing is recaptured and checked; the audit does not perform the revision.

### Entity & Source Consistency (`ENT-01`, 20)

Before comparison, declare stable facts to inspect: applicable organization/brand name, canonical domain, product identity, address, phone, locale, pricing, availability, people, and relationships. Capture the owned canonical record and only third-party records actually observed within the declared boundary. Compare exact fact, locale, date, and source.

Third-party search snippets are evidence of the snippet observed, not of the underlying page or provider knowledge. Do not invent directory, press, review, knowledge-panel, or citation presence. An inaccessible or absent required third-party record makes the row unavailable, not inconsistent. A verified mismatch supports a finding only for that record and fact; it does not establish a general entity problem.

Completion: every predeclared owned and comparison record is captured and every required fact is matched or traced to a verified mismatch. For a recommended correction, recapture both authoritative and comparison records after the owner publishes through legitimate channels; never recommend fabricated mentions, spam, or coordinated manipulation.

### Measurement & Experimentation (`MEA-01`, 10)

Inspect attributable query panels, answer captures, change logs, deployment records, before/after windows, and private exports supplied for this scope. Require the conditions, repetitions, outcomes, counts, denominators, attribution, and matched controls specified in `visibility-observation.md`. A private aggregate supports only its attributable scope; missing underlying records remain unavailable.

No monitoring artifact means `MEA-01` is unavailable, not failed. A readiness score does not predict mentions, citations, traffic, conversion, rank, or uplift. Optional discovery files do not substitute for controlled measurement.

Completion: an attributable inspectable artifact records all required conditions and internally consistent observations for the declared scope; any change claim also has matched baseline and comparison controls. A proposed experiment remains a recommendation until its dated artifacts exist.

## Focused Experimental Artifacts

When the modifier is limited to `/llms.txt`, OKF, a knowledge bundle, or a similar discovery artifact, inspect only the declared paths. Record status, media type, parse validity, content date/currentness, and exact contents or bounded inventory. A `200` verifies delivery only. Invalid syntax and stale content are observations about that artifact, not benchmark deductions.

Treat every such artifact as optional experimentation unless a current primary platform source explicitly documents support and effect. Never require an AI-only file or schema, claim that a crawler consumes it, infer visibility, or award/deduct readiness points merely because it exists, is absent, or is invalid. For unknown formats, mark the primary format source or platform support `unavailable`.

Serialize each requested artifact separately with `optional_feature_status`:

| Optional feature status | Use only when | Scoring treatment |
| --- | --- | --- |
| `implemented` | An inspectable implementation artifact exists at the declared path. Record its HTTP result, validity, and currentness separately; `implemented` does not mean valid, supported, or effective. | Observation only; no fixed-row award or deduction. |
| `no-feature` | An attributable implementation inventory or explicit owner record says the optional capability was not built or promised. A 404 alone does not establish this state. | Observation only; not `unavailable`, not fail, and no finding. |
| `unavailable` | Implementation status cannot be established from an inspectable artifact or attributable inventory. | Optional-feature evidence gap only; no fixed-row result, finding, or deduction. |

`optional_feature_status=no-feature` is not the visibility-panel `answer=no-feature` in `visibility-observation.md`; the fields, scopes, and denominators are unrelated. Record a delivered but invalid artifact as `optional_feature_status=implemented` plus `format_validity=fail`, never as a readiness failure.

A focused modifier does not make an optional path a required unit of `ACC-01`, `EXT-01`, `EVD-01`, `ENT-01`, or `MEA-01`. Do not use its 200, 404, invalid syntax, staleness, absence, or unknown support to assign any fixed-row property. If the request contains only optional-feature inspection and supplies no independently declared readiness units, still render the five-row readiness card: mark all five rows `unavailable`, assessed applicable maximum `0`, all applicable maximum `100`, evidence coverage `0.00%`, and readiness `Not scored`. Keep the optional-feature results outside the fixed-row traces. Any required unavailable-register entries describe the missing underlying readiness evidence, never the optional file's absence or status.

## Audit Completion Gate

The diagnostic audit is complete only when it:

- preserves the declared boundary, timestamps, sources, retrieval conditions, required-unit inventory, and collection completeness;
- shows raw and rendered evidence separately, sample denominators, all five fixed rows, score and evidence coverage when defensible, and `Not scored` when none are assessed;
- keeps verified observations, inferred explanations, unavailable evidence, reported signals, and out-of-scope routing distinct;
- creates one unique finding for each partial/fail row, and separate unavailable-evidence requests with owners or acquisition steps and testable completion conditions;
- names limitations: no site-wide generalization from a sample, no generic bot conclusions, no fabricated third-party presence, no visibility or causal inference from readiness, and no unsupported ranking factor or uplift;
- recommends only bounded actions and verification. Implementation requires a separate handoff or explicit user request.
