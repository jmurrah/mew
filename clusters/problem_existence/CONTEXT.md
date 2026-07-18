# Cluster Context: `problem_existence`

This file distills the supplied Problem Existence Evidence specification and
practical API-availability notes. Those inputs are design context, not collected
market evidence.

## Identity

- **Cluster ID:** `problem_existence`
- **Display name:** Problem Existence Evidence
- **Python module:** `problem_existence.py`
- **Purpose:** Determine whether a specific group, in a specific circumstance,
  repeatedly encounters the same obstacle and whether the observed pattern is
  unlikely to be a one-off complaint, temporary incident, or a few loud users.

## Central Research Question

Are multiple independent people, across independent threads or communities and
over a meaningful period, describing the same lived problem with behavioral
consequences?

This is narrower than asking whether a business, market, or product idea is
good. The cluster should stop at evidence that pain exists. Pricing, market
size, distribution, product selection, and build decisions belong elsewhere.

## Scope

### Included

- First-person accounts of current or past difficulty in a defined context.
- Repeated manual workarounds and tool stacks assembled to complete a job.
- Active requests for a better way, alternative, template, automation, or fix.
- Named incumbent tools or methods and their specific failure modes.
- Concrete consequences: time, money, errors, risk, delay, frustration, or
  urgency.
- Recurrence across distinct authors, threads, communities, source families,
  and time periods.
- Concentration, duplication, burst, source-coverage, and collection-quality
  measurements needed to challenge apparent recurrence.
- Search results used to discover or corroborate source records.
- Raw links, excerpts, timestamps, engagement snapshots, collection metadata,
  and canonical examples needed for manual inspection.

### Excluded

- Product recommendations, app ideas, go/no-go decisions, build plans, or
  validation plans.
- Claims about market size, pricing, profitability, or affected-population
  prevalence.
- A single opportunity score or any label presented as market proof.
- Cross-platform identity resolution.
- Training or fine-tuning models on collected Reddit content.
- Broad HTML scraping of platforms that require approved or restricted access.
- Complete historical coverage claims.
- Universal engagement normalization across unlike platforms.
- Current automatic collection from arbitrary app stores, G2, Capterra,
  Trustpilot, LinkedIn, Instagram, Facebook, X, Quora, or arbitrary blog-comment
  systems.

All nine profile sections remain required. Non-problem sections should stay
empty unless later collection produces evidence that genuinely supports them.

## Canonical Terminology

- **Problem mention:** One inspectable post, comment, question, review, or other
  source record relevant to a normalized problem statement.
- **Problem cluster:** Mentions grouped around the same actor, job, context,
  obstacle, and consequence. It is not an automatically generated product idea.
- **Normalized problem statement:** `[actor/segment] struggles to [job] in
  [context] because [obstacle], causing [cost/consequence]`.
- **Behavioral proof:** First-person account of an actual task, failure,
  workaround, switch, or repeated hassle.
- **Active search:** Request for a better method, alternative, template,
  automation, or fix.
- **Contextual complaint:** Complaint containing enough workflow context to
  understand the job and obstacle.
- **Generic dissatisfaction:** Negative reaction without enough context to
  establish the problem.
- **Hypothetical wish:** Speculative feature or “someone should build” statement,
  not evidence of lived behavior.
- **Source family:** Broad source type such as Q&A, code-hosting discussion,
  forum, social, review, or search.
- **Community:** Specific site, forum, subreddit, repository ecosystem, or other
  bounded venue within a source family.
- **Discovery:** Finding candidate URLs or native source IDs.
- **Hydration:** Retrieving the full source record from the original page or
  native API.
- **Planning context:** Supplied specifications, API notes, thresholds, and
  architecture ideas. It guides research design but is not market evidence.
- **Coverage grade:** Separate description of collection completeness and
  limitations. It does not measure problem strength.

## Evidence Model

### Evidence Quality Ladder

The supplied specification proposes these annotation tiers and tentative
weights:

1. Behavioral proof: `1.0`
2. Active search: `0.8`
3. Contextual complaint: `0.6`
4. Generic dissatisfaction: `0.3`
5. Hypothetical wish: `0.1`

These weights are design hypotheses, not validated truth. Preserve raw mention
counts beside any quality-weighted counts. An annotation or model result never
replaces its supporting excerpt and metadata.

### Strong Raw Signals

- Specific first-person story about an experienced event.
- Repeated workaround behavior, including named tools and manual steps.
- Alternative-seeking or comparison behavior.
- Named current solution with an explicit failure mode.
- Time, money, error, risk, delay, frustration, or urgency consequence.
- Similar accounts from distinct people in distinct threads.
- Recurrence across communities or source families.
- Persistence over time rather than a short-lived spike.

