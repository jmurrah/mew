# Dissatisfaction and Complaint Evidence

- **Cluster ID:** `dissatisfaction`
- **Python module:** `dissatisfaction.py`
- **Layer:** Market evidence

Shared rules: [Evidence Contract](../../docs/core/evidence-contract.md).
Field catalog: [Cluster Records](../../docs/schemas/cluster-records.md#dissatisfaction).

## Purpose

Determine whether users repeatedly report specific failures in current products.
Preserve enough source, product, date, text, workflow, consequence, and coverage
context for manual inspection. Negative sentiment alone is insufficient.

## Scope

- Complaint-bearing reviews, issues, discussions, and public support records.
- Product/source snapshots containing displayed ratings, rating distributions,
  written-review counts, versions, updates, and source mechanics.
- Concrete failures, blocked outcomes, affected workflows, missing/removed
  features, consequences, and public response behavior.
- Complaints inside positive or high-star records.
- Theme recurrence within and across products, sources, windows, and releases.
- Explicit statements about switching, cancellation, uninstall, refund, or
  willingness to pay.
- Representative supporting and contradictory records.

## Out of Scope

- Satisfaction prevalence, silent churn, retention, conversion, refund, or
  uninstall rates.
- Verified willingness to pay inferred from text.
- Fake-review determination or automatic anomaly-based exclusion.
- Causal claims from temporal proximity to an update.
- Complete support-quality or resolution claims from public replies or closure.
- Cross-platform reviewer identity.
- Complete lifetime review coverage without demonstrated pagination.
- Global/multilingual comparison in initial planning; default is US English.

## Research Unit

One complaint evidence unit is one source-native review, issue, discussion post,
or public support record with stable identity, source, product, date, text, and
collection metadata.

A useful complaint needs both:

1. A complaint theme.
2. A specific problem object, workflow, capability, consequence, or blocked
   outcome.

One evidence unit can have several theme-tag rows without becoming several raw
complaints.

## Evidence Model

Maintain four linked levels:

1. Evidence units.
2. Theme rollups.
3. Product/source snapshots.
4. Cross-product comparisons over an explicitly defined competitor set.

### Specificity

| Score | Meaning |
|---:|---|
| 0 | Pure negativity without inspectable object |
| 1 | Complaint theme only |
| 2 | Theme plus affected object or flow |
| 3 | Theme, object, and consequence or context |
| 4 | Theme, object, consequence, and reproducibility detail |

Low-specificity records remain preserved and reviewable. They are not silently
discarded.

### Complaint Taxonomy

- Missing feature, category-baseline gap, or removed feature.
- Update regression.
- Reliability, crashes, performance, sync, and network failures.
- Data loss, restore failure, duplication, or overwrite.
- Login, lockout, verification, and recovery.
- UX, complexity, onboarding, excess steps, or hidden actions.
- Pricing, subscription, hidden charge, trial, cancellation, and refund.
- Ads by frequency, placement, timing, interruption, and secondary harm.
- Public support response or escalation failure.
- Privacy and trust.
- Compatibility, integration, export, API, and portability.
- Content or domain fit.

Frequency and harm remain separate. Suggested consequence labels include
annoyance, friction, blocked task, lockout, data loss, money loss, and
abandonment.

Solvability is a derived review aid: `directly_solvable`, `product_tradeoff`,
`business_model_pain`, `external_or_domain_inherent`, or `unknown`. It never
automatically excludes evidence.

## Observable Fields

- Evidence, source, product, snapshot, and collection-run IDs.
- Stable source-native record ID, source/product URLs, country, language, dates,
  title, text, star rating, public author, visible version/device/OS when explicit.
- Developer or maintainer reply presence, date, and text.
- Source-native helpful votes, reactions, comments, labels, and state.
- Displayed/lifetime rating kept separate; total ratings/reviews; histogram;
  current version and update date.
- Query, sort, pages, requested/returned counts, pagination, oldest/newest record,
  access type, raw snapshot path/hash, errors, and coverage scope.
- Explicit switching, uninstall, cancellation, refund, payment, and value
  statements.

Allowed coverage includes `complete_population`, `complete_for_filter`,
`recent_window`, `page_limited`, `sample`, and `unknown`.

## Derived Fields

- Complaint presence, specificity, theme/subtheme, problem object, affected
  workflow, consequence, harm, and workaround presence.
- Missing/removed feature, pricing surprise, forced subscription, refund,
  intrusive ads, UX, bugs, data loss, lockout, support, privacy, and integration
  flags.
- Solvability estimate/reason/confidence and manual verification.
- Product/source/theme/window counts, rating distributions, first/latest dates,
  sampled trends, and possible post-update spike.
- Sample complaint and specific-complaint ratios.
- Public response count/rate.
- Cross-product recurrence and representative evidence IDs.

Use `possible_post_update_spike`, not causal wording. Use `public_response_rate`,
not total support response. Use `stated_*` fields for behavior claims.

## Analysis

### Time and Rating Context

Support bounded 30-, 90-, and 180-day windows. Lifetime claims require complete
coverage. Preserve raw dates and possible release-linked windows, suggested as
14 days before/after release.

Written-review density is valid only with trustworthy rating and written-review
denominators. Preserve high-star complaint clusters and rating/text mismatch
flags without implying fraud.

### Provisional Signals

- **Weak dissatisfaction:** 5 useful complaints in 90 days, or 15% useful
  complaints in retrieved coverage, plus one three-mention theme.
- **Medium:** 12 useful complaints, 25% useful complaints, 50% specific, and one
  five-mention theme.
- **Strong:** 25 useful complaints in 90 days or 10 in 30 days, 35% useful,
  60% specific, and one severe or high-priority eight-mention theme.
- **Strong gap candidate:** Strong dissatisfaction plus cross-product recurrence,
  180-day persistence, or high displayed rating masking recent complaints.

These are unvalidated triage hypotheses. Population ratios require complete
denominators; otherwise use `sample_*` names.

### Failure Modes

- Generic anger, off-topic disputes, old fixed complaints, and one-time outages.
- Bought, coordinated, brigaded, duplicated, or syndicated reviews.
- Vocal minorities and self-selection.
- Silent dissatisfaction absent from public text.
- High-star complaints missed by low-rating filters.
- Country, reset, moderation, deletion, or access mechanics hiding records.

Never store `fake_review_flag`; use `suspicious_review_pattern_flag` with raw
support and no automatic exclusion.

## Source Applicability

Phase 1A favors Mozilla Add-ons and GitHub. Phase 1B adds bounded Google Play and
Apple samples. WordPress.org, Stack Exchange, Hacker News, and Trustpilot are
later or supplemental. See
[Marketplace Providers](../../docs/sources/providers/marketplaces.md),
[Community Sources](../../docs/sources/providers/communities.md), and
[Restricted Sources](../../docs/sources/providers/restricted.md).

Mozilla may support complete-filter metrics when pagination is exhausted.
GitHub is issue-tracker evidence, not a review population. Mobile competitor
reviews remain country-, sort-, page-, and adapter-bounded.

Research foundations retained for future review:

- <https://link.springer.com/article/10.1007/s10664-021-10065-7>
- <https://cs.uwaterloo.ca/~m2nagapp/publications/pdfs/What-Do-Mobile-App-Users-Complain-About-A-Study-on-Free-iOS-Apps.pdf>
- <https://ieeexplore.ieee.org/document/6624001/>
- <https://xin-xia.github.io/publication/ist211.pdf>
- <https://link.springer.com/article/10.1007/s10664-019-09706-9>
- <https://www.sciencedirect.com/science/article/abs/pii/S0167923617300428>
- <https://researchmgt.monash.edu/ws/files/632550033/629297137-oa.pdf>
- <https://strategyn.com/jobs-to-be-done/>

These sources explain design choices; they are not collected market evidence.

## Guardrails

- Preserve source mechanics and native denominators.
- Keep ratings, text, versions, time windows, and collection coverage separate.
- Preserve nearby contradictions for strong or mixed claims.
- Treat unavailable fields as null.
- Do not infer verified churn, purchase, resolution, or causation.

## Output Contract

Future output should provide source snapshots, complaint evidence units,
evidence-unit/theme rows, product/source/theme/window rollups, and explicit
cross-product summaries. Every aggregate retains coverage and evidence IDs.
Output feeds section 3 of the investigation profile.

## Open Questions

- Should first implementation target Mozilla, GitHub, or both?
- Which store adapter is permitted, current, and maintainable?
- How will contradiction selection and manual verification be stored?
- Should recurring snapshots track review edits and histogram changes?
- Which source-specific thresholds remain useful after observing real data?
