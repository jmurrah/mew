# Raw Evidence and Audit Trail Artifacts

Store inspectable evidence indexes for this cluster here. Supplied planning
specifications and API assessments do not belong here as collected evidence.

Future logical artifacts may include:

- `raw_evidence.jsonl`: evidence records with stable IDs, locators, timestamps,
  policy IDs, payload references, extraction state, and source-native context.
- `evidence_links.jsonl`: typed links from claims and derived records to raw
  records, supporting spans, and transformation IDs.
- `duplicate_groups.jsonl`: exact and near-duplicate group membership without
  deleting original records.
- `runs.csv` or run manifests: immutable run times, parameters, source-policy
  versions, counts, and failures.
- `source_registry.jsonl` and `source_policies.jsonl`: versioned source access,
  storage, attribution, deletion, retention, rate-limit, and review decisions.
- `transformations.jsonl`: input IDs, output IDs, methods, versions, timestamps,
  confidence where relevant, and failures.

Large raw payloads should remain in referenced immutable files with SHA-256,
byte size, media type, storage status, and retention events. Do not place
secrets, credentials, cookies, or personal session data in evidence artifacts.

Final shared storage ownership remains undecided. Do not duplicate shared raw
payloads into this directory if stable cross-cluster references can preserve
traceability.

`PROFILE.md` remains the human-readable summary. Every future factual item must
link to stable raw evidence identifiers.
