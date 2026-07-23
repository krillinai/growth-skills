# Program Contract

Use this contract for every lifecycle mode. It defines when a blueprint is useful, when copy is blocked, and how to preserve evidence and action boundaries.

## Public-First Intake

Start from public product pages, help content, release notes, pricing, terms, or other inspectable public artifacts. Freeze capture date, scope, publisher, and limitations. Public evidence can support product facts and a program hypothesis; it cannot establish customer eligibility, events, consent, suppression, sender/account status, or performance.

Private CRM, CDP, event, consent, account, or analytics artifacts are optional. Use them only when supplied with purpose, fields, owner, scope, and retention limits. Mark unavailable or declined inputs `unavailable`; do not lower a score, claim absence, or repeat the request. Ask only for the smallest fact needed to clear a copy gate.

## Classification Record

Record classification, accountable owner, decision evidence, unresolved review, and prohibited content before drafting.

| Classification | Allowed scope | Guardrail |
| --- | --- | --- |
| `transactional/service` | Necessary state or action tied to a verified service, account, security, appointment, delivery, or transaction | No offer, discount, cross-sell, win-back, or promotional CTA |
| `marketing` | Optional engagement, activation, retention, reactivation, education, event, promotion, or campaign | Requires independently verified marketing eligibility and channel permission |
| `mixed/uncertain` | Combined or unresolved purposes | Keep visible; produce evidence and review handoff, not combined copy |

Do not turn marketing into service by changing the subject line or adding a disclaimer. A real discount is still promotional. A service duty does not authorize adjacent promotion.

## Final-Copy Gate

Resolve all applicable fields before producing final or sendable copy:

- bounded audience and recipient eligibility rule;
- real sender and accountable organization/account;
- single purpose and resolved classification;
- attributable evidence for every explicit or implied claim;
- trigger/event name, semantics, source, timestamp, freshness window, and current state;
- channel-specific permission/consent basis for the named sender, recipient, purpose, market, and channel;
- current platform, provider, enterprise, and account-policy status;
- required sender, signature, template, business account, or account registration status;
- current opt-out, do-not-contact, complaint, hard-bounce/invalid-destination, consent-withdrawal, sequence, quiet-hour, frequency-cap, and owner-suppression state;
- owner-approved cadence and deterministic collision policy;
- current owner/legal/platform review state.

When any field is unresolved, return no subject line, preview text, SMS body, notification body, chat message, CTA, or copy variant. Return known context, exact gaps, smallest next evidence, useful public findings, and an accountable handoff.

The only exception is the local-review boundary in `SKILL.md`. It requires every operational gate above to be resolved, explicit owner authorization for a review draft, and only final owner/legal/platform review explicitly pending. Never infer those states. Missing review status blocks copy. Use both exact labels `restricted local review` and `not approved for sending`.

## Eligibility And Trigger Record

Define eligibility as a bounded Boolean rule from supplied fields. Include inclusion, exclusion, and stop predicates. Do not substitute a broad persona for recipient eligibility.

For every trigger record:

| Field | Requirement |
| --- | --- |
| Event | Exact supplied name and owner |
| Meaning | What occurred and what it does not prove |
| Time | Occurred-at timestamp and timezone when supplied |
| Freshness | Owner-approved validity window |
| Completion | Event or state that ends eligibility |
| Material change | State changes that invalidate the original context |

Stale, superseded, duplicated, or already-completed events block the original message. Do not invent a replacement program.

## Stop And Suppression Order

Evaluate in this order before copy or fallback:

1. consent withdrawal, opt-out, do-not-contact, complaint, or objection;
2. hard bounce, invalid destination, blocked account, or unusable channel;
3. expired, rejected, banned, consumed, or otherwise exhausted subscription/permission;
4. completed sequence, completed goal, stale event, or material context change;
5. owner suppression, quiet hours, frequency cap, and collision policy.

Record the exact source and timestamp. Missing state is `unavailable`, not clear. An active stop blocks copy for that channel and purpose.

## Evidence Ledger

Use one row per proposed or excluded claim:

| Claim | Evidence state | Source | Supported scope | Copy decision | Limitation |
| --- | --- | --- | --- | --- | --- |

Use `verified`, `inferred`, `unavailable`, or `not applicable`. A stakeholder-only statement may use signal status `reported signal` with evidence state left blank. Missing evidence never proves a claim false; it only prevents its use.

Never invent or silently strengthen customer state, identities, event completion, consent, sender identity, product capabilities, outcomes, metrics, customer names, testimonials, prices, discounts, scarcity, guarantees, approvals, registrations, delivery/open/read/click behavior, or legal conclusions.

## Cadence And Collision

Use only owner-approved rules scoped to market, purpose, mode, classification, channel, recipient, and time zone. Record:

- maximum eligible messages per bounded period;
- quiet-hour window and time-zone source;
- priority order between service and marketing duties;
- deterministic tie-breaker, such as oldest eligible event or named program priority;
- disposition of losing messages: suppress, defer until a supplied window, or owner review;
- sequence completion and re-entry rules.

Do not invent universal timing, touch counts, rates, or benchmarks. If collision rules are absent, report the collision unresolved and do not choose arbitrarily.

## Measurement Capability Ledger

Define only events the supplied stack or inspected platform artifact exposes. Record event name, producer, trigger, timestamp, identifier scope, retention, and availability. Distinguish local eligibility/suppression/draft events from provider acceptance/rejection and downstream business outcomes.

Never imply `delivered`, `opened`, `read`, `clicked`, conversion, attribution, or revenue events exist without supplied capability evidence. Provider acceptance is not delivery; delivery is not reading; reading is not conversion. Mark unavailable events `unavailable` and omit unsupplied benchmarks.

## Privacy And Future Actions

Minimize fields to the declared purpose. Do not expose raw contact identifiers, phone numbers, email addresses, account IDs, signed/private URLs, credentials, or unnecessary event rows in the deliverable. Preserve supplied field, purpose, access, and retention scope.

State deletion, suppression, consent updates, imports, or automation changes as future owner actions until attributable completion evidence exists. Never say an action happened because it is planned.

## Artifact Types

| Artifact | When | Copy allowed |
| --- | --- | --- |
| `program blueprint` | Public context is useful but operational gates are unresolved | No |
| `focused intake` | A small set of facts blocks useful design or copy | No |
| `evidence/handoff` | Active stop, mixed classification, stale event, or owner action is required | No |
| `restricted local review` | All operational gates resolved; only authorized final review remains | Yes, with both exact labels |
| `context-complete local copy` | All gates and required reviews are recorded as resolved | Yes, still local-only |

No artifact authorizes sending or another external action.
