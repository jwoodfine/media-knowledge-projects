---
schema: foundry-doc-v1
title: "Composition-based catchment ranking methodology"
slug: catchment-ranking-methodology
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
short_description: "The current predicate-gate system that assigns each co-location cluster to one of four tiers — Regional, District, Local, Fringe — using anchor composition, national catchment rank, civic infrastructure, and spatial independence, introduced May 2026 to replace an earlier composite-score model."
paired_with: site-selection/catchment-ranking-methodology.es.md
cites:
  - osm-odbl
  - overture-maps-cdla-2-0
  - ni-51-102
  - osc-sn-51-721
---

The [[co-location-methodology|co-location]] tier system assigns each cluster to one of four tiers — Regional, District, Local, or Fringe (labelled per the [[co-location-tier-nomenclature|tier nomenclature]]) — using binary predicate gates rather than a composite score. A cluster must pass every gate in a tier's gate set to qualify for that tier; partial scores do not accumulate. This methodology describes the current implementation, introduced in May 2026. It complements the [[co-location-ranking-system|deterministic ranking system]] and draws its trade-area inputs from the [[od-catchment-methodology|distance-band methodology]] and the [[trade-area-data-sources|trade-area data sources]].

## Why Predicate Gates Replace Composite Scores

The prior system assigned tiers by combining several weighted signals into a single composite score. The result was internally consistent but difficult to explain: a cluster could reach a higher tier on the strength of one favourable signal even where it lacked the population catchment and civic infrastructure that the tier was intended to indicate.

Binary gates make the qualification criteria explicit and independently verifiable. A Regional cluster must have national-scale population reach, a specific anchor composition, regional hospital access, and spatial independence from stronger clusters. None of these requirements can be satisfied by proxy.

## Population Catchment Ranks

Catchment population is computed using a fixed-resolution geographic grid over crow-flies distance, per the [[od-catchment-methodology|distance-band methodology]]. Two zones are defined for each cluster:

- **Primary zone**: all grid cells within 35 km of the cluster anchor
- **Secondary zone**: all grid cells between 35 km and 150 km of the cluster anchor

Population totals draw from an open-licensed gridded population dataset, aggregated to the same grid used for catchment analysis (see [[trade-area-data-sources|trade-area data sources]]). Each cluster is then ranked against every other cluster in its own ISO country on two families of measure — population reach, and category-level consumer spend — each taken across both zones.

The rank is expressed as a percentile fraction within the cluster's country: a lower value indicates a higher relative reach. This puts countries with very different total cluster counts on a common scale.

Spend measures are modelled estimates rather than observed transactions, derived by applying published per-capita household-spending patterns to the population grid and stratifying the result by retail category.

## Tier Gate Definitions

The anchor classes referenced below — Hypermarket, Warehouse, Hardware, and Lifestyle — are defined in the [[retail-brand-family-taxonomy|retail brand-family taxonomy]].

### Tier 1 — Regional

A cluster qualifies as Regional if all five of the following conditions are true:

1. **Composition**: The cluster pairs a Hypermarket anchor with either a Warehouse anchor or a Lifestyle anchor.
2. **Primary catchment**: The cluster's primary-population rank within its country must be among the highest in the country — this is the tightest primary-catchment bar of any tier.
3. **Secondary catchment**: The cluster's secondary-population rank within its country must also sit well above the country median, though the bar here is looser than the primary-catchment gate.
4. **Civic — regional hospital**: A hospital serving a regional catchment is present within a defined civic-proximity ring around the cluster anchor.
5. **Spatial independence**: The cluster's trade area must not substantially overlap that of any cluster in the same country with a higher primary-population rank — Regional carries the strictest independence bar of any tier.

### Tier 2 — District

A cluster qualifies as District if all five of the following conditions are true:

1. **Composition**: The cluster contains a Hypermarket anchor together with a Hardware or a Warehouse anchor.
2. **Primary catchment**: The cluster's primary-population rank within its country must clear a materially lower bar than Regional, but still sit well above the country median.
3. **Spend reach**: The cluster's rank within its country on at least one spend category must also clear that same bar.
4. **Civic — hospital present**: A hospital serving at least a district-level catchment is present within the civic-proximity ring.
5. **Spatial independence**: Overlap between this cluster's trade area and that of any Regional cluster in the same country is allowed to run higher than the Regional-tier limit, but remains bounded.

### Tier 3 — Local

A cluster qualifies as Local if all three of the following conditions are true:

1. **Composition**: The cluster contains a Hardware or a Warehouse anchor.
2. **Primary catchment**: The cluster's primary-population rank within its country must be at or above the country median.
3. **Civic — any hospital**: A hospital of any kind is present within the civic-proximity ring.

