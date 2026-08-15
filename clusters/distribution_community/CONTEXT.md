# Cluster Context: `distribution_community`

This file stores durable design guidance for the Distribution and Community
Evidence cluster. It models the supplied ideal specification and practical
API-access assessment. Neither input is collected market evidence.

## Identity

- **Cluster ID:** `distribution_community`
- **Display name:** Distribution and Community Evidence
- **Python module:** `distribution_community.py`
- **Purpose:** Find inspectable public surfaces where likely early users gather,
  search, discuss, compare tools, or can plausibly be reached with little
  distribution infrastructure.
- **Decision role:** Help the user inspect audience reachability and access
  constraints. This cluster does not validate a market, estimate market size,
  select an opportunity, propose a go-to-market plan, or decide what to build.

## Core Research Question

If this problem matters, are there visible places where likely early users
already gather, search, discuss, compare tools, or are assembled into a relevant
audience—and what direct evidence shows current activity, specificity,
engagement, access, and policy constraints on each surface?

A problem can be real yet operationally difficult when affected people are hard
to find, hard to contact, or reachable only through expensive or closed
channels. This cluster measures observable reachability, not abstract audience
size or product-market fit.

## Conceptual Model

### Surface Families

- **Interactive community:** Public discussions where users ask for help,
  complain, compare tools, or share workflows. Examples include Stack Exchange,
  GitHub Issues or Discussions, Discourse forums, Hacker News, approved Reddit
  access, and other niche forums.
- **Launch and discovery community:** Concentrated early-adopter exposure and
  feedback, such as Product Hunt or niche launch boards. Engagement may be
  episodic and audience-biased; launch activity is not sustained acquisition.
- **Organic search surface:** Search engines and public Q&A discovery where
  users express informational, problem-aware, solution-seeking, comparison, or
  navigational intent.
- **Marketplace search surface:** App stores and marketplaces where users look
  for tools through queries, categories, rankings, ratings, reviews, badges, or
  visible listing metadata.
- **Audience node:** Newsletter, blog, creator, podcast, publication, tag
  ecosystem, or other curator that aggregates a niche. Access may be indirect
  through sponsorship, submissions, guest posts, recommendations, or comments.

Some surfaces span families. TikTok and YouTube can combine search, UGC, and
creator audiences. Stack Exchange combines Q&A community and search discovery.
Store surfaces provide intent without public conversation. Preserve the actual
interaction mode instead of forcing one generic channel type.

### Reachability Classes

- **Conversation-reachable:** A person can post, comment, reply, DM, submit,
  join, or otherwise participate under visible constraints.
- **Search-reachable:** Users express intent through search or marketplace
  browsing; reach depends on producing a discoverable result or listing.
- **Audience-mediated:** A creator, publication, newsletter, or curator
  aggregates the audience and offers some indirect path.
- **Mixed:** More than one supported reachability mode exists.
- **Passive-only:** Audience size or visibility is observable, but no credible
  interaction, search-intent, or mediated access path is established.

Visibility and reachability are separate. A large visible audience may be
passive. A small exact-fit search surface may be useful without public posts.

## Scope

### Included

- Public, permitted, manually inspectable surfaces tied to one explicit problem,
  audience, workflow, query family, or adjacent terminology set.
- Surface identity, family, platform, canonical URL, visibility, interaction
  mode, access method, audience description, query, and capture time.
- Recent relevant activity in bounded 30- and 90-day windows, unique authors,
  latest activity, replies/comments, reactions, views where available, and
  repeated problem wording.
- Explicit questions, complaints, solution requests, recommendation requests,
  comparison requests, workarounds, tutorials, and creator coverage.
- Public rules, guidelines, join/post/link requirements, visible self-promotion
  policy, store eligibility/review constraints, and manual policy review.
- Public search and marketplace samples with exact query, returned position,
  sample size, direct relevance classification, visible ratings/review counts,
  prices, categories, and listing-quality signals.
- Public newsletters, blogs, feeds, creators, and publications with cadence,
  topic specificity, visible engagement, recommendation links, and visible
  submission/sponsorship/contact paths.
- Stable raw evidence IDs, URLs, limited excerpts, capture/publication dates,
  visible counts, raw snapshots when permitted, transformation metadata, and
  missing-data reasons.
- Explicit uncertainty about private, non-indexed, unsupported, denied, or
  uncollected surfaces.

### Excluded

