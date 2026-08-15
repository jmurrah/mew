# Cluster Context: `dissatisfaction`

This file distills two user-supplied planning inputs received on 2026-08-15:

1. An ideal specification for a dissatisfaction and complaint evidence cluster.
2. A practical assessment of free API and public-source availability.

The PDF describes the desired evidence model. The practical assessment narrows
what an inexpensive MVP can support. Neither input is collected market evidence,
and neither belongs in `PROFILE.md` or `evidence/` as proof of market demand.
Provider facts, policies, limits, and package behavior are a planning snapshot
that must be reverified before implementation or collection.

## Identity

- **Cluster ID:** `dissatisfaction`
- **Display name:** Dissatisfaction and Complaint Evidence
- **Python module:** `dissatisfaction.py`
- **Purpose:** Determine whether users are repeatedly unhappy with existing
  products and preserve enough inspectable detail to identify the exact failing
  object, blocked outcome, consequence, recency, recurrence, and source context.

## Central Research Question

Are users unhappy with current products, and exactly what are they unhappy
about?

A useful complaint contains enough evidence for manual inspection: source,
product, date, text, and a specific problem object or blocked outcome. Negative
sentiment alone is insufficient.

The cluster must stop at organized dissatisfaction evidence. It may surface
specific, repeated, recent, severe, cross-product, or plausibly solvable pain for
manual investigation, but it must not choose a product opportunity, claim a
verified market gap, or make a build decision.

## Scope

### Included

- Complaint-bearing reviews, issues, discussions, and public support records.
- Product/source snapshots containing displayed ratings, rating distributions,
  written-review counts, versions, update dates, and source mechanics when
  exposed.
- Specific failures, blocked outcomes, affected workflows, requested or removed
  features, consequences, and public response behavior.
- Complaints inside positive or high-star reviews.
- Theme recurrence within products, across products, across sources, across time
  windows, and around releases when the source supports those observations.
- Stated switching, cancellation, uninstall, refund, or willingness-to-pay
  language, clearly labeled as statements.
- Coverage, pagination, sampling, country, language, query, sort, access method,
  errors, and collection quality needed to bound claims.
- Representative confirming excerpts and nearby contradictory records.
- Manual URLs for useful sources that cannot be collected automatically.

### Excluded

- A sentiment dashboard, automatic idea generator, market-gap verdict, go/no-go
  engine, opportunity score, or product recommendation.
- Claims about all customers, actual satisfaction prevalence, retention,
  conversion, refund rate, or uninstall rate from public complaints.
- Silent churn or silent abandonment estimates.
- Verified willingness-to-pay or monetization probability inferred from text.
- Reliable fake-review detection or automatic record exclusion based on anomaly
  flags.
- Causal claims that an update produced complaints when only temporal proximity
  is observed.
- Claims about complete support quality or resolution from public replies or
  issue closure alone.
- Cross-platform reviewer identity resolution or reviewer-profile histories.
- Device or operating-system complaint rates when competitor sources do not
  expose representative device metadata.
- Automated Capterra collection.
- MVP ingestion from G2, GetApp, Software Advice, Chrome Web Store reviews,
  social-media firehoses, private communities, or other deferred sources.
- Global and multilingual comparison in MVP. Initial collection scope is US and
  English unless later guidance changes it.
- Complete lifetime review coverage where public access cannot establish it.

All nine profile sections remain required. Sections outside dissatisfaction
stay empty until collected records genuinely support them.

## Canonical Terminology

- **Complaint evidence unit:** One inspectable review, issue, discussion post,
  or public support record with stable identity, source, product, date, text,
  and collection metadata.
- **Useful complaint:** Complaint with a theme plus a specific problem object or
  blocked outcome. Pure negativity does not qualify.
- **Generic negativity:** Negative emotion without a product-specific object,
  workflow, capability, consequence, or reproducible context.
- **Problem object:** Feature, workflow, account state, charge, ad placement,
  data object, integration, device interaction, or other concrete subject of the
  complaint.
- **Blocked outcome:** Job or desired result the product prevents or degrades.
- **Complaint theme:** Derived classification such as missing feature, pricing,
  reliability, data loss, or support failure. It is not raw proof.
- **Complaint tagging row:** One review-theme pair. One review may produce
  multiple rows without becoming multiple raw reviews.
- **Product/source snapshot:** Source-specific product metrics observed on one
  date. Snapshots must not silently merge unlike store mechanics.
- **Sample metric:** Metric computed from an incomplete, capped, region-limited,
  sort-dependent, or otherwise non-population collection.
- **Population metric:** Metric whose denominator and collection coverage are
  known to represent the relevant source population or complete filter.
- **Coverage scope:** Explicit collection class: `complete_population`,
  `complete_for_filter`, `recent_window`, `page_limited`, `sample`, or `unknown`.
- **Source evidence type:** Native record family such as `review`,
  `issue_tracker`, `discussion`, or `support_thread`. These types do not share a
  denominator.
