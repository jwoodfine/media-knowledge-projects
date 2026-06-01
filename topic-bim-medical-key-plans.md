---
schema: foundry-doc-v1
title: "Medical — key plans"
slug: topic-bim-medical-key-plans
aliases:
  - topic-bim-medical-key-plans
short_description: "Medical Office key plan specifications within the Professional Office classification, distinguished by the widest Zone 1 Habitat depth at 7.28 m to accommodate exam-table clearance and dual patient-clinician circulation, in three sizes from 223 to 486 m²."
category: bim
type: topic
quality: complete
status: pre-build
audience: operator
bcsc_class: vendor-internal
language_protocol: PROSE-TOPIC
last_edited: 2026-05-17
editor: pointsav-engineering
paired_with: topic-bim-medical-key-plans.es.md
---

Medical Office is one of the five [[topic-bim-professional-office-key-plans|Professional Office]] sub-types. Its distinguishing feature is Zone 1 Habitat at 7.2 m — the widest of any sub-type — driven by exam-table depth plus the circulation required for both patient and clinician access. The depth is computed using the [[topic-bim-building-width-method|Building Width Calculator]] and feeds the [[topic-bim-tile-system|Tile system]] that composes the [[topic-bim-floor-plate-methodology|floor plate]].

## The three sizes

| Size | Dental chairs | Code | Area (m²) | Area (SF) | Façade frontage |
|---|---:|---|---:|---:|---|
| Small | 2 | M3 | 223 | 2,401.5 | 718" (18.24 m) |
| Medium | 4 | M1 | 331 | 3,567.7 | 1,066-5/8" (27.10 m) |
| Large | 6 | M2 | 486 | 5,231.4 | 1,564" (39.73 m) |

The FFE codes are numbered by historical authoring order, not by size: M1 was the first dental-suite sample drawn, then M2 (Large) and M3 (Small). For external documents, size labels (Small / Medium / Large) are preferred over FFE codes.

## Zone vocabulary

| Zone | Depth | Note |
|---|---|---|
| Zone 1 — Habitat | 7.2 m (23'-10") | Widest Z1 across all use types — exam table + patient + clinician circulation |
| Zone 2 — Magazine | 4.9 m (16') | Medical supply storage, sterilisation, equipment staging |
| Zone 3 — Corridor | 2.9 m (9'-5") | Bilateral; ADA/CSA-B651 compliant width for stretcher and wheelchair passage |

Computed building width = 2 × (7.2 + 4.9) + 2.9 = **27.1 m** (88'-11").

## Furniture anchor — the KaVo uniQa dental chair

Every Medical sketch carries the KaVo uniQa dental chair as the reference SKU. Chair envelope: 2,451 mm × 2,898 mm. Each exam room is approximately 7,280 mm × 4,877 mm (~35.5 m²). The KaVo SKU is a tracked dependency: if the dental-chair line is updated, exam-room dimensions cascade.

## M3 (Small) — 2 dental chairs

Suite components: one doctor's office, two exam rooms, one administrative office with reception window, one waiting area (6 patients), one storage room, one lab, one staff room.

Equipment list: mechanical room, workbench with 2–3 seats and sinks, autoclave (sterilisation), imaging room, file room, storage.

Key design notes from the cappelletti sestito architetti sketches (DRAFT 250512):
- Reception requires a direct line of sight to the entrance door.
- Waiting seats positioned outside Zone 1 so the façade is reserved for clinical Habitat.
- Second egress door required for emergencies.

## M1 (Medium) — 4 dental chairs

M1 extends M3 with two additional exam rooms and a reorganised Zone 2 for additional clinical throughput. Key revisions: the File Room moves adjacent to Reception; the staff-room approach to the washroom adds a vestibule with a sink; waiting-room capacity increases.

## M2 (Large) — 6 dental chairs

M2 extends M1 with two additional exam rooms, two doctor's offices, and a full Zone 2 build-out: mechanical/electrical, workbench with 2–3 seats and sink, file room, imaging and autoclave, staff room, atrium. Key revision: washrooms are paired as a single block (M+F or universal) rather than spread across the suite.

## Magazine depth optimisation

The Zone 2 depth at 4.9 m is driven by the Staff Room table depth plus circulation. Narrowing the Staff Room table is the lever for reducing building width — but the table must remain a real, widely available, affordable Steelcase piece to preserve the furniture-driven methodology. Changing dimensions requires using furniture that can be independently sourced and verified.

A differential rent rate for Habitat versus Magazine has been identified as a future leasing convention: the rates applied to Zone 2 need not match those applied to Zone 1.

## Reception line-of-sight requirement

A recurring requirement across all three Medical sketches: Reception must maintain a direct line of sight to the entrance door. The canonical solution is the Reception "window" pattern — an administrative office adjacent to reception with a glazed opening. This is a soft-functional requirement that drives desk placement and the orientation of the doctor's-office wall.

## AART vs cappelletti sestito

An earlier Medical-Tile design by AART architects (March 2024) was superseded by the cappelletti sestito sketches for four stated reasons: the earlier layout was not people-centred, used modular rather than need-based sizing, used non-verified furniture SKUs, and provided improper circulation for accessibility. Reception in the earlier design had no natural light.

## See also

- [[topic-bim-key-plans-index]]
- [[topic-bim-professional-office-key-plans]]
- [[topic-bim-zone-depths-per-use-type]]
- [[topic-bim-building-width-method]]
