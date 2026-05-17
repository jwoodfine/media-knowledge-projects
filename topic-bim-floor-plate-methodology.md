---
schema: foundry-doc-v1
title: "Floor plate methodology — key plans and tiles"
slug: topic-bim-floor-plate-methodology
category: bim
type: topic
quality: complete
status: pre-build
audience: operator
bcsc_class: vendor-internal
language_protocol: PROSE-TOPIC
last_edited: 2026-05-17
editor: pointsav-engineering
paired_with: topic-bim-floor-plate-methodology.es.md
---

> "Key Plans and Tiles" means a geometric self-similar aperiodic space-planning system based on furniture and equipment arrangements and circulation versus modular area-per-person progressions.

Source: V12 Methodology (May 2025) and V12 Tear Sheet (January 2026). The definition is invariant across both versions.

A **Key Plan** is the smallest unit: a labelled rectangle around one tenant's actual furniture inventory, sized to enclose desks, storage, circulation, and accessibility. A **Tile** is a composable group of Key Plans. A **Floor Plate** is the assembly of Tiles plus a Building Core plus Special Tiles. Nothing on the floor is left unrepresented.

Three properties qualify the system:

- **Aperiodic** — Tiles do not repeat on a fixed grid.
- **Self-similar** — each Tile is exactly one HVAC climate zone, regardless of size.
- **Geometric** — all dimensions resolve to real metric measurements driven by real furniture SKUs (Steelcase, Midmark, Treston, Agati).

## The three tile families

| Family | Area | m² | Role |
|---|---|---|---|
| Small | 2,700 SF | 250.84 | Most flexible; smallest unit of climate-zone autonomy |
| Medium | 3,500 SF | 325.16 | Bridge family; absorbs short-side geometry |
| Large | 4,900 SF | 455.22 | Corporate anchor; approaches 1/4 floor tile |

Source: V12 Methodology p. 2. The Medium family is documented in the V12 Methodology PDF but is currently absent from `tile-system.dtcg.json` — flagged as a token-store gap.

## Tile composition rules

These rules govern how Tiles compose into a valid Floor Plate. They are encoded as `FP-*` validators in the planned `tool-floorplates` Rust crate.

### FP-SUM — every square foot is represented

The aggregate of Basic Tiles + Compound Tiles + Special Tiles + the Building Core sums to the full Net Leasable Area within a ±100 SF tolerance. No free space exists without a corresponding Key Plan.

### FP-ENDCAP — short sides receive natural light

The two ends of the building use End Cap tiles:

- Small-family End Caps: Tile B-1 (Private 2,700 SF), Tile E-1 (Mixed Left 2,700 SF), Tile E-2 (Mixed Right 2,700 SF).
- 6,000 SF paired End Caps: Tile A-1 (Corporate), Tile B-2 (Private), Tile C-3 (Professional Medium), Tile C-4 (Professional Large).
- Medium-family End Caps: Tile E-1 (Private Office Medium variant) and Tile E-2 (Professional Office Medium variant), each approximately 3,500–5,500 SF.

End Caps must receive natural light on both perpendicular axes; an End Cap with no window on one axis triggers a window-bay revision (V12 Methodology p. 8, Sample #3/#4).

### FP-CORE — Offset Pulled Back Core

The Building Core (Elevators, Service Stairs, Emergency Stairs, Restrooms, Meter Room, Mop Room) is positioned at least 18 m from the short end of the building. This leaves enough plate length for two End Cap tiles plus at least one Basic Tile on each side of the core.

### FP-SNAP — Special Tile width matches Key Plan width

Special Tiles SP-A, SP-B, SP-C fill the residual area surrounding the Core. Their width is snapped to the nearest Professional Office Key Plan width. This preserves demising-wall continuity. SP-C, in front of the Core, must avoid direct alignment of any door with the elevator opening (V12 Methodology p. 9).

### FP-CLIMATE — one tile, one HVAC zone

Each Tile is an independent climate zone. Tenants who combine Tiles combine climate-control authority; the leasing agreement prices this trade-off explicitly. Smaller tiles increase tenant autonomy; larger tiles reduce zone count in favour of contiguous space.

### FP-DOORS — door count per tile and per floor

Each tile may carry up to 10 doors; each floor may carry up to 80 doors. The door count is one of the cost drivers in the leasing economics — every door is also a Service Hookup (electric, data, HVAC tap).

### FP-CORNER — small tiles at corners trigger structural review

When a Small-family tile lands at a structural corner, the column grid is reviewed before the tile is finalised. Small tiles may conflict with the structural module; the core position is adjusted if the short-side tiles conflict (V12 Methodology p. 2, Inventory of Tiles note).

## Floor-plate dimensional range

| Class | Net leasable per floor | Floor count |
|---|---|---|
| Professional Centres | 19,000 – 23,000 SF | 3 – 5 floors |
| Suburban Office | 17,000 – 21,000 SF | 6 – 9 floors |
| Retail Select | 4,500 / 6,700 / 7,700 SF | varies |
| Tech Industrial | 7,200 / 8,400 SF | varies |

Source: V1 Combinations PDF p. 2 (formal algebra).

## Why "geometric self-similar aperiodic" matters

- **Geometric** — every dimension cites a furniture SKU plus a regulatory clearance, not a developer rule of thumb.
- **Self-similar** — a Tile at 2,700 SF is the same kind of object as a Tile at 4,900 SF: one climate zone, one leasable instrument.
- **Aperiodic** — tiles do not repeat on a fixed grid. A floor can carry a different tile sequence on every level.

## Floor-plate composition example

From V12 Methodology p. 4 (Sample Small Tile):

- Tile A (Corporate Office 2,700) ×2 left of left emergency stairs
- Tile A (Corporate Office 2,700) ×2 between emergency stairs
- Special Tile A (400 SF) — core-adjacent left
- Building Core
- Special Tile B (300 SF) — core-adjacent right
- Tile A (Corporate Office 2,700) — right of core
- Tile A ×2 (5,400 SF combined) at right end

Basic Tiles: 18,900 SF. Special Tiles: 1,100 SF. Total: 20,000 SF.

## Open research

- **Q1.** The token store lists E-1 and E-2 as 2,700 SF Small End Caps. The V12 Methodology shows them as Medium End Caps at approximately 3,500–5,500 SF. Which convention is authoritative?
- **Q2.** SP-C is documented at 4,700 SF in front of the Core. How does it interact with the Elevator Lobby for compositions using Medium tiles?
- **Q3.** What is the exact derivation of the 18 m minimum core-to-short-end distance? Inferred from end-cap and first-tile width, but no PDF cites the figure directly.
- **Q4.** The Tile B-1 token records 1,800 SF office + 900 SF corridor. The May Methodology shows 5 PO modules summing to 1,850 SF + 850 SF residual. Which composition is current?
- **Q5.** The 100 SF tolerance in FP-SUM is operator policy, not source-document text. Confirm the tolerance band before encoding.

## See also

- [[topic-bim-tile-system]]
- [[topic-bim-floor-plate-tile-combinations]]
- [[topic-bim-building-width-method]]
- [[topic-bim-zone-depths-per-use-type]]
