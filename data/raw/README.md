# MTL-XF-033 — Raw-data preservation

**No raw data are uploaded by this update.** This directory documents the strategy; it does not assert that input payloads are in Git.

Acquire bank.zip → bank-full.csv and bank-names.txt from [S1 exact URL and checked-byte reference](../SOURCE_REGISTER.md). Retain original archive/members/codebooks outside Git in an immutable S1-v1 snapshot; record retrieval UTC, URL, filename, bytes and SHA-256. Keep a recoverable copy with retention owner and reviewer access.

**Frozen scope:** Use bank-full.csv, all 45,211 records, from the nested bank.zip archive only. Do not stack bank.csv samples or bank-additional variants. Retain original order and categorical unknowns.

Extract nested bank.zip; read bank-full.csv with semicolon separator and bank-names.txt. Ignore bank.csv sample and bank-additional variants.

Never overwrite, edit, re-encode or deduplicate originals. Extract into a separate working area; transformations, exclusions and parsed labels belong in code and curated outputs with source-row lineage. Check original and extracted byte hashes before analysis. A mismatch or missing approved snapshot blocks processing until resolved.

Team repositories should ignore local raw payloads while tracking this guidance and metadata. Do not remove any previously supplied raw data without explicit approval. Store access instructions without credentials and document restoration from retained bytes if upstream changes.
