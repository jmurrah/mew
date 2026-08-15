# Paid Behavior Evidence: Cluster Instructions

- Read `CONTEXT.md` completely before changing this cluster.
- Ask only whether an observable money trail exists near the researched job,
  pain, or audience. Do not infer that an opportunity is good or should be
  built.
- Call visible pricing `public paid-offer evidence`, not proven willingness to
  pay. Ratings, reviews, installs, users, IAP flags, and seller-level sales are
  traction or monetization proxies, not paid-customer counts.
- Keep direct, adjacent, and paid-complaint evidence distinct. Also preserve
  `exact_vs_adjacent`; payment language and market proximity are separate
  dimensions.
- Preserve source-native scope. Listing-level metrics, seller-level metrics,
  storefront-specific ratings, displayed installs, and external-site pricing
  must never be silently combined or relabeled.
- Use `unknown`, never zero, for unavailable private metrics such as revenue,
  paying users, conversion, churn, and listing-level sales.
- Treat supplied specifications and API notes as planning context, not collected
  market evidence. They must not appear as findings in `PROFILE.md`.
- Current MVP source plan: Apple App Store, Google Play, Shopify App Store,
  Chrome Web Store, and public SaaS pricing pages. Etsy is next-phase.
  Gumroad, Notion Marketplace, paid communities, G2, Capterra, and revenue or
  sales estimates are deferred from initial collection.
- Recheck provider terms, access, pricing, quotas, returned fields, and parser
  behavior immediately before implementation or collection. July 2026 access
  notes are dated planning assumptions.
- Keep one inspectable source observation per evidence row. Preserve exact raw
  price text, source URL, query, rank, storefront, capture time, raw artifact
  path, content hash, parser version, and collection status where available.
- Keep query aggregates derived and auditable. Never use listing count alone as
  paid demand proof; expose seller diversity, source diversity, pricing,
  traction proxies, complaints, coverage, and missingness separately.
- Keep NLP limited to classification and retrieval. Every payer, pricing-model,
  value, or complaint label must retain its supporting review excerpt and raw
  evidence ID.
- Keep future cluster-specific logic in `paid_behavior.py`. Do not invent its
  public interface before shared runner contracts exist.
- Maintain all nine `PROFILE.md` sections. Every factual profile item must cite
  raw evidence IDs; empty sections remain `No evidence collected yet`.

