# Market Gap Finder: Agent Instructions

## Mission

Build a private, local research pipeline that finds evidence of small software,
app, and product opportunities. Help the user investigate unmet demand; never
choose opportunities for them.

For any topic, answer:

> Where is there evidence that people repeatedly experience a specific problem,
> current solutions are weak or mismatched, and money may already be spent
> nearby?

Long-term success means a repeatable process for finding and reviewing many
small, informed product bets. Individual bets may fail.

## Decision Priorities

When goals conflict, use this order:

1. Traceability to raw evidence
2. Quality and relevance of evidence
3. Manual inspectability
4. Simple local operation
5. Automation and model-generated analysis

## Product Boundary

- Collect and organize evidence. Leave conclusions and build decisions to the
  user.
- Use NLP only to classify, cluster, tag, or summarize. Never treat model output,
  sentiment, confidence, or cluster size as market proof.
- Separate observed facts from inferred labels and summaries.
- Surface uncertainty and missing evidence instead of hiding or guessing.

Do not build any of these unless the user explicitly changes scope:

- Public SaaS
- Dashboard-first UI
- Automatic app-idea generator
- Go/no-go decision engine
- Build-plan or validation-plan generator
- Single opportunity score

## MVP Scope

Every cluster profile must contain these sections. Prioritize implementation and
evidence depth in this order:

1. Repeated problems or questions
2. Manual workarounds
3. Complaints about current solutions
4. Nearby paid behavior
5. Weak or mismatched competitors
6. Search and discovery evidence
7. Distribution and community evidence
8. Risk and regulation evidence
9. Raw links and excerpts

## Cluster Layout

Use one self-contained directory per cluster:

```text
clusters/<cluster_id>/
  AGENTS.md
  CONTEXT.md
  <cluster_id>.py
  PROFILE.md
  evidence/
```

- Use lowercase `snake_case` for `<cluster_id>`.
- Copy `clusters/_template/` when creating a cluster; never use `_template` as
  real research input.
- Name the cluster's Python module `<cluster_id>.py`; never leave it named
  `cluster.py` or `cluster_name.py`.
- Put cluster-specific Python collection and transformation functions in that
  module.
- Keep shared orchestration in the eventual top-level runner, not duplicated in
  cluster modules.
- Store detailed, durable domain guidance in `CONTEXT.md`, not in Python comments
  or generated output.
- Keep the nine-part human-readable evidence profile in `PROFILE.md`.
- Store raw and derived evidence artifacts under `evidence/`.

Before changing a cluster, read `clusters/AGENTS.md`, then that cluster's
`AGENTS.md` and `CONTEXT.md`. These files may contain constraints more specific
than this root file.

## Context Preservation

- Treat user-provided cluster context as canonical project knowledge.
- Use supplied PDFs and long-form text to model the cluster Markdown files. Do
  not retain those inputs unless the user asks.
- Preserve substantive facts, distinctions, caveats, terminology, and examples;
  exact wording is unnecessary unless wording itself matters.
- Never silently replace or delete earlier guidance. When new guidance conflicts,
  record what it supersedes and why in the context change log.
- Keep hypotheses, confirmed facts, exclusions, and open questions visibly
  separate.
- Update cluster context whenever the user supplies durable corrections or new
  research direction for that cluster.

## Evidence Contract

- Preserve raw collected data whenever practical.
- Give raw records stable identifiers.
- Link every cluster, label, summary, and conclusion to supporting raw record
  identifiers.
- Retain source URLs, excerpts, collection dates, publication dates when
  available, counts, product names, prices, ratings, and review details.
- Record transformations well enough to reproduce or audit derived output.
- Never present an unsupported derived claim as collected fact.

Useful evidence includes repeated questions, public complaints, manual
workarounds, competitor gaps, adjacent paid products, search results, community
discussions, reviews, ratings, prices, links, excerpts, counts, and dates.

## Output Contract

- Run locally.
- Prefer CSV, JSONL, and Markdown.
- Keep output spreadsheet-friendly and manually reviewable.
- Preserve intermediate artifacts when they improve provenance or
  reproducibility.
- Prefer schemas that can evolve without breaking raw-evidence references.

## Working Rules

- Choose the smallest file-based design that meets the request and preserves
  provenance.
- Keep evidence collection separate from later product-selection or build work.
- Avoid UI, hosted infrastructure, and new abstractions until required by the
  active task.
- Keep cluster modules independent. They may share stable utilities but must not
  depend on another cluster's private context or generated artifacts.
- Keep changes within requested scope. Preserve unrelated user changes.
- Add specific repository layout, setup, build, test, lint, and formatting
  commands here once the implementation establishes them; do not invent them.

## Done When

- The requested behavior or artifact exists.
- Derived findings remain traceable to raw evidence.
- Facts, inference, and uncertainty are visibly distinct.
- Outputs remain local, inspectable, and spreadsheet-friendly where applicable.
- Relevant available checks pass; report checks that could not run.
