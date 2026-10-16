# MTL-XF-031 — Acceptance and domain tests

Acceptance requires executed evidence, not headings. Growth Assurance Analyst records state, actual result, evidence/commit, date, author, reviewer and defect/retest reference. Templates start NOT RUN.

## AC1–AC12

| Criterion | Output | Measurable pass condition |
| --- | --- | --- |
| AC1 | D1 | All eight link source support, D/AC/DT and Head of Ecommerce Growth approval. |
| AC2 | D2 | Every required file/field is verified and approved; unsupported requirements explicitly block G1. |
| AC3 | D3 | Input=retained+excluded+quarantined exactly; no unexplained join multiplication; clean-run instructions exist. |
| AC4 | D4 | Every treatment has affected count, reason, owner and reviewer; no silent row loss or coercion. |
| AC5 | D5 / SC1 | Every retained session belongs to exactly one scorecard row; segment counts reconcile to cohort totals; groups below 100 are visible but unranked; 1 purchase/4 sessions=25%. |
| AC6 | D6 / SC2 | Publish partition counts and exact predictor list; no PageValues/Revenue predictors; report holdout results even when baseline wins; describe end-of-session signals as retrospective. |
| AC7 | D7 / SC3 | Deterministic ties use TrafficType then VisitorType; every list row links its scorecard; include at least one excluded/deferred segment and explain why. |
| AC8 | D8 / SC4 | A reviewer completes three tasks: find largest eligible non-purchase segment, compare its gap/interval, and identify its proposed experiment; all values match the scorecard. |
| AC9 | D9 | All ten tests and three tasks pass; zero unresolved critical/high defects. |
| AC10 | D10 | Second member reproduces all seven KPIs and policy queue from approved bytes; environment, elapsed time and discrepancies recorded. |
| AC11 | D11 / SC5 | Every selected segment has ≥100 observed sessions and cited evidence; calculate sample-size needs from declared baseline/MDE/power assumptions; no realised uplift or ordered-checkout-funnel claim. |
| AC12 | D12 | All D/AC/DT evidence links resolve at final commit/tag; individual contribution is demonstrated beyond bulk upload or commit count. |

## SC1–SC5 — Business output success contracts

These requirements supplement AC1–AC12 and are mandatory. Record approval at G1, then execute against final outputs. All five require PASS with traceable evidence, or a formally approved scope revision; an unmet model-performance target must be reported as unmet and reflected in the recommendation.

### SC1 / D5 — Segment conversion scorecard

**Accountable delivery role:** Digital Product Analyst. **Business reviewer:** Head of Ecommerce Growth. **Independent assurance:** Growth Assurance Analyst.

**Required artefact:** data/curated/segment-conversion-scorecard.csv and docs/05-kpi-catalogue/segment-conversion-scorecard.md.

**Content:** One row per TrafficType × VisitorType; sessions, purchases, non-purchases, conversion %, Wilson interval, overall comparator, gap in percentage points, month distribution and n≥100 eligibility flag.

**Pass condition:** Every retained session belongs to exactly one scorecard row; segment counts reconcile to cohort totals; groups below 100 are visible but unranked; 1 purchase/4 sessions=25%.

**Evidence to retain:** actual output at final commit, source/configuration lineage, executed expected-versus-actual checks, reviewer identity/date and PASS/FAIL/BLOCKED. Do not mark complete from document presence alone.

### SC2 / D6 — Conversion driver and leakage assessment

**Accountable delivery role:** Data Scientist / Decision Modelling Analyst. **Business reviewer:** Head of Ecommerce Growth. **Independent assurance:** Growth Assurance Analyst.

**Required artefact:** docs/06-analysis/conversion-driver-and-leakage-assessment.md plus machine-readable evaluation_results.csv.

**Content:** Descriptive association report plus baseline/model comparison using the approved holdout; show PageValues exclusion, feature timing, PR performance and precision/recall at the locked threshold.

**Pass condition:** Publish partition counts and exact predictor list; no PageValues/Revenue predictors; report holdout results even when baseline wins; describe end-of-session signals as retrospective.

**Evidence to retain:** actual output at final commit, source/configuration lineage, executed expected-versus-actual checks, reviewer identity/date and PASS/FAIL/BLOCKED. Do not mark complete from document presence alone.

### SC3 / D7 — Two ranked opportunity lists

**Accountable delivery role:** Digital Product Analyst. **Business reviewer:** Head of Ecommerce Growth. **Independent assurance:** Growth Assurance Analyst.

**Required artefact:** docs/07-decision-framework/two-ranked-opportunity-lists.csv plus policy.md.

**Content:** Baseline top ten by non-purchase volume and alternative top ten by conversion shortfall within the identical eligible segment population; include overlap, rank changes and reasons.

**Pass condition:** Deterministic ties use TrafficType then VisitorType; every list row links its scorecard; include at least one excluded/deferred segment and explain why.

