---
schema: foundry-doc-v1
title: "Trade area data sources — population and spend"
slug: topic-trade-area-data-sources
category: governance
type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: PROSE-TOPIC
last_edited: 2026-05-25
editor: pointsav-engineering
short_description: "Population estimates from WorldPop 2026 and annual per-capita spend proxies from national household surveys underpin the trade area statistics for each co-location cluster."
paired_with: topic-trade-area-data-sources.es.md
---

Population estimates and retail spend estimates are the two input layers that drive trade area statistics for each co-location cluster. Both are derived from publicly available data sources and applied at the H3 resolution-7 hexagonal grid level.

## Population Data

Population estimates are sourced from the **WorldPop 2026 100-metre population grid** (worldpop.org). WorldPop produces modelled population estimates derived from census microdata, satellite imagery, and dasymetric redistribution. The 100 m resolution places population at the sub-block level, enabling precise trade area delineation.

### Processing pipeline

1. **Spatial filter:** Only grid cells within 150 km of at least one co-location cluster centroid are retained, reducing data volume by approximately 80% while preserving all cells relevant to catchment computation.

2. **H3 aggregation:** Retained cells are assigned to their containing H3 resolution-7 hexagon and population values are summed. H3 resolution-7 cells have an average area of 5.16 km².

3. **Output:** `census-h3-res7.jsonl` — one record per H3 cell with fields `{h3, lat, lon, pop, iso}`.

### Countries covered

United States, Canada, Mexico, Great Britain, Germany, France, Netherlands, Austria, Portugal, Greece, Denmark, Iceland, and Poland — 13 countries as of the current pipeline version.

## Spend Data

Spend estimates are synthesised by applying **annual per-capita expenditure multipliers** by retail category to the population grid. The multipliers are proxies derived from national household expenditure surveys.

| Country | Grocery (p.a.) | Hardware (p.a.) | Wholesale (p.a.) | Currency |
|---------|----------------|-----------------|------------------|----------|
| United States | $3,500 | $1,200 | $1,500 | USD |
| Canada | C$3,200 | C$1,100 | C$1,300 | CAD |
| Mexico | MX$18,000 | MX$3,500 | MX$2,500 | MXN |
| Great Britain | £2,800 | £850 | £900 | GBP |
| Germany | €2,900 | €950 | €1,000 | EUR |
| France | €3,100 | €900 | €1,000 | EUR |
| Netherlands | €2,700 | €1,000 | €1,100 | EUR |
| Austria | €3,000 | €950 | €1,000 | EUR |
| Portugal | €2,400 | €600 | €700 | EUR |
| Greece | €2,200 | €500 | €600 | EUR |
| Denmark | €3,500 | €1,200 | €1,100 | EUR |
| Iceland | €4,000 | €1,500 | €1,500 | EUR |
| Poland | PLN 8,000 | PLN 2,000 | PLN 2,500 | PLN |

Multipliers are expressed in local currency. Cross-country spend comparisons require foreign-exchange normalisation, which is not applied in the current pipeline. Rankings are most meaningful within a single country or within the eurozone.

### Retail categories

- **Grocery:** Supermarkets, hypermarkets, food cooperatives, and food sections of general merchandise retailers.
- **Hardware:** Home improvement, building materials, and garden centres.
- **Wholesale:** Members-only warehouse clubs and cash-and-carry retailers.

### Processing pipeline

Spend values are computed at the H3 resolution-7 level by multiplying each cell's aggregated population by the per-capita multipliers for its country. Output: `cleansed-spend-h3-res7.jsonl` — one record per H3 cell with fields `{h3, pop, spend_grocery, spend_hardware, spend_wholesale, currency}`.

## Catchment Aggregation

For each co-location cluster, primary and secondary catchment zones are defined by crow-flies distance rings (see: O-D Catchment Methodology). Population and spend for all H3 cells within each zone are summed to produce the cluster's trade area statistics. These aggregated values are the basis for cross-cluster competitive ranking.

## See Also

- [[topic-od-catchment-methodology]]
- [[topic-catchment-ranking-methodology-v3]]
- [[topic-co-location-methodology]]
