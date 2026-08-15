# Community and Publishing Sources

## GitHub

- **Role in project:** Software problems, issues, discussions, feature requests,
  workarounds, repeated failures, maintenance, repositories, and linked
  competitor activity.
- **Fields:** Repository numeric ID/name, issue number/node ID, title, body,
  state, author, timestamps, labels, reactions, comments, pull-request status,
  releases, archive state, stars, and forks when relevant.
- **Access:** Official REST or GraphQL APIs. Supplied snapshot reports 60
  unauthenticated and 5,000 authenticated REST requests per hour, with tighter
  search limits.
- **Limitations:** Developer-facing, open-source, and technically engaged bias.
  Preserve issue/comment relationships and source-native metrics.
- **Project status:** Core structured source.
- **Last verified:** Not yet independently verified. Planning snapshot:
  2026-08-15.
- **Source:**
  <https://docs.github.com/en/rest/using-the-rest-api/rate-limits-for-the-rest-api>

## Stack Exchange

- **Role in project:** Repeated questions, unresolved demand, answers,
  workarounds, tags, professional workflows, and related terminology.
- **Fields:** Site, question/answer/comment IDs, title, body, tags, votes, views,
  answer state, accepted answer, author, dates, paging, quota, and backoff.
- **Access:** Official API. Supplied snapshot reports a common 10,000-request
  daily quota with registered key and required dynamic backoff handling.
- **Limitations:** Audience and relevance differ by site. Preserve relational
  context and never equate views or votes with demand.
- **Project status:** Core structured source.
- **Last verified:** Not yet independently verified. Planning snapshot:
  2026-08-15.

## Hacker News

- **Role in project:** Technical/operator problems, founder discussion, product
  commentary, and public community discovery.
- **Interfaces:** Algolia may discover stories/comments; official Firebase API
  hydrates known item trees.
- **Fields:** Item, parent, and root IDs; type, author, title, text, URL, score,
  timestamp, children, descendants, deleted/dead state.
- **Limitations:** Technology- and founder-heavy audience. Flattening comments
  can erase reply meaning. Supplied notes report no stated official API rate
  limit; reverify.
- **Project status:** Core or supplemental depending on cluster.
- **Last verified:** Not yet independently verified. Planning snapshot:
  2026-08-15.

## Discourse

- **Role in project:** Public niche forums, especially non-developer domains,
  recurring questions, community activity, tags, and rules.
- **Interfaces:** Prefer public JSON or RSS over rendered HTML.
- **Fields:** Topics, replies, views, likes, authors, categories, tags, activity
  dates, rules, and public directory data when enabled.
- **Limitations:** Access, limits, and enabled interfaces vary by community. Use
  an explicit allowlist and preserve site-specific policy.
- **Project status:** Core curated source family.
- **Last verified:** Per-site verification required at collection time.

## RSS and Atom

- **Role in project:** Open collection from blogs, newsletters, forums,
  changelogs, and publications.
- **Fields:** Feed URL, GUID or item ID, item URL, title, author, dates, summary,
  position, ETag, Last-Modified, and raw feed payload.
- **Limitations:** Feeds may contain partial text or short history. Record text
  completeness and retrieval metadata.
- **Project status:** Core source family.
- **Last verified:** Per-feed verification required.

## WordPress and WordPress.org

- **Role in project:** Compatible REST comments, RSS/Atom, plugin metadata,
  public reviews/support pages, compatibility complaints, and update evidence.
- **Limits:** Use only interfaces publicly exposed by each site. Do not promise
  universal blog-comment access or complete support history.
- **Project status:** Opportunistic source; WordPress.org product/support
  analysis is later than initial structured collectors.
- **Last verified:** Per-site verification required.
- **Source:** <https://codex.wordpress.org/WordPress.org_API>

## YouTube

- **Role in project:** Creator/tutorial niches, workarounds, reviews, public UGC,
  audience nodes, and comments when the domain depends on video.
- **Fields:** Videos, channels, dates, descriptions, views, likes, comments,
  subscriber counts, and distinct channels.
- **Access:** Official Data API. Supplied notes describe 10,000 daily quota units
  and, after 2026-06-01, 100 `search.list` calls/day; verify before use.
- **Limitations:** Comments can concern presentation rather than product use.
  Views and subscribers are context, not reachable-user counts.
- **Project status:** Next-phase source, not core dependency.
- **Last verified:** Not yet independently verified. Planning snapshot:
  2026-08-15.

## Direct Public Pages

- **Role in project:** Product, pricing, changelog, documentation, policy,
  support, comparison, and selected evidence pages.
- **Access:** Static HTTP first; selective main-text extraction. Browser
  rendering only when material dynamic content or proof screenshots require it.
- **Preservation:** Requested/final URLs, redirects, status, headers, title,
  canonical URL, raw response hash, extracted-text hash, parser version,
  capture time, and source-policy version.
- **Limitations:** Public access and `robots.txt` do not settle storage,
  commercial-use, republication, or legal permission. Avoid whole-site crawling.
