---
schema: foundry-doc-v1
title: "Co-location Cluster Formation"
slug: topic-co-location-cluster-formation
aliases:
  - topic-co-location-cluster-formation
category: governance
type: topic
quality: stub
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: PROSE-TOPIC
last_edited: 2026-06-04
editor: pointsav-engineering
paired_with: topic-co-location-cluster-formation.es.md
---

# Co-location Cluster Formation

Cluster formation is the step in the [[topic-co-location-methodology|co-location index]] pipeline that turns qualifying anchor stores into candidate clusters. Every qualifying [[topic-co-location-anchors|anchor]] store — each hypermarket, home-improvement superstore, and warehouse club that has independently committed capital within 1.0 to 3.0 km of the others — generates one candidate cluster centred on that store's coordinates.

Because each anchor produces its own candidate, a single commercial zone with several adjacent anchors yields several overlapping clusters that describe the same trade area. Those overlaps are resolved downstream by the [[topic-cluster-deduplication-threshold|deduplication]] step before trade-area inputs are aggregated for the [[topic-co-location-ranking-system|ranking system]].

Cluster formation does not score or rank. It only enumerates candidate clusters from the qualification logic; qualification, formation, and anchor adjacency are the three structural inputs to the index.

## See also

- [[topic-co-location-methodology|Retail Co-location Methodology]]
- [[topic-co-location-anchors|Co-location Anchors]]
- [[topic-cluster-deduplication-threshold|Cluster Deduplication Threshold]]
