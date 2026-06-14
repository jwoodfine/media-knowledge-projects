---
schema: foundry-doc-v1
title: "Zone depths per use type — sources, values, rationale"
slug: topic-bim-zone-depths-per-use-type
aliases:
  - topic-bim-zone-depths-per-use-type
short_description: "Canonical Zone 1 Habitat, Zone 2 Magazine, and Zone 3 Corridor per-side depths for seven Professional Office use types from Private Office to Business, with derived building widths and source citations to V12 sketches and methodology documents."
category: bim
type: topic
content_type: topic
quality: complete
status: pre-build
audience: operator
bcsc_class: vendor-internal
language_protocol: PROSE-TOPIC
last_edited: 2026-05-17
editor: pointsav-engineering
paired_with: topic-bim-zone-depths-per-use-type.es.md
---

> **Companion:** [[topic-bim-building-width-method]] for the formula and the mirror cross-section.

This article catalogues the per-side zone depths feeding the [[topic-bim-tile-system|Tile system]] and the [[topic-bim-floor-plate-methodology|floor plate methodology]]; the inventory of named Key Plans is in [[topic-bim-key-plans-index|the Key Plans index]]. Sub-type specialisations are documented under [[topic-bim-professional-office-key-plans|Professional Office]] and its [[topic-bim-medical-key-plans|Medical]], [[topic-bim-business-key-plans|Business]], and [[topic-bim-private-office-key-plans|Private Office]] sub-articles.

## Summary table — canonical values

The Z1/Z2/Z3 values below are the **per-side** depths (Z1 and Z2 are mirrored, Z3 is centreline single). All values trace to the cited source.

| Use Type | Z1 Habitat | Z2 Magazine | Z3 Corridor | Building Width | Source |
|---|---|---|---|---|---|
| [[topic-bim-private-office-key-plans|Private Office]] | 5.9944 m / 19'8" | 1.3716 m / 4'6" | — | **14.73 m / 48'4"** | PO-1/PO-2/PO-3 sketches |
| Academic | 4.7 m / 15'5" | 3.0 m / 9'10" | — | **15.40 m / 50'6"** | Summary V2, 2025-05-13 |
| [[topic-bim-professional-office-key-plans|Professional Office]] (V12 baseline) | 6.0 m / 19'8" | 3.0 m / 9'10" | 3.0 m / 9'10" | **21.00 m / 68'11"** | V12, 2025-01-07 (Z2/Z3 marked TBD) |
| Laboratory | 6.7818 m / 22'3" | 4.8006 m / 15'9" | 3.048 m / 10'0" | **26.21 m / 86'0"** | Summary V2; IBC high-hazard egress |
| [[topic-bim-medical-key-plans|Medical]] | 7.2819 m / 23'10" | 4.877 m / 16'0" | 2.892 m / 9'5" | **27.20 m / 89'3"** | M3/M1/M2 sketches (286 5/8" + 192" + 113 7/8") |
| [[topic-bim-business-key-plans|Business]] | 5.51 m / 18'1" | 9.26 m / 30'5" | 2.75 m / 9'0" | **29.30 m / 96'2"** | Notes V3 Option A/A (widest enumerated) |
| Civic | 6.0 m / 19'8" | 7.23 m / 23'9" | 3.6 m / 11'10" | **30.06 m / 98'8"** | Synthesised values; no completed sketch |

Formula: `Width = 2 × (Z1 + Z2) + Z3`. See [[topic-bim-building-width-method]] for the derivation.

## Per use type

### Private Office (PO-1 / PO-2 / PO-3)

| Zone | Value | Sketch evidence |
|---|---|---|
| Z1 Habitat | **5.9944 m / 19'8"** | "19'-8"" on each of PO-1, PO-2, PO-3 |
| Z2 Magazine | **1.3716 m / 4'6"** | "4'-6"" on each sketch (shallow storage zone, below the dashed centreline) |
| Z3 Corridor | **— (none)** | Each office opens to the shared building corridor (outside the leasehold) |
| Key plan SF | PO-1 = 325, PO-2 = 465, PO-3 = 685 | Sketch labels |
| Key plan m² | 30.19, 43.20, 63.64 | Calculated from SF |
| Building width | **14.73 m / 48'4"** | 2 × (5.9944 + 1.3716) |

Private Office is the narrowest of the use types. The 5.9944 m Habitat is marginally under the 6.0 m European Lighting Standard threshold — flagged for review at Key Plan sign-off.

Combinations: PO-1 + PO-1 = 60.4 m² (650 SF); PO-1 + PO-2 = 73.4 m² (790 SF); PO-1 + PO-3 = 93.8 m² (1,010 SF); PO-2 + PO-3 = 106.8 m² (1,150 SF). These fill the gap between Private Office Large and Professional Office Small.

