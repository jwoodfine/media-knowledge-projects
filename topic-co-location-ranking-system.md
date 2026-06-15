---
schema: foundry-doc-v1
title: "Retail Co-location Ranking System"
slug: topic-co-location-ranking-system
aliases:
  - topic-co-location-ranking-system
category: governance
type: topic
content_type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: PROSE-TOPIC
last_edited: 2026-05-25
editor: pointsav-engineering
short_description: "Deterministic 12-rank scoring algorithm evaluating retail co-location sites by named-anchor convergence across defined catchment radii."
paired_with: topic-co-location-ranking-system.es.md
cites:
  - ni-51-102
  - osc-sn-51-721
---

The Woodfine [[topic-co-location-methodology|co-location methodology]] is operationalised as a **named-anchor combination matrix** — a deterministic algorithm that scores each hypermarket [[topic-co-location-anchors|anchor]] location based on the convergence of secondary and tertiary retail and civic categories within defined catchment radii.

The system produces a 12-rank index mapped to five quality tiers, visualised on the Geographic Information System (GIS) platform at [gis.woodfinegroup.com](https://gis.woodfinegroup.com) using a warm-to-cool colour scale: deep amber (★★★★★ Tier 5, highest) through pale blue (★ Tier 1, lowest). The map-facing labels — Regional, District, Local, Fringe — follow the ICSC hierarchy described in [[topic-co-location-tier-nomenclature|tier nomenclature]], and qualification gates are detailed in the [[topic-catchment-ranking-methodology-v3|V3 catchment ranking methodology]]. This approach provides an objective, capital-validated framework for assessing commercial site defensibility.

## The named-anchor model

Every co-location site in the index is anchored by a single hypermarket or large-format general merchandise operator — Walmart, IKEA, Carrefour, and their regional equivalents. The anchor is the foundational requirement: no site without a qualifying anchor is admitted to the index. The full chain-to-family mapping is documented in the [[topic-retail-brand-family-taxonomy|retail brand family taxonomy]].

Secondary and tertiary operators are classified into four deterministic categories:

| Category | Role | Commercial Rationale |
|----------|------|----------------------|
| **Hardware** | Secondary-1 | High-frequency, destination-driven superstores (Home Depot, Lowe's, Leroy Merlin). |
| **Warehouse Club** | Secondary-2 | Membership-driven, high-volume bulk retail (Costco, Sam's Club, Makro). |
| **Healthcare** | Tertiary-A | Critical civic infrastructure (hospitals, medical centers) providing stable demographic baselines. |
| **Higher Education** | Tertiary-B | Institutional anchors (universities, colleges) driving non-cyclical traffic density. |

A secondary operator qualifies as co-located when it falls within the secondary radius (default: 3 km from the anchor). Tertiary operators are scored within a 5 km radius.

## The 12-rank matrix

The combination of present categories determines the site rank. There are twelve named combinations in the matrix, ordered by structural complexity and commercial validation:

| Rank | Tier | Hardware | Warehouse | Healthcare | Higher Ed |
|------|------|:--------:|:---------:|:----------:|:---------:|
| 1  | ★★★★★ | ✓ | ✓ | ✓ | ✓ |
| 2  | ★★★★ | ✓ | ✓ |   | ✓ |
| 3  | ★★★★ | ✓ | ✓ | ✓ |   |
| 4  | ★★★  | ✓ | ✓ |   |   |
| 5  | ★★★  | ✓ |   |   | ✓ |
| 6  | ★★★  | ✓ |   | ✓ |   |
| 7  | ★★★  |   | ✓ | ✓ | ✓ |
| 8  | ★★   | ✓ |   |   |   |
| 9  | ★★   |   | ✓ |   | ✓ |
| 10 | ★★   |   | ✓ | ✓ |   |
| 11 | ★    |   |   | ✓ | ✓ |
| 12 | ★    |   | ✓ |   |   |

*Anchors present with no qualifying secondary or tertiary operators are excluded from the ranked index.*

## Quality tiers and distribution

The twelve ranks are grouped into five tiers to provide a high-level view of market quality.

**Tier scale note.** This article's five-tier scale (Tier 1 = lowest, Tier 5 = highest) describes the scoring index rendered on the map. Individual co-location sites within a Regional Market are separately described using a three-tier cluster classification (T1, T2, T3) in which T1 denotes the cluster with the most anchor-type categories present — the highest-composition cluster type in a given market. These two classification scales share vocabulary but are distinct: the map tier measures commercial density across the full index; the cluster tier ranks anchor composition within a single market.

### ★★★★★ Tier 5 — Full co-location
*Rank 1 only. All four categories present.*
The highest designation. The anchor operates within 3 km of both a hardware superstore and a warehouse club, and within 5 km of both a healthcare facility and a university. This indicates that all four independent capital-selection processes have converged on the same node. As of 2 May 2026: **102 sites** (North America).

### ★★★★ Tier 4 — Strong co-location
*Ranks 2–3. Three categories present.*
The anchor is paired with both a hardware superstore and a warehouse club, plus one of the two tertiary categories. The commercial co-location is structurally complete; one institutional dimension is absent. As of 2 May 2026: **268 sites** (NA: 259, EU: 9).

### ★★★ Tier 3 — Partial co-location
*Ranks 4–7. Two categories present.*
The commercial baseline for the index. Includes the Rank 4 combination (anchor + hardware + warehouse) as well as single-secondary combinations supported by tertiary institutional presence. As of 2 May 2026: **1,571 sites** (NA: 1,396, EU: 175).

### ★★ Tier 2 — Limited co-location
*Ranks 8–10. One category present.*
The anchor has one major co-located secondary or tertiary support. Site quality in this tier is highly market-dependent. As of 2 May 2026: **356 sites** (NA: 333, EU: 23).

### ★ Tier 1 — Anchor only
*Ranks 11–12. Tertiary-only or Warehouse-only.*
The hypermarket anchor is present, but the primary commercial co-location secondaries (hardware and/or warehouse club) are mostly absent. These sites represent the floor of the index. As of 2 May 2026: **441 sites** (NA: 398, EU: 43).

## Calibration and scarcity

The secondary radius (1 km, 2 km, or 3 km) determines index density. The platform enforces an automatic **calibration rule** to maintain index scarcity: if Rank-1 sites exceed 10% of total anchor locations, the system tightens the radius default. 

As of 2 May 2026, Rank-1 sites represent 3.7% of total anchors — well below the threshold. The current 3 km default remains the active calibration setting.

## Market adaptation

Each of the eight retail markets uses a dedicated region configuration that maps local operators to the canonical anchor and secondary roles. This ensures the algorithm applies consistent structural logic across jurisdictions where different brands fill equivalent commercial functions (e.g., Costco in Canada, Makro in Europe).

Integration of the aviation facility dataset (29,020 records) into tertiary scoring is a planned target for future iterations of the ranking matrix. [ni-51-102] [osc-sn-51-721]

## Provenance
- **Verification:** Rank distribution and matrix logic confirmed against the GIS platform build configuration as of 2 May 2026.
- **Forward-looking disclosure:** Aviation dataset integration into tertiary scoring is an intended target, labeled per [ni-51-102].

## See also
*   [[topic-co-location-methodology]]
*   [[topic-co-location-intelligence-overview]]
*   [[topic-co-location-anchors]]

## References

- [Big-box store](https://en.wikipedia.org/wiki/Big-box_store) — Wikipedia, accessed 2026-06-14
- [DBSCAN](https://en.wikipedia.org/wiki/DBSCAN) — Wikipedia, accessed 2026-06-14

---

*Copyright © 2026 Woodfine Capital Projects Inc. Licensed under [Creative Commons Attribution 4.0 International](https://creativecommons.org/licenses/by/4.0/).*
