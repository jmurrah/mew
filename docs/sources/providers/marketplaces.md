# Marketplaces and Product Catalogs

## Apple App Store

- **Role in project:** App discovery, observed search order, product metadata,
  upfront pricing, ratings, versions, updates, descriptions, categories, and
  screenshots.
- **Interface:** Official legacy iTunes Search/Lookup API for catalog metadata.
  Competitor reviews require a bounded, replaceable public or unofficial
  adapter and explicit coverage labels.
- **Fields:** App ID, title, developer, URL, category, price/currency,
  rating/count, version, release/update dates, release notes, screenshots,
  storefront, query, and observed rank.
- **Access notes:** Supplied snapshot reports up to 200 results and roughly 20
  calls/minute. Public review adapters were described as country-specific and
  page-limited, commonly near ten pages.
- **Limitations:** No paying-user count, revenue, conversion, installs, complete
  review history, universal rank, or reliable historical pricing. Ratings can
  be storefront-specific or reset.
- **Project status:** Planned core catalog source; review adapter unresolved.
- **Last verified:** Not yet independently verified. Planning snapshot:
  2026-08-15.
- **Sources:**
  <https://developer.apple.com/library/archive/documentation/AudioVideo/Conceptual/iTuneSearchAPI/Searching.html>,
  <https://developer.apple.com/help/app-store-connect/monitor-ratings-and-reviews/ratings-and-reviews-overview/>,
  <https://github.com/facundoolano/app-store-scraper>

## Google Play

- **Role in project:** App discovery, metadata, monetization flags, install
  buckets, ratings, reviews, versions, updates, and developer replies.
- **Interface:** Official Reviews API applies mainly to publisher-owned apps.
  Current competitor planning uses replaceable unofficial tooling such as
  `google-play-scraper`.
- **Fields:** Package ID, title, developer, category, rating/count, review count,
  install range, price/currency, IAP range, ads/IAP flags, version/update,
  screenshots, review ID/text/date/rating/version/helpful votes/reply.
- **Access notes:** Supplied snapshot describes up to 30 search hits and 200
  reviews per request for common adapter behavior.
- **Limitations:** Parser can break when pages change. Install buckets are not
  active users. IAP proves an offer, not purchase. Samples are not complete
  histories or global representation.
- **Project status:** Planned core source behind a versioned replaceable adapter.
- **Last verified:** Not yet independently verified. Planning snapshot:
  2026-08-15.
- **Sources:**
  <https://developers.google.com/android-publisher/api-ref/rest/v3/reviews>,
  <https://github.com/JoMingyu/google-play-scraper>,
  <https://support.google.com/googleplay/android-developer/answer/138230?hl=en>

## Shopify App Store

- **Role in project:** Business-software plans, billing terms, trials, reviews,
  merchant context, related apps, and explicit paid offers.
- **Interface:** Public HTML. Static HTTP first; selective rendering for
  client-generated sections.
- **Fields:** Product/developer/category, plan names and prices, cadence, free
  plan, trial, usage billing, rating/reviews, distribution, review text/date,
  reviewer country, usage duration, related apps, and launch date when visible.
- **Limitations:** No documented public search-and-analysis catalog API in
  current notes. Parser health depends on page structure.
- **Project status:** Planned core paid-behavior source; experimental for broad
  distribution collection.
- **Last verified:** Not yet independently verified. Planning snapshot:
  2026-08-15.

## Chrome Web Store

- **Role in project:** Extension discovery, displayed users, ratings, category,
  updates, IAP presence, vendor website, and route to external pricing.
- **Interface:** Public listings. Official API is for publishers managing their
  own items, not general competitor history.
- **Limitations:** Displayed users may represent installs rather than active
  users. IAP does not reveal paying users, price, conversion, or revenue. Public
  page parsers remain versioned and replaceable.
- **Project status:** Planned catalog and vendor-discovery source.
- **Last verified:** Not yet independently verified. Planning snapshot:
  2026-08-15.

## Mozilla Add-ons

- **Role in project:** Structured browser-extension metadata and complaint
  analysis.
- **Interface:** Documented public add-on and ratings APIs.
- **Fields:** Add-on metadata, users, versions, grouped rating counts, written
  reviews, pagination, filters, review bodies, and developer replies when
  available.
- **Limitations:** Browser-extension scope; current API behavior and stability
  require verification. Population language requires exhausted pagination and
  complete filters.
- **Project status:** Preferred first structured dissatisfaction collector.
- **Last verified:** Not yet independently verified. Planning snapshot:
  2026-08-15.
- **Sources:** <https://mozilla.github.io/addons-server/topics/api/addons.html>,
  <https://mozilla.github.io/addons-server/topics/api/ratings.html>

## Etsy

- **Role in project:** Adjacent paid templates, downloads, spreadsheets,
  calculators, printables, and other digital products.
- **Interface:** Official Open API after key approval, plus limited permitted
  public-page capture.
- **Fields:** Listing title/URL, current/original price, discount, shop/seller,
  digital-download flag, listing reviews, shop reviews, public shop sales,
  categories, tags, and seller diversity.
- **Limitations:** Shop sales remain seller-level and must never be attributed
  to one listing. Quotas are application-specific.
- **Project status:** Phase 1.1 or vertical-specific, not initial core.
- **Last verified:** Not yet independently verified. Planning snapshot:
  2026-08-15.

## Marketplace Metric Rules

- Preserve storefront, country, language, query, observed rank, capture time,
  collection method, and sample bounds.
- Ratings, reviews, installs, users, IAP flags, prices, and seller totals retain
  source-native scope.
- Visible offer, monetization presence, traction, and observed purchase remain
  separate.
- Do not claim revenue, market share, paying users, conversion, complete review
  coverage, or historical rank from public metadata.
