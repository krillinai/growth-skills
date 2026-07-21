# Offline HTML ASO Report

Use this reference only when the requester asks for HTML. Deliver one standalone, script-free, locally openable file named `{app-slug}-{store}-aso-audit.html`; never make HTML the default audit format.

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

HTML is presentation, not a second audit. Preserve the underlying audit's substantive findings, evidence states, check trace, score, coverage, priority order, actions, completion conditions, limitations, and sources exactly. The presentation cannot add, omit, strengthen, soften, or reorder conclusions.

## Brand And Asset Handling

Brand extraction is evidence-led. Derive a wordmark/text fallback, icon, palette, and screenshot order only from accepted listing evidence. If no acceptable icon is available, render the app name/initials in a neutral text treatment. If no safe colors are observed, use a small neutral canonical palette. Do not invent a logo, product imagery, screenshots, or brand colors.

Never interpolate raw CSS, SVG, HTML, style attributes, font declarations, URLs, or untrusted text into the document. Use only canonicalized safe color values (for example, a validated `#RRGGBB` allowlist) in CSS; otherwise use the neutral palette. Escape all untrusted text for its HTML context. Permit only sanitized `https:` or `http:` citation anchors and validated embedded raster image data URLs; reject `javascript:`, other `data:` URLs, protocol-relative URLs, and unknown schemes.

Embed only a trusted raster asset as a data URL after this sequence. Reject a source download over 8 MiB, a decoded width or height over 4096 px, or more than 16,777,216 decoded pixels; apply these ceilings before embedding and before any re-encode.

1. Download bounded bytes with a fixed size limit and verify the actual byte count.
2. Decode with an image decoder, verify dimensions/pixel budget, and validate the file signature/magic bytes against an allowlist of actual raster formats such as PNG, JPEG, or WebP. Declared content type, filename, extension, and URL are not proof.
3. Reject malformed, mismatched, oversized, unsupported, HTML-disguised, or SVG inputs. SVG is never embedded, including data URLs.
4. Re-encode accepted pixels through a trusted raster encoder, strip metadata, then base64 encode the re-encoded bytes as `data:image/{format};base64,...` for an `<img>` only. Do not preserve source bytes.

Build the document from authored inert HTML and escaped text only. Semantic headings, paragraphs, lists, tables, `figure`/`figcaption`, `main`, `section`, `header`, `footer`, `details`, and `summary` are allowed. Do not interpolate HTML fragments or raw CSS. Do not allow scripts; injected styles beyond authored inline CSS; event handlers; `iframe`, `object`, `embed`, `audio`, `video`, `source`, or `track`; forms, inputs, buttons, or submission controls; `base`; meta refresh; SVG or MathML; remote stylesheet/font/link resources; or URL-bearing attributes. The only URL-bearing exceptions are sanitized citation anchors and validated embedded raster `img` data URLs. Citation anchors may use sanitized `https:` or `http:` URLs; when `target="_blank"` is used, add `rel="noopener noreferrer"`. Citation links are references, not remote rendering dependencies: never hotlink images or fetch/render remote CSS, fonts, media, or other assets.

When an input is rejected, retain its evidence record and show an inert text placeholder naming the rejection reason; keep the report usable when every visual is rejected. For screenshots, preserve the supplied/listing display order and use text placeholders for missing or unsafe members.

## Verification

The HTML must contain no scripts, injected styles, event handlers, `iframe`/`object`/`embed`, media or form controls, base, meta refresh, SVG/MathML, unsafe image/link schemes, or remote rendering dependencies. It must be script-free, responsive, and open without a server or network connection; sanitized remote citation anchors are allowed.

When a browser is available, visually inspect the generated local file at desktop and mobile widths: confirm readable hierarchy, wrapping, screenshots/placeholders in order, no clipped evidence tables, and no remote rendering dependency. When browser inspection is unavailable, run structural checks for the filename, one HTML document, escaped dynamic text, allowed URL schemes, no remote rendering dependencies, no SVG/MathML, no scripts/event attributes/injected styles, safe data-image URLs only, and score/coverage plus evidence-state sections.
