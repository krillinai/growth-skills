# Copy Contract

Use this contract to decide whether to intake or draft, classify claims, and structure every deliverable.

## Deterministic Context Rules

Treat these as blocking facts:

1. product or offer identity plus enough factual truth to describe what is being offered;
2. audience;
3. desired action.

If any blocking fact is missing, return focused intake only. Blocking facts can never be assumptions. Do not create a generic fill-in-the-blank asset, invent a business, choose a broad audience, or guess the conversion action.

User permission to `pick`, `choose`, `make up`, `assume`, or use the `broadest possible` answer does not supply a blocking fact. Treat these instructions as confirmation that the fact is missing, preserve the context that is known, ask for the missing fact, and produce no copy.

For `localization`, target market, target language, and target locale are also blocking. Source language, operator location, domain, currency, or interface language cannot substitute for any of them.

For a channel-specific request, the channel is blocking. A missing numeric channel limit is not blocking when a conservative draft remains useful: state the limit `unavailable`, avoid an exact compliance claim, and request a current platform or owner source.

When all blocking facts are supplied, missing awareness, objections, voice, detailed proof, or format preference may be handled with a bounded assumption-labelled draft only when all of these conditions hold:

- the user requests an immediate draft;
- the assumption is reversible and does not create a product, commercial, legal, regulatory, safety, health, financial, employment, privacy, or performance fact;
- the draft labels each assumption before the copy;
- the draft repeats each assumption under unresolved evidence;
- the draft does not present itself as approved or publication-ready.

Do not assume market, language, or locale for localization. Do not assume a claim source, permission, price, guarantee, award, metric, capability, certification, legal status, or sensitive outcome in any mode.

## Focused Intake Output

Return only:

1. `Mode`: one fixed mode for an in-scope copy intake.
2. `Known context`: supplied decision-relevant facts.
3. `Blocking gaps`: missing facts that prevent truthful copy.
4. `Questions`: the smallest ordered questions that resolve those gaps.
5. `Useful evidence`: supplied or bounded public artifacts that could support the next draft.

Ask product, audience, and action questions first. Ask market, language, locale, channel, constraints, and sources only to the degree they can change the asset. Do not repeatedly request private inputs the user declined.

Do not include `Final Copy`, `Message Hierarchy`, `Claim/Source Ledger`, `CTA Alternatives`, `Unresolved Evidence`, or market notes as a draft package during focused intake. Those sections would imply that the gate passed.

## Draft Output

Return these six sections in this order:

### 1. Final Copy

Label the artifact `Final copy` when no material assumptions remain. Label it `Bounded draft` and list assumptions immediately above it when reversible context is assumed. Match the requested asset and channel; do not expand scope automatically.

### 2. Message Hierarchy

State the ordered decision logic:

- audience situation or job;
- supportable promise;
- proof;
- objection response;
- desired action.

Do not add a layer that the copy does not contain.

### 3. Claim/Source Ledger

Use one row per factual or implied claim:

| Claim ID | Proposed or excluded claim | Evidence state | Signal status | Source ID | Supported scope | Copy decision | Missing proof or limitation |
| --- | --- | --- | --- | --- | --- | --- | --- |

Include excluded claims so the user can see why they are absent. Preserve source names, dates, markets, segments, windows, sample boundaries, permissions, and limitations when supplied.

Use exactly these evidence-state labels:

- `verified`: directly supported by a dated inspectable public artifact or attributable supplied/private artifact within the wording's exact scope.
- `inferred`: a reasoned messaging interpretation that is not itself a product, customer, market, or outcome fact.
- `unavailable`: applicable evidence was not supplied, could not be inspected, is stale, lacks provenance, or does not support the proposed scope.
- `not applicable`: the evidence category or claim is outside the declared product, offer, market, mode, or asset.

