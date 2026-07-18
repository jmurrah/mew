# Cluster Work Instructions

These rules apply to every directory under `clusters/`.

## Required Reading

Before editing a cluster:

1. Read the root `AGENTS.md`.
2. Read the cluster's `AGENTS.md`.
3. Read the cluster's `CONTEXT.md` completely.
4. Inspect existing `PROFILE.md` and relevant files under `evidence/`.

Do not infer one cluster's guidance from another cluster.

## Context Updates

- Process one cluster at a time. Do not mix context from other clusters.
- Use supplied PDFs and long-form text to structure or update `AGENTS.md`,
  `CONTEXT.md`, and `PROFILE.md` as appropriate.
- Preserve substantive detail, terminology, examples, edge cases, and caveats.
- Do not retain original planning inputs unless the user asks.
- Mark superseded guidance explicitly; do not silently erase history.
- Add a dated entry to the context change log for meaningful updates.
- Keep raw evidence out of `CONTEXT.md`; link to stable evidence identifiers
  instead.

## Code Boundary

- Keep cluster-specific collection, normalization, and profiling functions in
  `<cluster_id>.py`, where the filename matches the cluster directory exactly.
- Never keep the template name `cluster_name.py` in a real cluster.
- Keep orchestration and reusable infrastructure outside individual clusters.
- Make cluster failures isolated and diagnosable.
- Preserve provenance through every transformation.

## Profile Boundary

Maintain all nine headings in `PROFILE.md`, even when a section has no evidence.
Write `No evidence collected yet` instead of inventing or omitting findings.
Every factual profile item must cite one or more raw evidence identifiers.

## Validation

Before finishing cluster work:

- Confirm all derived claims reference raw evidence.
- Confirm facts, inference, and unknowns remain distinct.
- Confirm no prior durable context disappeared unintentionally.
- Run established project checks once those commands exist.
