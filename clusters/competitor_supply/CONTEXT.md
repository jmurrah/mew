# Cluster Context: `competitor_supply`

This file stores durable design guidance for the Competitor and Supply Evidence
cluster. It models the supplied ideal specification and practical API-access
assessment. Neither input is collected market evidence.

## Identity

- **Cluster ID:** `competitor_supply`
- **Display name:** Competitor and Supply Evidence
- **Python module:** `competitor_supply.py`
- **Purpose:** Show what visible product supply appears for a specific job and
  preserve inspectable evidence of exact-fit strength, mismatch, staleness,
  complaint pressure, pricing friction, breadth, and discoverability.
- **Decision role:** Help the user investigate possible under-supply. This
  cluster does not choose opportunities, recommend products, or decide whether
  anything should be built.

## Core Research Question

For this exact job and query, what products visibly appear; how well do their
titles, descriptions, screenshots, reviews, maintenance signals, and pricing
match the job; and is there already a strong, current, trusted, discoverable,
competitively packaged exact-fit incumbent?

Weak supply means observable failure to satisfy, appropriately scope, package,
or reach the target job and segment. It does not mean merely that competitors
exist, a category is crowded, or one result is imperfect.

## Jobs-to-Be-Done Frame

- Define supply around the job a buyer is trying to complete, not only the
  category labels vendors use.
- Include real alternatives that may sit in adjacent product categories or use
  different vocabulary when buyers could hire them for the same job.
- Treat over-serving as a possible mismatch: broad, complex, or costly products
  may serve larger buyers well while mismatching a lighter segment.
- Treat narrow packaging, migration, adoption, or pricing wedges as possible
  gaps without concluding that incumbent products are universally weak.
- Separate theoretical supply from visible supply. Buyers can only shortlist
  products they can discover and understand on relevant surfaces.

## Scope

### Included

- Query-result-set observations from app stores, web search, marketplaces, and
  other approved public discovery surfaces.
- Product identity, vendor identity, URLs, categories, descriptions, first
  visible copy, screenshots, store metadata, and source-specific rank.
- Exact-job evidence in product framing, category, visible workflow, and recent
  review language.
- Ratings, rating counts, bounded review samples, rating distributions where
  available, helpful votes, developer replies, and complaint themes.
- Maintenance evidence: update dates, versions, release notes, changelogs,
  repository activity, recent issue activity, and buyer reports of breakage or
  neglect.
- Public pricing and packaging: visible price strings, entry-price candidates,
  billing units, plan count, free/trial claims, quote-only status, and clearly
  visible caps or minimums.
- Broadness and specificity proxies: named jobs, use cases, personas,
  categories, feature groups, and screenshot workflow diversity.
- Query-level distributions showing exact-fit, broad, stale, opaque-price,
  complaint-heavy, dominant, or poorly discoverable results.
- Screenshots, raw JSON/HTML, excerpts, URLs, timestamps, hashes, and collection
  metadata needed for manual inspection.

### Excluded

- Build/no-build recommendations, opportunity selection, validation plans,
  build plans, and automatic idea generation.
- A single opportunity, market-gap, competitor, or supply score that hides its
  evidence dimensions.
- Exact competitor revenue, downloads, paid conversions, market share,
  retention, activation, customer success, or negotiated B2B price.
- Claims of complete review history, total recent-review velocity, universal
  sentiment, or platform-wide complaint rates from samples.
- Reliable sponsored-placement detection when sponsorship is not directly
  observable in the captured surface.
- Personalized or universal search rank. Every position is one observed surface
  result under recorded conditions.
- Automated aesthetic judgments such as ugly, outdated-looking, polished, or
  generic-looking. Preserve assets and objective proxies for human review.
- Automated G2 or Capterra ingestion as an MVP dependency. Their URLs may be
  discovery records and their pages may be reviewed manually.
- Multi-country and multi-language coverage in the initial practical scope.
- Universal cross-category price comparison or total-cost normalization.

