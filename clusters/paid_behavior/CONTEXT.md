# Cluster Context: `paid_behavior`

This file distills the supplied Paid Behavior Evidence specification and its
July 2026 practical API-availability assessment. Both inputs are design context,
not collected market evidence.

## Identity

- **Cluster ID:** `paid_behavior`
- **Display name:** Paid Behavior Evidence
- **Python module:** `paid_behavior.py`
- **Purpose:** Determine whether observable public evidence shows that money is
  already offered or exchanged for products near the same job, pain, workflow,
  or audience.

## Central Research Question

Does an inspectable money trail already exist near this problem, and what does
public evidence reveal about offer type, price, billing model, traction proxies,
market proximity, and payer dissatisfaction?

This is narrower than asking whether a product should be built. The cluster
organizes public evidence; it does not prove total demand, market size,
profitability, or future willingness to pay.

## Scope

### Included

- Public paid offers for software, apps, extensions, plugins, templates,
  spreadsheets, calculators, digital downloads, communities, courses, and
  service-adjacent workflow products.
- Direct and adjacent products addressing the same job, pain, workflow, or
  audience.
- Exact displayed prices, original and discounted prices, currencies, billing
  cadences, free tiers, trials, subscriptions, one-time purchases, lifetime
  offers, usage-based billing, IAP, and pay-what-you-want offers.
- Public traction proxies: ratings, reviews, installs, users, members, visible
  listing sales, seller-level sales, and seller-level reviews, with their native
  scope preserved.
- Reviews or complaints containing explicit payment, subscription, renewal,
  refund, cancellation, price, or value language.
- Seller, product, source, and marketplace diversity around a research query.
- Search and vendor-page discovery needed to find public pricing evidence.
- Raw source links, excerpts, response or page snapshots, capture dates,
  parser metadata, and collection limitations needed for audit.

### Excluded

- Product selection, app ideas, go/no-go decisions, build plans, validation
  plans, or claims that a gap should be pursued.
- Exact revenue, MRR, ARR, per-listing sales, paying subscribers, free-to-paid
  conversion, trial conversion, churn, retention, refund rate, average revenue
  per user, customer acquisition cost, or revenue by plan unless a primary
  source explicitly discloses them.
- Estimates presented as observed facts.
- A single opportunity score or opaque willingness-to-pay score.
- Claims of complete marketplace coverage, exact market-wide seller counts, or
  historical prices before this project begins taking snapshots.
- Proof that a reviewer paid unless the source or review explicitly supports
  that conclusion.
- Initial automated coverage of Gumroad, Notion Marketplace, paid communities,
  G2, Capterra, or Etsy. Etsy is planned shortly after the core MVP; the others
  are deferred.

All nine profile sections remain required. This cluster primarily contributes
to Paid Behavior Evidence; other sections stay empty unless collected records
genuinely support them.

## Canonical Terminology

- **Public paid-offer evidence:** A publicly visible price or monetization model.
  It proves an offer exists, not that anyone purchased it.
- **Observable paid behavior:** Public evidence of actual exchange or buyer
  behavior, such as a verified-buyer review, explicit payer statement, renewal
  account, or correctly scoped public sales count.
- **Direct paid behavior:** Payment evidence for essentially the same product or
  job.
- **Adjacent paid behavior:** Payment evidence for a neighboring tool, format,
  service, template, community, or workaround serving the same workflow or
  audience.
- **Paid complaint behavior:** Feedback from an explicit or source-verified
  payer about price, value, subscription shape, renewal, cancellation, or
  refund.
- **Exact versus adjacent:** Relationship between observed product and research
  target: `exact`, `adjacent`, or `broad_category`. This is separate from
  whether payment was merely offered or actually evidenced.
- **Traction proxy:** Public rating, review, install, user, member, or seller
  count. It does not equal active or paying users.
- **Monetization presence:** Evidence that payment is available, such as an IAP
  flag or pricing page. It does not establish conversion.
