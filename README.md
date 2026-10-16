# MTL-XF-031 — Ecommerce Conversion Customer Journey Optimisation Intelligence

**Track:** Cross-Functional · **Sector:** Private-sector commercial operations · **Team:** 3–5 · **Duration:** 8 weeks

## The business problem

The retailer's growth team must choose its next three product and acquisition experiments. Marketing sees traffic-source totals, while product managers see page-engagement summaries; neither view shows which sufficiently large visitor groups combine weak purchase conversion with meaningful session volume. A high non-purchase count can reflect scale, while a low conversion rate can reflect a small or seasonal group. Spending the next development sprint against the wrong signal risks consuming experiment capacity without a defensible hypothesis.

**Simulated organisation:** Confidential Online Retailer. **Accountable decision owner:** Head of Ecommerce Growth.

## Practical use case

At the monthly growth meeting, the Head of Ecommerce Growth filters TrafficType and VisitorType, checks conversion, sample size and uncertainty, compares two priority lists, and assigns up to three experiment hypotheses to product or marketing owners. The analyst provides the evidence and measurement design; the meeting decides what to test.

**Decision the project must enable:** Select three segment-specific conversion experiments for product and marketing review.

**Current approach:** Select ideas from headline traffic and engagement reports without a consistent eligibility rule.

**Required future approach:** Review one reproducible segment scorecard, compare volume-led and conversion-gap priorities, and approve evidence-backed experiment cards.

## Specific deliverables

| Deliverable | What the team must hand over | Required contents |
| --- | --- | --- |
| D5 | Segment conversion scorecard | One row per TrafficType × VisitorType; sessions, purchases, non-purchases, conversion %, Wilson interval, overall comparator, gap in percentage points, month distribution and n≥100 eligibility flag. |
| D6 | Conversion driver and leakage assessment | Descriptive association report plus baseline/model comparison using the approved holdout; show PageValues exclusion, feature timing, PR performance and precision/recall at the locked threshold. |
| D7 | Two ranked opportunity lists | Baseline top ten by non-purchase volume and alternative top ten by conversion shortfall within the identical eligible segment population; include overlap, rank changes and reasons. |
| D8 | Growth meeting dashboard | Views for commercial overview, eligible segment comparison, month/visitor diagnostics and evidence quality; user can trace a segment to the action register. |
| D11 | Three experiment decision cards | Exactly three proposals, or fewer with explicit evidence-based deferral; each names segment, hypothesis, owner role, change to test, randomisation unit, purchase outcome, guardrail, sample-size inputs and stop/review rule. |

These five business outputs sit inside the full D1–D12 engagement. The team also delivers requirements/process mapping, source governance, engineering and quality evidence, independent UAT, handover and contribution records. [Detailed deliverable specifications](project/DELIVERABLES.md) define owners, artefact paths, fields, calculations and review evidence.

## Required success criteria

| Success ID | Required deliverable | Specific pass condition |
| --- | --- | --- |
| SC1 | D5 — Segment conversion scorecard | Every retained session belongs to exactly one scorecard row; segment counts reconcile to cohort totals; groups below 100 are visible but unranked; 1 purchase/4 sessions=25%. |
| SC2 | D6 — Conversion driver and leakage assessment | Publish partition counts and exact predictor list; no PageValues/Revenue predictors; report holdout results even when baseline wins; describe end-of-session signals as retrospective. |
| SC3 | D7 — Two ranked opportunity lists | Deterministic ties use TrafficType then VisitorType; every list row links its scorecard; include at least one excluded/deferred segment and explain why. |
| SC4 | D8 — Growth meeting dashboard | A reviewer completes three tasks: find largest eligible non-purchase segment, compare its gap/interval, and identify its proposed experiment; all values match the scorecard. |
| SC5 | D11 — Three experiment decision cards | Every selected segment has ≥100 observed sessions and cited evidence; calculate sample-size needs from declared baseline/MDE/power assumptions; no realised uplift or ordered-checkout-funnel claim. |

These are assessment requirements, not claims that results have already been achieved. At G1 the team records simulated stakeholder approval of scope, policy assumptions and criteria; later changes require a decision log. Financial benefit, causal uplift, production safety and operational adoption need separate pilot evidence. [Acceptance and worked tests](project/ACCEPTANCE_CRITERIA.md) control pass/fail.