- **Specificity score:** Derived zero-to-four rubric describing inspectability,
  not truth or importance.
- **Harm score:** Derived consequence label separate from complaint frequency.
- **Solvability estimate:** Human- or model-assisted assessment of controllability,
  never a fact or automatic exclusion rule.
- **Rating/review mismatch:** Observed divergence between star rating and review
  text, or between displayed average and recent sampled complaint text. It does
  not prove fraud or rating inaccuracy.
- **Planning context:** Supplied specifications, source-access claims,
  thresholds, schemas, and architecture suggestions. It guides future work but
  is not market evidence.

## Evidence Architecture

Maintain four linked levels without collapsing them:

1. **Evidence units:** raw complaint-bearing records with source metadata and
   original text.
2. **Theme rollups:** counts, dates, trends, consequences, and representative
   evidence IDs for complaint types.
3. **Product/source snapshots:** rating distributions, written-review counts,
   version and date context, public response fields, and collection coverage.
4. **Cross-product comparisons:** recurrence of the same failing job, feature,
   workflow, or outcome across a defined competitor set.

Raw records are evidence. Themes, clusters, summaries, confidence values,
specificity, harm, solvability, trend labels, and signal labels are derived
navigation aids. Every derived row must retain the raw record IDs supporting it.

Sources are not interchangeable. Preserve platform mechanics and native
denominators. Google Play's visible rating may emphasize recent ratings; Apple
overview ratings may be reset and are country-specific; issue trackers represent
technical and formal reporters rather than a review population. Never flatten
these into one universal product score.

### Rationale Preserved from the Ideal Specification

The supplied ideal specification cites research and operator guidance for these
design choices. Treat these as planning claims pending source review, not market
evidence:

- Review classification and clustering reduce manual effort, but counts, dates,
  ratings, products, versions, excerpts, and links remain the trustworthy layer.
- App-review research commonly separates actionable bug reports, feature
  requests, and user-experience complaints.
- One cited feature-request study reported 23.3% of its analyzed reviews as
  feature requests. A cited iOS complaint study reported 18.8% of post-update
  complaint reviews involved new or previously removed feature requests.
- The cited iOS study distinguishes complaint frequency from negative impact;
  privacy/ethical issues, hidden costs, and feature removal may be highly
  negative even when other categories occur more often.
- Cited advertising research describes 15 in-app advertising issue types and
  reports that more than half of studied ad-supported apps had at least 3.28% of
  complaints addressing ads.
- Cited helpfulness research suggests concrete written details, timeliness,
  valence, and similarity among reviews affect perceived usefulness and
  credibility. Repeated specific wording is therefore useful, while duplicate
  or coordinated text remains a false-positive risk.
- Supplied survey material says many buyers trust written reviews more than star
  ratings alone. Written-review density is therefore useful only when its
  denominator is reliable.
- JTBD framing motivates extracting the failing outcome, not merely emotion.

## Complaint Qualification

### Specificity Rubric

Suggested score:

- **0:** Pure negativity without an inspectable object. Example: “Terrible app.”
- **1:** Complaint theme only. Example: “Too expensive.”
- **2:** Theme plus affected object or flow. Example: “Too expensive for basic
  export.”
- **3:** Theme, object, and consequence or context. Example: a new paywall blocks
  CSV export needed for reports.
- **4:** Theme, object, consequence, and reproducibility detail. Example: named
  version/device plus a repeatable sync failure that deletes due dates.

Useful evidence should normally clear both a specificity threshold and a
problem-object threshold. Preserve low-specificity records; downweight or route
them for manual review rather than deleting them.

### Weak or Generic Records

Usually weak unless repetition and context change their interpretation:

- One-line insults or vague praise/criticism.
- Sarcasm without a concrete issue.
- Off-topic or ideological complaints unrelated to product execution.
- Blanket demands that everything be free.
- Pricing or ad complaints with no product-specific object or consequence.
- Repetitive identical text or suspiciously templated phrasing.

Do not convert these patterns into a fake-review conclusion.

### Behavioral Signals

Capture explicit statements that the reviewer will or did:

- switch products;
- cancel a subscription;
- uninstall or stop using the product;
- request a refund;
- look for an alternative;
- pay for a stated fix or cleaner alternative.

Store these as `stated_*` fields. They are observable claims in text, not
verified behavior or population rates.

## Complaint Taxonomy

### Core Themes

- **Missing feature:** Requested capability, repeated entity, affected workflow,
  blocked job, star context, recurrence across competitors.
- **Removed feature:** Explicit loss language, former behavior, release/version
  context, switching or churn language.
- **Update regression:** “After update” language, visible version, review timing,
  release window, possible spike.
- **Reliability and bugs:** Crashes, freezes, failure to open, sync or network
  errors, heavy battery/resource use, broken core flows.
- **Data loss:** Missing or deleted data, broken backups, failed restore,
  duplicate creation, or sync overwrite.
