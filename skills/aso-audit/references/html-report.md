# Offline HTML ASO Report

Use this reference for every in-scope ASO audit unless the requester explicitly opts out or requests a non-HTML-only result. Deliver one standalone, script-free, locally openable file named `{app-slug}-{store}-aso-audit.html` in the same task as the audit. HTML is the default primary artifact.

## Default Delivery Contract

Generate the file without asking for separate confirmation and without deferring it to a later turn. Complete the underlying evidence and scoring record first, render that exact record into HTML, write the file, run the available structural and visual checks, and return the local path with a concise summary. Do not report the audit complete while the default file is missing.

Unavailable private evidence, a partial public capture, rejected images, missing logo, missing brand colors, or low evidence coverage does not justify postponing HTML. Render unavailable states, neutral brand fallbacks, and inert asset placeholders so the report remains complete within the supported evidence boundary. If local file creation is impossible, state the current blocker and provide the complete report content in the response; do not promise to generate it later.

## Layout B: Evidence And Action Hierarchy

Use a responsive, offline document with restrained inline CSS and browser-default typography as the fallback. At the top, show the app, store, canonical identifier, country/storefront, locale, mode/scope, capture date, and report date. Follow this order:

1. **Executive constraint and next decision.** State the most material evidence limit, what is verified now, and the decision or evidence collection needed next. Do not turn an inference into a performance claim.
2. **Score and evidence coverage.** Show score, assessed earned/assessed max, coverage, assessed applicable max/all applicable max, and unavailable applicable checks. Display `Not scored` when the relevant denominator is zero and `Unassessed` when no applicable surface was assessed. Explain that unavailable checks are excluded from score math but remain in coverage; not-applicable checks are excluded from both.
3. **Inspected assets and evidence.** List public and owner-supplied sources in capture order, including screenshot order, scope, date, evidence state, and render limits. Keep listing observations distinct from query results, private exports, and policy sources.
4. **Findings, actions, and completion.** Use one row/block per evidence-linked partial or fail: ID, state, check, observed impact, action, completion proof, effort, source, and date. Keep a separate unavailable register with requested evidence, why unavailable, and next collection step.
5. **Copy-ready metadata and asset counts.** Provide clearly labeled proposed copy only when supported by evidence. State exact characters, words, screenshots, and assets as observed/proposed counts; never invent policy limits, asset availability, or a compliance verdict.
6. **Roadmap and experiments.** Separate public-surface changes from owner evidence requests. For experiments, state hypothesis, metric, audience/market, window, control/variant, decision rule, and prerequisite; mark an unmeasured result unavailable rather than predicting uplift.
7. **Limitations, method, and sources.** State capture constraints, evidence-state definitions, fixed scoring formula, platform source URLs/retrieval dates, and the official verification path for any unverified time-sensitive policy.

Use the fixed Apple or Google Play card and point trace from the audit. Preserve `verified`, `inferred`, `unavailable`, and `not applicable` exactly; never fabricate rank, conversion, installs, causal attribution, or uplift.

HTML is presentation, not a second audit. Preserve the underlying audit's substantive findings, evidence states, check trace, score, coverage, priority order, actions, completion conditions, limitations, sources, and asset evidence records exactly. Preserve supplied or verified byte counts, dimensions, signature observations, acceptance/rejection decisions, and rejection reasons; render unsafe payload text only as escaped inert text. The presentation cannot add, omit, strengthen, soften, or reorder conclusions.

## Brand And Asset Handling

Brand extraction is evidence-led. Derive a wordmark/text fallback, icon, palette, and screenshot order only from accepted listing evidence. If no acceptable icon is available, render the app name/initials in a neutral text treatment. If no safe colors are observed, use a small neutral canonical palette. Do not invent a logo, product imagery, screenshots, or brand colors.