## Canonical Terminology

- **Canonical job:** The target outcome or workflow expressed independently of
  vendor category labels.
- **Query:** Exact search text used on one surface. Related queries remain
  separate observations even when grouped under one canonical job.
- **Search surface:** Apple App Store, Google Play, web search, marketplace, or
  other public system producing an ordered result set.
- **Supply snapshot:** One query, surface, locale, capture time, method, and
  bounded result set.
- **Result observation:** One product appearance at one observed rank within a
  supply snapshot.
- **Normalized product:** Auditable identity joining multiple product surfaces.
  Surface records remain preserved; similar names alone do not justify a merge.
- **Exact-fit product:** Product whose visible framing, workflow assets, and/or
  recent user language directly support the canonical job.
- **Adjacent product:** Product that overlaps the category or workflow but lacks
  enough evidence of exact-job fit.
- **Intent match:** Derived comparison of canonical job with text, category,
  visual workflow, and review-language evidence.
- **Broad/generic signal:** Derived indication that many jobs, personas,
  categories, or unrelated workflows obscure the target job. Breadth is not
  automatically weakness.
- **Staleness signal:** Derived maintenance concern supported by activity dates
  and, for a strong label, buyer-observed breakage, incompatibility, or neglect.
- **Complaint pressure:** Repetition of a core-job blocker inside a documented
  review sample. It is not overall customer sentiment.
- **Pricing mismatch:** Query- and segment-relative candidate supported by
  visible prices or opacity; not a universal expensive/cheap judgment.
- **Dominance blocker:** Candidate finding that at least one exact-fit product is
  current, visible, trusted, sufficiently reviewed, and lightly criticized on
  core-job themes. It is a guardrail against wishful gap claims.
- **Discoverability gap:** Strong-fit, strong-quality product appears poorly for
  target query and has evidence of weak keyword, category, or first-asset
  alignment. This is not automatically a product gap.
- **Positioning gap:** Product may satisfy the job, but category, copy,
  screenshots, keywords, or market frame obscure its value.
- **Distribution gap:** Product may satisfy the job but is not visible where the
  target buyer searches.
- **Product-gap candidate:** Visible supply shows weak fit, freshness,
  satisfaction, packaging, or adoption evidence for target job. Candidate only.
- **Observed API rank:** Order returned by a named API or adapter under recorded
  conditions; never synonymous with a user's on-device rank.
- **Sample complaint rate:** Matching reviewed records divided by the recorded
  sample denominator. Never rename it as a product-wide complaint rate.
- **Planning context:** Supplied specifications and access assessments guiding
  future work; not evidence that any real market has a gap.

## Unit of Analysis

Primary research unit is query-conditioned supply snapshot, not isolated
product. Product-level evidence and query-level interpretation are both needed:

1. Preserve each source result and surface independently.
2. Resolve product identity without deleting conflicting surface facts.
3. Evaluate each product against one canonical job and query context.
4. Summarize distribution across bounded visible result set.
5. Check for dominant exact-fit incumbent before surfacing weakness.
6. Preserve raw metrics, evidence IDs, counts, denominators, and exceptions
   behind every label.

A market appears visibly well served when one or more top products are exact
fit, current, trusted with meaningful recent evidence, understandable from early
assets, and suitably packaged for target buyer. Possible supply weakness
requires a pattern across visible results plus absence of a convincing dominance
blocker. This remains inference, not proof of market opportunity.

## Important Distinctions

### Crowded Does Not Mean Well Served or Weak

Result count alone says little. Crowded markets can contain paid behavior and
persistent mismatch. Sparse public results can reflect poor query choice,
localization, access limits, or weak public review coverage rather than a gap.

### Product, Positioning, and Distribution Gaps Are Separate

- Product gap: weak job fit, maintenance, satisfaction, packaging, or adoption.
- Positioning gap: strong product evidence but unclear category/copy/assets.
- Distribution gap: strong product evidence but weak relevant visibility.

