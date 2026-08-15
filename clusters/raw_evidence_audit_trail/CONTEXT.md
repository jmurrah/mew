# Cluster Context: `raw_evidence_audit_trail`

This file models the supplied Raw Evidence / Audit Trail specification and the
practical API-availability assessment. Those inputs are design context, not
collected market evidence. Provider access, prices, quotas, and policies in the
assessment are time-sensitive claims that must be reverified before use.

## Identity

- **Cluster ID:** `raw_evidence_audit_trail`
- **Display name:** Raw Evidence and Audit Trail
- **Python module:** `raw_evidence_audit_trail.py`
- **Purpose:** Define the provenance contract beneath collection,
  transformation, clustering, labeling, metrics, and human-readable profiles so
  a reviewer can retrace every derived statement to inspectable source material.
- **Decision role:** Make research auditable and expose missing, stale,
  duplicated, restricted, or weakly linked evidence. This cluster does not prove
  demand, select an opportunity, or recommend what to build.

## Core Research Question

For every factual statement, count, label, cluster membership, or summary:

1. Which exact source records support it?
2. What did each source contain when collected?
3. How, when, and under which source policy was it acquired?
4. Which transformations produced the derived value?
5. Can a human inspect enough original context to confirm or reject it?
6. What was missing, unavailable, truncated, duplicated, stale, or uncertain?

The intended result is not a universal archive. It is a metadata-first,
policy-aware evidence trail sufficient for local investigation and manual
review.

## Scope

### Included

- Raw search API responses and result records, including exact query,
  environment, rank, URL, title, snippet, request timing, and pagination.
- Selected public webpage responses, redirects, headers, extracted text,
  extraction metadata, and content hashes where access and retention are
  permitted.
- Structured records from official or approved APIs such as GitHub, Stack
  Exchange, Hacker News, RSS/Atom, and optional app catalog metadata.
- Manual imports, including selected review excerpts, exported CSV files,
  screenshots, reports, saved pages, and researcher notes with original-file
  hashes and source context.
- Stable IDs for records, artifacts, runs, requests, fetches, policies,
  transformations, duplicate groups, derived records, and claims.
- Explicit raw-to-derived and raw-to-cluster lineage, including exact supporting
  spans where language interpretation is involved.
- Run snapshots, retrieval events, update observations, content hashes,
  staleness, deduplication, and deletion or retention events.
- Source-policy registry covering access method, terms, robots rules, storage,
  commercial-use status, attribution, deletion, quotas, and review date.
- Human-readable JSONL, CSV, and Markdown indexes plus referenced raw payload
  files.
- Failures and nulls: HTTP errors, parse errors, blocked access, policy blocks,
  missing dates, partial threads, truncation, and unsupported fields.

### Excluded or Deferred

- Market proof, product choice, go/no-go logic, build plans, validation plans,
  automatic app ideas, or a single opportunity score.
- A comprehensive archive of all complaints, reviews, social posts, deleted
  content, webpages, or search-volume signals on the internet.
- Automated Google SERP scraping as an API replacement.
- Bing Search API as a new-project dependency under the supplied assessment.
- Full competitor Apple App Store or Google Play review-body collection.
- Automated archives of G2, Capterra, other commercial review platforms,
  paywalled pages, login-required pages, LinkedIn, or closed social networks.
- Bulk or permanent Reddit post/comment archives without approved access and a
  current policy decision.
- Product Hunt API as a core commercial-research dependency without permission.
- Exact keyword volume, unofficial Google Trends scraping, or generally
  available official Trends API access as an MVP assumption.
- Whole-site crawling, general browser automation, screenshot or media archives,
  app artwork archives, and reconstruction of deleted posts.
- WARC as a required v1 storage format; it remains a later option.
- Raw evidence embedded directly in this `CONTEXT.md` file.

## Canonical Terminology

