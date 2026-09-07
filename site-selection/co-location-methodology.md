---
schema: foundry-doc-v1
title: "Retail co-location methodology"
slug: co-location-methodology
category: site-selection
index_group: strategy-and-investment-thesis
type: topic
content_type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: PROSE-TOPIC
last_edited: 2026-08-25
editor: pointsav-engineering
short_description: "A deterministic spatial-analysis framework that classifies commercial real-estate nodes by the objective convergence of independent, capital-intensive retail operators — independent corroboration in place of market sentiment."
paired_with: site-selection/co-location-methodology.es.md
cites:
  - ni-51-102
  - osc-sn-51-721
  - planetizen-retail-clusters
  - osm-odbl
---

Retail development capital is usually committed on comparables and analyst sentiment. Whether independent demand actually converges at a site — the reason it should succeed — is assumed rather than measured.

The Woodfine co-location methodology measures it. It classifies development sites by the objective convergence of independent, capital-intensive retail operators, not by market sentiment or analyst forecasts. The framework is operationalised by the [[co-location-ranking-system|deterministic ranking system]] and exposed to platform users via the [[co-location-intelligence-overview|co-location intelligence overview]].

A node qualifies when a hypermarket, a warehouse club, and a home-improvement superstore have each independently committed capital within a defined catchment radius of one another. Each operator runs its own site-selection process; convergence is independent corroboration, not a single forecast. The qualification logic, [[co-location-cluster-formation|cluster formation]], and the [[co-location-anchors|anchor]] adjacency requirement are the three structural inputs to the index.

For a capital allocator the index is a defensive filter: it prioritises the sites where several parties have independently validated the trade area. This article covers the anchor taxonomy and the tier system's predicate gates; sibling articles describe the [[od-catchment-methodology|distance-band methodology]], the [[trade-area-data-sources|trade-area data sources]], and the [[catchment-ranking-methodology|catchment ranking methodology]].

## Anchor taxonomy

Large-format retailers apply rigorous, data-driven site-selection criteria before committing capital to a market. When several independent operators converge on the same geographic node, that convergence signals a validated commercial corridor — a location where multiple parties have independently confirmed the trade area's strength.

Every cluster forms around a primary anchor from one of four classes. **Hypermarket** anchors are general-merchandise chains — Walmart, Target, Mercadona, Tesco. **Lifestyle** anchors are large-format home retailers; IKEA is the only chain in this class. **Hardware** anchors are home-improvement chains — Home Depot, Lowe's, Leroy Merlin. **Warehouse** anchors are membership clubs — Costco, Sam's Club, Makro. The full chain-to-family mapping is documented in [[retail-brand-family-taxonomy|the retail brand family taxonomy]].

## Tier classification

Each cluster is assigned one of four tiers — **Regional**, **District**, **Local**, **Fringe** — by clearing a set of predicate gates rather than accumulating a score. The map-facing labels follow the ICSC retail property hierarchy; the full naming history is in [[co-location-tier-nomenclature|tier nomenclature]].

| Tier | What it requires |
|---|---|
| **Regional** | A hypermarket paired with a warehouse or lifestyle anchor, top-decile catchment population nationally, and a regional hospital within the civic ring. The highest tier. |
| **District** | A hypermarket paired with hardware or warehouse, top-quartile catchment population, and hospital access within the civic ring. |
| **Local** | A hardware or warehouse anchor, top-half catchment population, and any hospital within the civic ring. |
| **Fringe** | Retail co-tenancy is present, but catchment reach, composition, or civic support falls short of Local. |

The full gate definitions — composition, catchment rank, civic presence, and spatial non-overlap — are set out in the [[catchment-ranking-methodology|catchment ranking methodology]].

## Strategy and application

The tier system acts as a defensive filter for capital deployment. By prioritising Regional and District nodes, an investor selects sites with the strongest multi-operator capital validation and the deepest catchment population support.

The methodology applies consistently across global markets by mapping regional operators to these canonical anchor classes. Expansion of the tertiary civic dataset — bringing university and hospital coverage in Mexico and Canada to the same maturity as the United States — is a planned target for future iterations. [ni-51-102] [osc-sn-51-721]

## Data sources

Anchor and secondary operator locations are sourced from **OpenStreetMap contributors** under the [Open Database Licence (ODbL)](https://opendatacommons.org/licenses/odbl/). Records are filtered by canonical Wikidata brand identifiers to ensure consistent chain-family matching across borders. The full chain-to-family mapping is documented in [[retail-brand-family-taxonomy]]. [osm-odbl]

## See also

- [[co-location-ranking-system]]
- [[co-location-intelligence-overview]]
- [[co-location-anchors]]

## References

- [Retail park](https://en.wikipedia.org/wiki/Retail_park) — Wikipedia, accessed 2026-06-14
- [Big-box store](https://en.wikipedia.org/wiki/Big-box_store) — Wikipedia, accessed 2026-06-14
- [DBSCAN](https://en.wikipedia.org/wiki/DBSCAN) — Wikipedia, accessed 2026-06-14

*OpenStreetMap data © OpenStreetMap contributors, licensed under ODbL.*

---

*Copyright © 2026 Woodfine Capital Projects Inc. Licensed under [Creative Commons Attribution-NoDerivatives 4.0 International](https://creativecommons.org/licenses/by-nd/4.0/).*