- Market validation, total addressable market, reachable-user population,
  passive-searcher count, conversion forecasts, acquisition forecasts, and
  product-channel fit conclusions.
- Opportunity scoring, build/no-build decisions, automatic app ideas, product
  recommendations, validation plans, and go-to-market plans.
- Automated outreach, DMs, posting, joining communities, promotion, sponsorship
  purchases, or contactability analysis.
- Automated moderation strictness, removal rate, ban rate, or promotion-risk
  judgments not grounded in explicit captured rules.
- Facebook Group post analysis; TikTok post, hashtag, keyword, comment, view, or
  creator analysis; private Discord/Slack/community message analysis; Quora
  crawling; and aggressive unauthenticated Reddit scraping.
- Exact newsletter subscriber counts when not directly visible; hidden audience
  identities; private-group content; exact marketplace keyword volume; exact
  total marketplace-result counts; store impressions; install counts where not
  exposed; and rankings predating this project's own snapshots.
- Complete claims from bounded samples, including complete platform discussion
  volume, universal audience size, universal rank, or all-time recurrence.
- Treating search snippets, broad views, hashtags, members, followers, ratings,
  repository stars, or Product Hunt upvotes as direct proof of reachability or
  demand.

## Canonical Terminology

- **Surface:** One inspectable community, forum, query/result set, marketplace,
  feed, publication, creator, tag, category, known invite, or launch context.
- **Surface observation:** One surface captured under recorded query, locale,
  access method, time, limits, and visibility conditions.
- **Evidence artifact:** One supporting thread, comment, rules page, search
  result, listing, tag page, article, video, feed item, or snapshot.
- **Audience entity:** Role, company type, workflow, hobby, segment, or creator
  niche visibly gathered on a surface.
- **Problem match:** Whether captured content addresses exact problem, adjacent
  problem, broad topic, or unclear relationship.
- **Audience match:** Whether observed participants or publication audience
  match intended users. Keep separate from problem match.
- **Surface discovery:** Locating a possible surface through search results,
  links, directories, or invites. Discovery alone does not establish metrics.
- **Public discussion:** Repeated recent relevant items from independent authors,
  not merely one viral or highly engaged thread.
- **Recent relevant item:** Captured item inside declared time window that a
  documented relevance rule or manual review connects to the problem.
- **Unique author:** Distinct source-provided author identity inside recorded
  window. Deleted, anonymous, or unstable identities remain explicit.
- **Visible count:** Count directly exposed by source at capture time; it may be
  approximate, stale, rounded, scoped, or absent.
- **Top-N sample:** Bounded ordered results returned for one query and capture.
  It is not complete marketplace supply or total result count.
- **Relevant results in top N:** Manually confirmed or reviewable relevant items
  divided by recorded top-N sample size. This replaces ideal
  `competitor_listing_count` in practical MVP.
- **Interaction mode:** Visible action supported by surface: post, comment,
  reply, DM, join-and-lurk, search-click, list/install, sponsor, submit, or
  recommend.
- **Access friction:** Visible cost or requirement for joining, reading,
  searching, posting, listing, or contacting.
- **Policy evidence:** Captured explicit rule, guideline, permission, ban,
  eligibility constraint, or direct access response. Absence of a rule is not
  permission.
- **Specificity evidence:** Independent appearance of same role + workflow +
  problem language across names, descriptions, tags, threads, queries, or
  publication focus.
- **Planning context:** Supplied specifications and access assessments guiding
  future work; not evidence that any real audience or market exists.

## Research Principles and Important Distinctions

### Activity Beats Membership

Member or subscriber count is weak alone because most community members may be
inactive or silent. Prefer recent relevant items, unique authors, recency,
comment depth, reactions, explicit solution requests, and repeated problem
language. A large dormant group should not outrank a smaller exact-fit surface
with repeated current discussion.

### Repetition Beats Virality

Do not label public discussion strong from one viral item. Look for independent
authors and recurring language across 30- and 90-day windows. Preserve item IDs,
dates, authors, excerpts, and deduplication method.

### Exact Intent Beats Broad Popularity

Broad topics such as productivity, AI, or small business may have huge audiences
but weak fit. Strong specificity names a role, workflow, and pain—for example,
Shopify merchants needing upsell bundles, Chrome users automating tab workflows,
or teachers managing rubric feedback. Store categories, tags, related terms,
and publication focus can support specificity but never replace item-level
evidence.

