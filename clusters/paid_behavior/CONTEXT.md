# Paid Behavior Evidence

- **Cluster ID:** `paid_behavior`
- **Python module:** `paid_behavior.py`
- **Layer:** Market evidence

Shared rules: [Evidence Contract](../../docs/core/evidence-contract.md).
Field catalog: [Cluster Records](../../docs/schemas/cluster-records.md#paid-behavior).

## Purpose

Determine whether public evidence shows a money trail near the same job, pain,
workflow, or audience. Organize offer type, price, billing model, source-native
traction, market proximity, and payer complaints without claiming total demand,
profitability, or future willingness to pay.

## Scope

- Paid software, apps, extensions, plugins, templates, spreadsheets,
  calculators, downloads, communities, courses, and service-adjacent products.
- Exact and adjacent products serving the same job, workflow, or audience.
- Visible prices, currencies, billing cadence, free tiers, trials,
  subscriptions, one-time/lifetime offers, usage billing, IAP, discounts, and
  pay-what-you-want models.
- Ratings, reviews, installs, users, members, visible sales, and seller totals
  with native scope preserved.
- Explicit payer language concerning purchase, value, renewal, cancellation,
  refund, price, or subscription shape.
- Seller, product, source, and marketplace diversity.

## Out of Scope

- Revenue, MRR/ARR, paying users, conversion, churn, retention, refunds, CAC,
  or plan-level revenue unless a primary source explicitly discloses them.
- Estimates presented as observed facts.
- Complete marketplace coverage or historical prices before project snapshots.
- Proof that a reviewer paid without source or textual support.
- One willingness-to-pay or opportunity score.
- Automated initial coverage of Gumroad, Notion Marketplace, paid communities,
  G2, Capterra, or Etsy. Etsy is planned after core sources.

## Research Unit

One source observation is one listing, product page, pricing page, marketplace
observation, or linked review captured at a named source and time.

Two axes remain independent:

- `exact_vs_adjacent`: `exact`, `adjacent`, or `broad_category`.
- payment state: offer, monetization presence, traction proxy, explicit payer,
  source-verified buyer, paid complaint, or unknown.

A paid complaint can be direct or adjacent. Do not encode these axes as one
exclusive label.

## Evidence Model

Strength ordering for manual inspection:

1. Explicit payer language with price, cadence, renewal, purchase, or refund.
2. Source-verified buyer record or correctly scoped listing-level sales count.
3. Positive payer value language.
4. Visible paid price plus substantial source-native traction.
5. Visible paid price without transaction evidence.
6. IAP/subscription/premium flag without visible price or buyer evidence.
7. Cost complaint without purchase evidence.
8. Free popularity without monetization evidence.

Use `public paid-offer evidence` for visible pricing. `Observable paid behavior`
requires stronger transaction or payer support.

## Observable Fields

- Query and evidence IDs; source, marketplace, product, seller, and review IDs.
- Product/seller URLs, title, kind, audience/workflow tags, query, rank,
  storefront, capture time, and collection method.
- Exact raw price text, parsed amount, currency, billing period, discount, free
  plan/trial, subscription, one-time, lifetime, usage, IAP, and pay-what-you-want
  observations.
- Ratings and review counts kept separate; displayed installs/users/downloads;
  visible member count; listing-level or seller-level sales with explicit scope.
- Review text, date, rating, payer/value/payment-language spans, and source
  verification state.
- Raw artifact path, content hash, parser version, collection status, errors,
  coverage, and manual notes.

Always retain raw and parsed prices, for example:

```text
price_display_raw = "$15 / month"
price_amount = 15.00
billing_period = "monthly"
```

Suggested billing values remain:

```text
one_time
weekly
monthly
yearly
annual_commitment
usage_based
free
freemium
free_to_install
pay_what_you_want
unknown
```

## Derived Fields

- Exact and adjacent paid counts.
- Unique paid sellers and source diversity.
- Query-relative price distributions.
- Subscription, one-time, usage, lifetime, free-trial, template, and community
  counts.
- Explicit-payer, price-resistance, subscription-model, renewal, refund, and
  positive-value classifications.
- Seller and cross-platform product deduplication with method/confidence.
- Coverage, parser-failure, missingness, and duplicate indicators.

Never normalize unlike traction metrics into one score.

## Analysis

### Interpretation Rules

- Listed price means an offer exists.
- IAP means monetization exists.
- Rating/review means use or engagement; payment remains unknown.
- Install/user count is distribution, not active or paid users.
- Verified-buyer or explicit payer language is stronger transaction evidence.
- Shop total sales are seller-level, not listing-level.
- “Useful but not worth a subscription” may indicate value plus price-model
  mismatch, not no demand.
- Many free offers do not establish a free-only market.

### Provisional Labels

- **Strong paid behavior:** At least three paid sellers, two source types, plus
  public traction or strong review support.
- **Medium:** At least two sellers with visible pricing but weaker traction or
  one dominant source.
- **Weak:** One or two paid offers with little social proof or vague price
  mentions.
- **Free-only candidate:** No meaningful paid rows across at least three source
  types plus five free/freemium rows.
- **Adjacent paid candidate:** Several adjacent paid rows but few exact rows.
- **Subscription-resistant candidate:** Recurring pricing plus explicit model
  complaints and stronger one-time/lifetime reactions.

These are unvalidated workflow aids. Expose inputs, coverage, and exceptions.

### Failure Modes

- Free app with IAP mistaken for paying users.
- Displayed users mistaken for active subscribers.
- Seller totals attributed to one listing.
- Ratings assumed to be paid reviews.
- Listing abundance treated as demand.
- Vendor testimonials treated like independent reviews.
- Hidden web, enterprise, community, or adjacent-format payments missed.

## Source Applicability

Current core planning uses Apple, Google Play, Shopify App Store, Chrome Web
Store, and public vendor pricing pages. Etsy follows. See
[Marketplace Providers](../../docs/sources/providers/marketplaces.md),
[Search Providers](../../docs/sources/providers/search.md), and
[Restricted Sources](../../docs/sources/providers/restricted.md).

Shopify offers strong explicit business-software pricing and review context.
Google Play offers broad discovery, traction, monetization flags, and review
text but uses a brittle unofficial competitor adapter. Apple provides reliable
catalog/upfront-price evidence but weak subscription detail. Chrome provides
distribution plus vendor-site discovery.

## Guardrails

- Keep product, seller, listing, storefront, and external-page scope explicit.
- Preserve exact raw price strings and source-native metrics.
- Keep unavailable private metrics `unknown`, never zero.
- Use `may` for price-resistance and model-mismatch interpretations.
- Treat public pages as changeable; preserve capture time and local proof where
  policy allows.

## Output Contract

Future output should provide inspectable product/listing/pricing observations,
linked review records, exact/adjacent and payment-state axes, query-level
aggregates, coverage, and raw IDs. It feeds section 4 of the investigation
profile. No collector or public interface exists yet.

## Open Questions

- Which job, audience, or market query seeds first collection?
- Should reviews be independent records or linked product artifacts?
- Which seller and cross-platform deduplication rules remain reversible?
- Which locales and storefronts belong in initial scope?
- When should Etsy or another deferred source enter active collection?
