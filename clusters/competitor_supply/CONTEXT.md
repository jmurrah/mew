# Competitor and Supply Evidence

- **Cluster ID:** `competitor_supply`
- **Python module:** `competitor_supply.py`
- **Layer:** Market evidence

Shared rules: [Evidence Contract](../../docs/core/evidence-contract.md).
Field catalog: [Cluster Records](../../docs/schemas/cluster-records.md#competitor-supply).

## Purpose

Show what visible product supply appears for a specific job and preserve
inspectable evidence of exact-fit strength, mismatch, staleness, complaint
pressure, pricing friction, breadth, dominance, and discoverability.

Weak supply means visible failure to satisfy, scope, package, or reach the
target job and segment. Competitor existence, category crowding, or one weak
result alone says little.

## Scope

- Query-result snapshots from approved app stores, web search, marketplaces,
  and discovery surfaces.
- Product/vendor identity, URLs, categories, early copy, descriptions,
  screenshots, and observed source rank.
- Exact-job evidence from copy, categories, workflow assets, and recent reviews.
- Source-native ratings/counts and bounded review samples.
- Maintenance from updates, releases, changelogs, repositories, issues, and
  buyer-observed breakage.
- Visible pricing, cadence, plan count, free/trial, quote-only, caps, and minimums.
- Query-level fit, breadth, freshness, opacity, complaint, dominance, and
  discoverability distributions.

## Out of Scope

- Build/no-build decisions or one competitor/supply score.
- Revenue, downloads, paid conversion, market share, retention, activation, or
  negotiated pricing.
- Complete review history, universal sentiment, or review velocity from samples.
- Universal/personalized rank or unobserved sponsorship.
- Automated aesthetic judgments.
- Universal total-cost normalization or unrelated-job price comparisons.
- Initial multi-country/multilingual coverage.

## Research Unit

Primary unit is one query-conditioned supply snapshot:

```text
canonical job + exact query + surface + locale + capture time + bounded results
```

Preserve source result observations independently, then resolve normalized
product identity without overwriting conflicting surface facts. Never merge by
display name alone.

## Evidence Model

### Fit

Assess four evidence families independently:

1. Text names job, workflow, or buyer.
2. Category aligns with job.
3. Early screenshots show target workflow.
4. Recent review language describes target job.

Missing evidence remains missing. A provisional mismatch heuristic treats three
failed families as likely mismatch, but requires calibration.

### Gap Types

- **Product-gap candidate:** Weak fit, maintenance, satisfaction, packaging, or
  adoption evidence.
- **Positioning-gap candidate:** Product may work, but copy, category, assets, or
  keywords obscure value.
- **Distribution-gap candidate:** Product may work, but target users cannot find
  it on relevant surfaces.
- **Dominance blocker:** Current, trusted, visible, competitively packaged,
  exact-fit incumbent with low core-job complaint pressure.

These are derived review aids, not definitive diagnoses.

## Observable Fields

- Query, capture-run, result, source-product, normalized-product, vendor, review,
  and evidence-asset IDs.
- Exact query, canonical job, segment, surface, locale, timestamps, method,
  limits, pagination, filters, sort, early-stop reason, and raw artifact/hash.
- Observed rank/block, title, URL, result type, explicit sponsorship, shown
  category/price/rating/count, and snippet.
- Title, subtitle, hero, first 160 characters, description, categories, personas,
  use cases, screenshots, and workflow assets.
- Rating/scale/count, review count/distribution, price/currency, free/IAP,
  version, release/update dates, release notes, changelog, and repository facts.
- Review ID, date, text, rating, language, version, helpful count, developer
  reply, sample type, sample denominator, and date window.
- Pricing-page path, exact visible strings, cadence, free/trial, quote-only,
  plan count, and clearly visible caps or minimums.

## Derived Fields

- Product identity resolution method/confidence and merge/split state.
- Text/category/visual/review intent support and `intent_match_label`.
- Broadness from jobs, use cases, personas, categories, and early-asset focus.
- Staleness from activity dates plus buyer-observed decay.
- Sample complaint themes, core-job blockers, and complaint pressure.
- Query-relative peer price, rating, and review distributions.
- Discoverability, dominance, product-gap, positioning-gap, distribution-gap,
  and query-supply weakness candidates.

Every label stores rule/version, inputs, missing inputs, evidence IDs, and manual
state.

## Analysis

### Provisional Heuristics

- Broadness candidate: five or more jobs/use cases and three relevant categories
  while exact job is absent from early copy/assets.
- Strong staleness candidate: no update for over 365 days plus recent buyer
  evidence of breakage or neglect.
- Medium staleness candidate: over 180 days with little activity or mixed signals.
- Dominance starting point: exact fit, current activity, meaningful peer-relative
  volume, top visibility across surfaces, low core-job complaints, and rating
  around 4.2 or above.

Thresholds are hypotheses. Mature products may update infrequently; tiny perfect
ratings do not prove dominance.

### Review Sampling

Planning defaults per US-English query:

- top 20 Apple results;
- top 20–30 Google Play results;
- top 10–20 web results;
- detailed enrichment for top 10 resolved competitors;
- up to 200 recent mobile reviews;
- up to 100 low-rating reviews where filtering exists;
- optional 50 relevance-sorted reviews;
- first three store screenshots;
- homepage plus one pricing page.

Record truncation, ordering, sampling strategy, missing pages, and early-stop
reason. Never rename bounded review shares as product-wide complaint rates.

### Failure Modes

- Rank/category bias, sample-as-population, and missing-review assumptions.
- Broadness mistaken for failure.
- Visual age mistaken for abandonment.
- Good copy mistaken for product performance or weak copy for weak product.
- Price strings normalized beyond visible evidence.
- Strong niche or B2B products missed through low public review volume,
  localization, adjacent category language, or poor rank.

## Source Applicability

Core candidates are Apple, Google Play, Brave, direct product sites, selective
rendering, and linked GitHub repositories. See
[Marketplace Providers](../../docs/sources/providers/marketplaces.md),
[Search Providers](../../docs/sources/providers/search.md), and
[Community Sources](../../docs/sources/providers/communities.md).

Wayback, DataForSEO, SerpAPI, and OCR are optional. G2/Capterra remain manual;
Product Hunt and paid market intelligence are not core.

## Guardrails

- Rank always includes source, query, locale, time, and method.
- Preserve sponsorship only when directly visible.
- Compare prices only among exact-job peers and keep raw strings.
- Keep product quality separate from positioning and distribution.
- Check for dominance before promoting weakness.
- Use `no public evidence found` or `insufficient coverage`, never `no competitor
  exists`.

## Output Contract

Future output should expose linked competitors, reviews, search results, evidence
assets, and query summaries. Each summary includes bounded counts, distributions,
gap candidates, dominance result, coverage, uncertainty, and evidence IDs.
Output feeds section 5 of the investigation profile.

## Open Questions

- Which canonical job, target segment, and query family seeds first collection?
- How will product merges/splits be reviewed across surfaces and locales?
- How should missing visual/review evidence affect fit without counting as
  failure?
- What real data calibrates rating, staleness, breadth, and review-volume rules?
- Which pricing units can be compared without hiding seat, usage, or annual
  commitments?
