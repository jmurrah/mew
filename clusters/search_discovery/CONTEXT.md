# Search and Discovery Evidence

- **Cluster ID:** `search_discovery`
- **Python module:** `search_discovery.py`
- **Layer:** Market evidence

Shared rules: [Evidence Contract](../../docs/core/evidence-contract.md).
Field catalog: [Cluster Records](../../docs/schemas/cluster-records.md#search-discovery).

## Purpose

Show whether people express a specific job in search and whether a captured
discovery surface serves that intent directly, indirectly, or poorly. The result
is evidence about one recorded environment, not market size, universal rankings,
conversion, or profitability.

## Scope

- One problem hypothesis and one to five manual seed queries.
- Exact variants from autocomplete, related searches, manual input, trends,
  keyword tools, or competitor-derived discovery.
- Google-shaped SERP captures through a named provider.
- Brave captures as a separate engine.
- Top-N result/block observations with rank, title, URL, domain, snippet, date,
  and provider result type.
- Ads, product blocks, app results, forums units, AI Overview presence, and other
  captured features.
- Deterministic classification, selective page metadata, and traceable optional
  model classification.
- Separate demand, intent, composition, mismatch, concentration, trend, and
  commercial-support metrics.

## Out of Scope

- Exact search volume as a requirement.
- CTR, zero-click rate, unique searchers, installs, purchases, or revenue.
- Keyword difficulty, domain authority, backlink gaps, or traffic estimates in
  v1.
- Universal/personalized results, multi-environment automation, or direct Google
  scraping.
- Full-page crawl or screenshot for every result.
- Exact AI Overview text/citation analysis.
- One SEO, demand, opportunity, or market-gap score.

## Research Unit

Primary unit is a query family: related exact strings grouped under one problem
hypothesis and canonical job. Membership is derived and retains raw IDs.

Evidence remains normalized at five levels:

1. Query records.
2. Suggestion records.
3. SERP result records.
4. Query summaries.
5. Optional demand enrichment.

## Evidence Model

### Intent

- **Predicted intent:** Derived from query wording and family context;
  informational, commercial, transactional, navigational, or mixed.
- **Observed SERP intent:** Derived from returned result mix.
- **Mismatch:** Action/evaluation language met mainly by explanatory/community
  results rather than direct/evaluative product surfaces.

Preserve lexical cues, result counts, block structure, and unknowns behind each
label.

### Result Axes

Surface type:

```text
direct_tool
app_page
marketplace_listing
directory_or_review
article_or_guide
forum_or_qa
video
local_listing
irrelevant
unknown
```

Direct-solution disposition:

```text
direct
evaluative
explanatory
community
irrelevant
unknown
```

Competitor, marketplace, directory, forum, article, video, pricing, signup, and
store states are separate flags. Do not force unknown records into a class.

## Observable Fields

- Problem, query, suggestion, SERP, result, capture-run, and raw evidence IDs.
- Exact query/source, parent query, suggestion text and source order.
- Engine, provider, country, language, device, signed-in/personalization state,
  timestamp, top-N, block, provider rank, and rank-within-block.
- Title, URL, canonical URL, display/registrable domain, snippet, visible date,
  provider result type, and source flags.
- Raw provider response, request status, retry/error state, screenshot or page
  artifact when captured.
- Optional provider-native volume, monthly values, CPC, bids, paid competition,
  Trends direction, seasonality, and related terms.

## Derived Fields

- Job verb/object, audience/constraint modifier, journey stage, specificity, and
  lexical intent flags.
- Surface type, direct-solution disposition, competitor status, method,
  confidence, and notes.
- Direct, article, forum, video, directory, marketplace, irrelevant, and unknown
  counts/shares with denominator.
- Unique domains, top-domain share, competitor share, ads/product/app/forum/AI
  feature presence.
- Predicted/observed intent, mismatch severity, demand signal, intent-gap signal,
  and discoverability signal.

## Analysis

### Classification Order

1. Provider block/type.
2. Known-domain rules.
3. URL patterns.
4. Title and snippet cues.
5. Selective page metadata.
6. Optional NLP or model classification.
7. Manual review.

Every result stores method, confidence, notes, and raw IDs.

### Provisional Mismatch Thresholds

- **Strong:** Action/evaluation intent, direct-solution share at most 0.20, and
  article/forum/video share at least 0.60.
- **Medium:** Direct-solution share 0.21–0.40 or article/forum/video share
  0.45–0.59.
- **Weak:** Direct-solution share above 0.40 or product surfaces clearly match
  intent.

### Provisional Demand and Discoverability

- Strong demand candidate: five variants across suggestion/related sources,
  clear trend growth, or non-trivial keyword-tool support.
- Medium: two to four variants or mixed corroboration.
- Weak: zero or one weak variant without corroboration.
- Strong discoverability candidate: strong demand, medium/strong intent gap, and
  no heavy domain monopoly.

All thresholds require calibration. Suggestion order is not demand volume.

### Failure Modes

- Poor query wording or weak demand mistaken for gap.
- Forum-heavy results mistaken for absent tools when users prefer lived advice.
- High-volume ambiguous/zero-click head terms.
- Short-lived trend or fresh suggestions.
- Articles correctly satisfying informational intent.
- Provider normalization omitting special blocks.
- Different engines mistaken for confirmation or contradiction of Google.

## Source Applicability

Current planning prefers DataForSEO for Google Organic and Autocomplete, Brave
for development/corroboration, SerpAPI as optional convenience, and provider or
manual data for volume/Trends. See
[Search Providers](../../docs/sources/providers/search.md).

Practical v1 baseline: US English desktop, up to 10–20 variants, top ten results
per query, complete raw JSON, deterministic classification, and selective
screenshots/page fetches for strong, ambiguous, low-confidence, or requested
cases.

Research foundations:

- <https://online.hbs.edu/blog/post/jobs-to-be-done-examples>
- <https://support.google.com/websearch/answer/12412910?hl=en>
- <https://blog.google/products-and-platforms/products/search/how-google-autocomplete-predictions-work/>
- <https://developers.google.com/search/docs/appearance/structured-data/search-gallery>
- <https://blog.google/products-and-platforms/products/search/google-search-discussions-forums-news/>
- <https://ahrefs.com/blog/search-intent/>
- <https://www.semrush.com/blog/search-intent/>
- <https://www.semrush.com/blog/types-of-keywords-commercial-informational-navigational-transactional/>
- <https://www.indiehackers.com/post/how-i-ll-choose-the-next-startup-idea-b7290748bb>
- <https://help.ahrefs.com/en/articles/72571-how-accurate-is-keyword-search-volume-in-ahrefs>
- <https://ahrefs.com/blog/long-tail-keywords/>
- <https://ahrefs.com/blog/keyword-search-volume/>
- <https://support.google.com/google-ads/answer/3022575?hl=en>
- <https://support.google.com/google-ads/answer/10261137?hl=en>

These guide research design; they are not collected market evidence.

## Guardrails

- Keep Google and Brave observations separate.
- Keep volume, predicted intent, observed intent, composition, trend, paid
  competition, and concentration separate.
- Never use missing/zero volume to reject a query family.
- Preserve exact denominator and top-N/block policy.
- Use screenshots selectively; raw JSON does not reproduce pixel layout.

## Output Contract

Future required artifacts are `queries`, `suggestions`, `serp_results`, and
`query_summaries`; `keyword_enrichment` is optional. Every summary exposes
components, formulas, denominator, confidence, coverage, and raw IDs. Output
feeds section 6 of the investigation profile.

## Open Questions

- What exact query-family grouping and manual override process will apply?
- How will organic and mixed SERP block denominators be defined?
- What calibration set governs classification and mismatch thresholds?
- What concentration threshold indicates heavy domain control?
- Which screenshot mechanism satisfies triggered capture cases?
