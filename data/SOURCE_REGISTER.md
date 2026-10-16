# MTL-XF-033 — Source register

## S1 — Bank Marketing

| Field | Approved definition |
| --- | --- |
| Provider | UCI Machine Learning Repository; preserve original creator attribution |
| Documentation | https://archive.ics.uci.edu/dataset/222 |
| Exact download | https://archive.ics.uci.edu/static/public/222/bank+marketing.zip |
| Required inputs | bank.zip → bank-full.csv and bank-names.txt |
| Source population | 45,211 records in bank-full.csv |
| Decision owner | Head of Retail Banking Marketing |
| Status | Official archive/feed retrieved and inspected; team freeze/sign-off and analysis remain to be completed. No raw data uploaded. |

Persistent citation: https://doi.org/10.24432/C5K306

## Checked byte reference

Official archive retrieved and inspected on **2026-10-16**. Archive size **1023843 bytes**; SHA-256 **e0bf5f5de5b846e2f18e9d90606637267d46dfa260e0f17bb12e605db5efbeb4**.

| Archive member | Bytes | SHA-256 |
| --- | --- | --- |
| bank.zip | 579043 | 99d7e8eb12401ed278b793984423915411ea8df099e1795f9fefe254f513fe5e |
| bank-additional.zip | 444572 | a607b5edab6c6c75ce09c39142a77702c38123bd5aa7ae89a63503bbe17d65cd |

Nested bank-full.csv verified at 45,211 records, SHA-256 d1513ec63b385506f7cfce9f2c5caa9fe99e7ba4e8c3fa264b3aaf0f849ed32d. Extract bank.zip, then parse bank-full.csv with semicolon delimiter. Do not combine overlapping sample/additional variants.

Extract nested bank.zip; read bank-full.csv with semicolon separator and bank-names.txt. Ignore bank.csv sample and bank-additional variants.

## Cohort and field support

Use bank-full.csv, all 45,211 records, from the nested bank.zip archive only. Do not stack bank.csv samples or bank-additional variants. Retain original order and categorical unknowns.

**Grain:** One published campaign record, not an assured unique customer; source-row surrogate ID.

**Required mapping:** age, job, marital, education, default, balance, housing, loan, contact, day, month, duration, campaign, pdays, previous, poutcome, y.

**Interpretation limits:** No stable customer ID is available. duration leaks completed-call information and must be excluded from pre-call prioritisation. Historical subscription probability is not incremental campaign uplift; consent, customer vulnerability and actual account profitability are absent.

## Rights and attribution

Publisher page declares [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Cite original creators, UCI and [dataset DOI](https://doi.org/10.24432/C5K306); preserve notices and state transformations.

## Team acquisition record required at G1

Record source/freeze ID, requested/resolved URL, retrieval UTC, release/feed timestamp, archive/member filename, actual bytes/checksum, encoding/delimiter/worksheet/schema, row count, date bounds, included/excluded scope, licence/citation evidence, storage/access and retention owner, verification checks, analyst and reviewer approval/date. Unknown or unexecuted fields remain explicitly pending.

## Raw-data durability

Preserve original archive, required members and documentation in a read-only S1-v1 snapshot in approved durable storage outside Git with a second recoverable copy. Record reviewer access and restore instructions without credentials. Provider/DOI URLs locate the source; retained checksum-addressed bytes define reproducibility. Stable URLs do not guarantee immutable contents or perpetual availability.

No raw data are committed by this master update. Restore verified retained bytes if the provider becomes unavailable. If no approved copy exists, block G1; do not substitute an unofficial mirror, another variant or guessed schema. A new official version requires rights/schema/scope review, new freeze ID and rerun of affected tests.

## Refresh and supplementary inputs

Do not stack overlapping UCI samples/variants. Required publisher codebooks remain source references. Business costs, capacities and pilot outcomes absent from S1 are synthetic assumptions, not measured facts.

Every added reference/supplement needs ID, official source/version/URL, rights, grain/coverage, purpose, join key/cardinality, effect on K/D/AC/DT and reviewer approval. Optional extensions cannot replace core requirements silently.
