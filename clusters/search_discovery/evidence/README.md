# Search and Discovery Evidence Artifacts

Store inspectable query-family evidence here. Planning specifications and API
assessments do not belong in this directory as collected evidence.

Expected logical artifacts:

- `raw/`: immutable provider payloads, manual exports, selective screenshots,
  and selective HTML snapshots, each with stable artifact ID and capture
  metadata.
- `queries.jsonl` or `queries.csv`: exact searched queries and environments.
- `suggestions.jsonl` or `suggestions.csv`: autocomplete, related-query, trend,
  keyword-tool, and manual expansion records tied to parent queries.
- `serp_results.jsonl` or `serp_results.csv`: one result per row with provider
  rank/block, classification axes, confidence, notes, and raw IDs.
- `query_summaries.jsonl` or `query_summaries.csv`: derived counts, shares,
  denominators, separate labels, and supporting evidence IDs.
- `keyword_enrichment.jsonl` or `keyword_enrichment.csv`: optional volume, CPC,
  bid, paid-competition, and trend observations.
- `transformations.md` or machine-readable equivalent: formulas, taxonomy and
  rule versions, denominator policy, query-family grouping, and known failures.

Preserve complete raw responses before normalization. Never overwrite raw
records with normalized or summarized data. Keep Google and Brave captures
separate through explicit engine and provider fields.

`PROFILE.md` remains the human-readable summary. Every factual profile item must
link to stable raw evidence identifiers.
