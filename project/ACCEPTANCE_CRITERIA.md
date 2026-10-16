# MTL-XF-033 — Acceptance and domain tests

Acceptance requires executed evidence, not headings. Marketing Model Assurance Analyst records state, actual result, evidence/commit, date, author, reviewer and defect/retest reference. Templates start NOT RUN.

## AC1–AC12

| Criterion | Output | Measurable pass condition |
| --- | --- | --- |
| AC1 | D1 | All eight link source support, D/AC/DT and Head of Retail Banking Marketing approval. |
| AC2 | D2 | Every required file/field is verified and approved; unsupported requirements explicitly block G1. |
| AC3 | D3 | Input=retained+excluded+quarantined exactly; no unexplained join multiplication; clean-run instructions exist. |
| AC4 | D4 | Every treatment has affected count, reason, owner and reviewer; no silent row loss or coercion. |
| AC5 | D5 / SC1 | All 45,211 source records accounted for; y=yes is positive; pdays=−1 means no previous contact; repeated records are not claimed to be unique customers. |
| AC6 | D6 / SC2 | duration and y never enter predictors; completed last-contact fields excluded from core as specified; no test tuning; report class counts and baseline underperformance. |
| AC7 | D7 / SC3 | Both lists use identical eligible records/capacity; ties use source ID; net-value arithmetic is reproducible and labelled assumed historical response economics, not incremental profit. |
| AC8 | D8 / SC4 | Reviewer changes cost/value assumptions, verifies selected count remains fixed, and traces one selected/deferred case without exposing unnecessary personal fields. |
| AC9 | D9 | All ten tests and three tasks pass; zero unresolved critical/high defects. |
| AC10 | D10 | Second member reproduces all seven KPIs and policy queue from approved bytes; environment, elapsed time and discrepancies recorded. |
| AC11 | D11 / SC5 | Pilot distinguishes propensity from causal uplift; specifies actual customer IDs and consent evidence needed before operation; no live contact or sales claim. |
| AC12 | D12 | All D/AC/DT evidence links resolve at final commit/tag; individual contribution is demonstrated beyond bulk upload or commit count. |

## SC1–SC5 — Business output success contracts

These requirements supplement AC1–AC12 and are mandatory. Record approval at G1, then execute against final outputs. All five require PASS with traceable evidence, or a formally approved scope revision; an unmet model-performance target must be reported as unmet and reflected in the recommendation.

### SC1 / D5 — Campaign population and contact scorecard

**Accountable delivery role:** Campaign Strategy Analyst. **Business reviewer:** Head of Retail Banking Marketing. **Independent assurance:** Marketing Model Assurance Analyst.

**Required artefact:** data/curated/campaign-population-and-contact-scorecard.csv and docs/05-kpi-catalogue/campaign-population-and-contact-scorecard.md.

**Content:** Response counts/rate, campaign contact distribution, previous-contact coverage and unknown-category counts; source-row identity and approved chronological partition.

**Pass condition:** All 45,211 source records accounted for; y=yes is positive; pdays=−1 means no previous contact; repeated records are not claimed to be unique customers.

**Evidence to retain:** actual output at final commit, source/configuration lineage, executed expected-versus-actual checks, reviewer identity/date and PASS/FAIL/BLOCKED. Do not mark complete from document presence alone.

### SC2 / D6 — Pre-contact propensity evaluation

**Accountable delivery role:** Data Scientist / Decision Modelling Analyst. **Business reviewer:** Head of Retail Banking Marketing. **Independent assurance:** Marketing Model Assurance Analyst.

**Required artefact:** docs/06-analysis/pre-contact-propensity-evaluation.md plus machine-readable evaluation_results.csv.

**Content:** Majority/rate baseline and interpretable candidate model; explicit feature-availability audit; precision/recall/lift at 20% test capacity and uncertainty.

**Pass condition:** duration and y never enter predictors; completed last-contact fields excluded from core as specified; no test tuning; report class counts and baseline underperformance.

