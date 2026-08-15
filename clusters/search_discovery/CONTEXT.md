# Cluster Context: `search_discovery`

This file stores durable design guidance for the Search and Discovery Evidence
cluster. It models the supplied ideal specification and practical API-access
assessment. Neither input is collected market evidence.

## Identity

- **Cluster ID:** `search_discovery`
- **Display name:** Search and Discovery Evidence
- **Python module:** `search_discovery.py`
- **Purpose:** Show whether people express a specific job in search and whether
  captured discovery surfaces serve that intent directly, indirectly, or
  poorly.
- **Decision role:** Help the user inspect expressed demand, intent, and possible
  discoverability mismatch. This cluster does not prove a business will work,
  choose an opportunity, or recommend what to build.

## Core Research Question

For a defined problem hypothesis and query family:

1. Is the job expressed through repeated, specific query language?
2. What intent does the query language suggest?
3. What intent and solution types does the captured SERP actually serve?
4. Are action-oriented or evaluative queries met mostly by articles, forums,
   videos, directories, marketplaces, or irrelevant results instead of usable
   tools and product surfaces?
5. What raw records let a human audit that interpretation?

The useful claim is narrow: a query family exists, expresses a recognizable
job, and may be underserved in one recorded discovery environment. It is not a
claim about market size, conversion, profitability, or universal rankings.

## Jobs-to-Be-Done Frame

- Group queries around the outcome a person is trying to achieve, not only the
  keyword or product category.
- Extract action, object, audience, constraint, and journey-stage language.
- Prefer specific jobs such as progress billing for contractors over broad
  category terms such as invoice software.
- Treat action and evaluation language as predicted intent. Compare it with the
  observed result mix instead of assuming the words alone reveal true intent.
- Use autocomplete and related queries to discover phrasing and modifiers.
  Suggestion presence is evidence that the language appears on that source; it
  is not clean search-volume evidence.

## Scope

### Included

- Manually supplied problem hypotheses and one to five seed queries.
- Exact query variants from autocomplete, related searches, manual input,
  keyword tools, trend sources, or competitor-derived discovery.
- Google-shaped SERP captures through a provider, with explicit engine,
  provider, country, language, device, and timestamp.
- Brave results as a separate development, fallback, or corroboration surface.
- Top-N results with rank, block, title, URL, domain, snippet, visible date, and
  provider-specific result type.
- Ads, merchant/product blocks, app/software results, discussions/forums units,
  AI Overview presence, and other captured SERP features.
- Local deterministic result classification, optional selective page metadata,
  and later NLP/LLM classification when raw support remains inspectable.
- Separate demand, intent, composition, mismatch, concentration, trend, and
  commercial-support metrics.
- Optional approximate volume, CPC, bid, paid-competition, and trend enrichment.
- Raw responses, exports, selective screenshots, selective HTML/page metadata,
  stable IDs, timestamps, hashes where useful, and transformation notes.

### Excluded or Deferred

- Business viability proof, product selection, go/no-go logic, build plans,
  validation plans, and automatic app-idea generation.
- One opaque opportunity, SEO, keyword, demand, or market-gap score.
- Exact search volume as an MVP requirement.
- Query-specific CTR, zero-click rate, unique searchers, installs, purchases,
  conversions, or revenue inference.
- Keyword difficulty, domain authority, backlink gaps, estimated organic
  traffic, and traffic-potential models in v1.
- Personalized or signed-in-result modeling and claims about what every user
  sees.
- Automatic multi-city, multi-country, multi-language, or multi-device capture
  in v1.
- Full-page crawling for every result, screenshots for every query, or pixel
  parsing as default behavior.
- Exact AI Overview text, citation-order, stability, or answer-quality analysis.
- Direct Google scraping as the primary source.
- Official Google Custom Search as a provider target.
- Official Google Trends API or Google Ads API as required MVP dependencies.
- Unofficial Google Trends scraping as a required component.

## Canonical Terminology

- **Problem hypothesis:** User-supplied description of a possible recurring job
  or pain. It is research framing, not evidence.
- **Seed query:** Exact starting query selected manually or supplied by another
  traceable source.
- **Query family:** Related exact queries grouped under one problem hypothesis
  and canonical job. Membership is derived and must retain supporting IDs.
- **Query variant:** Exact string captured or searched; never silently merged
  with close variants.
- **Search environment:** Engine, provider, country, language, device, account
  state, personalization state, and capture time.
