# Cluster Context: `workaround`

This file stores durable design guidance for the Workaround Evidence cluster.
It models user-supplied ideal guidance and a practical API-access assessment.
Neither input is collected market evidence.

## Identity

- **Cluster ID:** `workaround`
- **Display name:** Workaround Evidence
- **Python module:** `workaround.py`
- **Purpose:** Find public, inspectable evidence that people or teams are
  compensating for an underserved job through substitutes, patches, manual
  routines, or stitched-together tools.
- **Decision role:** Help the user investigate whether an underlying problem
  deserves manual attention. This cluster does not choose opportunities,
  recommend products, or prove demand by itself.

## Core Research Question

Where do people repeatedly reveal an important job, a concrete substitute
behavior, and friction or cost caused by completing that job without a
purpose-built solution?

The unit of detection is not a complaint or stated preference. It is observable
compensating behavior.

## Scope

### Included

- Public statements describing manual routines, copy/paste, recurring exports,
  reconciliation, renaming, data movement, or repeated coordination.
- Stitched workflows using spreadsheets, Notion, notes, PDFs, checklists,
  calculators, Zapier, n8n, scripts, macros, formulas, or multiple apps.
- Self-built substitutes such as internal tools, personal scripts, browser
  extensions, userscripts, templates, Google Apps Script, Excel/VBA macros,
  command-line tools, and lightweight dashboards.
- Repeated requests for templates, trackers, workarounds, recommendations, or
  ways to automate the same underlying job.
- Evidence of effort: time, cadence, volume, money, tool count, collaborators,
  maintenance, breakage, errors, delay, duplicate work, or operational risk.
- Public substitute artifacts and search-result ecosystems when their relation
  to a specific problem is inspectable.
- Search results as discovery records and, when recorded as top-N result-set
  observations, as limited search/discovery evidence.

### Excluded

- Mere complaints, wishes, sentiment, or feature requests without compensating
  behavior.
- Ordinary use of flexible general-purpose tools without friction, manual
  labor, missing functionality, fragility, repeated help-seeking, or cost.
- Temporary fixes tied only to a narrow software version, short outage, or
  recently fixed defect, unless recurrence shows a persistent underlying job.
- Founder idea-fishing, lead generation, or promotional posts without
  independent user behavior in replies or linked sources.
- Private Slack or Discord communities, closed social groups, internal company
  documents, support tickets, customer calls, and private spreadsheets unless
  the user later supplies authorized material.
- Broad automated ingestion of app-store reviews, G2, Capterra, Trustpilot,
  LinkedIn, Facebook, Instagram, X, Quora, or private communities for the MVP.
- Universal web coverage, historical web-wide recurrence, accurate market
  sizing, willingness-to-pay inference, opportunity scoring, product
  recommendations, and validation or build plans.
- Automated competitor-review research. That belongs primarily with
  competitor/supply evidence and requires separate access decisions.

## Canonical Terminology

- **Job/problem:** The outcome or task the person or team is trying to complete.
- **Workaround:** Observable use of a substitute, patch, manual routine, or
  stitched process to complete a job despite friction, insufficiency, risk, or
  cost.
- **Substitute:** The concrete artifact, tool, routine, or combination used in
  place of a better-matched solution.
- **Compensating behavior:** Action taken to bridge a mismatch, such as manual
  transfer, repeated reconciliation, self-built code, or multi-tool stitching.
- **Workaround mention:** One preserved public statement or source observation
  tied to raw evidence and, when possible, one normalized problem cluster.
- **Workaround artifact:** A linked spreadsheet, template, script, repository,
  PDF, checklist, calculator, or workflow used as a substitute.
- **Problem cluster:** A revisable grouping of semantically related mentions
  about the same underlying job. Membership is derived, not collected fact.
- **Adjacent signal:** Relevant material missing one or more qualification
  elements. It remains available for review but does not count as workaround
  evidence.
- **Named substitute:** An explicitly identified tool or artifact; never infer a
  named substitute from generic workflow language.
