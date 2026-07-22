# Migration And Validation

## Migration Row Contract

Every unique scoped old URL receives exactly one explicit disposition:

| Disposition | Required fields |
| --- | --- |
| `preserve` | Exact old URL, same destination URL, preservation rationale |
| `redirect` | Exact source, exact target, redirect rationale, target evidence |
| `retire` | Exact old URL, intended response or removal behavior, rationale |
| `hold-needs-evidence` | Exact old URL, missing input, owner, and resolution condition |

`hold-needs-evidence` is an explicit reconciliation disposition, not a deployable redirect. Preserve URLs when page identity, locale, and implementation support preservation. Do not create redirects for cosmetic slug changes alone, and do not send unmatched pages to the homepage without evidence that the homepage satisfies the source intent.

Retain raw URL text and parsed components. A fragment is not sent in an HTTP request and therefore is not a server redirect source; record its intended anchor behavior separately. Query parameters are part of the requested URL semantics until evidence supports preserving, transforming, or dropping them.

## Reconciliation Formulas

Let `O` be unique scoped old URLs and `M` the migration rows.

```text
count(M) = count(O)
count(unique(M.source)) = count(O)
O - M.source = empty
M.source - O = empty
redirect rows with empty target = 0
redirect rows with missing rationale = 0
```

Report every failed equality with the exact rows. Do not announce readiness while a source is missing, duplicated, or outside scope.

For distinct destinations, require destination uniqueness unless multiple sources are intentionally merged into one target. A many-to-one merge is not inherently ambiguous; it becomes acceptable only when the target exists, all source intents are reconciled, locale and market remain appropriate, and each source row contains its own merge rationale.

## Redirect Graph Review

Model each redirect as a directed edge from exact source to exact target and run these checks:

1. **Missing row:** an old URL has no migration row.
2. **Duplicate source:** one old URL has more than one row, even when targets match.
3. **Ambiguous target:** one source has competing targets, target identity is unclear, or a shared target lacks an explicit merge rationale.
4. **Target existence:** target is neither in the approved target inventory nor an explicitly approved external destination.
5. **Loop:** following redirect edges returns to a previously visited URL, including self-loops.
6. **Chain:** a redirect target is itself a redirect source. Resolve to the intended final destination before release unless a documented platform constraint requires otherwise.
7. **Query handling:** each material parameter is preserved, transformed, or dropped through an explicit rule with examples and rationale.
8. **Fragment handling:** source fragments are tracked as client-side intent; validate the destination anchor rather than configuring a fragment-only server redirect.
9. **Locale and market:** source and target market, language, and locale are compared independently; any loss or consolidation needs an explicit approved rationale.
10. **Orphan target:** an approved destination lacks expected navigation, breadcrumb, or internal-link discovery within the bounded target graph, or the proposed target is absent from that inventory.

Keep graph observations separate from search-product claims. A clean mapping does not guarantee crawling, indexing, rankings, traffic, or conversion.

## Navigation And Breadcrumb Parity

For every retained or replacement destination, compare the captured old and proposed new user path:

- relevant navigation surface and label;
- parent and sibling relationships;
- breadcrumb root, intermediate nodes, label, and URL;
- inbound internal links required by declared tasks;
- locale switch or market handoff when in scope;
- destination page identity and response behavior.

Parity does not require identical markup or menu position. It requires an explicit decision about whether the task and relationship remain available. Mark uncaptured old or new behavior `unavailable`; do not assume parity.

## Implementation Ledger

Prepare a local ledger with owner, system, change, dependency, preview artifact, approval state, rollback action, and completion condition. Include only applicable systems:

- route or CMS records;
- redirect configuration;
- navigation data and templates;
- breadcrumb data and templates;
- body and component internal links;
- locale routing;
- canonical, alternate-language annotations, sitemaps, and robots controls;
- monitoring or validation queries.

The planner may specify these changes without executing them. Editing or deploying any listed system needs separate explicit authorization.

## Validation Sequence

### Before release

1. Freeze old and target inventories and rerun reconciliation formulas.
2. Parse every source and target; compare exact components and locale fields.
3. Verify target existence and intended response in an authorized preview environment.
4. Detect duplicates, missing rows, competing targets, loops, chains, unsupported homepage mappings, and unresolved holds.
5. Compare hierarchy, navigation, breadcrumbs, and internal links against the approved plan.
6. Exercise representative query transformations and destination fragments.
7. Record a rollback trigger, responsible owner, configuration backup or reversal, and restoration validation.

### After an authorized release

Validate exact old URLs, final targets, response paths, navigation, breadcrumbs, internal links, locale behavior, query examples, fragment anchors, canonical and sitemap state when authorized, and material error logs or webmaster reports when supplied. Record capture time and inspected count. A sample supports only sample-level conclusions.

Do not claim production validation from a worksheet, local config, staging capture, or inaccessible console. Authentication, Search Console or webmaster actions, deployment, DNS, publishing, and production checks remain separate authorized actions.

## Rollback Record

State the release identifier, trigger conditions, decision owner, reversible configuration or content artifact, reversal steps, expected restoration behavior, and post-rollback checks. If rollback is not technically possible, label that constraint before release; do not omit the risk because timing is tight.
