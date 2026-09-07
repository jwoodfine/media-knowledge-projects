---
schema: foundry-doc-v1
title: "Geographic co-location methodology"
slug: geographic-co-location-methodology
category: site-selection
index_group: site-scoring-and-trade-areas
type: topic
content_type: topic
quality: complete
short_description: "Predicate-gate tier system classifying retail co-location clusters by anchor composition, catchment rank, and civic presence to identify development sites by anchor strength."
status: stable
bcsc_class: current-fact
last_edited: 2026-08-26
editor: pointsav-engineering
language_protocol: PROSE-TOPIC
source_refs:
  - "bfe6fb6bbb557fd15bdb7ffd53bce60e527911eb7658c906df5b69813bdb8747"
paired_with: geographic-co-location-methodology.es.md
cites: []
---

The **Geographic Co-Location Methodology** is the spatial analysis discipline Woodfine applies to identify and classify potential Development Sites across its nine planned jurisdictions: Canada, the United States, Spain, Mexico, Poland, the United Kingdom, Italy, the Nordics, and New Europe. The methodology classifies retail nodes by the proximity and combination of anchor retailers operating in the geography, producing a classified dataset of sites in which development investment is validated by the demonstrable commercial commitments of institutional retailers rather than by speculative demographic projections.

The methodology assigns each cluster to one of four tiers by predicate gate, not by an accumulated score. A cluster earns a tier only when every gate required for that tier passes — anchor composition, catchment rank, and civic presence together, not any one factor alone. This gate structure replaced an earlier points-based scale on 2026-05-16; the retired scale, and its numeric labels, no longer describe any current cluster.

## The Tier System

Each cluster is anchored by a store from one of four anchor classes — Hypermarket, Lifestyle, Hardware, or Warehouse — and is assigned to a tier by clearing that tier's required gates. The tier names follow the retail property hierarchy used by the International Council of Shopping Centres: **Regional**, **District**, **Local**, and **Fringe**, from highest to lowest. The full tier definitions and gate tables are maintained in the [[gis-cluster-scoring-glossary|cluster scoring glossary]] and [[co-location-tier-nomenclature|tier nomenclature]]; the summary below states what a development analyst needs to read the map.

### Regional and District — the qualifying tiers for site selection

**Regional** clusters combine a Warehouse or Lifestyle anchor with a Hypermarket anchor, rank in the top decile of their country by primary catchment population, and have a regionally classified hospital nearby. This is the highest-conviction tier: the simultaneous presence of multiple independent anchor categories, at a nationally significant catchment scale, confirms that several institutional operators have reached the same conclusion about the geography.

**District** clusters combine a Hypermarket anchor with a Hardware or Warehouse anchor, rank in the top quartile of their country by primary catchment population, and have hospital access within the civic ring. District clusters are qualified candidates: the co-location and catchment conditions are met, but at a sub-regional rather than a nationally significant scale.

### Local and Fringe

**Local** clusters contain a Hardware or Warehouse anchor, rank in the top half of their country by primary catchment population, and have any hospital within the civic ring. Local clusters confirm co-location and community-level catchment support without qualifying at District or Regional scale.

**Fringe** is assigned to any cluster that does not clear the gates for Regional, District, or Local. A Fringe cluster may still show retail co-tenancy; it lacks the catchment reach, composition, or civic support the higher tiers require.

## Non-Overlap Radius

Two nearby clusters are compared for overlap using a fixed 3.0 km radius disk centred on each. When the overlap between two clusters' disks exceeds the non-overlap gate's limit, the weaker cluster is held below the tier its composition would otherwise earn — preventing a single strong node from being double-counted as several separate clusters. This single radius convention applies uniformly; it is not adjusted upward or downward by how many clusters currently qualify at a given tier.

## Dataset Output Metrics

For each Primary Target entry, the geographic co-location output records: the city, town, or municipality of the Primary Target; the population of the surrounding community; the sales per square foot of the Primary Target; and the global ranking of that Primary Target by sales per square foot across all Primary Target entries in the dataset. No additional demographic categories are included in the geographic co-location output — demographic profiling is a separate analytical step addressed by the [[optimum-mosaic-demographic-profiling|Optimum Mosaic methodology]].

### Ranking and shortlist production

The output is then ranked to balance cluster tier, anchor proximity, and the absolute sales per square foot of the Primary Target. The ranking produces the site shortlist from which Woodfine engages real estate professionals in each identified market to assess land availability and development timeline.

## Required Site Count by Jurisdiction

The site shortlist requirements are calibrated to the planned capital raises and construction timelines of each Direct-Hold Solution, with a jurisdiction-specific required development count set for Canada, the United States, Spain, and Mexico across the equity and debt financings planned over the multi-year build-out.

### Shortlist ratio and land availability

Because not every high-ranked Primary Target will have available land adjacent to its site, and some available sites will carry rezoning or permitting timelines extending three to seven years, the site shortlist must exceed the required development count by a substantial margin. Enough shortlisted candidates are carried per required site to absorb land-availability and entitlement attrition.

Four separate datasets are maintained, one per jurisdiction, reflecting the distinct retail landscapes of Canada, the United States, Spain, and Mexico.
