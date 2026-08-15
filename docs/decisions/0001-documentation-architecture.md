# Decision 0001: Documentation Architecture

- **Status:** Accepted
- **Date:** 2026-08-15

## Context

Project knowledge was distributed across long root and cluster instructions,
nine repeated profile placeholders, repeated evidence README files, and cluster
specifications containing duplicated provider mechanics and shared research
rules. Future agents had to load many files before locating authoritative
guidance.

## Decision

Use progressive disclosure:

1. Concise `AGENTS.md` files provide scoped instructions and navigation.
2. `docs/` owns shared durable concepts, conceptual schemas, providers,
   decisions, and templates.
3. Each real cluster owns one canonical `CONTEXT.md` containing only
   cluster-specific research knowledge.
4. Runtime evidence and generated profiles remain outside planning docs.

## Consequences

- Shared concepts have one canonical owner.
- Provider facts can be reverified without editing every cluster.
- Cluster work requires fewer documents.
- Git history handles ordinary wording evolution; decision records preserve
  only durable architectural rationale.
- Future edits must link to canonical material instead of copying it.
