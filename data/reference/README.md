# MTL-XF-031 — References and mappings

Retain source documentation, licence/citation notices and required codebooks for Online Shoppers Purchasing Intention. Preserve actual header spellings, field types and original row order; distinguish identifiers, predictors and outcomes.

Version each reference with ID, official URL, retrieval date/version, content checksum, rights, raw→display mapping, rationale, owner and reviewer. Unknown categories remain visible; validate mapping completeness/uniqueness and all many-to-many joins.

**Interpretation rule:** Session summaries cannot reconstruct a sequential funnel or prove abandonment at a checkout step. Revenue is a Boolean purchase outcome, not money. PageValues may contain outcome-related information; exclude it from the core model. Completed-session behaviour supports retrospective analysis only, not an at-arrival targeting claim.

**Project policy assumptions:** Baseline ranks TrafficType × VisitorType groups with at least 100 sessions by non-purchase session count. Alternative ranks those same groups by conversion gap below the overall rate, with group sizes and Wilson intervals shown. Recommend at most three experiments; effects remain unmeasured.

Keep choices separate from publisher facts. Register categorical/segment/class labels, unit conversions and any financial or capacity assumptions. Do not invent operational history absent from S1.

A reference explains the source; it cannot supply an unmeasured outcome. Register supplements and scope changes in [SOURCE_REGISTER.md](../SOURCE_REGISTER.md) before dependent work.
