---
schema: foundry-doc-v1
slug: about-regional-markets-system
title: "Regional Markets intelligence system"
language: en
language_protocol: PROSE-TOPIC
category: markets
index_group: coverage-methodology
type: reference
content_type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
short_description: "Reference article for the co-location analysis system that identifies suburban retail markets in North America and Europe."
paired_with: markets/about-regional-markets-system.es.md
last_edited: 2026-08-26
editor: editorial
---

The Regional Markets Intelligence System is a continental-scale geographic analysis framework that identifies suburban retail markets — named suburbs and satellite municipalities lying within commuting distance of major metropolitan centres — defined by the convergence of large-format retail anchors, civic infrastructure, and demographic catchment.

The research addresses a gap in institutional commercial real estate analysis. Established research coverage concentrates on primary metro markets — London, Paris, New York, Chicago, Dallas, Toronto, and their immediate urban cores. The belt of named municipalities beyond those cores is analysed far less consistently. This is where large-format retail, hospital systems, and university campuses co-locate in patterns that function as leading indicators of demographic and economic activity at the sub-metropolitan scale. The Regional Markets dataset is the analytical surface for that belt.

The current dataset spans several thousand co-location clusters across 24 countries in North America and Europe, classified into four tiers (Regional, District, Local, Fringe) and aggregated into named Regional Markets. The Top 400 is the flagship published output of this system: a curated, editorially-selected subset of roughly 400 markets for each continent. Selection method below.

## Dataset Scope

The current build covers several thousand co-location clusters across 24 countries on two continents.

| Region | Countries |
|---|---|
| North America | United States, Canada, Mexico |
| Europe — west and south | Spain, Italy, Greece, France, Germany, Portugal, Netherlands, Austria |
| Europe — Nordic | Sweden, Norway, Denmark, Finland, Iceland |
| Europe — central | Poland, United Kingdom, Czechia, Hungary, Slovakia |
| Europe — southeast | Bulgaria, Croatia, Romania |

Clusters are counted by tier — Regional, District, and Local anchors — on the GIS platform rather than restated here, because a wiki snapshot goes stale between processing runs. The build pipeline draws on four primary data sources.

### Primary data sources

**OpenStreetMap (ODbL licence).** Retail chain locations filtered by Wikidata QID via the Overpass API. The current ingest covers more than sixty chains spanning hypermarkets, hardware superstores, warehouse clubs, electronics retailers, sporting-goods stores, and pharmacies.

**Overture Maps Foundation (CDLA Permissive 2.0).** Civic anchor locations extracted from the Places dataset, covering medical and higher-education sites across the 24 countries.

**Kontur Population 2023 (CC BY 4.0).** A global H3 resolution-8 population hex grid covering all 24 countries; aggregated to H3 resolution-7 (≈1.22 km² per cell) for catchment calculations.

**Per-country spend multipliers** from BLS (United States), Statistics Canada, and Eurostat household budget surveys are applied to the same Kontur-derived population figure to model grocery, hardware, and wholesale spend potential at the catchment level — spend is not drawn from a separate population source.

Clusters are formed in two passes: the first identifies hypermarket and full-anchor cores, the second adds peripheral hardware and warehouse-club anchors that fall within the cluster's span.

## Co-location Tier System

Each cluster is assigned one of four tiers by clearing a set of predicate gates spanning anchor composition, catchment population rank, civic infrastructure, and non-overlap with neighbouring clusters. Full methodology: [[co-location-tier-system]].

| Tier | Label | Composition rule |
|---|---|---|
| **T1** | Regional | Hypermarket + hardware + warehouse-club (or full equivalent across three independent anchor categories), plus catchment population in the highest national band and a regional hospital within the civic ring |
| **T2** | District | Hypermarket + hardware (two independent anchor categories), plus catchment population in a high national band and hospital access within the civic ring |
| **T3** | Local | Any single qualifying anchor category, plus catchment population above the national midpoint and any hospital within the civic ring |
| **T4** | Fringe | Retail co-tenancy is present, but catchment reach, composition, or civic support falls short of Local |

The tier rule is compositional rather than count-based. A site with four co-located hypermarket banners and no hardware or warehouse-club anchor remains T3, because the compositional signal that distinguishes regional draw from local convenience is the presence of *independent* anchor categories, not the count of stores within a single category.

### Geometric span and anchor categories

**Span ordering within tiers.** Within each tier, clusters are ordered by span — the diameter of the smallest circle containing all member anchors. Compact clusters are classified ahead of dispersed ones, because anchors within walking or short-driving distance of each other represent a genuinely shared trade position. An upper limit prevents a long arterial corridor being treated as one cluster.

**Anchor categories.** Six anchor categories are recognised in the current build: `hypermarket`, `hardware`, `warehouse_club`, `electronics`, `sporting_goods`, and `pharmacy`. Hypermarket, hardware, and warehouse-club are weighted as tier-determining; electronics, sporting-goods, and pharmacy are recognised as supporting anchors and contribute to the descriptive fields but do not alter tier classification.

## Regional Markets

A Regional Market is a named municipality or equivalent administrative unit that contains one or more co-location clusters. Each market records the metropolitan centre it is measured against and its straight-line distance from that centre.

**Distance is recorded, not gated.** It describes where a market sits; it does not decide whether the market qualifies. Across the published set, recorded distances run from roughly 12 to nearly 700 kilometres, with a median near 80. Markets close enough to read as extensions of a metro core and markets several hundred kilometres from any major centre both appear in the published set, because both can carry the anchor composition the framework selects on.

