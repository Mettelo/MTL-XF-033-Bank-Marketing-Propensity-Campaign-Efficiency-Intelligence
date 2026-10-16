# MTL-XF-033 — Deliverables and metric contracts

**Decision:** Compare capacity-limited contact lists and design a controlled term-deposit campaign pilot.

Required team outputs follow; this master does not claim they are complete. Each item needs a named author, distinct reviewer, version, evidence link and status.

## D1 — Discovery and requirements

**Due:** Week 2 · **Owner:** Business Analyst / Delivery Lead · **Team location:** docs/01-discovery/

Eight user requirements, prioritised by decision value, each with owner and measurable test; stakeholder map and as-is/to-be workflow for outbound campaign planning review.

**Pass evidence:** All eight link source support, D/AC/DT and Head of Retail Banking Marketing approval.

## D2 — Governed source and freeze

**Due:** Week 2 · **Owner:** Data Governance Analyst · **Team location:** docs/02-data-governance/

S1 provenance, rights, dictionary, storage/restore path and immutable byte manifest. Use bank-full.csv, all 45,211 records, from the nested bank.zip archive only. Do not stack bank.csv samples or bank-additional variants. Retain original order and categorical unknowns.

**Pass evidence:** Every required file/field is verified and approved; unsupported requirements explicitly block G1.

## D3 — Engineering pipeline and model

**Due:** Week 4 · **Owner:** Data Engineer · **Team location:** src/ and docs/03-data-model/

Versioned ingestion/transformation and curated model. Grain: One published campaign record, not an assured unique customer; source-row surrogate ID. Preserve file/sheet/row lineage and all exclusion reasons.

**Pass evidence:** Input=retained+excluded+quarantined exactly; no unexplained join multiplication; clean-run instructions exist.

## D4 — Quality and exceptions

**Due:** Week 4 · **Owner:** Data Engineer + independent reviewer · **Team location:** docs/04-data-quality/

Profile types, nulls, duplicates, sentinels, labels, units and source support. Address Using call duration or confusing propensity with causal uplift would create an invalid pre-call business case.

**Pass evidence:** Every treatment has affected count, reason, owner and reviewer; no silent row loss or coercion.

## D5 — Campaign population and contact scorecard

**Due:** Week 4 · **Owner:** Campaign Strategy Analyst · **Business reviewer:** Head of Retail Banking Marketing · **Independent reviewer:** Marketing Model Assurance Analyst

**Required artefact:** data/curated/campaign-population-and-contact-scorecard.csv and docs/05-kpi-catalogue/campaign-population-and-contact-scorecard.md.

Response counts/rate, campaign contact distribution, previous-contact coverage and unknown-category counts; source-row identity and approved chronological partition.

**Mandatory pass condition (SC1):** All 45,211 source records accounted for; y=yes is positive; pdays=−1 means no previous contact; repeated records are not claimed to be unique customers.

**Review evidence:** retain the actual output, source-to-field/code/configuration lineage, expected/actual verification, reviewer and date. A heading, screenshot or unsupported claim alone cannot satisfy this deliverable.


## D6 — Pre-contact propensity evaluation

**Due:** Week 6 · **Owner:** Data Scientist / Decision Modelling Analyst · **Business reviewer:** Head of Retail Banking Marketing · **Independent reviewer:** Marketing Model Assurance Analyst

**Required artefact:** docs/06-analysis/pre-contact-propensity-evaluation.md plus machine-readable evaluation_results.csv.

Majority/rate baseline and interpretable candidate model; explicit feature-availability audit; precision/recall/lift at 20% test capacity and uncertainty.

**Mandatory pass condition (SC2):** duration and y never enter predictors; completed last-contact fields excluded from core as specified; no test tuning; report class counts and baseline underperformance.

**Review evidence:** retain the actual output, source-to-field/code/configuration lineage, expected/actual verification, reviewer and date. A heading, screenshot or unsupported claim alone cannot satisfy this deliverable.


## D7 — Equal-capacity campaign and economics comparison

**Due:** Week 6 · **Owner:** Campaign Strategy Analyst · **Business reviewer:** Head of Retail Banking Marketing · **Independent reviewer:** Marketing Model Assurance Analyst

**Required artefact:** docs/07-decision-framework/equal-capacity-campaign-and-economics-comparison.csv plus policy.md.

Random seed-33 list and ranked list, each floor(0.2×N) test records; subscriptions per 1,000 selected contacts and nine stated cost/value scenarios.

**Mandatory pass condition (SC3):** Both lists use identical eligible records/capacity; ties use source ID; net-value arithmetic is reproducible and labelled assumed historical response economics, not incremental profit.

**Review evidence:** retain the actual output, source-to-field/code/configuration lineage, expected/actual verification, reviewer and date. A heading, screenshot or unsupported claim alone cannot satisfy this deliverable.


## D8 — Campaign planning dashboard

**Due:** Week 7 · **Owner:** BI / Decision Product Developer · **Business reviewer:** Head of Retail Banking Marketing · **Independent reviewer:** Marketing Model Assurance Analyst

**Required artefact:** dashboard/README.md, runnable dashboard/prototype and static review export.

