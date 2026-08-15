# Problem Existence Evidence

- **Cluster ID:** `problem_existence`
- **Python module:** `problem_existence.py`
- **Layer:** Market evidence

Shared rules: [Evidence Contract](../../docs/core/evidence-contract.md).
Field catalog: [Cluster Records](../../docs/schemas/cluster-records.md#problem-existence).

## Purpose

Determine whether a defined group, in a defined circumstance, repeatedly
encounters the same obstacle with behavioral consequences. Stop at evidence that
pain exists; do not infer market size, pricing, profitability, product choice,
or build quality.

Central question: are multiple independent people, across independent threads
or communities and a meaningful period, describing the same lived problem?

## Scope

- First-person current or past difficulty in a defined context.
- Repeated manual workarounds and assembled tool stacks.
- Active requests for alternatives, templates, automation, or fixes.
- Named incumbent methods and specific failure modes.
- Consequences involving time, money, errors, risk, delay, frustration, or
  urgency.
- Recurrence and concentration across authors, threads, communities, source
  families, and time.
- Collection quality, duplication, burst, and coverage observations needed to
  challenge apparent recurrence.

## Out of Scope

- Product recommendations, opportunity selection, and go/no-go decisions.
- Market size, pricing, profitability, or population prevalence.
- Cross-platform identity resolution or `global_unique_people`.
- Universal engagement normalization.
- Complete historical coverage or authenticity claims.
- Model training on collected Reddit content.

## Research Unit

A normalized problem statement has this shape:

```text
[actor or segment] struggles to [job] in [context] because [obstacle],
causing [cost or consequence]
```

A problem mention is one inspectable post, comment, question, review, or source
record. A problem cluster groups compatible mentions by actor, job,
circumstance, obstacle, and consequence. Keyword overlap alone cannot justify a
merge.

## Evidence Model

### Evidence Tiers

Provisional annotation tiers from strongest to weakest:

| Tier | Meaning | Tentative weight |
|---|---|---:|
| Behavioral proof | Actual task, failure, workaround, switch, or repeated hassle | 1.0 |
| Active search | Request for better method, alternative, template, or automation | 0.8 |
| Contextual complaint | Job and obstacle are inspectable | 0.6 |
| Generic dissatisfaction | Negative reaction with weak workflow context | 0.3 |
| Hypothetical wish | Future-facing feature or product wish | 0.1 |

Weights are calibration hypotheses. Preserve raw mention counts beside weighted
counts. Annotation never replaces excerpts and metadata.

Strong signals combine firsthand behavior, workarounds, active search, named
failure, explicit consequence, independent recurrence, and persistence. Votes,
views, sentiment, cluster size, and model confidence are supporting metadata
only.

## Observable Fields

- Evidence, thread, post/comment, parent, and source-native IDs.
- Source family, community, URL, title, tags, and native state.
- Created, updated, and captured times.
- Raw and clean excerpt; exact pain phrase.
- Public author identity under explicit source scope or permitted hash.
- Firsthand, historical, hypothetical, solution-seeking, workaround, and
  alternative-seeking language.
- Named current solution and stated failure mode.
- Explicit time, money, risk/error, delay, frustration, and urgency.
- Source-native votes, reactions, replies, views, answer state, and issue state.
- Query, collection method, pagination, rank, result cap, intended/actual window,
  retrieval status, errors, payload path, and content hash.

Unknown metrics remain null. Deleted authors receive record-specific missing
states, not one shared identity.

## Derived Fields

- Normalized problem statement and cluster membership.
- Evidence tier and quality-weighted count.
- Source-scoped unique authors; unique threads, communities, and source families.
- First/last seen, span, active weeks/months, recency, and 7/30-day burst ratios.
- Workaround, alternative-seeking, incumbent-failure, and explicit-consequence
  rates.
- Top-author, top-three-author, top-thread, and top-community concentration.
- Exact/near-duplicate groups and duplicate ratio.
- Coverage description, missing-metric flags, and manual relevance state.

All derived values retain supporting raw IDs, methods, denominators, and missing
inputs.

## Analysis

### Provisional Signal Labels

- **Weak:** at least 5 relevant mentions, 3 authors, 2 threads, and at least 10%
  workaround, alternative-seeking, or explicit-cost rate.
- **Medium:** at least 15 mentions, 10 authors, 5 threads, 2 communities, 2
  source families, 60 days, 2 active months, 25% workaround-or-alternative rate,
  top-three-author share at most 35%, and top-thread share at most 40%.
- **Strong:** at least 30 mentions, 20 authors, 10 threads, 3 communities, 2
  source families, 180 days, 4 active months, 35%
  workaround-or-alternative rate, 20% explicit-cost rate, top-three-author share
  at most 25%, top-thread share at most 30%, and one corroborating source.

These thresholds are unvalidated review aids. If implemented, expose every raw
condition, override flag, evidence ID, manual state, and separate coverage grade.

### False Positives

- Feature wishes mistaken for lived pain.
- Outages, launches, pricing changes, policy events, or media spikes mistaken for
  persistence.
- One prolific author, community, or large thread dominating recurrence.
- Fake, bought, coordinated, duplicated, quoted, or syndicated material.
- Search-ranking artifacts mistaken for prevalence.

### Expected False Negatives

- Nonconsumers blocked by cost, complexity, habit, anxiety, or switching costs.
- Pain visible only in private support, sales, internal workflows, or restricted
  communities.
- Quiet niches, deleted content, caps, migrations, and inaccessible sources.

Public evidence is a sample of expressed problems, not a representative survey.

## Source Applicability

Core candidates are GitHub, Stack Exchange, Hacker News, curated Discourse,
compatible WordPress/RSS, public static pages, manual URLs, and search discovery.
See [Community Sources](../../docs/sources/providers/communities.md) and
[Search Providers](../../docs/sources/providers/search.md).

GitHub is strongest for software problems; Stack Exchange for structured Q&A;
Hacker News for technical operators; Discourse and WordPress broaden niche
coverage. Search results discover and corroborate but require hydration before
counting a mention. Reddit remains conditional under
[Restricted Sources](../../docs/sources/providers/restricted.md).

## Guardrails

- Never infer cross-source identity, true prevalence, authenticity, or absence
  from missing public evidence.
- Compare engagement only inside compatible source and community contexts.
- Keep problem-signal strength and evidence coverage separate.
- Preserve three to seven canonical excerpts when possible across authors,
  communities, and time, including counter-evidence or concentration concerns.
- Label planning thresholds and provider notes as planning context, not evidence.

## Output Contract

Future cluster output should provide mention-level records, revisable problem
clusters, breadth/concentration/coverage measures, canonical evidence IDs, and
explicit uncertainty. It feeds section 1 of the investigation profile. No public
Python interface exists until the shared runner contract is chosen.

## Open Questions

- Which segment, job, circumstance, and seed problem begins first collection?
- How will ambiguous relevance and cluster merges receive manual review?
- How will coverage grades represent inaccessible sources without implying
  observed weakness?
- Which retention and deletion rules apply to stored excerpts and payloads?
- Which provisional signal thresholds survive calibration on real evidence?