### Conversation and Search Are Independent Signals

Some problems produce little public conversation because users search privately
or browse stores. Weak discussion does not cancel exact solution-seeking search
or marketplace evidence. Strong discussion does not prove users search for or
can discover a product. Preserve both dimensions.

### Search Discovery Is Not Source Evidence

Brave can locate Reddit threads, GitHub issues, forums, newsletters, rules pages,
and store listings. Search snippets and estimated result counts remain discovery
records. Platform-specific capture or manual verification must support factual
activity, policy, engagement, and audience claims.

### Visible Is Not Reachable

Public names or counts may expose an audience without offering an interaction or
intent path. Conversely, a store query can be search-reachable even when users
never post publicly. Store `public_visibility`, `interaction_mode`, access
friction, and `reachability_class` separately.

### Rules Are First-Class Evidence

Relevance does not imply permission to promote. Capture join, posting, link,
self-promotion, moderation, listing, review, and eligibility constraints. Use
explicit rules and direct observations. Unknown stays unknown. For marketplaces,
the equivalent question is whether a compliant listing can exist and plausibly
participate in discovery.

### Missing Access Is Not Absence

Private Facebook Groups, non-discoverable Discord servers, private Slack groups,
and inaccessible APIs can hide relevant audiences. Record visibility-limited,
private, unsupported, denied, or not collected instead of `no evidence` or zero.

### Vocabulary Mismatch Can Hide Evidence

Users may describe same job with tags, jargon, symptoms, product names, or
workaround language different from researcher's canonical phrase. Preserve
aliases, related tags, adjacent queries, and exact matched phrases. Do not merge
them silently or inflate one canonical count.

### Source Audiences Carry Bias

- Stack Exchange is strongest for technical and professional question domains.
- GitHub is strongest for developer, open-source, integration, and product-
  support problems. Repetition across independent repositories is more useful
  than repeated tickets inside one repository.
- Hacker News is startup-, founder-, and technology-heavy; use it as a
  supplemental source for ordinary consumer audiences.
- Product Hunt concentrates makers and early adopters; upvotes and comments are
  launch-event evidence, not durable acquisition or end-user fit.
- YouTube views may reflect broad interest. Preserve problem match and audience
  match separately.

## Practical Source Strategy

Supplied API assessment narrows the ideal cross-channel specification to a
cheap, public, structured MVP. Details below are a user-supplied planning
snapshot received 2026-08-15, not independently verified facts. Recheck access,
prices, quotas, documentation status, legal terms, retention/deletion duties,
and endpoint behavior before implementation or collection.

### First Release

1. **Brave Search:** Core surface-discovery layer. Supplied estimate is about
   1,000 searches per month covered by recurring $5 credits, then $5 per 1,000.
   Use site-restricted and audience/problem queries to discover forums,
   communities, rules, newsletters, GitHub issues, known invites, and public
   store pages. Never use snippets or estimated result counts as final facts.
2. **Stack Exchange:** Official API for questions, tags, answers, comments,
   scores, views, accepted answers, dates, authors, and related terminology.
   Supplied default is 10,000 requests/day with documented backoff. High value
   for recent counts, recurrence, author diversity, and technical workflows.
3. **GitHub Issues and Discussions:** Official REST data for titles, bodies,
   comments, reactions, labels, states, dates, repositories, organizations, and
   authors. Supplied limits are 60 unauthenticated or 5,000 authenticated calls
   per hour. Track distinct repositories to separate cross-product pain from
   one support queue.
4. **Discourse:** Prefer public JSON or RSS across independent forums. Capture
   topics, replies, views, likes, authors, categories, tags, activity dates,
   rules, and public directory fields when enabled. Limits vary per site.
   Detect Discourse and avoid rendered-HTML scraping when structured endpoints
   work.
5. **RSS/Atom:** Core open-standard collection for blogs, newsletters, forums,
   and publications. Capture feed/site URLs, titles, authors, dates, excerpts,
   cadence, recent relevant posts, comments where visible, and submission or
   sponsorship pages. Subscriber counts remain optional.
6. **Hacker News:** Public Algolia search for stories/comments, points, comment
   counts, authors, dates, threads, and repeated mentions. Supplemental because
   audience is broad and founder/technology-heavy.
7. **Evidence storage and manual review:** Required from first release. Source
   limits or missing credentials must produce explicit status, not fabricated
   zeros.

