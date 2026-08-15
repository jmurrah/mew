# Restricted and Deferred Sources

## Reddit

- **Potential role:** General problems, workarounds, complaints, alternatives,
  communities, and public discussion.
- **Constraints in supplied notes:** Approved OAuth access, unique user agent,
  commercial-use uncertainty, deletion reconciliation, retention limits, and
  restrictions on stored or upstream-deleted content. Earlier notes mention a
  100-query-per-minute eligible-free-use limit and guidance favoring short
  retention where appropriate.
- **Project rule:** Do not make Reddit foundational. Confirm current approved
  access, commercial-use terms, retention, deletion, and AI restrictions before
  collection. Search-discovered URLs remain discovery records. Do not train or
  fine-tune models on stored Reddit text.
- **Project status:** Conditional.
- **Last verified:** Not yet independently verified. Planning snapshots:
  2026-07-13 and 2026-08-15.
- **Source:**
  <https://support.reddithelp.com/hc/en-us/articles/16160319875092-Reddit-Data-API-Wiki>

## Commercial Review Platforms

- **G2, GetApp, Software Advice, Trustpilot:** Useful for manual research or
  licensed future access. No stable public competitor-review interface was
  selected.
- **Capterra:** Automated collection excluded. Supplied assessment reports
  prohibitions affecting scraping, automated collection, and some machine-
  learning uses without authorization.
- **Project rule:** Preserve manual URLs and authorized imports with source
  policy and coverage. Never promise complete automated review histories.
- **Last verified:** Not yet independently verified. Planning snapshot:
  2026-08-15.
- **Source:** <https://www.capterra.com/legal/terms-of-use/>

## Product Hunt

- **Potential role:** Launch-event evidence, makers, early adopters, products,
  topics, and engagement.
- **Constraints:** Supplied notes describe public read access but commercial-use
  restrictions requiring separate contact. Upvotes and comments are launch
  evidence, not durable acquisition or end-user fit.
- **Project status:** Optional after permission review; not core.
- **Last verified:** Not yet independently verified. Planning snapshot:
  2026-08-15.

## Social and Private Communities

- **Facebook Groups:** Manual public identity/visibility notes only. No general
  automated post, activity, author, rules, or history collection.
- **TikTok:** No ordinary general research API suitable for this commercial
  context in supplied notes. Manual URLs only.
- **LinkedIn, Instagram, X:** Excluded from MVP automatic collection because of
  access, cost, instability, privacy, and weak-denominator concerns.
- **Discord and Slack:** Known public invite metadata may be captured where
  official access permits. No private message or member analysis without
  explicit authority.
- **Quora:** Search-discovered URLs and manual inspection only; no crawling
  dependency.
- **Project status:** Deferred, manual, or excluded depending on source.
- **Last verified:** Not yet independently verified. Planning snapshot:
  2026-08-15.

## Gumroad, Notion, and Paid Communities

- **Potential role:** Adjacent paid templates, downloads, communities, and
  workflow products.
- **Limitations:** Discovery, page structure, visible price, review, sales, and
  membership semantics are inconsistent. Member counts can mix paid, free,
  trial, grandfathered, and inactive users.
- **Project status:** Deferred from initial automated paid-behavior collection.

## Common Crawl and Browser Automation

- **Common Crawl:** Free but operationally large; deferred to targeted
  historical backfill after core collection proves useful.
- **Playwright:** Selective fallback for high-value dynamic pages, exact visible
  states, or proof screenshots. Never default whole-site collection.
- **Managed extraction services:** Firecrawl was an earlier optional fallback
  for difficult permitted pages; not core infrastructure.