- **Price resistance:** Complaint about price without proof of purchase. Useful,
  weaker than feedback from an explicit payer.
- **Price-model mismatch:** Evidence that value exists but buyers reject the
  billing form, such as recurring payment rather than one-time purchase.
- **Existing budget container:** Evidence that buyers already spend on some
  version of the workflow, even when no exact product match exists.
- **Source observation:** One captured listing, product page, pricing page, or
  review record at a specific source and time.
- **Planning context:** Supplied specifications, API notes, proposed fields,
  thresholds, and architecture options. It is not market evidence.

## Evidence Model

### Core Evidence Distinctions

Preserve three evidence buckets from the ideal specification:

1. **Direct paid behavior:** people appear to pay for the same product or job.
2. **Adjacent paid behavior:** people appear to pay for neighboring tools,
   templates, services, communities, or workarounds.
3. **Paid complaint behavior:** an existing payer complains about price,
   subscription shape, limits, renewal, cancellation, refund, or fit.

Do not encode those as one mutually exclusive field. `exact_vs_adjacent` and
payment or complaint status answer different questions. A paid complaint can
also be direct or adjacent.

### Evidence Strength

From strongest to weaker public signals:

- Explicit payer language with specific price, cadence, renewal, purchase, or
  refund detail.
- Source-verified buyer review or correctly scoped listing-level sales count.
- Positive payer value language such as `worth it` or `good value`.
- Visible paid price plus substantial source-native traction proxies.
- Visible paid price without transaction evidence.
- IAP, subscription, or premium flag without visible price or buyer evidence.
- Cost complaint without proof of purchase.
- Free product popularity without monetization evidence.

This ordering guides inspection only. No item independently proves broad demand.

### Why Nearby Paid Evidence Matters

Problem complaints establish pain, not payment. Nearby products can show an
existing budget container and reveal accepted pricing forms. Adjacent formats
also prevent a false conclusion that nobody pays when buyers currently use
templates, spreadsheets, extensions, communities, or services instead of
software.

## Practical Source Strategy

The practical July 2026 assessment supersedes the ideal specification's broad
source coverage for initial collection. Official APIs are preferred where they
expose public competitor data; public HTML is used where no catalog API exists;
one low-cost search API discovers vendor pricing pages.

### Core MVP Sources

#### Apple App Store

- Proposed method: official iTunes Search API with `media=software`.
- Capture: app ID, title, developer, App Store URL, category, upfront price,
  currency, release/update metadata when returned, search rank, and storefront.
- Strength: reliable catalog discovery and upfront-price evidence.
- Limits: no paying-user count, revenue, subscription conversion, full plan
  details, lifetime sales, or dependable historical pricing.
- Optional later enrichment: public product-page IAP names and prices. This
  must not be a v1 dependency.
- Planning snapshot reports a maximum of 200 results per query, roughly 20
  calls per minute, free access, high API reliability, medium product-page
  enrichment reliability, and caching guidance. Reverify before use.

#### Google Play

- Proposed method: unofficial Python package `google-play-scraper` because the
  official Android Publisher API is for authorized publisher access, not broad
  public competitor research.
- Capture: package ID, title, URL, developer, category, rating, rating count,
  written review count, install range, upfront price, currency, free/paid flag,
  IAP presence and displayed range, ads flag, release/update date, review text,
  review date and rating, and search rank.
- Strength: broad combination of discovery, traction, monetization flags, and
  review text.
- Limits: unofficial parser; page changes can break collection. IAP presence
  proves only that purchases are offered.
- Planning snapshot classifies this route as free with medium reliability.
- Required operational metadata when later implemented: caching, conservative
  rates, retry/backoff, tests against known apps, and `collection_status` such
  as `success`, `partial`, or `parser_failed`.

#### Shopify App Store

- Proposed method: direct public HTML parsing. Start with normal HTTP requests;
  use browser automation only for specific client-rendered sections.
