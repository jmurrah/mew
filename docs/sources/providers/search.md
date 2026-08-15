# Search Providers

## Brave Search

- **Role in project:** Low-cost general discovery, pipeline development,
  competitor/page discovery, and optional corroboration.
- **Supported evidence:** Query, provider rank, title, URL, domain, snippet,
  result type, visible date, and captured Brave result composition.
- **Limitations:** Brave describes its own index. It cannot support claims about
  Google rank, Google ads, Google AI Overviews, or Google result composition.
- **Cost notes:** Supplied snapshot reports `$5` per 1,000 web requests with a
  recurring `$5` monthly credit, roughly 1,000 requests covered monthly.
- **Project status:** Planned core discovery source. Never treat snippets or
  estimated result counts as hydrated source facts.
- **Last verified:** Not yet independently verified. Planning snapshot:
  2026-08-15.
- **Sources:** <https://brave.com/search/api/>,
  <https://api-dashboard.search.brave.com/app/documentation/web-search/responses>

## DataForSEO

- **Role in project:** Planned Google-shaped Organic SERP and Autocomplete
  evidence; optional Google Ads keyword and Google Trends enrichment.
- **Supported evidence:** Provider-returned Google result blocks, ranks,
  snippets, autocomplete, approximate volume, CPC, bid ranges, paid competition,
  and normalized Trends data depending on endpoint.
- **Access:** Standard queue, priority, and live modes were described in supplied
  notes. Queue use requires task submission, later retrieval, retry isolation,
  and raw-response preservation.
- **Cost notes:** Supplied snapshot estimates `$0.0006` per ten-result standard
  SERP, `$1.20` per 1,000 priority captures, and `$2.00` per 1,000 live captures.
  Add-ons and deeper result pages can change cost.
- **Limitations:** Provider normalization may omit or flatten result features.
  Keyword volume may group close variants. Trends values are relative.
- **Project status:** Preferred long-term Google provider in current planning;
  not implemented.
- **Last verified:** Not yet independently verified. Planning snapshot:
  2026-08-15.
- **Sources:**
  <https://dataforseo.com/pricing/serp/google-organic-serp-api>,
  <https://docs.dataforseo.com/v3/keywords_data/google_ads/search_volume/live/>,
  <https://docs.dataforseo.com/v3/keywords_data/google_trends/explore/live/>

## SerpAPI

- **Role in project:** Prototype convenience or emergency replacement when
  clean JSON and specialized engines matter more than price.
- **Cost notes:** Supplied snapshot reports 250 free monthly searches and paid
  pricing starting near `$25` per 1,000 searches.
- **Limitations:** Higher supplied cost than DataForSEO. Provider and legal
  continuity require review before adoption.
- **Project status:** Optional, not default.
- **Last verified:** Not yet independently verified. Planning snapshot:
  2026-08-15.
- **Source:** <https://serpapi.com/pricing>

## Tavily

- **Role in project:** Optional search or extraction fallback for selective
  authoritative-source or pricing-page discovery.
- **Cost notes:** Supplied snapshot reports 1,000 free monthly credits; basic
  search one credit, advanced search two, basic extraction one per five
  successful URLs.
- **Project status:** Candidate fallback only.
- **Last verified:** Not yet independently verified. Planning snapshot:
  2026-08-15.

## Exa

- **Role in project:** Earlier planning candidate for broad public-web discovery
  and page text or highlights, especially workaround research.
- **Cost notes:** July 2026 notes claimed up to 20,000 free requests per month.
- **Project status:** Superseded as default by later Brave/DataForSEO planning;
  remains a replaceable option pending verification.
- **Last verified:** Not yet independently verified. Planning snapshot:
  2026-07-13.

## Google Ads Keyword Data

- **Role in project:** Optional approximate volume, monthly history, CPC, bid,
  and paid-competition enrichment.
- **Limitations:** Volume is not unique people, guaranteed clicks, product
  demand, or market size. Paid competition is advertiser competition, not
  organic difficulty or product saturation. Missing or zero values cannot
  reject an investigation.
- **Access:** DataForSEO or manual Keyword Planner CSV is preferred initially.
  Direct Google Ads API was deferred because supplied notes report manager
  account, developer token, access-level, and permissible-use friction.
- **Project status:** Optional enrichment after core evidence.
- **Last verified:** Not yet independently verified. Planning snapshot:
  2026-08-15.
- **Sources:**
  <https://developers.google.com/google-ads/api/docs/keyword-planning/generate-historical-metrics>,
  <https://developers.google.com/google-ads/api/docs/access-levels>,
  <https://support.google.com/google-ads/answer/7337243?hl=en>

## Google Trends

- **Role in project:** Optional direction, seasonality, and related-query
  enrichment for shortlisted investigations.
- **Limitations:** Values are normalized relative interest, not searches. Zero
  can hide niche or low-volume demand.
- **Access:** DataForSEO, SerpAPI, or manual export are acceptable candidates.
  Unofficial website emulation is nonessential. Supplied notes describe the
  official API as limited-access alpha.
- **Project status:** Deferred optional enrichment.
- **Last verified:** Not yet independently verified. Planning snapshot:
  2026-08-15.
- **Sources:** <https://developers.google.com/search/blog/2025/07/trends-api>,
  <https://support.google.com/trends/answer/4365533?hl=en>

## Retired or Rejected Foundations

- **Google Custom Search JSON API:** Supplied notes say it is closed to new
  customers with an existing-customer transition by 2027-01-01. Do not use as a
  new-project foundation. Source:
  <https://developers.google.com/custom-search/v1/overview>.
- **Bing Search APIs:** Supplied notes say they retired on 2025-08-11. Do not use
  as a new dependency without current evidence.
- **Direct Google scraping:** Rejected as primary collection because CAPTCHA,
  consent, personalization, proxy, reproducibility, policy, and maintenance
  costs outweigh cheap provider use.
- **Ahrefs/Semrush models:** Useful later for acquisition research, not core
  evidence of missing products. Proprietary difficulty and traffic estimates
  remain separate from captured search evidence.
