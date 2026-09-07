---
schema: foundry-doc-v1
title: "Data overview — location intelligence and GIS data layers"
slug: gis-data-overview
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
short_description: "An orientation to the spatial data layers behind the site-selection map: the point-of-interest, population, and spend inputs, the four-tier predicate-gate scoring they feed, and where each is documented in full."
paired_with: gis/gis-data-overview.es.md
cites:
  - osm-odbl
---

Every Development Site Woodfine shortlists is drawn from a scored map rather than from a market narrative. **The location intelligence data layers** are what that map is made of. Three layers stack on one another: point-of-interest records that locate every retail anchor, a gridded population layer, and a modelled retail-spend layer built on top of it. Together they produce a co-location cluster dataset spanning North American and European markets, in which every cluster carries one of four tiers — Regional, District, Local, or Fringe — assigned by binary predicate gate rather than by an accumulated score. This article is the orientation to those layers: what each contains, how they combine into a tier, and which article documents each in full. Woodfine owns the framework and the resulting dataset; MCorp maintains the data and runs the analysis.

## The three data layers

### Point-of-interest records

The base layer locates the stores. Retail anchor and secondary operator locations are sourced from OpenStreetMap contributors under the Open Database Licence. Four anchor classes carry scoring weight: Hypermarket, the general-merchandise chains such as Walmart, Target, Mercadona, and Tesco; Lifestyle, large-format home and furnishings, of which IKEA is the only chain in the class; Hardware, the home-improvement chains such as Home Depot, Lowe's, and Leroy Merlin; and Warehouse, the membership clubs such as Costco, Sam's Club, and Makro. The chain-to-family mapping is documented in the [[retail-brand-family-taxonomy|retail brand family taxonomy]], and the anchor definitions themselves in [[co-location-anchors|co-location anchors]].

Not every chain on the map changes a grade. Food retailers appear as supporting context without entering the scoring gates, and neighbourhood grocery formats are deliberately excluded, because their density would generate clusters carrying no development signal. [osm-odbl]

### Population

Population comes from published gridded population estimates, which model residents from census microdata and satellite imagery rather than reporting them by administrative boundary. Estimates are aggregated onto a single worldwide grid, so a figure for a cluster in Norway is computed exactly as one in Mexico is. The ingest and aggregation pipeline is documented in [[trade-area-data-sources|trade area data sources]]. The estimate's acknowledged weaknesses — the uniform per-capita assumption, the risk of false precision, and the modifiable areal unit problem — are set out in [[spend-population-provenance|spend and population provenance]], which also states plainly which parts of the chain are live and which are planned.

### Retail spend

Spend is modelled, not observed. Annual per-capita expenditure multipliers, split across grocery, hardware, and wholesale categories, are applied to the population grid. The multipliers are proxies drawn from national household expenditure surveys, expressed in local currency with no foreign-exchange normalisation applied, so a spend ranking is most defensible within a single country.

## From points to scored clusters

Co-located point-of-interest records are grouped into a cluster, the node against which everything downstream is measured. The formation rule is documented in [[co-location-cluster-formation|cluster formation]], and the treatment of two anchors sharing a single parking lot in the [[cluster-deduplication-threshold|cluster deduplication threshold]].

Each cluster is then given two demand zones: a primary zone close to the anchor, and a wider secondary zone beyond it. Both are straight-line bands, not road-network drive times, and the platform labels them as such — a distance band approximates where customers come from, and is not a measured catchment. The band definitions, their rationale, and the planned move to observed origin data are set out in the [[od-catchment-methodology|distance-band methodology]]. Population and spend for every grid cell inside each zone are summed to produce the cluster's trade-area figures.

Those figures are then converted into a rank within the cluster's own country, expressed as a percentile. This is what lets a cluster in a country with a few hundred scored nodes be compared against one in a country with several thousand.

Tier assignment applies four families of binary gate: **composition**, which anchor classes are present; **catchment rank**, the cluster's national percentile on population and spend; **civic**, whether a hospital of the required classification sits within the surrounding ring; and **non-overlap**, whether a stronger nearby cluster already dominates the same node. A cluster must clear every gate its tier requires. Partial results do not accumulate, and a strong showing on one gate does not compensate for a failure on another — which is the discipline predicate gates were introduced to enforce.

