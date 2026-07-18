# Workaround Evidence: Cluster-Specific Instructions

- Read `CONTEXT.md` completely before changing `workaround.py`, evidence, or
  profile output.
- Treat a mention as workaround evidence only when the source contains all
  three elements: a job or problem, concrete substitute behavior, and friction,
  insufficiency, risk, or cost.
- Do not classify ordinary use of a spreadsheet, template, checklist, notes
  app, PDF, automation tool, or other general-purpose tool as a workaround
  without compensating behavior.
- Keep raw mention facts separate from problem-cluster labels and rollups.
  Preserve the raw identifiers behind every derived field.
- Retain borderline material as `adjacent_signal`; do not promote it or discard
  it silently.
- Treat search snippets as discovery evidence until the original page is
  retrieved. Mark unretrieved records `snippet_only=true`.
- Preserve each platform's native engagement value and type. Never compare
  unlike scores as one universal engagement measure.
- Down-rank temporary version-specific fixes and suspected promotional
  idea-fishing unless independent sources show a persistent underlying job.
- Say `no public evidence found`, never `no workaround exists`, when collection
  cannot observe private or restricted sources.
- Keep access terms, quotas, prices, and source availability explicitly dated
  and reverified before relying on them.
- Keep cluster-specific collection and transformation logic in `workaround.py`.
  Do not invent its public interface before shared runner contracts exist.
- Never present this cluster's planning material as collected market evidence
  in `PROFILE.md`.
