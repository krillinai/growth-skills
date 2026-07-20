# Source Notes

This ledger supports factual statements used by the audit playbooks. It is not a checklist. Recheck a source when engine behavior, eligibility rules, or web platform thresholds may have changed.

## Crawling and indexing

- **Claim:** Google discovers pages through links and sitemaps, while indexing remains separate from discovery and is not guaranteed by a crawl or sitemap submission.
  Source title: How Google Search Works
  Source: https://developers.google.com/search/docs/fundamentals/how-search-works
  Checked: 2026-07-20
- **Claim:** A robots.txt rule controls crawler access, not whether a URL can appear in search; a blocked URL can still be indexed from other signals, and `noindex` must be crawlable to be observed.
  Source title: Introduction to robots.txt
  Source: https://developers.google.com/search/docs/crawling-indexing/robots/intro
  Checked: 2026-07-20
- **Claim:** Google documents `noindex` as a robots meta tag or HTTP response header directive and must fetch the URL to see it.
  Source title: Block Search indexing with noindex
  Source: https://developers.google.com/search/docs/crawling-indexing/block-indexing
  Checked: 2026-07-20

## Robots and sitemaps

- **Claim:** robots.txt belongs at the root of a protocol and host, uses crawler groups and rules, and may declare sitemap locations.
  Source title: How to write and submit a robots.txt file
  Source: https://developers.google.com/search/docs/crawling-indexing/robots/create-robots-txt
  Checked: 2026-07-20
- **Claim:** A single sitemap is limited to 50 MB uncompressed or 50,000 URLs; larger inventories require multiple sitemaps and can be grouped in an index. Sitemap inclusion is a hint rather than an indexing guarantee.
  Source title: Build and submit a sitemap
  Source: https://developers.google.com/search/docs/crawling-indexing/sitemaps/build-sitemap
  Checked: 2026-07-20

## Canonicalization

- **Claim:** Redirects and `rel="canonical"` are strong canonical signals, sitemap inclusion is weaker, and aligned signals improve the chance that the preferred URL is selected.
  Source title: How to specify a canonical URL with rel="canonical" and other methods
  Source: https://developers.google.com/search/docs/crawling-indexing/consolidate-duplicate-urls
  Checked: 2026-07-20
- **Claim:** Google may select a different canonical from the one a site declares because canonical declarations are signals rather than absolute commands.
  Source title: Troubleshooting canonicalization
  Source: https://developers.google.com/search/docs/crawling-indexing/canonicalization-troubleshooting
  Checked: 2026-07-20

## Redirects and migrations

- **Claim:** Google recommends permanent server-side redirects for permanent URL changes and advises redirecting old URLs to relevant new destinations rather than broadly sending them to an unrelated home page.
  Source title: Redirects and Google Search
  Source: https://developers.google.com/search/docs/crawling-indexing/301-redirects
  Checked: 2026-07-20
- **Claim:** For a site move with URL changes, Google recommends preparing old-to-new URL mappings, updating internal signals, using permanent redirects, submitting the new sitemap, and monitoring both properties.
  Source title: Site moves with URL changes
  Source: https://developers.google.com/search/docs/crawling-indexing/site-move-with-url-changes
  Checked: 2026-07-20

## Core Web Vitals

- **Claim:** The current Core Web Vitals are LCP, INP, and CLS. The documented good thresholds are at most 2.5 seconds for LCP, at most 200 milliseconds for INP, and at most 0.1 for CLS, evaluated at the 75th percentile.
  Source title: Web Vitals
  Source: https://web.dev/articles/vitals
  Checked: 2026-07-20
- **Claim:** Field data reflects real user experiences, while lab tools provide controlled diagnostics; the two can differ because they observe different environments and samples.
  Source title: Why lab and field data can be different (and what to do about it)
  Source: https://web.dev/articles/lab-and-field-data-differences
  Checked: 2026-07-20

