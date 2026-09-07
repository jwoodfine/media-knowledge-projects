---
schema: foundry-doc-v1
title: "Trade area data sources — population and spend"
slug: trade-area-data-sources
category: gis
index_group: data-overview-and-sources
type: topic
content_type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: PROSE-TOPIC
last_edited: 2026-09-04
editor: pointsav-engineering
short_description: "Population estimates from Kontur Population and annual per-capita spend proxies from national household surveys underpin the trade area statistics for each co-location cluster."
paired_with: gis/trade-area-data-sources.es.md
cites:
  - osm-odbl
---

Population estimates and retail spend estimates are the two input layers that drive trade area statistics for each [[co-location-methodology|co-location]] cluster. Both are derived from publicly available data sources and applied at the H3 resolution-7 hexagonal grid level, per the [[od-catchment-methodology|distance-band methodology]]. Together they supply the population and spend axes used by the [[co-location-ranking-system|deterministic ranking system]] and the [[catchment-ranking-methodology|catchment ranking methodology]].

## Population Data

Population estimates are sourced from **Kontur Population**, an H3-native population dataset delivered as per-country files at H3 resolution-8 — a finer grid than the resolution-7 hexagons the platform aggregates catchments to. Unlike a raster-based product, Kontur's population values are already bound to hexagon geometry at ingestion, so no raster-to-hexagon reprojection step is required.

### Processing pipeline

1. **Per-country ingestion:** Each country's resolution-8 population file is read directly; only cells with a positive population value are retained.

2. **H3 rollup:** Each resolution-8 cell is resolved to its resolution-7 parent hexagon, and population values are summed across all resolution-8 children sharing a parent. H3 resolution-7 cells have an average area of 5.16 km².

3. **Output:** Population is aggregated to one record per resolution-7 cell, giving each cell's coordinates, summed population, and the set of countries contributing to it.

### Countries covered

United States, Canada, Mexico, Spain, France, Germany, Great Britain, Italy, Netherlands, Austria, Poland, Greece, and Portugal — 13 countries as of the current pipeline version. This is the set with published per-capita spend multipliers. It is a subset of the platform's broader co-location footprint, which spans 24 countries as of the most recent full processing run (2026-08-06). See [[co-location-intelligence-overview]] for full country coverage.

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
| Denmark | €3,500\* | €1,200\* | €1,100\* | DKK\* |
| Iceland | €4,000\* | €1,500\* | €1,500\* | ISK\* |
| Poland | PLN 8,000 | PLN 2,000 | PLN 2,500 | PLN |

Multipliers are expressed in local currency. Cross-country spend comparisons require foreign-exchange normalisation, which is not applied in the current pipeline. Rankings are most meaningful within a single country or within the eurozone.

\* Denmark and Iceland are not eurozone members; their multipliers are shown here still denominated in euros pending re-derivation in DKK and ISK, and are not yet comparable to the eurozone figures above them.

### Retail categories

- **Grocery:** Supermarkets, hypermarkets, food cooperatives, and food sections of general merchandise retailers.
- **Hardware:** Home improvement, building materials, and garden centres.
- **Wholesale:** Members-only warehouse clubs and cash-and-carry retailers.

### Processing pipeline

Spend values are computed at the H3 resolution-7 level by multiplying each cell's aggregated population by the per-capita multipliers for its country, producing one record per H3 cell with population and estimated spend by category (grocery, hardware, wholesale) in local currency.

## Catchment Aggregation

For each co-location cluster, primary and secondary catchment zones are defined by crow-flies distance rings (see: O-D Catchment Methodology). Population and spend for all H3 cells within each zone are summed to produce the cluster's trade area statistics. These aggregated values are the basis for cross-cluster competitive ranking.

## Point-of-interest data

The retail anchor and secondary operator locations that form co-location cluster centroids are sourced from **OpenStreetMap contributors** under the [Open Database Licence (ODbL)](https://opendatacommons.org/licenses/odbl/). Point-of-interest data is distinct from the population and spend layers described above; it provides the geographic seed points from which catchment zones are measured. The full data-attribution statement covering all pipeline layers appears in [[about-regional-markets-system]]. [osm-odbl]

## References

- [Trade area](https://en.wikipedia.org/wiki/Trade_area) — Wikipedia, accessed 2026-06-14
- [Kontur Population Dataset](https://data.humdata.org/dataset/kontur-population-dataset) — Kontur, accessed 2026-09-07
- [H3: Uber's Hexagonal Hierarchical Spatial Index](https://h3geo.org/) — H3 Geo, accessed 2026-06-14

*Wikipedia content reproduced under [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/).*

*Kontur Population data licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).*

*OpenStreetMap data © OpenStreetMap contributors, licensed under ODbL.*

## See also

- [[od-catchment-methodology]]
- [[catchment-ranking-methodology]]
- [[co-location-methodology]]

*OpenStreetMap data © OpenStreetMap contributors, licensed under ODbL.*