List-capacity comparison, response capture, contact-burden diagnostics and model/source limitations.

**Mandatory pass condition (SC4):** Reviewer changes cost/value assumptions, verifies selected count remains fixed, and traces one selected/deferred case without exposing unnecessary personal fields.

**Review evidence:** retain the actual output, source-to-field/code/configuration lineage, expected/actual verification, reviewer and date. A heading, screenshot or unsupported claim alone cannot satisfy this deliverable.


## D9 — Independent assurance and UAT

**Due:** Week 7 · **Owner:** Marketing Model Assurance Analyst · **Team location:** docs/08-assurance-uat/

Execute DT1–DT10 and three stakeholder tasks; record actual results and defects/retests.

**Pass evidence:** All ten tests and three tasks pass; zero unresolved critical/high defects.

## D10 — Technical/operational handover

**Due:** Week 8 · **Owner:** Engineer + Delivery Lead · **Team location:** docs/09-technical-handover/

One documented run entry point, dependency versions, manifest, output checksums/tolerances, refresh, rollback and operational owner.

**Pass evidence:** Second member reproduces all seven KPIs and policy queue from approved bytes; environment, elapsed time and discrepancies recorded.

## D11 — Controlled campaign pilot brief

**Due:** Week 8 · **Owner:** Business Analyst / Delivery Lead with domain specialist · **Business reviewer:** Head of Retail Banking Marketing · **Independent reviewer:** Marketing Model Assurance Analyst

**Required artefact:** deliverables/controlled-campaign-pilot-brief.pdf plus editable slides and supporting cards/runbook.

Pilot arms, eligibility/consent checks, contact-frequency guardrail, randomisation unit, outcome window, sample-size assumptions and stop/review rules.

**Mandatory pass condition (SC5):** Pilot distinguishes propensity from causal uplift; specifies actual customer IDs and consent evidence needed before operation; no live contact or sales claim.

**Review evidence:** retain the actual output, source-to-field/code/configuration lineage, expected/actual verification, reviewer and date. A heading, screenshot or unsupported claim alone cannot satisfy this deliverable.


## D12 — Contribution and final submission

**Due:** Weekly; final week 8 · **Owner:** Delivery Lead · **Team location:** CONTRIBUTIONS.md and submission/FINAL_SUBMISSION.md

Named D owners/reviewers, authored work, issues/PRs/commits, substantive reviews and demo/handover contribution for each member.

**Pass evidence:** All D/AC/DT evidence links resolve at final commit/tag; individual contribution is demonstrated beyond bulk upload or commit count.

## K1–K7 — Authoritative contracts

| ID | Metric | Definition and population | Grain |
| --- | --- | --- | --- |
| K1 | Subscription rate | count(y=yes)/valid y records; retain unknown inputs as categories. | campaign record cohort |
| K2 | Contact burden | mean and median campaign contacts; report extreme values separately. | subscription group |
| K3 | Prior-contact coverage | count(pdays≠−1)/valid pdays records; −1 means no previous contact. | cohort |
| K4 | Precision at capacity | subscribers in selected top 20% / selected records. | test |
| K5 | Recall at capacity | subscribers in selected list / all test subscribers. | test |
| K6 | Lift at capacity | selected-list subscription rate / overall test subscription rate. | test |
| K7 | Assumed campaign net value | selected count × (observed selected subscription fraction × assumed subscription value − assumed contact cost); no causal or realised-profit claim. | nine cost/value scenarios |

Extend each contract with actual S1 raw fields and curated columns, code lineage, population/exclusions, numerator/denominator, units/grain, aggregation, missing/zero/undefined policy, owner/reviewer, freeze ID and tests. Campaign Strategy Analyst owns interpretation; Engineer implements; Marketing Model Assurance Analyst reviews.

Zero denominators produce unavailable values with reasons. Do not average subgroup rates when compatible summed numerators/denominators are required. Show class/segment counts beside rates and uncertainty. Counts reconcile exactly; arithmetic reconciles unrounded or to a documented tolerance no wider than 0.01 displayed unit. No source field can silently be replaced by an assumption.

## Evaluation and decision policy

Use first 60%, next 20%, last 20% in published record order, documenting that exact dates and repeated customers cannot be verified. Preserve order; train-only transforms; exclude duration and y. Treat contact/day/month/campaign as planned-context features only with explicit timing assumptions. Core pre-contact model also excludes contact, day, month and campaign unless separately evaluated as a labelled planned-contact scenario; this avoids treating the completed last contact as known before selection.

Baseline selects a deterministic random 20% contact list (seed 33). Alternative selects top-scored 20% using a validation-selected model and locked tie rule. Evaluate subscriptions per 1,000 attempted contacts and assumed net value under £1/£3/£5 contact costs and £20/£50/£100 subscription value; all amounts are simulation assumptions.

**Interpretation boundary:** No stable customer ID is available. duration leaks completed-call information and must be excluded from pre-call prioritisation. Historical subscription probability is not incremental campaign uplift; consent, customer vulnerability and actual account profitability are absent.

See [acceptance](ACCEPTANCE_CRITERIA.md) for tests and [governance](GOVERNANCE.md) for release decisions.
