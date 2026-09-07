---
schema: foundry-doc-v1
title: "Regional market definition"
slug: regional-market-definition
short_description: "Spatial containers on the location intelligence map — how coverage differs from a qualified Regional Market, and why coverage alone is not a market-strength claim."
category: markets
index_group: coverage-methodology
type: concept
content_type: topic
quality: complete
status: stable
audience: customer-woodfine
bcsc_class: public-disclosure-safe
language: en
language_protocol: PROSE-TOPIC
last_edited: 2026-09-07
editor: pointsav-engineering
paired_with: markets/regional-market-definition.es.md
cites: []
---

The Woodfine location intelligence map distinguishes two spatial containers for a settlement with retail co-location activity. A settlement enters the **coverage layer** the moment one co-location cluster falls inside its boundary. It becomes a **Regional Market** only once its clusters clear the platform's anchor-composition gates. A third, coarser container — the **Metro Market** — places each Regional Market in its metropolitan context. The distinction matters because coverage measures how widely the platform's tracked retail chains have been observed; it does not measure where retail demand concentrates.

## Settlement with co-location presence

A settlement with co-location presence is any incorporated municipal or CSD polygon containing at least one co-location cluster, assigned by point-in-polygon match against TIGER 2023 boundaries in the United States and GISCO LAU 2021 plus GADM GBR boundaries in the European Union and United Kingdom. As of the most recent processing run, **12,689 settlements across 24 countries** carry this coverage flag; **12,578** of them — about 99% — carry the high-confidence geocoding flag.

This is a coverage statistic. It records how widely the platform's tracked anchor chains have been observed, not where retail demand concentrates: a town with a single qualifying co-location and a metropolitan area with dozens both clear this floor on the same terms. Geocoding confidence measures the precision of the boundary assignment, not the strength of the underlying market, and is not treated as a quality signal anywhere on the platform.

## Regional Market

A Regional Market is a settlement whose co-location clusters clear the platform's anchor-composition gates — the same compositional logic applied to individual clusters under the [[co-location-tier-system|tier system]], assessed at the settlement level. Each continent draws its qualifying pool from every settlement that clears the gates — 1,121 settlements across three countries in North America, 650 across fifteen countries in Europe. [[about-regional-markets-system|Regional Markets Intelligence System]] documents the full qualification method.

The distinction from raw coverage is deliberate: a single-anchor settlement clears the coverage floor without carrying the anchor diversity a Regional Market requires. The composition gate, not settlement count, is what determines whether a name appears on the platform's Regional Markets tables.

## The Top 400 — a qualifying set, not a ranking

Publication is capped at 400 markets per continent, presented in a fixed, alphabetical order that carries no rank. Every published market has already cleared the anchor-composition gates described above. Where a continent's qualifying pool exceeds 400, the markets with the strongest anchor composition are published — 400 of 1,121 in North America, 400 of 650 in Europe. A composite score exists internally to support that selection but is not published and carries no bearing on how a market is described on this wiki. The published lists are at [[atlas-top-400-north-america]] and [[atlas-top-400-europe]].

## Metro Market

The Metro Market is a coarser, contextual container: a major metropolitan area on a published reference list (US MSA/CBSA, Canadian CMA). A Regional Market nests inside at most one Metro Market and is never dissolved into it. Metro Market is context only — it is never a co-location or ring zoom level, and never a breadcrumb level in its own right.

## Boundary resolution

Boundary resolution follows one rule with no settlement-specific exceptions. A co-location near Sherwood Park, Alberta resolves to its containing polygon, Strathcona County, on the same terms as any other settlement.

## Counts

| Object | Definition | Count |
|---|---|---|
| Settlements with co-location presence | At least one co-location cluster inside the settlement's polygon | 12,689 across 24 countries |
| Regional Markets — North America | Cleared the anchor-composition gates; published as the strongest 400 of a 1,121-market qualifying pool | 400 |
| Regional Markets — Europe | Cleared the anchor-composition gates; published as the strongest 400 of a 650-market qualifying pool | 400 |

*Regional Market figures from the 2026-08-07 dataset build. Coverage-layer figures (settlements with co-location presence) from the 2026-08-06 processing run.*

## See also

- [[about-regional-markets-system|Regional Markets Intelligence System]] — the full dataset, tier system, and qualification method this article's definitions build on
- [[catchment-ranking-methodology]] — how tiers and the planned strength score are computed for each co-location inside a Regional Market
- [[trade-area-methodology]] — how the trade area for each co-location is defined
- [[spend-population-provenance]] — the estimation chain for population and spend figures attributed to each co-location