### Next Additions

8. **YouTube:** Official API for videos, channels, views, likes, comments,
   publication dates, descriptions, channel subscriber counts, and distinct
   channels. Supplied post–June 1, 2026 quota is 100 `search.list` calls/day plus
   10,000 daily units for most other endpoints. Treat views and subscribers as
   contextual proxies, not reachable-user counts. Useful for creator interest,
   tutorials, workarounds, reviews, and public UGC.
9. **Apple App Store Search:** Legacy official iTunes Search API, whose supplied
   documentation snapshot is archived and last updated in 2017. Preserve query,
   returned position, top-N sample size, app ID/URL/name/developer/category,
   price, rating/count, version/update metadata, description, and relevance.
   Never claim exact keyword volume, total matching apps, installs, impressions,
   complete rank history, or autocomplete popularity.
10. **Reddit after approved access:** Potentially strong source for posts,
    comments, authors, scores, subreddit metadata, descriptions, and rules.
    Supplied assessment flags OAuth, discretionary limits, possible fees,
    commercial-use agreement risk, and uncertainty for this side-income research
    context. Do not make MVP dependent on approval. Brave may discover URLs but
    cannot supply reliable activity/member counts. Preserve limited excerpts and
    URLs; avoid building a permanent archive beyond approved terms.
11. **Shopify App Store and Chrome Web Store public-page parsers:** Experimental,
    unsupported adapters discovered through Brave or public store pages. Save
    raw HTML, timestamp, parser version, and breakage status. Crawl slowly.
    Capture only visible listing metadata; never promise exact search result
    counts, keyword volume, actual downloads, or historical rankings.

### Later, Optional, or Vertical-Specific

- **Etsy:** Official Open API after key approval, useful for templates, digital
  downloads, printables, spreadsheets, design assets, guides, and small digital
  products. Quotas are application-specific; respect `429` and retry headers.
- **Product Hunt:** Official GraphQL source for launches, products, topics, and
  engagement. Supplied terms allow public read use but require separate contact
  for commercial use. Treat as optional and audience-biased.
- **Discord invite enrichment:** For an already known invite, capture server
  name, URL, description, approximate members/online users, discoverability,
  validity, and timestamp when official API permits. No message, engagement,
  rules-channel, or author analysis without explicit joining and bot authority.
- **Manual Google Keyword Planner CSV:** Optional later import for average
  monthly searches. Keep field nullable. Supplied assessment says automated
  Keyword Plan Idea access usually needs Basic Access review and permitted-use
  alignment.
- **Manual Google Trends CSV:** Optional later. Supplied assessment says official
  API remained limited alpha and returned scaled interest, not absolute volume.
  Do not make unofficial `pytrends` a core dependency.

### Excluded from MVP

- **TikTok automated research:** Research API is reportedly limited to eligible
  academic/nonprofit public-interest researchers independent of commercial
  interests; ordinary Display API is not general search. Keep only optional
  manual URL/notes and `surface_discovered`; no automated engagement score.
- **Facebook Groups:** No practical general-purpose public research API for
  posts, activity, identities, comments, rules, or history. Store manually
  observed name, URL, visibility, and visible member count only, with manual
  review required.
- **Quora:** Search-engine-discovered URLs only; no crawling dependency.
- **Private Discord, Slack, or other communities:** No automated message or
  member analysis.
- **Google Custom Search:** Supplied assessment says JSON API is closed to new
  customers and existing users must migrate by 2027-01-01; do not adopt it.

## Access and Missing-Data Model

Every attempted source should retain:

- `collector_name`, `collector_version`, `collection_status`, `http_status`;
- `data_access_method`, `data_source_type`, `is_official_api`;
- `is_unsupported_parser`, `access_limited`, and `metric_missing_reason`;
- credentials-present state without secrets, quota/backoff response, capture
  time, raw artifact path, and source URL where allowed.

Distinguish measured zero from `not_available`, `private`, `not_supported`,
`access_denied`, and `not_collected`. A nullable metric requires reason when
known. Source changes or adapter failures must not overwrite earlier snapshots.

## Evidence Model

### Surface Observation

One row per captured surface. Preserve at least:

