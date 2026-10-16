# MTL-XF-033 — Project brief

This is a simulated confidential-client engagement using public/open data. Stakeholders and commercial/security scenarios are fictional. Do not claim real-client employment, endorsement, operational deployment or realised benefits. This master pack specifies work to be completed; it does not claim the team has executed it.

**Client:** Confidential Retail Bank · **Sponsor:** Head of Retail Banking Marketing · **Team:** 3–5 · **Duration:** 8 weeks · **Cycle:** outbound campaign planning review

## Problem and commission

The outbound campaign manager can contact only one fifth of the eligible list in the planning scenario. Selecting customers by a broad demographic profile may waste calls, but selecting on completed-call duration would make a pre-call model look useful using information the caller does not yet know. The bank needs a comparison of contact lists at the same capacity and a transparent view of response concentration, customer contact burden and assumed economics.

> Compare capacity-limited contact lists and design a controlled term-deposit campaign pilot.

## Practical use case and business outputs

Before a term-deposit campaign, marketing compares a fixed random 20% list with a model-ranked 20% list, reviews expected historical response capture and cost scenarios, and approves a consent-screened randomised pilot rather than deploying historical propensity as proven uplift.

| Deliverable | What the team must hand over | Required contents |
| --- | --- | --- |
| D5 | Campaign population and contact scorecard | Response counts/rate, campaign contact distribution, previous-contact coverage and unknown-category counts; source-row identity and approved chronological partition. |
| D6 | Pre-contact propensity evaluation | Majority/rate baseline and interpretable candidate model; explicit feature-availability audit; precision/recall/lift at 20% test capacity and uncertainty. |
| D7 | Equal-capacity campaign and economics comparison | Random seed-33 list and ranked list, each floor(0.2×N) test records; subscriptions per 1,000 selected contacts and nine stated cost/value scenarios. |
| D8 | Campaign planning dashboard | List-capacity comparison, response capture, contact-burden diagnostics and model/source limitations. |
| D11 | Controlled campaign pilot brief | Pilot arms, eligibility/consent checks, contact-frequency guardrail, randomisation unit, outcome window, sample-size assumptions and stop/review rules. |

## Required success contract

| Success ID | Required deliverable | Specific pass condition |
| --- | --- | --- |
| SC1 | D5 — Campaign population and contact scorecard | All 45,211 source records accounted for; y=yes is positive; pdays=−1 means no previous contact; repeated records are not claimed to be unique customers. |
| SC2 | D6 — Pre-contact propensity evaluation | duration and y never enter predictors; completed last-contact fields excluded from core as specified; no test tuning; report class counts and baseline underperformance. |
| SC3 | D7 — Equal-capacity campaign and economics comparison | Both lists use identical eligible records/capacity; ties use source ID; net-value arithmetic is reproducible and labelled assumed historical response economics, not incremental profit. |
| SC4 | D8 — Campaign planning dashboard | Reviewer changes cost/value assumptions, verifies selected count remains fixed, and traces one selected/deferred case without exposing unnecessary personal fields. |
| SC5 | D11 — Controlled campaign pilot brief | Pilot distinguishes propensity from causal uplift; specifies actual customer IDs and consent evidence needed before operation; no live contact or sales claim. |

[Detailed acceptance](ACCEPTANCE_CRITERIA.md) defines executed evidence; [deliverables](DELIVERABLES.md) defines exact artefacts and ownership. G1 records simulated sponsor approval, not invented real-client agreement.

## Core scope

Use bank-full.csv, all 45,211 records, from the nested bank.zip archive only. Do not stack bank.csv samples or bank-additional variants. Retain original order and categorical unknowns.

Required source: bank.zip → bank-full.csv and bank-names.txt. Model grain: One published campaign record, not an assured unique customer; source-row surrogate ID.

No stable customer ID is available. duration leaks completed-call information and must be excluded from pre-call prioritisation. Historical subscription probability is not incremental campaign uplift; consent, customer vulnerability and actual account profitability are absent.

Additional datasets, live integrations, operational deployment and claims of achieved benefits are outside core. Scope/source changes need approval and updated tests.

## Cross-functional roles

