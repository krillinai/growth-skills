---
name: aso-audit
description: Use when auditing an Apple App Store or Google Play listing, comparing same-store listings, diagnosing a store-listing performance signal, or producing a requested ASO audit report.
---

# ASO Audit

Audit store listings, not product implementation, release submission, or app code. Route those requests to engineering or release operations; state that a later audit needs a dated listing capture, store identifier or canonical URL, country, locale, and requested surfaces.

## Compose The Smallest Scope

Choose one primary mode from the decision requested, then add only necessary modifiers:

- `listing` primary: assess a bounded Apple App Store or Google Play product page when the decision concerns the listing overall.
- `focused` primary: decide a question about only named listing surfaces, such as the first three screenshots; do not expand to metadata, reviews, or the app.
- `performance` primary: investigate a reported store-performance signal. Treat it as a signal until dated, segmented measurement verifies it; keep performance primary when adding comparison or surface bounds.
- `competitive` modifier: compare supplied listings using the same store, fixed card, country, locale, and date. Label the work competitive, but retain the decision's primary mode; a performance comparison is `performance + competitive`, not competitive primary. Listing-page evidence cannot establish query rank.
- `focused` bound: constrain a performance or competitive assessment to the named surfaces without changing its primary decision. For example, a performance diagnosis comparing only two screenshots is `performance + competitive`, focused to those screenshots.
- `out-of-scope`: own implementation-only requests for onboarding, deep links, release submission, or unrelated engineering. Give a concise ownership handoff instead of an audit. For mixed requests, audit only the ASO portion and hand off implementation work.

## Establish Scope And Evidence

1. Identify the store from a canonical URL or stable identifier: Apple ID/`apps.apple.com` routes to Apple; package/`play.google.com` routes to Google Play. Record app, canonical ID/URL, country or storefront, locale, capture/retrieval date, mode, requested surfaces, and limits. Do not substitute another store, market, locale, or historical capture.
2. Start public-first with supplied dated captures or bounded, read-only public pages. Do not require App Store Connect, Play Console, attribution, keywords, acquisition, ranking, conversion, or experiment access before beginning. Obtain authorization before private-console access or high-volume collection; keep access read-only and within the agreed scope.
3. Inventory observable surfaces and failed renders. Apple: name, subtitle, promotional text when displayed, description, screenshots, preview when displayed, ratings, reviews, age/content, release notes, and localization. Google Play: title, short description, full description, category, feature graphic when displayed, screenshots, promotional video when displayed, ratings, reviews, content rating, Data safety, release information, and localization.
4. Label every statement: `verified` for a dated observation or attributable export; `inferred` for a reasoned explanation or expected effect; `unavailable` for applicable missing/inaccessible/unrendered evidence; `not applicable` for another platform or excluded scope. A loading skeleton, HTTP error, or partial page proves only that rendered state.
5. Use optional owner evidence to refine an already-started audit: dated listing history, query capture, keyword export, acquisition/source/territory time series, attribution, experiment plan/results, and review samples. Ask for the smallest evidence that would change a conclusion.

## Assess With Fixed Cards

1. Read [Apple card](references/apple-audit.md) or [Google Play card](references/google-play-audit.md), then apply only its fixed atomic checks and six shared dimensions: Discovery, Metadata, Creative, Trust, Localization, and Experimentation. Use platform terms; Apple subtitle is not Google Play short description, and cross-platform fields are `not applicable`.
2. Use [evidence and scoring](references/evidence-and-scoring.md): assessed checks receive exactly pass `100%`, partial `50%`, or fail `0%` of the fixed maximum. Never reweight for brand fame, asset quantity, aesthetics, executive preference, or absent private data.
3. Keep unavailable applicable checks in coverage but out of score math; they earn and lose zero points. Exclude not-applicable checks from both denominators. Report `score = assessed earned / assessed max * 100` and `coverage = assessed applicable max / all applicable max * 100`, each to two decimals; show `Not scored` when its denominator is zero.
4. Define the full membership of each collection-level check before scoring. If membership is unknown or any applicable member is unavailable, the parent is unavailable; record member observations but do not subscore or partially score the collection.
5. Produce the required trace: `check ID | state | result | earned/max | finding ID`. Give every partial/fail one stable, evidence-linked finding; list unavailable checks in a separate register with the smallest next collection step. No missing-data penalty.

## Diagnose And Recommend

1. Inspect public copy, creative, visible trust signals, locale fit, and dated listing changes. For screenshots, record supplied or observed viewport, rendered size, message size, contrast, obstruction, first-use-case clarity, and narrative sequence. Label an expected conversion effect `inferred`; do not claim conversion, rank, installs, causality, or uplift without dated measurement.
2. For performance work, separate verified measurement (metric, segment, market, window) from inferred cause. Prioritize a validation sequence: before/after listing history, acquisition source and territory series, query/visibility evidence, then controlled experiment result.
3. Order findings by verified fail, verified partial, inferred adverse partial; then fixed-point deduction, validation dependencies, and lower effort. Keep public-surface changes separate from evidence-collection tasks. Each finding has ID, scoped source/date/check, observed impact, action, observable completion proof, and `S`/`M`/`L` effort.
4. Treat popularity and premium appearance as context, never proof of discoverability, relevance, quality, conversion, or installs. Treat platform requirements as verified only when a current primary source supplies its URL and retrieval date; add publication/update date only if exposed. Otherwise mark the exact rule unavailable and point to [platform sources](references/source-notes.md).

## Deliver

Present scope and limits; evidence states; fixed-card point trace; score and coverage with numerators/denominators; unavailable register; findings/actions/completion; prioritized roadmap; and validation plan. Generate HTML only when requested. For a standalone offline report, follow [HTML report](references/html-report.md). Hand implementation-ready listing-copy or creative briefs to the owning marketing/content/design team; hand app-code and release work to engineering/release operations.