- **Login and access:** Sign-in failures, lockouts, verification loops, password
  reset dead ends.
- **UX and complexity:** Confusing layout, excess steps, hidden actions, clutter,
  poor onboarding, hard setup, or workaround creation.
- **Pricing and subscription:** High price, value mismatch, forced recurring
  payment, hidden charges, trial confusion, cancellation difficulty, refund
  disputes, or formerly free capability moved behind a paywall.
- **Ads:** Frequency, placement, timing, interruptiveness, task blocking,
  accidental clicks, auto-audio, lag, battery, privacy, or security effects.
- **Support:** No reply, delayed reply, generic or canned response, inability to
  reach a human, unresolved billing or product complaint.
- **Privacy and trust:** Unexpected permissions or data collection, deception,
  scam language, or policy distrust.
- **Compatibility and integration:** Device/browser/OS mismatch, missing export,
  API, integration, interoperability, or data portability.
- **Content or domain fit:** Product does not fit the use case; preserve whether
  complaint targets execution or the underlying domain/content model.

### Required Distinctions

Missing-feature evidence must distinguish:

1. Net-new request.
2. Gap against an expected category baseline.
3. Removed capability.

Pricing evidence must distinguish:

- high price with accepted value;
- high price with low value;
- unexpected recurring subscription;
- charge surprise;
- refund difficulty;
- hidden pricing;
- formerly free capability moved behind a paywall.

Ad evidence must distinguish frequency, placement, timing, interruption,
task-blocking behavior, and secondary harm.

### Harm and Consequence

Frequency and impact are separate. Extract the outcome and a nullable derived
harm category such as:

- annoyance;
- friction;
- blocked task;
- account lockout;
- data loss;
- money loss;
- abandonment.

Do not infer severity only from angry wording.

### Solvability

Suggested derived labels:

- **Directly solvable:** Narrow engineering, workflow, access, export,
  onboarding, performance, or public-support process issue.
- **Product tradeoff:** Real but requires segment or roadmap choice.
- **Business-model pain:** Pricing, advertising, privacy posture, or positioning
  change may be required.
- **External or domain inherent:** Driven mainly by regulation, platform policy,
  upstream dependencies, or unavoidable domain complexity.
- **Unknown:** Evidence is insufficient.

Store `solvability_estimate`, `solvability_reason`,
`solvability_confidence`, and `manual_verified`. Never let this estimate
automatically eliminate evidence or choose an opportunity.

## Time, Ratings, and Density

### Time Windows

Retain raw dates and support multiple windows when coverage permits:

- last 30 days;
- last 90 days;
- last 180 days;
- lifetime only when collection coverage supports it;
- release-linked windows, suggested as 14 days before and after a release.

For each theme, retain first seen, most recent seen, raw window counts,
recency-weighted count if later authorized, persistence across windows, and a
possible post-release spike flag. Old records remain useful for determining
whether pain persisted or disappeared.

Never label temporal association as causation. Use
`possible_post_update_spike_flag`, not `update_caused_complaints`.

### Rating Context

Average stars alone are incomplete. Preserve when available:

- displayed average rating;
- lifetime average rating, separately;
- total ratings;
- total written reviews;
- written-review density with denominator source;
- reviews collected and recent written-review counts;
- one- through five-star counts or shares;
- population or sample negative-review ratio;
- population or sample complaint ratio;
- population or sample specific-complaint ratio;
- theme-specific rating distribution.

`written_review_density` is valid only when both total ratings and total written
reviews are trustworthy. Keep `written_review_density_available` and
`written_review_denominator_source`.

### Rating/Text Mismatch

Preserve review-level and product-level observations:

- high-star review with angry or complaint-bearing text;
- low-star review with positive-leaning text;
- high displayed average with repeated recent sampled complaints;
- recent text trend worsening while displayed average remains high;
- repeated missing-feature requests inside four- or five-star reviews.

Preferred flags:

- `high_average_recent_sample_anger_flag`
- `loyal_user_missing_feature_flag`

These flags identify records for inspection. They do not prove manipulated,
fraudulent, or inaccurate ratings.

## False Positives and False Negatives

### Main False Positives

- Fake, bought, incentivized, coordinated, brigaded, or competitor-authored
  reviews.
- Off-topic policy or ideological disputes unrelated to product execution.
- One-time outage or release spikes that do not persist.
- Old complaints fixed in later versions.
- Strong emotion without a specific object.
- Vocal-minority demands that do not recur beyond one narrow group.
- “Make it free” complaints mistaken for deceptive or mismatched pricing.
- Duplicated, syndicated, quoted, or near-identical text counted repeatedly.

Weak anomaly signals may include duplicate text, bursts, repetitive phrasing,
identical structure, rating/text contradiction, and off-topic content. Store
`suspicious_review_pattern_flag`; never store `fake_review_flag` as if verified,
and never remove records automatically on this basis.

### Main False Negatives