Use `reported signal` only as the exact signal-status label for a stakeholder or user statement without an inspectable artifact. Leave evidence state unset for that statement. Do not place `reported signal` in evidence state and do not relabel it verified, inferred, unavailable, or not applicable merely to fill the field.

Use `not applicable` only when the claim or source surface is outside the declared product, offer, market, mode, channel, or asset. For example, an App Store rating is not applicable to a web-only product with no mobile app; it is not merely unavailable.

### 4. CTA Alternatives

Provide two or three alternatives that preserve the same desired action. Vary directness or specificity, not the underlying offer. Do not introduce a free trial, discount, urgency, guarantee, eligibility rule, or next step that was not supplied.

### 5. Unresolved Evidence

List every missing item that could materially strengthen, narrow, or approve the copy. For each item, state the claim it affects and the smallest useful source. Keep private data optional unless the requested claim can only be supported by private evidence.

### 6. Market, Language, Locale, And Channel Notes

State the selected market, language, locale, channel, surface, supplied constraints, unresolved limits, and any risk or handoff note. Keep market, language, and locale as separate fields. Do not claim platform compliance unless checked against a current direct source or supplied owner constraint.

## Claim Decisions

Use the smallest supportable wording. Never turn weak support into strong copy by adding `up to`, `designed to`, `can help`, or similar qualifiers when the underlying fact is still unsupported.

### Metrics, Outcomes, Comparisons, And Superlatives

Require an attributable source with metric definition, relevant population or sample, market or segment, time window, measured value, and material limitations. Preserve the exact scope. A single case cannot become an all-customer result. An internal estimate cannot become an observed outcome. Omit or request evidence for `best`, `fastest`, `leading`, `number one`, universal, or competitor comparison claims without direct substantiation.

### Testimonials And Customer Names

Require attributable wording, the speaker or organization identity, the result's context, and permission for the intended use. If identity, authenticity, context, or permission is unavailable, omit the testimonial and record the gap. Never fabricate a quote, identity, title, logo permission, or release.

### Awards And Certifications

Require the awarding or certifying body, exact title or scope, recipient, date or validity period, and an inspectable source. Do not shorten a narrow certification into blanket approval. Do not use an award or badge whose current status or permission is unavailable.

### Prices, Discounts, Trials, Refunds, And Guarantees

Require current approved terms for the declared market, currency, eligibility, duration, renewal behavior, end date, exclusions, cancellation, refund, and guarantee conditions as applicable. Use only the supplied terms. Never invent `free`, `lowest`, `risk-free`, scarcity, a refund, or a guarantee.

### Capabilities And Compatibility

Require current product documentation, a directly observed product surface, or another attributable source. Match plan, version, market, integration, format, platform, and availability limits. Do not turn partial compatibility into `every`, `all`, `automatic`, or `works with anything`.

### Regulatory, Legal, And Sensitive Claims

Use a current direct primary source for certifications, approvals, mandated wording, legal eligibility, platform policy, or sector rules. Preserve jurisdiction, product category, entity, and validity scope. If current applicability cannot be established, mark it unavailable and request appropriate legal, regulatory, medical, financial, privacy, safety, employment, or policy review.

Never assume or soften unsupported claims about diagnosis, treatment, cure, prevention, guaranteed returns, credit outcomes, safety, legal compliance, discrimination, employment outcomes, or other material risks. A disclaimer does not make an unsupported claim usable.

## Conflicts And Source Priority

Prefer support by provenance and fit, not by magnitude or stakeholder seniority:

1. current direct primary or approved source within the exact scope;
2. attributable dated source with clear method and scope;
3. bounded public observation.

Keep `reported signal` outside this evidence order. It is an input to verify, not support for factual copy and not an evidence state.

Keep conflicting values as separate rows. Do not average them, silently select the larger value, or call the conflict resolved. Narrow copy to the common supported truth or omit the claim until the conflict is resolved.

For voice conflicts, prefer the current approved brand or legal source over an informal stakeholder request. Record the conflict in unresolved evidence when it materially affects approval.
