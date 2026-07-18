# Workaround Evidence Artifacts

Store inspectable evidence collected for the `workaround` cluster here. This
directory currently contains no market evidence.

Likely future artifacts:

- `raw.jsonl`: source records with stable mention identifiers, URLs, excerpts,
  source queries, collection metadata, and raw payload references
- `normalized.jsonl`: optional classifications and problem-cluster assignments
  that retain raw mention identifiers
- `profile.csv`: optional spreadsheet-friendly derived review output

Keep search snippets marked as discovery-only until original sources are
retrieved. Preserve each platform's native engagement value and type. Do not
overwrite raw records with normalized, clustered, or summarized data.

`PROFILE.md` remains the human-readable summary. Planning specifications and API
feasibility notes do not belong here as collected evidence.