**Evidence to retain:** actual output at final commit, source/configuration lineage, executed expected-versus-actual checks, reviewer identity/date and PASS/FAIL/BLOCKED. Do not mark complete from document presence alone.

### SC3 / D7 — Equal-capacity campaign and economics comparison

**Accountable delivery role:** Campaign Strategy Analyst. **Business reviewer:** Head of Retail Banking Marketing. **Independent assurance:** Marketing Model Assurance Analyst.

**Required artefact:** docs/07-decision-framework/equal-capacity-campaign-and-economics-comparison.csv plus policy.md.

**Content:** Random seed-33 list and ranked list, each floor(0.2×N) test records; subscriptions per 1,000 selected contacts and nine stated cost/value scenarios.

**Pass condition:** Both lists use identical eligible records/capacity; ties use source ID; net-value arithmetic is reproducible and labelled assumed historical response economics, not incremental profit.

**Evidence to retain:** actual output at final commit, source/configuration lineage, executed expected-versus-actual checks, reviewer identity/date and PASS/FAIL/BLOCKED. Do not mark complete from document presence alone.

### SC4 / D8 — Campaign planning dashboard

**Accountable delivery role:** BI / Decision Product Developer. **Business reviewer:** Head of Retail Banking Marketing. **Independent assurance:** Marketing Model Assurance Analyst.

**Required artefact:** dashboard/README.md, runnable dashboard/prototype and static review export.

**Content:** List-capacity comparison, response capture, contact-burden diagnostics and model/source limitations.

**Pass condition:** Reviewer changes cost/value assumptions, verifies selected count remains fixed, and traces one selected/deferred case without exposing unnecessary personal fields.

**Evidence to retain:** actual output at final commit, source/configuration lineage, executed expected-versus-actual checks, reviewer identity/date and PASS/FAIL/BLOCKED. Do not mark complete from document presence alone.

### SC5 / D11 — Controlled campaign pilot brief

**Accountable delivery role:** Business Analyst / Delivery Lead with domain specialist. **Business reviewer:** Head of Retail Banking Marketing. **Independent assurance:** Marketing Model Assurance Analyst.

**Required artefact:** deliverables/controlled-campaign-pilot-brief.pdf plus editable slides and supporting cards/runbook.

**Content:** Pilot arms, eligibility/consent checks, contact-frequency guardrail, randomisation unit, outcome window, sample-size assumptions and stop/review rules.

**Pass condition:** Pilot distinguishes propensity from causal uplift; specifies actual customer IDs and consent evidence needed before operation; no live contact or sales claim.

**Evidence to retain:** actual output at final commit, source/configuration lineage, executed expected-versus-actual checks, reviewer identity/date and PASS/FAIL/BLOCKED. Do not mark complete from document presence alone.


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

## Three project-specific UAT tasks

1. **Business review:** Before a term-deposit campaign, marketing compares a fixed random 20% list with a model-ranked 20% list, reviews expected historical response capture and cost scenarios, and approves a consent-screened randomised pilot rather than deploying historical propensity as proven uplift. The participant must explain the observed baseline, population and decision limitation without assistance from the author; record actual completion and any defect.
2. **Policy challenge:** use the D7 artefact to compare a baseline and alternative case, then record accept/defer/override with evidence and accountable owner. The domain reviewer must independently reproduce the case outcome.
3. **Operational walkthrough:** Reviewer changes cost/value assumptions, verifies selected count remains fixed, and traces one selected/deferred case without exposing unnecessary personal fields. Retain the task recording/screenshots, expected/actual values and reviewer outcome.

All three must pass after defect retest. Static exports may support review if interactive access is unavailable. The independent reviewer also checks every SC output against its declared artefact and source/configuration lineage.

## Release

All twelve ACs, ten DTs, UAT and independent rerun require evidence with zero unresolved critical/high defects. Underperformance can justify a baseline/manual policy; wrong labels/units, leakage, unregistered data or unsupported operational claims block acceptance. A scope revision updates affected requirements/tests; it cannot mark an unexecuted check passed.