Upvotes, likes, views, sentiment, cluster size, and model confidence are
supporting metadata only. None independently proves problem existence.

### Normalization Constraint

Keyword overlap is insufficient. Only merge mentions when actor, job,
circumstance, obstacle, and consequence are compatible. Preserve ambiguity and
route borderline merges to manual review.

## Source Strategy

### Core MVP Sources

- **Stack Exchange:** Broad Q&A access with questions, answers, comments,
  authors, tags, votes, views, answer state, creation time, and last activity.
  Especially useful for persistence and unresolved-demand measures.
- **GitHub issues and discussions:** Core when researching software-related
  problems. Often includes actions, errors, attempted fixes, repeated failures,
  reactions, labels, state, and timestamps.
- **Hacker News:** Core for technical and operator problems. Use search only to
  discover IDs; hydrate records from the official API.
- **Curated Discourse forums:** Core route into non-developer niches. Use an
  explicit allowlist because permissions and limits vary by community.
- **Compatible WordPress sites:** Use REST comments, RSS, or Atom only where
  publicly exposed. This is opportunistic, not universal blog-comment access.
- **Accessible static pages and RSS:** Fallback sources where provenance and
  source text remain inspectable.
- **Manual URL import:** Supported research path for useful pages without an
  automatic adapter.
- **Web-search API:** Discovery and corroboration only. Retrieve the original
  accessible page or native record before counting evidence.

### Search Discovery

The supplied practical guidance prefers Brave Search API for routine discovery
and SerpAPI only for selective structured SERP features. Candidate query forms
include exact problem phrases, `how do I`, `alternative to`, `does anyone else`,
`frustrated with`, and source-restricted searches.

Capture query, rank, title, URL, domain, snippet, and available result date, but
never substitute a search snippet for the source record. Search volume and
ranking are corroboration, not required proof. Google Custom Search JSON API was
explicitly rejected as a new foundation because the supplied material reports
its retirement path.

### Conditional Source

Reddit may be a high-value general source, but it is optional and must not block
the MVP:

- Confirm approved API access and current use terms before collection.
- Do not assume a private local side-income research tool is noncommercial.
- Prefer approved API access over broad HTML scraping.
- Retain raw Reddit ID and permalink; store only the excerpt needed for review.
- Hash authors and support later reconciliation of removed content.
- Do not train or fine-tune models on stored Reddit text.
- Keep all core analysis usable without Reddit.

### Optional Later Sources

- YouTube comments for tutorial, hardware, fitness, hobby, or creator niches.
- Bluesky where a niche has enough public discussion.
- Mastodon through selected instances, never as a supposedly complete corpus.
- A named comment provider or site-specific adapter when its value is clear.

### Deferred Automatic Sources

- Arbitrary Apple App Store and Google Play competitor reviews.
- G2, Capterra, Trustpilot, and similar review corpora.
- LinkedIn, Instagram, Facebook, X, and Quora.
- Universal blog-comment scraping.
- Exact search-volume collection or Google Trends dependency.
- Complete historical backfills and automated screenshots of every record.

These may accept manually supplied URLs later. Review evidence fits more
naturally in a competitor/supply weakness cluster unless it directly supports a
problem claim.

### Volatile Access Notes

The supplied API details are a planning snapshot, not verified-current provider
facts. They reported approximate access such as Stack Exchange's 10,000 daily
default quota, GitHub's 5,000 authenticated REST requests per hour with tighter
search limits, no stated HN API rate limit, and site-dependent Discourse and
WordPress access. They also reported changing prices or quotas for Brave,
SerpAPI, YouTube, Reddit, Bluesky, Mastodon, Google Trends, Google Ads, and X.

Recheck official provider documentation, pricing, approval requirements,
retention rules, deletion duties, and rate limits immediately before any source
is implemented or collected. Never encode volatile numbers as durable defaults
without that review.

## Mention-Level Record Guidance

### Identity and Provenance

- `cluster_id`, `evidence_id`, `source_family`, `community_name`
- `source_url`, `source_title`, `thread_id`, `post_or_comment_id`, `parent_id`
- `created_at`, `updated_at`, `captured_at`
- `author_id_hashed`, with explicit author scope
- `raw_payload_path`, `content_hash`, and duplicate group

### Inspectable Text and Annotation

