# Dissatisfaction and Complaint Evidence Artifacts

Store inspectable evidence collected for the `dissatisfaction` cluster here.
This directory currently contains no market evidence.

Likely future artifacts:

- `raw.jsonl`: source-native review, issue, discussion, or support records with
  stable IDs, URLs, text, dates, ratings, replies, and collection-run IDs
- `snapshots.jsonl`: product/source observations with displayed ratings, rating
  histograms, versions, update dates, source mechanics, and coverage metadata
- `tags.jsonl`: review-theme pairs and derived annotations retaining raw IDs
- `themes.csv`: spreadsheet-friendly product/source/theme/window rollups
- `cross_product.csv`: repeated themes across a defined competitor set

Keep raw source records separate from normalized annotations and summaries.
Unknown values remain missing, never zero. Sample metrics must be named as
samples and tied to collection coverage. Planning specifications and API notes
do not belong here as collected evidence.

`PROFILE.md` remains the human-readable summary. Every factual item must link
back to stable evidence IDs stored here.