- Capture: title, URL, developer, category, free-plan flag, trial flag and
  duration, visible plan names, plan prices, billing cadence, usage-based
  language, rating, review count, rating distribution when shown, review text,
  review date, reviewer country, usage duration, related apps and their visible
  prices/review counts, and launch date.
- Strength: explicit plans and billing terms plus merchant reviews make this the
  strongest planned public paid-offer source.
- Limits: no documented public search-and-analysis catalog API; parser health
  depends on page structure.
- Planning snapshot classifies direct HTML access as free with medium-high
  reliability.

#### Chrome Web Store

- Proposed method: parse public listings, capture vendor website, then inspect
  likely external pricing pages.
- The official Chrome Web Store API serves publishers managing their own items;
  it is not a public competitor-catalog API.
- Capture: extension ID, title, URL, developer, category, displayed users,
  rating, rating count, last update, IAP flag, vendor website, description, and
  free/premium language.
- Vendor follow-up paths may include `/pricing`, `/plans`, `/upgrade`, `/pro`,
  and `/premium`.
- Strength: distribution and traction evidence plus route to external pricing.
- Limits: displayed users may represent installs, not active users. IAP presence
  does not reveal paying users, conversion, or revenue.
- Preserve separately: distribution signal, monetization presence, and unknown
  paid-user count.
- Planning snapshot classifies public listing data as free and medium-high
  reliability; external pricing discovery is medium reliability.

#### General SaaS and Standalone Tools

- Proposed method: low-cost web-search API plus vendor pricing-page parsing.
- Default candidate from supplied notes: Brave Search API. Tavily is an optional
  search/extraction fallback. Pricing and credits are volatile and must be
  rechecked.
- July 2026 snapshot reports Brave Search at $5 per 1,000 requests with $5 in
  monthly credits, and Tavily at 1,000 free monthly credits without requiring a
  card. These figures are not current guarantees.
- Capture: vendor, product, pricing URL, plan names, exact price text, parsed
  price, currency, monthly/annual cadence, annual discount, per-user pricing,
  usage-based pricing, free tier, free trial, one-time/lifetime purchase, custom
  or contact-sales flag, supporting pricing snippet, and capture date.
- Extraction order: structured data where available, rule-based price parsing,
  pricing-section detection, optional model classification, preserved raw text
  or HTML for verification.
- Limits: no shared schema; hidden enterprise pricing and cross-platform web
  monetization cause false negatives.

### Phase 1.1 Source

#### Etsy

- Proposed method: official Etsy API plus limited public-page parsing where
  permitted.
- Capture: listing title and URL, current and original price, discount, shop,
  seller, digital-download flag, listing review count, shop review count, public
  shop total sales, category/tags, and seller diversity.
- Scope rule: shop sales remain seller-level. Never attribute them to a specific
  listing.
- Example interpretation form: a listing exists at a visible price, has a stated
  listing review count, and its seller has a stated shop-level sales count.
- Additional API approval, rate-limit, and scope work makes Etsy a next-phase
  source rather than an initial dependency.
- Planning snapshot reports an API key for all calls, OAuth for private or write
  operations, app-specific per-second and daily quotas, caching, and backoff.

### Deferred Initial Sources

- **Gumroad:** inconsistent discovery, indexing, sales visibility, review
  visibility, and page structure; no dependable marketplace-wide public API.
- **Notion Marketplace:** public discovery and page parsing may find templates,
  but price, review, and seller metadata are too inconsistent for a dedicated
  initial collector.
- **Paid communities such as Skool:** displayed price and member totals may be
  visible, but member counts can mix free, trial, grandfathered, inactive, and
  paid accounts; pages may be dynamic.
- **G2 and Capterra:** valuable for manual research, but broad collection has
  access, freshness, protection, pagination, scale, and maintenance costs.
- **Google Custom Search JSON API:** rejected as a new-project foundation by the
  supplied July 2026 notes because new access and retirement timing make it
  unsuitable. Reverify if reconsidered.

Deferred does not mean valueless. It means not required for the cheapest useful
initial pipeline.