Public metadata cannot definitively diagnose any. Preserve candidate labels and
supporting facts; leave final judgment to user.

### Top Result Is Not Best Product

Popularity, broad category presence, sponsorship, personalization, location,
device, account state, and API differences may change rank. Store observed rank
separately from product quality and exact-job fit. Preserve sponsorship only
when directly visible in screenshot or source field.

### Product Surface Is Not Product Reality

Good copy and screenshots can hide weak task performance. Weak copy can hide a
capable product. Cross-check product framing with recent review language,
maintenance evidence, pricing, and other surfaces.

### Category Match Is Not Job Match

A product can solve a job through configuration or templates despite adjacent
category placement. A product can occupy expected category yet solve a
different primary job. Category is one signal, never decisive alone.

### Old-Looking Is Not Abandoned

Visual age is subjective. Maintenance recency and buyer-observed decay are
separate. Strong abandonment claims require activity dates plus recent evidence
of breakage, incompatibility, neglect, deprecation, or absent support.

### Rating Needs Volume, Recency, and Context

A perfect rating with few reviews does not establish dominance. Ratings are
surface- and locale-specific. Preserve scale, counts, distribution, recency,
sampling method, and review IDs where available.

### Reviews Are Valuable but Incomplete

Some strong B2B products have little public review traffic. Consumer products
may attract large noisy samples. Combine reviews with fit, visibility,
maintenance, and public product evidence. Missing reviews are unknown, not zero.

### Pricing Capture Is Not Total Cost

Visible price text cannot reliably reveal seat minimums, overages,
implementation fees, taxes, mandatory annual billing, regional prices, login-
gated details, feature caps, or negotiated contracts. Keep raw strings and
candidate parses. Compare mismatch only among exact-fit peers for same job and
target segment.

## Detection Guidance

### Intent Match

Use four evidence families:

1. **Text:** title, subtitle, hero line, short description, and first 160
   characters name job, workflow, or buyer.
2. **Category:** functional placement matches job rather than only adjacent
   category.
3. **Visual:** first screenshots show target workflow rather than unrelated
   functionality.
4. **Review language:** recent users describe completing target job.

Ideal specification suggests likely mismatch when at least three families fail.
Keep this as unvalidated heuristic. Missing visual or review evidence must remain
missing; it must not count automatically as failure.

### Breadth and Genericness

Possible proxies:

- distinct jobs and use cases named in title, subtitle, hero copy, short
  description, and screenshot captions;
- explicitly named personas or segments;
- category and subcategory count;
- unrelated workflows in first five screenshots;
- whether first sentence or visual asset states a specific value proposition
  and target job.

Ideal draft proposes strong signal when at least five jobs/use cases and at
least three relevant categories are claimed while exact job is absent from early
copy/assets; medium when broad but job-explicit; weak when tightly framed.
Thresholds are hypotheses requiring calibration. Do not treat breadth as product
failure when evidence shows exact-job success.

### Staleness and Abandonment

Candidate inputs include days since update, days since release note, review
activity and rating trends, changelog or repository activity, support replies,
asset freshness, and recent mentions of abandonment, breakage, crashes,
deprecation, incompatibility, or absent updates.

Ideal draft proposes strong when no update exceeds 365 days and recent reviews
show breakage or neglect; medium beyond 180 days with little activity or mixed
signals; weak when updates are recent or buyers show improvement. Thresholds are
heuristics, not facts. Static mature product may need infrequent updates;
missing update data must remain unknown.

### Complaint Pressure

- Preserve every sampled review as a raw record.
- Identify core-job blockers separately from peripheral dislikes.
- Retain theme counts, sample denominator, sample type, date range, rating
  range, matching review IDs, distinct versions, excerpts, and developer reply.
- Use `sampled_recent_review_count`, `sampled_negative_review_count`,
  `theme_review_count`, `theme_share_of_sample`, and
  `theme_share_of_negative_sample`.
- Never call bounded observations product's overall complaint rate.

