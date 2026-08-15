# Market Gap Finder Instructions

## Read First

Start with [docs/index.md](docs/index.md). Before changing one cluster, also read
[clusters/AGENTS.md](clusters/AGENTS.md), that cluster's `AGENTS.md`, and its
complete `CONTEXT.md`.

## Non-Negotiable Rules

- Keep project private, local, evidence-first, and human-directed.
- Preserve traceability to inspectable raw evidence above convenience or
  automation.
- Keep observed facts separate from labels, summaries, hypotheses, and model
  output.
- Never present classification, sentiment, confidence, cluster size, or search
  rank as market proof.
- Keep missingness, source limits, contradictions, and uncertainty explicit.
- Do not choose opportunities, generate automatic app ideas, create a go/no-go
  engine, or produce one opportunity score unless user explicitly changes scope.
- Preserve unrelated user changes. Never silently discard unique context.

Canonical philosophy and boundaries:
[docs/core/mission-and-boundaries.md](docs/core/mission-and-boundaries.md).
Canonical evidence rules:
[docs/core/evidence-contract.md](docs/core/evidence-contract.md).

## Repository Boundaries

- Shared durable knowledge belongs under `docs/`.
- Cluster-specific research knowledge belongs in
  `clusters/<cluster_id>/CONTEXT.md`.
- Cluster-specific Python logic belongs in matching `<cluster_id>.py`.
- Shared orchestration and storage must remain outside cluster modules.
- Provider mechanics belong under `docs/sources/`, not repeated in clusters.
- Distill supplied PDFs and long-form planning inputs into canonical docs; retain
  original inputs only when user asks or durable reference ownership requires it.
- Runtime evidence and generated profiles must not be stored as planning docs.
- Prefer local Markdown, JSONL, and CSV outputs that remain manually inspectable.

No runner, storage contract, dependency set, or standard test command exists
yet. Do not invent one during unrelated work.

## Completion Checks

- Derived claims retain raw evidence IDs and applicable supporting spans.
- Facts, inference, and unknowns remain distinct.
- Source policy and coverage are explicit.
- Relevant links and established checks pass.
- Unresolved architecture remains documented instead of guessed.
