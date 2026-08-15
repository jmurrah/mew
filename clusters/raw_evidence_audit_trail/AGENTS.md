# Raw Evidence and Audit Trail: Cluster Instructions

- Read `CONTEXT.md` completely before changing this cluster.
- Treat this cluster as provenance infrastructure and evidence-quality guidance,
  not as evidence that any market problem, gap, or opportunity exists.
- Treat supplied specifications and API assessments as planning context. Never
  cite them in `PROFILE.md` as collected market evidence.
- Preserve source payloads unchanged before normalization when source policy
  allows retention. Store normalized records, annotations, and summaries as
  separate derived artifacts.
- Give every accepted record, run, request, fetch, payload, transformation, and
  derived claim a stable identifier appropriate to its entity type. Preserve
  source-native IDs separately from internal IDs.
- Carry raw record IDs and, when relevant, exact supporting spans through every
  transformation. A URL alone is not sufficient lineage for a derived claim.
- Keep facts, extracted fields, deterministic labels, model labels, human notes,
  and summaries visibly distinct. Record method and version for derived values.
- Never overwrite historical runs or silently mutate raw payloads. Record
  corrections, deletion observations, parser changes, and policy changes as new
  events or versions.
- Flag duplicates through lineage. Do not delete or merge away source records;
  repeated publication and independent repetition are different phenomena.
- Preserve query, locale, language, page or offset, rank, timestamp, and provider
  context for search results. Never report a naked rank.
- Keep publication, update, retrieval, and observation times separate. Missing
  dates stay null; do not guess them. Staleness is an explicit derived label, not
  permission to erase evidence.
- Keep raw payloads in referenced files rather than large CSV cells. Record
  path, hash, byte size, media type, and retention status. Never log secrets,
  authorization headers, cookies, or personal session data.
- Require a dated source-policy record for every accepted evidence row. Terms,
  robots rules, commercial use, automated access, storage, attribution,
  deletion, retention, and rate limits remain separate policy questions.
- Default future acquisition planning to Brave search, allowlisted public page
  retrieval, GitHub, Stack Exchange, Hacker News, RSS/Atom, and manual imports.
  Treat all provider access, pricing, quotas, and policies as time-sensitive and
  reverify them before implementation or collection.
- Do not make automated Google SERP scraping, Bing Search API, competitor review
  archives, Reddit archives, closed social networks, exact search volume,
  unofficial Google Trends access, browser automation, whole-site crawling, or
  deleted-content reconstruction MVP dependencies.
- Keep future cluster-specific provenance, validation, and artifact-index logic
  in `raw_evidence_audit_trail.py`. Do not implement acquisition adapters or
  invent a public interface before shared runner and storage contracts exist.
- Maintain all nine `PROFILE.md` sections. Every future factual item must cite
  stable raw evidence identifiers; absent evidence stays explicit.
