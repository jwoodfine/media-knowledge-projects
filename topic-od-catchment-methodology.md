---
schema: foundry-doc-v1
title: "O-D catchment methodology — primary and secondary trade areas"
slug: topic-od-catchment-methodology
aliases:
  - topic-od-catchment-methodology
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
short_description: "Trade areas for each co-location cluster are defined using crow-flies H3 hexagonal distance rings: a 35 km primary zone and a 35–150 km secondary zone, both computed from WorldPop 2026 population data."
paired_with: topic-od-catchment-methodology.es.md
---

The Woodfine [[topic-co-location-methodology|co-location]] platform defines trade areas for each cluster using an Origin-Destination (O-D) model based on crow-flies distance rings over a hexagonal spatial grid. Each cluster is assigned two catchment zones that determine which population and spend data is attributed to it. The trade-area inputs to the [[topic-co-location-ranking-system|deterministic ranking system]] and the [[topic-catchment-ranking-methodology-v3|V3 catchment ranking methodology]] flow from this model; population and spend layers are documented in [[topic-trade-area-data-sources|trade-area data sources]].

## Spatial Framework

Trade areas are computed using the H3 global hexagonal grid at resolution 7. Each H3 resolution-7 cell covers approximately 5.16 km² with a centre-to-centre spacing of approximately 2.11 km. The grid is continuous and consistent worldwide, enabling direct comparison between clusters across all countries in the current dataset.

## Catchment Zone Definitions

**Primary catchment:** All H3 resolution-7 cells whose centre point falls within 35 km (crow-flies) of the cluster centroid. This zone represents the immediate trade area where the majority of regular shopping trips originate.

**Secondary catchment:** All H3 resolution-7 cells whose centre point falls between 35 km and 150 km (crow-flies) of the cluster centroid. This zone captures the wider regional draw, including occasional shoppers and cross-regional trips.

The 35 km primary boundary is a provisional parameter based on established retail geography conventions. It is subject to refinement once empirical origin-destination data becomes available.

The 150 km outer boundary aligns with the platform's data collection radius, ensuring that every cell contributing to a cluster's catchment has been ingested and verified.

## Distance Method

All distances are calculated as the crow-flies (great-circle) distance using the haversine formula. No drive-time routing is used. This approach is:

- Reproducible without map routing infrastructure
- Consistent across urban and rural geographies
- Computationally efficient over millions of H3 cells
- Suitable as a baseline before empirical O-D data is available

H3 ring traversal identifies candidate cells efficiently (17 rings ≈ 35 km; 72 rings ≈ 150 km at resolution 7), with haversine as the definitive distance measure.

## HOME and AWAY Perspectives

The platform distinguishes two perspectives on catchment population.

**HOME:** Population counts derived from residential data (WorldPop 2026). Represents where people live within each catchment zone. This is the default view and is fully implemented.

**AWAY:** Population counts representing daytime or workplace population. Workplace distribution differs from residential distribution — concentrated in commercial districts and employment centres rather than dispersed across residential areas. The AWAY perspective is planned; the data source is pending.

## One Cell, Multiple Clusters

A single H3 cell may fall within the catchment of multiple co-location clusters. This is intentional: trade areas are not exclusive territories. A household within 35 km of two competing clusters contributes to both clusters' primary catchment populations. This reflects the competitive retail landscape and is foundational to the cross-cluster comparison methodology; cluster boundary handling at the same parking lot is documented in [[topic-cluster-deduplication-threshold|cluster deduplication threshold]].

## Application

Catchment zone membership is the basis for:

- Population aggregation (census data by zone)
- Spend aggregation (grocery, hardware, wholesale spend by zone)
- Cross-cluster competitive ranking (see: Catchment Ranking Methodology V3)

The catchment polygons displayed on the map are generated from the same 35 km / 150 km crow-flies radii, visualised in two distinct colours to distinguish primary from secondary zones.

## See also

- [[topic-catchment-ranking-methodology-v3]]
- [[topic-trade-area-data-sources]]
- [[topic-co-location-methodology]]

## References

- [Catchment area](https://en.wikipedia.org/wiki/Catchment_area_(human_geography)) — Wikipedia, accessed 2026-06-14
- [Trade area](https://en.wikipedia.org/wiki/Trade_area) — Wikipedia, accessed 2026-06-14
- [H3: Uber's Hexagonal Hierarchical Spatial Index](https://h3geo.org/) — H3 Geo, accessed 2026-06-14
- [WorldPop Global High Resolution Population Denominators Project](https://www.worldpop.org/) — WorldPop, University of Southampton, accessed 2026-06-14

*Wikipedia content reproduced under [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/).*

*Cluster centroids from which catchment distances are measured are derived from OpenStreetMap POI records. OpenStreetMap data © OpenStreetMap contributors, licensed under ODbL.*