Ideal draft asks for at least three complaint snippets behind strong staleness or
complaint label. Practical collection may not always produce three;
insufficiency must be visible instead of silently weakening rule.

### Dominance Blocker

Assess exact-job fit, rating band with meaningful volume, recent review or other
activity, maintenance, cross-surface visibility, and low core-job complaint
pressure. Ideal draft suggests `avg_rating >= 4.2` plus strong fit, volume above
peers, current activity, and top organic visibility across multiple surfaces.
Treat 4.2 as starting heuristic, not universal truth. Compare review volume
within observed result set and source, not across unlike platforms.

### Discoverability Gap

Candidate requires strong fit, ratings/trust, recent evidence, and maintenance,
paired with weak relevant rank plus observable keyword, category, localization,
copy, or first-asset mismatch. A buried strong product may indicate indexing,
positioning, or distribution weakness, not under-supply.

## Practical Source Strategy

Supplied API assessment narrows ideal multi-surface specification to low-cost,
locally runnable MVP. Details below are user-supplied planning snapshot received
2026-08-15, not independently verified facts. Recheck prices, limits, policies,
legal status, endpoint behavior, and package health before implementation or
collection.

### Core MVP Surfaces

1. **Apple App Store, US English:** Use official Apple search/lookup for product
   discovery and core metadata: observed order, IDs, name, developer,
   description, genres, listed price, ratings/counts, release/update/version,
   release notes, screenshots, and store/developer URLs. Keep competitor review
   retrieval in replaceable adapter using bounded samples and label any
   undocumented source `unofficial_public_endpoint`.
2. **Google Play, US English:** Use replaceable unofficial adapter such as
   `google-play-scraper` for search, details, install bucket, ratings/counts,
   distribution, price/IAP range, ads/IAP flags, categories, screenshots,
   updates/version, review samples, helpful votes, and developer replies. Save
   raw responses plus adapter/parser version because fields and result order may
   change.
3. **Brave web search, US English:** Discover SaaS products, pricing pages,
   alternatives, reviews, extensions, repositories, comparison pages, and
   products using different category language. Store query, rank, locale,
   timestamp, snippet, and URL. Snippets remain discovery evidence until direct
   capture.
4. **Direct competitor websites:** Retrieve static HTTP first. Preserve final
   URL, status, title, metadata, canonical URL, headings, hero copy, calls to
   action, navigation, pricing/changelog/docs links, persona/use-case language,
   structured data, app-store links, social links, GitHub links, capture time,
   and raw HTML where justified.
5. **Rendered page fallback:** Use Playwright only when JavaScript, asynchronous
   pricing, toggles, banners, exact visible first screenful, or proof screenshots
   require it. Preserve rendered text, final URL, HTML, screenshots, timestamps,
   and hashes.
6. **GitHub REST API when linked:** Opportunistically enrich open-source
   competitors with push/commit/release activity, issue activity, archived
   state, contributors, stars, and forks. Do not require it for commercial
   competitors.

### Optional or Paid Fallbacks

- Wayback Machine for incomplete historical site or pricing snapshots.
- DataForSEO when localized Google results, exact Google positioning, commercial
  app/review APIs, or scraper maintenance justify small paid dependency.
- SerpAPI as convenient but costlier emergency replacement. Provider and legal
  continuity must be reviewed before use.
- OCR through Tesseract or EasyOCR only after preserved screenshots justify it.
  Stylized, localized, or compressed assets make OCR approximate.

### Manual, Deferred, or Excluded Sources

- G2 and Capterra: use search discovery and manual inspection. Do not promise
  stable bulk competitor profiles, reviews, verification status, pagination, or
  pricing ingestion.
- Product Hunt: exclude from core because supplied assessment flags commercial-
  use restrictions and only medium reliability.
- Google Custom Search: do not build around it; supplied assessment says it is
  closed to new customers and existing customers face 2027 transition.
