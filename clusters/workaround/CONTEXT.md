# Workaround Evidence

- **Cluster ID:** `workaround`
- **Python module:** `workaround.py`
- **Layer:** Market evidence

Shared rules: [Evidence Contract](../../docs/core/evidence-contract.md).
Field catalog: [Cluster Records](../../docs/schemas/cluster-records.md#workaround).

## Purpose

Find public, inspectable evidence that people or teams compensate for an
underserved job through substitutes, patches, manual routines, or stitched
tools. Observable compensating behavior is the target, not preference or
negative sentiment alone.

## Scope

- Manual entry, copy/paste, exports, reconciliation, renaming, data movement,
  and repeated coordination.
- Stitched workflows using spreadsheets, Notion, notes, PDFs, checklists,
  calculators, Zapier, n8n, scripts, formulas, macros, or several apps.
- Self-built scripts, browser extensions, templates, internal tools, and small
  dashboards.
- Repeated template, tracker, workaround, recommendation, and automation asks.
- Explicit cadence, volume, time, money, maintenance, breakage, errors, delay,
  duplicate work, or operational risk.
- Public substitute artifacts and bounded search-result observations.

## Out of Scope

- Complaints, wishes, sentiment, or feature requests without substitute behavior.
- Ordinary use of a general-purpose tool without compensating work or friction.
- Temporary version-specific fixes unless recurrence reveals a durable job.
- Promotional founder idea-fishing without independent qualifying behavior.
- Private communities or internal company material without authorized input.
- Market size, willingness-to-pay, opportunity scores, product recommendations,
  or universal web coverage.

## Research Unit

A workaround mention qualifies only when source material supports all three:

1. A stated or reasonably inferable job/problem.
2. A concrete substitute behavior.
3. Friction, insufficiency, risk, or cost.

Support for the third element may include manual labor, recurring cadence,
quantified effort, a self-built extension, repeated help-seeking, fragility,
errors, delay, duplicate work, compliance, revenue, client, or operational risk.
Ambiguous records become `adjacent_signal`; they are neither promoted nor
silently discarded.

## Evidence Model

Keep raw mentions separate from problem-cluster rollups. Raw statements are
evidence; normalized jobs, cluster membership, effort labels, confidence,
counts, and summaries are derived.

Important distinctions:

- Flexible-tool use is not automatically a workaround.
- Behavior is stronger than opinion but not market proof.
- Signal breadth and effort burden are separate dimensions.
- Search snippets are discovery evidence until source hydration.
- Artifact existence proves supply, not demand.

Classification examples are illustrative only:

- Qualifying: recurring manual transfer between two apps because neither exports
  needed report.
- Qualifying: internal script that repeatedly breaks when upstream API changes.
- Adjacent: “I use Google Sheets for inventory” without mismatch or friction.
- Adjacent: one workaround for a narrow fixed software version.

## Observable Fields

- Mention, source-native, thread, query, and artifact IDs.
- Platform/site, source type, URL, canonical URL, title, author, dates, query,
  rank, access method, and snippet-only state.
- Exact excerpt, surrounding context, matched phrase family, and matched terms.
- Raw job text, concrete substitute, named tools, manual/spreadsheet/script/
  macro/template/self-built/help-request indicators.
- Explicit time, cadence, volume, money, tool count, fragility, error, delay, and
  risk terms.
- Native scores, replies, answers, and accepted-answer state when exposed.
- Payload/text snapshot references, hashes, collection status, parser version,
  dedupe hash, and manual-review state.

## Derived Fields

- Normalized problem statement and optional job-to-be-done summary.
- Segment or industry only when supported.
- Problem-cluster assignment, confidence, and manual overrides.
- Independent mentions, source-scoped authors, platforms, source types, and
  recurrence span.
- Named-substitute, quantified-effort, self-built, fragility, and repeated-
  question counts.
- Toolchain breadth and provisional effort level.
- Promotional/temporary-bug flags and sampled search-result substitute counts.

Do not infer real role, country, team size, labor cost, willingness to pay,
cross-platform identity, or universal engagement.

## Analysis

### Effort Labels

- **Low:** One tool, no custom artifact or quantified time, occasional use,
  little downstream risk.
- **Moderate:** Weekly/monthly routine, two or three tools, light automation,
  some explicit time, or minor breakage.
- **High:** Daily/multi-user routine, three or more tools, self-built artifact,
  quantified hours/financial exposure, recurring breakage, or data errors.
- **Very high:** Explicitly business-critical reconciliation or internal build
  with stated revenue, compliance, client, or operational risk.

### Provisional Signal Labels

- **Weak:** One credible qualifying mention without recurrence.
- **Medium:** Two independent authors, or one quantified-effort/self-built case.
- **Strong:** At least three authors across two source types plus two of:
  quantified effort, repeated substitute, self-built artifact, repeated question,
  or fragility.
- **Very strong:** Strong conditions plus several high-effort or independent
  self-built examples.

Labels are unvalidated review aids, not market proof.

### Failure Modes

- Normal tool use mistaken for compensating behavior.
- Temporary bugs mistaken for durable jobs.
- Promotional posts mistaken for user evidence.
- Search snippets or artifact listings treated as proof.
- Private or differently worded workarounds missed by public keyword search.

Use `no public evidence found under recorded coverage`, never `no workaround
exists`.

## Source Applicability

Core candidates are public search discovery, Stack Exchange, GitHub, Hacker
News, RSS/Atom, and permitted static pages. See
[Search Providers](../../docs/sources/providers/search.md) and
[Community Sources](../../docs/sources/providers/communities.md).

GitHub is valuable for scripts, macros, repositories, issues, and self-built
artifacts. Stack Exchange supports repeated questions and accepted workarounds.
Hacker News favors technical operators. Template marketplaces may expose visible
artifacts but not downloads, demand, or active use. Reddit remains conditional.

## Guardrails

- Require concrete compensating behavior plus friction/cost.
- Label every inferred qualification element and preserve exact supporting span.
- Keep native engagement values and types separate.
- Keep original source records distinct from normalized clusters.
- Preserve source terms, policy, access limits, and provider status.

## Output Contract

Future output should contain mention-level records, revisable problem-cluster
rollups, explicit effort and signal components, artifact links, coverage, and
raw evidence IDs. A separate artifact table is deferred until recurring data
justifies it. Output feeds section 2 of the investigation profile.

## Open Questions

- Which market, role, or problem seeds first collection?
- When does one inferred qualification element permit promotion from
  `adjacent_signal`?
- When do repeated artifacts justify a separate artifact entity?
- How will semantic groupings be manually reviewed and corrected?
- Should initial collection include languages beyond English?
