# Evidence Contract

## Core Rule

Every factual statement, count, label, cluster membership, and summary must be
traceable to inspectable source material. Unsupported derived claims must never
be presented as collected facts.

## Raw Evidence

Preserve source-native data before normalization when policy allows. Every
accepted record needs:

- stable internal evidence ID;
- source-native ID when available;
- source and canonical URL or another durable locator;
- publication, update, retrieval, and observation times when available;
- exact excerpt or payload reference;
- query, locale, pagination, rank, and environment when applicable;
- source-native metrics with their native meanings;
- acquisition method, run, source-policy version, and collection status;
- raw payload path, media type, size, and hash when retained.

Unknown values remain null. A missing field is not zero.

## Derived Evidence

Normalized fields, classifications, duplicate groups, cluster memberships,
metrics, summaries, and profile prose are derived records. Preserve:

- every supporting raw record ID;
- exact supporting spans for language-based claims;
- transformation or rule name and version;
- model and prompt version when a model is used;
- classification method, confidence, and manual-review state;
- denominator, sample window, and coverage scope for every aggregate;
- missing inputs, contradictions, and known limitations.

Models can organize evidence. They cannot replace it.

## Discovery and Hydration

Search results, snippets, directories, and provider previews can discover a
source or document a captured search surface. They do not establish a full
source claim when surrounding context matters. Hydrate the accessible original
page or native API record before counting it as primary problem, workaround,
complaint, paid, or policy evidence.

## Source-Native Metrics

Do not combine unlike metrics into a universal engagement or traction score.
Votes, reactions, views, replies, ratings, reviews, installs, users, stars,
forks, and rank retain platform-specific definitions and denominators.

Population language is allowed only when collection proves the denominator and
coverage. Otherwise name metrics as samples and record collection bounds.

## Missingness and Failure States

Distinguish at least:

- `collected`;
- `not_available`;
- `not_supported`;
- `access_denied`;
- `policy_blocked`;
- `collection_failed`;
- `not_collected`;
- `not_applicable`;
- `unknown`.

No public evidence found means only that nothing was observed under recorded
queries, access, sources, and time windows.

## Duplication, Staleness, and Change

- Preserve every source record.
- Group exact or near duplicates; do not delete them during collection.
- State whether counts use raw records, canonical content groups, authors,
  threads, products, sellers, or another denominator.
- Keep publication, update, retrieval, and observation times separate.
- Mark staleness through explicit derived rules; never erase old evidence.
- Re-fetches and policy changes create new observations or versions.
- Record deletion and retention events without retaining prohibited content.

## Policy and Privacy

Every accepted record must link to a dated source-policy review appropriate to
its access method. Access, automated collection, commercial use, storage,
attribution, deletion, retention, and rate limits are separate questions.

Never store secrets, authorization headers, cookies, API keys, or personal
session data in evidence artifacts.

## Human-Readable Output

One investigation-level profile owns the nine evidence dimensions. Each
profile item cites stable evidence IDs and clearly labels inference,
uncertainty, coverage, and counter-evidence. See the
[opportunity profile template](../templates/opportunity-profile.md).

The detailed conceptual lineage contract lives in
[Evidence and Lineage](../schemas/evidence-lineage.md).
