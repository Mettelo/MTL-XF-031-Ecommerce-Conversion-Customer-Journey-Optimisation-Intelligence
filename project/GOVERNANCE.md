# MTL-XF-031 — Governance

This is a simulated confidential-client engagement using public/open data. Stakeholders and commercial/security scenarios are fictional. Do not claim real-client employment, endorsement, operational deployment or realised benefits. This master pack specifies work to be completed; it does not claim the team has executed it.

## Accountability and gates

Head of Ecommerce Growth owns business scope, assumptions and action approval. Governance owns source/rights/freeze; Engineer owns transformations; Digital Product Analyst owns interpretation; Growth Assurance Analyst independently reviews. The simulated Mettelo panel owns programme acceptance. Record actual team members separately from simulated stakeholder roles.

| Gate | Due | Evidence and accountable reviewers |
| --- | --- | --- |
| G1 scope/source | Week 2 | Head of Ecommerce Growth, BA and Governance approve eight requirements, S1 rights/manifest, actual fields and frozen cohort. Unsupported mandatory outputs block dependent work. |
| G2 engineering/metrics | Week 4 | Engineer, Digital Product Analyst and distinct reviewer approve row accounting, keys/joins, K1–K7, five reconciliations and evaluation manifest. |
| G3 policy | Week 6 | Head of Ecommerce Growth reviews baseline/alternative, sensitivity, workload, assumptions and one insufficient-evidence/manual-review case. |
| G4 release | Week 8 | Simulated Mettelo panel and Growth Assurance Analyst accept D1–D12, AC1–AC12, ten executed tests, three UAT tasks and clean rerun with zero critical/high defects. |

## Domain controls

Session summaries cannot reconstruct a sequential funnel or prove abandonment at a checkout step. Revenue is a Boolean purchase outcome, not money. PageValues may contain outcome-related information; exclude it from the core model. Completed-session behaviour supports retrospective analysis only, not an at-arrival targeting claim.

**Primary risk:** Treating PageValues or end-of-session features as information known at arrival would inflate targeting claims.

Baseline ranks TrafficType × VisitorType groups with at least 100 sessions by non-purchase session count. Alternative ranks those same groups by conversion gap below the overall rate, with group sizes and Wilson intervals shown. Recommend at most three experiments; effects remain unmeasured.

All capacity, threshold, financial and review/remediation targets are project assumptions unless explicitly attributed. Human deferrals/overrides record reason, evidence, owner and next review. No production action is authorised by this pack.

## Source and evaluation control

All 12,330 sessions in the original UCI CSV; one session per distinct user in the publisher's one-year sampling frame. Keep all available months; no invented year, event timestamps or ordered clickstream.

Follow [S1 register](../data/SOURCE_REGISTER.md); preserve original bytes outside Git, immutable snapshot, manifest and reviewer access. Checksum mismatch stops processing until investigated. Never silently replace a variant/feed. No raw data uploaded by this update.

Stratified 60/20/20 train/validation/test, seed 31, with exact duplicate feature groups kept together. Fit preprocessing on train only. Exclude Revenue and PageValues from predictors; document which remaining features would be unavailable at any proposed live decision time.

Lock target mapping, predictors, timing and policy configuration before test evaluation. Descriptive projects retain resample/sensitivity evidence. Record unsupported metrics and negative findings.

## Change and exception control

Record change ID, requester/date/reason, original/revised source/cohort/requirement, rights/field evidence, affected K/D/AC/DT, time/risk impact, owner, reviewer and decision. New inputs get new freeze IDs and affected checks rerun. Missing mandatory support blocks dependent work.

Each operational exception needs case, rationale, evidence, accountable owner, approval, compensating/manual control, expiry and next review; expired exceptions return to review.

Use only approved public data and fictional operational assumptions. Avoid unnecessary customer identifiers and unsupported protected-characteristic inference.

## Publication and release

Keep attribution, snapshot and limitations in every portfolio/dashboard/slide export. No secrets or private correspondence. Release after all AC/DT/UAT and rerun evidence passes with zero critical/high defects. Record final commit/tag and rollback to approved snapshot/configuration.
