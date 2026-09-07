---
schema: foundry-doc-v1
title: "Retail centres (PRO)"
slug: retail-centres
category: site-selection
index_group: anchors-and-tenants
type: concept
content_type: topic
quality: complete
status: active
audience: vendor-public
bcsc_class: public-disclosure-safe
language_protocol: PROSE-TOPIC
language: en
last_edited: 2026-09-04
editor: pointsav-engineering
paired_with: site-selection/retail-centres.es.md
short_description: "Retail Centres (PRO) are neighbourhood commercial centres anchored by grocery, pharmacy, bank, and casual dining — one of three Location Intelligence co-location archetypes, and the base map product for the site-selection dataset."
cites: []
---

**Retail Centres** (PRO) are neighbourhood commercial centres anchored by everyday-needs retail: a grocery hypermarket, a pharmacy, a bank branch, and casual dining. The archetype captures the grocery-anchored commercial gravity that organises local consumer activity — the cluster of stores residents visit weekly for routine shopping, banking, and meals.

Three-letter code: **PRO**. One of three Location Intelligence archetypes alongside [[urban-fringe|Urban Fringe (VWH)]] and [[commuter|Commuter (PKS)]]. PRO is the base map product — the foundation of the [[site-selection-terminology|site-selection]] dataset on which the other two archetypes are overlaid.

## What a Retail Centre is

A Retail Centre is the commercial heart of a residential catchment. Its anchor is a grocery hypermarket, around which a predictable tenant mix accumulates:

- **Grocery hypermarket** — the primary anchor; generates the weekly footfall that supports the rest of the centre
- **Pharmacy** — health and convenience retail co-located with grocery traffic
- **Bank branch** — retail financial services positioned where residents already shop
- **Casual dining** — quick-service and sit-down restaurants serving the same catchment
- **Secondary retail** — hardware, electronics, price clubs, and lifestyle retailers that deepen the centre's draw

Consumer traffic at a Retail Centre is steady and broadly distributed across the week, with weekend peaks driven by household grocery runs. The defining signal is grocery-anchored [[co-location-strategy|co-location]]: where a grocery hypermarket and a hardware retailer cluster within a defined span, a Retail Centre is present.

## Tier classification

PRO clusters are graded at four scales — **T1 Regional**, **T2 District**, **T3 Local**, and **T4 Fringe**.

A cluster's tier is assigned by predicate gate, not by an accumulated score. Every condition listed for a tier must pass, and a strong reading on one condition does not offset a failure on another. Four condition families apply in combination:

- **Composition** — which of the four anchor classes are present: hypermarket, lifestyle, hardware, and warehouse
- **Catchment rank** — where the cluster's trade-area population and spend rank against other clusters in the same country, drawn from the zones described in [[od-catchment-methodology|the distance-band methodology]]
- **Civic presence** — whether a hospital of the required classification sits within the cluster's civic ring
- **Spatial independence** — for the upper tiers, whether the cluster is substantially overlapped by a stronger cluster in the same country

**T1 — Regional:** the largest centres, drawing from a regional catchment. A hypermarket anchor combines with a warehouse or lifestyle anchor; the cluster ranks among the highest in its country by catchment population; a regionally classified hospital is present; and the cluster is spatially independent of stronger neighbours. This is the tightest bar on every condition.

**T2 — District:** a district centre serving a defined neighbourhood with a complete everyday-needs mix. A hypermarket anchor combines with a hardware or warehouse anchor; the cluster's catchment and spend ranks sit well above its country's median; and hospital access is present within the civic ring. Every bar is looser than Regional, but each is still a bar.

**T3 — Local:** a smaller local centre with partial anchor composition. A hardware or warehouse anchor is present, catchment rank reaches at least the country median, and any hospital classification satisfies the civic condition.

**T4 — Fringe:** clusters that clear none of the higher gates. A Fringe cluster may still show real retail co-tenancy; what it lacks is catchment reach, anchor composition, or civic support at the level a higher tier requires.

Span still matters, but as a clustering input rather than as the qualification test. Anchor-category retail locations are grouped into one candidate cluster only when they fall within a defined span of each other, so span determines what counts as a single cluster before any gate is tested. It does not, on its own, set the tier. The span conventions are platform parameters, re-tuned between rebuilds as anchor-chain coverage changes, and are not published here.

The full gate definitions are maintained in [[catchment-ranking-methodology|the catchment ranking methodology]]; the tier labels themselves are defined in [[co-location-tier-nomenclature|tier nomenclature]]. The T1–T4 tier labels used here are shared with the other Location Intelligence archetypes.

## Coverage

Retail Centres (PRO) form the foundation of the site-selection dataset, covering 17 display countries across North America and Europe. The three-letter archetype codes were ratified on 1 June 2026.

Cluster counts by tier are a moving figure. They change with each rebuild as anchor-chain coverage and the underlying retail footprint change, and tier boundaries are periodically re-tuned in response. Current counts are therefore not restated here.

## Why PRO is the base map

Retail Centres anchor the entire Location Intelligence dataset because grocery-anchored co-location is the most stable and widely distributed commercial pattern. Almost every populated catchment has a grocery anchor; the centre that forms around it is a reliable proxy for residential commercial gravity. The Urban Fringe and Commuter archetypes are defined partly in relation to PRO clusters — Urban Fringe sites are identified by the *absence* of grocery anchors, and Commuter sites reference the nearest T1 or T2 Retail Centre as the [[about-regional-markets-system|regional market]] generating their parking demand.

## See also

- [[location-intelligence-archetypes]] — the full PRO/VWH/PKS co-location archetype overview
- [[catchment-ranking-methodology]] — the tier gate definitions in full

## Data Sources

Map and location data © [OpenStreetMap contributors](https://www.openstreetmap.org/copyright) / [ODbL](https://opendatacommons.org/licenses/odbl/).
