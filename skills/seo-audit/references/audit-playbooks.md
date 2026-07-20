# Audit Playbooks

Choose the narrowest playbook that answers the request. Diagnose in this dependency order: (1) discovery, crawling, and indexability; (2) canonicalization and site integrity; (3) performance and mobile experience; (4) page relevance and search intent; (5) content quality and internal discovery; and (6) authority or market signals only when evidence exists. Conditional checks may skip irrelevant layers but must not reverse this default order. Record every result with the evidence contract. Consult [source-notes.md](source-notes.md) for the search-engine and web-platform facts that support selected checks; operational audit guidance remains in this file.

### Audit safety

- Default to bounded, read-only checks of public surfaces.
- Obtain explicit authorization before accessing authenticated or private systems, running high-volume crawls or broad automated requests, inspecting production configuration, joining warehouse or log data, or performing a test that could affect service.
- Respect access controls, robots directives and published policies as applicable, plus agreed rate and concurrency limits. Never bypass a control.
- Collect only data needed for the audit. Do not collect unnecessary personal data.
- Redact credentials, tokens, cookies, personal data, private paths, and sensitive raw exports from working notes and reports.
- Stop and re-scope when the site becomes unstable, scope expands unexpectedly, authorization is uncertain, or a check could create user impact.

## Focused Diagnosis

Use for one symptom, URL set, template, or search behavior.

**Minimum evidence**

- The reported symptom, first observed time, and expected behavior.
- At least one affected URL and, where possible, one unaffected comparator.
- Current HTTP response and relevant response headers for the sample.
- The page source or rendered result required to test the leading hypothesis.

**Dependency path**

First reproduce the symptom and define its boundary: URL, template, locale, device, crawler, and time window. Then test only the layers needed to distinguish the hypotheses, in order:

1. Test discovery paths, crawl reachability, status behavior, robots controls, rendering when relevant, and indexability.
2. Check canonical selection, redirect integrity, host consistency, and other site-integrity signals.
3. Check measured performance and mobile experience when they could explain the symptom.
4. Compare page relevance and search intent across the smallest meaningful affected and unaffected sample.
5. Compare content quality and internal discovery across that sample.
6. Evaluate authority or market explanations only when direct evidence for them exists.

**Conditional checks**

- For an indexing symptom, request URL inspection, sitemap state, and recent crawl evidence if accessible.
- For a ranking or traffic symptom, segment by query, landing page, device, country, and date; inspect the current live result set and all audited-site URLs competing for the query, then separate demand changes, intent mismatch, and cannibalization from technical causes.
- Turn lower-confidence relevance hypotheses into measurable experiments with a target query and page, baseline, success measure, review window, and rollback condition. Prioritize them only after higher-confidence dependency blockers.
- For a rich-result symptom, validate the rendered structured data and the feature-specific eligibility rules.
- Apply the site-type routing below when the affected surface matches it.

**Stop when**

- A verified upstream cause explains the observed scope and has a testable completion condition.
- Available evidence disproves the reported symptom.
- The next distinction depends only on unavailable private data or a capability that is not present; record the competing hypotheses and exact evidence request as a separate limitation.

**Private or specialized evidence**

Search performance and inspection exports, analytics, server logs, deployment history, rank tracking, full browser rendering, field performance data, and large-scale crawling may be required. Their absence is a limitation, not proof of a defect.

## Page Audit

Use for one representative URL and its search purpose. A page audit does not establish site-wide prevalence.

**Minimum evidence**

- Final URL, status, redirect path, headers, and source HTML.
- Rendered main content when client-side behavior affects what users or crawlers receive.
- Robots directives, declared canonical, indexable link paths, title, primary heading, and visible content.
- The page's intended audience, query need, or conversion role.

**Dependency path**

1. Confirm the URL is discoverable, crawlable, rendered as needed, and eligible for indexing.
2. Confirm the final URL, redirect path, declared canonical, and other integrity signals agree with the intended URL.
3. Assess measured performance and mobile experience after content delivery and rendering are understood.
4. Assess whether the title, primary heading, and page purpose match the intended audience and search need.
5. Assess visible content quality, media alternatives, internal discovery, and applicable structured data against the page content.
6. Assess authority or market signals only when supplied evidence makes them relevant to the page question.

