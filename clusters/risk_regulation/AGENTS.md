# Risk and Regulation Evidence: Cluster Instructions

- Read `CONTEXT.md` completely before changing this cluster.
- Treat supplied specifications and API assessments as planning context, not
  collected market evidence. Never cite them in `PROFILE.md` as proof that a
  candidate has a risk, that a rule applies, or that an opportunity is weak.
- Operate as an evidence layer, not a legal adviser, compliance checker,
  gatekeeper, or go/no-go engine. Surface reasons for manual investigation;
  never decide whether a product is legal, compliant, safe, or worth building.
- Use one risk claim as the primary unit. Link each claim to both the candidate-
  side trigger and the external authority or platform evidence supporting the
  concern.
- Prefer tangible, narrowly applicable triggers over generic warnings. Record
  behavior, data type, user population, platform, integration method, or
  operational obligation that caused each tag.
- Keep domain mention separate from performed function. Education about health,
  law, finance, or tax is not equivalent to diagnosis, legal discretion,
  personalized investment advice, filing, or official submission.
- Keep requested sensitive data separate from data inferred by product behavior.
  Preserve the text and rule that support each inference.
- Keep inherent risk separate from risk introduced by an optional feature.
  Preserve lower-risk product boundaries when evidence supports them.
- Keep policy, enforcement history, legal analysis, technical access posture,
  and community commentary separate. Never let a weak source overwrite a more
  authoritative one.
- Use this source order for review priority, not truth by fiat: official
  regulator; official platform policy; official marketplace guide; statute,
  court, or case record; qualified legal analysis; operator material; community
  discussion. Record source type, jurisdiction, date, and uncertainty.
- Preserve evidence direction: `prohibits`, `permits_with_conditions`,
  `requires_disclosure`, `requires_approval`, `requires_support`,
  `highlights_enforcement`, or `unclear`. High risk is not synonymous with a ban.
- Reserve hard-stop flags for explicit high-authority evidence of a ban,
  required authorization, required legal entity, or core conflict. Even then,
  route to manual review; never auto-drop the opportunity.
- Keep regulatory sensitivity, consequence of error, privacy sensitivity,
  platform dependency, and support burden separate. An optional overall signal
  must expose its components and cannot become an opportunity score.
- Use deterministic detection before semantic or LLM classification. Store rule
  version, matched text, derived tag, confidence, missing inputs, and supporting
  raw IDs. Model output is a classifier, never evidence.
- Prefer local tagging plus a curated authoritative source registry. Trigger
  live retrieval selectively; do not semantically search the entire CFR or the
  open web for every candidate.
- Reverify all provider access, endpoint, quota, price, policy, and legal-status
  claims before implementation or collection. Current API notes are a
  user-supplied planning snapshot dated 2026-08-15.
- Preserve complete retrieved policy or authority text where permitted, plus
  canonical URL, title, publisher, jurisdiction/platform, publication or update
  date, retrieval time, relevant excerpt, content hash, and prior-version link
  when available.
- Treat policy change as evidence. Never overwrite a prior captured policy
  version when retaining both improves auditability.
- Keep missing, unknown, not applicable, inaccessible, and not collected
  distinct. Missing evidence never means low risk.
- Reuse competitor reviews, complaints, or issue records only through stable
  cross-cluster evidence IDs and shared orchestration. Do not duplicate
  acquisition or depend on another cluster's private context or artifacts.
- Keep future cluster-specific collection, normalization, classification, and
  profiling logic in `risk_regulation.py`. Do not invent its public interface
  before the shared runner contract exists.
- Maintain all nine `PROFILE.md` sections. Every future factual profile item
  must cite stable raw evidence identifiers; absent evidence stays explicit.