- Paid intelligence platforms: required for more credible cross-store revenue,
  download, and market-share estimates; excluded from low-cost MVP.
- Complete review archives, universal review velocity, multi-country/language
  collection, and reliable sponsored detection are deferred.

### Supplied Access Snapshot Requiring Verification

- Apple search/lookup: supplied claim of up to 200 results and roughly 20 calls
  per minute; competitor reviews lack clean documented official endpoint.
- Apple review scraper interfaces: supplied claim of bounded pages and old
  Python package release; never make one aging package foundational.
- Google Play adapter: supplied claim of up to 30 search hits and at most 200
  reviews per review request; full histories can require huge request volume.
- Brave: supplied claim of $5 per 1,000 requests with recurring $5 monthly
  credits, roughly 1,000 searches covered monthly.
- DataForSEO: supplied claim of low pay-as-you-go pricing for queued/live Google
  SERPs plus store/review APIs.
- SerpAPI: supplied claim of 250 free monthly searches then $25 per 1,000, plus
  continuity risk from litigation reported in December 2025.
- GitHub: supplied claim of 60 unauthenticated or 5,000 authenticated REST calls
  per hour.

These statements guide feasibility checks only. They must not appear in
`PROFILE.md` as evidence about product or market.

### Cost Posture

Supplied assessment expects core Apple, Google Play adapter, Brave allowance,
HTTP/browser capture, GitHub, local analysis, and local files to operate near
$0 per month at private moderate volume, excluding local compute and storage.
First proposed paid upgrade is stable search/app data such as DataForSEO when
unofficial-adapter maintenance costs more than provider fees, not a hosted LLM.
This is a dated feasibility estimate requiring verification.

## Provisional Collection Bounds

Per exact query in initial US-English research:

- top 20 Apple results;
- top 20 to 30 Google Play results;
- top 10 to 20 web results;
- detailed enrichment for top 10 resolved competitors;
- up to 200 recent mobile reviews;
- up to 100 low-rating reviews when filtering exists;
- optionally 50 relevance-sorted reviews;
- stop review pagination when records exceed documented 12-month window;
- homepage plus one pricing page;
- first three store screenshots;
- one result-page evidence screenshot when possible.

These are planning defaults, not permanent requirements. Record truncation,
missing pages, source ordering, early-stop reason, and sampling strategy.

## Evidence Model

### Query and Capture Run

Preserve at least:

- `query_id`, exact `query`, canonical job, optional target segment;
- surface, locale/country, captured timestamp, collection method and version;
- requested and returned limits, pagination, filters, sort mode, early-stop
  reason, errors, and completeness status;
- raw response/artifact path, content hash, and transformation version.

### Search Result Observation

One row per query-surface-result observation:

- query and capture-run IDs;
- result ID, observed rank, result title, URL, result type, shown category,
  shown price/rating/review count, snippet, screenshot reference;
- sponsorship state only when explicit, otherwise unknown;
- resolved product ID plus identity-resolution method and confidence.

### Normalized Product

One product may join website, store, review, marketplace, changelog, repository,
and repeated search observations. Preserve:

- product and vendor IDs/names;
- canonical and alternate URLs, store IDs, bundle/package IDs, developer IDs;
- each contributing surface record and conflicts;
- locale-specific facts instead of overwriting them;
- manual merge/split status and notes.

Never merge solely by display name. Product identity is derived and revisable.

### Product-Surface Observation

Candidate direct fields include:

- title, subtitle, summary, first 160 characters, full description, categories,
  named use cases/personas, hero copy, and early asset references;
- rating, rating scale/count, review count, rating distribution;
- listed price, currency, free/paid, IAP flags/range;
- release/update dates, version, release notes, changelog and repository facts;
- screenshot/image URLs, direct page URL, capture timestamp, raw artifact, and
  source-specific availability states.

### Website and Pricing Capture

Preserve:

- hero title/subtitle, pricing-page discovery path, visible price strings,
  billing language, free/trial claims, quote-only status, visible plan count;
