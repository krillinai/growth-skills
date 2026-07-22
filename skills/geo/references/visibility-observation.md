# Visibility Observation

## Boundary

Visibility is an observed answer-panel result, not a readiness-score input. A panel can record what an accessible product returned under stated controls; it cannot establish a stable rank, market share, provider behavior outside the capture, causality, traffic, conversion, or uplift.

Use a primary mode of `visibility` for a repeated answer panel. Select primary `incident` whenever a stakeholder reports a citation or mention decline, whether or not comparison artifacts are supplied. Competitive comparison is a modifier to visibility, not a separate primary mode.

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
| access status | `success`, `error`, or `unavailable`, with the observed HTTP/product status, login/paywall/CAPTCHA state, and response metadata. |
| answer | Canonical status `answered`, `no answer`, `error`, `no-feature`, or `unavailable`; retain the response-state artifact when available. |
| mention | Whether each named entity is mentioned in an answered attempt. |
| owned citation | Each citation to a declared owned property. |
| third-party citation | Each citation to an observed non-owned property. |
| error | Exact observed error code or message, or `none` when access completed without error. |

An attributable private export can support its stated aggregate counts, but absent raw answer artifacts are unavailable for answer-level verification. It is not public evidence. Serialize an unsupported stakeholder report as `signal_status=reported signal`; `reported signal` is unscored and is not an `evidence_state`. A stakeholder-reported citation or mention decline with no inspectable capture selects `incident` mode, but change metrics and causes are unavailable until matched before/after evidence is supplied.

## Outcome Distinctions

Keep these states distinct in the raw attempt record and in the summary.

| State | Meaning | Counting rule |
| --- | --- | --- |
| Answered | A usable answer was observed. | Counts in total attempts and answered attempts. |
| No answer | The platform was successfully accessed and the request completed, but the captured response state contains no substantive answer, such as an empty completion or an explicit no-answer/results state. Serialize `answer=no answer`, `access status=success`, and `error=none`. | Counts in total attempts `N`, but not answered attempts `A`. It contributes no observed mention to `M/N` and is excluded from `M/A`. It is not unavailable, no-feature, error, or an absent mention in an answered response. |
| Mention | A named entity appears in an answered artifact. | Count against total attempts and answered attempts. |
| Absent | An answered artifact exists, but a named entity or citation is not present in it. | Counts as an answered observation and as no observed mention/citation; it is not `no answer`. |
| Owned citation | An observed citation points to the declared owned property. | Count against total attempts; retain the URL. |
| Third-party citation | An observed citation points to a non-owned property. | Count against total attempts; retain the URL. |
| Error | An attempt returned an error, including rate-limit or login-required. | Count as an error; it is not a non-mention. |
| No-feature | The accessed product explicitly shows that the requested feature or mode does not exist under the fully recorded condition. | Count separately as `F/N`; it is not an answer, non-mention, error, access failure, or product-wide claim. Login-required, paywall, CAPTCHA, timeout, and unobserved behavior are not no-feature. |
| Unavailable | Access, response-state artifact, or observation could not be obtained. | Do not convert to `no answer` or zero; state the unavailable condition and denominator. |

For a panel with `N` attempts and `A` answered attempts, report answer availability as `A/N`; no-answer observations as `Q/N`; owned citations as `O/N`; third-party citations as `T/N`; errors as `E/N`; and no-feature as `F/N`. A genuine `no answer` attempt remains in `N`, is excluded from `A`, contributes no observed mention to `M/N`, and is excluded from `M/A`. Record its successful access metadata and `error=none`; if access failed, an error occurred, or the response-state artifact is absent, classify that condition as error or unavailable instead of `no answer`.

For every named entity, both mention outputs are mandatory: `mention_count_all = M/N` over all attempts and, when `A>0`, `mention_count_answered = M/A` over answered observations. When `A=0`, emit `mention_count_all = M/N` and the exact non-rate value `mention_count_answered = not calculated (0 answered observations)`; do not emit `0/0`, `0%`, or omit the answered output. If the platform or product is unavailable under the recorded condition, `mention_count_all` remains only an observed mention count over attempts and must be paired with that unavailability status; it is not a zero mention rate or zero visibility claim.

## Repetition, Competition, And Incidents

Repeat the same controls to show observed variation. Record every attempt, including non-mentions, errors, citations, and timestamps. A small repeated sample may describe variation only within that panel; it does not create a stable visibility rate.

For a competitive modifier, compare named entities only on the same matched panel: identical platform, product, model/exposure status, search mode, query, market, language, login state, timestamp window, repetition count, and answer/citation definitions. Report entity counts with the shared denominator. If any required condition is absent or differs, the comparison is invalid: report separate panel observations and do not compute a competitive difference, ordering, or rank. Do not label an entity rank one or infer an enduring advantage from a panel.

For an incident, select the mode from the reported citation or mention decline. Without comparison artifacts, serialize the decline as `signal_status=reported signal`; do not calculate a change, verify a decline, or diagnose a cause. Request dated matched before/after answer artifacts with identical controls. Matched evidence is required to verify the change, not to select incident mode. If any required before/after condition is absent or differs, the comparison is invalid and no delta may be reported. When matched evidence is available, retain the before and after artifacts and report counts, for example mentions `4/4 -> 1/4`, owned citations `3/4 -> 0/4`, answers, and errors. Without deployment logs, provider changelogs, traffic, crawl data, or other primary evidence, incident cause is unavailable or inferred only.

## Access And Reporting Limits

Use only bounded lawful access: respect product terms, applicable law, access controls, rate limits, and account boundaries. Do not bypass login, paywalls, CAPTCHAs, or technical controls. A CAPTCHA or paywall that blocks the stated condition is an access error or unavailable observation, not no-feature and not a non-mention. Use a manual fallback only through ordinary permitted user access without changing the declared login, market, language, search mode, or other panel condition; capture the displayed answer and citations, record all schema fields, and state that the observation is manual. If lawful manual access would change a required condition, do not substitute it into the panel; record the original attempt unavailable.

Report observation counts and their denominators, method, source status, and limitations. No stable rank follows from a panel. No causality follows from a before/after change. No uplift follows from a mention, citation, readiness score, optional discovery artifact, or content change.
