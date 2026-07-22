# Visibility Observation

## Boundary

Visibility is an observed answer-panel result, not a readiness-score input. A panel can record what an accessible product returned under stated controls; it cannot establish a stable rank, market share, provider behavior outside the capture, causality, traffic, conversion, or uplift.

Use a primary mode of `visibility` for a repeated answer panel. Select primary `incident` whenever a stakeholder reports a citation or mention decline, whether or not comparison artifacts are supplied. Competitive comparison is a modifier to visibility, not a separate primary mode.

Select market and language before collection; neither may be inferred from the operator's location, IP address, interface language, top-level domain, or query text. Treat Mainland China as a first-class market recorded as `Mainland China (CN)`, separate from `zh-CN`. If the product exposes no market or language control, retain the declared collection value, record the control as `unexposed`, and do not claim that the product enforced it.

## Evidence And Panel Schema

Every panel must identify its artifact and these conditions. Preserve literal query text and timestamps; write `unexposed` when model or exposure is not observable rather than guessing.

| Field | Required value |
| --- | --- |
| Artifact | Dated inspectable public answer capture, or attributable private export with owner, generated time, run ID, method, and limits. |
| platform | The platform observed. |
| product | The user-facing product observed. |
| product source URL | The current direct official product entry URL when product identity or capability scope depends on it; otherwise record `not applicable` with the reason. |
| surface | The exact user-facing surface, such as `web chat answer`, `web AI search`, or a named app view. |
| shown model | Exact model identifier displayed on that surface, or `unexposed`; do not backfill from product marketing or another surface. |
| exposure | Stated exposure condition or `unexposed`. |
| search/network state | Exact displayed search mode and network state, such as `search shown on, network use unexposed`; use `unexposed` for any part not shown and never infer a fetch from a toggle. |
| query | Exact query text. |
| market | Preselected market or country value. |
| market product control | Exact market value shown by the product control, or `unexposed`; do not infer it from the preselected value. |
| language | Preselected language value. |
| language product control | Exact language value shown by the product control, or `unexposed`; do not infer it from the preselected value. |
| login state | Logged-out, logged-in, or the exact state observed. |
| timestamp | Capture time for each attempt or a dated series. |
| repetition | Attempt number and total planned repetitions. |
| access status | `success`, `error`, or `unavailable`, with the observed HTTP/product status and login/paywall/CAPTCHA state. |
| response metadata | Exact retained response-state metadata, or `none` with the reason when no response observation was collected. |
| answer | Canonical status `answered`, `no answer`, `error`, `no-feature`, or `unavailable`; retain the response-state artifact when available. |
| mention | Whether each named entity is mentioned in an answered attempt. |
| citation/source URLs | Every inspectable URL displayed as an answer citation or source. Use `[]` only after inspecting the complete citation/source surface; otherwise use `unavailable` with the reason. |
| owned citation | Classification, count, and exact URL list for citations to declared owned properties; use explicit `none observed`, `0`, and `[]` only after complete inspection, or `unavailable` for all three when uninspectable. |
| third-party citation | Classification, count, and exact URL list for observed non-owned citations; use explicit `none observed`, `0`, and `[]` only after complete inspection, or `unavailable` for all three when uninspectable. |
| error | Exact observed error code or message, or `none` when access completed without error. |

An attributable private export can support its stated aggregate counts, but absent raw answer artifacts are unavailable for answer-level verification. It is not public evidence. Serialize an unsupported stakeholder report as `signal_status=reported signal`; `reported signal` is unscored and is not an `evidence_state`. A stakeholder-reported citation or mention decline with no inspectable capture selects `incident` mode, but change metrics and causes are unavailable until matched before/after evidence is supplied.

## Legacy Field Compatibility

Normalize a supplied legacy panel record deterministically and retain its original keys and values in the evidence trace:

