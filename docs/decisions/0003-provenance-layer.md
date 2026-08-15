# Decision 0003: Provenance Is Cross-Cutting

- **Status:** Accepted
- **Date:** 2026-08-15

## Context

`raw_evidence_audit_trail` was shaped like an ordinary market-signal cluster for
directory symmetry. Its real responsibility is infrastructure shared by all
eight evidence investigations.

## Decision

Keep `raw_evidence_audit_trail` as a cluster specification because its domain
logic remains substantial, but document it explicitly as cross-cutting
provenance infrastructure. Do not require it to produce a ninth market signal.

## Consequences

- Stable IDs, payload hashes, immutable runs, lineage, source policies,
  missingness, deletion, and staleness apply across clusters.
- Shared payload storage versus cluster-local ownership remains open.
- Cross-cluster reuse must use stable evidence references rather than copied
  acquisition.
