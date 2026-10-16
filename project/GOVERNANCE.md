# MTL-XF-033 — Governance

This is a simulated confidential-client engagement using public/open data. Stakeholders and commercial/security scenarios are fictional. Do not claim real-client employment, endorsement, operational deployment or realised benefits. This master pack specifies work to be completed; it does not claim the team has executed it.

## Accountability and gates

Head of Retail Banking Marketing owns business scope, assumptions and action approval. Governance owns source/rights/freeze; Engineer owns transformations; Campaign Strategy Analyst owns interpretation; Marketing Model Assurance Analyst independently reviews. The simulated Mettelo panel owns programme acceptance. Record actual team members separately from simulated stakeholder roles.

| Gate | Due | Evidence and accountable reviewers |
| --- | --- | --- |
| G1 scope/source | Week 2 | Head of Retail Banking Marketing, BA and Governance approve eight requirements, S1 rights/manifest, actual fields and frozen cohort. Unsupported mandatory outputs block dependent work. |
| G2 engineering/metrics | Week 4 | Engineer, Campaign Strategy Analyst and distinct reviewer approve row accounting, keys/joins, K1–K7, five reconciliations and evaluation manifest. |
| G3 policy | Week 6 | Head of Retail Banking Marketing reviews baseline/alternative, sensitivity, workload, assumptions and one insufficient-evidence/manual-review case. |
| G4 release | Week 8 | Simulated Mettelo panel and Marketing Model Assurance Analyst accept D1–D12, AC1–AC12, ten executed tests, three UAT tasks and clean rerun with zero critical/high defects. |

## Domain controls

No stable customer ID is available. duration leaks completed-call information and must be excluded from pre-call prioritisation. Historical subscription probability is not incremental campaign uplift; consent, customer vulnerability and actual account profitability are absent.

**Primary risk:** Using call duration or confusing propensity with causal uplift would create an invalid pre-call business case.

Baseline selects a deterministic random 20% contact list (seed 33). Alternative selects top-scored 20% using a validation-selected model and locked tie rule. Evaluate subscriptions per 1,000 attempted contacts and assumed net value under £1/£3/£5 contact costs and £20/£50/£100 subscription value; all amounts are simulation assumptions.

All capacity, threshold, financial and review/remediation targets are project assumptions unless explicitly attributed. Human deferrals/overrides record reason, evidence, owner and next review. No production action is authorised by this pack.

## Source and evaluation control

Use bank-full.csv, all 45,211 records, from the nested bank.zip archive only. Do not stack bank.csv samples or bank-additional variants. Retain original order and categorical unknowns.

Follow [S1 register](../data/SOURCE_REGISTER.md); preserve original bytes outside Git, immutable snapshot, manifest and reviewer access. Checksum mismatch stops processing until investigated. Never silently replace a variant/feed. No raw data uploaded by this update.

Use first 60%, next 20%, last 20% in published record order, documenting that exact dates and repeated customers cannot be verified. Preserve order; train-only transforms; exclude duration and y. Treat contact/day/month/campaign as planned-context features only with explicit timing assumptions. Core pre-contact model also excludes contact, day, month and campaign unless separately evaluated as a labelled planned-contact scenario; this avoids treating the completed last contact as known before selection.

Lock target mapping, predictors, timing and policy configuration before test evaluation. Descriptive projects retain resample/sensitivity evidence. Record unsupported metrics and negative findings.

## Change and exception control

Record change ID, requester/date/reason, original/revised source/cohort/requirement, rights/field evidence, affected K/D/AC/DT, time/risk impact, owner, reviewer and decision. New inputs get new freeze IDs and affected checks rerun. Missing mandatory support blocks dependent work.

Each operational exception needs case, rationale, evidence, accountable owner, approval, compensating/manual control, expiry and next review; expired exceptions return to review.

Use only approved public data and fictional operational assumptions. Avoid unnecessary customer identifiers and unsupported protected-characteristic inference.

## Publication and release

Keep attribution, snapshot and limitations in every portfolio/dashboard/slide export. No secrets or private correspondence. Release after all AC/DT/UAT and rerun evidence passes with zero critical/high defects. Record final commit/tag and rollback to approved snapshot/configuration.

## Business acceptance and approval record

The specific use case is: Before a term-deposit campaign, marketing compares a fixed random 20% list with a model-ranked 20% list, reviews expected historical response capture and cost scenarios, and approves a consent-screened randomised pilot rather than deploying historical propensity as proven uplift.

SC1–SC5 in [acceptance](ACCEPTANCE_CRITERIA.md) govern the five concrete business outputs. G1 records criterion, version, actual team approver, simulated sponsor role, date and assumptions. G3 records measured baseline/alternative, decision and trade-off. G4 records executed pass evidence for each SC; a document's existence is insufficient. Never describe simulated sign-off or unmeasured benefits as real-client agreement or adoption.