- **Quantified effort:** Explicit time, cadence, volume, or money. Do not infer
  labor cost from salary assumptions.
- **Native engagement:** Platform-specific score, votes, replies, answers, or
  ratings stored with its native type and never normalized as proof.
- **Discovery evidence:** A search result or snippet that identifies a candidate
  source but does not yet establish the underlying claim.
- **Public evidence:** Material observable under permitted access. Missing public
  evidence does not imply the underlying behavior is absent.

## Qualification Rule

A raw mention counts as workaround evidence only when all three elements are
supported by the source:

1. A stated or reasonably inferable job or problem.
2. A concrete substitute behavior.
3. Friction, insufficiency, risk, or cost.

At least one of the following should support the third element:

- explicit friction or insufficiency language;
- explicit manual-labor language;
- quantified recurring effort;
- a self-built extension or internal artifact;
- repeated help-seeking;
- fragility, error, delay, duplicate-work, compliance, revenue, client, or
  operational-risk language.

Inference must remain labeled and linked to the exact excerpt. Ambiguous rows
become `adjacent_signal`, not confirmed workaround evidence.

## Important Distinctions

### Tool Use Is Not Automatically a Workaround

Spreadsheets, Notion, notes apps, PDFs, checklists, calculators, and automation
tools are legitimate solutions for many jobs. Their presence alone proves
nothing about mismatch. Promote a mention only when the source also shows
compensating work, repeated manual effort, missing functionality, maintenance,
fragility, or cost.

### Behavior Is Stronger Than Opinion, but Is Not Market Proof

A person investing time, attention, money, or labor is stronger evidence than a
hypothetical preference. It still does not prove market size, willingness to
pay, a viable product, or an attractive opportunity.

### Signal Strength and Effort Burden Are Separate

Do not collapse them into one conclusion. A problem may have broad recurring
evidence but little burden, or severe burden with little observable public
evidence. Both dimensions must remain inspectable.

### Raw Mentions and Rollups Are Separate

Raw statements are evidence. Normalized problem statements, cluster membership,
summaries, confidence values, counts, and labels are derived aids. Rollups must
point back to raw mention identifiers.

### Discovery and Proof Are Separate

Search snippets can be truncated, stale, or assembled from disconnected page
text. Record their query and rank, but do not treat them as full workaround
evidence until the original source is retrieved. Search-result composition can
support a limited top-N discovery observation when its sampling method is
recorded.

## Example Classification Guidance

### Likely Qualifying Mentions

- “Every Monday I copy data from two apps into a spreadsheet because neither
  exports the report we need.”
- “We wrote an internal script because the existing tools cannot reconcile the
  records; it breaks whenever the API changes.”
- “I need a template because the available products are overkill, and I still
  rebuild the report for every client.”
- “We use Zapier, Sheets, and Slack, then manually fix duplicates each week.”

These examples contain a job, a substitute behavior, and friction or cost. They
are classification examples only, not collected market evidence.

### Non-Qualifying or Adjacent Mentions

- “I use Google Sheets for inventory.” No mismatch or friction is shown.
- “I wish this app had dark mode.” No substitute behavior is shown.
- “Here is a workaround for version 3.2.1.” Treat as temporary-bug evidence
  unless persistence across time and sources is established.
- “What manual work should founders automate?” Likely idea-fishing unless
  independent replies provide concrete behavior.

## Detection Guidance

Match action plus artifact or consequence, not sentiment alone. Candidate phrase
families include:

- `copy/paste`, `manually enter`, `manual export`, `reconcile`, `rename files`;
- `track in Sheets`, `export to Excel`, `VLOOKUP`, `IMPORTRANGE`, `macro`;
- `built a script`, `built my own`, `internal tool`, `Apps Script`, `Python`,
  `SQL`;
- `hack together`, `Zapier`, `n8n`, multi-tool descriptions;
- `does anyone have a template`, `is there a tool for`, `how do you track`;
- cadence and burden phrases such as `every Monday`, `each client`, `hours a
  week`, `still breaks`, or `no one trusts`.

