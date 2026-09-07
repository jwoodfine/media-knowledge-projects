---
schema: foundry-doc-v1
title: "Retail co-location ranking system"
slug: co-location-ranking-system
category: site-selection
index_group: site-scoring-and-trade-areas
type: topic
content_type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: PROSE-TOPIC
last_edited: 2026-09-04
editor: pointsav-engineering
short_description: "The deterministic mechanics behind cluster ranking on the co-location platform — country-relative percentile ranking, the overlap test between neighbouring clusters, and the tiebreak order applied within a tier."
paired_with: site-selection/co-location-ranking-system.es.md
---

The Woodfine [[co-location-methodology|co-location methodology]] assigns each cluster's tier through binary predicate gates, not a composite score — no cluster earns a tier by accumulating points toward a threshold. This article covers the mechanics behind those gates: how a cluster's catchment position is measured against its national peers, how competing clusters are compared for overlap, and how clusters are ordered once ranked. The gate definitions themselves — which combination of tests each tier requires — are set out in the [[catchment-ranking-methodology|catchment ranking methodology]]; the tier labels are described in [[co-location-tier-nomenclature|tier nomenclature]].

## Country-relative ranking

A cluster's tier depends on where it stands against every other cluster in its own country, not against a fixed global threshold. Each cluster is ranked against its national peers on measures of catchment population and consumer spend. Ranking within-country, rather than against one global bar, keeps a smaller market's structure intact: a nationally significant cluster in a small country is read against its own national field, not swamped by the sheer scale of a larger one. The percentile axes and the calculation behind them are planned for publication at gis.woodfinegroup.com.

Catchment is measured across two distance bands — a primary zone within 35 km of the cluster and a secondary zone between 35 km and 150 km — per the [[od-catchment-methodology|distance-band methodology]]. Spend estimates draw on national household-spending surveys.

These thresholds are intentionally coarse. The system is built to separate nationally significant clusters from local nodes, not to finely rank clusters against one another within a tier.

## The overlap test

A cluster is only credited for its tier when it is not dominated by a stronger neighbour nearby. Overlap between neighbouring clusters is measured by a geometric test over a fixed radius around each cluster: the closer two clusters sit, the higher the measured overlap, and clusters far enough apart are treated as spatially independent. A cluster that substantially overlaps a stronger cluster is held below the tier its composition and catchment would otherwise earn. Regional carries the strictest overlap limit of any tier, per the [[catchment-ranking-methodology|gate definitions]]. The overlap measure and its radius are planned for publication at gis.woodfinegroup.com.

## Ordering within a tier

Clusters that share a tier and a country are ordered by a fixed sequence of criteria, ending in a tiebreak that cannot produce a tie. The ordering is therefore fully deterministic: the same data returns the same order on every run, so a ranking cited in one review can be reproduced in the next. The ordering criteria and tiebreak sequence are planned for publication at gis.woodfinegroup.com.

## Data Sources

Map and location data © [OpenStreetMap contributors](https://www.openstreetmap.org/copyright) / [ODbL](https://opendatacommons.org/licenses/odbl/).

## See also

- [[co-location-methodology]]
- [[co-location-intelligence-overview]]
- [[catchment-ranking-methodology]]

## References

- [Big-box store](https://en.wikipedia.org/wiki/Big-box_store) — Wikipedia, accessed 2026-06-14

---

*Copyright © 2026 Woodfine Capital Projects Inc. Licensed under [Creative Commons Attribution-NoDerivatives 4.0 International](https://creativecommons.org/licenses/by-nd/4.0/).*
