---
schema: foundry-doc-v1
title: "Trade-area methodology"
slug: trade-area-methodology
category: site-selection
index_group: site-scoring-and-trade-areas
type: topic
content_type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: PROSE-TOPIC
last_edited: 2026-08-26
editor: pointsav-engineering
short_description: "Honest labelling of demand geography — why straight-line distance bands are never called catchments, and the planned move to isochrones and observed origins."
paired_with: site-selection/trade-area-methodology.es.md
cites: []
---

The trade-area methodology governs how the Woodfine location intelligence map (gis.woodfinegroup.com) defines, renders, and labels the area around each co-location cluster from which customers are estimated to travel. A trade area is not simply the geographic extent of the stores in a cluster; it is a representation of where demand originates. The methodology specifies, plainly and with its limitations stated, how that representation is constructed at each stage of the product's development.

## What the map shows today

The live map renders a distance band around each cluster centroid. **Until the observed-trade-area pipeline is integrated, that band is a straight-line radius, not a measured catchment.** The labelling rule is unambiguous: any geometry derived from a straight-line formula reads as "distance band (straight-line)" on the map face and in the detail panel — never "catchment" and never "trade area."

The map states plainly: *"Distance bands are straight-line radii around the cluster centroid; they approximate, but do not measure, where customers come from."*

This is a deliberate honesty edit. A clearly-labelled approximation is defensible in front of a reviewer; a circle mislabelled as a measured catchment is not.

A band labelled 35 km represents 35 km of actual ground distance at any latitude. Distances are measured on the curved surface of the earth, not on the flattened map image, so a stated figure means the same thing in every market. The map itself, like every web map, stretches with latitude on screen — the underlying figures do not move. The distance and projection treatment behind that guarantee is planned for publication at gis.woodfinegroup.com.

## The intended model: observed origins and drive-time

A trade area is the set of places customers actually travel from. Two methods — drive-time isochrones and empirical origin-destination polygons — are planned as successive improvements to the current distance bands.

### Drive-time isochrones

An isochrone replaces the straight-line radius with the area reachable within a stated drive time (for example 10, 20, or 30 minutes) along the road network. Isochrones respect barriers that circles ignore — rivers, motorway access, mountain passes, one-way coastal routes — so two clusters with identical straight-line radii can have substantially different reachable areas. Drive-time isochrones are the retail-geography standard that site-selection reviewers expect.

The planned implementation uses self-hosted routing over open map data the platform already holds, rather than a metered third-party isochrone service — consistent with a product built on sovereign, self-contained data infrastructure.

### Observed origin-destination polygons

Rather than modelling where customers could come from, an O-D polygon draws where they do come from, using observed mobility data. Coverage currently spans two countries: worker origin-destination flows published for the United States, and the mobility matrices published by the Spanish Ministry of Transport — each providing an observed origin distribution rather than a modelled ring. The data needed to render observed-origin polygons for US and Spain clusters is in place; turning a cluster click into an observed-origin polygon, rather than a ring, is planned but not yet available. The source datasets and their coverage detail are planned for publication at gis.woodfinegroup.com.

The intended O-D trade area for a cluster is the set of origin areas contributing the top share — for example 70–80% — of observed trips or workers to that cluster. Coverage is uneven (US and Spain today; the UK, France, and Germany researched as viable next sources), so the planned rollout is country-by-country. Clusters without O-D coverage keep the clearly-labelled distance band as an explicit interim.

### Why both methods are complementary

Drive-time isochrones answer the question "who can reach this site." Observed O-D polygons answer "who actually shops or works here." The intended map exposes the best available representation per cluster, stating on screen which model produced the polygon and over what vintage. A measured polygon and a drawn circle are never combined under a single label.

## The previous radius formula

The distance band used in the initial product version was computed from the cluster's geographic span — how spread out its member stores are — inflated by an undocumented tuning factor with no published derivation, and bounded by a minimum floor so no cluster receives an unrealistically small band.

This is a geometric artifact, not a demand quantity. It describes how spread out the stores are; it carries no information about how far customers actually travel. Two failure modes follow directly: a dense urban cluster gets a small ring because its stores sit close together, even though its trade area may be large; a sprawling exurban cluster gets a large ring because its stores sit far apart, not because it draws from far away.

Neither the inflation factor nor the floor has a published derivation. They are tuning constants that make the picture look reasonable. Until observed O-D or drive-time boundaries are adopted, any interim distance band discloses that it rests on this unpublished, geometry-only formula rather than applying it silently.

The intended end state removes this span-based formula from the live pipeline entirely, replacing it with a boundary whose parameter is a quantity a domain expert can evaluate on its merits — a stated drive-time, a stated percentile of modelled demand, or a stated population threshold.

## Distances are measured on the ground, not on the screen

Every distance and area figure on the platform is a true ground measurement, computed consistently across the platform's full 24-country co-location footprint and both the North American and European frames. The map projection stretches with latitude, as every web map does — a ring drawn at the same on-screen size covers less ground near the poles than near the equator — so no figure is ever derived from the picture itself. The map discloses this on its face: the rendered shape may stretch; the underlying numbers do not. The projection and computation detail behind this is planned for publication at gis.woodfinegroup.com.

## Spatial framework

Population and spend are aggregated on a single hexagonal grid that is continuous and consistent worldwide. Because every market is measured on the same grid, a cluster's population and spend figures compare directly across the 13 countries with published per-capita spend multipliers (see [[spend-population-provenance]] for full coverage detail). This revision does not change the aggregation grid; it changes how the trade-area polygon over that grid is defined — by observed origin or drive-time where data allows, and by a clearly-labelled distance band where it does not yet. The grid specification is planned for publication at gis.woodfinegroup.com.

A single grid cell may fall inside the trade areas of several clusters. This is intentional: trade areas overlap because the retail landscape is competitive, and a household near two competing clusters contributes to both. This holds whether the boundary is a distance band, an isochrone, or an O-D polygon, and it underpins the cross-cluster comparison.

## What changes next

The move away from straight-line rings is planned as a phased, country-by-country migration: honest labelling of every interim band first; observed-origin polygons next, wherever mobility data already supports them, with uncovered clusters retaining the labelled band; drive-time isochrones then becoming the default reachable-area view, retiring the span-based interim formula; and calibrated distance-decay boundaries extending defensible polygons to further countries as viable sources are confirmed. Each step narrows the gap between what the polygon claims and what the data supports. The engineering sequence and its current status are planned for publication at gis.woodfinegroup.com.

## Application

Trade-area membership is the basis for population aggregation (Kontur Population), spend aggregation (modelled per-capita multipliers), and cross-cluster competitive ranking. The numbers attributed to a cluster are only as defensible as the polygon they are summed over — which is why the polygon's definition, parameters, and projection treatment are stated here rather than implied by a circle on a map.

## See also

- [[catchment-ranking-methodology]] — how clusters are assigned tiers and the planned strength score
- [[spend-population-provenance]] — the estimation chain for population and spend within the trade area
- the settlement-level rollup built over co-location clusters
- the process that runs the spatial analysis
- upstream retail clustering feeding the co-location index
