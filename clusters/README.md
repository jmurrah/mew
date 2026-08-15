# Cluster Index

Eight clusters investigate market evidence. One cluster provides cross-cutting
provenance infrastructure.

| Cluster | Responsibility |
|---|---|
| [`problem_existence`](problem_existence/CONTEXT.md) | Repeated lived problems and behavioral consequences |
| [`workaround`](workaround/CONTEXT.md) | Compensating behavior, substitutes, and friction |
| [`dissatisfaction`](dissatisfaction/CONTEXT.md) | Specific failures in current products |
| [`paid_behavior`](paid_behavior/CONTEXT.md) | Public paid offers and observable buyer behavior |
| [`competitor_supply`](competitor_supply/CONTEXT.md) | Query-conditioned exact-job supply and mismatch |
| [`search_discovery`](search_discovery/CONTEXT.md) | Query language, intent, SERP composition, and mismatch |
| [`distribution_community`](distribution_community/CONTEXT.md) | Public activity, audience specificity, and reachability |
| [`risk_regulation`](risk_regulation/CONTEXT.md) | Candidate triggers paired with authority evidence |
| [`raw_evidence_audit_trail`](raw_evidence_audit_trail/CONTEXT.md) | Stable IDs, payloads, lineage, policies, and change history |

Shared model: [Research Model](../docs/core/research-model.md).

## Layout

```text
clusters/<cluster_id>/
  AGENTS.md
  CONTEXT.md
  <cluster_id>.py
  evidence/
```

`CONTEXT.md` is canonical cluster specification. Runtime cluster output, if
needed, should contain only that cluster's evidence and feed one investigation-
level profile.

## Creating a Cluster

1. Copy `_template` to a lowercase `snake_case` directory.
2. Rename `cluster_name.py` to `<cluster_id>.py`.
3. Replace placeholders without copying shared project or provider guidance.
4. Add only cluster-specific operating rules to `AGENTS.md`.
5. Keep `evidence/` reserved until runtime ownership is defined.
