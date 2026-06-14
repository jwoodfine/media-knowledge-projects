---
schema: foundry-doc-v1
title: "Co-location Tier Nomenclature"
slug: topic-co-location-tier-nomenclature
aliases:
  - topic-co-location-tier-nomenclature
category: governance
type: topic
content_type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: PROSE-TOPIC
last_edited: 2026-05-25
editor: pointsav-engineering
short_description: "The four tier labels — Regional, District, Local, Fringe — visible on the co-location map follow the International Council of Shopping Centres retail property hierarchy, providing a nomenclature that carries meaning independently of the platform itself. Sprint 17 (May 2026) introduced both the ICSC labels and the V3 pure-predicate tier engine."
paired_with: topic-co-location-tier-nomenclature.es.md
cites:
  - ni-51-102
  - osc-sn-51-721
---

The [[topic-co-location-methodology|co-location index]] assigns each cluster to one of four tiers based on the categorical composition of its [[topic-co-location-anchors|anchor]] and secondary stores and on the cluster's position within its national population catchment. The tier labels visible on the map and in the inspector panel — **Regional**, **District**, **Local**, **Fringe** — follow the International Council of Shopping Centres (ICSC) retail property hierarchy, which is used by property developers, planners, and retail analysts across [[topic-tier-index-north-america|North America]] and [[topic-tier-index-europe|Europe]]. The qualifying gates are defined in the [[topic-catchment-ranking-methodology-v3|V3 catchment ranking methodology]] and the underlying scoring logic in the [[topic-co-location-ranking-system|co-location ranking system]].

## What Each Tier Means

| Tier | Name | Description |
|---|---|---|
| 1 | **Regional** | A nationally significant co-location node. Contains both a hypermarket-format anchor and a warehouse club or lifestyle anchor, is in the top decile of its country by primary catchment population, and has a regionally classified hospital within the civic ring. The highest tier. |
| 2 | **District** | A sub-regional trade-area node. Contains a hypermarket and a hardware or warehouse anchor, is in the top quartile of its country by primary catchment population, and has hospital access within the civic ring. |
| 3 | **Local** | A hardware or wholesale hub with community-level civic support. Contains at least one hardware or warehouse anchor, is in the top half of its country by primary catchment population, and has any hospital within the civic ring. |
| 4 | **Fringe** | Below threshold on one or more required gates. A commercial cluster with retail co-tenancy but insufficient catchment reach, composition, or civic support to qualify for Local or above. |

## Composition Chips

Each cluster carries a composition descriptor displayed below the tier badge in the inspector. The descriptor names the anchor classes present, separated by "+": for example, "Hypermarket + Hardware + Warehouse" or "Lifestyle + Hypermarket". The four anchor classes are Hypermarket (general-merchandise stores: Walmart, Target, Mercadona, Tesco, Sainsbury's), Lifestyle (large-format home and furnishings: IKEA), Hardware (home improvement: Home Depot, Lowe's, Leroy Merlin), and Warehouse (membership warehouse clubs: Costco, Sam's Club, Makro). The full chain-to-family mapping is documented in the [[topic-retail-brand-family-taxonomy|retail brand family taxonomy]].

## Naming History

The tier labels have been renamed twice since the platform launched.

**Sprint 9 (May 2026):** The original numeric labels (T3 Full Complement, T2 Retail Anchor, T0 Commercial Node, and variants) were replaced with plain-English nouns: Prime, Strong (Retail), Strong (Bulk), Strong (Hub), Core (Hyper), Core (Hardware), Core (Wholesale), Emerging. This resolved two readability failures: "+" ambiguity in compound descriptors, and the cognitive cost of mapping a tier number to a quality rank.

**Sprint 17 (May 2026):** The Sprint 9 labels were replaced with the ICSC hierarchy: Regional, District, Local, Fringe. The motivation was alignment with an internationally recognised nomenclature that carries meaning without requiring platform-specific context. A planner who opens the inspector without reading documentation knows what "Regional" means; "Prime" required learning.

The Spanish-language equivalents are: Regional, Distrital, Local, Marginal.

## What Changed and What Did Not

The Sprint 17 rename coincided with the introduction of the V3 pure-predicate tier engine. Before Sprint 17, tiers were assigned by a composite score (V2: base score + count bonus + diversity bonus + civic depth + overlap penalty). From Sprint 17 forward, tiers are assigned by binary gates: composition + national catchment rank + civic classification + spatial overlap limit. The gate definitions are described in the Catchment Ranking Methodology document.

The tier names changed from Sprint 9 labels to ICSC labels. The tier assignment method changed from score-threshold to predicate-gate. Both changes shipped together in Sprint 17.

## Reading the Inspector Panel

When a user selects a cluster on the map, the inspector panel displays the tier name as a large coloured badge. Below the badge, a muted composition chip names the anchor classes present.

The badge colour encodes the hierarchy: dark navy for Regional, indigo for District, slate for Local, light grey for Fringe.

## See Also

- [[topic-co-location-methodology]]
- [[topic-catchment-ranking-methodology-v3]]
- [[topic-retail-brand-family-taxonomy]]
