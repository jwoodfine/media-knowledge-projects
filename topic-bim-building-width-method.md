---
schema: foundry-doc-v1
title: "The backwards method — sizing buildings from furniture"
slug: topic-bim-building-width-method
short_description: "The Building Width Calculator inverts conventional office planning by deriving building width from actual furniture dimensions — desk, exam table, lab bench, courtroom bench — rather than fitting tenants into a predetermined structural grid."
category: bim
type: topic
quality: complete
status: pre-build
audience: operator
bcsc_class: vendor-internal
language_protocol: PROSE-TOPIC
last_edited: 2026-05-17
editor: pointsav-engineering
paired_with: topic-bim-building-width-method.es.md
---

Conventional office buildings begin with a building width — sixty feet for daylight is the rule of thumb in North American Class-A speculative office — and the tenant fit-out is then made to fit. The Building Width Calculator inverts the sequence. It starts with the tenant's furniture (desk, exam table, lab bench, courtroom bench) and the building width is whatever the arrangement requires. The method feeds the per-use-type values catalogued in [[topic-bim-zone-depths-per-use-type|Zone depths per use type]] and drives the geometry of the [[topic-bim-tile-system|Tile system]] that composes the [[topic-bim-floor-plate-methodology|floor plate]].

Source: V12 (January 2025), *Spatial Taxonomy — Building Width Calculator*.

## The mirror cross-section

The cross-section is a seven-row strip:

```
Façade
Zone 1 — Habitat   (desks/workstations)            6.0 m
Zone 2 — Magazine  (storage/bookshelves, etc.)     3.0 m  ← TBD per use type
Zone 3 — Corridor  (single, centreline)            3.0 m  ← TBD per use type
Zone 2 — Magazine  (mirrored)                      3.0 m
Zone 1 — Habitat   (mirrored)                      6.0 m
Façade
─────────────────────────────────────────────────────────
TOTAL                                              21 m / 69 ft
```

V12 establishes Professional Office at **21 m / 69 ft** total as the baseline. Zone 2 Magazine and Zone 3 Corridor are marked "TBD" — they are shaped per use type once the furniture is selected.

The crucial geometric fact: **Zone 3 Corridor is a single centreline row, not mirrored**. Habitat and Magazine appear on both sides of the corridor; the corridor appears once.

## The formula

```
Building Width = 2 × (Zone 1 Habitat + Zone 2 Magazine) + Zone 3 Corridor
```

This is confirmed by two independent sources:

- V12 Professional Office: 2 × (6 + 3) + 3 = **21 m** ✓
- Business Notes V3 Option A/A: 2 × (5.51 + 9.26) + 2.75 = **32.29 m** — the document explicitly tabulates this total.

A common error is to double the corridor as well. Doubling the corridor yields an overstated building width (Professional Office becomes 23.6 m instead of 21 m; Civic becomes 33.66 m instead of 30.06 m). Verify any third-party implementation against the formula above.

## Why three zones

### Zone 1 — Habitat

The 6 m daylight depth is the design intent for workstation-occupied space. It approximates the European Lighting Standard guidance for natural light at a workstation (EN 12464-1 / EN 17037, pending precise citation in the regulatory token file).

The 6 m figure is not universal. Three of the seven established use types diverge:

- **Academic** compresses Habitat to **4.7 m** because seating faces forward (toward a podium/board) rather than toward the façade.
- **[[topic-bim-medical-key-plans|Medical]]** widens Habitat to **7.28 m** to accommodate exam-table depth plus patient and clinician circulation per accessibility-code clearances.
- **Laboratory** widens Habitat to **6.78 m** to accommodate bench depth and fume-hood clearance.

### Zone 2 — Magazine

Magazine is the slack variable. It holds storage, bookshelves, filing, server rooms, and staff rooms. The width is set by what the tenant needs to balance the plate — V12 directs that the Zone 2 depth "can be used to balance out the dimensions of the floor plate to not end up with simply a long, narrow rectangle."

