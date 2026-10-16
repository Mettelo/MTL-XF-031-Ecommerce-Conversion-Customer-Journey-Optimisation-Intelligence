# MTL-XF-031 — Source register

## S1 — Online Shoppers Purchasing Intention

| Field | Approved definition |
| --- | --- |
| Provider | UCI Machine Learning Repository; preserve original creator attribution |
| Documentation | https://archive.ics.uci.edu/dataset/468 |
| Exact download | https://archive.ics.uci.edu/static/public/468/online+shoppers+purchasing+intention+dataset.zip |
| Required inputs | online_shoppers_intention.csv |
| Source population | 12,330 sessions |
| Decision owner | Head of Ecommerce Growth |
| Status | Official archive/feed retrieved and inspected; team freeze/sign-off and analysis remain to be completed. No raw data uploaded. |

Persistent citation: https://doi.org/10.24432/C5F88Q

## Checked byte reference

Official archive retrieved and inspected on **2026-10-16**. Archive size **1072219 bytes**; SHA-256 **2972e6184d3ad7beaaa831d9fc2b059dc3ee29df69d1ec593c466a5cd8485d14**.

| Archive member | Bytes | SHA-256 |
| --- | --- | --- |
| online_shoppers_intention.csv | 1072063 | b3055ee355f59134d851d32641183cb4a8b45def7124d2f50442a042f358e0d9 |

Member names and byte hashes were inspected; CSV record counts were checked where present. Actual cohort transformations and business analysis remain team delivery work.

Preserve actual header spellings, field types and original row order; distinguish identifiers, predictors and outcomes.

## Cohort and field support

All 12,330 sessions in the original UCI CSV; one session per distinct user in the publisher's one-year sampling frame. Keep all available months; no invented year, event timestamps or ordered clickstream.

**Grain:** One source session; immutable row number plus input SHA-256 is the surrogate key.

**Required mapping:** Revenue, Month, VisitorType, TrafficType, Weekend, Administrative, Informational, ProductRelated, their duration fields, BounceRates, ExitRates, PageValues, SpecialDay.

**Interpretation limits:** Session summaries cannot reconstruct a sequential funnel or prove abandonment at a checkout step. Revenue is a Boolean purchase outcome, not money. PageValues may contain outcome-related information; exclude it from the core model. Completed-session behaviour supports retrospective analysis only, not an at-arrival targeting claim.

## Rights and attribution

Publisher page declares [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Cite original creators, UCI and [dataset DOI](https://doi.org/10.24432/C5F88Q); preserve notices and state transformations.

## Team acquisition record required at G1

Record source/freeze ID, requested/resolved URL, retrieval UTC, release/feed timestamp, archive/member filename, actual bytes/checksum, encoding/delimiter/worksheet/schema, row count, date bounds, included/excluded scope, licence/citation evidence, storage/access and retention owner, verification checks, analyst and reviewer approval/date. Unknown or unexecuted fields remain explicitly pending.

## Raw-data durability

Preserve original archive, required members and documentation in a read-only S1-v1 snapshot in approved durable storage outside Git with a second recoverable copy. Record reviewer access and restore instructions without credentials. Provider/DOI URLs locate the source; retained checksum-addressed bytes define reproducibility. Stable URLs do not guarantee immutable contents or perpetual availability.

No raw data are committed by this master update. Restore verified retained bytes if the provider becomes unavailable. If no approved copy exists, block G1; do not substitute an unofficial mirror, another variant or guessed schema. A new official version requires rights/schema/scope review, new freeze ID and rerun of affected tests.

## Refresh and supplementary inputs

Do not stack overlapping UCI samples/variants. Required publisher codebooks remain source references. Business costs, capacities and pilot outcomes absent from S1 are synthetic assumptions, not measured facts.

Every added reference/supplement needs ID, official source/version/URL, rights, grain/coverage, purpose, join key/cardinality, effect on K/D/AC/DT and reviewer approval. Optional extensions cannot replace core requirements silently.
