---
schema: foundry-doc-v1
title: "Retail Centres (PRO)"
slug: topic-retail-centres
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
paired_with: topic-retail-centres.es.md
short_description: "Retail Centres (PRO) are neighbourhood commercial centres anchored by grocery, pharmacy, bank, and casual dining — one of three Location Intelligence co-location archetypes, and the base map product for the site-selection dataset."
cites: []
---

**Retail Centres** (PRO) are neighbourhood commercial centres anchored by everyday-needs retail: a grocery hypermarket, a pharmacy, a bank branch, and casual dining. The archetype captures the grocery-anchored commercial gravity that organises local consumer activity — the cluster of stores residents visit weekly for routine shopping, banking, and meals.

Three-letter code: **PRO**. One of three Location Intelligence archetypes alongside [[topic-urban-fringe|Urban Fringe (VWH)]] and [[topic-commuter|Commuter (PKS)]]. PRO is the base map product — the foundation of the site-selection dataset on which the other two archetypes are overlaid.

## What a Retail Centre is

A Retail Centre is the commercial heart of a residential catchment. Its anchor is a grocery hypermarket, around which a predictable tenant mix accumulates:

- **Grocery hypermarket** — the primary anchor; generates the weekly footfall that supports the rest of the centre
- **Pharmacy** — health and convenience retail co-located with grocery traffic
- **Bank branch** — retail financial services positioned where residents already shop
- **Casual dining** — quick-service and sit-down restaurants serving the same catchment
- **Secondary retail** — hardware, electronics, price clubs, and lifestyle retailers that deepen the centre's draw

Consumer traffic at a Retail Centre is steady and broadly distributed across the week, with weekend peaks driven by household grocery runs. The defining signal is grocery-anchored co-location: where a grocery hypermarket and a hardware retailer cluster within a defined span, a Retail Centre is present.

## Tier classification

PRO clusters are graded at three scales. The pipeline groups anchor-category retail locations that fall within a defined span distance, then assigns each group to a tier based on anchor composition.

**T1 — Regional:** A cluster containing a grocery hypermarket and a hardware retailer, plus at least one of a price club, lifestyle retailer, or electronics retailer. Alternatively: four or more anchor-category retailers in a tight cluster (span ≤ 1 km), or three or more anchors in any tight cluster. These are the largest centres, drawing from a regional catchment.

**T2 — District:** A cluster containing a grocery hypermarket and a hardware retailer, with a span no greater than 2.5 km. The district centre serves a defined neighbourhood with a complete everyday-needs mix.

**T3 — Local:** All remaining anchor pairs that do not qualify for T1 or T2. Smaller local centres with partial anchor composition.

The T1/T2/T3 tier labels used here are shared with the other Location Intelligence archetypes.

## Production dataset

The PRO pipeline is the foundation layer of the site-selection dataset, covering 17 display countries across North America and Europe.

| Tier | Clusters | Countries |
|------|----------|-----------|
| T1 | 1,746 | 17 |
| T2 | 2,726 | 17 |
| T3 | 2,021 | 17 |
| **Total** | **6,493** | |

The T2 span boundary was set to 2.5 km in the most recent rebuild, tightening the district-scale boundary relative to earlier phases. The three-letter archetype codes were ratified on 1 June 2026.

## Why PRO is the base map

Retail Centres anchor the entire Location Intelligence dataset because grocery-anchored co-location is the most stable and widely distributed commercial pattern. Almost every populated catchment has a grocery anchor; the centre that forms around it is a reliable proxy for residential commercial gravity. The Urban Fringe and Commuter archetypes are defined partly in relation to PRO clusters — Urban Fringe sites are identified by the *absence* of grocery anchors, and Commuter sites reference the nearest T1/T2 Retail Centre as the regional market generating their parking demand.

## See also

- [[topic-location-intelligence-archetypes]] — the full PRO/VWH/PKS co-location archetype overview

## Data Sources

Map and location data © [OpenStreetMap contributors](https://www.openstreetmap.org/copyright) / [ODbL](https://opendatacommons.org/licenses/odbl/).