- **SERP snapshot:** One query in one recorded search environment with a bounded
  set of result blocks and results.
- **Predicted intent:** Derived hypothesis from query language and query-family
  context: informational, commercial, transactional, navigational, or mixed.
- **Observed SERP intent:** Derived description of what the captured result mix
  appears to serve.
- **SERP composition:** Counts and shares of result surfaces and dispositions in
  a defined denominator.
- **Surface type:** What kind of page or search surface a result represents.
- **Direct-solution disposition:** Whether a result directly solves, supports
  evaluation, explains, hosts community discussion, is irrelevant, or remains
  unknown.
- **Search volume:** Approximate searches for a keyword and close variants under
  recorded tool settings; not unique people or guaranteed clicks.
- **Trend direction:** Normalized relative movement over time, not absolute
  demand.
- **Paid competition:** Competition among advertisers in paid SERPs; not product
  saturation, product quality, or organic difficulty.
- **Mismatch:** Derived difference between predicted action/evaluation intent
  and observed explanatory/community-heavy or weakly direct SERP composition.
- **Discoverability signal:** Headline weak/medium/strong inspection label based
  on separate demand, intent-gap, and concentration evidence. Not a decision.
- **Planning context:** Supplied design and provider guidance. It is not market
  evidence and receives no raw evidence ID.

## Concepts That Must Remain Separate

### Expressed Demand

Query variants, suggestions, related searches, rising terms, and optional
keyword metrics can show that people express a job using searchable language.
They do not establish unique users, willingness to pay, or market size.

### Search Intent

Intent describes the goal behind a query. Informational, commercial,
transactional, navigational, and mixed labels may overlap. Query wording alone
is insufficient; preserve lexical cues and compare them with the result mix.

### SERP Composition

Composition describes what the engine returned: tools, app pages, articles,
forums, directories, marketplaces, videos, ads, merchant results, and other
blocks. It can reveal a content-heavy or mismatched discovery surface but cannot
measure absolute demand.

### Trend Direction

Trend data describes normalized movement, seasonality, or rising related terms.
It is useful for distinguishing stable, rising, seasonal, and temporary query
families. It cannot provide exact market size; low-volume terms may appear as
zero.

### Commercial Support

Ads, pricing/comparison results, product blocks, app-store results, CPC, and bid
ranges support an inference that economic behavior exists nearby. Each stays
separate. No single cue proves buying intent or a viable product market.

## Unit of Analysis and Artifact Model

Primary research unit is a query family. Evidence remains normalized at five
levels so family summaries never erase individual observations.

### 1. Query Records

One row per searched query:

```text
query_id
problem_cluster_id
seed_query
query_text
query_source
engine
provider
country
language
device_class
signed_in_state
personalization_state
timestamp_utc
predicted_intent_primary
predicted_intent_confidence
commercial_lexical_flag
transactional_lexical_flag
job_verb
job_object
audience_modifier
constraint_modifier
journey_stage
query_specificity
raw_evidence_ids
```

`query_source` may be `seed`, `autocomplete`, `related_search`, `trends`,
`keyword_planner`, `manual`, or `competitor_derived`. Preserve exact strings and
source order before normalization.

### 2. Suggestion Records

One row per expansion tied to its parent query:

```text
suggestion_id
parent_query_id
suggestion_text
suggestion_source
position_in_source
job_verb
job_object
audience_modifier
constraint_modifier
journey_stage
suggests_specific_job_flag
suggests_commercial_research_flag
suggests_transaction_flag
raw_evidence_ids
```

Autocomplete, related searches, Trends rising terms, and keyword-tool ideas are
distinct sources. Never combine their ranks or imply equivalent generation.

### 3. SERP Result Records

One row per captured result or block item:

```text
serp_result_id
query_id
normalized_rank
rank_within_block
result_block
provider_result_type
title
url
canonical_url
display_domain
registrable_domain
snippet
visible_date
surface_type
direct_solution_disposition
competitor_flag
marketplace_flag
directory_flag
forum_flag
article_flag
video_flag
irrelevant_flag
pricing_visible_flag
download_or_signup_cta_flag
app_store_or_extension_store_flag
classification_method
classification_confidence
classification_notes
raw_evidence_ids
```

Preserve provider rank and block structure. `normalized_rank` must document its
policy; ads, AI citations, merchant blocks, and organic results may not share a
natural sequence.

### 4. Query Summaries