### Discovery Query Patterns

Candidate search forms supplied for future implementation:

```text
"{query}" pricing
"{query}" software pricing
"{query}" app pro
"{query}" subscription
"{query}" lifetime
"{query}" template price
site:apps.shopify.com "{query}"
site:chromewebstore.google.com "{query}"
site:etsy.com "{query}"
site:gumroad.com "{query}"
site:notion.com/templates "{query}"
```

Deferred source queries may still support manual discovery; they do not imply
an automated collector belongs in the initial MVP.

## Evidence-Row Guidance

Each discovered listing, product, pricing page, or marketplace observation
should remain independently inspectable. Review records may be separate raw
records linked to their product observation; schema choice remains open.

### Identity and Provenance

- `query_id`, `query_text`, `evidence_id`
- `source_type`, `marketplace_name`, `source_url`, `product_url`
- `product_title`, `product_kind`, `seller_name`, `seller_url`
- `audience_tag`, `workflow_tag`, `exact_vs_adjacent`
- Search query, search rank, storefront/country, collection method
- Capture timestamp, publication/update date when available
- Raw payload path, content hash, parser version, collection status
- Manual confidence or inspection note

Stable evidence IDs must link normalized rows, review labels, query aggregates,
profile statements, and raw artifacts.

### Price and Monetization

- `price_display_raw` plus nullable parsed `price_amount`
- Currency and billing period
- Subscription, one-time, usage-based, free-plan, free-trial, lifetime,
  template/download, IAP, discounted, and pay-what-you-want indicators
- Original price when visibly discounted
- Human-readable monetization notes

Suggested billing values from supplied guidance include `one_time`, `weekly`,
`monthly`, `yearly`, `annual_commitment`, `usage_based`, `free`, `freemium`,
`free_to_install`, `pay_what_you_want`, and `unknown`.

Always preserve both raw and parsed representations, for example:

```text
price_raw = "$15 / month"
price_amount = 15.00
billing_period = "monthly"
```

### Traction and Social Proof

- Rating value and scale
- Rating and review counts, kept separate when the source separates them
- Visible listing-level sales or range
- Displayed installs, users, or downloads in source-native text
- Visible member count
- Seller-level total sales and reviews with explicit seller scope
- Last-updated or launch date when visible

Do not normalize unlike metrics into one engagement or traction score. Keep
marketplace semantics and visibility limits attached.

### Review and Complaint Evidence

Initial complaint sources should prioritize Google Play and Shopify App Store.
Public SaaS reviews or testimonials on product/pricing pages may be retained
with source-bias notes. Broad marketplace complaint classification is deferred.

Candidate discovery terms:

```text
paid
subscribed
subscription
renewed
renewal
charged
refund
cancel
monthly
annual
yearly
lifetime
one-time
worth it
too expensive
price increase
free plan
paywall
```

Candidate review labels:

- `explicit_payer`
- `price_too_high`
- `subscription_model_rejected`
- `requested_one_time_purchase`
- `renewal_problem`
- `refund_problem`
- `positive_value_statement`
- `free_tier_sufficient`

Preserve raw review ID, product evidence ID, source URL, review text/excerpt,
review date, rating, classification method, confidence, and supporting snippet.
NLP labels are indexes, never proof.

### Derived Fields

Medium-feasibility fields need method, confidence, and support:

```text
derived_label
classification_method
classification_confidence
supporting_snippet
source_url
```

Examples include arbitrary-site plan extraction, annual discounts, usage-based
pricing, lifetime options, payer or value classification, subscription
resistance, seller deduplication, cross-platform product matching, and
price-sensitive-market labels.

## Query-Level Measures

Potential rollups from evidence rows:

- Paid and free-only product counts
- Unique paid sellers
- Source types containing paid evidence
- Minimum, median, maximum, and interquartile paid prices
- Subscription, one-time, usage-based, lifetime, free-trial, template, and
  community counts
