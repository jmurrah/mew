# Glossary

## Core Terms

- **Investigation:** Bounded research around one problem, job, audience,
  workflow, query, or candidate behavior.
- **Cluster:** One evidence-analysis capability with canonical specification
  under `clusters/<cluster_id>/CONTEXT.md`.
- **Source:** Origin of evidence, such as site, API, feed, marketplace, document,
  or manual import.
- **Provider:** Service or interface used to discover or acquire source material.
  Provider and underlying source can differ.
- **Run:** Immutable, timestamped execution snapshot containing parameters,
  source-policy versions, acquisition events, counts, failures, and artifacts.
- **Raw payload:** Exact acquired bytes retained unchanged when source policy
  permits.
- **Evidence record:** Inspectable index entry connecting internal ID,
  source-native identity, source locator, context, timestamps, policy, and
  payload or excerpt.
- **Raw evidence:** Source observation before interpretive rewriting. It may be
  an evidence record plus referenced raw payload.
- **Source-native ID:** Identifier assigned by source. It remains separate from
  project IDs.
- **Derived record:** Output from normalization, extraction, deduplication,
  classification, clustering, counting, or summarization.
- **Claim:** Factual statement or explicit interpretation in a profile or report.
- **Supporting span:** Exact source text range or preserved excerpt supporting a
  language-based label or claim.
- **Lineage:** Explicit links from claims and derived records to supporting
  inputs, spans, and transformation versions.
- **Discovery record:** Search result, snippet, directory entry, or other pointer
  used to locate potential evidence. It may also document a captured discovery
  surface.
- **Primary evidence:** Hydrated original source or native API record containing
  enough context to support a claim.
- **Adjacent signal:** Relevant observation missing one or more qualification
  elements required by a cluster. It remains reviewable but does not count as
  confirmed evidence.
- **Profile:** One investigation-level, nine-part human-readable synthesis
  assembled from cluster outputs.

## Evidence Scope Terms

- **Direct evidence:** Evidence addressing substantially the same job, behavior,
  product, or claim.
- **Adjacent evidence:** Evidence from a neighboring tool, format, service,
  workflow, or audience whose relationship to target remains explicit.
- **Source-native metric:** Metric preserved with original platform meaning and
  denominator.
- **Sample metric:** Metric computed from bounded, capped, filtered, sorted,
  regional, or incomplete collection.
- **Population metric:** Metric whose denominator and coverage are demonstrated
  to represent stated population or complete filter.
- **Planning context:** Specifications, provider notes, proposed fields,
  thresholds, and architecture ideas. Planning context is not market evidence.