## JavaScript and structured data

- **Claim:** Google processes JavaScript pages through crawling, rendering, and indexing; rendering can occur later, so important content and links should not depend on fragile execution.
  Source title: Understand the JavaScript SEO basics
  Source: https://developers.google.com/search/docs/crawling-indexing/javascript/javascript-seo-basics
  Checked: 2026-07-20
- **Claim:** Google can process structured data generated with JavaScript when it is present in the rendered page, but rendering and implementation quality still need validation.
  Source title: Generate structured data with JavaScript
  Source: https://developers.google.com/search/docs/appearance/structured-data/generate-structured-data-with-javascript
  Checked: 2026-07-20
- **Claim:** Correct structured data does not guarantee a rich result; the page and site must also satisfy the relevant feature guidance, quality policies, and technical access requirements.
  Source title: General structured data guidelines
  Source: https://developers.google.com/search/docs/appearance/structured-data/sd-policies
  Checked: 2026-07-20
- **Claim:** Schema.org defines shared structured-data vocabularies, but a vocabulary type alone does not establish search-feature eligibility or ranking treatment.
  Source title: Schema.org FAQ
  Source: https://schema.org/docs/faq.html
  Checked: 2026-07-20

## International targeting

- **Claim:** Google supports alternate-language annotations in HTML, HTTP headers, or sitemaps. Every variant should list itself and the other variants, and corresponding pages should link back to each other.
  Source title: Tell Google about localized versions of your page
  Source: https://developers.google.com/search/docs/specialty/international/localized-versions
  Checked: 2026-07-20
- **Claim:** Google expects an ISO 639-1 language code and allows an optional ISO 3166-1 alpha-2 region code; a region by itself is not a valid hreflang value. `x-default` can identify a fallback URL.
  Source title: Tell Google about localized versions of your page
  Source: https://developers.google.com/search/docs/specialty/international/localized-versions
  Checked: 2026-07-20
- **Claim:** When using hreflang alongside canonicals, Google advises specifying a canonical in the same language when possible.
  Source title: How to specify a canonical URL with rel="canonical" and other methods
  Source: https://developers.google.com/search/docs/crawling-indexing/consolidate-duplicate-urls
  Checked: 2026-07-20
- **Claim:** Google recommends distinct locale URLs and warns that locale-adaptive delivery can be incompletely crawled because Googlebot commonly crawls from US IP addresses without setting `Accept-Language`.
  Source title: How Google crawls locale-adaptive pages
  Source: https://developers.google.com/search/docs/specialty/international/locale-adaptive-pages
  Checked: 2026-07-20

## Local and schema boundaries

- **Claim:** LocalBusiness is a Schema.org subtype of Organization and Place with properties for details such as address, telephone, opening hours, and geographic information.
  Source title: LocalBusiness
  Source: https://schema.org/LocalBusiness
  Checked: 2026-07-20
- **Claim:** Google's local business structured-data documentation describes eligible business details and recommends using the most specific applicable subtype, while search appearance remains governed by Google's structured-data rules.
  Source title: Local business structured data
  Source: https://developers.google.com/search/docs/appearance/structured-data/local-business
  Checked: 2026-07-20

## Ecommerce and local operations

- **Claim:** Google advises preventing crawling of faceted URLs when their content does not need to appear in Search; if those URLs must be crawlable, sites should keep parameter order consistent, return a not-found status for empty combinations, and avoid crawl traps.
  Source title: Managing crawling of faceted navigation URLs
  Source: https://developers.google.com/search/docs/crawling-indexing/crawling-managing-faceted-navigation
  Checked: 2026-07-20
- **Claim:** Google Business Profile guidelines require accurate real-world representation and generally allow one profile per business location; service-area businesses have separate address and service-area rules.
  Source title: Guidelines for representing your business on Google
  Source: https://support.google.com/business/answer/3038177
  Checked: 2026-07-20
