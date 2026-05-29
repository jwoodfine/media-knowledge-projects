---
schema: foundry-doc-v1
title: "Regional Name Resolution Architecture"
slug: topic-regional-name-resolution-architecture
category: governance
type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: PROSE-TOPIC
last_edited: 2026-05-25
editor: pointsav-engineering
short_description: "Each co-location cluster is labelled with a human-readable regional name — a North American Metropolitan Area, a European NUTS-3 region, a Mexican municipio, a Canadian Census Subdivision. That name is the output of a layered offline reverse-geocoding pipeline that draws from five open boundary datasets without requiring external API calls."
paired_with: topic-regional-name-resolution-architecture.es.md
cites:
  - osm-odbl
  - overture-maps-cdla-2-0
  - ni-51-102
  - osc-sn-51-721
---

The [[topic-co-location-methodology|co-location]] map labels each cluster with a human-readable regional name — a North American Metropolitan Area, a European NUTS-3 region, a Mexican municipio, a Canadian Census Subdivision. The name is not a single field on the source data; it is the output of a layered offline reverse-geocoding pipeline. This article documents the data sources, the lookup order, and the post-processing that produces the names visible on the platform; the cluster itself is produced by the [[topic-co-location-ranking-system|deterministic ranking system]] after [[topic-cluster-deduplication-threshold|deduplication]].

## The Five Boundary Layers

Each cluster anchor's coordinates are tested against five boundary datasets in a country-specific order:

| Layer | Source | Coverage | Granularity |
|---|---|---|---|
| `us_cbsa.geojson` | US Census Bureau TIGER GENZ2023 | United States | Core-Based Statistical Areas (Metro + Micropolitan) |
| `ca_cma.geojson` | Statistics Canada 2021 Census | Canada | Census Metropolitan Areas |
| `ca_csd.geojson` | GADM 4.1 admin-3 (UC Davis Open Data) | Canada | Census Subdivision proxies (municipalities) |
| `mx_municipio.geojson` | GADM 4.1 admin-2 (UC Davis Open Data) | Mexico | Municipios |
| `eu_nuts3.geojson` | Eurostat GISCO 2021 | EU + UK + EFTA + Western Balkans | NUTS-3 regions |
| `fallback_ne_admin1.geojson` | Natural Earth 10m | Global | Admin-1 (states / provinces) |

All files load once at engine initialisation. Spatial indexes accelerate point-in-polygon lookups to O(log N) per query.

## Country-Specific Routing

The engine routes each cluster's anchor coordinates by ISO country code:

- **United States**: CBSA lookup. If a match is found, the CBSA name is formatted (state suffix stripped, "Metro Area" appended if absent).
- **Canada**: Census Subdivision lookup first (admin-3). When both a Census Subdivision and the surrounding Census Metropolitan Area match and differ, the result is composed: "Strathcona County, Edmonton". When only one matches, that name is returned alone.
- **Mexico**: Municipio lookup (admin-2). On a match, the municipio name is returned with Spanish-text post-processing applied. On a miss, the engine falls through to the Natural Earth state-level fallback.
- **European Union, United Kingdom, EFTA, Western Balkans**: NUTS-3 lookup.
- **Fallback**: Natural Earth admin-1 for any country not covered by the layered files. Returns state or province names.

Each layer has a tolerance built into its spatial query: when a point falls just outside any polygon — for instance, a coastal store on a fjord edge — the engine accepts the nearest polygon within approximately 15 km. This prevents legitimate stores in coastal configurations from falling through to the fallback layer.

## Post-Processing the Raw Names

Boundary files carry source-language names with concatenated affixes that are not human-readable. Three transformations clean them.

**CamelCase splitter.** GADM 4.1 admin-2 and admin-3 names are stored without word separators. "StrathconaCounty" becomes "Strathcona County".

**Spanish preposition splitter.** Mexican municipio names occasionally carry preposition concatenation: "Bocadel Río", "Apetatitlánde Antonio Carvajal". A regular expression detects the prepositions *de*, *del*, *la*, *las*, *el*, *los* glued to a preceding lowercase character and inserts a space before the preposition.

**Period normaliser.** "Gustavo A.Madero" is normalised to "Gustavo A. Madero".

A separate explicit-override dictionary handles cases that fall outside the regular-expression scope: Greek names transliterated to English, Finnish suffix simplifications, Polish prefix stripping, Belgian bilingual name normalisation. This dictionary held approximately 200 entries as of mid-2026.

## Mexican Display Overrides

Some Mexican municipio names are technically correct but not the form a Spanish-speaking reader expects on a map. A small display-override dictionary maps INEGI Zona Metropolitana names to their common short forms — "Zona Metropolitana del Valle de México" becomes "Ciudad de México", "Zona Metropolitana de Guadalajara" becomes "Guadalajara".

## Scale

After the layered routing and post-processing, the engine produces approximately 1,200 unique region names across the operational footprint as of May 2026. By country: 671 distinct US Metropolitan Areas, 245 Canadian regions (Census Subdivisions and Census Metropolitan Areas combined), 104 Mexican Municipios, and several hundred European NUTS-3 regions. Each region name appears on the map in cluster pop-ups and the inspector panel.

## See Also

- [[topic-co-location-methodology]]
- [[topic-cluster-deduplication-threshold]]