- `excerpt_raw`, `excerpt_clean`, `exact_pain_phrase`
- `normalized_problem_statement`, `segment_hint`, `context_hint`
- Firsthand-current, firsthand-past, hypothetical, solution-seeking,
  alternative-seeking, and workaround indicators
- Current solution, solution-failure indicator, and failure mode
- Explicit time, money, risk/error, frustration, and urgency indicators
- Evidence tier, manual relevance state, and manual notes

### Source-Native Metrics

- Preserve each source's votes, reactions, replies, views, helpful votes, answer
  state, open/closed state, tags, and categories only where available.
- Prefer `engagement_metric_name`, `engagement_metric_value`, `reply_count`,
  `view_count`, and `view_count_available_bool` over a universal engagement
  score.
- Compare engagement percentiles only within the same platform and community.

### Collection Quality

- `collection_method`: official API, public JSON, RSS, HTML, search result, or
  manual
- Exact `source_query`, API name/version, pagination page, and rank at capture
- Retrieval status, capture error, metric availability, and terms-risk class
- Intended collection window, actual retrieved range, page count, completeness,
  result-cap status, historical-coverage class, and coverage notes

Store original responses separately from normalized rows so extraction can be
re-run without reacquiring the source.

### Missingness Rules

- Unknown or unsupported values remain `NULL`, never `0`.
- Deleted authors receive a record-specific missing state, not one shared
  identity.
- Incomplete pagination and result caps remain explicit.
- Search absence and missing public discussion are not proof that pain is absent.

## Cluster-Level Measures

### Breadth and Persistence

- Relevant and quality-weighted mentions
- Unique authors within their source scope
- Unique threads, communities, and source families
- First and last seen dates, span days, active weeks, and active months
- Seven-day and 30-day burst ratios and recency

Never create `global_unique_people`. Report source-scoped unique authors and
state that possible cross-source duplicates are unknown.

### Behavioral Consequence

- Workaround rate
- Alternative-seeking rate
- Incumbent-failure rate
- Explicit-cost or consequence rate

### Concentration and Duplication

- Top-author and top-three-author shares
- Top-thread and top-community shares
- Duplicate ratio
- Community and timeline distributions

Raw mention count must never be interpreted without author/thread breadth and
concentration. Cross-source recurrence is generally more persuasive than the
same count inside one venue, but this remains an interpretation, not collected
fact.

### Coverage

- Attempted and successful source counts
- Pagination completeness and result-cap status
- Intended and actual coverage windows
- Oldest and newest retrieved items
- Coverage description or grade
- Missing-metric flags
- Eligibility for any later problem-signal label

Problem-signal strength and evidence coverage must remain separate. Missing a
closed platform should reduce coverage, not silently weaken or strengthen the
observed pattern.

## Proposed Labels and Overrides

The ideal specification proposed inspectable `weak`, `medium`, and `strong`
problem-signal labels plus burst, single-community, thin-behavior, review-bias,
and search-only flags. It also proposed numeric starting thresholds:

- **Weak:** at least 5 relevant mentions, 3 authors, 2 threads, and at least 10%
  workaround, alternative-seeking, or explicit-cost rate.
- **Medium:** at least 15 mentions, 10 authors, 5 threads, 2 communities, 2 source
  families, 60 days, 2 active months, 25% workaround-or-alternative rate,
  top-three-author share at most 35%, and top-thread share at most 40%.
- **Strong:** at least 30 mentions, 20 authors, 10 threads, 3 communities, 2
  source families, 180 days, 4 active months, 35%
  workaround-or-alternative rate, 20% explicit-cost rate, top-three-author share
  at most 25%, top-thread share at most 30%, and one corroborating source.

The practical notes narrow eligible inputs to metrics broadly obtainable from
core sources. Search volume, app-review count, helpful votes, views,
cross-platform identities, follower counts, and sentiment must not be required.

These thresholds are unvalidated design hypotheses. Do not implement or present
them as truth, a market score, or a go/no-go decision without later user
authorization. If labels are later used, always expose raw support, override
flags, manual review state, canonical evidence IDs, and a separate coverage
grade.

## False Positives

- Feature wishlists mistaken for experienced pain.
- Viral complaints caused by outages, launches, pricing changes, API
  deprecations, policy events, or media attention.
- One community's culture or negativity mistaken for broad recurrence.
- Fake, bought, coordinated, or incentivized reviews.
- Search-ranking artifacts mistaken for prevalence.
- Duplicated, cross-posted, quoted, or syndicated text counted repeatedly.
- One prolific author or one large thread dominating results.

## Expected False Negatives

