---
schema: foundry-doc-v1
title: "Co-location tier system"
slug: co-location-tier-system
category: markets
index_group: coverage-methodology
type: topic
content_type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: PROSE-TOPIC
last_edited: 2026-08-26
editor: editorial
short_description: "The four-tier classification — Regional, District, Local, Fringe — assigned to every co-location cluster on the platform, the predicate gates that determine it, and how the system applies across North American and European markets."
paired_with: markets/co-location-tier-system.es.md
cites:
  - ni-51-102
  - osc-sn-51-721
---

Every co-location cluster the platform tracks carries one of four tiers — **Regional**, **District**, **Local**, or **Fringe**. The tier reports how strongly independent capital commitments have converged on that node before any land is bought. Retail anchors, catchment population, and civic infrastructure are the three converging signals. Map-facing labels follow the International Council of Shopping Centres (ICSC) retail property hierarchy; the full naming history is in [[co-location-tier-nomenclature|tier nomenclature]].

## How a tier is assigned

A cluster earns its tier by clearing a set of predicate gates — pass-or-fail tests, not a points score. Four gate families apply.

**Composition.** Every cluster forms around a [[co-location-anchors|primary anchor]] from one of four classes: Hypermarket (general-merchandise chains such as Walmart, Target, Mercadona, and Tesco), Lifestyle (large-format home retailers — IKEA is the sole chain in this class), Hardware (home-improvement chains such as Home Depot, Lowe's, and Leroy Merlin), and Warehouse (membership clubs such as Costco, Sam's Club, and Makro). The classes present at one node determine which tier a cluster can reach.

**Catchment rank.** A cluster's population is ranked against others in its own country, so a node is judged against national conditions rather than a single cross-border yardstick. Higher tiers require a higher national standing.

**Civic presence.** A qualifying hospital must sit within the cluster's civic ring. Regional and District require a regionally or district-classified hospital; Local accepts any hospital classification.

**Non-overlap.** Neighbouring clusters that substantially overlap are compared against each other. A cluster dominated by a stronger neighbour is held below the tier its composition would otherwise earn, so that one trading location is not counted twice.

## The four tiers

| Tier | What it requires |
|---|---|
| **Regional** | A hypermarket paired with a warehouse or lifestyle anchor, catchment population in the highest national band, and a regional hospital within the civic ring. The highest tier. |
| **District** | A hypermarket paired with hardware or warehouse, catchment population in a high national band, and hospital access within the civic ring. |
| **Local** | A hardware or warehouse anchor, catchment population above the national midpoint, and any hospital within the civic ring. |
| **Fringe** | Retail co-tenancy is present, but catchment reach, composition, or civic support falls short of Local. |

## Application across North America and Europe

The tier system applies identically on both continents; only the anchor network differs. In North America, Walmart Supercentre is the dominant primary anchor, paired against Home Depot and Costco as secondaries. In Europe, IKEA is the primary anchor across Spain, the Nordic countries, Italy, and Poland, paired against Leroy Merlin and Makro.

| Market | Primary anchor | Detailed index |
|---|---|---|
| United States | Walmart Supercentre | [[atlas-united-states]] |
| Canada | Walmart Supercentre | [[atlas-canada]] |
| Mexico | Walmart Supercentre | [[atlas-co-location-index-mexico]] |
| Spain | IKEA | [[atlas-spain]] |
| Nordics | IKEA | [[atlas-co-location-index-nordics]] |
| Italy | IKEA | [[atlas-italy]] |
| Poland | IKEA | [[atlas-poland]] |

Current tier counts by country are published live on the GIS platform rather than restated here; a wiki snapshot goes stale between data-refresh cycles, while the platform updates on every processing run.

Expansion of the tertiary civic dataset — bringing university and hospital coverage in Mexico and Canada to the same maturity as the United States — is a planned target for future iterations. [ni-51-102] [osc-sn-51-721]

## Provenance
- **Verification:** Tier definitions and predicate gates confirmed against the GIS platform's current scoring methodology.
- **Forward-looking disclosure:** Tertiary civic dataset expansion for Mexico and Canada is an intended outcome, labeled per [ni-51-102].

## See also
*   [[co-location-methodology]]
*   [[co-location-tier-nomenclature]]
*   [[co-location-ranking-system]]

---

*Copyright © 2026 Woodfine Capital Projects Inc. Licensed under [Creative Commons Attribution-NoDerivatives 4.0 International](https://creativecommons.org/licenses/by-nd/4.0/).*
