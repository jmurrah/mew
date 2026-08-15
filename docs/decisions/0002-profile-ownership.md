# Decision 0002: Investigation Profile Ownership

- **Status:** Accepted
- **Date:** 2026-08-15

## Context

Every cluster contained a `PROFILE.md` with the same nine headings. Those nine
dimensions describe one market investigation, not nine independent cluster
profiles. Empty copies implied incorrect ownership and created boilerplate.

## Decision

Maintain one canonical nine-part template at
`docs/templates/opportunity-profile.md`. A future runner will instantiate it per
investigation. Cluster outputs, if created, contain only that cluster's evidence
and feed the investigation profile.

## Consequences

- Cluster-local `PROFILE.md` placeholders are removed.
- Profile runtime location remains undecided until runner and storage contracts
  exist.
- Raw links and provenance become the ninth investigation section, backed by
  the cross-cutting audit layer.
