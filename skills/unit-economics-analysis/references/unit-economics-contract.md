# Unit Economics Contract

Freeze one contract before calculating CAC, LTV:CAC, payback, or portfolio economics. Split the model when one row cannot describe the entities, cohorts, costs, values, or markets being combined.

## Decision And Scope

| Field | Required definition |
| --- | --- |
| Decision | Choice, owner, deadline, reversibility, threshold, and actions this model cannot approve |
| Unit | User, account, payer, legal customer, contract, order, transaction, or marketplace side |
| Cohort | Acquisition and value entry, eligibility, source, product, segment, market, and version |
| Time | Cost period, attribution window, sales cycle, conversion, value horizon, maturity, and finalization |
| Cost | Media, sales, labor, agency, partner, incentive, subsidy, onboarding, shared, and cash scope |
| Value | Revenue, gross profit, contribution, cash, retention, expansion, contraction, and LTV basis |
| State | Observed, estimate, forecast, scenario, target, plan, benchmark, attribution, and incrementality |
| Action | Local analysis allowed now and separately authorized data or operating work |

## Entity And Cohort

Define who is acquired, activates, buys, pays, retains, expands, contracts, churns, returns, produces value, and incurs service cost. Preserve person, user, seat, workspace, account, payer, legal customer, contract, subscription, order, transaction, and marketplace-side hierarchy.

Record identity source, deduplication, anonymous-to-known transition, merge, split, transfer, guest, deletion, fraud, and unknown state. Define cohort origin, attribution or sales window, acquisition eligibility, product and price version, segment, market, channel, and exclusions.

## Time And Maturity

Record event, effective, ingestion, availability, revision, and finalization times; cost recognition and payment; acquisition, activation, conversion, renewal, refund, chargeback, servicing, contribution, and cash windows; observation, maturity, censoring, and tail horizon. A recent cohort is not final economics.

## Cost And Value Bases

Version every cost scope and allocation rule. Keep media, direct acquisition, sales, fully loaded, attributed, incremental, average, and marginal costs separate. Keep bookings, billings, invoices, cash, recognized revenue, GMV, gross profit, contribution, recurring value, and lifetime value separate.

State currency, exchange-rate source and date, constant- or reported-currency policy, tax, discounts, credits, refunds, payment fees, bad debt, hosting, support, fulfillment, servicing, incentive, subsidy, fraud, cost allocation, recognition, and discounting basis.

## Evidence And Compatibility

For every input record source, artifact, field, owner, definition, version, entity, cohort, period, market, cost or value basis, lineage, quality, limitation, and evidence state. Use only `verified`, `inferred`, `unavailable`, or `not applicable`; keep `reported signal` outside that state set.

Before combining inputs align entity, cohort, product, offer, price, segment, market, channel, period, horizon, maturity, currency, cost scope, value basis, attribution, incrementality, forecast status, source version, and owner. Split any mismatch that changes meaning.