Two settlement relationships are distinguished descriptively. Most markets are satellites, recorded against the metropolitan centre they relate to. A smaller group are standalone regional centres — places that function independently rather than as satellites, and that are published on the same terms as any other qualifying market.

A geographic coherence rule excludes name-collision aggregations: a settlement whose constituent clusters are scattered far too widely to form one trading location is treated as an administrative artefact rather than a functioning market.

## Top 400 Qualification Method

What puts a market in the Top 400 is the composition of retail anchors that have already converged on it. The set is produced separately for North America and Europe, yielding two lists of 400 markets each, ordered alphabetically rather than by any score. No rank or score field is published for any market.

### Qualification

A market qualifies on the mix of independent anchor categories present across its co-location clusters — the same compositional logic behind the tier system, applied at market rather than cluster level. A market isolated from other qualifying markets is assessed on the same compositional basis, so that a genuine regional centre is not excluded for having no qualifying neighbours. The specific gate predicates are platform logic and are not restated here.

Each continent's 400 are drawn from a larger qualifying pool: 650 markets across fifteen countries in Europe, and 1,121 across three in North America. Where the qualifying pool exceeds 400, the markets with the strongest anchor composition are published. Per-country counts are a result of that cutoff, not a quota set in advance.

A composite score exists internally to support selection but is not published and is not a market-facing ranking. It has no bearing on how a market is described in this wiki.

**No metro-distance term participates in selection.** Under a previous iteration of the methodology, a distance bonus inadvertently caused standalone secondary cities to outrank genuine suburbs of major metros. That term was removed. Distance is now recorded against each market as descriptive context, and anchor composition alone determines whether a market qualifies. Population and consumer-spend figures are likewise descriptive and do not participate in selection.

The full lists are published separately: see [[atlas-top-400-north-america|Top 400 Regional Markets — North America]] and [[atlas-top-400-europe|Top 400 Regional Markets — Europe]].

## Civic Infrastructure Layer

The civic infrastructure layer adds medical and higher-education anchor presence to the cluster member data. The source is the Overture Maps Foundation Places dataset.

**Coverage.** Tens of thousands of medical and higher-education records across the 24 countries. Current counts are published live on the GIS platform.

**Encoding.** Civic presence is recorded as a simple yes or no per cluster: a cluster carries it if any member site is medical or higher-education, and a Regional Market inherits it from any of its clusters. It is a descriptive field, not a public ranking input.

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

## Catchment Model

The catchment model assigns each cluster a primary and secondary trade area defined by crow-flies radius from the cluster centroid.

| Ring | Radius | Role |
|---|---|---|
| Primary | 35 km | Local-residence trade area |
| Secondary | 150 km | Regional draw |

Catchment population and spend are calculated by intersecting these rings with H3 resolution-7 hexagons (≈1.22 km² per cell) populated from Kontur Population 2023; spend is modelled from that same population figure combined with per-country household-budget multipliers.

### Catchment dimensions and mobility catchments

**Catchment dimensions.** Each cluster carries four independent catchment measures: population, grocery spend, hardware spend, and wholesale spend — each based on combined primary and secondary catchment totals. These are descriptive dataset fields, not a published ranking.

**Mobility-derived catchments.** A mobility-defined catchment layer sits alongside the radius-based model. For United States clusters, the US LODES origin-destination employment dataset provides a worker-commute catchment per H3 cell. For Spain, the Ministerio de Transportes (MITMA) mobility dataset provides a parallel surface.

## Forward-Looking Work

Work planned or intended for the next iterations of the system.

**Climate and hazard layer completion.** The seismic peak-ground-acceleration layer and the flood-hazard layer are scheduled for build in May–June 2026. Once delivered, every Regional Market will carry a complete envelope record covering climate zone, ecoregion, seismic design category, and flood-zone designation.

**Regression on cluster span.** A cluster-level regression of geometric span against catchment population density, modelled spend, and mobility-derived activity is in preparation, intended to test how tightly anchor clustering tracks underlying demand.

**Per-market article surfaces.** Dedicated wiki articles for each of the 400 Regional Markets in the Top-400 list are planned. The articles are intended to combine the data fields described here with locally-resolved narrative drawn from public sources.

**FX normalisation for cross-country spend.** A foreign-exchange normalisation pass on the modelled spend layer is planned, enabling direct comparison of grocery, hardware, and wholesale spend between countries.

---

*Reference data current as of 30 May 2026. Sources: OpenStreetMap contributors (ODbL); Overture Maps Foundation (CDLA Permissive 2.0); Kontur Population 2023 (CC BY 4.0); Beck et al. 2018 Köppen-Geiger raster (CC BY 4.0); WWF Ecoregions 2017 (CC BY 4.0); US LODES (public domain); Spain MITMA mobility (open data).*

## See Also

- [[regional-market-definition|Regional market definition]]
- [[co-location-methodology|Co-location Methodology]]
- [[co-location-intelligence-overview|Co-location Intelligence Overview]]
- [[od-catchment-methodology|Distance-Band Methodology]]
- [[atlas-top-400-north-america|Top 400 Regional Markets — North America]]
- [[atlas-top-400-europe|Top 400 Regional Markets — Europe]]
- [[development-regions|Development Regions]]