People often describe routines without using the word `workaround`. Prioritize
verbs, cadence, substitute artifacts, and consequences. Use semantic grouping
because similar questions can use materially different words. Preserve
membership scores and allow manual reassignment.

## Practical Source Strategy

The supplied practical assessment narrows the ideal universal-source design to
a low-cost public-web MVP. Access details below are a user-supplied planning
snapshot received on 2026-07-13, not independently verified facts. Pricing,
quotas, policies, and endpoint behavior must be checked before implementation or
collection.

### Recommended MVP Sources

1. **General web search API:** Broad discovery of public blogs, niche forums,
   Q&A, templates, and substitute ecosystems. Exa is the supplied first choice;
   Brave is an alternative or validation source. Keep the provider replaceable.
2. **Stack Exchange API:** Structured repeated questions, answers, scores,
   accepted-answer state, dates, authors, and tags. Useful sites may include
   Stack Overflow, Super User, Web Applications, Software Recommendations, Ask
   Ubuntu, Server Fault, and relevant profession-specific communities.
3. **GitHub REST API:** Repositories, issues, README text, scripts, macros,
   templates, userscripts, browser extensions, and DIY/internal-tool behavior.
   Repository and issue search are expected to be more useful than raw code
   search.
4. **Hacker News:** Use a search index such as HN Algolia for discovery, then
   hydrate stories and comments through the official Hacker News API. Treat the
   audience as technically sophisticated operators, not representative
   consumers.
5. **RSS/Atom:** Low-cost collection from blogs, changelogs, and supported niche
   communities, with ETag and `Last-Modified` support where available.
6. **Permitted static-page retrieval:** Retrieve original text and metadata from
   high-value results. Prefer an allowlist and ordinary HTTP before dynamic
   browser extraction.

### Optional Fallbacks

- Firecrawl for difficult high-value pages when permitted local extraction
  fails. It is not core infrastructure.
- Playwright for dynamic pages and screenshots only when a high-value page
  cannot otherwise be retrieved.
- Reddit only after appropriate access and terms review. Do not make it
  foundational, and preserve deletion/retention obligations. Search-only Reddit
  discoveries remain `snippet_only=true` until permitted retrieval.

### Deferred or Excluded MVP Sources

- YouTube: defer unless the niche relies primarily on tutorials; transcripts
  can be inconsistent, comments noisy, and promotional false positives common.
- Common Crawl: exclude from MVP because processing burden is disproportionate
  to initial discovery. Consider only for targeted historical backfill.
- Public competitor app reviews: official APIs generally concern
  publisher-controlled apps; arbitrary competitor coverage needs separate
  providers, scraping decisions, or manual exports.
- G2, Capterra, Trustpilot, and similar review sites: do not promise complete or
  stable automated extraction.
- LinkedIn, Facebook, Instagram, X, Quora, private communities, and internal
  company material: exclude from automatic v1 collection.
- Notion, Canva, and other template marketplaces: retain visible title, URL,
  platform, creator, price, and clearly visible ratings or counts. Do not infer
  demand, downloads, revenue, or active use from a listing's existence.

### Supplied Access Snapshot Requiring Verification

- Exa: supplied claim of up to 20,000 free requests per month, including search
  and page text/highlights.
- Brave Search: supplied claim of about 1,000 searches per month covered by
  recurring credits, then $5 per 1,000 searches.
- Stack Exchange: supplied claim of a default 10,000-request daily quota, with
  dynamic backoff and duplicate-request constraints.
- GitHub REST: supplied claim of 5,000 authenticated requests per hour, with
  lower search-specific limits.
- Hacker News official API: supplied claim of no stated rate limit, with item-by-
  item comment-tree hydration.
- Firecrawl: supplied claim of 1,000 free pages or credits per month.
- Reddit: supplied claim of OAuth approval, contractual restrictions, deletion
  obligations, and a 100-query-per-minute eligible-free-use limit.