- Reviewers are self-selected and not representative of all users.
- Written-review density may be low despite real dissatisfaction.
- Churn and abandonment may occur silently.
- Useful complaints may be buried in high-star reviews.
- Recency weighting, country storefronts, or rating resets may hide historical
  pain.
- Support tickets, private communities, forums, and search behavior may contain
  complaints absent from stores.
- Moderation, deletion, suspicious-activity handling, caps, or access limits may
  remove visible records.

Public complaint evidence is a sampled observation of expressed dissatisfaction,
not a representative customer survey.

## Source Strategy

Access notes below came from the supplied practical assessment. Recheck current
official documents, terms, limits, and package behavior before use.

### Phase 1A: Prove Analysis on Structured Sources

- **Mozilla Add-ons:** Preferred reference collector because the documented
  public API reportedly exposes add-on metadata, users, versions, ratings,
  grouped star counts, written-review counts, review bodies, pagination,
  filtering, and developer replies. It may support population or
  complete-filter metrics when pagination is exhausted. Scope is browser
  extensions; API stability is not guaranteed.
- **GitHub Issues and Discussions:** Strong structured source for public
  developer products. Preserve issue title/body, labels, state, dates, comments,
  reactions, milestones, assignees, maintainer replies, linked pull requests,
  discussion categories, and duplicates. Treat records as
  `source_evidence_type = issue_tracker`, not reviews. Expect technical-user,
  open-source, and formal-reporting bias. Supplied access snapshot reports 5,000
  authenticated REST requests per hour and 60 unauthenticated public requests,
  with tighter search limits.

Suggested initial analysis for these sources: deterministic rules, local
embeddings, optional local LLM tagging, local analytical storage, and CSV export
with raw IDs and URLs. This is staged planning, not an implementation request.

### Phase 1B: Add Mobile-App Samples

- **Google Play:** Google's official Reviews API is described as suitable for
  apps managed by the authenticated publisher, not arbitrary competitors. For
  competitor research, the supplied plan recommends the unofficial Python
  `google-play-scraper` package. Reported fields include stable review ID, text,
  score, date, review-created/current app version, helpful votes, developer
  response, and response date. Newest sorting, score filtering, continuation
  pagination, and up to 200 records per public page are reported. Suggested
  investigation bounds are newest 500–2,000 reviews, up to 500 recent one- or
  two-star reviews, plus a smaller high-star sample. Do not claim every lifetime
  review, stable ordering, global representation, or competitor device metadata.
  Treat this collector as brittle and unofficial.
- **Apple App Store:** Official search supports discovery and metadata but not
  arbitrary competitor review histories. Public feeds/pages or unofficial
  adapters reportedly expose review ID, reviewer, version, score, title, text,
  update date, URL, country, and recent/helpful sort. Common tooling reports a
  ten-page cap. Favor a small internal Python adapter with fixture tests or a
  maintained Node adapter over an abandoned foundational Python dependency,
  subject to verification. Treat reviews as recent, page-limited,
  country-specific samples. Preserve displayed rating, rating count/histogram,
  visible version history, pages collected, date range, and coverage status.

The supplied final MVP combination is Google Play sample, Apple sample, Mozilla
complete reviews where supported, GitHub issues, local rules/embeddings, and
explicit coverage metadata. Phase 1A remains the lower-risk starting slice;
Phase 1B completes that broader MVP.

### Phase 1C: Broaden Small-Product Ecosystems

- **WordPress.org:** Official metadata reportedly exposes ratings, active
  installs, update data, and product details. Public support and review text may
  require polite RSS or static HTML parsing. Useful native observations include
  support state, replies, author participation, compatibility complaints,
  rating distribution, install scale, and last update. Measure public response
  behavior, unresolved public topics, compatibility recurrence, and possible
  abandonment without inferring private support quality.
- **Stack Exchange:** Optional corroboration for repeated workflow limitations,
  especially developer tools. Weak product-rating context.
- **Hacker News:** Optional qualitative corroboration through official Firebase
  item hydration. Sparse, noisy, technically skewed, and awkward to traverse.
- **Trustpilot:** Phase 2 only, contingent on acceptable account/API-key access,
  current terms, and company-level relevance. It may be less useful for narrow
  app-feature complaints.

### Deferred or Excluded Automatic Sources

- **Reddit:** Valuable complaints, alternatives, and workarounds, but supplied
  terms notes require OAuth, unique user agent, deletion reconciliation, and
  removal of stored content when deleted upstream. Reported eligible-free-use
  limit is 100 queries per minute. Supplied guidance also reports a recommendation
  to routinely delete stored user content within 48 hours when appropriate and
  says retaining upstream-deleted content, even anonymized, violates the terms.
  If later used, retain post/comment IDs, regularly reconcile deletions, mark
  `deleted_upstream`, remove deleted raw text, and recompute affected aggregates.
  Do not make Reddit foundational.
