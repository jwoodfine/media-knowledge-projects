---
schema: foundry-doc-v1
title: "Co-location tiering and scoring"
slug: co-location-tiering-scoring
category: site-selection
index_group: site-scoring-and-trade-areas
type: topic
content_type: topic
quality: complete
status: archived
archived: 2026-09-05
archived_reason: "Reconciled 2026-09-05: this article documented the points-based T1/T2/T3 compositional tier scale retired platform-wide on 2026-05-16, which describes no current cluster in the dataset. Its two passages with no equivalent elsewhere -- the cluster-count sensitivity finding and the planned per-cluster strength score -- were merged into catchment-ranking-methodology, the canonical four-tier predicate-gate article; the remaining T1/T2/T3 material is superseded vocabulary and is retained here as historical record only."
superseded_by: catchment-ranking-methodology
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: PROSE-TOPIC
last_edited: 2026-08-26
editor: pointsav-engineering
short_description: "Tier scoring for co-location clusters — what the T1–T3 composition tiers measure, what they explicitly do not claim, and why a headline cluster count is a model output rather than a measurement."
paired_with: site-selection/co-location-tiering-scoring.es.md
cites: []
---

This article describes a compositional tiering methodology that assigns each co-location cluster one of three tiers, T1, T2, or T3, on the basis of retailer-category composition. Rendered as coloured dots, the tiers are graduated from T1 (deepest co-location) to T3 (shallowest qualifying co-location). Understanding precisely what these tiers measure — and what they do not — is necessary for reading a compositional cluster result correctly.

The tier labels currently rendered on the Woodfine location intelligence map are the four-tier system — Regional, District, Local, Fringe — described in [[co-location-tier-nomenclature]]. The compositional T1/T2/T3 model documented in this article is a distinct, related classification approach; the two should not be read as interchangeable.

## What the tiers measure

The variable that drives the tier is **retailer-category composition**: the count and mix of distinct anchor categories co-present within a single spatial cluster. A cluster that contains a hypermarket, a home-improvement big-box, and a warehouse-club anchor has deeper composition than a cluster with a single hypermarket and one grocer. The tier is therefore an ordinal compositional classification.

The tiers measure composition. They do not measure trade-area strength, sales potential, population reached, or spend captured. Two consequences follow directly:

**Composition does not imply demand.** A T1 cluster has more anchor diversity than a T3 cluster. It does not follow that a T1 cluster has more people, more spend, or better accessibility in its trade area. A dense small-city cluster of three anchors can rank T1 on composition while serving a smaller catchment than a single-anchor T3 site in a major metropolitan area. The tier ranks the bundle of retailers present, not the market the bundle sits in.

**Quality claims require an outcome variable.** A label asserting quality implies evaluation against an outcome — footfall, revenue, return on a hypothetical investment. The compositional tier carries no such outcome. The on-map labelling therefore reads "co-location depth (anchor count)" rather than "quality tiers," and the plain-language definition of each tier is tied to composition:

- **T1** — strongest co-location depth (most anchor categories co-present)
- **T2** — intermediate co-location depth
- **T3** — shallowest qualifying co-location

## How clusters are formed

Clusters are produced by density-based spatial clustering of anchor retailer locations, followed by a de-duplication pass so the same physical agglomeration is never counted twice. Three published settings govern the result: the spatial scale at which separate stores read as one cluster, the minimum store presence that qualifies as a co-location rather than an isolated store, and the overlap cut-off used in de-duplication. A hard cap on cluster span applies uniformly, because a wider setting merges agglomerations that operate as distinct retail destinations. Every setting is published alongside each cluster result. The full clustering specification and current parameter values are planned for publication at gis.woodfinegroup.com.

### Sensitivity: the cluster count is a model output, not a measurement

Clustering is a descriptive procedure. It partitions the retailer locations observed under a chosen density model; it does not recover a true, setting-independent number of clusters that exists in the world. The number returned moves materially when the settings move within a defensible range.

Parameter sweeps conducted during development demonstrate this directly: across the reasonable range tested, the North American cluster count varies by more than a factor of two, with no change whatsoever to the underlying retailer data. A headline cluster count is therefore a figure produced under one chosen parameterisation. Any presentation of a cluster count states the parameters that produced it — an unqualified count invites a reader to treat a modelling choice as an observed fact.

## The planned strength score

The composition tier answers "what retailer mix is here." A separate per-cluster **strength score** is intended to answer "how much market does this location command." The two dimensions are reported side by side once available; they are never collapsed into a single colour or a single number.

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

- Composition tier and its plain-language definition.
- Catchment population and households, with vintage noted.
- Estimated annual spend, explicitly framed as a modelled estimate.
- The list of co-located chains driving the composition.
- The strength score (when built) with its top drivers, each driver's contribution, and whether its accessibility figure is observed or approximated.

## See also

- [[trade-area-methodology]] — catchment derivation, geodesic computation, and the migration from distance bands toward observed trade areas
- [[spend-population-provenance]] — the estimation chain for the spend driver in the strength score
- the settlement-level rollup and the Top-400 selection criterion
- the process that produces the tiered clusters
- upstream retail clustering feeding the co-location index