- `surface_id`, linked problem/query ID, `platform`, `surface_family`, name, URL;
- query, aliases/related terms, locale when relevant, capture timestamp;
- public visibility, access method, interaction modes, reachability class;
- audience entity, problem match, audience match, specificity evidence;
- member/online counts only when visible and source-scoped;
- 30/90-day relevant counts, unique authors, latest activity, sampled medians;
- exact top-N sample size and relevant-results count for search/store surfaces;
- join/post/link/self-promotion/listing friction and rules evidence;
- collection status, access limits, missing reasons, evidence count, and notes.

### Evidence Artifact

One row per supporting artifact:

- stable `evidence_id` and `surface_id`;
- type: thread, question, answer, comment, rule, listing, search result, tag,
  article, feed item, video, creator/channel, or manual observation;
- title, author/source, published/updated dates, canonical URL, capture time;
- short excerpt in context plus exact problem, role, and workflow phrase found;
- visible comments, replies, reactions, views, members, rating, or price when
  relevant, each source-scoped and timestamped;
- relevance classification and reason, collector/transform version, raw record
  reference, and manual-review status.

### Rules and Openness Observation

Preserve independently because policy can change faster than discussion:

- surface and rules URL, capture time, explicit excerpt;
- join/read/search/post/link/DM/listing requirements;
- self-promotion status: allowed, conditional/limited, banned, or unknown;
- visible store review or eligibility barrier;
- direct versus inferred fields and manual-review status.

No automatic moderation-strictness or promotion-risk conclusion belongs in MVP.
If later added, it must be a versioned review aid linked to explicit rules and
missing inputs.

### Cluster Summary

One row per problem may summarize:

- total and publicly inspectable surfaces;
- distinct platforms and family counts;
- conversation, search, marketplace, launch, and audience-node coverage;
- counts of recent relevant items and unique authors with windows/denominators;
- recurring audience entity and problem language;
- explicit allowed/conditional/banned/unknown policy counts;
- manual-review priority, uncertainty, access gaps, and top evidence IDs.

Summary must not estimate total audience, choose an opportunity, or hide source
coverage and unknowns behind one score.

## Metric Guidance

### Universal Fields

Practical MVP should support:

- `platform`, `surface_name`, `surface_url`, `surface_family`;
- `query_used`, `capture_timestamp`, `public_visibility`;
- `data_access_method`, `api_supported`, and provenance/status fields;
- `interaction_mode`, `audience_entity`, `problem_match_level`, and separate
  `audience_match_level`;
- `exact_problem_excerpt`, `evidence_url`, `raw_snapshot_path`, and
  `manual_review_status`.

### Community Activity and Engagement

Prefer:

- `recent_relevant_items_30d`, `recent_relevant_items_90d`;
- `unique_authors_90d`, `latest_relevant_activity_at`;
- `median_comments`, `median_reactions` with linked sampled records;
- repeated/deduplicated pain threads;
- question, complaint, workaround, recommendation, and solution-request types;
- self-identifying roles/workflows where explicitly stated.

Ideal ratios such as question-post, complaint-post, and solution-request ratios
remain provisional. Each needs documented classifier version, numerator,
denominator, evidence IDs, and manual review. Do not present model labels as
observed facts.

### Search and Marketplace

Preserve:

- exact query and match type: exact, close variant, related, or category-only;
- intent class: navigational, informational, problem-aware, solution-seeking,
  or comparison;
- observed result position, `top_n_sample_size`, and
  `relevant_results_in_top_n`;
- visible category/tag fit, rating, rating count, price, badges, update metadata,
  and listing-quality signals;
- related/autocomplete terms only when directly available;
- search/listing policy barriers and capture conditions.

Do not use `competitor_listing_count` or visible search-result estimates as
complete competitor counts. `search_volume` remains nullable/manual import.

### Audience Nodes and UGC

Preserve node type, topic focus, publication cadence, recent relevant items,
authors/creators, visible engagement, recommendations/cross-links, and visible
sponsorship/submission/comment paths. Visible subscriber/follower counts are
optional context. Do not infer trust, reach, or audience overlap solely from
size.

YouTube-specific measures may include returned relevant-video sample,
publication dates, views, likes, comments, channel names, subscriber counts,
descriptions, top-level comments/replies, distinct channels, recent frequency,
and median engagement. Every metric stays bounded by query and sample.

## Provisional Derived Labels

Ideal specification proposes these multidimensional review labels:

- `reachability_class`: conversation, search, audience-mediated, mixed, or
  passive-only;
- `specificity_label`: low, medium, or high from repeated role + workflow +
  problem language;
