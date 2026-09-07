---
schema: foundry-doc-v1
title: "Site Selection"
slug: site-selection-index
category: site-selection
type: topic
content_type: topic
quality: complete
short_description: "The strategy behind near Power Centres: the retail anchors, catchment and cluster analysis, scoring, and the tests a site must pass before land is bought."
index_type: thematic
index_scope: site-selection
status: active
bcsc_class: current-fact
language_protocol: PROSE-TOPIC
last_edited: 2026-09-06
editor: pointsav-engineering
paired_with: _index.es.md
---

Site Selection covers the strategy and investment thesis behind "near Power Centres" — the discipline that decides where a building goes before land changes hands.

<!-- START-HERE-HIGHLIGHT: engine reads this block to render the single "start here" card (reuses the existing cluster-card--start-here component). Do not add more than one. -->

**Start here:** [[co-location-intelligence-overview|Retail Co-Location Intelligence]]

<!-- END-START-HERE-HIGHLIGHT -->

## Where to start

Twenty-seven articles cover how a Development Site is found, scored, and cleared for purchase. These eight run that sequence end to end and reach every group below.

- [[co-location-methodology|Co-location methodology]] — The deterministic framework that classifies a commercial node by where capital-intensive retailers converge. The most-cited article on this wiki.
- [[co-location-intelligence-overview|Retail co-location intelligence]] — The entry point: what the analysis produces, and how a classified site list is built from public location data.
- [[co-location-strategy|Co-location strategy]] — Why professional centres are sited beside national retail anchors, and what that transposes onto office demand.
- [[power-centres|Power Centres]] — The retail hubs every candidate site is measured against.
- [[co-location-anchors|Co-location anchors]] — The large-format retailers whose verified presence qualifies a node. This is the binary test the dataset turns on.
- [[co-location-ranking-system|Ranking system]] — How clusters are tiered within a country, how overlaps are resolved, and how ties are broken.
- [[catchment-ranking-methodology|Catchment ranking methodology]] — The current four tier gates: anchor composition, catchment rank, civic infrastructure, and spatial independence.
- [[zoning-acquisition-rules|Zoning acquisition standard]] — No parcel is bought without a verified entitlement position and an active development timeline.

## Strategy and Investment Thesis

The nine articles behind "near Power Centres": the analysis framework, the site-positioning logic, the investment case, and where the land itself comes from. Proximity to an operating Power Centre transfers necessity-retail demand stability onto adjacent office space — that transfer is the thesis these articles argue.

<!-- AUTO-GENERATED MEMBERSHIP: DO NOT EDIT BELOW — regenerate from index_group: strategy-and-investment-thesis -->
- [[co-location-intelligence-overview]] — Systematic geographic analysis identifying and classifying retail sites where large-format categories converge within defined catchment radii.
- [[co-location-methodology]] — A deterministic spatial-analysis framework that classifies commercial real-estate nodes by the objective convergence of independent, capital-intensive retail operators — independent corroboration in place of market sentiment.
- [[co-location-strategy]] — The strategy of positioning professional centres adjacent to national retail anchors to transpose retail resilience onto office demand.
- [[co-location-investment-thesis]] — The investment thesis that commercial nodes where institutional-grade retailers converge within defined catchment radii present objectively verifiable, superior site characteristics.
- [[power-centre-co-location-thesis]] — Site-selection discipline requiring Qualified Investment sites to co-locate with operating Power Centre anchors, aligning development to proven National Retailer Rollout Programs.
- [[institutional-retail-halo]] — Economic thesis that co-location with grocery-anchored Power Centres transfers the cash-flow stability of necessity retail to adjacent Woodfine professional office space.
- [[power-centre-land-availability]] — Woodfine's land-sourcing thesis: the excess parking Power Centre owners reserve against future National Retailer demand is frequently underutilized and available for purchase.
- [[co-location-convergence-thesis]] — Three trends converge at a Power Centre — live/work/play shopping-centre design, underutilized parking land, and a shortage of professional leasable space — and Woodfine's professional-hours tenancy is built to capture each of them.
- [[location-intelligence-archetypes]] — Three co-location archetypes — Retail Centres, Urban Fringe, and Commuter — identifying distinct commercial clustering patterns across 18 countries in North America and Europe.
<!-- END AUTO-GENERATED -->

## Anchors and Tenants

What a site is measured against. Seven articles define the retail hubs, the qualifying anchors, the four tier labels applied to them, and the professional occupiers whose institutional identity anchors building credibility.

