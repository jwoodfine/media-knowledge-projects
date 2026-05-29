---
schema: foundry-doc-v1
title: "Business — key plans"
slug: topic-bim-business-key-plans
short_description: "Business Office key plan specifications within the Professional Office classification, distinguished by the widest Zone 2 Magazine depth of any sub-type at 9.26 m, driven by open storage walls, server rooms, and team collaboration zones, in three sizes from 311 to 669 m²."
category: bim
type: topic
quality: complete
status: pre-build
audience: operator
bcsc_class: vendor-internal
language_protocol: PROSE-TOPIC
last_edited: 2026-05-17
editor: pointsav-engineering
paired_with: topic-bim-business-key-plans.es.md
---

Business Office (Professional Office — Business) is one of the five [[topic-bim-professional-office-key-plans|Professional Office]] sub-types. Its distinguishing feature is Zone 2 Magazine at 7.3 m — the widest of any sub-type — driven by open storage walls, server rooms, print areas, and team collaboration zones characteristic of professional-services practices. The depth is computed using the [[topic-bim-building-width-method|Building Width Calculator]] and feeds the [[topic-bim-tile-system|Tile system]] that composes the [[topic-bim-floor-plate-methodology|floor plate]].

## The three sizes

| Size | Code | Area (m²) | Area (SF) |
|---|---|---:|---:|
| Small | B-1 | 311 | 3,350 |
| Medium | B-2 | 400 | 4,302 |
| Large | B-3 | 669 | 7,524 |

## Zone vocabulary

| Zone | Depth | Note |
|---|---|---|
| Zone 1 — Habitat | 6.0 m (19'-8") | European Lighting Standard minimum |
| Zone 2 — Magazine | 7.3 m (23'-11") | Widest Magazine across all sub-types |
| Zone 3 — Corridor | 2.7 m (8'-10") | Bilateral corridor |

Computed building width = 2 × (6.0 + 7.3) + 2.7 = **29.3 m** (96'-1").

## Specialisations

The Business sub-type encompasses professional services practices: Law Firm, Accounting Firm, Engineering Firm. These are not separate Key Plans — they are variants on the B-1/B-2/B-3 footprints with adjusted Magazine content (legal files, audit binders, engineering plotters respectively).

## Building Width Options A/B/C/D

The Business — Small sketches include a four-option width exploration that captures the bidirectional adjustment principle:

| Option | Workstations | Z1 Habitat | Z2 Magazine | Total width | Area (m²) |
|---|---:|---:|---:|---:|---:|
| A | 15 | 5.51 m | 9.26 m | 17.52 m | 450.7 |
| B | 21 | 7.39 m | 6.76 m | 16.90 m | 399.6 |
| C | 15 | 5.63 m | 6.63 m | 15.01 m | 345.5 |
| D | 15 | 5.51 m | 5.76 m | 14.02 m | 339.5 |

Option A maximises Magazine. Option D compresses both zones but loses the Executive Office capability. The V3 baseline (Z2 = 7.3 m) is the Building Width Calculator output that guides the three-size Key Plan set.

## Design principles from the MW3 commentary

The inline commentary on the Business sketches establishes design principles that apply across all sub-types:

**On natural light:** The 6.0 m standard governs natural light provision, but must be considered alongside the functional requirements of the Use Cases as determined by their furniture arrangements.

**On zone flexibility:** Zone 1 Habitat and Zone 2 Magazine are not necessarily fixed after the Building Width Calculator has been established. Tenants should find it straightforward to position enclosed offices at the façade frontage or push them into Zone 2 while maintaining furniture arrangements and circulation.

**On unallocated Magazine:** Any empty Zone 2 area that is unallocated gives an opportunity for interior design to create informal areas and storage supporting the occupancy — the floor-plate solver should treat unallocated Magazine as snap-fill territory rather than forcing a tile family change.

**On building-width discipline:** Option D highlights the case where the Building Width Calculator must be trimmed to achieve building aesthetics or to bring overall Fixed Floor Plate area within the target range (Professional Centres 19,000–23,000 SF; Suburban Office 17,000–21,000 SF).

## Tenant Washroom in Zone 2

A Tenant Washroom can be contained within Zone 2 — Magazine. Five washroom configurations (Options A–E) show different 2-stall + sinks + vestibule arrangements, all fitting within approximately 7 m × 3 m. The minimum Zone 2 width is therefore co-driven by either the Staff/Conference Room or the Tenant Washroom, whichever is wider.

For sub-types with narrow Magazine (e.g., [[topic-bim-private-office-key-plans|Private Office]] at 1.4 m), there is no Tenant Washroom in the suite — tenants use building-core washrooms.

## Spatial taxonomy anchor element

Each Professional Office sub-type carries one anchor element at the façade end whose dimensions drive the Habitat depth. For Business, this is the Reception — the same grammatical role that the Clean Room plays in Laboratory, the Auditorium in Academic, the Court Room in Civic, and the exam room in [[topic-bim-medical-key-plans|Medical]].

## See also

- [[topic-bim-key-plans-index]]
- [[topic-bim-professional-office-key-plans]]
- [[topic-bim-zone-depths-per-use-type]]
- [[topic-bim-building-width-method]]
