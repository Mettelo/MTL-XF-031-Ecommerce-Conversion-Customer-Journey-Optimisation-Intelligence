# MTL-XF-031 — Business context and practical use case

## Organisation and accountable decision

Confidential Online Retailer is the simulated sponsor. The Head of Ecommerce Growth owns the monthly conversion opportunity review and must decide: **Select three segment-specific conversion experiments for product and marketing review.**

## The operational problem

The retailer's growth team must choose its next three product and acquisition experiments. Marketing sees traffic-source totals, while product managers see page-engagement summaries; neither view shows which sufficiently large visitor groups combine weak purchase conversion with meaningful session volume. A high non-purchase count can reflect scale, while a low conversion rate can reflect a small or seasonal group. Spending the next development sprint against the wrong signal risks consuming experiment capacity without a defensible hypothesis.

## How the finished product will be used

At the monthly growth meeting, the Head of Ecommerce Growth filters TrafficType and VisitorType, checks conversion, sample size and uncertainty, compares two priority lists, and assigns up to three experiment hypotheses to product or marketing owners. The analyst provides the evidence and measurement design; the meeting decides what to test.

**Current approach:** Select ideas from headline traffic and engagement reports without a consistent eligibility rule.

**Required future approach:** Review one reproducible segment scorecard, compare volume-led and conversion-gap priorities, and approve evidence-backed experiment cards.

The review starts with a verified frozen population and measured baseline. The domain analyst demonstrates the specified business outputs, the operational owner challenges workload and feasibility, assurance challenges correctness, and the sponsor records accept/defer/override. Each action records a source/configuration reference, rationale, accountable role, next step and review date. Uncertain cases remain in a visible manual-review/defer route.

## Stakeholder responsibilities

| Stakeholder | Responsibility | Decision evidence |
| --- | --- | --- |
| Head of Ecommerce Growth | Approve scope, project assumptions, acceptance contract and final recommendation. | SC1–SC5 outputs; baseline/alternative trade-offs; pilot/investigation actions. |
| Digital Product Analyst | Own session-summary interpretation and write three experiment cards with hypothesis, audience, primary conversion metric, guardrail and stop/review rule. | Domain scorecard, worked cases, supported interpretation and source lineage. |
| Operational service owner | Accept workload, assignment and escalation route. | Case register, capacity/threshold comparison, due dates and overrides. |
| Data Governance Analyst | Confirm source identity, rights, exact freeze and required fields. | S1 manifest and source→field→measure→deliverable matrix. |
| Growth Assurance Analyst | Approve evidence quality and independently challenge the release. | Executed SC/AC/DT checks, three UAT tasks and rerun. |

## Business questions tied to outputs

1. Can the sponsor use **Segment conversion scorecard** to support the stated decision, with this evidence: One row per TrafficType × VisitorType; sessions, purchases, non-purchases, conversion %, Wilson interval, overall comparator, gap in percentage points, month distribution and n≥100 eligibility flag.
2. Can the sponsor use **Conversion driver and leakage assessment** to support the stated decision, with this evidence: Descriptive association report plus baseline/model comparison using the approved holdout; show PageValues exclusion, feature timing, PR performance and precision/recall at the locked threshold.
3. Can the sponsor use **Two ranked opportunity lists** to support the stated decision, with this evidence: Baseline top ten by non-purchase volume and alternative top ten by conversion shortfall within the identical eligible segment population; include overlap, rank changes and reasons.
4. Can the sponsor use **Growth meeting dashboard** to support the stated decision, with this evidence: Views for commercial overview, eligible segment comparison, month/visitor diagnostics and evidence quality; user can trace a segment to the action register.
5. Can the sponsor use **Three experiment decision cards** to support the stated decision, with this evidence: Exactly three proposals, or fewer with explicit evidence-based deferral; each names segment, hypothesis, owner role, change to test, randomisation unit, purchase outcome, guardrail, sample-size inputs and stop/review rule.

## Concrete outputs and required success

| Deliverable | What the team must hand over | Required contents |
| --- | --- | --- |
| D5 | Segment conversion scorecard | One row per TrafficType × VisitorType; sessions, purchases, non-purchases, conversion %, Wilson interval, overall comparator, gap in percentage points, month distribution and n≥100 eligibility flag. |
| D6 | Conversion driver and leakage assessment | Descriptive association report plus baseline/model comparison using the approved holdout; show PageValues exclusion, feature timing, PR performance and precision/recall at the locked threshold. |
| D7 | Two ranked opportunity lists | Baseline top ten by non-purchase volume and alternative top ten by conversion shortfall within the identical eligible segment population; include overlap, rank changes and reasons. |
| D8 | Growth meeting dashboard | Views for commercial overview, eligible segment comparison, month/visitor diagnostics and evidence quality; user can trace a segment to the action register. |
| D11 | Three experiment decision cards | Exactly three proposals, or fewer with explicit evidence-based deferral; each names segment, hypothesis, owner role, change to test, randomisation unit, purchase outcome, guardrail, sample-size inputs and stop/review rule. |

| Success ID | Required deliverable | Specific pass condition |
| --- | --- | --- |
| SC1 | D5 — Segment conversion scorecard | Every retained session belongs to exactly one scorecard row; segment counts reconcile to cohort totals; groups below 100 are visible but unranked; 1 purchase/4 sessions=25%. |
| SC2 | D6 — Conversion driver and leakage assessment | Publish partition counts and exact predictor list; no PageValues/Revenue predictors; report holdout results even when baseline wins; describe end-of-session signals as retrospective. |
| SC3 | D7 — Two ranked opportunity lists | Deterministic ties use TrafficType then VisitorType; every list row links its scorecard; include at least one excluded/deferred segment and explain why. |
| SC4 | D8 — Growth meeting dashboard | A reviewer completes three tasks: find largest eligible non-purchase segment, compare its gap/interval, and identify its proposed experiment; all values match the scorecard. |
| SC5 | D11 — Three experiment decision cards | Every selected segment has ≥100 observed sessions and cited evidence; calculate sample-size needs from declared baseline/MDE/power assumptions; no realised uplift or ordered-checkout-funnel claim. |

## Benefit and adoption boundary

Assessment success means the required outputs are correct, reproducible and usable in the specified review. It does not mean a model must win, a customer must buy, a fault must disappear or a security incident must be prevented. The executive pack must name the measured baseline, alternative, operating trade-off, recommendation and evidence still required for a real pilot. Do not invent commercial savings or success percentages to make the business case appear complete.

At G1 record simulated sponsor approval of the requirements and criteria. At G3 record the policy recommendation and unresolved evidence gaps. At G4 record an actual team reviewer and simulated sponsor role separately; template text is not an approval.

## Source and scope limits

All 12,330 sessions in the original UCI CSV; one session per distinct user in the publisher's one-year sampling frame. Keep all available months; no invented year, event timestamps or ordered clickstream.

Session summaries cannot reconstruct a sequential funnel or prove abandonment at a checkout step. Revenue is a Boolean purchase outcome, not money. PageValues may contain outcome-related information; exclude it from the core model. Completed-session behaviour supports retrospective analysis only, not an at-arrival targeting claim.

**Failure to prevent:** Treating PageValues or end-of-session features as information known at arrival would inflate targeting claims.

Missing mandatory support blocks dependent acceptance until an explicit source/scope decision updates the affected deliverables and tests.

This is a simulated confidential-client engagement using public/open data. Stakeholders and commercial/security scenarios are fictional. Do not claim real-client employment, endorsement, operational deployment or realised benefits. This master pack specifies work to be completed; it does not claim the team has executed it.
