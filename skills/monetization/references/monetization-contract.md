# Monetization Contract

## Minimum Context

Capture these fields independently:

- decision question and primary mode;
- customer segment, job, realized outcome, alternatives, urgency, and purchase constraints;
- user, beneficiary, champion, administrator, buyer, approver, and payer roles;
- product, offer, package, entitlements, limits, add-ons, and service commitments;
- price metric, list price, realized price basis, currency, billing frequency, commitment, included units, overage, minimums, and maximums;
- free, trial, credit, grace, discount, renewal, uplift, upgrade, downgrade, cancellation, refund, tax, fee, payment, and collection rules;
- eligible population, qualified offer exposure, conversion event, cohort, window, cutoff, timezone, and maturity rule;
- product-use, retention, expansion, contraction, renewal, and customer-outcome validation;
- revenue basis: bookings, billings, cash, recognized revenue, recurring revenue, transaction revenue, or another declared basis;
- cost basis: direct service, infrastructure, model or tool, support, success, implementation, payment, incentives, refunds, risk, and variable sales or acquisition costs;
- market, language, locale, product surface, sales motion, channel, and other decision-relevant segments;
- source IDs, owners, capture dates, definitions, populations, and limitations;
- available private fields, purpose, access scope, and retention scope.

Public pricing and product information can verify visible offers, terms, currencies, and claims at a dated capture. It cannot establish private exposure, conversion, realized price, willingness to pay, cost, margin, retention, renewal, expansion, or causal effects.

## Metric Contract

For every reported metric, include:

| Field | Requirement |
| --- | --- |
| Name | Stable, specific metric name |
| Decision | Decision the metric informs |
| Entity | User, account, payer, transaction, subscription, product, revenue, or contribution unit |
| Segment | Customer job and commercial segment |
| Roles | Relevant user, buyer, approver, and payer |
| Eligibility | Inclusion, exclusion, and qualified-exposure rule |
| Event | Exact purchase, payment, renewal, expansion, churn, or value event |
| Numerator | Qualifying entities, revenue, or contribution |
| Denominator | Compatible eligible population, starting base, revenue, or cost base |
| Basis | Bookings, billings, cash, recognized, recurring, transaction, gross, or contribution basis |
| Adjustments | Discounts, credits, refunds, taxes, fees, payment loss, incentives, and cost inclusions |
| Window | Cohort age, commercial period, cutoff, and timezone |
| Currency | Reporting currency, source currency, and FX rule when relevant |
| Maturity | Conversion, renewal, retention, or payback maturity rule |
| Source | Attributable table, artifact, export, contract, or public record |
| Availability | `verified`, `inferred`, `unavailable`, or `not applicable` |
| Limitation | Missingness, censoring, attribution, accounting, selection, or bias risk |

Do not compare metrics whose entity, segment, roles, eligibility, event, basis, adjustments, currency, maturity, window, or source definition differs without making the mismatch the finding.

## Evidence And Data Quality Gate

Check identity and account mapping, duplicate orders, retries, failed payments, refunds, credits, taxes, chargebacks, cancellations, backfills, contract amendments, currency conversion, billing versus finance timing, free periods, sales-assisted attribution, discount approvals, metering versions, one-time versus recurring revenue, cost allocation, cohort maturity, and reconciliation across product, CRM, billing, payment, and finance systems.

Missing data is `unavailable`, not zero. No observed payment is not proof of unwillingness to pay unless eligibility, exposure, payment opportunity, and instrumentation are verified. Preserve the supplied accounting or commercial definition when proposing a corrected one.

## Privacy

Use aggregate or pseudonymous records whenever individual identity is unnecessary. Exclude raw names, email addresses, phone numbers, billing addresses, bank or card data, tax identifiers, credentials, signed links, private contracts, customer payloads, and unrelated transaction history from the deliverable. Do not claim a future deletion, refund, credit, notice, or state change already occurred.

## Output Boundary

If a calculation gate fails, return the contract, known evidence, exact missing fields, reconciliation requirements, and calculation-ready formula. Do not fill the gap with a category benchmark, another company's price, a synthetic willingness-to-pay result, an assumed margin, or a made-up commercial score.
