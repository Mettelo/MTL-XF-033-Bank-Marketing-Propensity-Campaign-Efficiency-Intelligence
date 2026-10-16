# MTL-XF-033 — Data acquisition and engineering

## Approved S1

[Bank Marketing](https://archive.ics.uci.edu/dataset/222); required files: **bank.zip → bank-full.csv and bank-names.txt**. Expected source population: 45,211 records in bank-full.csv.

Exact official download:

https://archive.ics.uci.edu/static/public/222/bank+marketing.zip

No paid API or temporary dashboard export is required. [Source register](SOURCE_REGISTER.md) records checked byte references and rights.

## Frozen cohort and schema

Use bank-full.csv, all 45,211 records, from the nested bank.zip archive only. Do not stack bank.csv samples or bank-additional variants. Retain original order and categorical unknowns.

**Grain:** One published campaign record, not an assured unique customer; source-row surrogate ID.

**Required fields:** age, job, marital, education, default, balance, housing, loan, contact, day, month, duration, campaign, pdays, previous, poutcome, y.

## Acquisition and freeze procedure

1. Retrieve original bytes and required documentation into approved durable storage outside Git. Record retrieval UTC, requested/resolved URLs and HTTP result.
2. Verify archive/member integrity, actual sizes and SHA-256 against the checked reference. A mismatch stops processing for publisher-change/corruption review.
3. Inspect schema, encoding, separator, headers/sheets, count, label coding, dates and coverage. Extract nested bank.zip; read bank-full.csv with semicolon separator and bank-names.txt. Ignore bank.csv sample and bank-additional variants.
4. Complete source→actual field→KPI→deliverable support matrix for K1–K7 and D1–D12. Missing mandatory fields block dependent work; do not invent substitutes.
5. Approve an immutable S1-v1 byte manifest and exact cohort with retention owner, reviewer access, analyst/reviewer identities and date. Master source verification does not replace team G1 approval.
6. Transform reproducibly into separate curated outputs. Account for every raw row once as retained, excluded or quarantined; preserve lineage and treatment reason.

## Evaluation

Use first 60%, next 20%, last 20% in published record order, documenting that exact dates and repeated customers cannot be verified. Preserve order; train-only transforms; exclude duration and y. Treat contact/day/month/campaign as planned-context features only with explicit timing assumptions. Core pre-contact model also excludes contact, day, month and campaign unless separately evaluated as a labelled planned-contact scenario; this avoids treating the completed last contact as known before selection.

## Interpretation and quality

No stable customer ID is available. duration leaks completed-call information and must be excluded from pre-call prioritisation. Historical subscription probability is not incremental campaign uplift; consent, customer vulnerability and actual account profitability are absent.

Profile every actual column. Dictionary includes spelling, type, unit, valid values, sentinel/null policy, meaning and feature/target/ID role plus availability time. Investigate duplicates/label conflicts; no silent deduplication or denominator invention. Validate key uniqueness and joins at the declared grain.

Keep [raw](raw/README.md), [references](reference/README.md) and [metadata](metadata/README.md) separate. Derived outputs belong in team data/curated/ or an approved location. Raw data are not uploaded by this update. Refresh creates a new snapshot while the accepted core stays reproducible.
