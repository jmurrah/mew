# Distribution and Community Evidence

- **Cluster ID:** `distribution_community`
- **Python module:** `distribution_community.py`
- **Layer:** Market evidence

Shared rules: [Evidence Contract](../../docs/core/evidence-contract.md).
Field catalog: [Cluster Records](../../docs/schemas/cluster-records.md#distribution-community).

## Purpose

Find inspectable public surfaces where likely early users gather, search,
discuss, compare tools, or can plausibly be reached with little distribution
infrastructure. Measure observable reachability and access constraints, not
market validation, audience size, or a go-to-market plan.

## Scope

- Public, permitted communities, forums, search surfaces, marketplaces, feeds,
  publications, creators, tags, categories, launch contexts, and known invites.
- Surface identity, query, locale, visibility, access method, interaction mode,
  audience description, and capture time.
- Relevant activity in bounded 30/90-day windows, authors, latest activity,
  replies, reactions, views, and repeated problem language.
- Explicit questions, complaints, solution requests, recommendations,
  comparisons, workarounds, tutorials, and creator coverage.
- Public rules for joining, posting, linking, promotion, listing, or eligibility.
- Top-N search/marketplace samples and public audience-node observations.

## Out of Scope

- Total audience, reachable-user population, conversion, acquisition forecasts,
  product-channel fit, opportunity selection, or outreach plans.
- Automated posting, joining, messaging, sponsorship purchasing, or contactability
  analysis.
- Automated moderation strictness, removal/ban rates, or promotion safety.
- Facebook Group posts, TikTok discussion, private Discord/Slack messages,
  Quora crawling, or aggressive unauthenticated Reddit collection.
- Exact marketplace volume, store impressions, hidden audience identities,
  passive searcher counts, or historical rank before project snapshots.

## Research Unit

One surface observation captures one community, query/result set, marketplace,
feed, publication, creator, tag, category, known invite, or launch context under
recorded access, query, locale, time, and collection bounds.

Reachability classes:

- `conversation_reachable`: post, comment, reply, message, submit, or join under
  visible constraints.
- `search_reachable`: user intent appears through search or marketplace browsing.
- `audience_mediated`: creator, publication, newsletter, or curator provides an
  indirect path.
- `mixed`: several supported modes.
- `passive_only`: visibility without credible interaction, search, or mediated
  path.

## Evidence Model

Important distinctions:

- Activity is stronger than member count.
- Independent repetition is stronger than one viral item.
- Exact role/workflow/problem language is stronger than broad popularity.
- Conversation and search reachability are independent.
- Surface discovery is not hydrated source evidence.
- Visibility is not reachability.
- Problem match and audience match are separate.
- Explicit rules are evidence; absent rules are not permission.
- Private, unsupported, denied, and uncollected do not mean no audience.

Surface families include interactive community, launch/discovery community,
organic search, marketplace search, and audience node. Some surfaces legitimately
span families; preserve interaction mode rather than forcing one generic type.

## Observable Fields

- Surface, evidence, problem/query, run, and source-native IDs.
- Platform, family, name, canonical URL, query, aliases, locale, capture time,
  public visibility, access method, and collection status.
- Interaction modes, audience entity, exact problem/role/workflow excerpts,
  publication/update times, and manual-review state.
- Visible member/online/follower/subscriber counts with source scope.
- Relevant items in 30/90 days, unique source-scoped authors, latest activity,
  and sampled comments/reactions/views.
- Top-N sample size, observed position, relevant-results count, ratings, prices,
  categories, tags, and listing metadata.
- Join/read/search/post/link/message/listing requirements; promotion state;
  rules URL, excerpt, and capture time.
- Raw snapshot, collector/parser version, access limits, failures, and missing
  reasons.

## Derived Fields

- Problem match, audience match, and specificity.
- Conversation/search/audience-mediated/passive reachability.
- Relevant activity, author diversity, recurrence, and sampled engagement.
- Question, complaint, workaround, recommendation, and solution-request types.
- Relevant-results share inside one explicit top-N sample.
- Discussion, engagement, specificity, per-surface distribution, and aggregate
  distribution labels.

Every label retains rule/version, raw inputs, missing inputs, evidence IDs, and
manual-review status.

## Analysis

### Provisional Labels

- **Strong surface:** Practical access, repeated recent discussion or search
  intent, medium/high specificity, and no explicit prohibitive access rule.
- **Medium:** Evidence exists but activity is sporadic, specificity is weak, or
  access/rules reduce reachability.
- **Weak:** Evidence is size-only, stale, broad, passive, or visibility-blocked.
- **Strong aggregate:** Two independent strong surfaces, or one strong
  conversation surface plus one strong search/store surface.
- **Medium aggregate:** One strong surface or at least two medium surfaces.
- **Weak aggregate:** Shallow, stale, generic, or policy-blocked evidence.

These are unvalidated review aids. MVP does not automate promotion-risk
judgment; policy remains explicit fields plus manual review.

### Failure Modes

- Large size metrics with little current problem-specific activity.
- One viral thread or launch spike treated as recurrence.
- Broad entertainment/information interest treated as solution intent.
- Search snippets or result estimates treated as verified counts.
- Public group name treated as access or promotion permission.
- Overlapping/cross-posted items counted independently.
- Private communities, vocabulary mismatch, silent search/store behavior, and
  source bias hiding real reachability.

Report `no public evidence found under recorded access and queries` or
`insufficient coverage`, never `no audience exists`.

## Source Applicability

First release uses Brave discovery, Stack Exchange, GitHub, Discourse, RSS/Atom,
Hacker News, evidence storage, and manual review. YouTube and Apple follow.
Reddit is conditional; Shopify/Chrome parsers are experimental; Etsy, Product
Hunt, known Discord invites, and manual keyword imports are later or
vertical-specific.

See [Search Providers](../../docs/sources/providers/search.md),
[Community Sources](../../docs/sources/providers/communities.md),
[Marketplace Providers](../../docs/sources/providers/marketplaces.md), and
[Restricted Sources](../../docs/sources/providers/restricted.md).

GitHub recurrence across repositories is stronger than repetition inside one
support queue. Hacker News and Product Hunt are founder/technology biased.
YouTube views may show broad interest but not reachability. Store queries expose
intent without public conversation.

## Guardrails

- Preserve exact windows, samples, queries, medians, and evidence IDs.
- Keep visible counts source-scoped and timestamped.
- Derive policy only from explicit captured rules or direct access responses.
- Record unavailable, private, unsupported, denied, and not-collected separately.
- Never convert size proxies into market size or reachable-user counts.

## Output Contract

Future output should contain surface observations, evidence artifacts, rules and
openness observations, and one bounded cluster summary. It exposes reachability,
specificity, activity, access, policy, uncertainty, and raw IDs without selecting
a channel or opportunity. Output feeds section 7 of the investigation profile.

## Open Questions

- Which problem, audience, aliases, and locales seed first collection?
- What relevance process governs 30/90-day counts and top-N samples?
- How should deleted, anonymous, renamed, or cross-posting authors affect
  recurrence?
- What evidence supports aggregate labels without becoming hidden scoring?
- When should YouTube, Apple, Reddit, Chrome, or Shopify enter active scope?
