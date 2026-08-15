# Source and Provider Index

Provider mechanics are volatile planning knowledge, not market evidence. Verify
official documentation, pricing, quotas, terms, retention duties, and endpoint
behavior immediately before implementation or collection.

## Canonical References

- [Search providers](providers/search.md): Brave, DataForSEO, SerpAPI, Tavily,
  Exa, Google Ads, Google Trends, and retired/deferred search interfaces.
- [Community and publishing sources](providers/communities.md): GitHub, Stack
  Exchange, Hacker News, Discourse, RSS/Atom, WordPress, YouTube, and public
  pages.
- [Marketplaces and product catalogs](providers/marketplaces.md): Apple, Google
  Play, Shopify, Chrome, Mozilla, Etsy, and WordPress.org.
- [Restricted and deferred sources](providers/restricted.md): Reddit, review
  platforms, social networks, Product Hunt, private communities, and other
  non-core sources.
- [Authority sources](providers/authorities.md): regulator and platform-policy
  sources used by risk research.

## Source Selection Rules

1. Prefer official APIs, public structured interfaces, RSS/Atom, and permitted
   static pages.
2. Use search providers for discovery and recorded SERP evidence; hydrate an
   original source before making a context-dependent primary claim.
3. Preserve complete provider responses before normalization when permitted.
4. Keep provider, underlying source, engine, locale, and access method separate.
5. Treat unsupported parsers as isolated, replaceable, versioned adapters.
6. Record unavailable, unsupported, denied, failed, and uncollected separately.
7. Do not replace inaccessible official access with aggressive unauthenticated
   scraping.

## Verification Status

Existing facts came from user-supplied planning assessments dated 2026-07-13 or
2026-08-15. They were not independently verified during documentation work.
Each provider section records this explicitly. No price, quota, package health,
or access statement should become a durable code default without revalidation.