- Rows with visible public sales/member/install/user signals
- Total ratings and reviews across qualifying paid rows
- Paid rows above a documented source-native social-proof threshold
- Explicit-payer, price, subscription, refund, and positive-value review counts
- Exact and adjacent paid counts
- Adjacent source diversity, median price, and social-proof distribution
- Coverage, parser-failure, missingness, and duplicate indicators

Do not sum or compare source-native metrics without exposing their meanings.
Seller and same-product deduplication must remain auditable and uncertain.

## Interpretation Rules

### Offer Evidence Versus Payment Evidence

- Listed price: an offer exists.
- IAP flag: monetization exists.
- Rating or review: product use and engagement proxy; payment unknown unless
  source or text establishes it.
- Install or user count: distribution proxy; active and paid users unknown.
- Verified-buyer review: stronger transaction evidence within source rules.
- Explicit payer review: strong payment evidence for that reviewer.
- Shop total sales: seller-level transaction evidence, not listing sales.

Recommended truthful umbrella label: **Public paid-offer evidence**. Avoid
**Proven willingness to pay**.

### Payment and Price Resistance

- Explicit purchase, subscription, renewal, or lifetime purchase plus positive
  or negative feedback: strong payment evidence.
- `Too expensive` without purchase evidence: weak price-resistance signal.
- `Worth it`, `good value`, or a specific reasonable-price statement from an
  apparent payer: positive paid signal.
- `Useful, but not worth a subscription`: value may exist; pricing-model mismatch
  is plausible.
- `Should be one-time`: willingness to pay may exist; recurring aversion is
  plausible.
- `I use the free plan only`: weak paid evidence unless upgrade behavior or paid
  features are discussed.

Use `may` for interpretations. Raw text remains proof; labels remain inference.

### Subscription Complaints

Preserve at least these distinctions:

- `too_expensive`: buyer may pay, but visible price exceeds comfort.
- `should_be_one_time`: value may be recognized while recurring form is
  rejected.
- `hidden_renewal_or_cancel_friction`: payment exists; trust or packaging may be
  the issue.
- `not_enough_ongoing_value`: outcome may have value, but recurring delivery may
  not.

Subscription complaints are not automatically negative demand evidence.

### Free-Only and Price-Sensitive Markets

Many free offers do not prove a free-only market; freemium products can still
monetize. A defensible free-only observation requires documented multi-source
search with no meaningful paid evidence plus visible free/freemium supply.

Price sensitivity may be suggested by low visible price bands, heavy discounts,
pay-what-you-want offers, or recurring-price complaints. Category norms matter;
no universal low-price threshold is established.

### Adjacent Payment

Weak exact paid evidence plus diverse adjacent paid formats may indicate a
format mismatch. It does not by itself prove an open gap. Preserve exact and
adjacent counts, sources, prices, social proof, and examples separately.

## Proposed Labels and Heuristics

The ideal specification proposed `strong_paid_behavior`,
`medium_paid_behavior`, `weak_paid_behavior`, `free_only_market`,
`adjacent_paid_market`, `subscription_resistant`, and `low_ticket_market` as
auditable workflow aids.

Proposed starting heuristics included:

- Strong: at least three unique paid sellers, at least two source types, plus
  public traction evidence or strong review volume on paid offers.
- Medium: at least two sellers with visible pricing, but weaker traction or one
  main source type.
- Weak: one or two paid offers with low social proof, or vague price mentions.
- Free-only: no meaningful paid rows across at least three source types plus at
  least five free/freemium rows.
- Adjacent paid: multiple adjacent paid rows but few or no exact paid rows.
- Subscription-resistant: recurring pricing is common while explicit
  subscription complaints are comparatively high and one-time/lifetime
  alternatives receive stronger sentiment.
- Low-ticket: paid evidence exists, but observed prices are low for the category
  and discounts or pay-what-you-want models are common.

These are unvalidated design hypotheses. Do not implement them as truth, an
opportunity score, or a build decision. If later authorized, expose every input,
coverage limit, override, and supporting evidence ID.