- Map legacy `model=<value>` to `shown model=<same literal value>`. Preserve a separately supplied exposure value; use `exposure=unexposed` only when the artifact did not show it.
- Map legacy `search_mode=<value>` to `search/network state="search mode <same literal value>; network state unexposed"` unless the artifact independently shows a network state. A legacy search mode never proves a network fetch.
- Map an absent legacy surface to `surface=unexposed` only when the retained artifact did not show a surface. If it did, record the exact shown surface; never derive one from platform, product, URL, model, or search mode.
- Treat legacy market and language values as the preselected values. Record each corresponding product control as `unexposed` only when the artifact did not show it; never copy the preselected value into the product-control field.

Compatibility is only for already supplied legacy records. It does not permit omission of any field from a newly collected panel and never permits silent guessing.

For Mainland China panels on Baidu, Quark, Doubao, Tencent Yuanbao, Kimi, or DeepSeek, read [mainland-china-platforms.md](mainland-china-platforms.md). Use a current direct official source only for the exact product or surface statement it supports. If official documentation does not establish a capability, record it `unavailable`; only an explicitly captured manual observation may describe the bounded product behavior actually displayed.

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

Citation availability is independent of answer and mention availability. When answer text is inspectable but the citation/source surface is not, preserve the answer and mention record and set `citation/source URLs=unavailable`; do not emit a zero citation count or observed empty list. When login is required under the declared logged-out condition, set the answer, mention, and citation/source URLs unavailable and retain the exact login error. Do not bypass login, substitute a logged-in attempt, or count the gate as no answer, no-feature, or non-mention.

For every named entity, both mention outputs are mandatory: `mention_count_all = M/N` over all attempts and, when `A>0`, `mention_count_answered = M/A` over answered observations. When `A=0`, emit `mention_count_all = M/N` and the exact non-rate value `mention_count_answered = not calculated (0 answered observations)`; do not emit `0/0`, `0%`, or omit the answered output. If the platform or product is unavailable under the recorded condition, `mention_count_all` remains only an observed mention count over attempts and must be paired with that unavailability status; it is not a zero mention rate or zero visibility claim.

## Repetition, Competition, And Incidents

Repeat the same controls to show observed variation. Record every attempt, including non-mentions, errors, citations, and timestamps. A small repeated sample may describe variation only within that panel; it does not create a stable visibility rate.

For a competitive modifier, compare named entities only on the same matched panel: identical platform, product, surface, shown model/exposure status, search/network state, query, market, language, login and access state, timestamp window, repetition count, collection method, and answer/citation definitions. Report entity counts with the shared denominator. If any required condition is absent or differs, the comparison is invalid: report separate panel observations and do not compute a competitive difference, ordering, or rank. A cross-market or cross-language pair is always separate observations, even when every other condition matches. Do not label an entity rank one or infer an enduring advantage from a panel.

For an incident, select the mode from the reported citation or mention decline. Without comparison artifacts, serialize the decline as `signal_status=reported signal`; do not calculate a change, verify a decline, or diagnose a cause. Request dated matched before/after answer artifacts with identical controls, including product, surface, shown model/exposure, search/network state, market, language, login and access state. Matched evidence is required to verify the change, not to select incident mode. If any required before/after condition is absent or differs, the comparison is invalid and no delta may be reported. When matched evidence is available, retain the before and after artifacts and report counts, for example mentions `4/4 -> 1/4`, owned citations `3/4 -> 0/4`, answers, and errors. Without deployment logs, provider changelogs, traffic, crawl data, or other primary evidence, incident cause is unavailable or inferred only.

## Access And Reporting Limits

Use only bounded lawful access: respect product terms, applicable law, access controls, rate limits, and account boundaries. Do not bypass login, paywalls, CAPTCHAs, or technical controls. A CAPTCHA or paywall that blocks the stated condition is an access error or unavailable observation, not no-feature and not a non-mention. Use a manual fallback only through ordinary permitted user access without changing the declared login, market, language, search mode, or other panel condition; capture the displayed answer and citations, record all schema fields, and state that the observation is manual. If lawful manual access would change a required condition, do not substitute it into the panel; record the original attempt unavailable.

Report observation counts and their denominators, method, source status, and limitations. No stable rank follows from a panel. No causality follows from a before/after change. No uplift follows from a mention, citation, readiness score, optional discovery artifact, or content change.
