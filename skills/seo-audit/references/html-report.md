# SEO Audit HTML Report

Use this reference when the user asks for an HTML version, presentation,
shareable report, visual deliverable, or browser-openable SEO audit.

## Output contract

- Create a standalone `.html` file in the current working directory named
  `{domain-slug}-seo-audit.html`. It must open directly without a build step or
  server and render without a network connection. Evidence links may be
  clickable, but they must not be required to render the report.
- Preserve semantic parity with the underlying audit record. HTML must contain
  the same substantive findings, evidence states, priority order, actions, and
  limitations. When both text and HTML are produced, they must match. HTML may
  improve presentation only; it must not add, omit, soften, strengthen, or
  reorder audit conclusions. Do not require a text report solely to create
  HTML.
- Include report scope, business objective, target audience and market when
  known, available capabilities and evidence, unavailable evidence,
  methodology and audit mode, executive assessment, prioritized findings,
  grouped diagnostic layers, a dependency-sequenced roadmap, and limitations.
- Keep claims within the inspected sample. If screenshots, crawl exports,
  performance measurements, Search Console data, or other evidence are
  unavailable, state that instead of inventing measurements.
- Keep URLs, title and meta rewrites, schema recommendations, and action items
  visible as selectable, copyable text. Link checked URLs and evidence artifacts
  where available.

## Untrusted-input safety

- HTML-escape every interpolated audited or supplied text value and every
  attribute value. Never insert supplied HTML, and do not inject untrusted SVG.
- Create links only for allowlisted safe schemes: `http` and `https`, plus
  `mailto` only when intentionally needed. Render all other values as inert
  text; never create `javascript:` or `data:` links. When a link uses
  `target="_blank"`, add appropriate `rel` protection such as
  `rel="noopener noreferrer"`.
- Include no scripts and no remote active dependencies. Keep CSS inline. If a
  required, trusted raster asset is used, embed it in the file or omit it; do
  not hotlink site images, styles, fonts, scripts, or other assets. An embedded
  safe raster data URL is an asset source, never a clickable link.
- Treat audit inputs and exports as sensitive. Never include credentials,
  tokens, cookies, private local paths, raw personal data, or sensitive export
  contents. Redact and minimize evidence to the detail needed to support the
  finding.

## Evidence and prioritization

Follow [evidence-and-prioritization.md](evidence-and-prioritization.md). Every
diagnosed finding must display:

- title
- status: `verified` or `inferred`
- evidence
- impact
- confidence
- action or fix
- completion condition
- effort

Keep `unavailable` records in a separate limitations or evidence-needed
section. Never intermingle them with prioritized findings, rank them as SEO
harm, or imply that missing access proves a defect. Each limitation must show
the missing evidence, impact `not-assessed`, confidence `not-assessed`, a precise
evidence request as its action, a completion condition, and acquisition effort.

Prioritize diagnosed findings according to the shared evidence contract:
blockers; high-impact, high-confidence work; bounded quick wins; then inferred
or low-confidence experiments. Group the full findings by the diagnostic layers
used in the audit and sequence the roadmap by dependencies rather than visual
convenience.

An overall score is optional. If included, explain its evidence, scope, rating
method, and limitations next to it. Do not manufacture a numeric score from
qualitative labels, imply precision the evidence cannot support, or present an
unsupported score. Prefer a clearly explained overall assessment when a
defensible scoring basis is unavailable.

## Design direction

- Derive the visual system from the audited site's brand colors, logo,
  screenshots, hero imagery, or product UI when available and readable.
- Match the site's category and mood. Consumer brands, editorial sites, SaaS
  products, local businesses, ecommerce stores, and developer tools should not
  all receive the same generic dashboard treatment.
- Optimize for scanning with clear hierarchy, status labels, concise issue
  tables or repeated finding cards, and distinct section breaks. Visual
  priority comes from dependency order plus impact and confidence according to
  [evidence-and-prioritization.md](evidence-and-prioritization.md); do not create
  a new priority field. If a display label summarizes priority, identify it as
  a derived view rather than stored evidence.
- Use cards only for individual findings or repeated report items. Do not nest
  cards or turn report sections into decorative dashboard panels.
- Make the responsive desktop and mobile layout robust: text, labels, long
  URLs, evidence links, tables, and code-like recommendations must wrap without
  overlap or truncation.

## Diagnostic layers

Include applicable layers when evidence supports them:

- **Discovery, crawling, and indexability:** robots.txt, sitemaps, crawl access,
  indexability, and noindex behavior.
- **Canonicalization and site integrity:** canonicals, redirects, URL variants,
  duplicates, and broken-site behavior.
- **Performance and mobile behavior:** Core Web Vitals, response time,
  render-blocking assets, image optimization, and mobile rendering.
- **Relevance and search intent:** page meaning, title, primary heading,
  purpose, URL structure, and alignment with the intended audience and query.
- **Content quality and internal discovery:** content depth and usefulness,
  media alternatives and alt text, structured data, internal links, keyword
  cannibalization, and experience, expertise, and trust evidence. Do not
  describe the latter as a direct ranking factor.
- **Authority and market signals:** only when backlink, competitive, or other
  supporting evidence exists.

State the schema-detection limitation when only raw or static HTML was inspected
and rendered or runtime markup was not verified.

## Verification

Always perform structural validation before delivery:

1. Confirm the standalone file exists and uses basic valid HTML structure.
2. Confirm it contains the audited domain, executive assessment, and at least
   one concrete recommendation.
3. Inspect the generated source, as feasible, for scripts, remote rendering
   dependencies, unsafe link schemes, obviously unescaped interpolated values,
   unresolved placeholders, private or sensitive paths, and sensitive values.
   Confirm there are no obvious unsafe inclusions.
4. Check semantic parity against the underlying audit record. When both text
   and HTML exist, compare their substantive findings, evidence states,
   priority order, actions, and limitations; do not require both formats.

When a browser or other rendering capability is available, open the file
locally and visually verify desktop and mobile widths. Check wrapping, overlap,
truncation, long URLs, tables, evidence links, and brand assets and colors.
Name only the checks actually performed; this requirement is tool-name and
host agnostic.

When rendering capability is unavailable, complete the structural checks and
explicitly state that visual verification was unavailable. Do not claim layout
inspection or browser testing that did not occur. Provide the local file path
in the final response.