- **Capterra:** Exclude automated collection. Supplied terms assessment reports
  prohibitions on scraping, automated data collection, and use of content in
  machine-learning systems without authorization. Manual URL and observation
  entry may be supported.
- **G2, GetApp, Software Advice:** No suitable public competitor-review API was
  identified in supplied planning. Defer pending licensed access and terms
  review. Preserve manual research URLs only.
- **Chrome Web Store reviews:** No robust official API for arbitrary competitor
  review histories was identified. Mozilla provides a related, more accessible
  extension market. Chrome listing URLs may belong in competitor/supply work.
- **X, LinkedIn, Facebook, Discord, Slack:** Exclude from MVP because of API,
  authentication, privacy, permissions, cost, instability, and weak-denominator
  concerns.
- **YouTube comments:** Defer. Comments are noisy and often concern presentation
  rather than product use.
- **Global/multilingual collection:** Defer. Start with country `US` and English.
  Preserve encountered non-English records with
  `classification_status = unsupported_language`.

### Source-Specific Native Measures

Candidate measures must stay source-specific:

- **Mozilla Add-ons:** Written-review density, population negative-rating ratio
  when pagination and filters are complete, rating histogram, version-linked
  complaints, users, public replies, and complaint counts per known written
  review denominator.
- **GitHub:** Open bugs and feature requests, unresolved age, no-maintainer-reply
  count, first-public-maintainer-response delay, reaction counts, closure and
  reopen/regression observations, duplicates, repeated clusters, and
  workaround-containing issues. Do not compare these directly with review
  ratios.
- **WordPress.org:** Unresolved public-topic ratio, no-author-response count,
  public first-response time, old unresolved topics, compatibility recurrence,
  update age, active-install context, rating distribution, and possible
  abandoned-plugin indicator.
- **Google Play and Apple:** Recent collected complaint counts, theme and
  version observations, displayed rating/histogram snapshots, public reply
  presence, and sample ratios tied to country, sort, page, and date coverage.

## Collection Coverage Contract

Every run should preserve:

```text
collector_name
collector_version
collector_access_type
collection_started_at
collection_completed_at
source_terms_reviewed_at
product_id
source_product_url
query_country
query_language
query_sort
requested_review_count
returned_review_count
pages_requested
pages_completed
pagination_exhausted
coverage_scope
coverage_notes
oldest_record_date
newest_record_date
raw_snapshot_path
raw_snapshot_hash
http_error_count
rate_limit_events
collection_success
```

Allowed `collector_access_type` values should include:

- `official_public_api`
- `official_authenticated_api`
- `public_rss`
- `public_html`
- `unofficial_library`
- `manual_entry`

Allowed `coverage_scope` values should include:

- `complete_population`
- `complete_for_filter`
- `recent_window`
- `page_limited`
- `sample`
- `unknown`

Coverage belongs on both collection runs and derived metrics. A count in a
collected 90-day window means “within retrieved coverage,” not necessarily all
records published in that window.

## Record and Output Guidance

### Product/Source Snapshot

One row per product, source, country/region, and observation date. Preserve:

- observation and collection-run IDs;
- source type/name and source evidence type;
- product ID, name, vendor, category, URL, platform, country, language;
- displayed and lifetime averages separately;
- total ratings and total written reviews when trustworthy;
- one- through five-star histogram;
- written-review density availability and denominator source;
- recent written-review counts within collected coverage;
- current version and last update date;
- collection coverage class and notes on store mechanics.

### Review or Complaint Evidence Unit

One row per source-native record. Preserve when available:

- stable review/issue/post ID, product and source IDs, URLs;
- publication, update, first-observed, and last-observed dates;
- country, language, original text, optional machine translation, and short
  quoted excerpt;
- title, star rating, public author handle, visible version, and explicitly
  mentioned device or operating system;
- developer or maintainer response presence, date, and text;
- source-native helpful votes, reactions, comments, labels, state, or other
  metrics without universal normalization;
- changed/edited state visible across snapshots;
- complaint presence, specificity, harm, switching, uninstall, cancellation,
  stated willingness to pay, update linkage, anomaly flags, manual priority;
- raw snapshot path/hash, collector/run identity, and coverage scope.

Where source terms require deletion or minimization, retention rules override
the general preference to retain full raw text.

### Complaint Tagging

One row per evidence-unit/theme pair. Suggested fields:

```text
evidence_id
theme_primary
theme_secondary
subtheme
requested_feature_entity
affected_workflow
failure_object
consequence_type
consequence_text
workaround_present
workaround_text
feature_removed_flag
pricing_surprise_flag
forced_subscription_flag
refund_or_cancel_flag
ads_frequency_flag
ads_intrusion_flag
ux_complexity_flag
bugs_or_crashes_flag
data_loss_flag
account_lockout_flag
support_failure_flag
privacy_trust_flag
integration_export_gap_flag
solvability_estimate
solvability_reason
solvability_confidence
theme_confidence
manual_verified
```

NLP may help populate these fields. The source record remains proof.