- **Raw record:** Source observation represented without interpretive rewriting.
  It may reference a separately stored payload.
- **Raw payload:** Exact API response, HTML response, imported file, or other
  acquired bytes retained unchanged when policy allows.
- **Evidence record:** Human-inspectable index row connecting an internal ID,
  source locator, context, timestamps, policy, payload, and extraction state.
- **Source-native ID:** Identifier issued by the source, preserved separately
  from internal IDs because URLs and names may change.
- **Internal ID:** Stable project identifier for one entity. It must remain
  immutable even if metadata, names, URLs, or classifications later change.
- **Run:** Timestamped, non-overwriting execution snapshot with parameters,
  queries, source versions, policy references, counts, and failures.
- **Acquisition event:** One request, fetch, API call, feed read, or manual import
  attempt, including failures.
- **Retrieval event:** Observation of a source or payload at a particular time.
  Re-fetches are new events, not edits to the original event.
- **Transformation:** Reproducible operation that parses, normalizes, extracts,
  deduplicates, classifies, groups, counts, or summarizes records.
- **Derived record:** Output produced from one or more input records or artifacts.
- **Claim:** Human- or machine-written factual statement or interpretation in a
  profile or report.
- **Supporting span:** Exact source text range or preserved excerpt used to
  justify a language-based label or claim.
- **Lineage:** Explicit relationship from a derived record or claim to every
  supporting input ID, relevant span, and transformation version.
- **Duplicate group:** Records with identical or highly similar content that
  remain independently addressable while counting policy is made explicit.
- **Staleness:** Derived, time-aware status based on source dates, retrieval
  dates, topic sensitivity, and an explicit threshold or rule.
- **Source policy:** Dated human-reviewed interpretation of permitted access,
  storage, use, attribution, deletion, and retention for one source and method.
- **Planning context:** Supplied specifications, access assessments, schemas,
  thresholds, architecture ideas, and provider claims. It is not market
  evidence and receives no raw evidence ID.

## Evidence Layers

### 1. Acquired Payload Layer

Preserve exact source responses or imported files before filtering or
interpretation when terms and size permit. Payload files are immutable. At
minimum record hash, byte count, media type, retrieval time, acquisition event,
and storage/retention status.

If payload retention is prohibited or unclear, preserve only permitted metadata
and excerpts. Record that absence explicitly; never imply that a full response
exists.

### 2. Evidence Record Layer

Create one independent JSONL record per source item or meaningful source entity.
Do not force all source types into identical non-null fields. Preserve native
structure such as question-answer-comment relationships, GitHub issue-comment
relationships, Hacker News parent-child trees, and search request-result links.

### 3. Normalized and Annotated Layer

Extraction, canonical URLs, normalized dates, text cleanup, classification,
duplicate detection, and entity tagging belong in derived artifacts. Retain
input IDs, method, software or rule version, timestamp, confidence where
appropriate, notes, and failures. Do not overwrite raw values.

### 4. Profile and Claim Layer

Every factual profile item, metric, cluster membership, or summary cites its
supporting raw record IDs. Language-based interpretations also retain exact
supporting spans. Unsupported or contradictory evidence stays visible.

## Identifier and Lineage Contract

### Required Properties

- One stable internal ID per entity; never recycle IDs.
- Separate namespaces or entity-type prefixes for raw records, runs, requests,
  fetches, payloads, policies, transformations, clusters, and claims.
- Preserve source-native IDs in their own fields.
- Do not make uniqueness depend only on mutable URLs, titles, usernames, or
  repository names.
- Readable source and time components are useful for inspection but are not a
  substitute for collision-safe uniqueness.
- Filename-safe representations must avoid punctuation that breaks paths across
  supported operating systems.

The supplied ideal examples embed source and timestamps in IDs. Exact syntax is
not yet decided. Future design should choose one convention consistently and
document generation, collision handling, and migration.

### Link Types

Preserve explicit relations for:

