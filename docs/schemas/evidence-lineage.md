# Evidence and Lineage

This document defines a shared conceptual data contract. It does not select a
database, file layout, Python schema, or public runner interface.

## Entity Types

- run;
- acquisition event;
- search request;
- retrieval event;
- raw payload;
- evidence record;
- source-policy version;
- transformation;
- derived record;
- duplicate group;
- cluster membership;
- claim;
- supporting span.

Each entity receives a stable internal ID from a documented namespace. IDs are
immutable, collision-safe, filename-safe, and separate from source-native IDs.
Exact syntax remains undecided.

## Required Evidence Fields

Every accepted evidence record requires:

```text
evidence_id
run_id
source_id
record_type
acquisition_method
retrieved_at
source_policy_id
```

It also requires at least one usable locator:

```text
source_native_id
final_url
raw_payload_path
imported_file_path
```

Common nullable fields:

```text
query_id
parent_evidence_id
thread_evidence_id
requested_url
canonical_url
title
excerpt
published_at
updated_at
rank
author_display
score
rating
rating_count
raw_payload_path
raw_payload_sha256
raw_payload_bytes
raw_payload_content_type
raw_payload_storage_status
content_sha256
http_status
extraction_status
processing_status
duplicate_group_id
```

## Required Links

Preserve typed relationships from:

- run to acquisition event;
- request to result;
- parent record to child record;
- evidence record to raw payload;
- evidence record to source-policy version;
- evidence record to normalized or annotated record;
- evidence record to duplicate group;
- derived record to every supporting evidence record;
- cluster membership to supporting evidence records;
- claim to supporting evidence records and spans;
- transformation output to inputs and transformation version.

Many-to-many relationships should use arrays or join artifacts. Delimited CSV
cells may be export views, not the only canonical representation.

## Search Context

Never store naked rank. Preserve exact query, provider, engine, country,
language, device, safe-search setting, account and personalization state,
requested result count, page or offset, timestamps, response artifact, and
provider-native block or rank.

## Payload Contract

Large JSON, HTML, XML, text, images, and imported files remain outside tabular
indexes. Record path, SHA-256, bytes, media type, retention status, and deletion
events. Compression is allowed only when original bytes can be reproduced.

Raw payload and extracted-text hashes remain separate so source changes and
parser changes can be distinguished.

## Transformation Contract

Each transformation records:

```text
transformation_id
method
version
executed_at
input_ids
output_ids
rule_or_taxonomy_version
model_and_prompt_version
confidence
failure_state
notes
```

Use only applicable fields. Deterministic extraction, model annotation, and
human review remain distinguishable.

## Source-Policy Contract

Each evidence record links to policy active at acquisition. Store access method,
official interface status, documentation and terms URLs, commercial-use state,
automated-access state, payload and excerpt retention state, attribution,
deletion duties, rate limits, review date, and notes.

Policy changes create new versions. Required deletion creates a tombstone or
event linking affected artifacts without retaining prohibited material.

Recommended controlled states include:

```text
commercial_use_status:
  allowed
  prohibited
  permission_required
  unclear
  not_reviewed

full_text_storage_status:
  allowed
  excerpt_only
  metadata_only
  prohibited
  unclear
```

Manual imports follow the same contract and additionally preserve imported file
path/hash, import time, importer identity where appropriate, original source URL,
contextual excerpt, researcher note, and source-policy ID.

## Storage Ownership

Shared immutable run storage versus cluster-local evidence ownership remains an
open decision. Preferred direction is shared payloads plus cluster-local indexes
or stable references, avoiding copied raw data. See the
[provenance decision](../decisions/0003-provenance-layer.md).
