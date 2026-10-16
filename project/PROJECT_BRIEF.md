# MTL-XF-031 — Project brief

This is a simulated confidential-client engagement using public/open data. Stakeholders and commercial/security scenarios are fictional. Do not claim real-client employment, endorsement, operational deployment or realised benefits. This master pack specifies work to be completed; it does not claim the team has executed it.

**Client:** Confidential Online Retailer · **Sponsor:** Head of Ecommerce Growth · **Team:** 6–8 · **Duration:** 8 weeks · **Cycle:** monthly conversion opportunity review

## Problem and commission

Paid traffic and product-page investment compete for a limited experimentation budget. The growth team cannot distinguish high-volume, low-conversion traffic segments from small unstable groups, and needs an auditable shortlist of journey improvements rather than an unsupported promise of sales uplift.

> Select three segment-specific conversion experiments for product and marketing review.

## Core scope

All 12,330 sessions in the original UCI CSV; one session per distinct user in the publisher's one-year sampling frame. Keep all available months; no invented year, event timestamps or ordered clickstream.

Required source: online_shoppers_intention.csv. Model grain: One source session; immutable row number plus input SHA-256 is the surrogate key.

Session summaries cannot reconstruct a sequential funnel or prove abandonment at a checkout step. Revenue is a Boolean purchase outcome, not money. PageValues may contain outcome-related information; exclude it from the core model. Completed-session behaviour supports retrospective analysis only, not an at-arrival targeting claim.

Additional datasets, live integrations, operational deployment and claims of achieved benefits are outside core. Scope/source changes need approval and updated tests.

## Cross-functional roles

| Role | Required evidence |
| --- | --- |
| Business Analyst / Delivery Lead | Eight numbered prioritised requirements for Select three segment-specific conversion experiments for product and marketing review. As-is/to-be workflow, stakeholder map and requirement→D→AC→DT traceability. |
| Data Governance Analyst | S1 rights, byte manifest, field support, approved cohort and lineage for all seven KPIs; review Treating PageValues or end-of-session features as information known at arrival would inflate targeting claims. |
| Data Engineer | Reproducible ingestion, curated model, source-row ledger and key/join controls at grain: One source session; immutable row number plus input SHA-256 is the surrogate key. |
| Digital Product Analyst | Own session-summary interpretation and write three experiment cards with hypothesis, audience, primary conversion metric, guardrail and stop/review rule. |
| Data Scientist / Decision Modelling Analyst | Baseline/alternative implementation, evaluation manifest, uncertainty and sensitivity. Stratified 60/20/20 train/validation/test, seed 31, with exact duplicate feature groups kept together. Fit preprocessing on train only. Exclude Revenue and PageValues from predictors; document which remaining features would be unavailable at any proposed live decision time. |
| BI / Decision Product Developer | Four views for the monthly conversion opportunity review: overview, diagnostics, action/policy comparison, quality/limitations. Five independent KPI reconciliations and static export. |
| Growth Assurance Analyst | Execute DT1–DT10, three UAT tasks and a distinct-member clean rerun; record expected/actual evidence, defects and retests. |

Assign named owners and review partners at kickoff. Combine roles only when a distinct member reviews critical calculations and performs final clean rerun. Sponsor labels describe simulated roles, separate from actual team identities.

## Evaluation contract

Stratified 60/20/20 train/validation/test, seed 31, with exact duplicate feature groups kept together. Fit preprocessing on train only. Exclude Revenue and PageValues from predictors; document which remaining features would be unavailable at any proposed live decision time.

Record predictor allowlist, target mapping, timing assumptions, partition/resample IDs and train-only transforms. Report partition/class counts and uncertainty. Negative model results can support a manual/baseline recommendation; invented performance cannot.

## Decision contract

Baseline ranks TrafficType × VisitorType groups with at least 100 sessions by non-purchase session count. Alternative ranks those same groups by conversion gap below the overall rate, with group sizes and Wilson intervals shown. Recommend at most three experiments; effects remain unmeasured.

## Objectives and gates

Deliver D1–D12, K1–K7, AC1–AC12, ten executed domain tests, three UAT tasks, five reconciliations and an independent rerun. The sponsor must trace one action to source and explain why uncertain cases are deferred.

| Gate | Due | Evidence and accountable reviewers |
| --- | --- | --- |
| G1 scope/source | Week 2 | Head of Ecommerce Growth, BA and Governance approve eight requirements, S1 rights/manifest, actual fields and frozen cohort. Unsupported mandatory outputs block dependent work. |
| G2 engineering/metrics | Week 4 | Engineer, Digital Product Analyst and distinct reviewer approve row accounting, keys/joins, K1–K7, five reconciliations and evaluation manifest. |
| G3 policy | Week 6 | Head of Ecommerce Growth reviews baseline/alternative, sensitivity, workload, assumptions and one insufficient-evidence/manual-review case. |
| G4 release | Week 8 | Simulated Mettelo panel and Growth Assurance Analyst accept D1–D12, AC1–AC12, ten executed tests, three UAT tasks and clean rerun with zero critical/high defects. |

[Deliverables](DELIVERABLES.md), [acceptance](ACCEPTANCE_CRITERIA.md), [data register](../data/SOURCE_REGISTER.md).
