# Distribution and Community Evidence: Cluster Instructions

- Read `CONTEXT.md` completely before changing this cluster.
- Answer one operational question: if a problem matters, where do likely early
  users visibly gather, search, discuss, compare tools, or become reachable with
  little distribution infrastructure?
- Do not treat this cluster as market validation, market sizing, a go-to-market
  plan, an opportunity selector, or proof that a product should be built.
- Keep four reachability classes distinct: conversation-reachable,
  search-reachable, audience-mediated, and passive-only. A visible audience is
  not necessarily reachable.
- Treat each community, query, marketplace result set, feed, publication,
  creator, or known invite as a separate surface observation. Record exact
  query, platform, URL, locale where relevant, capture time, access method, and
  collection bounds.
- Prioritize repeated recent activity, independent authors, exact role/workflow/
  problem language, engagement depth, explicit solution requests, and visible
  access paths. Member counts, views, broad hashtags, or one viral thread are
  weak alone.
- Keep source discovery separate from source evidence. Brave snippets and
  estimated result counts may locate surfaces but cannot establish activity,
  audience size, policy, or factual counts. Fetch and preserve underlying public
  source when possible.
- Prefer official APIs, public JSON, RSS/Atom, and static public pages. Use
  unsupported HTML parsers only as isolated, versioned, timestamped adapters.
  Never substitute aggressive unauthenticated scraping for unavailable access.
- Initial practical sources are Brave discovery, Stack Exchange, GitHub,
  Discourse JSON/RSS, generic RSS/Atom, and Hacker News. YouTube and legacy Apple
  App Store search are next. Reddit requires approved access; Chrome and Shopify
  public-page parsers remain experimental.
- Exclude automated Facebook Group, TikTok discussion, private Discord/Slack,
  Quora, exact newsletter-subscriber, exact marketplace-volume, passive-searcher,
  DM/contactability, removal-rate, and ban-rate collection from the MVP.
- Treat unavailable, private, unsupported, denied, and uncollected data as
  distinct states. Never turn missing access into zero demand or no audience.
- Preserve exact problem wording, stable evidence IDs, raw URLs, limited
  excerpts, publication and capture dates, visible counts, query text, raw
  snapshots when permitted, collector versions, and manual-review state.
- Keep sample metrics explicit. `relevant_results_in_top_n` needs its sample
  size; recent activity needs its time window; medians need the sampled records;
  every aggregate needs linked evidence IDs and a reproducible denominator.
- Derive policy only from explicit visible rules or directly observed access
  constraints. Save rules URLs and excerpts. Unknown policy remains unknown;
  automated promotion-risk judgment is outside MVP scope.
- Keep `problem_match_level` separate from `audience_match_level`. Views,
  followers, subscribers, repository stars, ratings, or launch upvotes are
  source-specific proxies, not reachable-user or market-size counts.
- Derived discussion, engagement, specificity, reachability, and distribution
  labels are inspection aids only. Store rule/version, raw inputs, missing
  inputs, evidence IDs, and manual-review status. Never collapse this cluster
  into an opportunity score.
- Reverify source access, pricing, quotas, terms, retention limits, and API
  behavior before implementation or collection. Supplied access notes are a
  dated planning snapshot, not collected market evidence.
- Keep future collection, normalization, and annotation logic in
  `distribution_community.py`. Do not invent its public interface before the
  shared runner contract exists.
- Maintain all nine `PROFILE.md` sections. Every future factual profile item
  must cite stable raw evidence identifiers.
