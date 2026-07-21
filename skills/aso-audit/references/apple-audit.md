# Apple App Store Audit

Use this fixed Apple card for App Store product-page assessments. The public surfaces are app name, subtitle, promotional text when displayed, description, screenshots, app preview when displayed, ratings, written reviews, age/content information, release notes, and localized storefront rendering. The App Store Connect keyword field, product-page optimization, discovery and conversion measures are optional private evidence: mark them unavailable when absent, never fail them for absence.

| Dimension | Check ID | Check | Points | Usual evidence |
| --- | --- | --- | ---: | --- |
| Discovery | APL-DSC-01 | Search query and visibility evidence is scoped to country, locale, and date | 10 | Query-result capture or dated export |
| Discovery | APL-DSC-02 | Keyword-field intent and duplication are evidenced | 10 | App Store Connect export |
| Metadata | APL-MET-01 | App name communicates the product/category without unsupported claims | 6 | Product-page capture |
| Metadata | APL-MET-02 | Subtitle sharpens positioning without repeating the name | 5 | Product-page capture |
| Metadata | APL-MET-03 | Promotional text is current and aligned when displayed | 3 | Product-page capture |
| Metadata | APL-MET-04 | Description opens with a clear, supportable value proposition | 6 | Product-page capture |
| Creative | APL-CRT-01 | First screenshot communicates the primary use case at browse size | 8 | Dated screenshot capture |
| Creative | APL-CRT-02 | Screenshot sequence forms a coherent feature/benefit story | 8 | Dated screenshot capture |
| Creative | APL-CRT-03 | Screenshot messages are legible, unobscured, and visually specific at browse size | 5 | Dated screenshot capture |
| Creative | APL-CRT-04 | App preview, when present, communicates a distinct usable story | 4 | Product-page capture |
| Trust | APL-TRU-01 | Visible rating and rating-count context are accurately represented | 3 | Product-page capture |
| Trust | APL-TRU-02 | Visible review themes are acknowledged by listing claims or follow-up evidence | 5 | Product-page capture or dated review sample |
| Trust | APL-TRU-03 | Public age/content and release-note information is consistent and current | 7 | Product-page capture |
| Localization | APL-LOC-01 | Selected storefront and locale are recorded; copy fits that locale | 5 | Dated locale capture |
| Localization | APL-LOC-02 | Visible creative and terminology fit the selected market | 5 | Dated locale capture |
| Experimentation | APL-EXP-01 | Product-page optimization plan or variant evidence is dated and testable | 5 | App Store Connect export |
| Experimentation | APL-EXP-02 | Experiment result or decision record identifies metric, window, and audience | 5 | App Store Connect export |
| **Total** |  |  | **100** |  |

**Apple boundaries.** The keyword field is not publicly observable. Promotional text and app preview are checked only when the capture exposes them; absent components must distinguish a verified absence from a rendering failure. Do not call the subtitle a Google Play short description, and mark Google Play-only fields such as feature graphic and short description `not applicable` in an Apple assessment. Do not assert a screenshot-count policy or compliance without a current, dated Apple primary source and matching product-page evidence.

**Creative-focused work.** When scope is limited to named screenshots, assess only the relevant creative and localization checks. Record viewport, rendered asset size, message size, contrast, obstruction, and sequence as supplied or observed. Label an expected conversion consequence `inferred`; performance remains unavailable unless measured.

**Apple point trace.** For an assessed check, record `check ID | state | result (pass/partial/fail) | earned/max | finding ID`. For unavailable checks, record `check ID | unavailable | max | requested evidence`; do not put these in the finding list. Sum each dimension exactly as listed above; do not reweight for brand maturity, number of assets, missing private access, or a stakeholder-requested score.