In practice Zone 2 is the widest zone for [[topic-bim-business-key-plans|Business]] (9.26 m, Option A/A) and Civic (7.23 m), and the narrowest for [[topic-bim-private-office-key-plans|Private Office]] (1.37 m, 4'6") because individual offices carry minimal shared storage.

### Zone 3 — Corridor

The corridor is a single centreline. Its width is set by egress and accessibility — IBC stretcher minima for Medical, IBC high-hazard egress for Laboratory, public assembly egress for Civic. V12 directs that corridors be **overdesigned by 20%** to promote well-being and absorb in-and-out traffic.

Two use types — [[topic-bim-private-office-key-plans|Private Office]] and Academic — have **no Zone 3**. Their leaseholds open directly onto the shared building corridor, which is part of the building core and outside the leasehold.

## The 0.7 m perpendicular-desk addition

V2 Summary (May 2025) records a perpendicular-desk supplement:

> With desks placed perpendicular to the façade, be careful, as an extra 0.7 metres is required for proper circulation for three desks in series in Zone 1—Habitat. Without accounting for the circulation, 6 metres exactly to the façade results in only two desks perpendicular to the façade in Zone 1—Habitat rather than three desks.

Token: `bim.circulation-addition.perpendicular-desk = 0.7 m`.

This is a Zone 1 supplement, not a separate zone. It changes the effective Habitat depth from 6.0 m to 6.7 m when perpendicular desk arrangements are required to seat three desks in series.

## Why this method matters

The backwards method makes three claims that conventional speculative office practice does not:

1. **Furniture drives geometry.** A landlord cannot reduce a tenant's exam-table depth by tightening the floor plate; the building must accommodate the use, not vice versa.
2. **Each tenant type has a known width.** Once the use type is selected, the building width is computed, not negotiated.
3. **Mixed-tenant floors must reconcile widths at design time.** A floor with a Medical anchor (27.2 m) and a Private Office cluster (14.7 m) must absorb 12.5 m of demising tolerance — the floor plate width must match the widest tenant, with narrower tenants accepting the surplus as wider Zone 2 magazines.

## Status and ratification

| Component | Source | Status |
|---|---|---|
| Mirror cross-section diagram | V12 (January 2025) | Ratified |
| Z1 = 6 m default | V12 + EN 12464-1 (cited) | Ratified |
| Z2 = TBD per use type | V12 | Ratified |
| Z3 = centreline, single | V12 (visual); Business V3 totals | Ratified |
| Formula `2(Z1+Z2) + Z3` | V12; Business V3 enumeration | Ratified |
| 0.7 m perpendicular-desk add | Summary V2 (May 2025) | Ratified |
| Professional Office Z2/Z3 | V12 ("TBD", placeholder 3 m / 3 m) | Pending |
| Business Z1/Z2/Z3 | Notes V3 (21 options enumerated) | Pending operator selection |
| Civic Z1/Z2/Z3 | No completed sketch | Pending |

## Future research

- [ ] Add precise regulatory citation for the 6 m Habitat (EN 12464-1 clause, ArbStättV cross-reference)
- [ ] Document the accessibility clearance referenced in Medical and Laboratory
- [ ] Confirm whether Zone 3 corridor is always a single centreline, or whether a large floor plate ever introduces a secondary corridor
- [ ] Resolve the Professional Office Z2/Z3 placeholders (V12 leaves them at 3 m / 3 m TBD)
- [ ] Decide which of the 21 Business width options is canonical for the token store (current proposal: Option A/A at 32.29 m)
- [ ] Verify the 0.7 m perpendicular-desk addition is a Habitat supplement (effective Z1 = 6.7 m) versus a separate zone contribution

## See also

- [[topic-bim-zone-depths-per-use-type]]
- [[topic-bim-floor-plate-methodology]]
- [[topic-bim-tile-system]]
