---
schema: foundry-doc-v1
title: "Key Plans and Tiles"
slug: key-plans-and-tiles
category: co-location
type: topic
content_type: topic
quality: pre-build
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: PROSE-TOPIC
last_edited: 2026-06-26
editor: pointsav-engineering
short_description: "A geometric, self-similar space planning system derived from tenant equipment and circulation geometry, used to derive fixed floor plate dimensions."
paired_with: co-location/key-plans-and-tiles.es.md
---

Key Plans and Tiles is the space planning methodology that translates professional occupier equipment and circulation requirements into standardized geometric units, which are then aggregated to produce the [[fixed-floor-plates|fixed floor plate]] dimensions. The system is geometric and self-similar: a single tile unit — derived from the physical footprint of workstation equipment, furniture arrangement, and minimum circulation path — generates the full range of floor plate configurations through repetition and aggregation rather than custom design.

## From equipment geometry to tile

The base tile is derived by measuring the physical geometry of the primary equipment configuration for each [[mix-of-use|professional tenant category]]:

- The workstation or treatment area footprint
- The circulation clearance required on each side (typically governed by the German Circulation Law 3-foot minimum or equivalent)
- The secondary adjacency — filing, storage, or equipment — that must be within the workstation's immediate zone

This measurement produces a rectangular unit of defined dimensions. The tile is the smallest self-contained space unit that can accommodate the equipment geometry plus required circulation. All further space planning is done by aggregating tiles, not by designing from scratch.

## The self-similar and aperiodic character

Key Plans are geometric, self-similar, and aperiodic — the tile repeats to fill a floor plate area, but the repetition produces a non-periodic pattern. This means no two adjacent tiles have identical orientation to every neighbour; the floor plate geometry avoids the monotony of orthogonal grid repetition while remaining fully derivable from the base tile.

This aperiodic property has practical consequences for space flexibility. A tenant requiring a different use-case configuration — a laboratory bench arrangement versus a medical treatment room versus a business workstation cluster — can be accommodated by reorienting the tiles within the plate boundary, not by reconfiguring structural elements.

## Tiles and floor plate subdivisions

The tile unit defines the minimum leasable module. Floor plate subdivisions — 1/8, 1/4, 1/2, 3/4, and full floor — are each multiples of the tile unit: a subdivision boundary falls at a tile boundary, not at an arbitrary point on the floor plate. This ensures that any subdivision of the plate remains a geometrically coherent, equipment-ready space without residual fragments.

The subdivision boundaries are fixed in the structural grid (they determine where demising walls can be placed) before the building is leased. A prospective tenant is selecting from a defined set of geometrically complete space configurations, not requesting a custom partition arrangement.

## Application to prototype design

The Key Plans and Tiles derivation process runs once per prototype class. The output — the base tile dimensions and the aggregation rules — is then fixed for that prototype. When a new deployment of the same prototype class is undertaken, the floor plate is not redesigned; it is reproduced from the fixed tile parameters.

This means that equipment and circulation standards embedded in the tile — lighting proximity requirements, circulation clearances, adjacency minimums — carry through to every deployment in the prototype class without re-derivation. The tile is the operational specification of the building's usable space, expressed as geometry rather than prose.
