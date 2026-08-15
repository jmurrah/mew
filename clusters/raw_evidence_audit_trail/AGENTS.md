# Raw Evidence Audit Instructions

- Read `CONTEXT.md` and shared
  [Evidence and Lineage](../../docs/schemas/evidence-lineage.md) completely.
- Treat this cluster as cross-cutting provenance infrastructure, not a market
  signal.
- Preserve immutable payloads, source-native IDs, internal IDs, runs, policies,
  transformations, supporting spans, and lineage.
- Never overwrite historical observations or delete duplicates during
  collection.
- Never log secrets or retain content beyond source policy.
- Keep future provenance logic in `raw_evidence_audit_trail.py` after shared
  runner and storage contracts exist.
