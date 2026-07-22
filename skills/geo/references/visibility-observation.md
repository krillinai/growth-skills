# Visibility Observation

## Boundary

Visibility is an observed answer-panel result, not a readiness-score input. A panel can record what an accessible product returned under stated controls; it cannot establish a stable rank, market share, provider behavior outside the capture, causality, traffic, conversion, or uplift.

Use a primary mode of `visibility` for a repeated answer panel, or `incident` for a matched before/after comparison. Competitive comparison is a modifier to visibility, not a separate primary mode.

## Evidence And Panel Schema

Every panel must identify its artifact and these conditions. Preserve literal query text and timestamps; write `unexposed` when model or exposure is not observable rather than guessing.

| Field | Required value |
| --- | --- |
| Artifact | Dated inspectable public answer capture, or attributable private export with owner, generated time, run ID, method, and limits. |
| platform | The platform observed. |
| product | The user-facing product observed. |
| model | Observed model identifier or `unexposed`. |
| exposure | Stated exposure condition or `unexposed`. |
| search mode | Exact mode, such as `web-search`, `search`, or `no-search`. |
| query | Exact query text. |
| market | Market or country setting. |
| language | Language setting. |
| login state | Logged-out, logged-in, or the exact state observed. |
| timestamp | Capture time for each attempt or a dated series. |
| repetition | Attempt number and total planned repetitions. |
| answer | Answered, error, no-feature, or unavailable; retain answer artifact when available. |
| mention | Whether each named entity is mentioned in an answered attempt. |
| owned citation | Each citation to a declared owned property. |
| third-party citation | Each citation to an observed non-owned property. |
| error | Exact observed error code or message. |

An attributable private export can support its stated aggregate counts, but absent raw answer artifacts are unavailable for answer-level verification. It is not public evidence. A stakeholder statement with no inspectable capture is a reported signal, unscored: request a matched panel rather than manufacture a baseline.

## Outcome Distinctions

Keep these states distinct in the raw attempt record and in the summary.

| State | Meaning | Counting rule |
| --- | --- | --- |
| Answered | A usable answer was observed. | Counts in total attempts and answered attempts. |
| Mention | A named entity appears in an answered artifact. | Count against total attempts and answered attempts. |
| Owned citation | An observed citation points to the declared owned property. | Count against total attempts; retain the URL. |
| Third-party citation | An observed citation points to a non-owned property. | Count against total attempts; retain the URL. |
| Error | An attempt returned an error, including rate-limit or login-required. | Count as an error; it is not a non-mention. |
| No-feature | The observed product has no requested feature or mode under the documented condition. | Count separately; it is not an answered non-mention or a product-wide claim. |
| Unavailable | Access, artifact, or observation is absent. | Do not convert to zero; state the unavailable condition and denominator. |

For a panel with `N` attempts and `A` answered attempts, report answer availability as `A/N`; mentions as `M/N` total attempts and `M/A` answered attempts; owned citations as `O/N`; third-party citations as `T/N`; errors as `E/N`; and no-feature as `F/N`. State `A=0` rather than calculating an answered-attempt mention rate. A product unavailable in a logged-out condition is unavailable under that condition, not a zero mention rate.

## Repetition, Competition, And Incidents

Repeat the same controls to show observed variation. Record every attempt, including non-mentions, errors, citations, and timestamps. A small repeated sample may describe variation only within that panel; it does not create a stable visibility rate.

For a competitive modifier, compare named entities only on the same matched panel: identical platform, product, model/exposure status, search mode, query, market, language, login state, timestamp window, repetition count, and answer/citation definitions. Report entity counts with the shared denominator. Do not label an entity rank one or infer an enduring advantage from a panel.

For an incident, retain dated before and after artifacts and verify that all controls match. Report counts before and after, for example mentions `4/4 -> 1/4`, owned citations `3/4 -> 0/4`, answers, and errors. Without deployment logs, provider changelogs, traffic, crawl data, or other primary evidence, incident cause is unavailable or inferred only.

## Access And Reporting Limits

Use only bounded lawful access: respect product terms, applicable law, access controls, rate limits, and account boundaries. Do not bypass login, paywalls, CAPTCHAs, or technical controls. When automation is not permitted or reliable, use a manual fallback: capture the displayed answer and citations, record all schema fields, and state that the observation is manual.

Report observation counts and their denominators, method, source status, and limitations. No stable rank follows from a panel. No causality follows from a before/after change. No uplift follows from a mention, citation, readiness score, optional discovery artifact, or content change.