### Academic (A1 / A2 / A3)

| Zone | Value | Source |
|---|---|---|
| Z1 Habitat | **4.7 m / 15'5"** | Summary V2 |
| Z2 Magazine | **3.0 m / 9'10"** | Summary V2 (the source shows "3'7"" in feet, which is a transposition; 3.0 m = 9'10" is correct) |
| Z3 Corridor | **— (none)** | Suites open to building corridor |
| Key plan m² | Small 87.7 / Medium 240.3 / Large 376.3 | Key Plans Samples V2 |
| Key plan SF | Small 944 / Medium 2,586 / Large 4,050 | |
| Building width | **15.40 m / 50'6"** | 2 × (4.7 + 3.0) |

Academic compresses Habitat below 6 m because **seating faces forward** (toward a podium/board) rather than toward the façade. The European Lighting Standard applies to workstations; auditorium-style seating is not workstation use.

**Inconsistency:** `building-width-calculator.dtcg.json` records Academic Small as **105 m² / 1,131 SF**, while `professional-office-subtypes.dtcg.json` records it as **87.7 m² / 944 SF**. Pending operator decision on which is canonical.

### Professional Office (baseline)

| Zone | Value | Source |
|---|---|---|
| Z1 Habitat | **6.0 m / 19'8"** | V12 (January 2025) |
| Z2 Magazine | **3.0 m / 9'10"** | V12 — *marked "TBD"; placeholder* |
| Z3 Corridor | **3.0 m / 9'10"** | V12 — *marked "TBD"; placeholder* |
| Key plan m² | Small 130.06 (only) | DTCG token; Medium/Large pending |
| Key plan SF | Small 1,400 (only) | DTCG token |
| Building width | **21.00 m / 68'11"** | V12 stated total |

Professional Office is the **baseline** use type — the type from which the other Professional Centre sub-types (Medical, Business, Laboratory, Academic, Civic) are derived by varying Z1, Z2, and Z3.

V12 explicitly marks Z2 and Z3 as **"TBD"** with 3 m placeholders. When the Professional Office Key Plan is completed, the operator will lock Z2 and Z3 to match the furnished layout.

### Laboratory (L1 / L2 / L3)

| Zone | Value | Source |
|---|---|---|
| Z1 Habitat | **6.7818 m / 22'3"** | Summary V2 |
| Z2 Magazine | **4.8006 m / 15'9"** | Summary V2 |
| Z3 Corridor | **3.048 m / 10'0"** | Summary V2 (IBC high-hazard occupancy minimum) |
| Key plan m² | Small 195.0 / Medium 316.0 / Large 400.7 | Samples V2 |
| Key plan SF | Small 2,099 / Medium 3,401 / Large 4,313 | Samples V2 |
| Building width | **26.21 m / 86'0"** | 2 × (6.7818 + 4.8006) + 3.048 |

Laboratory's wider Z1 accommodates bench depth (Treston TP-915 ≈ 900 mm) and fume-hood clearance (≈ 940 mm + 1,500 mm egress in front of the hood). The 10'0" corridor is the IBC high-hazard occupancy egress minimum.

Specialisations: Medical Laboratory, Research Laboratory.

### Medical (M1 / M2 / M3)

| Zone | Value | Sketch evidence |
|---|---|---|
| Z1 Habitat | **7.2819 m / 23'10"** | "286 5/8"" on M1/M2/M3 (= 7.282 m) |
| Z2 Magazine | **4.877 m / 16'0"** | "192"" on M1/M2/M3 (= 4.877 m) |
| Z3 Corridor | **2.892 m / 9'5"** | "113 7/8"" on M1/M2/M3 (= 2.892 m) |
| M3 (Small, 2 dental chairs) | **2,401.5 SF** / 223 m² | Sketch label |
| M1 (Medium, 4 dental chairs) | **3,567.7 SF** / 331 m² | Sketch label |
| M2 (Large, 6 dental chairs) | **5,231.4 SF** / 486 m² | Sketch label |
| Building width | **27.20 m / 89'3"** | 2 × (7.2819 + 4.877) + 2.892 |

Medical has the widest Habitat across the use types. The depth accommodates exam-table depth (Midmark 626 ≈ 790 mm) plus patient seating, clinician circulation, and a reception window facing the façade. The 2.892 m corridor is the ADA/CSA-B651 stretcher-and-wheelchair clearance.

Operator notes on the M3 sketch flag: "Add second door for emergencies", "Line of sight — safety — reception needs to see the door", and "Move seats down out of Zone #1".