- YouTube Data API: supplied claim of quota-based access with expensive search
  calls relative to other endpoints.

These values guide future feasibility checks only. Do not copy them into
`PROFILE.md` as evidence about a market problem.

## Retrieval and Processing Direction

This section records design context, not an implementation mandate.

- Prefer `httpx` or `requests` for APIs and permitted static pages.
- Use `feedparser` for RSS/Atom and incremental feed metadata.
- Consider `trafilatura` for main text and metadata; use BeautifulSoup or lxml
  only for justified site-specific extraction.
- Use Playwright or managed extraction only for high-value retrieval failures.
- Start with phrase dictionaries, regex, unit/currency parsing, named-tool
  dictionaries, negation handling, and sentence-window extraction.
- Consider spaCy for sentence boundaries and rule matchers,
  sentence-transformers for semantic similarity, RapidFuzz for fuzzy matching,
  and datasketch for near-duplicate detection.
- Model output may classify, cluster, tag, or summarize. It cannot replace raw
  excerpts or become market proof.
- Local storage may eventually use SQLite or DuckDB with CSV, JSONL, or Parquet
  exports, but no storage interface is chosen in this task.

## Evidence Model

### Workaround Mentions: Primary Record

One row should represent one human statement, review snippet, Q&A item, or
explicitly sampled search-result observation. Preserve at least:

- identity and provenance: `mention_id`, problem `cluster_id`, source type,
  platform/site, URL, canonical URL, title, published date, captured date,
  public author handle, source query, rank, access method, and
  `snippet_only_flag`;
- evidence text: exact excerpt, surrounding context, matched phrase family, and
  matched terms;
- qualification: raw problem text, workaround-present status, workaround type,
  named substitutes, manual-process flag, spreadsheet flag, self-built flag,
  script/macro flag, template flag, and help-request flag;
- explicit effort: time value/unit, cadence, volume value/unit, money
  value/currency, and named tool count;
- consequences: fragility, error, delay, and explicit risk terms;
- native context: native score and score type, replies, answers, and
  accepted-answer state where available;
- preservation: raw payload path, text snapshot path, content hash, extraction
  confidence, suspected false-positive/promotional flags, dedupe hash, and
  manual-review status.

Record source-specific fields as nullable. Do not fabricate unavailable values.

### Problem-Cluster Rollups: Derived Review Aid

A rollup may contain:

- normalized problem statement and optional JTBD summary;
- primary segment or industry only when supported;
- first and last seen dates;
- independent mentions, unique authors, platforms, and source types;
- repeated-question threads;
- named substitute, quantified-effort, self-built, and fragility counts;
- average toolchain breadth;
- top evidence identifiers;
- explicitly derived confidence, signal label, and manual notes.

All counts and summaries must remain reproducible from raw identifiers. Cluster
membership must be revisable.

### Artifact Records: Deferred

The ideal design proposed a separate artifact table for substitute objects. The
practical MVP defers it until repeated scripts, templates, spreadsheets, PDFs,
or workflows justify the added structure. Initially, retain artifact names and
URLs on mention records. If later added, preserve artifact type, name, platform,
URL, official/user-generated status, visible price, observation dates, mention
IDs, and only publicly visible usage metrics.

## Field Confidence

### Direct or Deterministic Fields

- URLs, titles, platform/source type, dates, public author handles, excerpts,
  and source-specific tags or categories.
- Native scores, replies, answers, and accepted-answer state where the source
  exposes them.
- Matched phrases, named substitutes, spreadsheet/manual/self-built/template
  flags, explicit cadence, time, money, volume, and clearly stated risk terms.
- First/last seen dates, unique authors, source counts, raw paths, and hashes
  computed from preserved records.

### Approximate Derived Fields

Keep these nullable and labeled as inference:

- normalized problem statement and JTBD summary;
- user segment and industry;
- workaround effort level;
- semantic repeated-question count;
- toolchain breadth when names are ambiguous;
- promotional or temporary-bug probability;
- problem-cluster assignment and confidence;
- sampled search-result substitute count.