- run to acquisition event;
- request to result;
- source parent to child or thread to item;
- raw record to payload;
- raw record to source-policy version;
- raw record to normalized record;
- record to duplicate group and optional canonical record;
- derived record to all supporting raw records;
- claim to supporting raw records and spans;
- cluster membership to raw records;
- transformation output to input artifacts and transformation version.

Many-to-many relationships should use JSON arrays or join files rather than
opaque delimited strings when reliable parsing matters. Spreadsheet exports may
use delimited cells as views, not as the only canonical relationship store.

## Common Record Contract

### Required for Every Accepted Raw Record

```text
raw_record_id
run_id
source_id
record_type
acquisition_method
retrieved_at
source_policy_id
```

Every accepted record also needs at least one usable locator:

```text
source_native_id
OR final_url
OR raw_payload_path
OR imported_file_path
```

### Recommended Common Fields

```text
source_native_id
query_id
parent_raw_record_id
thread_raw_record_id
requested_url
final_url
canonical_url
title
snippet
full_text_path
published_at
updated_at
rank
author_display
score
rating
rating_count
raw_payload_path
raw_payload_sha256
raw_payload_bytes
raw_payload_content_type
raw_payload_storage_status
content_sha256
http_status
extraction_status
processing_status
source_policy_id
duplicate_group_id
duplicate_of_raw_record_id
```

`published_at`, `updated_at`, `author_display`, `rank`, `score`, `rating`,
`full_text_path`, and `source_native_id` are nullable. Unknown values stay null;
absence is not silently converted to zero or collection failure.

### Raw Payload Handling

- Keep large JSON, HTML, XML, text, screenshots, and imported files outside the
  primary CSV or JSONL index.
- Reference payload path, SHA-256, byte size, media type, policy status, and
  deletion or retention event.
- Distinguish `raw_payload_sha256` from `extracted_text_sha256`. This separates
  source changes from parser changes.
- Never write authorization headers, cookies, API keys, tokens, or personal
  session data to payloads or logs.
- Compression is allowed only when decompression reproduces original bytes.
- A suggested character cap such as 2,000 is not a universal rule. Preserve at
  least a complete sentence or paragraph around relevant text, record any
  truncation, and let policy and storage design determine source-specific limits.

## Search Evidence Contract

A search result is meaningful only within its request environment.

### Request Fields

```text
search_request_id
run_id
provider
engine
query_text
query_normalized
country
language
device_class
safesearch_setting
requested_result_count
page_or_offset
account_state
personalization_state
requested_at
response_received_at
http_status
api_response_path
api_response_sha256
```

### Result Fields

```text
search_result_id
search_request_id
rank_on_page
absolute_rank
title
display_url
result_url
canonical_url
snippet
result_type
published_or_age_value
source_domain
```

Never report rank without exact query, provider, engine, locale, language,
pagination, device where available, and collection time. Search snippets support
discovery and recorded SERP observations; they should not replace hydration from
an original accessible source when a claim depends on full context.

## Source-Specific Native Context

### Direct Webpage Retrieval

Future retrieval should capture requested and final URLs, redirect chain, HTTP
status, content type and length, ETag, Last-Modified, Cache-Control, retrieval
time, elapsed time, raw-response hash, extracted-text hash, extraction method,
and extraction status.

Fetch selected evidence pages only: product and pricing pages, changelogs,
documentation, public threads, comparisons, and other pages selected for an
investigation. Do not crawl whole sites by default.

Robots permission, terms permission, storage permission, and commercial-use
permission are separate. `robots_allowed = true` never implies permission for
permanent storage, republication, commercial use, or API circumvention.

### GitHub

Preserve repository numeric ID, repository full name, issue number, node ID,
issue URL, title, body, state, author, timestamps, labels, reactions, comment
count, pull-request status, and raw API path. Preserve comment IDs, bodies,
authors, timestamps, reactions, and parent issue relations separately.

