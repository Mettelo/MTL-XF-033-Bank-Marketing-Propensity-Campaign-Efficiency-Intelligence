# MTL-XF-033 — Business context and practical use case

## Organisation and accountable decision

Confidential Retail Bank is the simulated sponsor. The Head of Retail Banking Marketing owns the outbound campaign planning review and must decide: **Compare capacity-limited contact lists and design a controlled term-deposit campaign pilot.**

## The operational problem

The outbound campaign manager can contact only one fifth of the eligible list in the planning scenario. Selecting customers by a broad demographic profile may waste calls, but selecting on completed-call duration would make a pre-call model look useful using information the caller does not yet know. The bank needs a comparison of contact lists at the same capacity and a transparent view of response concentration, customer contact burden and assumed economics.

## How the finished product will be used

Before a term-deposit campaign, marketing compares a fixed random 20% list with a model-ranked 20% list, reviews expected historical response capture and cost scenarios, and approves a consent-screened randomised pilot rather than deploying historical propensity as proven uplift.

**Current approach:** Build broad lists and judge campaigns mainly by aggregate response.

**Required future approach:** Compare equal-capacity lists using pre-contact information, audit customer-contact assumptions and approve a controlled pilot.

The review starts with a verified frozen population and measured baseline. The domain analyst demonstrates the specified business outputs, the operational owner challenges workload and feasibility, assurance challenges correctness, and the sponsor records accept/defer/override. Each action records a source/configuration reference, rationale, accountable role, next step and review date. Uncertain cases remain in a visible manual-review/defer route.

## Stakeholder responsibilities

| Stakeholder | Responsibility | Decision evidence |
| --- | --- | --- |
| Head of Retail Banking Marketing | Approve scope, project assumptions, acceptance contract and final recommendation. | SC1–SC5 outputs; baseline/alternative trade-offs; pilot/investigation actions. |
| Campaign Strategy Analyst | Write the contact-capacity policy and a randomised pilot design with consent screening, contact-frequency guardrails and subscription outcome window. | Domain scorecard, worked cases, supported interpretation and source lineage. |
| Operational service owner | Accept workload, assignment and escalation route. | Case register, capacity/threshold comparison, due dates and overrides. |
| Data Governance Analyst | Confirm source identity, rights, exact freeze and required fields. | S1 manifest and source→field→measure→deliverable matrix. |
| Marketing Model Assurance Analyst | Approve evidence quality and independently challenge the release. | Executed SC/AC/DT checks, three UAT tasks and rerun. |

## Business questions tied to outputs

1. Can the sponsor use **Campaign population and contact scorecard** to support the stated decision, with this evidence: Response counts/rate, campaign contact distribution, previous-contact coverage and unknown-category counts; source-row identity and approved chronological partition.
2. Can the sponsor use **Pre-contact propensity evaluation** to support the stated decision, with this evidence: Majority/rate baseline and interpretable candidate model; explicit feature-availability audit; precision/recall/lift at 20% test capacity and uncertainty.
3. Can the sponsor use **Equal-capacity campaign and economics comparison** to support the stated decision, with this evidence: Random seed-33 list and ranked list, each floor(0.2×N) test records; subscriptions per 1,000 selected contacts and nine stated cost/value scenarios.
4. Can the sponsor use **Campaign planning dashboard** to support the stated decision, with this evidence: List-capacity comparison, response capture, contact-burden diagnostics and model/source limitations.
5. Can the sponsor use **Controlled campaign pilot brief** to support the stated decision, with this evidence: Pilot arms, eligibility/consent checks, contact-frequency guardrail, randomisation unit, outcome window, sample-size assumptions and stop/review rules.

## Concrete outputs and required success

| Deliverable | What the team must hand over | Required contents |
| --- | --- | --- |
| D5 | Campaign population and contact scorecard | Response counts/rate, campaign contact distribution, previous-contact coverage and unknown-category counts; source-row identity and approved chronological partition. |
| D6 | Pre-contact propensity evaluation | Majority/rate baseline and interpretable candidate model; explicit feature-availability audit; precision/recall/lift at 20% test capacity and uncertainty. |
| D7 | Equal-capacity campaign and economics comparison | Random seed-33 list and ranked list, each floor(0.2×N) test records; subscriptions per 1,000 selected contacts and nine stated cost/value scenarios. |
| D8 | Campaign planning dashboard | List-capacity comparison, response capture, contact-burden diagnostics and model/source limitations. |
| D11 | Controlled campaign pilot brief | Pilot arms, eligibility/consent checks, contact-frequency guardrail, randomisation unit, outcome window, sample-size assumptions and stop/review rules. |

| Success ID | Required deliverable | Specific pass condition |
| --- | --- | --- |
| SC1 | D5 — Campaign population and contact scorecard | All 45,211 source records accounted for; y=yes is positive; pdays=−1 means no previous contact; repeated records are not claimed to be unique customers. |
| SC2 | D6 — Pre-contact propensity evaluation | duration and y never enter predictors; completed last-contact fields excluded from core as specified; no test tuning; report class counts and baseline underperformance. |
| SC3 | D7 — Equal-capacity campaign and economics comparison | Both lists use identical eligible records/capacity; ties use source ID; net-value arithmetic is reproducible and labelled assumed historical response economics, not incremental profit. |
| SC4 | D8 — Campaign planning dashboard | Reviewer changes cost/value assumptions, verifies selected count remains fixed, and traces one selected/deferred case without exposing unnecessary personal fields. |
| SC5 | D11 — Controlled campaign pilot brief | Pilot distinguishes propensity from causal uplift; specifies actual customer IDs and consent evidence needed before operation; no live contact or sales claim. |

## Benefit and adoption boundary

Assessment success means the required outputs are correct, reproducible and usable in the specified review. It does not mean a model must win, a customer must buy, a fault must disappear or a security incident must be prevented. The executive pack must name the measured baseline, alternative, operating trade-off, recommendation and evidence still required for a real pilot. Do not invent commercial savings or success percentages to make the business case appear complete.

At G1 record simulated sponsor approval of the requirements and criteria. At G3 record the policy recommendation and unresolved evidence gaps. At G4 record an actual team reviewer and simulated sponsor role separately; template text is not an approval.

## Source and scope limits

Use bank-full.csv, all 45,211 records, from the nested bank.zip archive only. Do not stack bank.csv samples or bank-additional variants. Retain original order and categorical unknowns.

No stable customer ID is available. duration leaks completed-call information and must be excluded from pre-call prioritisation. Historical subscription probability is not incremental campaign uplift; consent, customer vulnerability and actual account profitability are absent.

**Failure to prevent:** Using call duration or confusing propensity with causal uplift would create an invalid pre-call business case.

Missing mandatory support blocks dependent acceptance until an explicit source/scope decision updates the affected deliverables and tests.

This is a simulated confidential-client engagement using public/open data. Stakeholders and commercial/security scenarios are fictional. Do not claim real-client employment, endorsement, operational deployment or realised benefits. This master pack specifies work to be completed; it does not claim the team has executed it.
