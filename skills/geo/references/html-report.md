# Standalone HTML Report

Use this contract only when HTML, a shareable or visual report, or a browser-openable deliverable is requested. Produce one script-free file named `{domain-slug}-geo-audit.html` that opens from local disk without a server or network dependency.

## Semantic Parity

Treat the canonical audit record as immutable report data. Before rendering, inventory its scope, evidence states, fixed checks, arithmetic, observations, findings, unavailable-register rows, actions, completion conditions, dependencies, priority/order, limitations, and sources. After rendering, compare the HTML against that inventory field by field.

Do not add, omit, merge, strengthen, soften, summarize away, or reorder conclusions. In particular:

- keep readiness and evidence coverage separate from observed visibility;
- keep findings separate from unavailable-evidence requests;
- preserve every source ID, state, check link, count, denominator, observation condition, action, completion condition, and limitation;
- preserve dependency order, placing evidence requests before remediations that depend on them;
- never manufacture a logo, citation, screenshot, platform observation, source, check, finding, metric, or claim.

## Information Hierarchy

Use the following visible order under the title `Evidence and action`:

1. audited brand/domain, primary mode and modifiers, property/sample boundary, market/language, audit date, and safely selected logo or escaped wordmark;
2. primary constraint and next decision;
3. readiness score and evidence coverage, with numerator/denominator arithmetic and the complete fixed-row trace;
4. observed mention, owned-citation, third-party-citation, answer, and error counts with exact denominators and test conditions;
5. platform/query matrix showing each repetition and keeping unavailable, error, no-answer, no-feature, and brand absence distinct;
6. findings linked to evidence, affected check, action, and completion condition, followed by the separate unavailable-evidence register;
7. citation-source observations and bounded, condition-matched competitor comparison when present;
8. dependency-sequenced roadmap and repeat-test protocol;
9. methodology, source register, unavailable evidence, and limitations.

If a section has no applicable canonical data, label it not applicable or omit the empty presentation block only when omission does not erase a recorded state. Never replace missing values with zero.

## Inert Document Contract

Emit `<!doctype html>` and one `html`, `head`, `title`, and `body`. Author all CSS inline in a single `style` element. Do not include JavaScript, `script`, event-handler attributes, forms, frames, embedded documents, media players, remote fonts, stylesheets, imports, refreshes, preload/prefetch hints, or network rendering dependencies.

Use only these content elements unless an equally inert semantic element is strictly necessary:

```text
html head meta title style body header main section footer nav
h1 h2 h3 h4 p span strong em small
ul ol li dl dt dd
table caption thead tbody tfoot tr th td
figure figcaption img a code pre br hr
```

Use only these attributes as applicable:

```text
lang charset name content viewport class id role aria-label
scope colspan rowspan href title rel src alt width height
```

Forbid `style` attributes, every attribute beginning with `on`, `srcset`, `sizes`, `poster`, `ping`, `download`, `target`, `base`, `object`, `embed`, `iframe`, `svg`, `math`, and unknown elements/attributes. Do not interpolate audited or downloaded CSS, HTML fragments, data attributes, class names, IDs, URLs, colors, or markup.

Escape all untrusted text for its exact context. HTML text requires `& < >` escaping; quoted attributes additionally require quote escaping. Generate class names and IDs internally. Sanitize citation links by parsing URLs and allowing only absolute `http:` or `https:` URLs; serialize the parsed URL, use `rel="noreferrer noopener"`, and render rejected or unavailable URLs as escaped text. Asset `src` values may only be locally generated `data:image/png;base64,...`, `data:image/jpeg;base64,...`, or `data:image/webp;base64,...` from the validated pipeline below.

## Evidence-Based Branding

Inspect the audited site's publicly delivered identity evidence. Record the selected brand name, color/logo source URL or artifact ID, capture date, and rationale. Prefer a canonical header logo, documented identity asset, or consistently used site mark over incidental imagery.

Derive colors only from inspected evidence, then canonicalize each accepted value to a generated six-digit hexadecimal token matching `#[0-9A-Fa-f]{6}`. Check readable foreground/background contrast and use neutral authored report colors when brand colors are unsafe, ambiguous, or illegible. Never paste a remote stylesheet, CSS variable, gradient, filter, or raw color string into the report.

Use a logo only when its decoded pixels visibly match the claimed brand and its content is appropriate for the report. File extension, response header, URL, or signature alone does not establish content identity. If no safe verified logo survives the pipeline, show the escaped brand name as a text wordmark and disclose the asset omission in method/limitations.