<!-- AUTO-GENERATED MEMBERSHIP: DO NOT EDIT BELOW — regenerate from index_group: anchors-and-tenants -->
- [[power-centres]] — Retail hubs anchored by multiple big-box national retailers, serving as the primary site-selection anchors for Woodfine co-location deployments.
- [[co-location-anchors]] — Large-format national retailers whose verified presence within defined proximity thresholds is the binary qualifying criterion for commercial node inclusion.
- [[co-location-target-hierarchy]] — The signals the co-location dataset looks for and the role each plays — a hypermarket anchor, category-dominant co-anchors, and civic institutions — and why the current tier system requires each one independently rather than summing them into a score.
- [[co-location-tier-nomenclature]] — The four tier labels — Regional, District, Local, Fringe — visible on the co-location map are named after the International Council of Shopping Centres retail property hierarchy, though only "Regional" is a genuine ICSC term; District, Local, and Fringe are the platform's own naming choices. Introduced together with the current predicate-gate scoring system in May 2026.
- [[national-tenants]] — Revenue-driving professional occupiers — academic, medical, and civic — whose institutional identity anchors building credibility and stabilizes the mix-of-use tenant composition.
- [[retail-brand-family-taxonomy]] — Every retail location on the co-location map carries a brand family classification that determines how the location is displayed and, for some families, whether it contributes to cluster scoring. The taxonomy was designed around the anchor types used in the co-location methodology while remaining extensible to the full range of ingested operators.
- [[retail-centres]] — Retail Centres are neighbourhood commercial centres anchored by grocery, pharmacy, bank, and casual dining — one of three Location Intelligence co-location archetypes, and the base map product for the site-selection dataset.
<!-- END AUTO-GENERATED -->

## Commuter Belts and the Urban Fringe

Two of the three co-location archetypes: transit-adjacent sites carrying significant parking, and large-format retail and distribution-industrial activity on the metropolitan periphery. The third, Retail Centres, sits under Anchors and Tenants above.

<!-- AUTO-GENERATED MEMBERSHIP: DO NOT EDIT BELOW — regenerate from index_group: commuter-belts-and-the-urban-fringe -->
- [[commuter]] — Commuter clusters identify transit-adjacent commercial sites with significant parking — commuter rail, transit hubs, park-and-ride, and highway-exit commercial — one of three Location Intelligence co-location archetypes.
- [[urban-fringe]] — Urban Fringe clusters identify large-format retail and distribution-industrial activity on the urban periphery — big-box hardware, home improvement, and logistics — one of three Location Intelligence co-location archetypes.
<!-- END AUTO-GENERATED -->

## Site Scoring and Trade Areas

How a qualifying anchor becomes a classified cluster. Seven articles cover cluster formation, deduplication of overlapping candidates, the deterministic tier engine, and the distance bands scoring runs against.

<!-- AUTO-GENERATED MEMBERSHIP: DO NOT EDIT BELOW — regenerate from index_group: site-scoring-and-trade-areas -->
- [[co-location-cluster-formation]] — The pipeline step that converts each qualifying anchor store into a candidate co-location cluster; overlapping candidates from a single trade area are resolved by deduplication before ranking inputs are aggregated.
- [[cluster-deduplication-threshold]] — The co-location index pipeline deduplicates overlapping clusters that represent the same commercial zone using a fixed, tightly-set proximity threshold, retaining the cluster with the higher secondary operator count.
- [[co-location-ranking-system]] — The deterministic mechanics behind cluster ranking on the co-location platform — country-relative percentile ranking, the overlap test between neighbouring clusters, and the tiebreak order applied within a tier.
- [[catchment-ranking-methodology]] — The current predicate-gate system that assigns each co-location cluster to one of four tiers — Regional, District, Local, Fringe — using anchor composition, national catchment rank, civic infrastructure, and spatial independence, introduced May 2026 to replace an earlier composite-score model.
- [[geographic-co-location-methodology]] — Predicate-gate tier system classifying retail co-location clusters by anchor composition, catchment rank, and civic presence to identify development sites by anchor strength.
- [[od-catchment-methodology]] — Each co-location cluster is assigned two straight-line distance bands — a primary zone within 35 km and a secondary zone from 35 km to 150 km — that determine the population and spend attributed to it.
- [[trade-area-methodology]] — Honest labelling of demand geography — why straight-line distance bands are never called catchments, and the planned move to isochrones and observed origins.
<!-- END AUTO-GENERATED -->

## Before Land Is Bought

The two tests a candidate site clears before purchase: a verified entitlement position on the parcel — a permitted use or an evidenced, achievable rezoning path — and independent GIS verification of its tier.

<!-- AUTO-GENERATED MEMBERSHIP: DO NOT EDIT BELOW — regenerate from index_group: before-land-is-bought -->
- [[zoning-acquisition-rules]] — Pre-purchase entitlement verification: every parcel is acquired against either a permitted use or an evidenced, achievable rezoning path, with an active development timeline and no speculative land banking.
- [[asset-evaluation-protocol]] — How the co-location classification matrix drives Woodfine's commercial asset acquisition targeting: the tier classification as the entry criterion, deterministic scoring on public location data as the verification method.
<!-- END AUTO-GENERATED -->

## See also

- [[markets|Regional Markets]]
- [[gis|Maps and Data]]