GitHub is valuable for feature requests, repeated bugs, workarounds, complexity,
migration demand, abandonment, unanswered issues, and maintenance history. It is
biased toward developer-facing, open-source, and technically engaged users; do
not generalize it to an entire market.

### Stack Exchange

Preserve site, question, answer, and comment IDs; title; body; tags; score; view
count; answer count; answer state; accepted answer; creation and activity dates;
links; owner ID; paging; quota; and returned backoff values.

Question, answer, comment, and revision relationships matter. High-view
unanswered questions differ from low-view unanswered questions, and accepted
answers requiring complex workarounds may be evidence worth separate annotation.

### Hacker News

Preserve item ID, parent ID, root story ID, item type, author, title, text, URL,
score, timestamp, child IDs, descendant count, deleted state, and dead state.
Retain tree structure. Flattened comments without parent relationships can
reverse or erase meaning because replies may contradict parents.

The supplied assessment recommends discovering HN URLs through search and then
hydrating known item IDs through the official API.

### RSS and Atom

Preserve feed URL, feed retrieval event, stable item ID or GUID, item URL,
title, publication and update dates, summary, position, raw feed payload, and
source-policy version. Feed content can be incomplete; record whether full text
was available.

### Apple App Catalog

Optional competitor-supply metadata may include app ID, name, developer, store
URL and country, price and currency, category, rating average and count, version,
release or update date, and description. Store complete returned JSON when
allowed because software fields may exceed generic documentation.

Catalog metadata is feasible under the supplied assessment; competitor review
bodies are not. Provide a manual review URL instead of promising automated full
review collection.

## Practical Acquisition Boundary

### Recommended Core Adapters

The supplied practical assessment recommends these first adapters:

1. `brave_search`
2. `web_page`
3. `github`
4. `stack_exchange`
5. `hacker_news`
6. `rss`
7. `manual_import`

This stack is intended to test whether investigations are useful before solving
hostile, closed, expensive, or legally uncertain sources.

### Dated Provider Assessment

These are supplied planning claims, not independently verified facts:

- Brave Search API was identified as the core inexpensive general-search
  provider, with structured results, its own index, and a small monthly credit.
- GitHub REST API was described as allowing 60 requests per hour
  unauthenticated and generally 5,000 per hour authenticated, with tighter
  search limits.
- Stack Exchange API was described as offering a generally 10,000-request daily
  quota with a registered key, paging, filters, and mandatory backoff handling.
- Hacker News official Firebase API was described as exposing public item trees
  without a documented rate limit.
- Apple iTunes Search API was described as keyless, legacy/archived, and suited
  to catalog metadata, with roughly 20 calls per minute recommended.
- Common Crawl was identified as free but operationally large and deferred to a
  later phase.
- Google Custom Search JSON API was described as closed to new customers with a
  January 1, 2027 transition deadline for existing customers.
- Bing Search APIs were described as retired on August 11, 2025.
- Google Trends API was described as limited alpha access rather than a reliable
  general MVP dependency.

Reverify documentation, price, quota, authentication, storage terms, and
commercial-use status before implementation and at least periodically afterward.

## Restricted, Conditional, and Manual Sources

### Reddit

Do not assume private use for side-income research is noncommercial. Before any
automatic ingestion, confirm approved access, current terms, permitted storage,
deletion handling, and AI restrictions.

Safe MVP default: preserve search query, rank, Reddit URL, result title, result
snippet, and retrieval time; set content capture to manual review only.

If a later policy decision permits limited collection, prefer native IDs,
permalinks, timestamps, subreddit, small contextual excerpts, and removed or
deleted status. Do not build a permanent bulk archive or train models on stored
Reddit content.

### Product Hunt

Treat API as conditional because supplied documentation was assessed as
noncommercial by default. Search-discovered URLs, titles, snippets, and visible
launch metadata may be manually inspected. Obtain permission or clarify use
before API integration for commercial research.

