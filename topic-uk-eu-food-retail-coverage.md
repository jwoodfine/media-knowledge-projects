---
schema: foundry-doc-v1
title: "UK and European Food Retail Coverage"
slug: topic-uk-eu-food-retail-coverage
category: governance
type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: PROSE-TOPIC
last_edited: 2026-05-25
editor: pointsav-engineering
short_description: "The co-location index distinguishes between chains that participate in cluster scoring — anchors, hardware, warehouse — and chains that appear on the map as supporting context without affecting cluster grades. The Food family is the latter. This article documents United Kingdom and European Union food-retail coverage as of the May 2026 expansion."
paired_with: topic-uk-eu-food-retail-coverage.es.md
cites:
  - osm-odbl
  - ni-51-102
  - osc-sn-51-721
---

The [[topic-co-location-methodology|co-location index]] distinguishes between retail chains that participate in the cluster scoring algorithm — [[topic-co-location-anchors|anchors]], hardware, warehouse clubs — and chains that appear on the map as supporting context but do not affect cluster grades. The latter category is the Food family within the [[topic-retail-brand-family-taxonomy|retail brand family taxonomy]]. This article documents the United Kingdom and European Union food-retail coverage as of the May 2026 expansion.

## Why Food Is Data-Only

The [[topic-co-location-methodology|co-location methodology]] measures the convergence of large-format anchor stores: hypermarkets, hardware retailers, warehouse clubs. Adding a grocery chain to the [[topic-co-location-ranking-system|scoring algorithm]] would dilute the signal — most urban areas have many grocery operators, so a "co-location" of one anchor and one grocer would provide limited insight into commercial density. Keeping the Food family data-layer-only preserves the index as a measure of large-format anchor convergence while still showing field operators the broader retail context around an anchor.

A Tesco store appears on the map as a green dot. It does not contribute to any cluster grade. It does appear in the inspector panel of the surrounding cluster as part of the All Locations layer.

## United Kingdom Coverage

Three chains anchor the UK food layer as of May 2026:

| Chain | Wikidata | Approx. Stores | Notes |
|---|---|---|---|
| Tesco | Q487494 | 3,300 | Largest UK grocer. Sub-formats Extra, Superstore, Metro, Express are handled via the post-ingest sub-entity pass. |
| Sainsbury's | Q152096 | 1,400 | Local + Superstore sub-formats. |
| Lidl GB | Q151954 | 960 | Discount segment. Country bounding box confines results to Great Britain. |

These join the prior UK retail coverage of B&Q (hardware), IKEA (anchor), and Costco (anchor + warehouse). The Food layer roughly triples the on-map dot density across the United Kingdom while leaving the cluster grades unchanged.

## European Union Coverage

Five Lidl country instances and four Aldi country instances were added in May 2026:

| Lidl | Wikidata | Approx. Stores | | Aldi | Wikidata | Approx. Stores |
|---|---|---|---|---|---|---|
| Lidl Germany | Q151954 | 3,250 | | Aldi Germany | Q41171 + name query | 4,200 |
| Lidl France | Q151954 | 1,600 | | Aldi United Kingdom | Q41171 + name query | 1,000 |
| Lidl Netherlands | Q151954 | 440 | | Aldi Netherlands | Q125054 + name query | ~480 |
| Lidl Austria | Q151954 | 260 | | Aldi Poland | Q41171 + name query | 280 |
| Lidl Portugal | Q151954 | 270 | | | | |

Aldi operates as two corporate entities — Aldi Süd (Wikidata Q41171) and Aldi Nord (Wikidata Q125054) — that split European geography along a north-south axis. In the Netherlands and Nordic-adjacent markets, only Aldi Nord operates. In the United Kingdom and Poland, only Aldi Süd operates. The OpenStreetMap brand identifier tag on individual store records is inconsistent across markets — many stores carry one identifier, the other, or neither. To achieve acceptable coverage in markets where the identifier tag is sparse, the ingest configuration falls back to a name-based query confined to the country's bounding box.

## Coverage Observations

Three coverage notes surfaced during the May 2026 expansion:

**Aldi Netherlands undercoverage.** The first ingest pass returned three records via the Wikidata identifier query, well below the expected approximately 480 stores. Switching the configuration to force the name-based query fallback restored coverage to several hundred records.

**Tesco sub-format leak.** Tesco operates Express stores in transport-hub formats. A small number of these may be tagged with non-store tags in OpenStreetMap and dropped during the fuel-station and pharmacy filter pass. Field review of urban Tesco coverage is encouraged.

**Food-family expansion is not exhaustive.** Carrefour France, Auchan, Mercadona Spain, and other major European grocers are not yet ingested in their home countries. Adding each is a single chain configuration addition; these were not within the May 2026 sprint scope.

## Why This Matters

For a Woodfine evaluation of a development opportunity in the United Kingdom or Continental Europe, the co-location grade tells one story: how many large-format anchors converge on this site. The Food layer adds a second story: what is the surrounding daily-trip retail density. A cluster with a strong grade and high local Food density behaves differently in the field from a cluster with the same grade in a sparse Food-density market. Keeping the two layers analytically separate but visually present is the design intent.

## See Also

- [[topic-retail-brand-family-taxonomy]]
- [[topic-co-location-methodology]]
