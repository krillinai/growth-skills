# Channel Gates

Use this reference to keep permission, account capability, recipient relationship, and fallback specific to the selected channel and context.

## Shared Rule

Permission belongs to the named recipient or cohort, sender, purpose, market, channel, provider/account, and current state. Do not transfer email consent to SMS; international SMS assumptions to China; WeChat Official Account permission to Mini Program subscriptions; WeChat permission to WeCom; or one provider, account, or market rule to another.

Fallback is a new channel decision. Verify independent eligibility, permission, sender/account status, current suppression, routing, and content fit before drafting. Otherwise record fallback `unavailable` and keep the original duty in owner handoff.

## Email

Resolve the real sender, sending account/domain policy, audience eligibility, classification-specific permission basis, current unsubscribe/do-not-contact/complaint/bounce state, and owner-approved cadence. Use only supplied authentication or deliverability evidence. Do not promise inbox placement, delivery, opens, clicks, or benchmarks.

## International SMS

Resolve destination country, recipient number eligibility, provider, route, sender type or number, provider/account registration, classification-specific consent, proof scope, opt-out mechanism, invalid-destination state, quiet hours, and frequency cap. Country and provider routing precede copy.

Do not present a character count, sender type, opt-out keyword, registration rule, or consent rule as universal. Use current direct country/provider sources or supplied owner constraints. A phone number collected for security or account recovery is not marketing SMS permission.

## China SMS

Keep China, Simplified Chinese, `zh-CN`, provider, channel, sender, and classification separate. Resolve the selected provider and account before applying provider requirements. When that provider requires them, record the sender signature, template, account/brand registration, review state, and exact approved scope. Do not borrow another provider's signature or template rule.

Require a real sender, bounded recipient eligibility, attributable purpose and claims, current SMS consent basis, trigger freshness, current unsubscribe/do-not-contact/complaint/invalid-number/withdrawal/suppression state, owner-approved quiet hours and frequency, and a deterministic collision rule.

For Simplified Chinese output, write concise native Chinese. Avoid literal English nurture, win-back, or urgency idioms; artificial familiarity; unsupported scarcity; and improvised opt-out language. Use only the owner/provider-approved opt-out instruction.

## WeChat Official Accounts

Identify whether the account is the relevant Official Account or service-account type. Resolve the exact sender account, current messaging surface/capability, account-policy status, recipient relationship required by that surface, purpose-specific permission, and current stop state. Generic `WeChat account` presence is insufficient.

Do not transfer an Official Account relationship or permission to a Mini Program subscription, WeCom, personal WeChat, or another account. Account capability does not establish that a specific recipient is eligible.

## Mini Program Subscription Messages

Resolve the Mini Program identity, exact template ID and scope, trigger/action that requested subscription, recipient-level result/state, current template status, and whether a one-time or otherwise bounded permission is active, rejected, banned, expired, or consumed. Apply consumed/expired/rejected state before copy.

Template availability does not prove recipient permission. A service duty does not renew a consumed subscription. Do not switch channels automatically.

## WeCom

Resolve the enterprise identity, sending account and member, customer-contact or other selected feature status, enterprise/account policy, member permission, recipient's external-contact relationship and source, purpose-specific consent or permission basis, current complaint/withdrawal/suppression state, and any application authorization required by the selected operation.

Do not infer WeCom permission from personal WeChat, Official Account, or Mini Program status. An external-contact identifier or account capability is not consent for a marketing message.

## WhatsApp

Resolve the WhatsApp Business sender/account, recipient phone source, current opt-in for the named business and purpose, classification, account quality/policy state supplied by the owner, current conversation context, template category and approval when a template is required, destination validity, opt-out/block/report state, and frequency/quiet-hour controls.

Do not transfer email or SMS consent to WhatsApp. Do not infer a usable template, open conversation, account status, or opt-in from a phone number. If current direct policy text is inaccessible, mark the rule `unavailable` and request current owner/platform evidence.

## Localization Integrity

Preserve market, language, locale, channel, classification, sender, facts, consent scope, trigger meaning, opt-out, stops, cadence, and review labels. Rebuild syntax and tone natively; do not translate lifecycle idioms mechanically. Never use localization to soften a stop, broaden permission, add urgency, or turn an unsupported claim into implication.