- clearly visible caps, seat minimums, overage or hidden-fee signals without
  assuming absent facts;
- parse candidates with confidence plus exact supporting text;
- full-page, first-screenful, and pricing screenshots when material.

### Review Record and Sample

One row per preserved review plus one sample manifest:

- review ID, product, surface, URL/app ID, date, title, text, rating and scale,
  language, version, helpful count, verified flag only when exposed;
- developer reply and date;
- collection method, sample type (`newest`, `negative`, `relevant`), sort/filter,
  capture time, date window, requested/returned counts, pagination, raw payload;
- derived theme, polarity, core-job blocker, price/complexity/bug/missing-feature/
  support/abandonment/switching flags, and evidence reference.

Every aggregate must retain denominator, review IDs, date range, and method.

### Evidence Asset

One row per artifact:

- stable evidence reference, product/query/run IDs, artifact type, surface;
- capture timestamp, page title, description, source URL;
- local path or storage reference, content hash, dimensions where applicable;
- extraction/renderer/parser version and notes.

### Query Summary

Derived review aid may contain:

- result count and surface coverage;
- exact-fit, adjacent, broad, stale, transparent-price, quote-only, and
  complaint-pressure counts;
- query-relative peer price/rating/review distributions;
- dominant-incumbent and discoverability-gap counts;
- product-, positioning-, or distribution-gap candidates;
- supply-weakness label, rationale, uncertainty, and top evidence IDs.

No query summary is market proof. All counts must reproduce from linked raw
observations.

## Provisional Output Views

Ideal specification proposes five linked, spreadsheet-friendly views. Names and
columns remain design guidance until shared schema exists.

### Competitors

One row per normalized product within query context. Candidate columns include
query/product/vendor identity, surface count, primary URL, best observed rank,
sponsorship observation, intent/category fit, broadness, rating/count/sample
recency, maintenance, visible pricing/free/trial/quote-only fields, complaint
themes, discoverability, dominance, weakness candidate, manual notes, and one
evidence-bundle ID.

### Reviews

One row per preserved review. Keep source, date, rating, title, excerpt, URL,
language, explicit verification status, primary/secondary themes, core-job
blocker, price/complexity/bug/missing-feature/support/abandonment flags,
sentiment annotation, and raw evidence reference.

### Search Results

One row per query-surface-result observation. Keep exact query, surface, locale,
capture time, observed position, result title/URL/type, explicit sponsorship,
resolved product ID, shown category/price/rating/count, snippet, and screenshot.

### Evidence Assets

One row per preserved artifact. Keep evidence/product/query IDs, artifact type,
surface, capture time, page title, description, local reference, source URL,
hash, and notes.

### Query Summaries

One row per analyzed query or intent cluster. Keep visible, exact-fit, broad,
stale, transparent-price, quote-only, dominant-incumbent, and discoverability-
gap counts; query-relative price/rating/review distributions; supply-weakness
candidate; gap-type candidates; rationale; uncertainty; and top evidence IDs.

## Field Confidence

### Strong Direct Evidence

- Source-returned IDs, observed rank, query, surface, locale, timestamp, URL,
  title, description, categories, update/version, visible price, rating/count,
  screenshots, dated review text, developer reply, and captured page content.
- Direct does not mean complete, representative, comparable across sources, or
  temporally stable.

### Useful but Approximate Evidence

- Google Play install bucket;
- bounded sample complaint shares and recent-review counts;
- parsed price candidates and plan structures;
- semantic intent match, broadness counts, screenshot OCR, category fit;
- web/API rank and product identity resolution.

### Hypothesis-Only Interpretations

- bloated, abandoned, dominant, poorly positioned, overpriced, poorly
  discoverable, product gap, distribution gap, positioning gap, or true supply
  gap.

Hypothesis labels must point to direct and approximate evidence, expose missing
inputs, and remain editable during manual review.

## Derived Labels

Each label must store its rule/version, raw inputs, missing inputs, evidence IDs,
and manual-review state.

