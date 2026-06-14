---
schema: foundry-doc-v1
slug: topic-regional-markets-system
aliases:
  - topic-regional-markets-system
title: "Regional Markets Intelligence System"
language: en
language_protocol: PROSE-TOPIC
category: governance
type: reference
content_type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
short_description: "Reference article for the co-location analysis system that identifies and ranks suburban retail markets in North America and Europe."
paired_with: topic-regional-markets-system.es.md
last_edited: 2026-05-30
editor: editorial
---

# Regional Markets Intelligence System

The Regional Markets Intelligence System is a continental-scale geographic analysis framework that identifies suburban retail markets — named suburbs and satellite municipalities lying within commuting distance of major metropolitan centres — defined by the convergence of large-format retail anchors, civic infrastructure, and demographic catchment.

The research addresses a gap in institutional commercial real estate analysis. Major research organisations, including Oxford Economics, CBRE, and Colliers International, produce extensive coverage of primary metro markets: London, Paris, New York, Chicago, Dallas, Toronto, and their immediate urban cores. The suburban ring — the belt of named municipalities 15 to 80 kilometres from a major metro centre — is systematically underanalysed by institutional research. This is where large-format retail, hospital systems, and university campuses co-locate in patterns that function as leading indicators of demographic and economic activity at the sub-metropolitan scale. The Regional Markets dataset is the analytical surface for that suburban ring.

The current dataset spans 6,493 co-location clusters across eighteen countries in North America and Europe, classified into three compositional tiers (T1, T2, T3) and aggregated into 4,436 named Regional Markets.

## Dataset Scope

The current build covers 6,493 co-location clusters across eighteen countries on two continents.

| Region | Countries |
|---|---|
| North America | United States, Canada, Mexico |
| Europe — west and south | Spain, Italy, Greece, France, Germany, Portugal, Netherlands, Austria |
| Europe — Nordic | Sweden, Norway, Denmark, Finland, Iceland |
| Europe — central / east | Poland, United Kingdom |

Cluster counts by tier: **T1 = 1,746** (Regional anchors), **T2 = 2,726** (District anchors), **T3 = 2,021** (Local anchors). The build pipeline draws on four primary data sources.

**OpenStreetMap (ODbL licence).** Retail chain locations filtered by Wikidata QID via the Overpass API. The current ingest covers more than sixty chains spanning hypermarkets, hardware superstores, warehouse clubs, electronics retailers, sporting-goods stores, and pharmacies.

**Overture Maps Foundation (CDLA Permissive 2.0).** Civic anchor locations extracted from the Places dataset using the `taxonomy.primary` field. Current coverage includes 27,833 medical and 28,846 higher-education records across the eighteen countries.

**Kontur Population 2023 (CC BY 4.0).** A global H3 resolution-8 population hex grid covering all eighteen countries; aggregated to H3 resolution-7 (≈1.22 km² per cell) for catchment calculations.

**WorldPop 100-metre raster (2026 release, CC BY 4.0).** Used in combination with per-country spend multipliers from BLS (United States), Statistics Canada, and Eurostat household budget surveys to model grocery, hardware, and wholesale spend potential at the catchment level.

The clustering methodology is a two-pass DBSCAN: a first pass identifies hypermarket and full-anchor cores, a second pass adds peripheral hardware and warehouse-club anchors within a span constraint.

## Co-location Tier System

Each cluster is assigned one of three tiers based on the composition of retail anchors present within the cluster boundary.

| Tier | Label | Composition rule |
|---|---|---|
| **T1** | Regional | Hypermarket + hardware + warehouse-club (or full equivalent across three independent anchor categories) |
| **T2** | District | Hypermarket + hardware (two independent anchor categories) |
| **T3** | Local | Any single qualifying anchor category |

The tier rule is compositional rather than count-based. A site with four co-located hypermarket banners and no hardware or warehouse-club anchor remains T3, because the compositional signal that distinguishes regional draw from local convenience is the presence of *independent* anchor categories, not the count of stores within a single category.

**Geometric span ranking within tiers.** Within each tier, clusters are ordered by `span_km` — the diameter of the smallest enclosing circle that contains all member anchors. Compact clusters (`span_km` below 2.5) rank ahead of dispersed clusters. A cap is applied to prevent the algorithm from extending an arterial corridor into a single notional cluster.

**Anchor categories.** Six anchor categories are recognised in the current build: `hypermarket`, `hardware`, `warehouse_club`, `electronics`, `sporting_goods`, and `pharmacy`. Hypermarket, hardware, and warehouse-club are weighted as tier-determining; electronics, sporting-goods, and pharmacy are recognised as supporting anchors and contribute to the descriptive fields but do not alter tier classification.

