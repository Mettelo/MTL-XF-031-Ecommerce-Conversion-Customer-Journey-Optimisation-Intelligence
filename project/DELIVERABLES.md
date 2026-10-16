# MTL-XF-031 — Deliverables and metric contracts

**Decision:** Select three segment-specific conversion experiments for product and marketing review.

Required team outputs follow; this master does not claim they are complete. Each item needs a named author, distinct reviewer, version, evidence link and status.

## D1 — Discovery and requirements

**Due:** Week 2 · **Owner:** Business Analyst / Delivery Lead · **Team location:** docs/01-discovery/

Eight user requirements, prioritised by decision value, each with owner and measurable test; stakeholder map and as-is/to-be workflow for monthly conversion opportunity review.

**Pass evidence:** All eight link source support, D/AC/DT and Head of Ecommerce Growth approval.

## D2 — Governed source and freeze

**Due:** Week 2 · **Owner:** Data Governance Analyst · **Team location:** docs/02-data-governance/

S1 provenance, rights, dictionary, storage/restore path and immutable byte manifest. All 12,330 sessions in the original UCI CSV; one session per distinct user in the publisher's one-year sampling frame. Keep all available months; no invented year, event timestamps or ordered clickstream.

**Pass evidence:** Every required file/field is verified and approved; unsupported requirements explicitly block G1.

## D3 — Engineering pipeline and model

**Due:** Week 4 · **Owner:** Data Engineer · **Team location:** src/ and docs/03-data-model/

Versioned ingestion/transformation and curated model. Grain: One source session; immutable row number plus input SHA-256 is the surrogate key. Preserve file/sheet/row lineage and all exclusion reasons.

**Pass evidence:** Input=retained+excluded+quarantined exactly; no unexplained join multiplication; clean-run instructions exist.

## D4 — Quality and exceptions

**Due:** Week 4 · **Owner:** Data Engineer + independent reviewer · **Team location:** docs/04-data-quality/

Profile types, nulls, duplicates, sentinels, labels, units and source support. Address Treating PageValues or end-of-session features as information known at arrival would inflate targeting claims.

**Pass evidence:** Every treatment has affected count, reason, owner and reviewer; no silent row loss or coercion.

## D5 — KPI catalogue and lineage

**Due:** Week 4 · **Owner:** Digital Product Analyst · **Team location:** docs/05-kpi-catalogue/

Implement K1–K7 below with actual source fields, code, valid population, denominator, units, grain, exclusions, owner and worked examples.

**Pass evidence:** All seven reviewed; K1–K5 reconcile independently and in BI on full cohort and one filtered slice.

## D6 — Analysis and evaluation

**Due:** Week 6 · **Owner:** Data Scientist / Decision Modelling Analyst · **Team location:** docs/06-analysis/

Stratified 60/20/20 train/validation/test, seed 31, with exact duplicate feature groups kept together. Fit preprocessing on train only. Exclude Revenue and PageValues from predictors; document which remaining features would be unavailable at any proposed live decision time.

**Pass evidence:** Baseline and alternative results, population/class counts, uncertainty, negative findings and feature/timing audit retained; no test-driven tuning.

## D7 — Decision policy and action register

**Due:** Week 6 · **Owner:** Digital Product Analyst · **Team location:** docs/07-decision-framework/

Baseline ranks TrafficType × VisitorType groups with at least 100 sessions by non-purchase session count. Alternative ranks those same groups by conversion gap below the overall rate, with group sizes and Wilson intervals shown. Recommend at most three experiments; effects remain unmeasured.

**Pass evidence:** Both policies and sensitivity outputs supplied; every action has evidence, eligibility, owner, next review and uncertainty. Include a defer case.

## D8 — Dashboard / decision prototype

**Due:** Week 7 · **Owner:** BI / Decision Product Developer · **Team location:** dashboard/

Four linked views: K1–K7 executive overview, source-supported diagnostics, policy/action comparison and quality/limitations for Head of Ecommerce Growth.

**Pass evidence:** Five metric/filter checks pass; frozen scope and limitations survive export; static copy/user guide require no paid access.

## D9 — Independent assurance and UAT