- `intent_match_label`: text, category, visual, and review-language support.
- `broad_generic_label`: job/use-case/persona/category/asset breadth plus early
  target-job visibility.
- `staleness_label`: activity dates combined with buyer-observed decay when
  strong.
- `pricing_mismatch_label`: visible peer-relative packaging for same job and
  segment; ambiguity stays visible.
- `complaint_pressure_label`: repeated core blockers inside documented samples.
- `discoverability_gap_label`: strong fit/quality paired with weak visibility
  and observable listing/positioning mismatch.
- `dominance_blocker`: exact fit, credibility, freshness, visibility, packaging,
  and low core-job complaint pressure.
- `competitor_weakness_signal`: multiple weakness dimensions not offset by
  dominance evidence.
- `query_supply_weakness_signal`: distribution across bounded visible results,
  never automatic product or market recommendation.

Possible query-level interpretation:

- **Strong evidence candidate:** most visible results are mismatched, broad,
  stale, poorly packaged, complaint-heavy, or badly discoverable; no convincing
  dominant exact-fit incumbent.
- **Medium evidence candidate:** visible weaknesses exist, but one decent
  exact-fit option exists or evidence points mainly to positioning/distribution.
- **Weak evidence candidate:** one or more exact-fit, current, trusted products
  visibly serve job.

Always pair label with exact counts, source coverage, missing evidence, review
sample sizes, and dominance result.

## Manual Inspection Standard

For every promoted query pattern, user should be able to answer:

- What exact job, query, locale, surface, and timestamp produced this set?
- Which products appeared and at what observed ranks?
- Which raw copy, category, screenshots, and reviews support fit or mismatch?
- Which maintenance and pricing facts are direct versus parsed or missing?
- How many reviews were sampled, how, over what dates, and which IDs support
  each complaint theme?
- Is a strong product buried, making this positioning/distribution rather than
  product weakness?
- Is a dominant exact-fit incumbent present?
- What could inaccessible reviews, localization, personalization, sponsorship,
  or source limits have hidden?

Ideal evidence bundles include result-page screenshot, title/tagline/first
screenful capture, first three product screenshots, pricing capture, version or
changelog evidence, at least three complaint snippets per major promoted theme,
one positive excerpt for dominance blocker, source URLs, timestamps, and hashes.
Missing artifacts must be explicit; they are not automatic failures.

## Failure Modes and Guardrails

### False Positives

- Tiny perfect-rating samples: preserve volume and recency; do not call dominant.
- Rank bias: separate organic, sponsored, editorial, marketplace, and API order.
- Category-only inference: cross-check copy, assets, and review language.
- Broadness-as-failure: verify that breadth obscures or weakens target-job use.
- Age-as-abandonment: combine activity dates with buyer-observed decay.
- Sample-as-population: label all bounded review metrics and denominators.
- Price normalization: keep raw strings and compare only relevant peers.
- Missing public feedback: unknown does not mean weak satisfaction.

### False Negatives

- Great niche products may lack review volume or popular-list eligibility.
- US-English collection may miss strong localized products and assets.
- B2B products may serve users well despite little public feedback.
- Adjacent-category products may solve job through configuration/templates.
- Strong products may rank poorly because of positioning or distribution.
- API result order may differ from physical-device or personalized results.

Report `no public evidence found` or `insufficient coverage`, never `no
competitor exists`, when observation cannot support absence.

## Nonbinding Technical Context

Supplied material suggests `httpx`, retries, Apple search, replaceable Google
Play adapter, Brave, BeautifulSoup or selectolax, trafilatura, Playwright, and
GitHub REST for collection; pandas, RapidFuzz, sentence-transformers,
scikit-learn, optional local models, and optional OCR for analysis; local raw
JSON/HTML/images plus SHA-256 hashes, SQLite, CSV, or Parquet for storage.

These are options, not authorized dependencies or architecture. No collector,
schema, interface, database, score, or runner is implemented or selected by
this context task.