## Regional Markets

A Regional Market is a named municipality or equivalent administrative unit that contains one or more co-location clusters and lies within commuting distance of a major metropolitan centre. Three settlement types are distinguished:

| Type | Distance from major metro | Ranking |
|---|---|---|
| **Metro-core** | < 15 km | Excluded from Top 400 (covered by institutional metro-market research) |
| **Suburban-regional** | 15–80 km | Ranked in the Top 400 (the research gap) |
| **Standalone-secondary** | > 80 km | Excluded from Top 400 (separate analysis category) |

The suburban-regional type is the Top 400 pool. Markets closer than 15 km from a major metro centroid are treated as extensions of the metro core. Markets further than 80 km from any major metro centroid are standalone secondary cities that function independently rather than as satellites; they are tracked but ranked separately. A geographic coherence constraint excludes name-collision aggregations: any settlement whose constituent clusters span more than 200 km is excluded as an administrative artefact rather than a functioning market.

**Total count: 4,436 Regional Markets** (all three types combined). Of these, **2,327 are in North America** and **2,109 are in Europe**.

## Top 400 Composite Ranking

The Top 400 Regional Markets list is a composite ranking of suburban-regional settlements. The list is produced separately for North America and Europe, yielding two ranked surfaces of 400 markets each. The suburban-regional classification (15–80 km, described above) is a pre-filter, not a score component: every market that reaches the scoring stage is already in the correct proximity band.

**Composite score formula.**

```
score = tier_score × civic_multiplier × confidence_factor

where:
  tier_score = (T1 × 4) + (T2 × 2) + (T3 × 1)
  civic_multiplier = 1.5  if any medical or higher-education anchor present, else 1.0
  confidence_factor = 1.0  for high-confidence chain coverage
                      0.7  for low-confidence chain coverage
```

**Rationale.** The composite score identifies markets that combine supply-side anchor strength with civic infrastructure. The tier weighting (4 / 2 / 1) reflects the compositional hierarchy: a single T1 cluster contributes more than two T2 clusters because the simultaneous presence of three independent anchor categories — hypermarket, hardware, and warehouse club — is a stronger commercial-density signal than the presence of any two. The civic multiplier rewards the presence of medical or academic anchors, which indicate a functioning sub-metropolitan service centre rather than a pure retail strip.

No metro-distance multiplier appears in the formula. Under a previous iteration of the methodology, a distance bonus inadvertently caused standalone secondary cities to outrank genuine suburbs of major metros. The current design separates classification from scoring: the 15–80 km filter puts suburban markets in the ranked pool; the formula then ranks them by anchor depth and civic quality alone.

**Current top results.** North America: rank 1 Plano, TX (suburb of Dallas, 28 km, score 25.5); rank 2 Mesa, AZ (suburb of Phoenix, 31 km, score 22.5); rank 3 Frisco, TX (suburb of Dallas, 44 km, score 21.0). Europe: rank 1 Chemnitz (suburb of Dresden, 64 km, score 18.0); rank 5 Krefeld (suburb of Düsseldorf, 19 km, score 12.0).

The full ranked lists are published separately: see [Top 400 Regional Markets — North America](topic-top-400-regional-markets-na) and [Top 400 Regional Markets — Europe](topic-top-400-regional-markets-eu).

## Civic Infrastructure Layer

The civic infrastructure layer adds medical and higher-education anchor presence to the cluster member data. The source is the Overture Maps Foundation Places dataset, queried for the `healthcare` and `higher_education` primary categories.

**Coverage.** 27,833 medical records and 28,846 higher-education records across the eighteen countries.

**Encoding.** Civic presence is encoded as a binary flag per cluster: if any cluster member is classified as medical or higher-education, the cluster carries `civic = True`. The Regional Market inherits the civic flag from any constituent cluster. The civic flag is the input to the 1.5× civic multiplier in the composite score.

The civic layer is conceptually distinct from the retail layer. A hospital adjacent to a hypermarket-and-hardware cluster does not turn T2 into T1 — the tier classification is anchor-composition only. The civic flag operates orthogonally as a market-quality signal.

## AEC Data Layers

The AEC (architecture, engineering, construction) data layers add climate, regulatory, and ecological context to each Regional Market and to the surrounding development envelope. Four layers are currently delivered; two further layers are in preparation.

**Delivered layers.**