**Conditional checks**

- For a query-focused page question, inspect multiple current live-result competitors and other audited-site URLs appearing or optimized for that query; do not rely on one selected peer to establish intent or cannibalization.
- After upstream blockers, convert lower-confidence relevance hypotheses into prioritized experiments with a baseline, measurable outcome, review window, and rollback condition.
- Inspect mobile layout and interaction when content, links, or controls change by viewport.
- Follow the ecommerce, local, international, or JavaScript routing when applicable.

**Stop when**

- Each upstream layer is either verified or explicitly unavailable, every diagnosed finding is page-scoped, and unavailable layers are listed separately as limitations.
- The remaining question is prevalence across templates; route it to a Site Audit instead of extrapolating.

**Private or specialized evidence**

Query and landing-page performance, URL inspection, real-user performance, accessibility-assisted rendering, and feature-specific rich-result testing can confirm conclusions that public page evidence cannot.

## Site Audit

Use for patterns across a property. Define inventory and sampling before diagnosing individual examples.

**Minimum evidence**

- Known hostnames, protocols, locale or market variants, and business-critical templates.
- robots.txt, declared sitemaps, representative navigation paths, and response samples.
- A reproducible URL inventory or a clearly described sample frame.
- At least one sample per important template and state, including successful and failing examples where known.

**Dependency path**

First establish property boundaries, important templates, and the sample frame. Then:

1. Map discovery, crawling, rendering, and indexability through robots rules, sitemaps, internal links, and representative URL states.
2. Group canonical behavior, redirects, host consistency, and other site-integrity signals by template rather than treating URLs as isolated defects.
3. Measure performance and mobile experience by template and user context where data permits.
4. Test representative page relevance, titles, headings, and search-intent alignment.
5. Test content quality, media alternatives, structured data where applicable, and internal discovery patterns.
6. Evaluate authority or market signals only when supporting data exists.

Estimate prevalence from the inspected inventory only; label sample-based projections as inferred.

**Conditional checks**

- Inspect crawl traps, faceted navigation, pagination, or parameter handling when the inventory expands without corresponding useful pages.
- Compare submitted, crawlable, canonical, and indexed sets when private index coverage evidence is supplied.
- Route specialized templates through the site-type checks below.

**Stop when**

- Important templates and property variants have representative coverage, major findings have bounded scope, and dependencies are reflected in priority order.
- Inventory completeness cannot be established; report sampled conclusions and request the smallest missing dataset rather than claiming full coverage.

**Private or specialized evidence**

Complete crawl exports, server logs, Search Console, analytics, backlink data, production configuration, consented field metrics, and warehouse joins may be necessary for scale, history, and business impact. Apply the audit-safety contract before a complete or high-volume crawl and before accessing any private evidence.

## Incident Audit

Use for a sudden loss, migration regression, release-related change, or active indexing emergency. Preserve timestamps and avoid changing several variables before evidence is captured.

**Minimum evidence**

- Incident start window, affected property or segment, and a stable baseline period.
- Deployment, migration, domain, CDN, DNS, or CMS change timeline.
- Current and historical examples of affected and unaffected URLs.
- Available search performance, analytics, monitoring, or log evidence segmented enough to locate the break.

**Dependency path**

First confirm the loss is real, isolate its first visible time, distinguish reporting delay from site behavior, and segment the loss by template, directory, locale, device, and query class. Then:

1. Compare discovery, crawl access, response codes, robots controls, rendering, and indexability before and after the incident.
2. Compare URL mappings, redirects, canonicals, host behavior, and other site-integrity signals.
3. Check performance and mobile-experience regressions in the affected segments.
4. Check whether page relevance or search-intent alignment changed in the incident window.
5. Check content quality and internal discovery changes after upstream layers are resolved.
6. Consider authority, demand, competition, policy, or algorithmic explanations only when evidence exists.