- Nonconsumers whose alternatives are too expensive, slow, complex, or
  inaccessible.
- People tolerating pain because habit, anxiety, or switching costs block change.
- Private pain visible only in support tickets, sales calls, private groups, or
  internal workflows.
- Small valuable niches too quiet for keyword tools or social volume.
- Deleted, restricted, unindexed, capped, or migrated content.

Public evidence is a sampled observation of expressed problems, not a
representative survey. It cannot establish true prevalence or authenticate every
author.

## Manual Inspection Standard

Each claimed pattern should remain answerable in plain terms: how many observed
authors, where, when, in what words, using what workaround or failed alternative,
with what consequence, and with what concentration and coverage limits.

Preserve three to seven canonical excerpts where possible, spanning distinct
authors, communities, and times. A useful set includes a firsthand story, a
workaround, an alternative request, an incumbent failure, and later recurrence.
These are navigation aids, not substitutes for full distributions.

At minimum, every factual claim needs stable evidence IDs connected to raw
excerpt, original URL, source title, source date, capture date, and engagement
snapshot.

## Nonbinding Technical Context

The supplied material suggests native APIs first, `httpx` and bounded retries
for requests, RSS tools for feeds, targeted HTML extraction as fallback, and
Playwright only for a small explicit allowlist. It also suggests preserving raw
API responses alongside normalized local data, then using rules, local NLP,
embeddings, fuzzy matching, and near-duplicate detection only for annotation and
grouping.

SQLite/FTS5, Parquet, DuckDB, Polars or pandas, CSV/XLSX, Datasette, and
Streamlit were presented as possible local tools—not selected requirements.
Root repository boundaries still prohibit dashboard-first work. No dependency,
schema, interface, or architecture is chosen by this context update.

## Confirmed Project Facts

- User selected cluster ID `problem_existence`.
- Display name is `Problem Existence Evidence`, matching supplied material and
  the cluster's narrow research question.
- Supplied PDF and text are durable design context, not market evidence.
- No problem-existence evidence has been collected yet.
- Current task creates guidance and a module scaffold only; no collection logic
  or public interface is authorized.

## Assumptions

- This cluster is a horizontal evidence-research capability rather than a
  vertical market or audience cluster because the supplied material defines an
  evidence question and the user fixed `problem_existence` as the ID.
- Future research runs will supply a specific segment, job, circumstance, and
  seed problem before collection begins.
- API-access and pricing claims in the supplied text may drift and require live
  verification before implementation.

## Hypotheses

- First-person behavioral stories are stronger problem-existence signals than
  generic complaints or future-facing wishes.
- Repeated workarounds, active alternative searches, and named solution failures
  indicate more consequential pain.
- Cross-source recurrence is generally stronger than equal volume inside one
  thread or community.
- Longer persistence and lower burst concentration reduce the chance that a
  pattern is event-driven.
- The proposed evidence-tier weights and weak/medium/strong thresholds may help
  inspection, but remain unvalidated.

## Open Questions

- Which specific segment, workflow, and problem statement will seed the first
  evidence collection?
- What top-level runner interface and shared record schema will later govern
  cluster modules?
- Which Discourse, WordPress, RSS, and static-page domains belong on the initial
  allowlist?
- Which APIs, credentials, budgets, and use terms will be approved after current
  provider review?
- Should any problem-signal labels be implemented, and if so, how will their
  thresholds be calibrated and manually audited?
- How will coverage grades be defined without disguising inaccessible sources?
- What retention and deletion schedule will apply to source excerpts and raw
  payloads?
- What manual review workflow will resolve ambiguous relevance, deduplication,
  and cluster merges?

## Decisions and Superseded Guidance

- Practical API guidance narrows the PDF's ideal all-source model: v1 should
  favor Stack Exchange, GitHub, Hacker News, curated Discourse, compatible
  WordPress/RSS/static pages, search discovery, and manual URLs.
- Reddit changes from an assumed core source to a conditional adapter requiring
  approved access and terms review.
- Arbitrary review platforms, closed social networks, universal blog comments,
  exact search volume, and complete historical backfills are deferred.
- Search snippets may discover evidence but do not count as hydrated evidence.
- Cross-platform unique people, true prevalence, universal engagement scores,
  and authenticity booleans are rejected as unsupported.
- Problem-signal labels and coverage descriptions are separate; neither is a
  market-opportunity decision.
- No earlier cluster-specific guidance existed to supersede.

## Context Change Log

- `2026-07-13`: Created cluster context from supplied ideal specification and
  practical API-availability guidance. No raw market evidence imported.