- `discussion_signal_label`: none, weak, medium, or strong from frequency,
  recency, author diversity, and recurrence;
- `engagement_signal_label`: none, weak, medium, or strong from sampled comments
  and reactions;
- `distribution_signal_label`: weak, medium, or strong per surface;
- `cluster_distribution_label`: weak, medium, or strong across surfaces.

These are unvalidated heuristics, not collected facts or an opportunity score.
Every label needs rule/version, exact raw inputs, missing inputs, evidence IDs,
and manual-review status. The ideal draft suggests:

- Strong per-surface signal when access is practical, recent discussion or
  search/store intent repeats, specificity is medium/high, and policy is not
  known high-risk.
- Medium when evidence exists but activity is sporadic, specificity weak, or
  access/rules reduce reachability.
- Weak when evidence is mainly size-only, stale, broad, or visibility-blocked.
- Strong aggregate when two independent strong surfaces exist, or one strong
  conversation surface and one strong search/store surface exist.
- Medium aggregate when one strong or at least two medium surfaces exist.
- Weak aggregate when evidence is shallow, stale, generic, or policy-blocked.

Thresholds remain design hypotheses. Practical MVP explicitly excludes
automated promotion-risk judgment, so policy should remain explicit fields plus
manual review. Aggregate labels must expose component surfaces and uncertainty.

## Manual Inspection Standard

For every surfaced pattern, user should be able to answer:

- What exact problem, role, workflow, query, aliases, and locale were used?
- Which exact public surfaces were found, through what method, and when?
- How many relevant items and authors were observed in each bounded window?
- Which raw records support medians, recurrence, specificity, and intent?
- What exact language did users use for problem, workaround, or solution ask?
- Is surface conversation-, search-, or audience-mediated reachability?
- What explicit join, posting, link, promotion, listing, or review rules apply?
- Which policies are unknown because rules were missing or access limited?
- Which counts are direct, approximate, sampled, rounded, stale, or unavailable?
- Could private communities, vocabulary mismatch, quiet search intent, source
  bias, or API restrictions explain weak visible evidence?

Strong evidence preservation includes exact URL, surface name, query, capture
time, publication time, visible counts, short in-context excerpt, rules URL and
excerpt for policy claims, raw snapshot where permitted, and manual-review
state. Exact user language is especially important.

## Failure Modes and Guardrails

### False Positives

- Large member, follower, subscriber, view, rating, star, or hashtag counts with
  little current problem-specific activity.
- One viral thread or launch spike treated as repeated public discussion.
- Broad entertainment or informational interest treated as solution intent.
- Product Hunt upvotes treated as sustained acquisition or target-user demand.
- Search snippets or estimated results treated as verified source counts.
- Visible group name treated as accessible membership or promotion permission.
- Public store existence treated as easy listing, ranking, or discovery.
- Unknown rules treated as allowed; absence of removal evidence treated as safe.
- Overlapping or cross-posted items counted as independent recurrence.

### False Negatives

- Private or non-discoverable communities hidden from public collection.
- User vocabulary differs from canonical problem phrase.
- Users search or browse stores silently rather than discuss publicly.
- Small exact-fit publications or communities lack large visible counts.
- Strong nontechnical audiences are absent from Stack Exchange, GitHub, or HN.
- API quota, approval, indexing, deletion, or parser failures hide activity.
- Subscriber counts are unavailable despite active, highly specific publication.

Report `no public evidence found under recorded access and queries` or
`insufficient coverage`, never `no audience exists`.

## Nonbinding Technical Context

Supplied material suggests `httpx` or `requests`, `tenacity`, `requests-cache`,
`feedparser`, BeautifulSoup, `trafilatura`, fallback Playwright, `pydantic`,
SQLite or DuckDB, pandas or polars, approved Reddit through `praw`, Google's
YouTube client, and direct GitHub REST or PyGithub.

These are options, not authorized dependencies or architecture. Prefer static
HTTP and structured feeds/APIs; browser rendering is fallback. No collector,
schema, interface, database, score, or runner is implemented or selected by
this context task.

## Confirmed Project Facts

- User supplied an ideal Distribution and Community Evidence specification and
  a practical API-availability assessment.
- Inputs are durable planning context, not collected audience or market
  evidence.
- Practical assessment narrows ideal coverage to cheap, public, structured, and
  auditable sources while preserving explicit unknowns.