The gate tables are not restated here. They are maintained in the [[catchment-ranking-methodology|catchment ranking methodology]], with the vocabulary defined in the [[gis-cluster-scoring-glossary|cluster scoring glossary]] and the development-facing reading in the [[geographic-co-location-methodology|geographic co-location methodology]].

## The four tiers, and the vocabulary they replaced

The tiers are **Regional**, **District**, **Local**, and **Fringe**, highest to lowest. The names borrow from the retail property hierarchy used by the International Council of Shopping Centres, though only "Regional" is a genuine ICSC term; District, Local, and Fringe are the platform's own naming choices. The Spanish-language labels are Regional, Distrital, Local, and Marginal. The full naming history is recorded in the [[co-location-tier-nomenclature|tier nomenclature]].

This tier system replaced a points-based composite scale on 2026-05-16. The retired scale used numeric T1, T2, and T3 labels, and those labels describe no current cluster anywhere in the dataset. Where an article records an event that occurred before that date — [[nordic-uk-coverage|the Nordic and UK coverage expansion]] of May 2026 is the clearest case — it retains the vocabulary that was current on the event date and carries a dated note saying so. The store counts, cluster counts, and dates in those articles are unaffected by the rename; only the tier vocabulary describing them is historical. A T1, T2, or T3 label encountered anywhere in this wiki should be read as a historical record, never as a current grade.

## The three co-location archetypes

The same point, population, and spend layers support three archetypes, each describing a different commercial clustering pattern. **Retail Centres** is the base map product and the foundation of the site-selection dataset: grocery-anchored co-locations, scored through the four-tier gate system described above. **Urban Fringe** identifies concentrations of hardware and industrial-supply retailers where no grocery hypermarket is present, typically near highway interchanges with adjacent industrial land use. **Commuter** identifies commercial concentrations at regional airports and intercity stations beyond the metro core, where the defining demand pattern is park-and-fly or park-and-train rather than retail footfall.

Urban Fringe and Commuter render as overlay layers alongside the Retail Centres base view, so a reviewer sees adjacent market structures together with the core retail map. Each archetype's qualifying signals, disqualifiers, and production status are documented in the [[location-intelligence-archetypes|location intelligence archetypes]].

## Coverage and publication

Coverage grows by ingest, and each expansion is recorded as a dated article rather than folded silently into the dataset. [[nordic-uk-coverage|The Nordic and UK expansion]] records the entry of Norway, Sweden, and the United Kingdom; [[uk-eu-food-retail-coverage|the UK and EU food-retail expansion]] records which grocery chains became visible on the map, and states its own remaining gaps rather than implying completeness. Broader country coverage is summarised in the [[co-location-intelligence-overview|co-location intelligence overview]].

The scored clusters render on the map published at `gis.woodfinegroup.com`, where the full gate tables are also published.

Downstream, the scored dataset is the input to two things a development analyst uses directly: the four-hundred-market qualifying set maintained by the [[about-regional-markets-system|regional markets intelligence system]], and the ranked site shortlist from which Woodfine engages real estate professionals in each identified market to assess land availability and development timeline.

## What this is not

This article is an orientation, not a specification: it names the gate families but states no pass or fail threshold, and it describes the demand zones without restating their distances. Those belong to the canonical methodology articles.

Nor are the layers themselves stronger than their sources. The demand zones are straight-line approximations, not observed catchments; the planned move to reachability along the road network is described in [[trade-area-methodology|trade area methodology]]. The spend layer is modelled from survey averages, not from transaction data. And the dataset is rebuilt on a processing cadence, not served as a live feed.

## See also

- [[geographic-co-location-methodology]]
- [[catchment-ranking-methodology]]
- [[od-catchment-methodology]]
- [[trade-area-data-sources]]
- [[spend-population-provenance]]
- [[location-intelligence-archetypes]]
- [[gis-cluster-scoring-glossary]]
