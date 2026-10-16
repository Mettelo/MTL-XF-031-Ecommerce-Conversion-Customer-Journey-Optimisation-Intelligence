# MTL-XF-031 — Data acquisition and engineering

## Approved S1

[Online Shoppers Purchasing Intention](https://archive.ics.uci.edu/dataset/468); required files: **online_shoppers_intention.csv**. Expected source population: 12,330 sessions.

Exact official download:

https://archive.ics.uci.edu/static/public/468/online+shoppers+purchasing+intention+dataset.zip

No paid API or temporary dashboard export is required. [Source register](SOURCE_REGISTER.md) records checked byte references and rights.

## Frozen cohort and schema

All 12,330 sessions in the original UCI CSV; one session per distinct user in the publisher's one-year sampling frame. Keep all available months; no invented year, event timestamps or ordered clickstream.

**Grain:** One source session; immutable row number plus input SHA-256 is the surrogate key.

**Required fields:** Revenue, Month, VisitorType, TrafficType, Weekend, Administrative, Informational, ProductRelated, their duration fields, BounceRates, ExitRates, PageValues, SpecialDay.

## Acquisition and freeze procedure

1. Retrieve original bytes and required documentation into approved durable storage outside Git. Record retrieval UTC, requested/resolved URLs and HTTP result.
2. Verify archive/member integrity, actual sizes and SHA-256 against the checked reference. A mismatch stops processing for publisher-change/corruption review.
3. Inspect schema, encoding, separator, headers/sheets, count, label coding, dates and coverage. Preserve actual header spellings, field types and original row order; distinguish identifiers, predictors and outcomes.
4. Complete source→actual field→KPI→deliverable support matrix for K1–K7 and D1–D12. Missing mandatory fields block dependent work; do not invent substitutes.
5. Approve an immutable S1-v1 byte manifest and exact cohort with retention owner, reviewer access, analyst/reviewer identities and date. Master source verification does not replace team G1 approval.
6. Transform reproducibly into separate curated outputs. Account for every raw row once as retained, excluded or quarantined; preserve lineage and treatment reason.

## Evaluation

Stratified 60/20/20 train/validation/test, seed 31, with exact duplicate feature groups kept together. Fit preprocessing on train only. Exclude Revenue and PageValues from predictors; document which remaining features would be unavailable at any proposed live decision time.

## Interpretation and quality

Session summaries cannot reconstruct a sequential funnel or prove abandonment at a checkout step. Revenue is a Boolean purchase outcome, not money. PageValues may contain outcome-related information; exclude it from the core model. Completed-session behaviour supports retrospective analysis only, not an at-arrival targeting claim.

Profile every actual column. Dictionary includes spelling, type, unit, valid values, sentinel/null policy, meaning and feature/target/ID role plus availability time. Investigate duplicates/label conflicts; no silent deduplication or denominator invention. Validate key uniqueness and joins at the declared grain.

Keep [raw](raw/README.md), [references](reference/README.md) and [metadata](metadata/README.md) separate. Derived outputs belong in team data/curated/ or an approved location. Raw data are not uploaded by this update. Refresh creates a new snapshot while the accepted core stays reproducible.
