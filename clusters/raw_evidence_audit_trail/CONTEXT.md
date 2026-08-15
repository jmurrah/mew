# Raw Evidence and Audit Trail

- **Cluster ID:** `raw_evidence_audit_trail`
- **Python module:** `raw_evidence_audit_trail.py`
- **Layer:** Cross-cutting provenance infrastructure

Shared rules: [Evidence Contract](../../docs/core/evidence-contract.md).
Shared schema: [Evidence and Lineage](../../docs/schemas/evidence-lineage.md).

## Purpose

Define provenance beneath collection, transformation, clustering, metrics, and
human-readable claims so a reviewer can retrace every result to inspectable
source material. This layer exposes missing, stale, duplicated, restricted, or
weakly linked evidence; it is not evidence that a market gap exists.

## Scope

- Exact retained API/page/import payloads where source policy allows.
- Evidence indexes for search results, public pages, structured API records,
  feeds, and manual imports.
- Stable IDs for runs, requests, fetches, payloads, records, policies,
  transformations, duplicate groups, derived records, clusters, and claims.
- Raw-to-derived, cluster-to-raw, and claim-to-record/span lineage.
- Immutable runs, retrieval events, hashes, staleness, change, deletion, and
  retention events.
- Versioned source-policy registry.
- Explicit failures, nulls, blocked access, partial threads, truncation, and
  unsupported fields.

## Out of Scope

- Market proof, product choice, opportunity scoring, or automatic idea tables.
- Comprehensive archives of the web, reviews, social posts, or deleted content.
- Whole-site crawling, general browser automation, and universal media archives.
- Automated Google scraping, full competitor review histories, permanent Reddit
  archives, closed social sources, or exact search volume as v1 dependencies.
- WARC as required initial storage.
- Duplicating raw payloads into every cluster for directory symmetry.

## Research Unit

This layer does not have a market-signal unit. Its primary unit is one accepted
evidence record linked to one immutable acquisition event, source-policy
version, locator, and retained payload or permitted excerpt.

Every factual claim or derived record must answer:

1. Which exact records support it?
2. What did each source contain when observed?
3. How, when, and under which policy was it acquired?
4. Which transformations produced the value?
5. Which exact spans support language interpretation?
6. What was missing, truncated, duplicated, stale, contradictory, or uncertain?

## Evidence Model

Four layers remain separate:

1. **Acquired payload:** Exact bytes retained unchanged when permitted.
2. **Evidence record:** Inspectable source-native index and context.
3. **Normalized/annotated record:** Derived extraction, cleanup, classification,
   deduplication, and grouping.
4. **Claim/profile:** Human- or machine-written statement linked to records,
   spans, and transformations.

Identity rules:

- Internal IDs never depend only on mutable URLs, titles, names, or handles.
- Source-native IDs remain separate.
- Entity namespaces are stable, collision-safe, readable where useful, and
  filename-safe.
- Exact ID syntax remains unresolved until runner/storage design.

Duplicates remain independently addressable. Assign duplicate groups and state
whether a count uses raw records, canonical content, authors, threads, products,
or another denominator.

## Observable Fields

Shared entity and field contracts live in
[Evidence and Lineage](../../docs/schemas/evidence-lineage.md). Cluster-specific
provenance observations include:

- Exact payload hash, extracted-text hash, bytes, media type, storage status,
  path, and retention/deletion events.
- Requested/final/canonical URL, redirects, HTTP status, headers, source-native
  identifiers, parent/thread relations, dates, native scores, and author state.
- Run parameters, query environment, pagination, provider version, policy
  version, quotas/backoff, counts, failures, and notes.
- Source-visible edits, deletions, changed/unchanged/blocked states, and parser
  failures.
- Manual import path/hash, original URL, contextual excerpt, importer, and
  policy reference.

Never store secrets, credentials, cookies, authorization headers, or personal
session data.

## Derived Fields