## Raster Asset Pipeline

Inspect the complete candidate manifest and each supplied fixture/payload before selecting assets. Process at most 12 candidates and preserve rejection reasons and measurable metadata in the method record. Never hotlink an asset.

Apply these hard limits:

| Limit | Maximum |
| --- | ---: |
| Source bytes per candidate | 8 MiB (8,388,608 bytes) |
| Encoded output bytes per asset | 8 MiB (8,388,608 bytes) |
| Width or height | 4,096 pixels |
| Decoded pixels per asset | 16,777,216 |
| Frames | 1 static frame |
| Embedded assets | 12 |
| Aggregate decoded pixels | 50,331,648 |
| Aggregate encoded output | 32 MiB (33,554,432 bytes) |

Use lower limits supplied by the user or fixture manifest when present; never raise them to these ceilings.

For every candidate, run this order:

1. Fetch through a bounded HTTP(S) request only when permitted. Record final URL, redirects, status, declared media type, and exact source byte count. Abort during streaming once the source-byte limit is exceeded.
2. Before full decode, compare exact bytes against known raster signatures and container structure. Accept only PNG, JPEG, or WebP candidates. Reject CSS/text, HTML disguised as an image, SVG (including external references or scripts), GIF, unknown formats, and mismatched declarations.
3. Parse sufficient trusted decoder metadata to enforce width, height, pixel count, and frame count before allocating a full raster. Reject animated PNG/WebP and every multi-frame asset. Treat malformed lengths, decompression failures, and ambiguous animation state as rejection.
4. Decode with a maintained raster decoder under resource limits. Inspect the pixels to verify that the content is the expected logo or relevant static evidence; do not embed merely because decoding succeeds.
5. Flatten only a verified single frame, remove metadata/profiles/comments, and re-encode through a trusted encoder as PNG, JPEG, or static WebP. Never copy original encoded bytes into the report.
6. Reinspect the re-encoded output for signature, dimensions, pixels, one-frame status, and encoded size. Update aggregate asset count, decoded pixels, and encoded bytes before embedding; reject the asset if any aggregate limit would be exceeded.
7. Base64-encode the safe output and use an allowlisted raster data URI. Record source, selection rationale, original/re-encoded format, bytes, dimensions, frames, and rejection reason for every candidate.

Do not fully decode or re-encode a source that fails byte preflight, signature/container validation, dimension/pixel preflight, or frame validation. Screenshots and answer captures follow the same pipeline. When unsafe or over budget, preserve their ordered evidence as escaped text rather than losing the evidence or embedding active content.

## Authored Presentation

Build a quiet, work-focused report with a constrained reading width, clear typography, visible state labels, and tables designed for comparison. Use semantic headings and table captions. Do not rely on color alone for pass, partial, fail, unavailable, not-applicable, or reported-signal states.

Keep cards limited to genuinely repeated records; do not nest cards. Set stable widths for score blocks and observation counters. Allow long source URLs, queries, IDs, evidence text, and completion conditions to wrap (`overflow-wrap: anywhere`). Place wide tables in a horizontally scrollable authored wrapper while retaining headers and full cell text. Do not truncate canonical content.

Use responsive CSS with explicit breakpoints suitable for desktop and narrow mobile screens. At narrow widths, collapse multi-column layouts, keep the document within the viewport, preserve logical reading order, and maintain touch-readable spacing. Include print rules that avoid clipping, retain source URLs and state text, and do not hide canonical sections.

## Verification

Before delivery, inspect source text or parse the HTML with a standards-aware HTML parser and verify:

- one doctype/document, required structure, and local-file operation;
- no forbidden element, attribute, URL scheme, external request, script, handler, hotlink, remote font, active content, or untrusted CSS;
- every embedded asset passed all per-asset and aggregate checks;
- every canonical field is present exactly once where required, relationships are intact, and priority/order is unchanged;
- readiness and coverage arithmetic reconcile from the displayed row trace;
- observation counts reconcile from displayed records, including total-attempt and answered-only denominators;
- unavailable/error/no-answer/no-feature/absence states remain distinguishable;
- links and text are escaped and every citation anchor is sanitized.

When a browser is available, open the local file and inspect desktop and mobile widths. Check contrast, image decoding, table scrolling, long URLs/queries, wrapping, overlap, clipping, truncation, reading order, and print preview. Recheck arithmetic against visible content. If browser verification is unavailable, perform source/parse and arithmetic checks and state that visual browser verification was unavailable; do not imply it occurred.
