---
schema: foundry-doc-v1
title: "Distance-band methodology — primary and secondary demand zones"
slug: od-catchment-methodology
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
short_description: "Each co-location cluster is assigned two straight-line distance bands — a primary zone within 35 km and a secondary zone from 35 km to 150 km — that determine the population and spend attributed to it."
paired_with: site-selection/od-catchment-methodology.es.md
---

The Woodfine [[co-location-methodology|co-location]] platform assigns each cluster two demand zones that determine which population and spend data is attributed to it: a primary zone within 35 km of the cluster, and a secondary zone from 35 km to 150 km. Both are straight-line distance bands, and they are labelled as such: a distance band approximates where customers come from; it is not a measured catchment, and the platform does not label it one. The labelling rule, and the planned move to observed origins and drive-time boundaries, are set out in [[trade-area-methodology]]. The zone inputs to the [[co-location-ranking-system|deterministic ranking system]] and the [[catchment-ranking-methodology|catchment ranking methodology]] flow from this model; population and spend layers are documented in [[trade-area-data-sources|trade-area data sources]].

## Zone definitions

**Primary zone (0–35 km):** the area within 35 km straight-line distance of the cluster centroid. This zone represents the immediate trade area where the majority of regular shopping trips originate.

**Secondary zone (35–150 km):** the area between 35 km and 150 km straight-line distance of the cluster centroid. This zone captures the wider regional draw, including occasional shoppers and cross-regional trips.

The primary boundary is a provisional parameter based on established retail geography conventions. It is subject to refinement once empirical origin-destination data becomes available. The outer boundary aligns with the platform's own data-collection reach, so every location contributing to a cluster's zones has already been ingested and verified.

Zone membership is resolved the same way in every market, so zone figures compare directly between clusters in any country.

## Distance method

All distances are straight-line ground distances; no drive-time routing is used at this stage. A 35 km band therefore means the same thing in every market — urban or rural, North American or European — which is what makes cross-cluster comparison possible before observed origin data arrives. Reachability along the road network is a planned improvement, described in [[trade-area-methodology]].

## HOME and AWAY perspectives

The platform distinguishes two perspectives on zone population.

**HOME:** population counts derived from published residential population data. Represents where people live within each zone. This is the default view and is fully implemented.

**AWAY:** population counts representing daytime or workplace population. Workplace distribution differs from residential distribution — concentrated in commercial districts and employment centres rather than dispersed across residential areas. The AWAY perspective is planned; the data source is pending.

## One place, multiple clusters

A single location may fall within the zones of multiple co-location clusters. This is intentional: trade areas are not exclusive territories. A household within 35 km of two competing clusters contributes to both clusters' primary-zone populations. This reflects the competitive retail landscape and is foundational to the cross-cluster comparison methodology; cluster boundary handling at the same parking lot is documented in [[cluster-deduplication-threshold|cluster deduplication threshold]].

## Application

Zone membership is the basis for:

- Population aggregation (published population data by zone)
- Spend aggregation (grocery, hardware, wholesale spend by zone)
- Cross-cluster competitive ranking (see [[catchment-ranking-methodology]])

The zone polygons displayed on the map are generated from the same 35 km / 150 km straight-line radii, visualised in two distinct colours to distinguish primary from secondary zones.

## See also

- [[catchment-ranking-methodology]]
- [[trade-area-data-sources]]
- [[co-location-methodology]]

## References

- [Catchment area](https://en.wikipedia.org/wiki/Catchment_area_(human_geography)) — Wikipedia, accessed 2026-06-14
- [Trade area](https://en.wikipedia.org/wiki/Trade_area) — Wikipedia, accessed 2026-06-14
- [Kontur Population Dataset](https://data.humdata.org/dataset/kontur-population-dataset) — Kontur, accessed 2026-09-07

*Wikipedia content reproduced under [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/).*

*Cluster centroids from which zone distances are measured are derived from OpenStreetMap POI records. OpenStreetMap data © OpenStreetMap contributors, licensed under ODbL.*