## Confirmed Project Facts

- User supplied ideal Competitor Supply Weakness Evidence specification and
  practical API-availability assessment.
- Inputs are durable planning context, not collected market evidence.
- No competitor/supply evidence has been collected yet.
- Current task authorizes cluster guidance and scaffold updates only; no
  collection, transformation, scoring, or public Python interface.
- Product-level observations and query-level summaries must remain linked to
  raw evidence.

## Assumptions

- Cluster ID is `competitor_supply`, matching repository naming patterns and
  project's “Competitor/supply evidence” category. User's phrase “competitor
  supply chain evidence” is interpreted as this category, not physical supply-
  chain research.
- Initial practical scope is public, permitted, US-English product discovery.
- Review and store adapters will remain replaceable because public access and
  package behavior may change.
- Exact thresholds from ideal specification are provisional heuristics.

## Hypotheses

- Query-conditioned exact-job fit is more useful than category-level competitor
  count for manual gap investigation.
- Cross-checking early copy, first assets, and review language may distinguish
  visible category overlap from actual job fit.
- Maintenance dates plus recent neglect complaints may distinguish staleness
  from subjective visual age.
- Query-relative visible pricing may reveal segment mismatch without pretending
  to estimate total cost.
- A dominance blocker may reduce false optimism in visibly well-served markets.
- Separating product, positioning, and distribution candidates may prevent a
  buried strong competitor from being mislabeled as absent supply.

## Open Questions

- Which canonical job, target segment, and query family will seed first run?
- What shared runner contract, raw JSONL schema, and stable ID convention will
  govern all cluster modules?
- Which source credentials, budgets, terms, retention rules, and deletion
  obligations will be approved when implementation starts?
- How should product identity merges and splits be reviewed across surfaces and
  locales?
- How will missing visual/review evidence affect intent-match rules without
  becoming automatic failure?
- What real samples will calibrate proposed 4.2 rating, 180/365-day staleness,
  and 5-use-case/3-category breadth thresholds?
- What constitutes meaningful review volume within each source and query set?
- Which pricing units can be compared without hiding seat, usage, or annual-
  billing differences?
- When should manually observed sponsored result affect query interpretation?
- What evidence threshold promotes product-, positioning-, or distribution-gap
  candidate for review?

## Decisions and Superseded Guidance

- **2026-08-15 — Practical access scope narrows ideal multi-surface coverage.**
  Initial source candidates are Apple, Google Play, Brave web search, direct
  sites, and linked GitHub repositories. Wayback, DataForSEO, SerpAPI, and OCR
  are optional. Automated G2/Capterra, Product Hunt, paid market intelligence,
  full review archives, and multi-locale research are deferred or excluded.
- **2026-08-15 — Complete ideal fields become sampled, explicit-only, or
  nullable.** Recent review velocity becomes sample-bounded; sponsorship is
  observed-only; Apple installs stay null; exact market share/revenue are
  excluded; pricing preserves raw visible strings.
- **2026-08-15 — Rank renamed as observation.** Store/API/web ordering requires
  query, surface, locale, timestamp, and method. It cannot represent universal
  rank.
- **2026-08-15 — Gap types remain candidates.** Product, positioning,
  distribution, dominance, and supply weakness are derived review aids, never
  definitive diagnoses or build decisions.
- **2026-08-15 — Review collection bounded.** Recent and negative samples are
  preferred over complete histories; every aggregate requires denominator,
  sampling method, date range, and review IDs.
- **2026-08-15 — Evidence preservation remains proportional.** Raw responses,
  excerpts, URLs, timestamps, and hashes are core. Screenshots focus on result
  pages, early product assets, pricing, and other fragile proof.
- No earlier cluster-specific guidance existed to supersede.

## Context Change Log

- **2026-08-15:** Created cluster context from supplied ideal specification and
  practical API-availability assessment. Source documents were not copied into
  cluster; no market evidence or collection logic was added.
