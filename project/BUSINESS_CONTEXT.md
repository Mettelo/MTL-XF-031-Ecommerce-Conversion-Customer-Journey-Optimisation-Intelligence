# MTL-XF-031 — Business context

This is a simulated confidential-client engagement using public/open data. Stakeholders and commercial/security scenarios are fictional. Do not claim real-client employment, endorsement, operational deployment or realised benefits. This master pack specifies work to be completed; it does not claim the team has executed it.

## Organisation and problem

Confidential Online Retailer is the fictional organisation. Paid traffic and product-page investment compete for a limited experimentation budget. The growth team cannot distinguish high-volume, low-conversion traffic segments from small unstable groups, and needs an auditable shortlist of journey improvements rather than an unsupported promise of sales uplift.

The Head of Ecommerce Growth needs a monthly conversion opportunity review supporting **Select three segment-specific conversion experiments for product and marketing review.**

## Stakeholders

| Stakeholder | Decision | Required evidence |
| --- | --- | --- |
| Head of Ecommerce Growth | Approve scope, policy assumptions and next investigation/pilot. | D7 policy comparison, D11 recommendations, workload/risk and limitations. |
| Digital Product Analyst | Interpret observations and own action proposals. | K1–K7, source-supported dimensions, sensitivity and case lineage. |
| Data Governance Analyst | Approve source, freeze and interpretation rights. | S1 manifest, licence, actual schema and source-to-output support. |
| Operations / service owner | Accept workload and review/escalation responsibilities. | Action register, eligibility, owners, review dates and override reasons. |
| Growth Assurance Analyst | Challenge correctness and release readiness. | DT1–DT10, UAT, reconciliations and clean rerun. |

## Workflow to improve

Current simulated process: separate extracts/headline totals → informal prioritisation → manual review with limited lineage. This is a teaching scenario, not an observed real client process.

Proposed process: acquire approved bytes → validate/freeze → curate at declared grain → calculate K1–K7 → compare policies → inspect uncertainty/exclusions → sponsor approves investigation/pilot → record disposition and review date. No score bypasses human approval.

## Questions to answer

1. What is the baseline session conversion, and what defines its denominator?
2. Which supported groups/cases account for non-purchase volume, and with what sample support?
3. Which cases change between the baseline and alternative, and why?
4. How do the specified transformation, threshold, cost or capacity alternatives alter the decision?
5. Which recommendations remain unsupported and what evidence must be collected next?

## Decision and action evidence

Baseline ranks TrafficType × VisitorType groups with at least 100 sessions by non-purchase session count. Alternative ranks those same groups by conversion gap below the overall rate, with group sizes and Wilson intervals shown. Recommend at most three experiments; effects remain unmeasured.

Every action record contains case/group key, snapshot, observed measure, eligibility, baseline and alternative rank/policy, evidence link, uncertainty, proposed next step, accountable owner, due/review date, disposition and override rationale. Use source-row IDs; do not invent real customer identities.

## Value and limits

Delivery success is evidence-backed acceptance of D1–D12, not guaranteed model superiority. Benefits remain hypotheses until an approved pilot specifies population, comparator, outcome window and guardrails. D11 includes three next actions and a case where the evidence does not justify action.

Session summaries cannot reconstruct a sequential funnel or prove abandonment at a checkout step. Revenue is a Boolean purchase outcome, not money. PageValues may contain outcome-related information; exclude it from the core model. Completed-session behaviour supports retrospective analysis only, not an at-arrival targeting claim.

**Risk to prevent:** Treating PageValues or end-of-session features as information known at arrival would inflate targeting claims.

**Source boundary:** All 12,330 sessions in the original UCI CSV; one session per distinct user in the publisher's one-year sampling frame. Keep all available months; no invented year, event timestamps or ordered clickstream.

Missing mandatory support blocks G1 or a dependent output until a governed scope/source decision is recorded.