Never interpolate raw CSS, SVG, HTML, style attributes, font declarations, URLs, or untrusted text into the document. Use only canonicalized safe color values (for example, a validated `#RRGGBB` allowlist) in CSS; otherwise use the neutral palette. Escape all untrusted text for its HTML context. Permit only sanitized `https:` or `http:` citation anchors and validated embedded raster image data URLs; reject `javascript:`, other `data:` URLs, protocol-relative URLs, and unknown schemes.

Embed only a trusted, static, single-frame raster asset as a data URL. Enforce these budgets: source download at most 8 MiB; width and height at most 4096 px each; at most 16,777,216 decoded pixels per asset; trusted re-encoded output at most 8 MiB per asset; at most 12 embedded raster assets; at most 50,331,648 aggregate decoded pixels; and at most 32 MiB aggregate embedded encoded bytes for the whole report.

1. Stream no more than 8 MiB plus one byte; reject an over-limit source before buffering or decoding it fully, and verify the actual byte count.
2. Use a decoder configured with hard memory, dimension, pixel, and frame limits. Inspect signature plus header/frame metadata before full pixel decode. Reject unsupported or mismatched formats, either dimension over 4096 px, declared pixels over 16,777,216, animation, multiple frames, or ambiguous frame metadata. Reserve the asset's declared pixels against the aggregate budget before decoding; abort before expensive decode when any header or report budget would be exceeded. Do not rely on declared content type, filename, extension, or URL, and do not permit decompression bombs.
3. Fully decode only within those enforced limits, then verify the decoded dimensions, pixel count, and single-frame state again. Reject malformed, oversized, animated, multi-frame, HTML-disguised, or SVG inputs. SVG is never embedded, including data URLs.
4. Re-encode accepted pixels through a trusted static raster encoder, strip all metadata, and reject output over 8 MiB. Before embedding, enforce the maximum of 12 assets, 50,331,648 aggregate decoded pixels, and 32 MiB aggregate encoded bytes. Base64 encode only the trusted re-encoded bytes as `data:image/{format};base64,...` for an `<img>`; do not preserve source bytes.

Build the document from authored inert HTML and escaped text only. Semantic headings, paragraphs, lists, tables, `figure`/`figcaption`, `main`, `section`, `header`, `footer`, `details`, and `summary` are allowed. Do not interpolate HTML fragments or raw CSS. Do not allow scripts; injected styles beyond authored inline CSS; event handlers; `iframe`, `object`, `embed`, `audio`, `video`, `source`, or `track`; forms, inputs, buttons, or submission controls; `base`; meta refresh; SVG or MathML; remote stylesheet/font/link resources; or URL-bearing attributes. The only URL-bearing exceptions are sanitized citation anchors and validated embedded raster `img` data URLs. Citation anchors may use sanitized `https:` or `http:` URLs; when `target="_blank"` is used, add `rel="noopener noreferrer"`. Citation links are references, not remote rendering dependencies: never hotlink images or fetch/render remote CSS, fonts, media, or other assets.

When an input is rejected, retain its evidence record and show an inert text placeholder naming the rejection reason; keep the report usable when every visual is rejected. For screenshots, preserve the supplied/listing display order and use text placeholders for missing or unsafe members.

## Verification

The HTML must contain no scripts, injected styles, event handlers, `iframe`/`object`/`embed`, media or form controls, base, meta refresh, SVG/MathML, unsafe image/link schemes, or remote rendering dependencies. It must be script-free, responsive, and open without a server or network connection; sanitized remote citation anchors are allowed.

When a browser is available, visually inspect the generated local file at desktop and mobile widths: confirm readable hierarchy, wrapping, screenshots/placeholders in order, no clipped evidence tables, and no remote rendering dependency. When browser inspection is unavailable, run structural checks for the filename, one HTML document, escaped dynamic text, allowed URL schemes, no remote rendering dependencies, no SVG/MathML, no scripts/event attributes/injected styles, safe data-image URLs only, and score/coverage plus evidence-state sections.
