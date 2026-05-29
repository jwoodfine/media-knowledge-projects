---
schema: foundry-doc-v1
title: "Retail Brand Family Taxonomy"
slug: topic-retail-brand-family-taxonomy
category: governance
type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: PROSE-TOPIC
last_edited: 2026-05-25
editor: pointsav-engineering
short_description: "Every retail location on the co-location map carries a brand family classification that determines how the location is displayed and, for some families, whether it contributes to cluster scoring. The taxonomy was designed around the anchor types used in the co-location methodology while remaining extensible to the full range of ingested operators."
paired_with: topic-retail-brand-family-taxonomy.es.md
cites:
  - osm-odbl
  - ni-51-102
  - osc-sn-51-721
---

Every retail location on the [[topic-co-location-methodology|co-location]] map carries a brand family classification — a categorical label that determines how the location is displayed and, for some families, whether it contributes to cluster scoring. The taxonomy was designed around the specific [[topic-co-location-anchors|anchor]] types used by the [[topic-co-location-ranking-system|deterministic ranking system]] while remaining extensible to the full range of operators ingested as supporting data.

## The Six Primary Families

### Hypermarket

Large-format general merchandise and grocery retailers operating facilities of 80,000 square feet or more. Includes Walmart Supercenter, Target, Carrefour Hypermarket, IKEA, and equivalents across [[topic-tier-index-north-america|North American]] and [[topic-tier-index-europe|European]] markets. Hypermarket stores are the primary anchor type in the co-location methodology — cluster formation requires one Hypermarket anchor. Displayed with a navy badge.

### Hardware

Home improvement and building materials retailers. Includes Home Depot, Lowe's, Leroy Merlin, Canadian Tire, Hagebaumarkt, Praktiker, and regional equivalents. Hardware co-presence within the defined secondary radius of the primary anchor is the first scoring criterion in the co-location index. Displayed with an orange badge.

### Warehouse

Membership and cash-and-carry retailers operating under a wholesale or club format. Includes Costco, Sam's Club, BJ's Wholesale, Makro, and Metro. Warehouse co-presence within the secondary radius of the primary anchor is the second scoring criterion. Displayed with a teal badge.

### Food

Conventional and specialty grocery operators. Includes Save-On-Foods, Safeway, Whole Foods, Lidl, Mercadona, Biedronka, and regional grocery chains across all covered markets. Food-family stores are ingested and displayed on the All Locations layer as supporting context — they are visible on the map — but they do not affect cluster scores or tier assignments. This preserves the co-location index as a measure of large-format anchor convergence rather than general retail density. Displayed with a green badge.

### Furniture

Home furnishings and décor specialists operating at scale. Currently populated by Conforama in the Spanish market, with expansion to other European furniture retailers is intended. Displayed with a purple badge.

### Pharmacy

Health and pharmacy retail with a significant non-pharmaceutical product mix. Currently populated by London Drugs in the Canadian market. Displayed with a violet badge.

## Supporting Families

### Department

Traditional department store operators not classified as large-format hypermarkets. Currently populated by Macy's in the United States. Department stores typically share commercial zones with anchor-category retailers but represent a distinct format that does not map to any of the co-location methodology tier categories. Displayed with a neutral grey badge.

## Medical and Academic

Hospital and university locations, ingested as civic infrastructure, are classified outside the brand family system using a category identifier rather than a family identifier. Medical (hospital) and Academic (university) locations are displayed with distinct badges and contribute to tertiary scoring in the co-location methodology.

## Classification Scope

All ingested locations carry one of these classifications in their brand family field. Locations without a recognised chain identifier receive no brand family and display without a category badge. Unclassified locations remain visible on the map as grey dots and do not affect scoring.

## See Also

- [[topic-co-location-methodology]]
- [[topic-uk-eu-food-retail-coverage]]