One row per captured query:

```text
query_id
top_n_captured
metric_denominator
direct_solution_count
article_count
forum_count
marketplace_count
directory_count
video_count
irrelevant_count
unknown_count
direct_solution_share
article_forum_video_share
competitor_share
unique_domain_count
top_domain_share
ads_present_flag
merchant_or_product_result_flag
software_app_result_flag
discussions_forums_unit_flag
ai_overview_flag
observed_serp_intent_primary
mismatch_severity
articles_instead_of_tools_flag
forums_instead_of_tools_flag
demand_signal
intent_gap_signal
discoverability_signal
supporting_evidence_ids
```

Every count and share must name its denominator and top-N policy. Missing or
unclassified records remain visible.

### 5. Demand Enrichment

Keep optional provider data separate so missing access never blocks core SERP
analysis:

```text
query_id
avg_monthly_searches
monthly_searches
volume_source
volume_capture_date
volume_is_range_flag
paid_competition_level
paid_competition_index
cpc
bid_low
bid_high
trend_direction_12m
trend_slope_score
seasonality_flag
rising_related_terms_count
trend_data_source
raw_evidence_ids
```

Preserve nulls. Record when a provider groups close variants or returns no data.

## Result Classification

### Surface Type

Use one primary controlled value:

- `direct_tool`: job can be performed on the page itself.
- `app_page`: product landing, download, extension, or app-store page.
- `marketplace_listing`: store, plugin, extension, template, or marketplace
  listing/search result.
- `directory_or_review`: listings, reviews, alternatives, comparisons, or
  evaluation hubs.
- `article_or_guide`: how-to, tutorial, explainer, listicle, workaround, or
  editorial documentation.
- `forum_or_qa`: discussion, Q&A, official community, Reddit, Quora, or forum
  unit.
- `video`: video page or video block.
- `local_listing`: local business or generic local directory surface.
- `irrelevant`: wrong entity, geography, job, stale topic, brand confusion, or
  materially off-target result.
- `unknown`: evidence insufficient or conflicting.

Competitor status is orthogonal. A result may be `app_page` plus
`competitor_flag = true`, or `directory_or_review` plus evidence that competitors
are mentioned. Do not use `competitor_page` as a mutually exclusive surface.

### Direct-Solution Disposition

- `direct`: user can solve or start solving the job from the result.
- `evaluative`: result helps compare, shortlist, or decide.
- `explanatory`: result explains the problem or a workaround.
- `community`: result contains lived experience, troubleshooting, or anecdotal
  advice.
- `irrelevant`: result does not materially help with the job.
- `unknown`: evidence is insufficient.

An evaluative SERP suggests a known category where buyers compare options. An
explanatory/community SERP suggests problem awareness or workaround behavior.
Neither alone proves a gap.

### Classification Order

1. Provider-supplied result/block type.
2. Known-domain rules.
3. URL-path patterns.
4. Title and snippet cues.
5. Selective page metadata for ambiguous records.
6. Optional NLP or LLM classification as a final traceable method.

Examples include Reddit as forum evidence, YouTube as video, app stores as app
or marketplace surfaces, G2/Capterra as directory/review, article-like paths as
probable editorial surfaces, and pricing/signup/download paths as possible
product surfaces. Domain rules are starting heuristics, not immutable truth.

Every result stores `classification_method`, confidence, notes, and raw IDs.
Low-confidence results remain eligible for selective page fetch or manual review.

## Intent Detection

### Predicted Intent

Derive from query text and family context. Preserve cues rather than relying on
one keyword:

- commercial/evaluative: `best`, `compare`, `vs`, `alternatives`, `software`,
  `tool`, `app`, `pricing`;
- transactional/action: `buy`, `download`, `convert`, `merge`, `sync`, `export`,
  `track`, `schedule`, and other job verbs;
- informational: `what`, `why`, `how`, tutorials, and explanation language;
- navigational: named destination, brand, site, or login intent;
- mixed: overlapping goals or conflicting cues.

### Observed Intent

Infer from top results and SERP features. Count direct, evaluative,
explanatory, community, product, app, forum, article, video, directory, ad, and
merchant surfaces. Store raw counts beside label.

### Mismatch

Mismatch exists when predicted action/evaluation intent is met mainly by
explanatory or community results instead of direct or evaluative product
surfaces.

Starting v1 thresholds from ideal guidance:

- **Strong:** action/evaluation intent, `direct_solution_share <= 0.20`, and
  `article_forum_video_share >= 0.60`.
- **Medium:** action/evaluation intent with `direct_solution_share` from `0.21`
  through `0.40`, or `article_forum_video_share` from `0.45` through `0.59`.
- **Weak:** `direct_solution_share > 0.40`, or tools/app/commercial surfaces
  already match intent clearly.

These are unvalidated calibration hypotheses. Denominator policy, unknown
share, mixed intent, special blocks, and classification confidence must remain
visible. A forum-heavy result set may reflect genuine preference for first-hand
experience rather than unmet demand.

## Derived Metrics and Labels

Core local metrics:

```text
direct_solution_count
article_count
forum_count
video_count
directory_count
marketplace_count
irrelevant_count
unknown_count
direct_solution_share
article_forum_video_share
unique_domain_count
top_domain_share
competitor_share
```

Additional inspectable flags:

```text
articles_instead_of_tools_flag
forums_instead_of_tools_flag
action_intent_mismatch_flag
commercial_words_present
transactional_words_present
ads_present
shopping_block_present
pricing_result_count
comparison_result_count
app_store_result_count
ai_overview_present
```

Keep three labels separate:

1. **Demand signal:** whether this job is expressed through multiple query
   variants or corroborating sources.
2. **Intent gap signal:** whether captured SERPs poorly match predicted intent.
3. **Discoverability signal:** whether demand exists, intent gap is medium or
   strong, and results are not monopolized by a few domains.

Initial demand heuristic:

- strong: at least five variants across suggestion/related sources, clear trend
  growth, or non-trivial keyword-tool support;
- medium: two to four variants or mixed corroboration;
- weak: zero to one weak variant and no corroboration.

Initial discoverability heuristic:

- strong: demand strong, intent gap medium/strong, no heavy domain monopoly;
- medium: demand present with weaker gap or high concentration;
- weak: weak demand, mostly navigational intent, or incumbent tools already
  satisfy intent cleanly.

All thresholds need calibration against manually reviewed query families. Show
component counts, raw IDs, confidence, and exceptions. No label may choose an
opportunity for the user.

## False Positives

- Sparse or low-competition results may indicate weak demand or poor query
  wording, not a product gap.
- Forum-heavy SERPs may reflect preference for lived experience rather than an
  absent tool.
- High-volume head terms may be ambiguous, crowded, zero-click-heavy, or
  intercepted by search features.
- Temporary trends or fresh autocomplete suggestions may reflect short-lived
  events.
- Volume may aggregate repeat searches and close variants, overstating distinct
  people or buyers.
- Articles may fully satisfy an informational query even when no tool appears.
- Cross-engine disagreement may reflect different indexes, not confirmation or
  refutation of a Google gap.

## False Negatives

- A Trends value of zero can hide niche, long-tail, B2B, or emerging demand.
- SEO tools can report zero volume for real conversational queries expressed in
  many unique ways.
- One uncontrolled capture can miss locale-, device-, time-, or
  personalization-specific results.
- Article, community, or template dominance around a specific action job may
  reveal manual workaround behavior rather than absence of demand.
- Weak public discoverability may hide capable products using different category
  language.
- Provider normalization can omit or flatten special SERP blocks; raw responses
  must remain available.

## Practical Provider Strategy

Provider details below are user-supplied planning claims received 2026-08-15.
They were not independently verified. Prices, credits, API access, field shapes,
policy, and endpoint availability must be rechecked before implementation or
collection.

### Core Google Evidence: DataForSEO

- Intended long-term default for Google Organic SERPs and Google Autocomplete.
- Chosen because actual Google-shaped composition is required for claims about
  what a Google provider capture returned.
- Cheapest standard queue uses task submission and later retrieval; future
  design needs isolated retries, status tracking, raw-response preservation, and
  normalization across many result types.
- Supplied snapshot estimates standard queue at `$0.0006` per ten-result SERP,
  roughly `$0.60` per 1,000 captures; priority is estimated at `$1.20` and live
  mode at `$2.00` per 1,000 captures.
- A supplied example uses one seed plus ten autocomplete-derived variants: 11
  SERPs per opportunity, about `$0.66` for 100 opportunities or `$6.60` for
  1,000 at standard-queue pricing. This excludes screenshots, deeper pages,
  expanded People Also Ask records, and other add-ons.
- Optional features, deeper pages, screenshots, and expanded result blocks may
  change cost.