### Tier 4 — Fringe

A cluster that does not qualify for Regional, District, or Local is classified as Fringe. A Fringe cluster may still contain significant retail co-tenancy; the classification indicates that one or more required conditions for Local or above were not met.

## Overlap Measurement

The spatial-independence gate compares the trade areas of two clusters, each represented as a disk of fixed radius held constant across tiers, and measures how far the two overlap. Clusters far enough apart that their trade areas do not intersect at all are treated as fully independent. As the overlap grows, the weaker cluster's tier is capped accordingly.

## Civic Classification

Hospital presence is derived from open mapping data and graded by the scale of catchment a facility serves. Facilities serving a wide regional population satisfy the higher civic gates; small local facilities satisfy only the Local gate. The grading acts as a proxy for the depth of public infrastructure supporting a cluster, not as a clinical or capacity measure.

## Threshold Summary

The catchment and spend bars tighten moving from Local up through Regional, and the spatial-independence allowance tightens correspondingly — Regional clusters face both the highest catchment bar and the strictest overlap limit, while Local clusters face the lowest catchment bar and no explicit overlap gate. The civic-ring radius and the spatial-independence disk radius are each held constant across tiers.

Thresholds are intentionally coarse — designed to distinguish nationally significant clusters from local nodes, not to finely rank within a tier. Refinement is planned for a future update as additional catchment data becomes available.

## Sensitivity: the cluster count is a model output, not a measurement

Clustering is a descriptive procedure. It partitions the retailer locations observed under a chosen density model; it does not recover a true, setting-independent number of clusters that exists in the world. The number returned moves materially when the settings move within a defensible range.

Parameter sweeps conducted during development demonstrate this directly: across the reasonable range tested, the North American cluster count varies by more than a factor of two, with no change whatsoever to the underlying retailer data. A headline cluster count is therefore a figure produced under one chosen parameterisation. Any presentation of a cluster count states the parameters that produced it — an unqualified count invites a reader to treat a modelling choice as an observed fact.

## The planned strength score

The tier gates classify a cluster; they do not measure how much market it commands. A separate per-cluster **strength score** is intended to answer that second question. The two dimensions are reported side by side once available; they are never collapsed into a single colour or a single number.

### Design principles

The intended strength score is explainable, not opaque. It is a transparent combination of named drivers, each of which can be shown in the cluster scorecard with its own value and its contribution to the total. No machine-learned weights and no hidden interaction terms. A reviewer must be able to reconstruct the score from the displayed drivers.

### Proposed driver set

Three demand-side quantities the data layers already support:

1. **Population reached** — catchment population and households, from the WorldPop 2026 population estimates. This is the size of the addressable market.
2. **Spend captured** — estimated annual retail spend in the catchment, derived from population and per-capita spend proxies published by national statistical agencies. This carries the estimation caveats documented in the [[spend-population-provenance]] article and must be displayed with that framing.
3. **Accessibility** — how reachable the catchment is, expressed through observed origin-destination demand where a country's mobility data supports it, and a distance-band approximation elsewhere. Which of the two a cluster rests on is disclosed on the cluster itself, so an observed-mobility site and an approximated site are never ranked in one pool without the reader knowing.

### Weights: an open question

How these three drivers combine into a single number is an open question that this article deliberately does not resolve. Three candidate forms are on the table: an equal-weight normalised sum, a lexicographic ranking, and operator-tunable weights. Until the weighting is ratified, the scorecard displays driver values individually so any composite shown is always decomposable. A composite score with undisclosed weights would reintroduce exactly the credibility problem that the tier-label revision exists to remove.

### What the scorecard is intended to show

For each clicked cluster the planned detail panel presents, at minimum:

- The cluster's tier and its plain-language definition.
- Catchment population and households, with vintage noted.
- Estimated annual spend, explicitly framed as a modelled estimate.
- The list of co-located chains driving the composition.
- The strength score (when built) with its top drivers, each driver's contribution, and whether its accessibility figure is observed or approximated.

## See Also

- [[co-location-tier-nomenclature]]
- [[co-location-methodology]]
- [[co-location-ranking-system]]
- [[retail-brand-family-taxonomy]]
- [[trade-area-methodology]] — catchment derivation, geodesic computation, and the migration from distance bands toward observed trade areas
- [[spend-population-provenance]] — the estimation chain for the spend driver in the strength score

## References

*Hospital, university, and retailer location data used to derive cluster catchments is sourced from OpenStreetMap contributors and licensed under the Open Database Licence (ODbL). OpenStreetMap data © OpenStreetMap contributors.*
