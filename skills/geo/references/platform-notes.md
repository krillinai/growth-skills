# Platform Notes

## Use And Source Discipline

These notes contain only claims needed to interpret access mechanisms and optional discovery artifacts. Treat each claim as limited to its named product, agent, and source scope. Before relying on a time-sensitive rule, open the direct source, verify its title and relevant text rather than status alone, and record a new retrieval date. If the source is inaccessible or no longer supports the claim, mark the rule `unavailable` and do not score from it.

Robots directives express access preferences for the agent and path they address. They do not prove that a fetch occurred, that content was indexed or trained on, or that an answer cited the site. Never transfer a conclusion between ordinary indexing, training collection, automated search/browse retrieval, and user-triggered fetching.

## Current Primary Platform Sources

All pages below were retrieved and their title/content inspected on **2026-07-22**.

| Platform source | Necessary claim | Audit scope and limit |
| --- | --- | --- |
| Google, [AI features and your website](https://developers.google.com/search/docs/appearance/ai-features) | Google states that ordinary SEO best practices remain relevant to AI Overviews and AI Mode, that there are no additional requirements or special optimizations, and that supporting-link eligibility requires a page to be indexed and eligible for a Search snippet. | Applies only to Google Search AI Overviews and AI Mode. It supports checking ordinary Search eligibility; it does not make Schema, an AI-only file, or any optimization mandatory and does not promise appearance or ranking. |
| Google, [Google Crawler (User Agent) Overview](https://developers.google.com/crawling/docs/crawlers-fetchers/overview-google-crawlers) | Google separates common crawlers, special-case crawlers, and user-triggered fetchers; it says common crawlers automatically respect robots.txt and describes user-triggered fetchers as fetches initiated through user actions in tools or products. | Use the category and exact documented agent involved. A Googlebot result does not establish the behavior of a special-case crawler or user-triggered fetcher, and none of these observations alone proves model training. |
| Anthropic, [Does Anthropic crawl data from the web, and how can site owners block the crawler?](https://support.claude.com/en/articles/8896518-does-anthropic-crawl-data-from-the-web-and-how-can-site-owners-block-the-crawler) | Anthropic documents separate agents: `ClaudeBot` for content that could contribute to model training, `Claude-SearchBot` for search, and `Claude-User` for retrieval at a user's direction. | Apply a directive or observation only to the named agent. The page describes intended functions, not proof that a particular URL was fetched, trained on, indexed, or cited. |
| Perplexity, [Perplexity Crawlers](https://docs.perplexity.ai/docs/resources/perplexity-crawlers) | Perplexity documents `PerplexityBot` for surfacing and linking sites in search results and `Perplexity-User` for visits made in response to user actions; it states neither named agent is used to collect content for foundation-model training. | Apply only to the named Perplexity agents and current documented behavior. Allowing either agent does not prove a crawl, inclusion, citation, or visibility result. |

## Mechanism Matrix

| Mechanism | Evidence that can verify it | Evidence that cannot substitute |
| --- | --- | --- |
| Ordinary search indexing | A dated result in the named search product for the exact URL, or attributable index coverage evidence. | A robots rule, another URL's result, a training policy, or an AI answer. |
| Training collection or use | Current provider documentation plus URL-specific attributable collection/use evidence when the conclusion concerns a URL. | Search indexing, a search/browse fetch, a generic user agent rule, or a user-triggered request. |
| Automated search/browse retrieval | A provider-specific fetch log or dated product artifact tied to the named automated search mechanism. | Ordinary indexing, training permission, another provider's bot, or a user-triggered fetch. |
| User-triggered fetch | A dated session or attributable request/fetch record showing a user action and the named fetcher. | Automated crawler behavior, public search indexing, or an untested robots interpretation. |

When URL-specific evidence is missing, report the mechanism `unavailable`. A public result may verify that the exact page appeared in that search capture, while training, provider fetch, and user-triggered behavior remain unavailable.

## Experimental Discovery Protocols

The non-platform source [The `/llms.txt` file](https://llmstxt.org/) was retrieved and inspected on **2026-07-22**. Its title and description call `/llms.txt` a **proposal** for providing website information to LLMs at inference time. This verifies proposal status, not adoption by any platform, crawler use, ranking effect, citation effect, or required implementation.

No current primary platform source is established here for OKF, `/okf.json`, a knowledge bundle, or a mandatory AI-specific discovery file/schema. Their platform support and effect are therefore `unavailable` unless the audit captures a current direct platform source. Inspect supplied artifacts as optional experiments only: status, format validity, contents, date/currentness, and a declared before/after protocol.

An experimental protocol must declare the hypothesis, affected platform/product, exact artifact and version, baseline window, change timestamp, matched query or retrieval conditions, repetitions, outcomes, and stopping rule. Its completion is a dated matched comparison, not publication of the file. Do not award or deduct readiness points for presence, absence, invalidity, or staleness alone; do not turn an industry benchmark into a deduction or promised uplift.

## Prohibited Conclusions

- No crawler permission, Schema type, semantic pattern, protocol, or content format is a ranking or citation factor unless a current direct platform source says so within the stated scope.
- No fixed uplift, citation probability, traffic effect, or competitive advantage follows from a platform instruction, readiness result, benchmark, or artifact deployment.
- No AI-only file or schema is mandatory based on these sources.
- No generic `AI bot` conclusion may replace the named provider, agent, mechanism, path, condition, and date.
- No third-party presence, crawl, index state, training use, answer inclusion, or citation may be fabricated from an expectation or recommendation.