### Secondary Engine: Brave Search

- Use for effectively free pipeline development, extra competitor/article/forum
  discovery, additional snippets, fallback, or shortlisted corroboration.
- Supplied snapshot says `$5` monthly credit and `$5` per 1,000 web requests,
  approximately 1,000 free requests monthly.
- Brave describes Brave's own search landscape. It cannot support claims about
  Google ads, Google forum share, Google AI Overviews, or Google tool coverage.
- Keep `engine = brave`; never merge its ranks with Google.

### Prototype Convenience: SerpAPI

- Optional early prototype or emergency replacement when clean JSON and many
  specialized engines matter more than price.
- Supplied snapshot lists 250 free monthly searches and paid tiers starting at
  `$25` for 1,000 searches.
- Not preferred long-term default because supplied cost comparison is much
  higher than DataForSEO for equivalent Google-query volume.

### Optional Volume and Commercial Enrichment

- Prefer DataForSEO Google Ads-derived keyword data for approximate average
  volume, monthly history, paid competition, CPC, and bid ranges.
- Batch keywords where provider terms permit; supplied notes say up to 1,000
  keywords per request at same request price.
- Preserve provider grouping, missing values, capture date, and close-variant
  caveats.
- Allow manual Keyword Planner CSV import as an alternative.
- Defer official Google Ads API as an MVP dependency because supplied guidance
  reports manager-account, developer-token, access-level, and permissible-use
  friction for a private market-gap tool.

### Optional Trends Enrichment

- Apply only after SERP composition indicates medium/strong mismatch or manual
  shortlisting.
- Prefer DataForSEO Google Trends, SerpAPI Google Trends, or manual exports.
- Supplied notes say DataForSEO supports up to five comparison terms, while
  related topics/queries require single-keyword requests.
- Do not depend on official Google Trends API; supplied guidance says its July
  2025 release remained limited-access alpha.
- Unofficial website-emulation libraries are experimental, replaceable, and
  nonessential.

### Excluded Primary Sources

- Official Google Custom Search: supplied assessment says closed to new
  customers and not a clean general-purpose modern Google-SERP source.
- Direct Google scraping with `requests` or Playwright: CAPTCHA, consent,
  personalization, proxy, layout, reproducibility, policy, and maintenance costs
  outweigh cheap SERP-provider use.
- Ahrefs/Semrush-style proprietary difficulty and traffic models: enrichment for
  later acquisition analysis, not core missing-product evidence.

## Practical MVP Boundary

### Inputs

- One problem hypothesis.
- One to five manually selected seed queries.
- US English desktop baseline.

### Collection

- Google autocomplete suggestions.
- At most 10–20 query variants.
- Top ten Google results per query.
- Complete raw JSON for each provider capture.
- Optional Brave results for development or shortlisted corroboration.

### Processing

- URL and registrable-domain normalization.
- Multi-axis result classification.
- Predicted and observed intent cues.
- Result-type counts and shares.
- Domain diversity and concentration.
- Mismatch rules with explicit raw support.

### Output

Four required inspectable artifacts or relational tables:

```text
queries
suggestions
serp_results
query_summaries
```

Optional fifth artifact:

```text
keyword_enrichment
```

CSV, JSONL, Markdown, SQLite, DuckDB, or Parquet are acceptable when raw IDs and
manual inspectability remain intact. Spreadsheet-friendly exports should not
replace raw provider payloads.

### Staged Collection Strategy

1. Develop schema and classification with Brave plus manual inspection.
2. Add DataForSEO Google Organic and Autocomplete for actual Google-shaped
   evidence and preserve complete raw responses.
3. Enrich only medium/strong or manually shortlisted cases with volume, CPC,
   Trends, selective page fetches, screenshots, more environments, or another
   engine.

Cost principle: collect cheap SERP-composition evidence broadly; collect volume,
trends, screenshots, and page-level evidence narrowly.

### Possible Local Components

These are supplied implementation candidates, not installed dependencies or a
committed architecture:

```text
httpx or requests       API communication
pydantic                response and row schemas
sqlite3 or DuckDB       local relational evidence storage
pandas or polars        exports and aggregation
pyarrow                 optional Parquet storage
tldextract              registrable-domain extraction
urllib.parse            URL normalization
BeautifulSoup           selective page inspection
trafilatura              selective main-text extraction
Playwright              selective screenshots only
tenacity                 retry and backoff behavior
```

