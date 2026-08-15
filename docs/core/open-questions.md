# Shared Open Questions

These questions affect several clusters. They remain unresolved intentionally;
do not answer them during unrelated work.

## Runner and Interfaces

- What top-level runner contract invokes cluster modules?
- What public functions, inputs, outputs, errors, and isolation guarantees do
  all clusters share?
- How are collection, normalization, analysis, profile assembly, and manual
  review orchestrated without coupling cluster internals?

## Storage and Ownership

- Should canonical analytical storage use files only, SQLite, DuckDB, or a
  combination?
- Do immutable payloads live in shared run storage, cluster evidence folders,
  or shared storage with cluster-local indexes?
- How do cross-cluster references remain portable without duplicating raw data?
- Where will instantiated investigation profiles live?

## Identity and Schemas

- What collision-safe, readable, filename-safe ID convention applies to runs,
  requests, records, payloads, policies, transformations, clusters, and claims?
- Which conceptual fields in the
  [Cluster Record Catalog](../schemas/cluster-records.md) become required,
  optional, source-specific, or deferred?
- How will schema evolution preserve existing raw-evidence references?

## Human Review

- What workflow handles ambiguous relevance, cluster membership, entity merges,
  duplicate groups, contradictions, low-confidence classifications, and label
  overrides?
- How are reviewer identity, notes, decisions, and later corrections recorded?
- What calibration sets and disagreement thresholds govern rules or model use?

## Policy and Retention

- Who approves sources, credentials, budgets, commercial-use posture, and
  collection methods?
- What default retention, deletion, redaction, hashing, and truncation rules
  apply per source and media type?
- How often are provider price, quota, endpoint, package-health, and policy notes
  reverified?
- How do policy-required deletion events preserve permitted tombstones and
  downstream lineage?

## Initial Scope

- Which market, role, workflow, problem statement, audience, locale, and query
  family should seed the first end-to-end run?
- Which smallest source set proves raw-to-profile traceability before adding
  restricted or brittle sources?
