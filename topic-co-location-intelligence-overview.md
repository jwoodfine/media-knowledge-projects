---
schema: foundry-doc-v1
title: "Retail Co-location Intelligence — Overview"
slug: topic-co-location-intelligence-overview
aliases:
  - topic-co-location-intelligence-overview
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
short_description: "Systematic geographic analysis identifying and ranking retail sites where large-format categories converge within defined catchment radii."
paired_with: topic-co-location-intelligence-overview.es.md
cites:
  - overture-maps-cdla-2-0
  - osm-odbl
  - ni-51-102
  - osc-sn-51-721
---

Woodfine Management Corp.'s co-location intelligence platform ranks 2,738 commercial nodes across 8 retail markets by anchor convergence — the independent co-location of hypermarkets, warehouse clubs, and home improvement superstores at the same trade area. Each node is validated not by analyst forecasts, but by the independent capital commitments of the retailers who located there. Convergence is measured per the [[topic-co-location-methodology|co-location methodology]] and scored by the [[topic-co-location-ranking-system|deterministic ranking system]]; the population and spend inputs are documented in [[topic-trade-area-data-sources|trade-area data sources]] and the geographic policy in the [[topic-regional-market-matrix|regional market matrix]].

The platform is operated at [gis.woodfinegroup.com](https://gis.woodfinegroup.com), built and maintained by PointSav Digital Systems.

## Strategic Objective

Large-format retailers do not locate arbitrarily. Supercenter operators, warehouse clubs, and home improvement superstores each independently apply capital-intensive site selection criteria — traffic counts, household income density, road-network accessibility, and competitive positioning. When two or three such operators converge on the same node within a given corridor, that convergence signals a validated commercial location: one where multiple independent parties have independently committed capital to serve the same trade area. The qualifying [[topic-co-location-anchors|anchor]] adjacency requirement is binary, not a matter of degree.

The co-location intelligence system identifies and ranks those nodes using a deterministic named-anchor combination matrix. The output is a ranked index of sites, expressed as five quality tiers, which can be filtered by region, country, and secondary radius.

## Geographic Coverage and Scale

The platform currently evaluates 8 retail markets across 13 countries, providing a cross-border view of retail density and commercial defensibility.

| Region | Countries | Anchor operators |
|--------|-----------|-----------------|
| United States | US | Walmart, IKEA |
| Canada | CA | Walmart, IKEA, Real Canadian Superstore |
| Mexico | MX | Walmart, IKEA |
| Spain | ES | IKEA, Carrefour, Alcampo, Leclerc |
| Italy | IT | IKEA, Carrefour, Ipercoop, Iper La Grande, Bennet |
| Greece | GR | IKEA |
| Poland | PL | IKEA, Carrefour, Leclerc, Auchan |
| Nordics | SE · NO · DK · FI · IS | IKEA, Bilka, Prisma, K-Citymarket, Obs Coop |

## Data Foundations

The platform integrates three primary data sources to ensure high-fidelity spatial analysis:

1.  **Service-business (Retail Operators):** Sourced from OpenStreetMap contributors, filtered by canonical brand Wikidata identifiers to ensure consistent brand-family matching across borders. As of 2 May 2026, the dataset contains 31,219+ individual retail locations across 60+ chains.
2.  **Service-places (Civic Infrastructure):** Hospital and medical center records sourced from the Overture Maps Foundation Places dataset (2026-04-15 release). This tertiary layer provides the "stabilizing" demographic context required for high-tier ranking.
3.  **Service-transport (Logistics Support):** Aviation facility records from Overture Maps Foundation, retained for future tertiary scoring dimensions.

*Material assumptions for current dataset counts include the continued availability of OpenStreetMap and Overture Maps Foundation data under their respective licenses (ODbL and CDLA Permissive 2.0). [osm-odbl] [overture-maps-cdla-2-0]*

## Site Index and Quality Tiers

The current dataset identifies **2,738 ranked co-location sites** globally: 2,488 in [[topic-tier-index-north-america|North America]] and 250 in [[topic-tier-index-europe|Europe]]. Sites are ranked using a deterministic matrix that evaluates the proximity and category of secondary anchors relative to a primary hypermarket anchor.

| Tier | Description | NA count | EU count |
|------|-------------|----------|----------|
| ★★★★★ | Full co-location | 102 | 0 |
| ★★★★ | Strong co-location | 259 | 9 |
| ★★★ | Partial co-location | 1,396 | 175 |
| ★★ | Limited co-location | 333 | 23 |
| ★ | Anchor only | 398 | 43 |

The current absence of Tier 5 sites in Europe reflects data coverage target milestones; the tertiary scoring dimension (healthcare and higher education) currently draws on Overture data that has established maturity in North American markets. Expansion of European tertiary data sources is an intended target for future platform iterations. [ni-51-102] [osc-sn-51-721]

## Interactive Surface

The Geographic Information System (GIS) platform renders the ranked site index as an interactive map at [gis.woodfinegroup.com](https://gis.woodfinegroup.com). The interface supports real-time filtering by cluster grade and catchment radius (1 km, 2 km, or 3 km). 

The platform is updated when new chain data is ingested or when the ranking matrix is recalibrated. All dataset counts and version identifiers are displayed in the platform header to ensure operational transparency.

## Provenance
- **Verification:** Site counts and country coverage verified against the GIS platform configuration as of 2 May 2026.
- **Forward-looking disclosure:** European tertiary data expansion targets are intended outcomes, labeled per [ni-51-102].

## See Also
*   [[topic-co-location-methodology]]
*   [[topic-co-location-ranking-system]]
*   [[topic-tier-index-north-america]]

## References

- [Retail park](https://en.wikipedia.org/wiki/Retail_park) — Wikipedia, accessed 2026-06-14
- [Big-box store](https://en.wikipedia.org/wiki/Big-box_store) — Wikipedia, accessed 2026-06-14

---

*Copyright © 2026 Woodfine Capital Projects Inc. Licensed under [Creative Commons Attribution 4.0 International](https://creativecommons.org/licenses/by/4.0/).*