Start classification with deterministic rules. Add a local NLP model or local
LLM later only if ambiguity warrants it, with method and confidence stored per
label.

## Evidence Preservation

For every query family, retain when available:

- exact seed and query strings;
- stable query, suggestion, result, raw-artifact, and transformation IDs;
- capture timestamp and collection date;
- engine, provider, country, language, device, signed-in state, and
  personalization state;
- complete raw provider response before normalization;
- bounded top-N list with provider rank, block, URL, title, snippet, and visible
  date;
- autocomplete, related-query, trend, and keyword-enrichment rows with source;
- classification method, confidence, notes, rule/version, and evidence IDs;
- metric formulas, denominators, thresholds, and query-family membership;
- selective screenshot or HTML artifact when policy triggers it;
- artifact hashes when they improve integrity and reproducibility;
- errors, retries, missing fields, partial captures, and provider limitations.

Suggested screenshot policy:

```text
strong_signal OR
classification_confidence_low OR
manual_review_requested
```

An equivalent visual snapshot may also be preserved when a result block cannot
be reconstructed from raw provider data. Do not imply that JSON reproduces
pixel layout exactly.

No derived label is valid unless a human can trace it to exact queries, captured
SERP records, URLs, ranks, snippets, environment metadata, and enrichment rows
that produced it.

## Profile Guidance

- Primary findings belong in section 6, Search and Discovery Evidence.
- Cross-cluster implications may be noted only when this cluster actually
  collected supporting evidence; do not copy planning guidance into sections
  1–5 or 7–8 as findings.
- Section 9 lists raw evidence IDs, artifacts, URLs, excerpts, capture dates, and
  known limitations.
- Each interpretation must say that it is derived and show component metrics.
- Keep all nine headings. Use `No evidence collected yet` until collection
  exists.

## Confirmed Project Decisions

- Cluster remains evidence-gathering and query-centric.
- Search volume, intent, SERP composition, trend, and commercial support remain
  separate.
- Core v1 evidence is top-ten result composition plus query expansion.
- Google and Brave remain separate engines.
- Raw provider responses are preserved before transformation.
- Volume and Trends are optional, nullable enrichment.
- No functional collector or classifier is implemented during this context
  update.

## Provider Claims Requiring Revalidation

- DataForSEO endpoint availability, result types, queue behavior, prices, and
  add-on costs.
- Brave monthly credits, per-request price, endpoint behavior, and result limits.
- SerpAPI free allowance, plan prices, and search accounting.
- DataForSEO Google Ads batch limits, pricing, close-variant behavior, and
  returned fields.
- Google Ads API access requirements and permissible-use policy.
- Official Google Trends API access status.
- Google Custom Search customer availability and transition dates.

## Planning Source Registry

These links came from the supplied ideal specification or API assessment. They
support future design review and revalidation; they are not raw market evidence.

### Search, Intent, and Jobs Guidance

- Harvard Business School, Jobs to Be Done:
  <https://online.hbs.edu/blog/post/jobs-to-be-done-examples>
- Google Search Help, result variation:
  <https://support.google.com/websearch/answer/12412910?hl=en>
- Ahrefs, search intent:
  <https://ahrefs.com/blog/search-intent/>
- Semrush, search intent and SERP inspection:
  <https://www.semrush.com/blog/search-intent/>
- Semrush, informational/commercial/navigational/transactional keyword types:
  <https://www.semrush.com/blog/types-of-keywords-commercial-informational-navigational-transactional/>
- Google, Autocomplete generation:
  <https://blog.google/products-and-platforms/products/search/how-google-autocomplete-predictions-work/>
- Google Search Central, supported search appearances:
  <https://developers.google.com/search/docs/appearance/structured-data/search-gallery>
- Google, Discussions and forums:
  <https://blog.google/products-and-platforms/products/search/google-search-discussions-forums-news/>
- Indie Hackers operator example:
  <https://www.indiehackers.com/post/how-i-ll-choose-the-next-startup-idea-b7290748bb>

### Volume and Trend Guidance

- Google Ads Help, Keyword Planner forecasts:
  <https://support.google.com/google-ads/answer/3022575?hl=en>
- Google Ads Help, Keyword Planner:
  <https://support.google.com/google-ads/answer/7337243?hl=en>
- Google Ads Help, search trends in Insights:
  <https://support.google.com/google-ads/answer/10261137?hl=en>