### Theme Summary

One row per product/source/theme/window. Preserve:

- complaint and specific-complaint counts;
- coverage-aware recency weighting if later authorized;
- share of collected complaints, star distribution, first/latest dates;
- trend and growth with method/version;
- possible post-update spike and severe-consequence counts;
- switching and stated willingness-to-pay counts;
- repeated phrases and requested entities;
- oldest, newest, and representative evidence IDs.

### Product Signal Summary

One row per product/source/window. Preserve raw metrics beneath any label:

- collected written-review count;
- useful and specific complaint counts and ratios;
- population or sample negative-review ratio;
- top themes and counts;
- pricing, ad, missing-feature, support, and data-loss counts;
- rating/review mismatch count;
- public response count/rate;
- high-average/recent-sample-anger flag;
- coverage label and manual verification count;
- derived dissatisfaction label only if later authorized.

### Cross-Product Gap Summary

One row per theme across an explicitly defined competitor set. Preserve:

- market query and competitor-set definition;
- products examined and products containing the theme;
- total and recent mentions within each source's coverage;
- common requested entities, failure objects, and blocked outcomes;
- source consensus without combining unlike denominators;
- representative product and evidence IDs;
- manual investigation priority as an inference.

Cross-product recurrence is a strong routing signal, not proof of a viable gap.

### Human-Readable Profile

The required `PROFILE.md` remains the nine-part human-readable summary. Logical
“sheets” from the ideal design may be stored as CSV, JSONL, Markdown, or local
analytical tables; an `.xlsx` workbook is not mandatory. Outputs must remain
spreadsheet-friendly and manually inspectable.

## Metric Naming and Claim Boundaries

Use population names only for known denominators. Otherwise prefer:

- `sample_negative_review_ratio`
- `sample_complaint_ratio`
- `sample_specific_complaint_ratio`
- `reviews_collected_count`
- `review_pages_collected`
- `oldest_review_in_sample`
- `newest_review_in_sample`
- `written_review_coverage_status`

Use `population_negative_rating_ratio` only when source and pagination support
the claimed population.

Use `public_response_rate`, not `support_response_rate`. Private email, ticket,
or chat handling is invisible.

Keep separate:

- `public_reply_present`
- `issue_closed`
- `review_edited_after_reply`
- `review_score_changed_after_reply`
- `resolution_claimed_in_text`

Do not create a generic `resolved = true` unless the source explicitly provides
a meaningful resolution state.

Use:

- `stated_uninstall_intent`
- `stated_cancellation`
- `stated_switching_behavior`
- `stated_willingness_to_pay`

Do not convert these into churn, cancellation, switching, or purchase rates.

## MVP Metric Set

### Product and Coverage

- Displayed average rating and current histogram.
- Total ratings and written reviews when known.
- Reviews collected, country, language, date range, sort, and pages.
- Current version, last update, and coverage classification.

### Complaint Evidence

- Useful, specific, and generic-negativity counts.
- One- to two-star and three- to five-star complaint counts.
- Missing and removed feature counts.
- Pricing/subscription, ads, bug/crash, data-loss, login/access, UX/complexity,
  and public-support complaint counts.
- Stated switching, uninstall, cancellation, refund, and willingness-to-pay
  counts.

### Recency and Repetition

- Counts inside collected 30-, 90-, and 180-day windows.
- Theme first/latest dates and cluster size.
- Products represented per theme.
- Version-linked count and possible post-update spike flag.

### Evidence Quality

- Specificity distribution and ratio.
- Stable evidence IDs, source links, and representative excerpts.
- Rating/text mismatch count.
- Public developer/maintainer response count.
- Coverage label and manual verification count.

### Candidate Scan Flags

These provisional flags support spreadsheet triage. Each must expose its raw
conditions and coverage:

- `high_average_recent_sample_anger_flag`
- `loyal_user_missing_feature_flag`
- `possible_post_update_spike_flag`
- `removed_feature_flag`
- `pricing_surprise_flag`
- `refund_cancellation_pain_flag`
- `ad_intrusion_flag`
- `data_loss_flag`
- `account_lockout_flag`
- `support_escalation_flag`
- `cross_competitor_gap_flag`

## Deferred Metrics and Claims

Do not spend MVP effort on:

- lifetime complaint ratios under incomplete coverage;
- global rating comparisons;
- device or operating-system complaint rates;
- fake-review probability;
- silent churn, retention, conversion, or abandonment estimates;
- actual willingness-to-pay, refund, or cancellation rates;
- verified support-resolution rate;
- causal post-update conclusions;
- automated solvability exclusion;
- screenshots of every record;
- reviewer profiles or cross-product histories;
- helpfulness downvotes where sources do not expose them;
- translation and multilingual comparison;
- Capterra/G2 ingestion;
- social-media firehose collection.

Nullable forward-compatible fields are acceptable, but unavailable values must
remain `NULL`, never zero.

## Local Processing Direction

