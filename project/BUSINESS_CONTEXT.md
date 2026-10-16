# MTL-XF-033 — Business context

This is a simulated confidential-client engagement using public/open data. Stakeholders and commercial/security scenarios are fictional. Do not claim real-client employment, endorsement, operational deployment or realised benefits. This master pack specifies work to be completed; it does not claim the team has executed it.

## Organisation and problem

Confidential Retail Bank is the fictional organisation. A bank's outbound team has a fixed contact capacity but relies on broad lists. Historical subscription patterns may improve prioritisation, yet call duration is only known after a call and historical targeting does not establish the effect of contacting a customer.

The Head of Retail Banking Marketing needs a outbound campaign planning review supporting **Compare capacity-limited contact lists and design a controlled term-deposit campaign pilot.**

## Stakeholders

| Stakeholder | Decision | Required evidence |
| --- | --- | --- |
| Head of Retail Banking Marketing | Approve scope, policy assumptions and next investigation/pilot. | D7 policy comparison, D11 recommendations, workload/risk and limitations. |
| Campaign Strategy Analyst | Interpret observations and own action proposals. | K1–K7, source-supported dimensions, sensitivity and case lineage. |
| Data Governance Analyst | Approve source, freeze and interpretation rights. | S1 manifest, licence, actual schema and source-to-output support. |
| Operations / service owner | Accept workload and review/escalation responsibilities. | Action register, eligibility, owners, review dates and override reasons. |
| Marketing Model Assurance Analyst | Challenge correctness and release readiness. | DT1–DT10, UAT, reconciliations and clean rerun. |

## Workflow to improve

Current simulated process: separate extracts/headline totals → informal prioritisation → manual review with limited lineage. This is a teaching scenario, not an observed real client process.

Proposed process: acquire approved bytes → validate/freeze → curate at declared grain → calculate K1–K7 → compare policies → inspect uncertainty/exclusions → sponsor approves investigation/pilot → record disposition and review date. No score bypasses human approval.

## Questions to answer

1. What is the baseline subscription rate, and what defines its denominator?
2. Which supported groups/cases account for contact burden, and with what sample support?
3. Which cases change between the baseline and alternative, and why?
4. How do the specified transformation, threshold, cost or capacity alternatives alter the decision?
5. Which recommendations remain unsupported and what evidence must be collected next?

## Decision and action evidence

Baseline selects a deterministic random 20% contact list (seed 33). Alternative selects top-scored 20% using a validation-selected model and locked tie rule. Evaluate subscriptions per 1,000 attempted contacts and assumed net value under £1/£3/£5 contact costs and £20/£50/£100 subscription value; all amounts are simulation assumptions.

Every action record contains case/group key, snapshot, observed measure, eligibility, baseline and alternative rank/policy, evidence link, uncertainty, proposed next step, accountable owner, due/review date, disposition and override rationale. Use source-row IDs; do not invent real customer identities.

## Value and limits

Delivery success is evidence-backed acceptance of D1–D12, not guaranteed model superiority. Benefits remain hypotheses until an approved pilot specifies population, comparator, outcome window and guardrails. D11 includes three next actions and a case where the evidence does not justify action.

No stable customer ID is available. duration leaks completed-call information and must be excluded from pre-call prioritisation. Historical subscription probability is not incremental campaign uplift; consent, customer vulnerability and actual account profitability are absent.

**Risk to prevent:** Using call duration or confusing propensity with causal uplift would create an invalid pre-call business case.

**Source boundary:** Use bank-full.csv, all 45,211 records, from the nested bank.zip archive only. Do not stack bank.csv samples or bank-additional variants. Retain original order and categorical unknowns.

Missing mandatory support blocks G1 or a dependent output until a governed scope/source decision is recorded.
