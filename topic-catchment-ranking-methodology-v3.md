---
schema: foundry-doc-v1
title: "Pure-Predicate Catchment Ranking Methodology (V3)"
slug: topic-catchment-ranking-methodology-v3
aliases:
  - topic-catchment-ranking-methodology-v3
category: governance
type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: PROSE-TOPIC
last_edited: 2026-05-25
editor: pointsav-engineering
short_description: "The V3 tier-assignment methodology assigns each co-location cluster to one of four tiers using binary predicate gates — composition, national catchment rank, civic classification, and spatial overlap — replacing the prior composite-score system introduced in Sprint 17 (May 2026)."
paired_with: topic-catchment-ranking-methodology-v3.es.md
cites:
  - osm-odbl
  - overture-maps-cdla-2-0
  - ni-51-102
  - osc-sn-51-721
---

The [[topic-co-location-methodology|co-location]] tier system assigns each cluster to one of four tiers — Regional, District, Local, or Fringe (labelled per the [[topic-co-location-tier-nomenclature|tier nomenclature]]) — using binary predicate gates rather than a composite score. A cluster must pass every gate in a tier's gate set to qualify for that tier; partial scores do not accumulate. This methodology describes the V3 implementation introduced in Sprint 17 (May 2026). It complements the [[topic-co-location-ranking-system|deterministic ranking system]] and draws its trade-area inputs from the [[topic-od-catchment-methodology|O-D catchment methodology]] and the [[topic-trade-area-data-sources|trade-area data sources]].

## Why Predicate Gates Replace Composite Scores

The prior V2 system assigned tiers by summing a base score, count bonus, diversity bonus, civic depth term, and overlap penalty. The resulting composite score was internally consistent but difficult to explain: a cluster could reach Tier 2 via a high diversity bonus even if it lacked the population catchment and civic infrastructure that the tier was intended to signal.

Binary gates make the qualification criteria explicit and independently verifiable. A Regional cluster must have national-scale population reach, a specific anchor composition, regional hospital access, and spatial independence from stronger clusters. None of these requirements are satisfied by proxy.

## Population Catchment Ranks

Catchment population is computed using a crow-flies H3 grid at resolution 7 (cell width approximately 2.1 km), per the [[topic-od-catchment-methodology|O-D catchment methodology]]. Two zones are defined for each cluster:

- **Primary zone**: all H3 cells within 35 km of the cluster anchor
- **Secondary zone**: all H3 cells between 35 km and 150 km of the cluster anchor

Population totals draw from WorldPop 2026 100 m rasters aggregated to H3 resolution 7 (see [[topic-trade-area-data-sources|trade-area data sources]]). Clusters are ranked within their ISO country on each of eight axes: primary population, secondary population, primary grocery spend, secondary grocery spend, primary hardware spend, secondary hardware spend, primary wholesale spend, and secondary wholesale spend.

The rank is expressed as a fraction: rank 1 in a country of 500 clusters yields 0.002; rank 50 yields 0.100. Lower values indicate higher relative reach within the country. A cluster with a primary-population rank of 0.10 is in the top 10% of its country by primary trade-area population.

Spend estimates are derived from per-capita household spending surveys (BLS for the United States, StatCan for Canada, Eurostat HBS for European Union member states, INEGI for Mexico) applied to WorldPop grid cells, stratified by grocery, hardware, and wholesale category shares.

## Tier Gate Definitions

### Tier 1 — Regional

A cluster qualifies as Regional if all five of the following conditions are true:

1. **Composition**: The cluster contains a Warehouse anchor (Costco, Sam's Club, Makro, or equivalent) and a Hypermarket anchor (Walmart, Target, Mercadona, Tesco, Sainsbury's, or equivalent); or it contains a Lifestyle anchor (IKEA) and a Hypermarket anchor.
2. **Primary catchment**: The cluster's primary-population rank within its country is in the top 10% (rank value ≤ 0.10).
3. **Secondary catchment**: The cluster's secondary-population rank within its country is in the top 20% (rank value ≤ 0.20).
4. **Civic — regional hospital**: At least one hospital classified as "regional" by the OSM-derived civic classification is present within the 5 km civic ring around the cluster anchor.
5. **Spatial independence**: The Intersection over Union (IoU) between this cluster's 3 km disk and the 3 km disk of any cluster in the same country with a higher primary-population rank does not exceed 0.10.

### Tier 2 — District

A cluster qualifies as District if all five of the following conditions are true:

1. **Composition**: The cluster contains a Hypermarket anchor and a Hardware anchor (Home Depot, Lowe's, Leroy Merlin, or equivalent) or a Warehouse anchor.
2. **Primary catchment**: The cluster's primary-population rank within its country is in the top 25% (rank value ≤ 0.25).
3. **Spend reach**: The cluster's rank within its country on at least one of grocery spend, hardware spend, or wholesale spend is in the top 25% (rank value ≤ 0.25).
4. **Civic — hospital present**: At least one hospital classified as "regional" or "district" is present within the 5 km civic ring.
5. **Spatial independence**: The IoU between this cluster's 3 km disk and the 3 km disk of any Regional cluster in the same country does not exceed 0.25.

### Tier 3 — Local

A cluster qualifies as Local if all three of the following conditions are true:

1. **Composition**: The cluster contains a Hardware or Warehouse anchor.
2. **Primary catchment**: The cluster's primary-population rank within its country is in the top 50% (rank value ≤ 0.50).
3. **Civic — any hospital**: At least one hospital of any classification is present within the 5 km civic ring.

### Tier 4 — Fringe

A cluster that does not qualify for Regional, District, or Local is classified as Fringe. A Fringe cluster may still contain significant retail co-tenancy; the classification indicates that one or more required conditions for Local or above were not met.

## Overlap Measurement

The spatial independence gate uses the closed-form intersection-over-union formula for two equal-radius circles:

```
lens_area = 2r² · arccos(d/2r) − (d/2) · √(4r² − d²)
IoU = lens_area / (2·π·r² − lens_area)
```

where d is the haversine distance between cluster centroids and r = 3.0 km (the secondary co-location radius). Two clusters whose centroids are further than 6 km apart have IoU = 0 by definition.

## Civic Classification

Hospital and university tier assignments are produced from OpenStreetMap data. Hospitals are classified as `regional` (major general hospitals with emergency departments), `district` (secondary hospitals and specialist centres), or `clinic` (general practice and walk-in clinics). Clinics do not contribute to Regional or District civic gates.

## Threshold Summary

| Threshold | Symbol | Value |
|---|---|---|
| T1 primary catchment | P10 | top 10% within country |
| T1 secondary catchment | P20 | top 20% within country |
| T2 primary catchment / spend | P25 | top 25% within country |
| T3 primary catchment | P50 | top 50% within country |
| T1 IoU limit | — | ≤ 0.10 |
| T2 IoU limit | — | ≤ 0.25 |
| Civic ring radius | — | 5 km |
| IoU disk radius | — | 3 km |

Thresholds are intentionally coarse. The P10/P25/P50 values distinguish nationally significant clusters from local nodes. Refinement is planned for a future update as additional catchment data becomes available.

## See Also

- [[topic-co-location-tier-nomenclature]]
- [[topic-co-location-methodology]]
- [[topic-co-location-ranking-system]]