This section records nonbinding design context, not authorization to implement.

### Collection

- `httpx` or `requests` for HTTP.
- `tenacity` for retry and backoff.
- `google-play-scraper` for Google Play competitor samples, after verification.
- `feedparser` for RSS.
- Beautiful Soup or `lxml` for permitted static HTML.
- GitHub REST/GraphQL through direct HTTP or a maintained client.
- Browser automation only as a last resort, never the default.

### Storage

The supplied plan prefers DuckDB for analytical tables and repeated
aggregations, with SQLite as an alternative. Preserve immutable API/page
snapshots as JSON or compressed JSON, normalized exports as JSONL/CSV, and
analytical exports as CSV or Parquet when useful. No storage choice or schema is
approved by this context-only task.

### Classification

Start with deterministic regex and rule matching for phrases such as:

- “please add,” “wish it had,” “there is no way to”;
- “used to have,” “removed,” “after the update”;
- “subscription,” “charged,” “refund,” “cancel”;
- “too many ads,” “crashes,” “lost all,” “won't sync”;
- “no response,” “switching to,” “uninstalled.”

Rules should target high-precision categories such as pricing surprise, forced
subscription, ad frequency, feature requests, removed features, data loss,
cancellation, and switching intent. Use spaCy patterns when token context or
grammatical relationships improve precision.

### Semantic Grouping

Local embeddings may group semantically related complaints. Suggested tools are
`sentence-transformers`, scikit-learn, agglomerative clustering, HDBSCAN, and
optionally BERTopic. Preserve cluster ID, member evidence IDs, size,
representative records, common phrases, products represented, and first/latest
dates. Cluster membership and labels are inference, not proof.

### Optional Local LLM

A local model may propose complaint theme, specificity, harm, workflow,
requested feature, solvability, and short excerpt using structured output.
Preserve model name/version, prompt version, output schema version, confidence,
rule matches, source text, and manual verification state. LLM tagging remains
optional; rules plus embeddings may be enough for MVP.

## Provisional Signal Labels

The ideal specification proposed the following triage thresholds. They are
unvalidated design hypotheses, not published standards, truth labels, or
approved implementation requirements.

- **Weak dissatisfaction:** At least 5 useful complaint reviews in 90 days, or
  at least 15% useful complaints among collected written reviews in that window,
  plus one repeated theme with at least 3 mentions.
- **Medium dissatisfaction:** At least 12 useful complaints in 90 days, at least
  25% useful complaints, at least 50% specific complaints, and one meaningful
  theme with at least 5 mentions.
- **Strong dissatisfaction:** At least 25 useful complaints in 90 days or 10 in
  30 days, at least 35% useful complaints, at least 60% specific complaints, and
  one severe or high-opportunity theme with at least 8 mentions.
- **Strong and promising market-gap signal:** Strong dissatisfaction plus
  cross-product repetition, persistence across 180 days, or a high displayed
  rating masking a recent complaint cluster.

Proposed theme labels:

- **Weak:** At least 3 specific mentions.
- **Medium:** At least 5 specific mentions and at least 20% of collected
  complaints in the window.
- **Strong:** At least 8 specific mentions plus recent growth, release linkage,
  cross-product recurrence, or severe consequence language.

Proposed solvability strength is high for narrow/directly solvable themes,
medium for narrow product tradeoffs, and low for primarily business-model or
domain-inherent pain.

If labels are later authorized, expose every raw condition, coverage class,
denominator, override, uncertainty, and representative evidence ID. Never turn
them into one opportunity score or build decision.

## Manual Inspection Standard

Every claim should answer:

- Which source, product, country, language, and collection window?
- How many source-native records were collected and how complete was collection?
- What exact object, workflow, job, or outcome failed?
- When did complaints appear, persist, fade, or spike?
- Which products and source types contained the theme?
- Which evidence IDs show the strongest examples?
- Which nearby records contradict or weaken the interpretation?

A strong claim should normally preserve at least three independent excerpts,
an adequate written-record denominator, and cross-product or cross-source
corroboration where possible. Preserve at least one non-confirming or
contradictory excerpt when the signal is mixed. These examples are navigation
aids; distributions and raw records remain inspectable.

## Confirmed Facts

- No market evidence has been collected for this cluster.
- The supplied PDF and practical API notes are planning context only.
- The user explicitly requested context and agent-file updates, not
  implementation.
- API availability, pricing, quotas, platform mechanics, package behavior, and
  terms claims have not been independently verified in this task.

## Hypotheses

- Specific, repeated, narrow complaints with behavioral consequences are more
  useful for manual market-gap research than generic negative sentiment.
- Cross-product recurrence of the same blocked outcome may be more informative
  than a temporary complaint spike within one product.
- High-star feature requests may reveal unmet demand before average ratings
  deteriorate.
- Mozilla Add-ons and GitHub can provide the cleanest first proof of collection
  and analysis because their public interfaces are comparatively structured.