| Layer | Source | Coverage |
|---|---|---|
| ASHRAE 169-2013 climate zones | ASHRAE standard, US extent | 94.4% of US Regional Markets |
| EU regulatory energy climate zones | Per-country building-energy regulations | Variable — Germany and France near 100%, Spain and United Kingdom partial |
| Köppen-Geiger climate class | Beck et al. 2018 global raster (CC BY 4.0) | 100% of all Regional Markets |
| WWF Ecoregions 2017 | World Wildlife Fund global vector (CC BY 4.0) | 99.5% of all Regional Markets |

**Layers in preparation.**

| Layer | Source | Status |
|---|---|---|
| Seismic peak ground acceleration | USGS (United States) and EFEHR (Europe) | Re-run scheduled for 1 June 2026 |
| Flood hazard | FEMA (United States) and EU JRC | Build scheduled for 31 May 2026 |

## POI Data Schema

The platform operates two record classes within its location data layer: service-business records (retail chains) and service-places records (civic anchors).

**Service-business records.** Each record represents a single retail chain location and is identified by a `chain_id` linking to a chain configuration file and by a `brand_wikidata` field holding the Wikidata QID for the brand. The Wikidata QID is the canonical cross-source chain identifier because it is brand-level rather than name-level; two storefronts with different local-language spellings but the same QID belong to the same chain.

**Service-places records.** Civic anchors — hospitals, universities, airports — ingested from Overture Maps using `taxonomy.primary` as the category filter.

**Shared core fields.**

| Field | Type | Notes |
|---|---|---|
| `location_name` | string | Display name with category fallback |
| `brand_wikidata` | string or null | Wikidata QID; null for civic places with no brand identity |
| `street_address` | string or null | Freeform address |
| `city` | string or null | Locality |
| `region` | string or null | Province, state, or NUTS-3 region |
| `iso_country_code` | string | ISO 3166-1 alpha-2 country code |
| `latitude`, `longitude` | float | WGS 84, 7 decimal places |
| `naics_code` | string | NAICS classification |
| `source` | string | `osm` or `overture` |
| `confidence` | float | OSM fixed 0.85; Overture from dataset |

**Spatial deduplication.** Records within a 100-metre radius per chain are deduplicated, retaining the record with the most complete address fields. A second pass at 25 metres across different `chain_id` values sharing the same `brand_wikidata` QID identifies sub-format or co-branded stores.

## Catchment Model

The catchment model assigns each cluster a primary and secondary trade area defined by crow-flies radius from the cluster centroid.

| Ring | Radius | Role |
|---|---|---|
| Primary | 35 km | Local-residence trade area |
| Secondary | 150 km | Regional draw |

Catchment population and spend are calculated by intersecting these rings with H3 resolution-7 hexagons (≈1.22 km² per cell) populated from Kontur Population 2023 and modelled spend from WorldPop combined with per-country household-budget multipliers.

**Ranking dimensions.** Each cluster receives four independent ranks across the dataset: population rank, grocery rank, hardware rank, and wholesale rank — each based on combined primary and secondary catchment totals.

**Mobility-derived catchments.** A mobility-defined catchment layer sits alongside the radius-based model. For United States clusters, the US LODES origin-destination employment dataset provides a worker-commute catchment per H3 cell. For Spain, the Ministerio de Transportes (MITMA) mobility dataset provides a parallel surface.

## Forward-Looking Work

Work planned or intended for the next iterations of the system.

**Climate and hazard layer completion.** The seismic peak-ground-acceleration layer and the flood-hazard layer are scheduled for build in May–June 2026. Once delivered, every Regional Market will carry a complete envelope record covering climate zone, ecoregion, seismic design category, and flood-zone designation.

**OLS regression on span_km.** A cluster-level ordinary-least-squares regression of `span_km` against catchment population density, modelled spend, and mobility-derived activity is in preparation. Country fixed effects and an urban-core versus peri-urban interaction term are intended.

**Per-market article surfaces.** Dedicated wiki articles for each of the 400 Regional Markets in the Top-400 list are planned. The articles are intended to combine the data fields described here with locally-resolved narrative drawn from public sources.

**FX normalisation for cross-country spend.** A foreign-exchange normalisation pass on the modelled spend layer is planned, enabling cross-currency catchment ranking and direct comparison of grocery, hardware, and wholesale spend between countries.

---

*Reference data current as of 30 May 2026. Sources: OpenStreetMap contributors (ODbL); Overture Maps Foundation (CDLA Permissive 2.0); Kontur Population 2023 (CC BY 4.0); WorldPop 2026 (CC BY 4.0); Beck et al. 2018 Köppen-Geiger raster (CC BY 4.0); WWF Ecoregions 2017 (CC BY 4.0); US LODES (public domain); Spain MITMA mobility (open data).*