- Google Trends Help, data FAQ:
  <https://support.google.com/trends/answer/4365533?hl=en>
- Ahrefs, search-volume accuracy:
  <https://help.ahrefs.com/en/articles/72571-how-accurate-is-keyword-search-volume-in-ahrefs>
- Ahrefs, long-tail keywords:
  <https://ahrefs.com/blog/long-tail-keywords/>
- Ahrefs, keyword-volume caveats:
  <https://ahrefs.com/blog/keyword-search-volume/>

### Provider and Access Guidance

- DataForSEO Google Organic SERP pricing:
  <https://dataforseo.com/pricing/serp/google-organic-serp-api>
- DataForSEO Google Ads search-volume endpoint:
  <https://docs.dataforseo.com/v3/keywords_data/google_ads/search_volume/live/>
- DataForSEO Google Trends endpoint:
  <https://docs.dataforseo.com/v3/keywords_data/google_trends/explore/live/>
- Brave Search API overview:
  <https://brave.com/search/api/>
- Brave Search API response documentation:
  <https://api-dashboard.search.brave.com/app/documentation/web-search/responses>
- SerpAPI pricing:
  <https://serpapi.com/pricing>
- Google Ads API historical metrics:
  <https://developers.google.com/google-ads/api/docs/keyword-planning/generate-historical-metrics>
- Google Ads API access levels and permissible use:
  <https://developers.google.com/google-ads/api/docs/access-levels>
- Google Trends API alpha announcement:
  <https://developers.google.com/search/blog/2025/07/trends-api>
- Google Custom Search JSON API status:
  <https://developers.google.com/custom-search/v1/overview>

## Hypotheses

- Specific action/evaluation query families with few direct solutions and many
  article/forum/video results may reveal underserved discovery intent.
- Multiple job-specific suggestions provide stronger expressed-demand support
  than one broad head term.
- Domain diversity helps distinguish fragmented result sets from spaces
  controlled by a few incumbents.
- Deterministic rules using domain, URL, provider block, title, and snippet can
  classify enough results for a useful first pass.
- Selective screenshots and page fetches can preserve adequate reviewability at
  lower cost than exhaustive capture.
- Current mismatch and label thresholds will need manual calibration.

## Open Questions

- Exact public runner interface and shared schema conventions.
- Stable raw evidence ID and artifact-directory convention across clusters.
- Exact denominator policy for organic results versus mixed SERP blocks.
- Query-family grouping method and manual override workflow.
- Controlled lexical dictionaries and versioning strategy.
- Calibration set, reviewer process, and acceptable disagreement rate for
  surface and disposition labels.
- Domain-concentration threshold defining a monopoly or high concentration.
- Whether screenshots require a provider feature, local Playwright review, or
  manual capture for each trigger case.
- Whether SQLite or DuckDB becomes canonical local relational store.
- Frequency and owner of provider pricing/access revalidation.

## Decisions and Superseded Guidance

- **Ideal exhaustive screenshots narrowed for MVP:** The ideal specification
  asks for a first-page screenshot or equivalent visual snapshot for every query.
  Practical API guidance supersedes exhaustive screenshots with raw JSON for
  every query and selective screenshots for strong, ambiguous, low-confidence,
  or manually requested cases. Reason: cost, storage, parsing, and layout
  variability. Traceability remains mandatory.
- **Provider-neutral ideal narrowed to practical defaults:** Evidence roles stay
  provider-neutral, but current MVP planning prefers DataForSEO for Google SERPs
  and autocomplete, Brave for development/corroboration, SerpAPI as optional
  convenience, and DataForSEO/manual imports for enrichment. Reverify before
  implementation.
- **Exact volume removed as requirement:** Approximate volume remains nullable
  corroboration. Missing or zero volume cannot exclude a query family.
- **Full-page crawling narrowed to exception handling:** Classify first from raw
  SERP fields and fetch pages only for low-confidence or shortlisted cases.
- **Competitor made orthogonal:** Although practical notes list
  `competitor_page` among possible final classes, the ideal multi-axis model is
  canonical: competitor status is a separate flag from page surface.
- **Single label constrained:** `discoverability_signal` may be a headline label,
  but demand and intent-gap labels plus all raw components must remain visible.

## Context Change Log

- **2026-08-15:** Created cluster context from supplied ideal Search Discovery
  specification and practical API-availability assessment. Recorded practical
  MVP overrides without treating either source as collected market evidence.
