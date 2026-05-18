---
schema: foundry-doc-v1
title: "Floor plate tile combinations — sample compositions and trade-offs"
slug: topic-bim-floor-plate-tile-combinations
short_description: "The named sample Tile compositions from the V12 Methodology — four configurations documenting the trade-offs each makes across tenant mix, climate-zone autonomy, leasing gap positions, and demising tolerance."
category: bim
type: topic
quality: complete
status: pre-build
audience: operator
bcsc_class: vendor-internal
language_protocol: PROSE-TOPIC
last_edited: 2026-05-17
editor: pointsav-engineering
paired_with: topic-bim-floor-plate-tile-combinations.es.md
---

The Floor Plate Methodology is intentionally non-deterministic: the catalogue is sized so many valid compositions exist for any given tenant mix. This topic documents the named sample compositions from the V12 Methodology PDF, the trade-offs each makes, and the leasing implications.

## The four sample compositions in V12 Methodology

### Sample Small Tile (Methodology p. 3, p. 4)

```
Tile A | Tile A | SP-A | Core | SP-B | Tile A | Tile A×2
2,700  | 2,700  | 400  | —    | 300  | 2,700  | 5,400
```

Basic Tiles: 18,900 SF. Special Tiles: 1,100 SF. Total: 20,000 SF.

**Trade-off.** When all tiles are Small, climate-zone autonomy is maximised per square foot but the jump from Professional Office (2,700 SF tile) to Corporate Office (2,700 SF tile) collapses — the methodology notes this as the "Corporate Office (2,700) − Medium Professional Office (1,100) = 1,600" gap, leaving a difficult mid-tier between 1,600 and 2,700 SF.

### Sample Medium Tile (Methodology p. 3, p. 8)

```
Tile D | SP-A | Core | SP-A | Tile D | Tile D×2
3,500  | 2,100| —    | 2,000 | 3,500  | 7,000
```

Basic Tiles: 17,500 SF. Special Tiles: 2,500 SF. Total: 20,000 SF.

**Trade-off.** Medium tiles produce a more pleasing core-to-end proportion and reduce the Special Tile load but introduce a larger jump from PO Medium (1,100) to Corporate Office (3,500) = 2,400 SF.

### Sample Large Tile (Methodology p. 4, p. 8)

```
Internal Corridor | SP-B | Core | SP-A | Tile F
Corporate ×2 (9,800) | SP-B (800) | — | SP-A (2,000) | Tile F (4,900)
```

Basic Tiles: 14,700 SF. Special Tiles: 5,300 SF. Total: 20,000 SF.

**Trade-off.** Large tiles make the building shorter (longer floor length) but each tile occupies more of the short side, reducing the number of independent climate zones available to tenants. The methodology notes that with Large tiles, "the Tile itself becomes too large in that it prevents both ends of the building from being broken out into inclusive Climate Zones."

### Sample 2-Floor Tenant Lounge (Methodology p. 5, p. 8)

The second floor of every Professional Centre and Suburban Office building is reserved for a Tenant Lounge. The Lounge occupies a half-floor (10,000 SF reference) on the long side opposite the core; the other half-floor carries Private Office tiles. A Decorated Staircase connects the Main Floor lobby up to the Tenant Lounge atrium.

**Trade-off.** Half the second floor is non-leasable amenity. The Lounge is positioned to draw foot traffic through the building's public face; this loss-leader space is the methodology's expression of "the Office as a Retailer" (White Paper §3 heading).

## Composition typologies

The named samples above generalise into four composition typologies. These are operator-facing labels; the source documents do not use them but the trade-offs are explicit in the methodology.

### Corporate-heavy

Mostly Tile A / Tile F / Corporate fractions. Few climate zones per floor (4–6). Most contiguous space. Highest single-tenant suitability. Used for Corporate anchor tenants taking a full floor or larger fractions.

### Private-Office-heavy (Mixed)

Mostly Tile B-1 / Tile G / Mixed End Caps E-1/E-2. 30–40 climate zones per floor. Maximum thermostat autonomy. Higher HVAC engineering cost; higher leasing yield because every thermostat is its own line item.

### Professional Centre (Mixed)

Mostly Tile C-1/C-2/C-3/C-4 / Tile H. Suitable for mid-range medical, business, laboratory, academic, and civic tenants. Climate-zone count is moderate (8–15 per floor). The methodology calls this the canonical mid-floor configuration.

### Floor-plate mixed

A composition that combines several Basic, Compound, and Special tile types across one plate. Corporate Office on the left, Private Office in the middle, Professional Office immediately right of the Core, End Cap on both short sides.

## Tile combinations and demising tolerance

Tenants may take space across Tile boundaries provided demising walls align with one of the Tile edges. The methodology states:

> "Tenants have the ability to take any size space as long as the demising walls line up with any of the Tiles. Tenants who take space beyond the boundaries of the Tiles no longer maintain control of the Climate Zone."
> — V12 Methodology p. 10 (Leasing).

The Leasing page diagram shows three Tenants (A, B, C) overlapping multiple Tile boundaries. The leasing instrument prices the loss of climate-zone control explicitly: a Tenant whose demising wall splits a Climate Zone shares the thermostat with the neighbouring tenant in that zone.

## End-cap natural light samples

The V12 Methodology (pp. 7–8) shows four end-cap samples: two acceptable (Sample #1 and #2 — natural light on both perpendicular axes) and two unacceptable (Sample #3 and #4 — no natural light at the end caps, "Not 100% efficient in the leasehold"). Operators should reference these when reviewing end-cap window placement on new building designs.

## Open research

- **Q1.** The Sample Large Tile composition lists "Corporate Office ×2 = 9,800 SF" but two Tile F instances sum to 9,800. Is this intended as one leasable Corporate Office at 9,800 SF or two contiguous Corporate Office tiles at 4,900 each? The diagram is ambiguous.
- **Q2.** The Sample 2-Floor diagram shows "Special Tile x 2 = 11,200 SF" combined with "Corporate Office x 2 = 7,000 SF" on the Tenant Lounge half. The math (11,200 + 7,000 = 18,200) is inconsistent with the 20,000 SF reference. Confirm the lounge composition.
- **Q3.** The Methodology Sample Medium Tile reports a 22,900 SF total on p. 11, larger than the 20,000 SF reference. Confirm whether 22,900 SF is intended as a "Professional Centres upper bound" worked example.
- **Q4.** No source document specifies what happens when a tenant takes a partial Tile that does not align with any Tile edge. Is the leasing instrument permitted to refuse such a request, or is the Tile recomposed?

## See also

- [[topic-bim-floor-plate-methodology]]
- [[topic-bim-tile-system]]
- [[topic-bim-zone-depths-per-use-type]]
