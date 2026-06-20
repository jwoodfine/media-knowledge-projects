---
schema: foundry-doc-v1
title: "Commuter (PKS)"
slug: topic-commuter
category: governance
type: concept
content_type: topic
quality: complete
status: active
audience: vendor-public
bcsc_class: public-disclosure-safe
language_protocol: PROSE-TOPIC
language: en
last_edited: 2026-06-20
editor: pointsav-engineering
paired_with: topic-commuter.es.md
short_description: "Commuter (PKS) clusters identify transit-adjacent commercial sites with significant parking — commuter rail, transit hubs, park-and-ride, and highway-exit commercial — one of three Location Intelligence co-location archetypes."
cites: []
---

**Commuter** (PKS) clusters identify transit-adjacent commercial sites organised around significant parking. These are the commuter-rail stations, regional transit hubs, park-and-ride lots, and highway-exit commercial nodes where residents of a regional market drive to a transit point, leave their car, and travel onward to a metropolitan market. The parking infrastructure that makes this journey possible at scale is the defining feature of the archetype.

Three-letter code: **PKS**. One of three Location Intelligence archetypes alongside [[topic-retail-centres|Retail Centres (PRO)]] and [[topic-urban-fringe|Urban Fringe (VWH)]]. Commuter is an overlay archetype that identifies transit-adjacent market structure not captured by grocery-anchored Retail Centre clustering.

## What a Commuter cluster is

A Commuter cluster sits at the hinge between two markets:

- **Regional Market** — the city or suburb where the site's users live and shop (captured by the existing T1/T2/T3 Retail Centre system)
- **Metro Market** — the major city those users travel to by train or plane

The Commuter site exists because the journey between them is long enough that driving to the transit node and parking beats driving all the way to the metro. The threshold is approximately 15–150 km. The defining commercial signal is the presence of significant parking alongside transit infrastructure — park-and-ride lots, commuter-rail station car parks, and highway-exit commercial that serves drive-to travellers.

Transit anchor types include:

- **Commuter and intercity rail stations** — stations serving trains that travel to a metro centre, distinct from metro/subway and tram stops
- **Regional airports and transit hubs** — drive-to nodes serving primarily domestic and short-haul routes
- **Park-and-ride facilities** — the discrete car-to-transit transition points that anchor the demand pattern
- **Highway-exit commercial** — fuel, car rental, quick-service food, and convenience retail serving travellers at the transit interface

The commercial enrichment that distinguishes a mature Commuter site is car rental, hotels, fuel stations, and convenience retail — the services arriving and departing travellers require.

## The regional-to-metro relationship

| Distance to major metro | Commuter viability |
|---|---|
| ≤15 km | Too close — suburb; driving to the metro is faster than parking and transiting |
| 15–100 km | Prime Commuter zone — 1–2 hours driving; transit saves meaningful time |
| 100–150 km | Viable if transit is fast (high-speed rail, direct flight) |
| >150 km | Standalone market; may have its own metro relationship or be too remote |

## Co-location signals for site selection

**Essential:**

| Signal | Threshold | Rationale |
|---|---|---|
| Regional transit anchor | ≤3 km | Station, transit hub, or airport with direct metro service |
| Metro isolation | 15–150 km | Defines the regional relationship |
| T1 or T2 Retail Centre cluster | ≤10 km | The Regional Market whose population generates parking demand |
| Multi-lane road access | ≤1 km | Parking inflow/outflow requires arterial capacity |
| Regional population | ≥150,000 | Minimum demand for parking viability |

**Significant:**

| Signal | Threshold | Rationale |
|---|---|---|
| Car rental | ≤1 km | Arriving travellers need transport; highest-confidence Commuter commercial signal |
| Hotel cluster | ≤500 m | Business travel; multi-day parking demand |
| Second transit mode | ≤5 km | Rail plus airport, or rail plus bus = multi-modal integration; highest-value sites |
| No major hub | ≥30 km | A competing major airport kills park-and-travel demand to the regional node |