### Review Platforms and App Reviews

Do not promise automated competitor review bodies from Apple, Google Play, G2,
Capterra, or similar platforms. Official app-review APIs generally concern apps
owned by the authenticated developer. Later access may require a paid vendor,
source-specific legal review, or a brittle unofficial scraper.

Manual excerpts are acceptable only with original URL, surrounding context,
import metadata, policy record, and clear limitations.

### Trends and Search Volume

Allow manual Google Trends CSV imports. Preserve file unchanged with terms,
geography, time range, category, and export date. Treat values as normalized
relative interest, not absolute searches.

Do not promise exact monthly volume in v1. Missing or zero volume must not erase
other evidence or prove absence of demand.

## Manual Import Contract

Manual evidence follows the same audit rules as automated evidence. Preserve:

```text
acquisition_method = "manual_import"
imported_file_path
imported_file_sha256
imported_at
entered_by
original_source_url
manual_excerpt
manual_context_note
source_policy_id
```

Useful manual imports may include selected review excerpts, Trends exports,
screenshots, paid reports, exports for apps the user owns, browser-saved pages,
and competitor notes. Import itself does not establish truth or permission;
record source, limitations, and policy.

## Source-Policy Registry

No automated field can conclusively establish lawful access, storage, or reuse.
Maintain a small manually reviewed registry with versioned entries:

```text
source_policy_id
source_id
source_name
source_domain
access_method
official_api
api_documentation_url
terms_url
robots_url
authentication_type
free_quota_description
paid_price_description
commercial_use_status
automated_access_status
full_text_storage_status
excerpt_storage_status
raw_payload_storage_status
required_deletion_handling
required_attribution
rate_limit_policy
retention_days
policy_checked_at
policy_version_or_date
review_status
notes
```

Recommended controlled values include:

```text
commercial_use_status:
  allowed
  prohibited
  permission_required
  unclear
  not_reviewed

full_text_storage_status:
  allowed
  excerpt_only
  metadata_only
  prohibited
  unclear
```

Every evidence record links to the policy version active at collection time.
Policy updates create new versions; they do not rewrite history. If later terms
require deletion, record deletion event, reason, time, affected artifact IDs,
and retained metadata allowed by policy.

## Context Preservation

- Keep full sentences or paragraphs around relevant excerpts; avoid fragments
  that remove caveats, product versions, replies, or negation.
- Preserve titles, question text, thread roots, parent IDs, neighboring text
  windows, and overlap between chunks when needed.
- Store author or username only when permitted and necessary. Record redaction,
  hashing, or omission methods rather than implying identity is available.
- Preserve contradictory and counter-evidence. A collection biased toward only
  supportive examples produces false gaps.
- Source-visible edits and deletions become later observations. Do not promise
  restoration of content never lawfully retained.

## Deduplication With Provenance

- Compute exact and optional near-duplicate fingerprints on derived cleaned
  text, while preserving original hashes and records.
- Ideal specification suggests tentative greater-than-95-percent similarity
  threshold. Treat it as a calibration hypothesis, not fixed truth.
- Keep every source record. Assign `duplicate_group_id` and optionally
  `duplicate_of_raw_record_id`; never delete duplicates during collection.
- Distinguish syndicated copies, cross-posts, quoted text, repeated API results,
  and independent people reporting similar experiences.
- State whether counts use raw records, canonical content groups, distinct
  authors, distinct threads, or another denominator.
- Route near-duplicates and high-impact duplicate groups to manual review.

## Run Versioning and Change Detection

Each run should be immutable and timestamped. Preserve run ID, start and finish
times, code and rule versions when available, queries, parameters, source-policy
versions, source quotas, result counts, failures, and notes.

