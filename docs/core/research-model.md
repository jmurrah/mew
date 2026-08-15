# Research Model

## Investigation

An investigation starts with a defined problem, job, audience, workflow, query,
or candidate behavior. Eight evidence clusters inspect different dimensions.
The raw-evidence audit layer preserves provenance across all of them.

No cluster independently proves an opportunity. Agreement across clusters can
support human investigation but never becomes an automatic decision.

## Evidence Investigations

| Dimension | Cluster | Question |
|---|---|---|
| Problem | `problem_existence` | Is the same lived problem repeated across independent people, places, and time? |
| Workaround | `workaround` | Are people compensating through manual routines, substitutes, or stitched tools? |
| Dissatisfaction | `dissatisfaction` | What exact product object, workflow, or outcome fails for current users? |
| Paid behavior | `paid_behavior` | What public paid offers or observable buyer behavior exists near the job? |
| Competitor supply | `competitor_supply` | Does visible supply fit, satisfy, package, maintain, and reach the exact job? |
| Search discovery | `search_discovery` | How is the job expressed in search, and what does the captured result surface serve? |
| Distribution community | `distribution_community` | Where do likely users gather, search, compare, or become reachable? |
| Risk regulation | `risk_regulation` | What candidate trigger and authority evidence justify manual risk review? |

`raw_evidence_audit_trail` is cross-cutting provenance infrastructure, not a
ninth market signal. It owns conceptual guidance for stable IDs, immutable
acquisition records, hashes, lineage, source-policy versions, missingness,
retention, deletion, and change history.

## Required Distinctions

Keep these concepts separate throughout collection and analysis:

- observation and inference;
- raw evidence and derived records;
- discovery records and hydrated primary evidence;
- direct and adjacent evidence;
- visible paid offers and observed purchase behavior;
- source-native metrics and derived metrics;
- sample and population denominators;
- requested and inferred sensitive data;
- policy and enforcement;
- product, positioning, and distribution weakness;
- collected, unavailable, unsupported, failed, not applicable, and unknown.

## Evidence Lifecycle

1. Define investigation scope and exact inputs.
2. Record source policy and collection environment.
3. Acquire source-native records and immutable payloads where permitted.
4. Normalize without overwriting raw values.
5. Classify, cluster, or summarize with method and version recorded.
6. Link every derived value to supporting raw IDs and spans.
7. Produce cluster-specific outputs.
8. Assemble one cross-cluster opportunity profile for the investigation.
9. Preserve contradictions, missingness, coverage, and manual-review state.

Runner, storage, and cross-cluster output interfaces remain open architectural
questions. Current documentation defines responsibilities, not implementation.
