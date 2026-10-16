# MTL-XF-033 — Bank Marketing Propensity Campaign Efficiency Intelligence

**Track:** Cross-Functional · **Sector:** Private-sector commercial operations · **Team:** 6–8 · **Duration:** 8 weeks

## The business problem

The outbound campaign manager can contact only one fifth of the eligible list in the planning scenario. Selecting customers by a broad demographic profile may waste calls, but selecting on completed-call duration would make a pre-call model look useful using information the caller does not yet know. The bank needs a comparison of contact lists at the same capacity and a transparent view of response concentration, customer contact burden and assumed economics.

**Simulated organisation:** Confidential Retail Bank. **Accountable decision owner:** Head of Retail Banking Marketing.

## Practical use case

Before a term-deposit campaign, marketing compares a fixed random 20% list with a model-ranked 20% list, reviews expected historical response capture and cost scenarios, and approves a consent-screened randomised pilot rather than deploying historical propensity as proven uplift.

**Decision the project must enable:** Compare capacity-limited contact lists and design a controlled term-deposit campaign pilot.

**Current approach:** Build broad lists and judge campaigns mainly by aggregate response.

**Required future approach:** Compare equal-capacity lists using pre-contact information, audit customer-contact assumptions and approve a controlled pilot.

## Specific deliverables

| Deliverable | What the team must hand over | Required contents |
| --- | --- | --- |
| D5 | Campaign population and contact scorecard | Response counts/rate, campaign contact distribution, previous-contact coverage and unknown-category counts; source-row identity and approved chronological partition. |
| D6 | Pre-contact propensity evaluation | Majority/rate baseline and interpretable candidate model; explicit feature-availability audit; precision/recall/lift at 20% test capacity and uncertainty. |
| D7 | Equal-capacity campaign and economics comparison | Random seed-33 list and ranked list, each floor(0.2×N) test records; subscriptions per 1,000 selected contacts and nine stated cost/value scenarios. |
| D8 | Campaign planning dashboard | List-capacity comparison, response capture, contact-burden diagnostics and model/source limitations. |
| D11 | Controlled campaign pilot brief | Pilot arms, eligibility/consent checks, contact-frequency guardrail, randomisation unit, outcome window, sample-size assumptions and stop/review rules. |

These five business outputs sit inside the full D1–D12 engagement. The team also delivers requirements/process mapping, source governance, engineering and quality evidence, independent UAT, handover and contribution records. [Detailed deliverable specifications](project/DELIVERABLES.md) define owners, artefact paths, fields, calculations and review evidence.

## Required success criteria

| Success ID | Required deliverable | Specific pass condition |
| --- | --- | --- |
| SC1 | D5 — Campaign population and contact scorecard | All 45,211 source records accounted for; y=yes is positive; pdays=−1 means no previous contact; repeated records are not claimed to be unique customers. |
| SC2 | D6 — Pre-contact propensity evaluation | duration and y never enter predictors; completed last-contact fields excluded from core as specified; no test tuning; report class counts and baseline underperformance. |
| SC3 | D7 — Equal-capacity campaign and economics comparison | Both lists use identical eligible records/capacity; ties use source ID; net-value arithmetic is reproducible and labelled assumed historical response economics, not incremental profit. |
| SC4 | D8 — Campaign planning dashboard | Reviewer changes cost/value assumptions, verifies selected count remains fixed, and traces one selected/deferred case without exposing unnecessary personal fields. |
| SC5 | D11 — Controlled campaign pilot brief | Pilot distinguishes propensity from causal uplift; specifies actual customer IDs and consent evidence needed before operation; no live contact or sales claim. |

These are assessment requirements, not claims that results have already been achieved. At G1 the team records simulated stakeholder approval of scope, policy assumptions and criteria; later changes require a decision log. Financial benefit, causal uplift, production safety and operational adoption need separate pilot evidence. [Acceptance and worked tests](project/ACCEPTANCE_CRITERIA.md) control pass/fail.

## Data and fixed analytical boundary

