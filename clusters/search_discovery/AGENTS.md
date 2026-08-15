# Search and Discovery Evidence: Cluster Instructions

- Read `CONTEXT.md` completely before changing this cluster.
- Treat supplied specifications and API assessments as planning context, not
  collected market evidence. Never cite them in `PROFILE.md` as proof of demand
  or a gap.
- Use a query family as the research unit. Preserve every exact query,
  suggestion, result, enrichment row, environment field, and capture timestamp
  behind family-level summaries.
- Keep search volume, predicted intent, observed SERP intent, SERP composition,
  trend direction, and domain concentration separate. Never collapse them into
  one opportunity score.
- Describe rankings as results returned by a named provider under a recorded
  locale, language, device, account/personalization state, and capture time.
  Never present one capture as universal search behavior.
- Keep Google and Brave observations separate with an explicit `engine` field.
  Never combine their ranks or use Brave data to make claims about Google.
- Preserve complete provider responses before normalization. Assign stable raw
  evidence IDs; carry them through query, suggestion, SERP-result, enrichment,
  and query-summary artifacts.
- Classify results on separate axes: surface type, direct-solution disposition,
  competitor status, and other flags. Keep `unknown`; never force a label.
- Store classification method, confidence, notes, and supporting raw IDs.
  Deterministic rules come first; NLP or an LLM remains a traceable classifier,
  never evidence.
- Treat autocomplete and related queries as job-language evidence, not volume.
  Parse verbs, objects, audiences, constraints, and journey stage without
  claiming that suggestion order measures demand.
- Treat keyword volume as approximate, nullable enrichment. A zero or missing
  value cannot reject a query family. Paid competition measures ad-market
  competition, not product saturation or organic ranking difficulty.
- Treat Trends data as normalized direction, seasonality, and relative interest,
  not absolute searches. A Trends value of zero is not proof of no demand.
- Use mismatch and demand thresholds in `CONTEXT.md` as calibration hypotheses.
  Expose component metrics and exceptions beside every derived label.
- Preserve raw JSON for every capture. Use screenshots or selective page fetches
  for strong, ambiguous, low-confidence, or manually requested cases; record the
  capture policy.
- Default future MVP collection to US English desktop, one to five manual seed
  queries, no more than 10–20 variants, and top ten Google results per query.
  Expand geography, language, device, crawl depth, or providers only when the
  research question requires it.
- Keep provider availability, prices, quotas, policy, and endpoint claims dated.
  Reverify them before implementation or collection.
- Keep future cluster-specific collection, normalization, classification, and
  profiling logic in `search_discovery.py`. Do not invent its public interface
  before the shared runner contract exists.
- Maintain all nine `PROFILE.md` sections. Every future factual item must cite
  stable raw evidence identifiers; absent evidence stays explicit.