Specialisations: Dentist, General Practitioner.

### Business (B1 / B2 / B3)

The Business use type has **21 enumerated width options** per Notes V3. The token store records the widest symmetric option as the default:

| Zone | Value | Source |
|---|---|---|
| Z1 Habitat | **5.51 m / 18'1"** | Notes V3 Option A |
| Z2 Magazine | **9.26 m / 30'5"** | Notes V3 Option A (widest enumerated) |
| Z3 Corridor | **2.75 m / 9'0"** | Notes V3 (fixed across all 21 options) |
| Key plan SF | Small 3,350 / Medium 4,302 / Large 7,524 | Sketches 2-4 |
| Building width | **32.29 m / 105'11"** | 2 × (5.51 + 9.26) + 2.75 (Option A/A) |

**Important caveat:** Notes V3 enumerates 21 combinations (Option A/A through D/D), where the two letters denote the left-side and right-side Z1/Z2 choices. The narrowest Business option is **25.29 m (D/D)** and the widest is **32.29 m (A/A)**. The asymmetric options are generally disfavoured for tile composition because demising walls must absorb the asymmetry.

From operator commentary in Notes V3 on Option D: "The overall area of the Fixed Floor Plates [is] Professional Centres at approximately **19,000 SF to 23,000 SF** and Suburban Office at approximately **17,000 SF to 21,000 SF**."

### Civic (C1 / C2 / C3)

| Zone | Value | Source |
|---|---|---|
| Z1 Habitat | **6.0 m / 19'8"** | Synthesised (no completed sketch) |
| Z2 Magazine | **7.23 m / 23'9"** | Synthesised (token store value) |
| Z3 Corridor | **3.6 m / 11'10"** | Synthesised — public assembly egress |
| Key plan m² | Small 270 / Medium 577 / Large 822 | Token store (samples-derived) |
| Key plan SF | Small 2,912 / Medium 6,215 / Large 8,850 | Token store |
| Building width | **30.06 m / 98'8"** | 2 × (6.0 + 7.23) + 3.6 |

**Civic does not yet have a completed sketch.** Z1/Z2/Z3 values in the token store are synthesised from the design intent (public records storage; widest corridor for ceremonial circulation and public assembly egress). Specialisations: Courtroom, Municipal Office, Cultural Space, Civic Assembly.

## The 0.7 m perpendicular-desk addition

Applies to **any Z1 Habitat** that arranges desks perpendicular to the façade. Token: `bim.circulation-addition.perpendicular-desk = 0.7 m`. Effective Z1 = 6.0 + 0.7 = **6.7 m** when perpendicular desks are required to seat three desks in series.

## Floor-plate target ranges

| Class | Range |
|---|---|
| Professional Centres | 19,000 – 23,000 SF |
| Suburban Office | 17,000 – 21,000 SF |

The current token store hard-codes 20,000 SF as `floorPlate.netLeasableSF`. Convert to a range with PC and SU variants.

## Future research

- [ ] Confirm Academic Small key plan area: **87.7 m² (944 SF)** per Samples V2 vs. **105 m² (1,131 SF)** per DTCG token store
- [ ] Complete Civic sketch to anchor Z1/Z2/Z3 values to a real furniture arrangement
- [ ] Confirm operator preference for Business: Option A/A (widest, 32.29 m) versus a balanced option such as C/C (~27 m)
- [ ] Capture manufacturer SKU dimensions in a `furniture.dtcg.json` file
- [ ] Complete Professional Office Z2/Z3 (currently V12 placeholders at 3 m / 3 m TBD)
- [ ] Document the 0.7 m perpendicular-desk supplement as an effective-Habitat modifier
- [ ] Verify whether the 6.0 m Habitat tracks a specific clause in EN 12464-1

## Source-document inconsistencies (open)

| # | Issue | Action |
|---|---|---|
| 1 | Academic Small area: 105 m² (DTCG) vs 87.7 m² (subtypes DTCG / Samples V2) | Operator decision needed |
| 2 | Medical Z1 token = 7.2 m, sketch = 286 5/8" = 7.28 m | Token file pending update to 7.2819 m |
| 3 | Professional Office Z2/Z3 placeholders (V12: 3 m / 3 m TBD) | Values to confirm from Key Plan |
| 4 | Floor-plate hard-coded 20,000 SF; Notes V3 directs ranges | Convert to range token |
| 5 | 21 m PDF total vs prior 21.6 m token arithmetic | Reconciled 2026-05-17 by restoring V12 values |

## See also

- [[topic-bim-building-width-method]]
- [[topic-bim-floor-plate-methodology]]
- [[topic-bim-key-plans-index]]
