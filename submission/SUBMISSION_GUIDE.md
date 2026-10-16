# MTL-XF-031 — Submission guide

## Release sequence

1. Finish D1–D12 and link eight user requirements to D/AC/DT evidence.
2. Confirm S1 frozen manifest, rights/attribution, exact cohort and reviewer storage access.
3. Independently review K1–K7; reconcile K1–K5 in full cohort and one filtered slice against dashboard.
4. Lock policy/evaluation configuration and retain baseline, alternative and sensitivity outputs. Stratified 60/20/20 train/validation/test, seed 31, with exact duplicate feature groups kept together. Fit preprocessing on train only. Exclude Revenue and PageValues from predictors; document which remaining features would be unavailable at any proposed live decision time.
5. Execute ten domain tests and three UAT tasks with expected/actual results, reviewer, defects and retests. Resolve all critical/high defects.
6. A distinct member performs a clean run from approved bytes. Record environment, dependency versions, entry point, elapsed time, K1–K7 and policy membership comparison.
7. Produce 8–12 slides and a 5–10-minute demo with five findings, three next actions and a defer case for Head of Ecommerce Growth.
8. Complete FINAL_SUBMISSION.md, contribution evidence and immutable final commit/tag. Check reviewer access without paid-only dependencies.

## Walkthrough

Answer Select three segment-specific conversion experiments for product and marketing review. Demonstrate headline-to-source lineage, one policy change, one edge case and one unsupported/deferred action. Explain Treating PageValues or end-of-session features as information known at arrival would inflate targeting claims.

Keep assumptions, frozen scope and limitations in exports. No raw upload required; supply verified input access and restoration instructions. Security work remains offline and published examples defanged.

Reviewer records accepted/rework/blocked, date, actual reviewer and simulated sponsor role, unresolved low-severity issues with owners/dates and immutable evidence. A filled template without executed checks is not acceptance; formal scope revisions update affected tests before sign-off.

## Specific business acceptance walkthrough

At the monthly growth meeting, the Head of Ecommerce Growth filters TrafficType and VisitorType, checks conversion, sample size and uncertainty, compares two priority lists, and assigns up to three experiment hypotheses to product or marketing owners. The analyst provides the evidence and measurement design; the meeting decides what to test.

Supply all five named output artefacts in [deliverables](../project/DELIVERABLES.md), execute SC1–SC5 in [acceptance](../project/ACCEPTANCE_CRITERIA.md), and complete their final-submission evidence table. Show actual values/cases, not only screenshots or report headings. Include the G1 simulated-approval record and a final retain-baseline/revise/pilot recommendation tied to measured evidence.