## False Positives

- Free app with IAP and many downloads mistaken for many paying users.
- Chrome displayed users mistaken for active users or subscribers.
- Etsy shop-level sales assigned to one listing.
- Ratings or reviews assumed to come from paying users without source support.
- App Store ratings compared across territories or across a rating reset.
- Marketplace listing abundance treated as demand without pricing, seller
  diversity, or traction evidence.
- Cheap copycat supply, SEO arbitrage, or long-tail clutter treated as demand
  concentration.
- Vendor-selected testimonials treated like independent reviews.
- One incumbent, seller, storefront, or marketplace dominating a rollup.
- IAP or subscription presence treated as revenue or conversion evidence.

## Expected False Negatives

- Chrome extensions or mobile products monetize on vendor websites.
- Enterprise SaaS hides pricing behind demo or contact-sales forms.
- Hybrid web/store monetization is invisible on marketplace listings.
- Community price or access is hidden behind login, waitlist, or paywall.
- Buyers pay for adjacent templates, spreadsheets, communities, services, or
  courses while app-only searches appear empty.
- Private contracts, internal purchases, and unindexed products remain unseen.
- Search, pagination, geography, personalization, and marketplace caps omit
  products.

Absence means no public evidence was found within documented coverage, never
that no payment exists.

## Minimum Useful Initial Dataset

Highest-value fields from supplied guidance:

- Exact raw price, parsed amount, currency, and billing period
- Source type, marketplace, product kind, query, rank, and storefront
- Product and seller identity
- Unique paid sellers and source diversity
- Rating/review counts and native traction visibility
- `exact_vs_adjacent`
- Subscription, one-time, usage-based, lifetime, free, trial, template, and IAP
  indicators where visible
- Explicit payer and paid-complaint evidence
- Product-level counts for paid complaints, explicit-payer reviews, price
  complaints, subscription complaints, refund complaints, and positive-value
  statements when derived from preserved review records
- Evidence URL, snippet, capture date, raw artifact path, and status

Discounts, seller-level sales, positive-value labels, free tiers, and free trials
remain useful where cheaply available.

## Evidence Preservation Standard

Minimum durable proof:

- Stable evidence ID
- Source and product URLs
- Source title and type
- Exact displayed price string
- Decisive source excerpt
- Seller name and metric scope
- Rating/review or traction counts exactly as observed
- Capture timestamp and storefront or locale
- Raw JSON or HTML path when practical
- Content hash and parser version when practical
- Complaint excerpt containing payment language
- Collection status, error, and coverage notes

Public pages change. Apple summary ratings can be territory-specific or reset;
Google reviews can be edited; Chrome and marketplace counts change over time.
Preserve enough local material to explain every later classification without
reacquiring the page. Screenshots are optional for high-value or fragile
evidence, not a universal requirement.

## Nonbinding Technical Context

Supplied materials suggest a hybrid collector using official APIs, targeted
public HTML parsing, and search-assisted pricing discovery. Candidate Python
tools include `httpx`, `BeautifulSoup` or `selectolax`, `google-play-scraper`,
`tenacity`, local HTTP caching, and Playwright only for an explicit dynamic-page
allowlist.

Raw JSON and HTML, CSV/JSONL, SQLite, DuckDB, Parquet, hashes, timestamps, parser
versions, and optional screenshots were suggested preservation and analysis
options. No dependency, storage engine, schema, function interface, or runner
contract is selected by this context update. Root project rules favor local,
inspectable, spreadsheet-friendly files and raw-evidence traceability.

## Volatile Access Notes

All provider access, cost, rate-limit, field, and reliability statements came
from the supplied July 2026 practical assessment. They were not independently
verified during this documentation-only task.

Before implementation or collection, recheck official provider documentation,
terms, robots/access rules, pricing, credits, approvals, rate limits, caching
requirements, retention duties, and returned fields. Recheck unofficial parser
health against known pages. Record verification date rather than encoding
volatile claims as timeless defaults.

