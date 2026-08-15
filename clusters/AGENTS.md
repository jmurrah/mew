# Cluster Instructions

These rules specialize root [AGENTS.md](../AGENTS.md) for `clusters/`.

## Before Editing

1. Read target cluster's `AGENTS.md`.
2. Read target cluster's `CONTEXT.md` completely.
3. Read linked shared contracts and provider references.
4. Inspect target Python module and runtime evidence directory.

## Rules

- Process one cluster at a time. Do not infer its rules from another cluster.
- Keep `AGENTS.md` concise; durable domain knowledge belongs in `CONTEXT.md`.
- Keep shared concepts and provider mechanics in `docs/`; link instead of copy.
- Treat user-provided durable cluster guidance as canonical until explicitly
  superseded. Planning inputs are not market evidence.
- Preserve cluster-specific distinctions, fields, examples, heuristics, caveats,
  and open questions.
- Keep collection, normalization, and analysis in `<cluster_id>.py` once shared
  interfaces exist.
- Preserve raw-to-derived lineage through every transformation.
- Preserve proposed record terminology through the
  [Cluster Record Catalog](../docs/schemas/cluster-records.md).
- Do not create cluster-local nine-part profiles. Investigation profile ownership
  is defined in [Decision 0002](../docs/decisions/0002-profile-ownership.md).
- Runtime evidence directories remain empty until collection is authorized.
- Use Git history for ordinary document evolution and decision records for major
  architectural rationale; do not keep stale guidance beside current rules.

## Validation

- Confirm target `CONTEXT.md` follows standard conceptual headings.
- Confirm shared guidance was not duplicated locally.
- Confirm no planning material was presented as collected evidence.
- Confirm unique prior context was preserved or explicitly superseded.
