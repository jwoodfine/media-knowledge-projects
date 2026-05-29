---
schema: foundry-doc-v1
title: "Cluster Deduplication Threshold"
slug: topic-cluster-deduplication-threshold
category: governance
type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: PROSE-TOPIC
last_edited: 2026-05-25
editor: pointsav-engineering
short_description: "The co-location index pipeline deduplicates overlapping clusters that represent the same commercial zone using a 150-metre threshold, retaining the cluster with the higher secondary operator count. A prior 500-metre threshold was found to suppress legitimately distinct commercial nodes in dense suburban corridors."
paired_with: topic-cluster-deduplication-threshold.es.md
cites:
  - ni-51-102
  - osc-sn-51-721
---

The [[topic-co-location-methodology|co-location index]] pipeline produces one cluster per [[topic-co-location-anchors|anchor]] store — every qualifying hypermarket, hardware retailer, and warehouse club generates a candidate cluster centred on that store's coordinates, per the [[topic-co-location-cluster-formation|cluster formation]] rules. When two anchors occupy the same commercial zone, the result is two overlapping clusters representing the same trade area. The deduplication step resolves that redundancy. Trade-area inputs to the [[topic-co-location-ranking-system|ranking system]] are aggregated after deduplication runs.

## The Same-Parking-Lot Problem

Large commercial zones frequently host two or more anchor-category stores within metres of each other. A Home Depot and a Costco sharing a parking lot in suburban Edmonton, for example, sit roughly 20 metres apart. Without deduplication, both stores produce clusters with nearly identical catchment geometry, co-tenants, and scores. The map displays two concentric rings covering the same zone — neither wrong in isolation, but together misleading about the number of distinct commercial nodes in that corridor.

## Threshold Selection: 0.15 km

The deduplication step removes any cluster whose anchor store falls within a fixed radius of a higher-ranked cluster anchor already confirmed for retention. The threshold is set at **0.15 km (150 metres)**. At this distance, only stores that genuinely share a single parking lot or immediate building complex are collapsed. Anchors in adjacent strip malls separated by a service road (typically 200–500 metres apart) are treated as distinct nodes and retained.

An earlier implementation used a 0.50 km threshold. Field review of the Edmonton metropolitan area identified cases where legitimate, separately operated commercial zones were being suppressed without notification: a Walmart-anchored node and a Home Depot-anchored node in neighbouring commercial blocks, serving different residential catchments, were treated as duplicates and one was removed. The 0.50 km threshold proved too coarse for dense suburban corridors in Canadian and North American markets.

## Ranking the Survivor

When two anchors fall within the threshold distance, the retained cluster is the one with the higher count of co-tenants within the 3 km catchment radius. Ties break on the 1 km count. This ensures that the cluster representing the fuller commercial zone — more stores, broader multi-purpose draw — survives, regardless of which anchor happened to be processed first.

## Pipeline Effect

After applying the 0.15 km threshold, a representative pipeline run produced 6,422 retained clusters from 7,594 candidates — 1,172 same-zone duplicates removed. The reduction is concentrated in dense commercial corridors where multiple anchor formats co-locate in close proximity. Tier distribution and national rankings are assigned after deduplication runs, so the published counts reflect deduplicated zones only.

## See Also

- [[topic-co-location-methodology]]
- [[topic-tier-index-north-america]]
