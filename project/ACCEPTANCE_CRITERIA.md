# MTL-XF-033 — Acceptance and domain tests

Acceptance requires executed evidence, not headings. Marketing Model Assurance Analyst records state, actual result, evidence/commit, date, author, reviewer and defect/retest reference. Templates start NOT RUN.

## AC1–AC12

| Criterion | Output | Measurable pass condition |
| --- | --- | --- |
| AC1 | D1 | All eight link source support, D/AC/DT and Head of Retail Banking Marketing approval. |
| AC2 | D2 | Every required file/field is verified and approved; unsupported requirements explicitly block G1. |
| AC3 | D3 | Input=retained+excluded+quarantined exactly; no unexplained join multiplication; clean-run instructions exist. |
| AC4 | D4 | Every treatment has affected count, reason, owner and reviewer; no silent row loss or coercion. |
| AC5 | D5 | All seven reviewed; K1–K5 reconcile independently and in BI on full cohort and one filtered slice. |
| AC6 | D6 | Baseline and alternative results, population/class counts, uncertainty, negative findings and feature/timing audit retained; no test-driven tuning. |
| AC7 | D7 | Both policies and sensitivity outputs supplied; every action has evidence, eligibility, owner, next review and uncertainty. Include a defer case. |
| AC8 | D8 | Five metric/filter checks pass; frozen scope and limitations survive export; static copy/user guide require no paid access. |
| AC9 | D9 | All ten tests and three tasks pass; zero unresolved critical/high defects. |
| AC10 | D10 | Second member reproduces all seven KPIs and policy queue from approved bytes; environment, elapsed time and discrepancies recorded. |
| AC11 | D11 | Every numeric claim links tested evidence; costs/benefits and operational targets are labelled assumptions unless measured. |
| AC12 | D12 | All D/AC/DT evidence links resolve at final commit/tag; individual contribution is demonstrated beyond bulk upload or commit count. |

## DT1–DT10

| Test | Case | Expected result |
| --- | --- | --- |
| DT1 | Duration exclusion | Any core predictor named duration fails the pre-contact feature audit. |
| DT2 | Prior contact sentinel | pdays=−1 is not treated as a negative elapsed duration or imputed to a recent contact. |
| DT3 | Unknown category | An unseen job/contact category transforms without dropping the row or consulting test outcomes. |
| DT4 | Capacity ties | A tie at the 20% boundary follows stable source-ID ordering and returns exactly floor(0.2×N) rows. |
| DT5 | Outcome coding | y=yes is the positive class; 2 yes among 10 records gives 20%. |
| DT6 | Causal restraint | A higher historical selected response rate cannot be described as incremental campaign uplift. |
| DT7 | Source row accounting | One malformed fixture row is quarantined with source ID/reason; retained+excluded+quarantined equals input with no overlap. |
| DT8 | Missing versus zero | A 0/0 rate is unavailable with reason. Missing source evidence never becomes a measured zero or a fabricated result. |
| DT9 | BI reconciliation | K1–K5 match independent calculations on full cohort and one filtered slice. Counts exact; arithmetic unrounded or tolerance at most 0.01 displayed unit. |
| DT10 | Independent rerun | Distinct member reproduces cohort IDs, K1–K7 and policy selections from frozen bytes/configuration. Any stochastic tolerance is declared before running and discrepancies resolved. |

Use small synthetic fixtures for edge cases and frozen-source checks where relevant. Clearly distinguish fixture results from measured source outputs. Retain expected/actual evidence in docs/08-assurance-uat/; automate deterministic calculations where practical and document UI/interpretation reviews.

## Three UAT tasks

1. Head of Retail Banking Marketing finds K1, explains its denominator, snapshot and limitation.
2. Campaign Strategy Analyst compares one baseline/alternative case and records accept/defer/override with rationale.
3. An operational user traces an action to source evidence and finds the manual review/escalation owner.

Record participant role, expected/observed result, defect and retest. All three must pass; static exports may support review where interactive access is unavailable.

## Release

All twelve ACs, ten DTs, UAT and independent rerun require evidence with zero unresolved critical/high defects. Underperformance can justify a baseline/manual policy; wrong labels/units, leakage, unregistered data or unsupported operational claims block acceptance. A scope revision updates affected requirements/tests; it cannot mark an unexecuted check passed.
