# Dissatisfaction and Complaint Evidence: Cluster Instructions

- Read `CONTEXT.md` completely before changing this cluster.
- Treat the supplied ideal specification and API-feasibility notes as planning
  context. They are not collected market evidence and must never appear as such
  in `PROFILE.md`.
- Answer one narrow question: are users unhappy with existing products, and
  exactly what outcome, workflow, feature, or object is failing?
- Preserve complaint-bearing source records before classifying, clustering, or
  summarizing them. Every derived item must point to stable raw record IDs.
- Require both a complaint theme and an inspectable problem object before
  treating generic negativity as useful complaint evidence.
- Keep ratings, written text, source mechanics, time windows, versions, and
  collection coverage separate. Never flatten unlike sources into one score.
- Use population metrics only when collection coverage supports a known
  denominator. Prefix incomplete metrics with `sample_` or otherwise name their
  coverage explicitly.
- Preserve high-star complaints. Repeated “love this, but need X” reviews can
  reveal missing-feature pain before average ratings fall.
- Distinguish observed behavior from inference: stated switching, cancellation,
  uninstall, or willingness to pay is evidence of a statement, not verified
  churn, conversion, or payment.
- Treat specificity, harm, theme, solvability, sentiment, anomaly, and signal
  labels as derived review aids—not market proof.
- Never infer fake reviews, causal update effects, complete support quality,
  resolution, customer prevalence, or complete historical coverage from public
  records.
- Preserve source-native counts and platform mechanics. Do not compare GitHub
  issues, store reviews, ratings, users, reactions, and support threads as if
  they share a denominator.
- Keep collection-run coverage metadata with every source snapshot, including
  access type, requested and returned counts, pagination state, date range,
  country, language, sort, errors, and raw snapshot identity.
- Preserve representative confirming records plus nearby contradictions for
  strong or mixed claims.
- Recheck official documentation, terms, pricing, quotas, retention duties, and
  endpoint behavior immediately before implementing or running any collector.
  API details in `CONTEXT.md` are a user-supplied planning snapshot dated
  2026-08-15.
- Do not automate Capterra ingestion. Keep G2, GetApp, Software Advice, Chrome
  Web Store reviews, social platforms, private communities, and other deferred
  sources out of MVP collection unless later guidance explicitly changes scope.
- Reddit requires approved API access, current terms review, deletion
  reconciliation, raw-text removal when deleted upstream, and recomputation of
  affected derived data. It must not block MVP work.
- Keep future cluster-specific collection, normalization, tagging, and profiling
  logic in `dissatisfaction.py`. Do not invent its public interface before the
  top-level runner contract exists.
- Maintain all nine `PROFILE.md` sections. This cluster primarily supports
  section 3, but evidence may support other sections only when raw records do.

