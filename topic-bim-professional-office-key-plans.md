---
schema: foundry-doc-v1
title: "Professional Office — key plans baseline"
slug: topic-bim-professional-office-key-plans
short_description: "The Professional Office superordinate category covering five sub-types — Business, Medical, Laboratory, Academic, and Civic — with the Initial Design baseline zone dimensions that preceded sub-type specialisation."
category: bim
type: topic
quality: complete
status: pre-build
audience: operator
bcsc_class: vendor-internal
language_protocol: PROSE-TOPIC
last_edited: 2026-05-17
editor: pointsav-engineering
paired_with: topic-bim-professional-office-key-plans.es.md
---

Professional Office is the superordinate category for five sub-types: Business, Medical, Laboratory, Academic, and Civic. It carries an "Initial Design" baseline that pre-dates the sub-type specialisation and is preserved as design lineage.

## The Initial Design baseline

| Field | Value |
|---|---|
| Small | 130 m² / 1,400 SF |
| Medium | Not sampled |
| Large | Not sampled |
| Zone 1 — Habitat | 6.0 m / 19'-8" |
| Zone 2 — Magazine | 3.8 m / 12'-5" |
| Zone 3 — Corridor | 2.0 m / 6'-6" |

Computed building width = 2 × (6.0 + 3.8) + 2.0 = **21.6 m** (70'-10").

## Tenant categories

The Key Plans system recognises eleven tenant categories:

```
Private Office
Professional Office — Business
Professional Office — Medical
Professional Office — Laboratory
Professional Office — Academic
Professional Office — Civic
Corporate Office — 1/8 Floor
Corporate Office — 1/4 Floor
Corporate Office — 1/2 Floor
Corporate Office — 3/4 Floor
Corporate Office — Full Floor
```

A generic Professional Office tenant who does not fall into any of the five specialisations uses the Initial Design baseline at 130 m² / 1,400 SF. In practice this is rare: most professional-services firms self-identify as Business, clinical practices as Medical, and research operations as Laboratory.

## Why Small + Small combinations matter

Combining two Professional Office Smalls fills the gap between Professional Office Large and Corporate Office 1/8 Floor. The combinations table across sub-types:

| Combination | Lab | Academic | Business | Medical | Civic |
|---|---|---|---|---|---|
| Small + Small | 390 m² / 4,198 SF | 210 / 2,262 | 622 / 6,700 | 446 / 2,402 | 540 / 5,824 |
| Small + Medium | 511 / 5,500 | 345 / 3,714 | 711 / 7,652 | 554 / 5,969 | 847 / 9,127 |
| Small + Large | 596 / 6,412 | 483 / 5,201 | 980 / 10,874 | 709 / 7,633 | 1,092 / 11,762 |
| Medium + Large | 717 / 7,714 | 618 / 6,653 | 1,069 / 11,826 | 817 / 8,799 | 1,399 / 15,065 |

Combinations are how a Professional Centre fills a floor plate without gaps. Two Small Lab suites (390 m²) plus one Medium Medical suite (331 m²) plus one Large Civic suite (822 m²) = 1,543 m² — which fits inside a typical 19,000–23,000 SF Professional Centre floor alongside the building core, amenities, and elevator lobby.

## Initial Design vs sub-type zone widths

The Initial Design Z2 = 3.8 m is narrower than four of the five sub-types:

| Sub-type | Z2 Magazine | Delta vs Initial Design |
|---|---:|---:|
| Initial Design | 3.8 m | (baseline) |
| Academic | 3.0 m | −0.8 m |
| Medical | 4.9 m | +1.1 m |
| Laboratory | 4.8 m | +1.0 m |
| Business | 7.3 m | +3.5 m |
| Civic | 7.2 m | +3.4 m |

The Initial Design cannot satisfy any of the five specialisations without dimensional expansion. It serves as the "Professional Office without specialisation" footprint — as soon as a tenant declares a specialisation, the sub-type's Building Width Calculator applies.

## The 21 m vs 21.6 m discrepancy

The methodology presents the Professional Office total floor-plate width as 21 m (centreline) and 21.6 m when demising and structural walls are included. The arithmetic 2 × (6.0 + 3.8) + 2.0 = 21.6 m confirms that the "21 m" figure is the centreline-to-centreline distance and 21.6 m includes a 0.6 m demising-structural overhead. This overhead should be encoded as a distinct DTCG token to make the arithmetic self-documenting.

## Why no Professional Office Medium / Large samples exist

No source document carries a Professional Office Medium or Large sample at the Initial Design baseline. The sub-type Medium and Large roles are filled by the five specialisations' own Medium and Large samples. A tenant who needs a larger generic Professional Office in practice leases two Smalls (Small + Small ≈ 260 m² / 2,800 SF).

## See also

- [[topic-bim-key-plans-index]]
- [[topic-bim-business-key-plans]]
- [[topic-bim-medical-key-plans]]
- [[topic-bim-zone-depths-per-use-type]]
- [[topic-bim-building-width-method]]