**Evidence to retain:** actual output at final commit, source/configuration lineage, executed expected-versus-actual checks, reviewer identity/date and PASS/FAIL/BLOCKED. Do not mark complete from document presence alone.

### SC4 / D8 — Growth meeting dashboard

**Accountable delivery role:** BI / Decision Product Developer. **Business reviewer:** Head of Ecommerce Growth. **Independent assurance:** Growth Assurance Analyst.

**Required artefact:** dashboard/README.md, runnable dashboard/prototype and static review export.

**Content:** Views for commercial overview, eligible segment comparison, month/visitor diagnostics and evidence quality; user can trace a segment to the action register.

**Pass condition:** A reviewer completes three tasks: find largest eligible non-purchase segment, compare its gap/interval, and identify its proposed experiment; all values match the scorecard.

**Evidence to retain:** actual output at final commit, source/configuration lineage, executed expected-versus-actual checks, reviewer identity/date and PASS/FAIL/BLOCKED. Do not mark complete from document presence alone.

### SC5 / D11 — Three experiment decision cards

**Accountable delivery role:** Business Analyst / Delivery Lead with domain specialist. **Business reviewer:** Head of Ecommerce Growth. **Independent assurance:** Growth Assurance Analyst.

**Required artefact:** deliverables/three-experiment-decision-cards.pdf plus editable slides and supporting cards/runbook.

**Content:** Exactly three proposals, or fewer with explicit evidence-based deferral; each names segment, hypothesis, owner role, change to test, randomisation unit, purchase outcome, guardrail, sample-size inputs and stop/review rule.

**Pass condition:** Every selected segment has ≥100 observed sessions and cited evidence; calculate sample-size needs from declared baseline/MDE/power assumptions; no realised uplift or ordered-checkout-funnel claim.

**Evidence to retain:** actual output at final commit, source/configuration lineage, executed expected-versus-actual checks, reviewer identity/date and PASS/FAIL/BLOCKED. Do not mark complete from document presence alone.


## DT1–DT10

| Test | Case | Expected result |
| --- | --- | --- |
| DT1 | Revenue 1/4 | One purchasing session among four valid sessions produces 25% conversion. |
| DT2 | Small segment | A group of 99 sessions is excluded from prioritisation and shown as insufficient support; 100 is eligible. |
| DT3 | PageValues leak | Core predictor list containing PageValues or Revenue fails validation. |
| DT4 | No clickstream | A request for checkout-step conversion is flagged unsupported rather than inferred from page categories. |
| DT5 | Zero purchases | A segment with no purchases reports zero conversion with its nonzero denominator and interval. |
| DT6 | Experiment honesty | Any claimed realised uplift without an experiment fails review. |
| DT7 | Source row accounting | One malformed fixture row is quarantined with source ID/reason; retained+excluded+quarantined equals input with no overlap. |
| DT8 | Missing versus zero | A 0/0 rate is unavailable with reason. Missing source evidence never becomes a measured zero or a fabricated result. |
| DT9 | BI reconciliation | K1–K5 match independent calculations on full cohort and one filtered slice. Counts exact; arithmetic unrounded or tolerance at most 0.01 displayed unit. |
| DT10 | Independent rerun | Distinct member reproduces cohort IDs, K1–K7 and policy selections from frozen bytes/configuration. Any stochastic tolerance is declared before running and discrepancies resolved. |

Use small synthetic fixtures for edge cases and frozen-source checks where relevant. Clearly distinguish fixture results from measured source outputs. Retain expected/actual evidence in docs/08-assurance-uat/; automate deterministic calculations where practical and document UI/interpretation reviews.

## Three project-specific UAT tasks

1. **Business review:** At the monthly growth meeting, the Head of Ecommerce Growth filters TrafficType and VisitorType, checks conversion, sample size and uncertainty, compares two priority lists, and assigns up to three experiment hypotheses to product or marketing owners. The analyst provides the evidence and measurement design; the meeting decides what to test. The participant must explain the observed baseline, population and decision limitation without assistance from the author; record actual completion and any defect.
2. **Policy challenge:** use the D7 artefact to compare a baseline and alternative case, then record accept/defer/override with evidence and accountable owner. The domain reviewer must independently reproduce the case outcome.
3. **Operational walkthrough:** A reviewer completes three tasks: find largest eligible non-purchase segment, compare its gap/interval, and identify its proposed experiment; all values match the scorecard. Retain the task recording/screenshots, expected/actual values and reviewer outcome.

All three must pass after defect retest. Static exports may support review if interactive access is unavailable. The independent reviewer also checks every SC output against its declared artefact and source/configuration lineage.

## Release

All twelve ACs, ten DTs, UAT and independent rerun require evidence with zero unresolved critical/high defects. Underperformance can justify a baseline/manual policy; wrong labels/units, leakage, unregistered data or unsupported operational claims block acceptance. A scope revision updates affected requirements/tests; it cannot mark an unexecuted check passed.