Never overwrite earlier runs. Re-fetching a URL or repeating a query produces a
new retrieval event linked to prior observations. Compare response status,
headers, payload hashes, extracted-text hashes, and source-visible dates. This
supports changed, unchanged, removed, blocked, and parser-changed states without
pretending any one state is permanent.

## Staleness

Preserve publication, update, retrieval, and observation timestamps separately.
Date provenance and extraction method matter. A date inferred from a page is not
equivalent to a source-native API timestamp.

Ideal specification suggests six- to twelve-month thresholds. Future rules must
be topic-specific and explicit. Mark or de-prioritize stale evidence in a
derived view; do not delete it or silently exclude it. Current-state claims need
an explicit as-of date and recent supporting retrievals.

## Risk of False Positives

- Untraceable summaries may misstate or remove context.
- Duplicate copies may inflate apparent recurrence.
- Old complaints may be presented as current.
- Search snippets may be mistaken for hydrated evidence.
- Missing counter-evidence may make opinions look unanimous.
- One provider, query family, community, or top-ten result set may be mistaken
  for complete coverage.
- Source-native engagement values may be misread across unlike platforms.
- Policy-restricted payload absence may be hidden behind confident labels.

Mitigation: explicit lineage, spans, denominators, dates, duplicate policy,
coverage limits, source-policy status, failures, and manual inspection.

## Risk of False Negatives

- Aggressive deduplication may erase unique voices or niche variants.
- Rigid keywords may miss alternate language.
- Short snippets or truncation may remove decisive sentence.
- Top-N search sampling may miss deeper evidence.
- Policy or API limits may leave important platforms uncovered.
- Failed parsing may be mistaken for absent evidence.
- Required full-text hydration may discard useful metadata-only observations.

Mitigation: conservative filters, visible near-misses, nullable fields, explicit
failure records, manual imports, coverage notes, and inspectable raw artifacts.

## Logical Artifact Layout

Future implementation may use this run-scoped shape:

```text
data/
  runs/
    <run_id>/
      raw/
        brave/
        github/
        stack_exchange/
        hacker_news/
        rss/
        pages/
        manual/
      extracted/
        raw_evidence.jsonl
      indexes/
        search_requests.csv
        source_fetches.csv
        evidence_links.csv
      run.json
  registries/
    sources.jsonl
    source_policies.jsonl
```

This is design guidance, not an implemented path commitment. Shared runner and
repository storage contracts must decide final ownership. Raw payloads should
not be duplicated into every topic cluster merely to satisfy local layout; a
cluster-local evidence directory may contain indexes or links to shared,
immutable records if traceability remains intact.

Potential logical outputs include:

- `raw_evidence.jsonl`: one indexed evidence record per line;
- `queries.csv`: exact queries, environments, timestamps, and result counts;
- `runs.csv` or run manifests: immutable run metadata;
- `evidence_links.jsonl`: typed raw-to-derived and claim-to-raw relations;
- `duplicate_groups.jsonl`: duplicate membership and comparison method;
- `source_registry.jsonl` and `source_policies.jsonl`: source and policy history;
- spreadsheet-friendly derived exports with supporting raw IDs.

Do not create an automatic opportunity table. Any future cluster table must
represent research grouping, retain raw IDs, expose inference, and remain
separate from product-selection decisions.

## Recommended MVP Sequence

### Stage 1: Search and Selected Pages

- Brave Search API
- allowlisted direct page retrieval
- extracted main text
- raw response files
- hashes, IDs, runs, policies, and lineage

This validates end-to-end provenance first.

### Stage 2: Structured Communities

- GitHub
- Stack Exchange
- Hacker News
- RSS/Atom

These sources offer stable native IDs and relationships unavailable on many
ordinary webpages.

### Stage 3: Competitor Metadata

- Apple app catalog metadata
- public pricing pages
- changelogs and documentation
- competitor-associated GitHub repositories

### Stage 4: Conditional Expansion

- paid review-data provider
- approved Reddit access
- Product Hunt permission
- search-volume provider
- Common Crawl lookups
- narrow browser automation allowlist

