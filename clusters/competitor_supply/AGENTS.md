# Competitor and Supply Evidence: Cluster Instructions

- Read `CONTEXT.md` completely before changing this cluster.
- Treat the research unit as a query-conditioned supply snapshot: one exact job,
  one search surface, one locale, one capture time, and its visible results.
- Keep normalized products separate from source-surface observations. Preserve
  every source record behind product identity resolution and query summaries.
- Never infer that a market is weak because competitors exist, result count is
  low, or one top result is imperfect. Evaluate exact-job fit, freshness,
  complaints, pricing/packaging, breadth, visibility, and incumbent strength.
- Keep product weakness separate from positioning and distribution weakness. A
  strong product with poor copy or rank is not proof of under-supply.
- Store rank as an observed result with surface, locale, timestamp, query, and
  collection method. Never represent API order as universal or personalized
  rank. Preserve sponsorship only when directly visible.
- Label incomplete review metrics as sample metrics. Always retain sampling
  method, denominator, date range, review IDs, and raw records. Never claim a
  complete complaint rate or review history from a bounded sample.
- Preserve visible pricing text and screenshots. Do not invent total cost,
  normalize ambiguous packaging, or compare price across unrelated jobs.
- Treat ratings, review counts, install buckets, stars, forks, and search rank
  as source-specific proxies, not revenue, market share, retention, or demand.
- Derived labels are inspection aids only. `dominance_blocker`, product-gap,
  positioning-gap, distribution-gap, staleness, broadness, and supply-weakness
  candidates must cite raw metrics and evidence IDs; none may choose an
  opportunity for the user.
- Prefer static HTTP capture. Use browser rendering only for material dynamic
  content or proof screenshots. Hash preserved artifacts and record parser or
  adapter versions for brittle sources.
- Keep access methods, quotas, prices, policies, and provider availability
  dated. Reverify them before implementation or collection.
- Keep supplied specifications and API notes as planning context. They are not
  collected market evidence and must never appear as such in `PROFILE.md`.
- Keep future collection, normalization, and annotation logic in
  `competitor_supply.py`. Do not invent its public interface before the shared
  runner contract exists.
- Maintain all nine `PROFILE.md` sections. Every future factual profile item
  must cite stable raw evidence identifiers.