- Normalized URLs and dates.
- Extracted text and supporting spans.
- Exact/near-duplicate fingerprints and group membership.
- Staleness under explicit topic-specific rule.
- Changed, unchanged, removed, blocked, or parser-changed observations.
- Record-to-record, record-to-derived, claim-to-record/span, and
  transformation-to-input/output relations.
- Coverage, truncation, policy, and missingness summaries.

Every derived value preserves method, version, timestamp, inputs, outputs,
confidence where relevant, and failure state.

## Analysis

### Context Preservation

- Preserve complete sentences or paragraphs around relevant excerpts.
- Retain titles, roots, parent IDs, nearby text, replies, negation, versions, and
  overlap where needed.
- Preserve contradictory and counter-evidence.
- Store public identity only when permitted and necessary; record hashing,
  redaction, or omission.

### Deduplication

- Keep original hashes and source records.
- Exact and near-duplicate detection operates on derived text.
- The earlier greater-than-95% similarity suggestion remains an unvalidated
  calibration hypothesis.
- Distinguish syndicated copies, cross-posts, quotations, repeat API results,
  and independent similar experiences.

### Staleness and Change

Publication, update, retrieval, and observation times remain separate. Six- to
twelve-month suggestions are not universal; rules must be topic-specific.
Staleness changes review priority, not historical retention.

Re-fetches create new events. Compare response state, headers, payload hash,
extracted-text hash, and source dates to distinguish source change from parser
change.

### Failure Modes

- Untraceable summaries, context loss, duplicate inflation, stale-current
  confusion, search-snippet promotion, missing counter-evidence, one-source
  coverage, cross-platform metric comparison, and hidden policy restrictions.
- Overaggressive deduplication, rigid keywords, short excerpts, top-N sampling,
  policy/API limits, and parser failure can also erase real evidence.

Mitigation is explicit lineage, spans, denominators, dates, coverage, policy,
failures, near-misses, and manual inspection.

## Source Applicability

Recommended first adapters are Brave Search, allowlisted pages, GitHub, Stack
Exchange, Hacker News, RSS/Atom, and manual imports. Apple catalog metadata and
public pricing/changelog pages follow. Restricted or paid sources enter only
after core provenance proves useful.

See [Source and Provider Index](../../docs/sources/index.md). Provider facts are
centralized there and require verification.

Source-native structural requirements remain important:

- GitHub issue/comment and repository relations.
- Stack Exchange question/answer/comment/revision relations.
- Hacker News parent/root trees.
- RSS feed/item relations and incomplete-text state.
- Search request/environment/result relations.
- Apple storefront and catalog scope.

## Guardrails

- Never mutate raw payloads or historical runs.
- Never accept a URL alone as claim lineage when text interpretation matters.
- Link every accepted record to source-policy version active at collection.
- Keep robots, terms, commercial use, storage, attribution, deletion, retention,
  and rate-limit questions separate.
- If full retention is prohibited, store only permitted metadata/context and the
  explicit absence state.
- Deletion requirements override general preservation preference.

## Output Contract

Potential logical artifacts include:

```text
raw_evidence.jsonl
evidence_links.jsonl
duplicate_groups.jsonl
runs.csv
source_registry.jsonl
source_policies.jsonl
transformations.jsonl
```

Large payloads remain referenced immutable files. Shared run storage versus
cluster-local indexes remains undecided. Preferred direction is shared payloads
plus stable cluster references, not copied acquisition.

This layer supplies section 9 provenance for the investigation profile but does
not produce a ninth market signal.

## Open Questions

- Will payloads live in shared run storage, cluster directories, or a hybrid?
- What exact ID convention applies to each entity type?
- What shared runner interface governs acquisition and cluster modules?
- Which domains enter the first webpage allowlist, and who reviews them?
- What retention, truncation, redaction, and hashing rules apply per source?
- How will policy-required deletion preserve downstream lineage safely?
- What transformation manifest records code, rules, taxonomy, parsers, prompts,
  and models?
- When should evidence be shared across clusters instead of copied?
