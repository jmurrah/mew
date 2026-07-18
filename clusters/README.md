# Clusters

Each cluster is an independent evidence profiler for one market topic or domain.
The eventual top-level Python runner calls functions exposed by each cluster's
appropriately named Python module.

Create a cluster by copying `_template` to a lowercase `snake_case` directory:

```bash
cp -R clusters/_template clusters/<cluster_id>
```

Then replace placeholders in `AGENTS.md` and `CONTEXT.md`. Keep `_template`
unchanged except when improving the structure for all future clusters. Rename
`cluster_name.py` to match the cluster ID.

Expected layout:

```text
clusters/<cluster_id>/
  AGENTS.md     cluster-local operating rules
  CONTEXT.md    detailed, durable user guidance
  <cluster_id>.py  cluster-specific Python functions
  PROFILE.md    current nine-part evidence profile
  evidence/     raw and derived inspectable artifacts
```

For each new cluster:

1. Copy the template.
2. Rename `cluster_name.py` to `<cluster_id>.py`.
3. Use the supplied PDF and long-form context to model the cluster Markdown
   files.
4. Put durable operating rules in `AGENTS.md` and detailed domain guidance in
   `CONTEXT.md`.
5. Keep the required evidence structure in `PROFILE.md`.
6. Build or update the cluster profiler after the guidance is clear.