- No distribution/community evidence has been collected yet.
- Current task authorizes cluster guidance and scaffold updates only; no
  collection, transformation, scoring, dependencies, or public Python interface.
- Future derived findings must remain linked to raw evidence IDs.

## Assumptions

- Cluster ID is `distribution_community`, matching repository category naming
  and the profile heading “Distribution and Community Evidence.”
- Initial practical scope is public, permitted, English-language research unless
  a future run specifies locale/language differently.
- Access notes, prices, quotas, and platform policies are time-sensitive and
  require official-source verification at implementation time.
- Ideal thresholds and labels are provisional heuristics requiring real-sample
  calibration.

## Hypotheses

- Repeated recent items from independent authors are more useful than community
  membership size for finding inspectable early-user surfaces.
- Exact role + workflow + problem language across independent surfaces may
  indicate a narrower reachable audience than broad topic popularity.
- Combining conversation and search/store evidence may reduce false negatives
  for problems that users discuss little but search for directly.
- Separate policy and visibility fields may prevent relevant but inaccessible
  groups from being mislabeled as practical channels.
- Distinct-repository recurrence on GitHub may reveal cross-product pain rather
  than one product's isolated support issue.
- Creator/tutorial/workaround activity on YouTube may expose public UGC and
  audience nodes without implying a reachable-user count.

## Open Questions

- Which problem, audience entity, canonical phrases, aliases, and locales seed
  first research run?
- What shared runner contract, JSONL schemas, and stable ID convention will
  govern all cluster modules?
- Which source credentials, budgets, official terms, retention/deletion duties,
  and rate limits will be approved when implementation starts?
- What relevance-review process and sample sizes will govern 30/90-day counts,
  medians, and top-N marketplace results?
- How should deleted, anonymous, renamed, or cross-posting authors affect unique
  author and recurrence counts?
- Which independent surface types are sufficient before an aggregate label can
  be useful without becoming a hidden opportunity score?
- How should explicit rules be normalized without inventing promotion safety?
- What minimum evidence supports role/workflow/problem specificity across
  surfaces?
- When should YouTube and Apple enter after core public discussion adapters?
- Will Reddit access be approved under terms compatible with this private
  side-income research use?
- Which public-page adapters are worth brittleness risk for Chrome and Shopify?

## Decisions and Superseded Guidance

- **2026-08-15 — Practical access scope narrows ideal channel coverage.** Core
  MVP uses Brave discovery, Stack Exchange, GitHub, Discourse, RSS/Atom, Hacker
  News, evidence storage, and manual review. YouTube and Apple follow. Reddit is
  conditional; Chrome/Shopify are experimental; Etsy/Product Hunt/Discord and
  manual keyword imports are later or vertical-specific.
- **2026-08-15 — Several ideal channels are excluded from automated MVP.**
  Facebook Group posts, TikTok research, private Discord/Slack messages, Quora
  crawling, exact newsletter subscribers, and automated outreach/promotion
  analysis are not MVP dependencies.
- **2026-08-15 — Complete counts become bounded samples.** Ideal
  `competitor_listing_count` becomes `relevant_results_in_top_n` with
  `top_n_sample_size`; all-time similar-post counts become 30/90-day samples;
  visible member counts remain optional direct observations.
- **2026-08-15 — Search volume remains nullable.** Google Ads automation is
  deferred; manual Keyword Planner or Trends imports may be added later. Missing
  search volume cannot count as absent demand.
- **2026-08-15 — Policy stays explicit and manual.** Ideal automated moderation
  strictness and promotion-risk labels are superseded for MVP by captured rules,
  access friction, allowed/conditional/banned/unknown states, and manual review.
- **2026-08-15 — Surface discovery and factual evidence are separate.** Brave
  locates URLs. Underlying sources support counts, excerpts, engagement, and
  policy claims.
- **2026-08-15 — Unknown is a first-class outcome.** Private, unsupported,
  denied, unavailable, and uncollected data must not become zero or no demand.
- **2026-08-15 — Ideal aggregate labels remain provisional review aids.** They
  may organize evidence only if component surfaces, rules, missing inputs, and
  evidence IDs remain visible. They cannot become market proof or an opportunity
  score.
- No earlier cluster-specific guidance existed to supersede.

## Context Change Log

- **2026-08-15:** Created cluster context from supplied ideal specification and
  practical API-availability assessment. Source documents were not copied into
  cluster; no evidence, collection logic, dependencies, or scoring were added.