### Cut or Simplified for MVP

- Real author role, country, team size, mission-critical status, compliance
  risk, revenue risk, and client impact: retain only when explicit.
- Manual step count: exclude because it is subjective.
- Monetary labor cost: never infer from salary assumptions.
- Willingness to pay: outside this cluster unless separately collected as paid
  behavior evidence.
- Cross-platform identity deduplication: do not attempt.
- Universal engagement score: keep native values separate.
- Template downloads, app-review coverage, or private-community prevalence: do
  not claim without direct permitted access.
- Complete search-result dominance: replace with a documented top-N sample.
- Screenshot for every row and full HTML for every result: preserve API JSON or
  clean text first; capture richer artifacts for promoted evidence when useful.

## Review Metrics

Prioritize inspectable components rather than a single opportunity score:

- independent mention count and unique author count;
- source-type diversity;
- count of explicit time, cadence, volume, or money;
- named substitute count and repeated substitute types;
- self-built/internal-artifact count;
- repeated-question count;
- named toolchain breadth;
- fragility/risk count;
- current-spend mentions;
- first seen, last seen, and recurrence span;
- source-native engagement context.

Counts are routing aids for manual inspection, not proof. Do not compare GitHub
stars, Stack Exchange scores, Hacker News points, Reddit votes, review ratings,
or template metrics as equivalent units.

## Effort Guidance

Effort level is a derived review label, not a fact. Suggested rubric:

- **Low:** One tool, no custom artifact, no quantified time, ad hoc or
  occasional use, little stated downstream risk.
- **Moderate:** Weekly or monthly routine, two or three tools, light formula,
  template, or automation use, some explicit time, or minor breakage.
- **High:** Daily or multi-user routine, three or more tools, a self-built
  script/macro/template, quantified hours or financial exposure, recurring
  breakage, or data errors.
- **Very high:** Explicitly business-critical workflow, substantial manual
  reconciliation, paid workaround stack or internal build, and strong stated
  risk to revenue, compliance, client delivery, or operations.

Do not infer unstated severity merely because an artifact appears technically
complex.

## Signal-Label Guidance

The supplied material proposes weak, medium, strong, and very strong workaround
signal labels. Treat them as provisional derived labels whose raw conditions
must remain visible:

- **Weak:** One credible mention with behavior, substitute, and friction, but no
  recurrence.
- **Medium:** Two independent authors, or one explicit quantified-effort or
  self-built example.
- **Strong:** At least three authors across at least two source types, plus at
  least two of: quantified effort, repeated substitute, self-built artifact,
  repeated question, or fragility.
- **Very strong:** Strong conditions plus multiple quantified high-effort
  examples or several independent self-built solutions.

Do not treat these labels, confidence, cluster size, or any proposed numeric
workaround-signal calculation as market proof or an opportunity decision. No
numeric scoring interface is approved by this context task.

## Evidence Preservation

For each promoted mention, preserve whenever practical:

- stable raw identifier and capture-run identifier;
- original and canonical URL;
- title, public author/handle, publication date, and capture date;
- exact excerpt and surrounding context;
- matched phrases and source query;
- raw API payload or permitted text snapshot;
- content hash and transformation metadata;
- linked artifact URLs and metadata;
- source-specific engagement fields and types;
- manual-review status and explicitly derived fields.

Screenshots or HTML snapshots are useful for promoted or fragile evidence but
are not universal MVP requirements. Respect source terms, retention rules,
robots/access restrictions, and deletion obligations.

## Failure Modes and Guardrails

### False Positives

- **Normal tool use:** Require compensating behavior plus friction/cost.
- **Temporary bugs:** Down-rank narrow version/outage fixes unless persistent.
- **Promotional idea-fishing:** Flag the post; use independent replies only when
  they contain qualifying behavior.
- **Search snippets:** Keep as discovery evidence until retrieval.
- **Artifact existence:** One template or script proves supply, not demand.
- **Engagement:** Popularity does not establish a market gap.