**Conditional checks**

- During a migration, sample old-to-new mappings, redirect destinations, canonical targets, internal links, and sitemap membership together.
- During a release regression, compare generated source, rendered output, headers, and configuration before and after the release.
- During an availability event, preserve edge, origin, and bot-specific observations where authorized.

**Stop when**

- A verified cause matches the timing and affected scope, and a remediation or containment plan has a defined validation check.
- Recovery has a monitored completion condition and no unresolved critical dependency.
- Attribution requires unavailable historical or private evidence; state the last verified layer and do not label an algorithm update as the cause by elimination.

**Private or specialized evidence**

Deployment and configuration history, DNS/CDN logs, server logs, Search Console, analytics annotations, incident monitoring, archived responses, and external change records may be essential. Apply the audit-safety contract before inspecting logs or production configuration, joining data, or running an active incident test.

### Site-type routing

Apply these checks only when the site's business model or delivery architecture makes them relevant.

**Ecommerce**

- Trace category, product, variant, filter, sort, pagination, availability, and discontinued-product states through discovery, canonicalization, and internal linking.
- Verify price, availability, reviews, and identifiers against visible content before assessing product structured data.
- Request feed diagnostics, inventory rules, and faceted-navigation configuration when public pages cannot explain catalog coverage.
- Produce scalable controls for each URL state and keep a separate register of high-risk exceptions that cannot follow the general rule. Name the implementation owner and owning system for every control and exception.
- Define post-change verification before implementation: generate representative URL combinations, then recheck status, robots handling, canonical target, internal links, sitemap membership, and search-engine inspection when accessible.

**Local**

- Verify that each location page represents a real, distinct customer destination or service area and has stable, consistent identity details.
- Check crawlable location discovery, localized content, and applicable organization or local-business markup without assuming markup controls local rankings.
- For multi-location sites, separate network-wide template and entity fixes from market- or city-specific actions. After dependency blockers, prioritize city work by business importance and evidenced search opportunity while retaining each finding's evidence strength.
- When evidence exists, inspect review signals, citation consistency, and local authority or link signals. Record missing profile, citation, or link data as unavailable limitations rather than negative findings.
- Request Business Profile access, local performance data, and listing-management records when accuracy or visibility cannot be verified publicly.

**International**

- Identify stable, crawlable URLs for each intended language or region; treat redirects based on IP or language preference as a separate behavior to test.
- For each sampled locale cluster, verify that alternate annotations include the page itself, link back across variants, use supported language and optional region codes, and resolve to live URLs.
- Confirm canonical signals preserve the intended locale URL and do not contradict the alternate cluster.
- Test locale URL stability across navigation, redirects, parameters, and repeat requests.
- If rendered markup, headers, sitemap alternates, or private coverage data cannot be inspected, record that layer as an unavailable limitation. Do not infer broken international targeting from missing access.
- Consult source notes for supported annotation methods, code syntax, reciprocity, canonical interaction, and locale-adaptive crawling behavior.

**JavaScript-rendered sites**

- Test representative entry pages and deep routes for discovery through robots rules, sitemaps, and crawlable internal links. Check response status, error routes, and soft-404 behavior without relying on the rendered interface alone.
- Compare initial HTML with rendered content for main text, links, titles, descriptions, canonicals, robots directives, and structured data.
- Check whether meaningful URLs and navigation exist without requiring user gestures or transient client state. When the evidence shows fragile client-only delivery, recommend a durable fit such as server rendering, static generation, or server/edge metadata injection.
- Define a repeatable verification matrix across representative templates and routes. For each sample, record raw response, rendered DOM, response status, discoverable links, metadata, and search-engine inspection when accessible.
- Treat renderer access, execution failures, and delayed resources as distinct observations or layers, each assigned a `verified`, `inferred`, or `unavailable` state. Static source alone cannot prove rendered absence or presence.
- Request production rendering logs, error telemetry, or a browser-capable test when public fetching cannot execute the application.
