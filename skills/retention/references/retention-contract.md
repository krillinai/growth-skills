# Retention Contract

## Minimum Context

Capture these fields independently:

- decision question and primary mode;
- entity level: user, account, workspace, household, seller, buyer, subscription, product, logo, or revenue;
- eligible cohort rule and start event;
- recurring value event and quality threshold;
- natural interval or opportunity rule;
- primary retention definition;
- observation cutoff, cohort age, timezone, and maturity rule;
- market, language, locale, product surface, and segment;
- source IDs, owners, capture dates, definitions, and limitations;
- available private fields, purpose, access scope, and retention scope.

Public product information can support a draft recurring-value model and measurement specification. It cannot establish private cohort membership, event completion, churn reasons, retention rates, or causal effects.

## Metric Contract

For every reported metric, include:

| Field | Requirement |
| --- | --- |
| Name | Stable, specific metric name |
| Decision | Decision the metric informs |
| Entity | Unit counted |
| Cohort | Inclusion, exclusion, and start event |
| Value event | Exact event and quality threshold |
| Numerator | Counted qualifying entities or value |
| Denominator | Eligible population at the same maturity |
| Window | Cohort age, interval, opportunity, or survival time |
| Cutoff | Observation timestamp and timezone |
| Segments | Dimensions allowed for comparison |
| Source | Attributable table, artifact, export, or public record |
| Availability | `verified`, `inferred`, `unavailable`, or `not applicable` |
| Limitation | Missingness, censoring, identity, definition, or bias risk |

Do not compare metrics whose entity, start event, value event, denominator, maturity, window, or source definition differs without making the mismatch the finding.

## Data Quality Gate

Check identity stability, duplicate events, late arrivals, timezone, bot or internal activity, deleted accounts, backfills, event-version changes, missing opportunity records, billing lag, and right censoring. Preserve the supplied raw definition even when proposing a corrected definition.

Missing data is `unavailable`, not zero. No observed event is not proof that value did not occur unless event coverage is verified.

## Privacy

Use aggregate or pseudonymous records whenever individual identity is unnecessary. Exclude raw email addresses, phone numbers, names, private URLs, credentials, signed links, and unrelated event history from the deliverable. Do not claim a future deletion, suppression, or state change already occurred.

## Output Boundary

If a calculation gate fails, return the retention contract, known evidence, exact missing fields, and calculation-ready formula. Do not fill the gap with an industry benchmark or synthetic result.
