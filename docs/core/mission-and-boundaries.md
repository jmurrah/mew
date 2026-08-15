# Mission and Boundaries

## Mission

Build a private, local research pipeline that helps a human find evidence of
small software, app, and product opportunities.

For a defined investigation, ask:

> Where is evidence that people repeatedly experience a specific problem,
> current solutions are weak or mismatched, and money may already be spent
> nearby?

Success means a repeatable way to review many small, informed product bets. It
does not require every bet to succeed.

## Decision Priorities

When goals conflict, use this order:

1. Traceability to raw evidence.
2. Evidence quality and relevance.
3. Manual inspectability.
4. Simple local operation.
5. Automation and model-generated analysis.

## Product Boundary

The project collects, organizes, classifies, clusters, and summarizes evidence.
It assists investigation; it does not decide what should be built.

Human judgment remains responsible for:

- selecting opportunities;
- interpreting conflicting or incomplete evidence;
- deciding whether more research is needed;
- making validation, product, legal, and build decisions.

Model output may classify, tag, group, or summarize records. Sentiment, model
confidence, cluster size, and generated prose are not market proof.

## Out of Scope Without Explicit Authorization

- Public SaaS.
- Dashboard-first UI.
- Automatic app-idea generation.
- Opportunity ranking or one opaque score.
- Go/no-go decisions.
- Build or validation plans.
- Claims of market size, profitability, conversion, or prevalence unsupported
  by collected evidence.

## Operating Shape

- Run locally.
- Prefer inspectable Markdown, JSONL, and CSV.
- Preserve intermediate artifacts when they improve provenance.
- Keep collection separate from product selection.
- Surface missingness, uncertainty, contradictions, access limits, and source
  bias instead of hiding them.