## Data and fixed analytical boundary

**Official source:** [Online Shoppers Purchasing Intention](https://archive.ics.uci.edu/dataset/468). **Required input:** online_shoppers_intention.csv. **Expected source population:** 12,330 sessions.

All 12,330 sessions in the original UCI CSV; one session per distinct user in the publisher's one-year sampling frame. Keep all available months; no invented year, event timestamps or ordered clickstream.

**Download:** https://archive.ics.uci.edu/static/public/468/online+shoppers+purchasing+intention+dataset.zip

Session summaries cannot reconstruct a sequential funnel or prove abandonment at a checkout step. Revenue is a Boolean purchase outcome, not money. PageValues may contain outcome-related information; exclude it from the core model. Completed-session behaviour supports retrospective analysis only, not an at-arrival targeting claim.

The [source register](data/SOURCE_REGISTER.md) records checked hashes, exact acquisition and snapshot rules. No raw data are uploaded; teams retain immutable originals outside Git with a manifest and reviewer access.

## Analysis and decision rules

Stratified 60/20/20 train/validation/test, seed 31, with exact duplicate feature groups kept together. Fit preprocessing on train only. Exclude Revenue and PageValues from predictors; document which remaining features would be unavailable at any proposed live decision time.

Baseline ranks TrafficType × VisitorType groups with at least 100 sessions by non-purchase session count. Alternative ranks those same groups by conversion gap below the overall rate, with group sizes and Wilson intervals shown. Recommend at most three experiments; effects remain unmeasured.

Report measured baselines and alternatives, sample sizes, uncertainty and failure cases. A weaker model does not justify disguising results: the final recommendation must say whether to retain the baseline, improve the prototype or run a controlled pilot, and cite the evidence.

## Who does what

- Business Analyst / Delivery Lead: eight testable user requirements, process map and decision-to-evidence traceability.
- Data Governance Analyst: source rights, frozen cohort, field support and seven-KPI lineage.
- Data Engineer: reproducible model/pipeline, exact row accounting and key/join checks.
- Digital Product Analyst: Own session-summary interpretation and write three experiment cards with hypothesis, audience, primary conversion metric, guardrail and stop/review rule.
- Data Scientist / Decision Modelling Analyst: baseline/alternative, feature timing, validation and sensitivity.
- BI / Decision Product Developer: the specified decision views, filter reconciliation and static export.
- Growth Assurance Analyst: independent checks, three stakeholder walkthroughs and clean rerun.

Assign named authors and distinct reviewers; combining roles cannot remove independent review.

## Delivery and review

| Gate | Due | Evidence and accountable reviewers |
| --- | --- | --- |
| G1 scope/source | Week 2 | Head of Ecommerce Growth, BA and Governance approve eight requirements, S1 rights/manifest, actual fields and frozen cohort. Unsupported mandatory outputs block dependent work. |
| G2 engineering/metrics | Week 4 | Engineer, Digital Product Analyst and distinct reviewer approve row accounting, keys/joins, K1–K7, five reconciliations and evaluation manifest. |
| G3 policy | Week 6 | Head of Ecommerce Growth reviews baseline/alternative, sensitivity, workload, assumptions and one insufficient-evidence/manual-review case. |
| G4 release | Week 8 | Simulated Mettelo panel and Growth Assurance Analyst accept D1–D12, AC1–AC12, ten executed tests, three UAT tasks and clean rerun with zero critical/high defects. |

## Full master pack

[Project brief](project/PROJECT_BRIEF.md) · [Business context](project/BUSINESS_CONTEXT.md) · [Deliverables](project/DELIVERABLES.md) · [Success criteria and tests](project/ACCEPTANCE_CRITERIA.md) · [Governance](project/GOVERNANCE.md) · [Data guidance](data/README.md) · [Submission](submission/README.md).

This is a simulated confidential-client engagement using public/open data. Stakeholders and commercial/security scenarios are fictional. Do not claim real-client employment, endorsement, operational deployment or realised benefits. This master pack specifies work to be completed; it does not claim the team has executed it.