**Due:** Week 7 · **Owner:** Growth Assurance Analyst · **Team location:** docs/08-assurance-uat/

Execute DT1–DT10 and three stakeholder tasks; record actual results and defects/retests.

**Pass evidence:** All ten tests and three tasks pass; zero unresolved critical/high defects.

## D10 — Technical/operational handover

**Due:** Week 8 · **Owner:** Engineer + Delivery Lead · **Team location:** docs/09-technical-handover/

One documented run entry point, dependency versions, manifest, output checksums/tolerances, refresh, rollback and operational owner.

**Pass evidence:** Second member reproduces all seven KPIs and policy queue from approved bytes; environment, elapsed time and discrepancies recorded.

## D11 — Executive recommendation

**Due:** Week 8 · **Owner:** Delivery Lead + domain specialist · **Team location:** deliverables/

8–12 slides and a 5–10-minute demo answering Select three segment-specific conversion experiments for product and marketing review. Include five evidence-linked findings, three next actions, comparison and a defer case.

**Pass evidence:** Every numeric claim links tested evidence; costs/benefits and operational targets are labelled assumptions unless measured.

## D12 — Contribution and final submission

**Due:** Weekly; final week 8 · **Owner:** Delivery Lead · **Team location:** CONTRIBUTIONS.md and submission/FINAL_SUBMISSION.md

Named D owners/reviewers, authored work, issues/PRs/commits, substantive reviews and demo/handover contribution for each member.

**Pass evidence:** All D/AC/DT evidence links resolve at final commit/tag; individual contribution is demonstrated beyond bulk upload or commit count.

## K1–K7 — Authoritative contracts

| ID | Metric | Definition and population | Grain |
| --- | --- | --- | --- |
| K1 | Session conversion | count(Revenue=True) / valid labelled sessions; show denominator and Wilson 95% interval. | TrafficType × VisitorType and overall |
| K2 | Non-purchase volume | count(Revenue=False); do not label this lost revenue. | same eligible session groups |
| K3 | Conversion gap | 100 × (group conversion − overall conversion), percentage points. | groups with n≥100 |
| K4 | Product engagement | median ProductRelated_Duration seconds with zero-duration share shown. | VisitorType |
| K5 | Bounce signal | mean published BounceRates; not a reconstructed session bounce count. | TrafficType |
| K6 | Model precision/recall | TP/(TP+FP) and TP/(TP+FN), positive=purchase, at validation-locked threshold. | untouched test |
| K7 | Top-quintile lift | test purchase rate in top 20% scores / overall test purchase rate; deterministic tie rule. | test only |

Extend each contract with actual S1 raw fields and curated columns, code lineage, population/exclusions, numerator/denominator, units/grain, aggregation, missing/zero/undefined policy, owner/reviewer, freeze ID and tests. Digital Product Analyst owns interpretation; Engineer implements; Growth Assurance Analyst reviews.

Zero denominators produce unavailable values with reasons. Do not average subgroup rates when compatible summed numerators/denominators are required. Show class/segment counts beside rates and uncertainty. Counts reconcile exactly; arithmetic reconciles unrounded or to a documented tolerance no wider than 0.01 displayed unit. No source field can silently be replaced by an assumption.

## Evaluation and decision policy

Stratified 60/20/20 train/validation/test, seed 31, with exact duplicate feature groups kept together. Fit preprocessing on train only. Exclude Revenue and PageValues from predictors; document which remaining features would be unavailable at any proposed live decision time.

Baseline ranks TrafficType × VisitorType groups with at least 100 sessions by non-purchase session count. Alternative ranks those same groups by conversion gap below the overall rate, with group sizes and Wilson intervals shown. Recommend at most three experiments; effects remain unmeasured.

**Interpretation boundary:** Session summaries cannot reconstruct a sequential funnel or prove abandonment at a checkout step. Revenue is a Boolean purchase outcome, not money. PageValues may contain outcome-related information; exclude it from the core model. Completed-session behaviour supports retrospective analysis only, not an at-arrival targeting claim.

See [acceptance](ACCEPTANCE_CRITERIA.md) for tests and [governance](GOVERNANCE.md) for release decisions.