- The provisional weak/medium/strong thresholds may help triage records after
  collection, but require calibration and manual review.

## Open Questions

- Which source should be implemented first after the top-level runner contract
  exists: Mozilla Add-ons, GitHub, or both?
- Which exact competitor-set definition and market query will each collection
  run receive?
- Should storage use DuckDB, SQLite, or only file exports initially?
- Which Apple public adapter is currently permitted, stable, and maintainable?
- What source-specific thresholds are appropriate after real coverage and
  distributions are observed?
- How should manual verification workflow and contradiction selection be stored?
- Should recurring snapshots track review edits and rating-histogram changes
  from first collection onward?
- Which sources require source-specific deletion, minimization, or licensing
  rules beyond the general evidence-preservation contract?

## Decisions and Superseded Guidance

- The practical access assessment narrows the ideal universal-source design for
  MVP. Start with structured free sources, then mobile samples; postpone or
  exclude sources with poor access, high compliance cost, unclear licensing, or
  fragile collection.
- The ideal specification's unqualified review ratios are superseded where
  coverage is incomplete. Use explicit sample metrics and coverage metadata.
- `negative_review_ratio`, `complaint_review_ratio`, and similar fields are not
  population claims unless denominators and pagination prove population
  coverage.
- `post_update_spike_flag` is narrowed to
  `possible_post_update_spike_flag`; timing alone does not establish causation.
- `support_response_rate` is narrowed to `public_response_rate`; private support
  is not observable.
- `fake_review_flag` is replaced by `suspicious_review_pattern_flag`; public
  data cannot reliably authenticate reviews.
- Willingness to pay, uninstall, cancellation, switching, refund, and resolution
  fields record explicit statements or native states only.
- Global and multilingual ambitions are deferred. US/English is the initial
  planning scope.
- Logical multi-sheet structure is preserved, but local CSV, JSONL, Markdown,
  Parquet, or analytical tables may implement it; `.xlsx` is not required.
- No implementation, dependency selection, storage interface, collector, or
  signal threshold is approved by this context-only update.

## Planning References

These URLs came from supplied planning inputs. They support future design review
and source verification; they are not raw market evidence:

- App-review mining systematic review:
  https://link.springer.com/article/10.1007/s10664-021-10065-7
- Google Play rating mechanics:
  https://support.google.com/googleplay/android-developer/answer/138230?hl=en
- Google Play Reviews API:
  https://developers.google.com/android-publisher/api-ref/rest/v3/reviews
- `google-play-scraper`:
  https://github.com/JoMingyu/google-play-scraper
- Apple iTunes Search API:
  https://developer.apple.com/library/archive/documentation/AudioVideo/Conceptual/iTuneSearchAPI/Searching.html
- Apple App Store ratings and reviews overview:
  https://developer.apple.com/help/app-store-connect/monitor-ratings-and-reviews/ratings-and-reviews-overview/
- `app-store-scraper`:
  https://github.com/facundoolano/app-store-scraper
- Mozilla add-on API:
  https://mozilla.github.io/addons-server/topics/api/addons.html
- Mozilla ratings API:
  https://mozilla.github.io/addons-server/topics/api/ratings.html
- GitHub REST rate limits:
  https://docs.github.com/en/rest/using-the-rest-api/rate-limits-for-the-rest-api
- WordPress.org API:
  https://codex.wordpress.org/WordPress.org_API
- Reddit Data API terms and guidance:
  https://support.reddithelp.com/hc/en-us/articles/16160319875092-Reddit-Data-API-Wiki
- Capterra terms:
  https://www.capterra.com/legal/terms-of-use/
- spaCy rule matching:
  https://spacy.io/usage/rule-based-matching/
- Sentence Transformers semantic similarity:
  https://sbert.net/docs/sentence_transformer/usage/semantic_textual_similarity.html
- Ollama structured outputs:
  https://docs.ollama.com/capabilities/structured-outputs
- JTBD framework:
  https://strategyn.com/jobs-to-be-done/
- iOS complaint taxonomy research:
  https://cs.uwaterloo.ca/~m2nagapp/publications/pdfs/What-Do-Mobile-App-Users-Complain-About-A-Study-on-Free-iOS-Apps.pdf
- App feature-request research:
  https://ieeexplore.ieee.org/document/6624001/
- In-app advertising issue research:
  https://xin-xia.github.io/publication/ist211.pdf
- Fake app-review research:
  https://link.springer.com/article/10.1007/s10664-019-09706-9
- Review-system bias research:
  https://www.sciencedirect.com/science/article/abs/pii/S0167923617300428
- Review helpfulness and linguistic similarity research:
  https://researchmgt.monash.edu/ws/files/632550033/629297137-oa.pdf

## Context Change Log

- 2026-08-15: Created `dissatisfaction` cluster context from the supplied ideal
  specification and practical API-availability assessment. Recorded the
  practical MVP boundary as a constraint on the ideal design. No market evidence
  was collected and no implementation was added.
