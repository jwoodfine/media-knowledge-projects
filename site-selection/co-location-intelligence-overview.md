---
schema: foundry-doc-v1
title: "Retail co-location intelligence — overview"
slug: co-location-intelligence-overview
category: site-selection
index_group: strategy-and-investment-thesis
type: topic
index_type: thematic
content_type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: PROSE-TOPIC
last_edited: 2026-09-04
editor: pointsav-engineering
short_description: "Systematic geographic analysis identifying and classifying retail sites where large-format categories converge within defined catchment radii."
paired_with: site-selection/co-location-intelligence-overview.es.md
cites:
  - overture-maps-cdla-2-0
  - osm-odbl
  - ni-51-102
  - osc-sn-51-721
---

Woodfine's co-location intelligence platform classifies commercial nodes across a cross-border network of North American and European retail markets by anchor convergence — the independent co-location of hypermarkets, warehouse clubs, and home improvement superstores at the same trade area. Each node is validated not by analyst forecasts, but by the independent capital commitments of the retailers who located there. Convergence is measured per the [[co-location-methodology|co-location methodology]] and classified by the [[co-location-ranking-system|deterministic ranking system]]; the population and spend inputs are documented in [[trade-area-data-sources|trade-area data sources]] and the geographic policy in the [[about-regional-markets-system|regional market matrix]].

The platform is operated at [gis.woodfinegroup.com](https://gis.woodfinegroup.com).

## Strategic objective

Large-format retailers do not locate arbitrarily. Supercenter operators, warehouse clubs, and home improvement superstores each independently apply capital-intensive site selection criteria — traffic counts, household income density, road-network accessibility, and competitive positioning. When two or three such operators converge on the same node within a given corridor, that convergence signals a validated commercial location: one where multiple independent parties have independently committed capital to serve the same trade area. The qualifying [[co-location-anchors|anchor]] adjacency requirement is binary, not a matter of degree.

The co-location intelligence system identifies and classifies those nodes using a deterministic predicate-gate model. The output is a tiered index of sites — Regional, District, Local, Fringe — which can be filtered by region, country, and secondary radius.

## Geographic coverage and scale

The platform evaluates co-location clusters across North American and European retail markets, giving a cross-border view of retail density and commercial defensibility. Coverage expands as new chain data is ingested, so the live GIS platform — not this article — is the authoritative statement of which countries and which anchor operators are currently in scope. A wiki snapshot of coverage goes stale between data-refresh cycles; the platform does not.

Anchor operators are mapped onto four canonical classes — hypermarket, lifestyle, hardware, and warehouse — so that a regional chain in any covered market is evaluated on the same footing as its North American equivalent. That mapping is what makes cross-border comparison meaningful rather than nominal, and the chain-to-class assignments are documented in [[retail-brand-family-taxonomy|the retail brand family taxonomy]].

## Data foundations

The platform integrates three primary data sources to ensure high-fidelity spatial analysis:

1.  **Business location data (retail operators):** Sourced from OpenStreetMap contributors, filtered by canonical brand Wikidata identifiers to ensure consistent brand-family matching across borders. The dataset spans tens of thousands of individual retail locations across dozens of chains, and is refreshed on an ongoing basis as new chain data is ingested.
2.  **Place data (civic infrastructure):** Hospital and medical centre records sourced from the Overture Maps Foundation Places dataset. This tertiary layer provides the civic context required for the Regional and District tier gates.
3.  **Transportation data (logistics support):** Aviation facility records from Overture Maps Foundation, retained for tertiary scoring dimensions the platform may add in future.

*Material assumptions for the dataset include the continued availability of OpenStreetMap and Overture Maps Foundation data under their respective licenses (ODbL and CDLA Permissive 2.0). [osm-odbl] [overture-maps-cdla-2-0]*

## Site index and tier classification

Every scored node is classified into one of four tiers — **Regional**, **District**, **Local**, **Fringe** — covered by the [[co-location-tier-system|co-location tier system]]. A cluster earns its tier by clearing predicate gates on anchor composition, national catchment rank, civic infrastructure, and spatial non-overlap, described in full in the [[catchment-ranking-methodology|catchment ranking methodology]].

Current site counts by tier and country are published live on the GIS platform rather than restated here; a wiki snapshot goes stale between data-refresh cycles, while the platform updates on every processing run.

## Interactive surface

The Geographic Information System (GIS) platform renders the tiered site index as an interactive map at [gis.woodfinegroup.com](https://gis.woodfinegroup.com). The interface supports real-time filtering by cluster tier and by catchment radius.

The platform is updated when new chain data is ingested or when tier assignment is recalibrated. All dataset counts and version identifiers are displayed in the platform header, so the current figures are always available at source.

## Provenance
- **Verification:** Country coverage and anchor-operator scope are verified against the GIS platform's live cluster dataset rather than restated here.
- **Forward-looking disclosure:** European tertiary data expansion targets are intended outcomes, labeled per [ni-51-102].

## See also

- [[co-location-methodology]]
- [[co-location-ranking-system]]
- [[co-location-tier-system]]

## References

- [Retail park](https://en.wikipedia.org/wiki/Retail_park) — Wikipedia, accessed 2026-06-14
- [Big-box store](https://en.wikipedia.org/wiki/Big-box_store) — Wikipedia, accessed 2026-06-14

---

*Copyright © 2026 Woodfine Capital Projects Inc. Licensed under [Creative Commons Attribution-NoDerivatives 4.0 International](https://creativecommons.org/licenses/by-nd/4.0/).*