**Disqualifying:**
- Major international airport within 15 km
- Population under 100,000
- No direct service to a major metro

## Tier classification

PKS tiers use a **mode-group collapse model** that avoids double-counting transit infrastructure at the same physical node. A station offering both intercity and commuter rail at the same platform counts as one transit mode group (RAIL), not two. A genuine multi-modal hub must have distinct modal types — rail plus airport, for example — to qualify as multimodal. Four transit mode groups are recognised: AIR, RAIL (intercity and commuter combined), URBAN (metro and subway), and BUS.

Not all transit clusters qualify as Commuter sites. Walk-up urban stops without commercial drive-to infrastructure are excluded by a qualification gate: a cluster qualifies when it has a drive-to transit anchor, multiple distinct modal groups, or commercial enrichment evidence (car rental or park-and-ride) indicating that visitors arrive by car and leave it at the site.

**T1 Regional Hub:** Multi-modal site with a full commercial ecosystem (car rental plus hotel), or three or more distinct modal groups, or a drive-to anchor with at least one enrichment signal. The highest-confidence park-and-travel sites.

**T2 Transit Interchange:** Drive-to anchor without full T1 commercial enrichment, or a multi-modal site with at least one enrichment signal. Strong Commuter candidates with direct evidence of drive-to behaviour.

**T3 Transit Node:** Single modal group with one enrichment signal that qualifies the site as drive-to rather than walk-up. Transit infrastructure is present; the full commercial ecosystem is not yet established.

The T1/T2/T3 tier labels used here are shared with the other Location Intelligence archetypes.

## Production dataset

The PKS pipeline is production-grade. Park-and-ride records (23,117 locations) serve as the primary geographic anchor — actual car-to-transit transition points, distributed independently of rail-network geometry. Transit modes are enrichment signals; car rental and hotel presence define commercial maturity.

**6,953 clusters** across 17 display countries:

| Tier | Clusters | % | Definition |
|------|---------|---|-----------|
| T1 (Regional Hub) | 691 | 9.9% | Multi-modal + full commercial ecosystem |
| T2 (Transit Interchange) | 2,658 | 38.2% | Transit + at least one commercial signal |
| T3 (Transit Node) | 3,604 | 51.9% | Transit present; commercial opportunity |
| **Total** | **6,953** | | |

Rail stations dominate the dataset across all countries. The European park-and-train pattern means intercity and commuter rail sites substantially outnumber airport sites in the EU; railway stations are reliable Commuter candidates wherever regional service reaches a regional city.

Commercial enrichment chains — car rental (Hertz, Avis, Europcar, Sixt, Enterprise, and others) and hotels (Ibis, Premier Inn, Holiday Inn Express, Courtyard, and others) — are all ingested and active in the production build.

### Major hub filter

Transit anchors with a T1 Retail Centre cluster within 5 km are reviewed as likely major commercial hubs. Major international airports generate their own retail gravity and do not exhibit the park-and-travel pattern; the filter correctly removes LAX, JFK, LHR, and CDG.

## Related research

A companion academic study, *The Commuter Archetype: Car-Rental Clustering as a Proxy for Transit-Adjacent Commercial Co-location*, is in preparation for intended submission to the Journal of Transport Geography (Elsevier). The study identifies 14,332 Commuter candidates across eighteen countries using OpenStreetMap data and documents a rail-to-airport ratio of approximately 88% to 12%, with a 27% integration rate with adjacent commercial co-location clusters.

## See also

- [[topic-location-intelligence-archetypes]] — the full PRO/VWH/PKS co-location archetype overview

## References

- [Park and ride](https://en.wikipedia.org/wiki/Park_and_ride) — Wikipedia, accessed 2026-06-14

## Data Sources

Map and location data © [OpenStreetMap contributors](https://www.openstreetmap.org/copyright) / [ODbL](https://opendatacommons.org/licenses/odbl/).