| Role | Required evidence |
| --- | --- |
| Business Analyst / Delivery Lead | Eight numbered prioritised requirements for Compare capacity-limited contact lists and design a controlled term-deposit campaign pilot. As-is/to-be workflow, stakeholder map and requirement→D→AC→DT traceability. |
| Data Governance Analyst | S1 rights, byte manifest, field support, approved cohort and lineage for all seven KPIs; review Using call duration or confusing propensity with causal uplift would create an invalid pre-call business case. |
| Data Engineer | Reproducible ingestion, curated model, source-row ledger and key/join controls at grain: One published campaign record, not an assured unique customer; source-row surrogate ID. |
| Campaign Strategy Analyst | Write the contact-capacity policy and a randomised pilot design with consent screening, contact-frequency guardrails and subscription outcome window. |
| Data Scientist / Decision Modelling Analyst | Baseline/alternative implementation, evaluation manifest, uncertainty and sensitivity. Use first 60%, next 20%, last 20% in published record order, documenting that exact dates and repeated customers cannot be verified. Preserve order; train-only transforms; exclude duration and y. Treat contact/day/month/campaign as planned-context features only with explicit timing assumptions. Core pre-contact model also excludes contact, day, month and campaign unless separately evaluated as a labelled planned-contact scenario; this avoids treating the completed last contact as known before selection. |
| BI / Decision Product Developer | Four views for the outbound campaign planning review: overview, diagnostics, action/policy comparison, quality/limitations. Five independent KPI reconciliations and static export. |
| Marketing Model Assurance Analyst | Execute DT1–DT10, three UAT tasks and a distinct-member clean rerun; record expected/actual evidence, defects and retests. |

Assign named owners and review partners at kickoff. Combine roles only when a distinct member reviews critical calculations and performs final clean rerun. Sponsor labels describe simulated roles, separate from actual team identities.

## Evaluation contract

Use first 60%, next 20%, last 20% in published record order, documenting that exact dates and repeated customers cannot be verified. Preserve order; train-only transforms; exclude duration and y. Treat contact/day/month/campaign as planned-context features only with explicit timing assumptions. Core pre-contact model also excludes contact, day, month and campaign unless separately evaluated as a labelled planned-contact scenario; this avoids treating the completed last contact as known before selection.

Record predictor allowlist, target mapping, timing assumptions, partition/resample IDs and train-only transforms. Report partition/class counts and uncertainty. Negative model results can support a manual/baseline recommendation; invented performance cannot.

## Decision contract

Baseline selects a deterministic random 20% contact list (seed 33). Alternative selects top-scored 20% using a validation-selected model and locked tie rule. Evaluate subscriptions per 1,000 attempted contacts and assumed net value under £1/£3/£5 contact costs and £20/£50/£100 subscription value; all amounts are simulation assumptions.

## Objectives and gates

Deliver D1–D12, K1–K7, AC1–AC12, ten executed domain tests, three UAT tasks, five reconciliations and an independent rerun. The sponsor must trace one action to source and explain why uncertain cases are deferred.

| Gate | Due | Evidence and accountable reviewers |
| --- | --- | --- |
| G1 scope/source | Week 2 | Head of Retail Banking Marketing, BA and Governance approve eight requirements, S1 rights/manifest, actual fields and frozen cohort. Unsupported mandatory outputs block dependent work. |
| G2 engineering/metrics | Week 4 | Engineer, Campaign Strategy Analyst and distinct reviewer approve row accounting, keys/joins, K1–K7, five reconciliations and evaluation manifest. |
| G3 policy | Week 6 | Head of Retail Banking Marketing reviews baseline/alternative, sensitivity, workload, assumptions and one insufficient-evidence/manual-review case. |
| G4 release | Week 8 | Simulated Mettelo panel and Marketing Model Assurance Analyst accept D1–D12, AC1–AC12, ten executed tests, three UAT tasks and clean rerun with zero critical/high defects. |

[Deliverables](DELIVERABLES.md), [acceptance](ACCEPTANCE_CRITERIA.md), [data register](../data/SOURCE_REGISTER.md).

## Team organisation

The recommended team size is **3–5 people**. Delivery roles describe responsibilities, not separate positions: members can combine complementary business analysis, governance, engineering, analysis/modelling, BI and domain responsibilities. Assign a named owner to each deliverable and use a different team member to review critical calculations and perform the final clean rerun.
