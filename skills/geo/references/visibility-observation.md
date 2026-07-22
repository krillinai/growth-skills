# Visibility Observation

## Contents

- [Boundary](#boundary)
- [Evidence And Panel Schema](#evidence-and-panel-schema)
- [Legacy Required-Field Normalization](#legacy-required-field-normalization)
- [Outcome Distinctions](#outcome-distinctions)
- [Citation URL Normalization And Metrics](#citation-url-normalization-and-metrics)
- [Canonical Comparison Match Key](#canonical-comparison-match-key)
- [Repetition, Competition, And Incidents](#repetition-competition-and-incidents)
- [Access And Reporting Limits](#access-and-reporting-limits)

## Boundary

Visibility is an observed answer-panel result, not a readiness-score input. A panel can record what an accessible product returned under stated controls; it cannot establish a stable rank, market share, provider behavior outside the capture, causality, traffic, conversion, or uplift.

Use a primary mode of `visibility` for a repeated answer panel. Select primary `incident` whenever a stakeholder reports a citation or mention decline, whether or not comparison artifacts are supplied. Competitive comparison is a modifier to visibility, not a separate primary mode.

Select market and language before collection; neither may be inferred from the operator's location, IP address, interface language, top-level domain, or query text. Treat Mainland China as a first-class market recorded as `Mainland China (CN)`, separate from `zh-CN`. If the product exposes no market or language control, retain the declared collection value, record the control as `unexposed`, and do not claim that the product enforced it.

## Evidence And Panel Schema

Every panel must identify its artifact and these conditions. Preserve literal query text and timestamps; write `unexposed` when model or exposure is not observable rather than guessing.

| Field | Required value |
| --- | --- |
| Artifact | Dated inspectable public answer capture, or attributable private export with owner, generated time, run ID, method, and limits. |
| provider | Observed provider label and exact canonical provider ID; preserve the label used by the artifact. |
| platform | Observed platform label and exact canonical platform ID; do not substitute the provider or product. |
| product | Observed user-facing product label and exact canonical product ID; do not substitute the provider or platform. |
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
| timestamp window | Exact panel window, timezone, duration, and sampling schedule. |
| repetition | Attempt number and total planned repetitions. |
| collection method | Exact manual, automated, export, or supplied-artifact method. |
| collection protocol | Exact conversation isolation, ordering, spacing, retry, and other execution controls. |
| answer definition | The rule used to classify an answer as substantive, no answer, error, no-feature, or unavailable. |
| citation definition | The rule used to identify and classify each displayed citation/source URL occurrence. |
| access status | `success`, `error`, or `unavailable`, with the observed HTTP/product status and login/paywall/CAPTCHA state. |
| response metadata | Exact retained response-state metadata, or `none` with the reason when no response observation was collected. |
| answer | Canonical status `answered`, `no answer`, `error`, `no-feature`, or `unavailable`; retain the response-state artifact when available. |
| mention | Whether each named entity is mentioned in an answered attempt. |
| citation/source URL instances | Every inspectable rendered HTTP(S) URL occurrence, including duplicates, in display order. Use `[]` only after inspecting the complete citation/source surface; otherwise use `unavailable` with the reason. |
| owned citations | Frozen ownership classification, ordered unique normalized URL array, unique URL count, and URL instance count. |
| third-party citations | Frozen non-owned classification, ordered unique normalized URL array, unique URL count, and URL instance count. |
| error | Exact observed error code or message, or `none` when access completed without error. |

An attributable private export can support its stated aggregate counts, but absent raw answer artifacts are unavailable for answer-level verification. It is not public evidence. Serialize an unsupported stakeholder report as `signal_status=reported signal`; `reported signal` is unscored and is not an `evidence_state`. A stakeholder-reported citation or mention decline with no inspectable capture selects `incident` mode, but change metrics and causes are unavailable until matched before/after evidence is supplied.

## Legacy Required-Field Normalization

Normalize a supplied legacy panel record deterministically and retain every original key and value in the evidence trace. Missing is not an invitation to infer.

| Current required field | Legacy normalization |
| --- | --- |
| artifact | Preserve the supplied artifact ID and attribution; if absent, mark `unavailable`. |
| provider | Preserve a supplied label and map only through an explicit canonical alias registry. A missing legacy provider is `unavailable`; never infer it from platform, product, domain, or language. |
| platform / product | Preserve supplied labels and map exact registered aliases only. A missing value or unregistered alias is `unavailable`. |
| product source URL | Preserve a supplied direct URL. A missing legacy product source URL is `unavailable`; never synthesize one from a product or domain label. |
| surface | Map to `unexposed` only when a complete retained artifact explicitly did not show it. Otherwise a missing legacy surface is `unavailable`. |
| shown model / exposure | Map legacy `model=<value>` to the same literal shown-model value. Preserve supplied exposure; use `unexposed` only when a complete artifact explicitly did not show it, otherwise `unavailable`. |
| search/network state | Map legacy `search_mode=<value>` to `search mode <same literal value>; network state unexposed` only when the artifact did not show network state. Never infer a fetch. |
| query | Preserve the exact supplied query; if absent, mark `unavailable`. |
| market / language | Treat supplied legacy values as preselected values. A missing preselected value is `unavailable`. |
| market / language product controls | Use `unexposed` only when a complete artifact explicitly did not show the control; otherwise a missing value is `unavailable`. Never copy the preselected value into the control. |
| login state | Preserve the supplied state; if absent, mark `unavailable`. |
| timestamp / timestamp window / repetitions | Preserve supplied values. Mark each missing value `unavailable`; do not construct a window or repetition count from another field. |
| collection method / collection protocol | Preserve supplied values. A missing legacy collection field is `unavailable`; do not infer it from timestamps, platform, or an export type. |
| answer definition / citation definition | Preserve supplied definitions. A missing definition is `unavailable`; do not reverse-engineer one from aggregate counts. |
| access status | Preserve the supplied status. A missing legacy access status is `unavailable`; do not infer success from an answer or error from missing content. |
| response metadata | Preserve supplied metadata. Missing legacy response metadata is `unavailable`, not `none`. |
| answer / mention / error | Preserve the exact supplied values. Mark each absent value `unavailable`; only an explicit `error=none` becomes `none`. |
| citation URL instances / normalized arrays / unique counts / instance counts | Recompute only from complete raw URL occurrences and a frozen ownership rule. If raw URLs or ownership are absent, all new classified citation fields are `unavailable`; retain legacy aggregates separately. |

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
| Owned citation | An observed citation points to the frozen owned-property set. | Retain every URL occurrence, then report attempt presence, normalized unique URLs, and URL instances. |
| Third-party citation | An inspectable citation does not point to the frozen owned-property set. | Retain every URL occurrence, then report attempt presence, normalized unique URLs, and URL instances. |
| Error | An attempt returned an error, including rate-limit or login-required. | Count as an error; it is not a non-mention. |
| No-feature | The accessed product explicitly shows that the requested feature or mode does not exist under the fully recorded condition. | Count separately as `F/N`; it is not an answer, non-mention, error, access failure, or product-wide claim. Login-required, paywall, CAPTCHA, timeout, and unobserved behavior are not no-feature. |
| Unavailable | Access, response-state artifact, or observation could not be obtained. | Do not convert to `no answer` or zero; state the unavailable condition and denominator. |

For a panel with `N` attempts and `A` answered attempts, report answer availability as `A/N`, no-answer observations as `Q/N`, errors as `E/N`, and no-feature as `F/N`; report citations only with the separate metrics below. A genuine `no answer` attempt remains in `N`, is excluded from `A`, contributes no observed mention to `M/N`, and is excluded from `M/A`. Record its successful access metadata and `error=none`; if access failed, an error occurred, or the response-state artifact is absent, classify that condition as error or unavailable instead of `no answer`.

Citation availability is independent of answer and mention availability. When answer text is inspectable but the citation/source surface is not, preserve the answer and mention record and set `citation/source URLs=unavailable`; do not emit a zero citation count or observed empty list. When login is required under the declared logged-out condition, set the answer, mention, and citation/source URLs unavailable and retain the exact login error. Do not bypass login, substitute a logged-in attempt, or count the gate as no answer, no-feature, or non-mention.

For every named entity, both mention outputs are mandatory: `mention_count_all = M/N` over all attempts and, when `A>0`, `mention_count_answered = M/A` over answered observations. When `A=0`, emit `mention_count_all = M/N` and the exact non-rate value `mention_count_answered = not calculated (0 answered observations)`; do not emit `0/0`, `0%`, or omit the answered output. If the platform or product is unavailable under the recorded condition, `mention_count_all` remains only an observed mention count over attempts and must be paired with that unavailability status; it is not a zero mention rate or zero visibility claim.

## Citation URL Normalization And Metrics

Freeze the owned-property URL/domain set before collection. Classify every inspectable rendered URL occurrence against that set; a URL is third-party only when it is inspectable and not owned. Do not infer classification for an unavailable URL.

Normalize each absolute HTTP(S) URL in this order:

1. Parse it as a URL; retain invalid or non-HTTP(S) text separately and do not count it as a citation URL.
2. Lowercase the scheme and host.
3. Remove default port `:80` for HTTP or `:443` for HTTPS.
4. Remove the fragment.
5. Resolve dot segments and use `/` for an empty path.
6. Preserve path case, query parameter names, values, order, duplicates, and encoding. Do not strip tracking parameters.

For each attempt, retain the raw owned and third-party URL-instance arrays in display order. Produce each normalized URL array by first occurrence order with duplicate normalized URLs removed. `*_unique_url_count` is that array's length; `*_url_instance_count` is the raw occurrence-array length. Repeated rendered links remain separate instances even when they normalize to one URL.

For a panel of `N` attempts with complete citation-surface inspection, report all six metrics:

- `attempts_with_owned_citation/N`: attempts whose normalized owned URL array is non-empty;
- `attempts_with_third_party_citation/N`: attempts whose normalized third-party URL array is non-empty;
- `total_unique_owned_citation_urls`: size of the ordered union of normalized owned URLs across attempts;
- `total_unique_third_party_citation_urls`: size of the ordered union of normalized third-party URLs across attempts;
- `total_owned_citation_url_instances`: sum of owned instance counts across attempts;
- `total_third_party_citation_url_instances`: sum of third-party instance counts across attempts.

If any attempt's citation surface is unavailable, these six complete-panel metrics are `unavailable`. Report inspectable attempt-level arrays and counts separately with citation-surface coverage `K/N`; do not turn an uninspected attempt into an empty array or zero.

## Canonical Comparison Match Key

Use this one ordered match key for both competitive and incident comparisons:

```text
provider_id | platform_id | product_id | surface | shown_model | exposure |
search_network_state | query | market | market_control | language |
language_control | login_state | timestamp_window | repetitions |
collection_method | collection_protocol | answer_definition | citation_definition
```

Resolve identities to registered canonical IDs before matching and retain observed aliases outside the key. Every key must contain every field. `unexposed` is a comparable explicit value; `absent` or `unavailable` invalidates comparison. All non-time fields must match literally after declared normalization.

For a competitive comparison, `timestamp_window` must be identical. For an incident, retain the exact before and after windows and compare their normalized alignment signature: timezone, duration, sampling schedule, spacing, and planned observation positions must match while calendar dates intentionally differ. If the signature is absent or differs, reject the incident comparison. Never silently drop a key, wildcard a missing value, or use a field outside this schema as a substitute.

## Repetition, Competition, And Incidents

Repeat the same controls to show observed variation. Record every attempt, including non-mentions, errors, citations, and timestamps. A small repeated sample may describe variation only within that panel; it does not create a stable visibility rate.

For a competitive modifier, use the [Canonical Comparison Match Key](#canonical-comparison-match-key) exactly. If any key field is absent, unavailable, or different, the comparison is invalid: report separate panel observations and do not compute a competitive difference, ordering, or rank. A cross-market or cross-language pair is always separate observations, even when every other condition matches. Do not label an entity rank one or infer an enduring advantage from a panel.

For an incident, select the mode from the reported citation or mention decline and use the same [Canonical Comparison Match Key](#canonical-comparison-match-key) used for competitive work. Without comparison artifacts, serialize the decline as `signal_status=reported signal`; do not calculate a change, verify a decline, or diagnose a cause. Matched evidence is required to verify the change, not to select incident mode. If any key field is absent, unavailable, or unmatched under its stated rule, the comparison is invalid and no delta may be reported. When matched evidence is available, retain the before and after artifacts and report counts. Without deployment logs, provider changelogs, traffic, crawl data, or other primary evidence, incident cause is unavailable or inferred only.

## Access And Reporting Limits

Use only bounded lawful access: respect product terms, applicable law, access controls, rate limits, and account boundaries. Do not bypass login, paywalls, CAPTCHAs, or technical controls. A CAPTCHA or paywall that blocks the stated condition is an access error or unavailable observation, not no-feature and not a non-mention. Use a manual fallback only through ordinary permitted user access without changing any panel field or comparison key; capture the displayed answer and citation URL instances, record all schema fields, and state that the observation is manual. If lawful manual access would change a required condition, do not substitute it into the panel; record the original attempt unavailable.

Report observation counts and their denominators, method, source status, and limitations. No stable rank follows from a panel. No causality follows from a before/after change. No uplift follows from a mention, citation, readiness score, optional discovery artifact, or content change.
