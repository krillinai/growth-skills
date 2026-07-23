# Activation Contract

## Minimum Context

Capture these fields independently:

- decision question and primary mode;
- entity and level: user, workspace, account, buyer, seller, creator, subscriber, product, or payer;
- user intent, customer job, and acquisition promise when relevant;
- entry state: self-directed new, invited, returning but unactivated, imported, migrated, sales-assisted, implementation-assisted, or marketplace participant;
- eligible population, activation start event, and exclusions;
- first-value event and its success, relevance, completeness, trust, effort, repeatability, or collaboration threshold;
- observation window, cutoff, timezone, cohort age, and maturity rule;
- value-reinforcement signal and retention-validation horizon;
- market, language, locale, product surface, role, device, plan, and other decision-relevant segments;
- source IDs, owners, capture dates, definitions, populations, and limitations;
- available private fields, purpose, access scope, and retention scope.

Public product information can support a draft customer-job model, candidate first-value event, and measurement specification. It cannot establish private eligibility, event completion, activation rates, failure mechanisms, retained activation, or causal effects.

## Metric Contract

For every reported metric, include:

| Field | Requirement |
| --- | --- |
| Name | Stable, specific metric name |
| Decision | Decision the metric informs |
| Entity | Unit counted and product level |
| Intent | Customer job or use case represented |
| Entry state | Starting context and prerequisites |
| Eligibility | Inclusion and exclusion rule |
| Start event | Timestamp that starts the activation window |
| Value event | Exact first-value event and quality threshold |
| Numerator | Qualifying entities or events |
| Denominator | Full eligible population for the same window |
| Window | Duration and cutoff with timezone |
| Maturity | Rule for complete and right-censored observations |
| Segments | Dimensions allowed for comparison |
| Source | Attributable table, artifact, export, or public record |
| Availability | `verified`, `inferred`, `unavailable`, or `not applicable` |
| Limitation | Missingness, censoring, identity, instrumentation, selection, or bias risk |

Do not compare metrics whose entity, level, intent, entry state, eligibility, start event, value event, quality threshold, maturity, window, or source definition differs without making the mismatch the finding.

## Entry-State Gate

Do not place self-directed users, invited collaborators, imported accounts, sales-assisted customers, returning unactivated users, or marketplace sides in one denominator unless the contract proves that they share eligibility and prerequisites. Record pre-completed work and assistance rather than attributing it to the user's activation path.

## Data Quality Gate

Check identity stability, duplicate events, retries, event order, late arrivals, timezone, bots or internal activity, test accounts, deleted accounts, backfills, event-version changes, client/server disagreement, missing failure events, assistance attribution, experiment exposure, and right censoring. Preserve the supplied raw definition when proposing a corrected one.

Missing data is `unavailable`, not zero. No observed event is not proof that first value did not occur unless event coverage is verified. Do not silently remove users who encountered errors, waiting, permission failures, or other path friction from the denominator.

## Privacy

Use aggregate or pseudonymous records whenever individual identity is unnecessary. Exclude raw email addresses, phone numbers, names, private URLs, credentials, signed links, customer payloads, prompt contents, generated private content, and unrelated event history from the deliverable. Do not claim a future deletion, suppression, or state change already occurred.

## Output Boundary

If a calculation gate fails, return the activation contract, known evidence, exact missing fields, event and quality specification, and calculation-ready formula. Do not fill the gap with another product's Aha Moment, an industry benchmark, a synthetic funnel, or a made-up score.