### False Negatives

- Users describe routines without naming them workarounds. Search verbs,
  cadence, artifacts, and consequences.
- Semantically similar jobs use different nouns. Support revisable semantic
  grouping and manual review.
- Important behavior occurs in private or restricted spaces. Report collection
  limits and say `no public evidence found`.
- Template or calculator requests may express unmet need indirectly. Retain them
  as adjacent signals until all qualification elements are present.

## Confirmed Project Facts

- User selected cluster ID `workaround`.
- This cluster covers workaround evidence across markets rather than one
  industry, audience, or product category.
- Workaround evidence requires a job/problem, concrete substitute behavior, and
  friction, insufficiency, risk, or cost.
- Planning inputs must not appear as collected market evidence.
- This task creates context and scaffolding only; it does not implement
  collection logic or choose a public Python interface.
- Raw mentions and derived problem-cluster rollups must remain separable and
  traceable.
- Source availability is intentionally non-universal; restricted sources are not
  required for a useful MVP.

## Assumptions

- `workaround` is both the user-selected ID and the correct durable scope,
  despite this cluster spanning many markets.
- Initial research will use public, permitted, low-cost sources and local
  storage.
- English phrase examples are starting guidance, not a permanent language
  restriction.
- Artifact records can remain embedded in mention records until collected data
  demonstrates a need for a separate table.

## Hypotheses

- Concrete workaround behavior will be a stronger manual-investigation lead
  than complaint volume alone.
- Repeated independent self-built artifacts may indicate a persistent mismatch
  better than one highly engaged discussion.
- Cross-source recurrence may reduce platform-specific audience bias.
- Quantified effort and recurring fragility may help distinguish meaningful
  compensating work from harmless preference.
- Search results dominated by substitute artifacts may reveal underserved jobs,
  but only documented top-N samples can test this.
- The recommended public source stack may capture enough measurable workaround
  behavior for an MVP without restricted social or review-platform access.

## Open Questions

- Which market, role, or problem seed should the first collection run target?
- Which search provider will be available and acceptable when implementation
  begins?
- What source terms, retention rules, and deletion workflows will apply at that
  time?
- What exact raw JSONL schema and shared runner contract will the repository
  adopt?
- How should semantic cluster boundaries be reviewed and corrected manually?
- What capture threshold should promote a record from `adjacent_signal` to a
  qualifying mention when one element is inferred rather than explicit?
- When will recurring artifact evidence justify a separate artifact table?
- Should non-English collection be included in the first implemented version?
- Which label thresholds, if any, remain useful after observing real data?

## Decisions and Superseded Guidance

- **2026-07-13 — Practical source scope supersedes universal ideal coverage.**
  Exa or Brave discovery, Stack Exchange, GitHub, Hacker News, RSS/Atom, and
  permitted static retrieval form the candidate MVP stack. Reddit, broad review
  ingestion, social networks, private communities, YouTube, and Common Crawl
  are optional, deferred, or excluded for access and maintenance reasons.
- **2026-07-13 — Separate artifact table deferred.** The ideal three-table model
  remains a future option; mention rows and problem rollups are enough for
  initial scaffolding, with artifact names and URLs stored on mentions.
- **2026-07-13 — Ideal fields narrowed.** Subjective, unavailable, restricted,
  or misleading fields are nullable, explicit-only, sampled, or excluded as
  described under Field Confidence.
- **2026-07-13 — No universal engagement or opportunity score.** Preserve
  source-native values and visible signal components. Any workaround strength
  label remains derived, auditable, and non-decisive.
- **2026-07-13 — Preservation made proportional.** Raw payloads, text, hashes,
  URLs, excerpts, and transformation metadata are core; screenshots and full
  HTML are reserved for promoted or otherwise fragile evidence when useful.

## Context Change Log

- **2026-07-13:** Created cluster context from the supplied ideal Workaround
  Evidence specification and practical API-availability assessment. No source
  material was retained in the cluster, and no market evidence was collected.
