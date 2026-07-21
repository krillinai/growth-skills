# Google Play Audit

Use this fixed Google Play card for Play Store listing assessments. The public surfaces are title, short description, full description, category, feature graphic when displayed, screenshots, promotional video when displayed, rating, written reviews, content rating, Data safety disclosures, release information, and locale/country rendering. Play Console search, acquisition, and experiment evidence is optional private evidence: record it unavailable when it is not available, with no missing-data penalty.

| Dimension | Check ID | Check | Points | Usual evidence |
| --- | --- | --- | ---: | --- |
| Discovery | GPL-DSC-01 | Title supports evidenced query intent without unsupported claims | 7 | Dated listing/query capture |
| Discovery | GPL-DSC-02 | Category and genre context are appropriate to the stated use case | 3 | Dated listing capture |
| Discovery | GPL-DSC-03 | Search-term and visibility evidence is scoped to country, locale, and date | 5 | Play Console export or query capture |
| Discovery | GPL-DSC-04 | Store-listing acquisition source evidence is dated and segmented | 5 | Play Console export |
| Metadata | GPL-MET-01 | Title is clear and supportable | 6 | Dated listing capture |
| Metadata | GPL-MET-02 | Short description communicates a distinct, supportable value proposition | 6 | Dated listing capture |
| Metadata | GPL-MET-03 | Full description is structured, specific, and aligned with the listing | 8 | Dated listing capture |
| Creative | GPL-CRT-01 | [Optional] Feature graphic communicates a distinct product promise when present | 6 | Dated listing capture |
| Creative | GPL-CRT-02 | First screenshot communicates the primary use case at browse size | 8 | Dated screenshot capture |
| Creative | GPL-CRT-03 | Screenshot carousel forms a coherent story | 4 | Dated screenshot capture |
| Creative | GPL-CRT-04 | Screenshot messages are legible at browse size | 2 | Dated screenshot capture |
| Creative | GPL-CRT-05 | [Optional] Promotional video communicates the primary use case when present | 5 | Dated listing capture |
| Trust | GPL-TRU-01 | Visible rating and rating-count context are accurately represented | 3 | Dated listing capture |
| Trust | GPL-TRU-02 | Visible review themes are acknowledged by listing claims or follow-up evidence | 4 | Dated review sample |
| Trust | GPL-TRU-03 | Content rating is present and consistent with listing claims | 2 | Dated listing capture |
| Trust | GPL-TRU-04 | Data safety disclosure is present and consistent with listing claims | 3 | Dated listing capture |
| Trust | GPL-TRU-05 | Release information is current and consistent with visible listing claims | 3 | Dated listing capture |
| Localization | GPL-LOC-01 | Requested country, language, and observed selectors are recorded | 5 | Dated locale/country capture |
| Localization | GPL-LOC-02 | Visible copy and creative fit the observed locale and market | 5 | Dated locale/country capture |
| Experimentation | GPL-EXP-01 | Store-listing experiment plan or variant evidence is dated and testable | 5 | Play Console export |
| Experimentation | GPL-EXP-02 | Experiment result or decision record identifies metric, window, and audience | 5 | Play Console export |
| **Total** |  |  | **100** |  |

**Google Play boundaries.** Use Google Play terms: title, short description, full description, feature graphic, screenshots, and promotional video. Do not rename the short description an Apple subtitle. `GPL-CRT-01` feature graphic and `GPL-CRT-05` promotional video are explicitly optional. A complete, dated listing capture that verifies either is absent is always `not applicable` and excludes its 6 or 5 points; no audit scope or stakeholder request can change that result. A loading skeleton, HTTP error, non-rendered container, or other partial state that cannot establish presence is `unavailable`, not absent. When an optional surface is present, assess its stated quality check. An optional row never fails for absence. Only a separate, non-optional asset check backed by a current, cited Google primary rule requiring that asset in the exact listing context may fail for verified absence; cite the rule and retrieval date in the finding. In an Apple audit, these Google-only fields are `not applicable`; in a Google Play audit, unavailable console evidence is `unavailable`, not a failure. Request a static capture or supplied export and do not generalize copy from another locale or country.

**Creative collection checks.** `GPL-CRT-04` is collection-level only when its declared scope contains multiple screenshots. Define that set from the dated capture or supplied asset inventory and apply the shared collection rule to message legibility. `GPL-CRT-03` assesses the sequence as one story and does not create member rows or subweights.

**Performance work.** A Play Console measure is `verified` only from an attributable supplied artifact or export that exposes the source/system, scope, metric definition, date/window, country or segment, and value sufficiently to inspect. An owner's conversational measure is a reported signal. A listing change occurring in the same window does not prove cause; label that explanation `inferred` and request controlled experiment evidence, before/after asset history, and relevant source/territory splits. Do not forecast uplift.

**Google Play point trace.** For each fixed row, record `check ID | state | result (pass/partial/fail) | earned/max | finding ID`. For unavailable checks, record `check ID | unavailable | max | requested evidence`; keep them outside findings. Sum the fixed rows exactly as listed and do not reweight for app fame, rating volume, assumed team sophistication, asset quantity, missing private access, or requested executive outcomes.