Only expand after core trail proves useful and source-specific costs and
permissions are understood.

## MVP Success Boundary

First useful version should answer:

> For this candidate problem, which search results, public pages, GitHub issues,
> Stack Exchange discussions, Hacker News threads, feeds, app metadata, and
> manual imports appeared, and can a reviewer inspect the exact source behind
> every count and label?

It must not claim comprehensive capture of every complaint, review, social post,
deleted item, or search-volume signal.

Supplied assessment hypothesizes that moderate personal use can fit roughly
within a $0-$10 monthly data budget through a small paid-search allowance plus
free structured APIs and local processing. Treat that as a budget hypothesis,
not a guaranteed provider price or an implemented constraint.

## Confirmed Facts

- No market facts have been collected for this cluster.
- PDF and pasted API assessment are retained here only as supplied planning
  context; they are not raw evidence artifacts.

## Hypotheses

- Metadata-first collection will preserve enough context for useful manual
  review without requiring a universal web archive.
- Search, selected pages, GitHub, Stack Exchange, Hacker News, RSS, and manual
  imports provide enough source diversity to test pipeline.
- Local IDs, hashes, JSONL indexes, payload files, lineage tables, and immutable
  runs can provide a strong audit trail at low recurring infrastructure cost.
- Exact payload retention is useful where permitted, but policy-aware excerpts
  and metadata can preserve partial auditability when full storage is barred.
- WARC adds value later but is unnecessary for first useful version.

## Open Questions

- Will raw payloads live in shared run storage, cluster-local evidence folders,
  or a hybrid of shared payloads plus cluster-local indexes?
- What exact collision-safe, readable, filename-safe ID convention will apply
  to each entity type?
- What shared runner interface will acquisition adapters and cluster modules use?
- Which domains enter initial webpage allowlist, and who reviews them?
- What default retention and truncation rules apply per source and media type?
- How will policy-required deletion preserve a tombstone and downstream lineage
  without retaining prohibited content?
- Which transformation manifest format will capture code, rule, taxonomy,
  parser, and model versions?
- When should source records be shared across research clusters rather than
  copied, and how will cross-cluster references remain portable?
- Which fields may contain personal data, and what redaction or hashing policy
  will apply?
- How often will provider price, quota, documentation, and terms claims be
  reviewed?

## Decisions and Superseded Guidance

- Ideal instruction to collect all original relevant data is narrowed by source
  terms, storage rights, privacy, size, and practical access. Preserve exact
  payloads where allowed; otherwise retain permitted metadata, context, and
  explicit absence status.
- Universal web archiving is superseded for MVP by metadata-first collection
  from a small adapter set and selected page retrieval.
- General Google result scraping is rejected as an MVP fallback. Supplied
  assessment selects Brave as practical search provider and rejects Bing as a
  new dependency; both decisions require revalidation before implementation.
- Automated full competitor review collection, bulk Reddit storage, closed
  social ingestion, exact keyword volume, and unofficial Trends collection are
  excluded from MVP. Manual or permissioned routes remain possible.
- WARC remains optional phase-two storage; referenced compressed payload files
  plus hashes are preferred for initial simplicity.
- Duplicate detection creates groups and counting views; it never deletes raw
  source records.
- Staleness creates a derived flag or priority adjustment; it never silently
  removes historical evidence.
- Suggested 2,000-character limit is not adopted as a global cap because
  complete contextual sentences or paragraphs and source-specific policies take
  priority.
- Derived cluster tables may organize evidence but must not become an automatic
  app-idea generator, opportunity selector, or single score.

## Context Change Log

- 2026-08-15: Created cluster context from supplied ideal audit-trail PDF and
  practical API-availability assessment. Reconciled comprehensive provenance
  goals with a policy-aware, metadata-first MVP boundary. No code or collection
  behavior implemented.