**Official source:** [Bank Marketing](https://archive.ics.uci.edu/dataset/222). **Required input:** bank.zip → bank-full.csv and bank-names.txt. **Expected source population:** 45,211 records in bank-full.csv.

Use bank-full.csv, all 45,211 records, from the nested bank.zip archive only. Do not stack bank.csv samples or bank-additional variants. Retain original order and categorical unknowns.

**Download:** https://archive.ics.uci.edu/static/public/222/bank+marketing.zip

No stable customer ID is available. duration leaks completed-call information and must be excluded from pre-call prioritisation. Historical subscription probability is not incremental campaign uplift; consent, customer vulnerability and actual account profitability are absent.

The [source register](data/SOURCE_REGISTER.md) records checked hashes, exact acquisition and snapshot rules. No raw data are uploaded; teams retain immutable originals outside Git with a manifest and reviewer access.

## Analysis and decision rules

Use first 60%, next 20%, last 20% in published record order, documenting that exact dates and repeated customers cannot be verified. Preserve order; train-only transforms; exclude duration and y. Treat contact/day/month/campaign as planned-context features only with explicit timing assumptions. Core pre-contact model also excludes contact, day, month and campaign unless separately evaluated as a labelled planned-contact scenario; this avoids treating the completed last contact as known before selection.

Baseline selects a deterministic random 20% contact list (seed 33). Alternative selects top-scored 20% using a validation-selected model and locked tie rule. Evaluate subscriptions per 1,000 attempted contacts and assumed net value under £1/£3/£5 contact costs and £20/£50/£100 subscription value; all amounts are simulation assumptions.

Report measured baselines and alternatives, sample sizes, uncertainty and failure cases. A weaker model does not justify disguising results: the final recommendation must say whether to retain the baseline, improve the prototype or run a controlled pilot, and cite the evidence.

## Who does what

- Business Analyst / Delivery Lead: eight testable user requirements, process map and decision-to-evidence traceability.
- Data Governance Analyst: source rights, frozen cohort, field support and seven-KPI lineage.
- Data Engineer: reproducible model/pipeline, exact row accounting and key/join checks.
- Campaign Strategy Analyst: Write the contact-capacity policy and a randomised pilot design with consent screening, contact-frequency guardrails and subscription outcome window.
- Data Scientist / Decision Modelling Analyst: baseline/alternative, feature timing, validation and sensitivity.
- BI / Decision Product Developer: the specified decision views, filter reconciliation and static export.
- Marketing Model Assurance Analyst: independent checks, three stakeholder walkthroughs and clean rerun.

Assign named authors and distinct reviewers; combining roles cannot remove independent review.

## Delivery and review

| Gate | Due | Evidence and accountable reviewers |
| --- | --- | --- |
| G1 scope/source | Week 2 | Head of Retail Banking Marketing, BA and Governance approve eight requirements, S1 rights/manifest, actual fields and frozen cohort. Unsupported mandatory outputs block dependent work. |
| G2 engineering/metrics | Week 4 | Engineer, Campaign Strategy Analyst and distinct reviewer approve row accounting, keys/joins, K1–K7, five reconciliations and evaluation manifest. |
| G3 policy | Week 6 | Head of Retail Banking Marketing reviews baseline/alternative, sensitivity, workload, assumptions and one insufficient-evidence/manual-review case. |
| G4 release | Week 8 | Simulated Mettelo panel and Marketing Model Assurance Analyst accept D1–D12, AC1–AC12, ten executed tests, three UAT tasks and clean rerun with zero critical/high defects. |

## Full master pack

[Project brief](project/PROJECT_BRIEF.md) · [Business context](project/BUSINESS_CONTEXT.md) · [Deliverables](project/DELIVERABLES.md) · [Success criteria and tests](project/ACCEPTANCE_CRITERIA.md) · [Governance](project/GOVERNANCE.md) · [Data guidance](data/README.md) · [Submission](submission/README.md).

This is a simulated confidential-client engagement using public/open data. Stakeholders and commercial/security scenarios are fictional. Do not claim real-client employment, endorsement, operational deployment or realised benefits. This master pack specifies work to be completed; it does not claim the team has executed it.
