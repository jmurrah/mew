# Documentation Index

Market Gap Finder is a private, local research pipeline for collecting auditable
evidence about possible software, app, and product opportunities. Human judgment
chooses what to investigate or build.

## Start Here

- [Mission and boundaries](core/mission-and-boundaries.md): project purpose,
  priorities, and prohibited scope.
- [Research model](core/research-model.md): eight evidence investigations and
  one cross-cutting provenance layer.
- [Evidence contract](core/evidence-contract.md): rules every collected fact,
  derived value, and claim must follow.
- [Glossary](core/glossary.md): canonical project terminology.
- [Shared open questions](core/open-questions.md): unresolved runner, storage,
  schema, review, policy, and initial-scope decisions.
- [Cluster index](../clusters/README.md): cluster ownership and specifications.
- [Source index](sources/index.md): provider mechanics, access constraints, and
  verification status.
- [Evidence and lineage schema](schemas/evidence-lineage.md): shared conceptual
  data contract; not an implemented Python schema.
- [Cluster record catalog](schemas/cluster-records.md): proposed logical records
  and field names retained from cluster planning.
- [Opportunity profile template](templates/opportunity-profile.md): single
  nine-part cross-cluster profile.
- [Decisions](decisions/): architectural choices whose rationale remains useful.
- [Classification and analysis references](references/classification-and-analysis.md):
  retained optional tooling references.

## Documentation Layers

1. `AGENTS.md` files contain concise operating instructions and navigation.
2. `docs/` contains shared durable knowledge, source references, conceptual
   schemas, decisions, and templates.
3. `clusters/<cluster_id>/CONTEXT.md` contains one cluster's canonical research
   specification.
4. Runtime evidence and generated investigation profiles will live outside
   canonical documentation after runner and storage contracts are chosen.

## Task Routing

| Task | Read |
|---|---|
| Change project behavior or architecture | Root `AGENTS.md`, mission, research model, evidence contract |
| Change one cluster | Root and cluster instructions, then that cluster's `CONTEXT.md` |
| Add or change a provider adapter | Source index, relevant provider reference, evidence contract |
| Define storage or lineage | Evidence contract, evidence-lineage schema, provenance cluster specification |
| Produce an investigation profile | Opportunity profile template plus supporting cluster outputs |
| Review an old architectural choice | Relevant decision record |

## Current Implementation Status

- Cluster Python modules are namespace scaffolds only.
- No shared runner, storage contract, public cluster interface, or collector is
  implemented.
- No market evidence has been collected.
- Provider facts in source references are planning notes requiring live
  verification before implementation or collection.
