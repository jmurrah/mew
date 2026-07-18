# Problem Existence Evidence Artifacts

Store inspectable collected evidence here. Supplied planning documents do not
belong in this directory and must not be copied into evidence outputs.

Preferred future artifacts:

- `raw.jsonl`: original or minimally wrapped source records with stable evidence
  IDs, URLs, excerpts, source dates, capture dates, source-native metrics, and
  collection metadata
- `normalized.jsonl`: optional annotations and normalized problem statements
  retaining raw evidence IDs and missing values
- `profile.csv`: optional spreadsheet-friendly aggregate measures and coverage
  limitations

Preserve native API or page records separately from normalized rows. Search
results may record discovery provenance, but hydrate the original source before
counting a problem mention. Never overwrite raw records with annotations or
summaries.

`PROFILE.md` remains the human-readable cluster summary. Every factual item must
link back to stable IDs stored here.
