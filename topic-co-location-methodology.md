---
schema: foundry-doc-v1
title: "Retail Co-location Methodology"
slug: topic-co-location-methodology
category: governance
type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: PROSE-TOPIC
last_edited: 2026-05-02
editor: pointsav-engineering
short_description: "Deterministic spatial analysis framework evaluating commercial real estate nodes based on objective convergence of capital-intensive retail operators."
paired_with: topic-co-location-methodology.es.md
cites:
  - ni-51-102
  - osc-sn-51-721
---

The Woodfine co-location methodology ranks development sites by the objective convergence of independent, capital-intensive retail operators — not by subjective market sentiment or analyst forecasts. A node qualifies when a hypermarket, warehouse club, and home improvement superstore have each independently committed capital within 1.0–3.0 km of each other.

## The Named-Anchor Model

The foundation of the methodology is the **Named-Anchor Model**. Large-format retailers apply rigorous, data-driven site selection criteria before committing capital to a market. When multiple independent operators converge on the same geographic node, that convergence signals a validated commercial corridor: a location where multiple parties have independently confirmed the trade area's strength.

The methodology categorizes these operators into three distinct tiers based on their commercial function and foot-traffic contribution:

### 1. Primary Targets (The Anchor)
The foundational requirement for any evaluated node. The Primary Target represents the core traffic driver.
*   **North America:** Walmart Supercentre
*   **Europe:** IKEA (operational baseline)

### 2. Secondary Targets (Commercial Support)
Complementary large-format operators that validate the trade area's commercial depth. They are evaluated within a strict **1.0 km to 3.0 km** catchment radius of the Primary Target.
*   **Secondary-1 (Hardware):** Home Depot, Lowe's, Leroy Merlin.
*   **Secondary-2 (Warehouse Club):** Costco, Sam's Club, Makro.

### 3. Tertiary Targets (Institutional Support)
Civic and institutional infrastructure that provide a non-cyclical, stable demographic baseline. Evaluated within a **5.0 km** catchment radius.
*   **Tertiary-A (Healthcare):** Major hospitals and medical centers.
*   **Tertiary-B (Higher Education):** Universities and colleges.

## Quality Tiers and Site Validation

Sites are evaluated using a 12-rank matrix that maps to five quality tiers. This tiered approach allows for precise differentiation between "commodity" retail nodes and those rare locations where critical commercial elements converge.

| Tier | Description | Commercial Validation |
|------|-------------|-----------------------|
| ★★★★★ | Tier 5 — Full Co-location | All four categories present: Hardware, Warehouse Club, Healthcare, and Higher Education. |
| ★★★★ | Tier 4 — Strong Co-location | Both commercial secondaries plus one tertiary; one institutional dimension absent. |
| ★★★ | Tier 3 — Partial Co-location | Two categories present: full secondary pairing (Rank 4), or a single secondary with at least one tertiary (Ranks 5–7). |
| ★★ | Tier 2 — Limited Co-location | One category present: Hardware only (Rank 8), or Warehouse Club with a single tertiary (Ranks 9–10). |
| ★ | Tier 1 — Anchor Only | Commercial secondaries largely absent: tertiary-only convergence (Rank 11) or Warehouse Club only (Rank 12). |

See [[topic-co-location-ranking-system]] for the complete 12-rank specification, rank-to-tier mapping, and site counts by tier.

## Strategy and Application

The co-location index acts as a defensive filter for capital deployment. By focusing on Tier 4 and Tier 5 nodes, investors can prioritize sites with the highest levels of capital validation and the strongest multi-format demographic anchors.

The methodology is applied consistently across global markets by mapping regional operators to these canonical roles. Future expansion of the methodology includes the integration of logistics and transport data to add a fourth dimension to the matrix. [ni-51-102] [osc-sn-51-721]

## See Also
*   [[topic-co-location-ranking-system]]
*   [[topic-co-location-intelligence-overview]]
*   [[topic-co-location-anchors]]

---
## Provenance
- **Draft Source:** `TOPIC-co-location-methodology.md` (project-gis)
- **Refinement:** 2026-05-02 by project-language Task
- **Verification:** Methodology definitions confirmed against `app-orchestration-gis` documentation and current regional configurations.
- **BCSC Posture:** Forward-looking methodology expansions (transport data) labeled per ni-51-102.

---

*Copyright © 2026 Woodfine Capital Projects Inc. Licensed under [Creative Commons Attribution 4.0 International](https://creativecommons.org/licenses/by/4.0/).*