## Confirmed Project Facts

- User selected cluster ID `paid_behavior`.
- Display name is `Paid Behavior Evidence`.
- Supplied PDF is ideal guidance; supplied long-form text is the practical July
  2026 API and source-availability constraint.
- Both supplied inputs are planning context, not collected market evidence.
- Practical MVP source scope is Apple App Store, Google Play, Shopify App Store,
  Chrome Web Store, and public SaaS pricing pages.
- Etsy is planned after the initial source set.
- Gumroad, Notion Marketplace, paid communities, G2, Capterra, exact sales,
  revenue estimates, and conversion metrics are excluded from initial scope.
- No paid-behavior evidence has been collected.
- Current task creates guidance and module scaffold only. It does not implement
  collection logic or choose a public Python interface.

## Assumptions

- This cluster is a horizontal evidence capability, not a single market or
  audience cluster.
- Future runs will provide a specific job, pain, workflow, audience, or market
  query.
- `paid_behavior` is the intended durable cluster ID.
- Initial operation should remain private, local, low-cost, and manually
  inspectable.
- Public offers and traction proxies can support research even when actual
  payments remain unknown, provided wording preserves that limit.

## Hypotheses

- Explicit payer behavior is stronger evidence than stated willingness to pay.
- Diverse paid sellers and source types are more informative than many listings
  from one seller or marketplace.
- Paid complaints may reveal monetization plus incumbent mismatch.
- Adjacent paid formats may reveal an existing budget container when exact
  software evidence is weak.
- Shopify may offer the strongest cheap public combination of explicit business
  software pricing and customer reviews.
- Google Play may offer the broadest cheap combination of discovery, traction,
  monetization flags, and review text, despite parser risk.
- Apple and Chrome may require product-page or vendor-site enrichment for useful
  subscription detail.
- Proposed labels and thresholds may aid inspection but require real-data
  calibration.

## Open Questions

- Which market, workflow, audience, or problem query should the first research
  run target?
- Which search provider will be available and acceptable at implementation
  time?
- What exact raw JSONL schema and shared runner contract will the repository
  adopt?
- Should reviews be separate raw records or nested/linkable artifacts of product
  observations?
- What seller and cross-platform product deduplication rules will remain safe
  and manually reversible?
- Which locales and storefronts should initial collection cover?
- What source-native thresholds, if any, help manual review without becoming a
  score?
- What terms and retention constraints apply to HTML snapshots and review text
  for each source at collection time?
- When should Etsy or another deferred source be promoted into active scope?

## Decisions and Superseded Guidance

- **2026-08-15 — Practical source plan supersedes ideal broad coverage for the
  initial MVP.** Use Apple App Store, Google Play, Shopify App Store, Chrome Web
  Store, and vendor SaaS pricing pages first. Add Etsy later. Defer Gumroad,
  Notion Marketplace, paid communities, G2, and Capterra.
- **2026-08-15 — Public evidence wording narrowed.** Visible prices,
  monetization flags, ratings, reviews, installs, and users support `public
  paid-offer evidence` and traction proxies; they do not prove paid conversions
  or market-wide willingness to pay.
- **2026-08-15 — Private metrics excluded.** Unknown revenue, sales, paying-user,
  conversion, churn, and retention values remain unknown rather than estimated
  or recorded as zero.
- **2026-08-15 — Ideal fields retained as guidance, not implementation.** Row
  fields, aggregates, labels, thresholds, storage options, and Python tools are
  nonbinding until shared contracts and real-data calibration exist.
- **2026-08-15 — Market proximity and payment status remain separate.** Preserve
  `exact_vs_adjacent` independently from offer, payer, complaint, and traction
  observations.

## Context Change Log

- **2026-08-15:** Created cluster context from supplied ideal Paid Behavior
  Evidence specification and July 2026 practical API-availability assessment.
  Source inputs were not copied into cluster evidence. No market evidence was
  collected; no collection logic was implemented.
