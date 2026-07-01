---
schema: foundry-doc-v1
title: "GIS Cluster Scoring Glossary"
slug: gis-cluster-scoring-glossary
category: reference
type: topic
content_type: topic
quality: complete
short_description: "Definitions for the cluster degree terminology (First- through Fifth-Degree Cluster), tier labels (T3 Apex, T2 Hub, T1 Valid), and radius threshold conventions used in the Woodfine geographic co-location scoring system — the vocabulary for interpreting co-location dataset outputs and GIS coverage reports."
status: stable
bcsc_class: current-fact
last_edited: 2026-07-01
editor: pointsav-engineering
language_protocol: PROSE-TOPIC
source_refs:
  - "bfe6fb6bbb557fd15bdb7ffd53bce60e527911eb7658c906df5b69813bdb8747"
  - "42cddb0e1bbd6516c578dbfe4a48f5ff2fd084529ef9adeaf09612c3bd36a5e1"
paired_with: gis-cluster-scoring-glossary.es.md
cites: []
---

This glossary defines the terminology used in Woodfine Management Corp.'s geographic co-location scoring system. The vocabulary covers cluster degree designations, tier score labels, radius threshold conventions, and dataset output metrics. These terms appear in co-location dataset reports, GIS coverage communications, and site selection materials prepared for review by the Independent Directors of the General Partner.

## Cluster Degree Terms

**First-Degree Cluster** — A scored co-location node at which a Primary Target (Walmart Supercentre) and at least one Secondary Target (Home Depot or Costco Wholesale) are located within 1.0 km of each other. The baseline indicator of a co-anchored commercial node.

**Second-Degree Cluster** — A First-Degree Cluster at which at least one Tertiary Target (a post-secondary institution or a major medical centre) is located within 5.0 km. Indicates co-anchor presence plus institutional employment demand within commute range.

**Third-Degree Cluster** — A scored node at which a Primary Target and both Secondary Targets (Home Depot and Costco Wholesale) are located within 1.0 km of each other. Requires dual secondary confirmation at the 1.0 km radius.

**Fourth-Degree Cluster** — A Third-Degree Cluster with at least one Tertiary Target within 5.0 km. Dual secondary confirmation plus institutional employment demand.

**Fifth-Degree Cluster** — A Third-Degree Cluster with both Tertiary Targets (post-secondary institution and major medical centre) within 5.0 km. The highest-conviction cluster designation in the scoring system: five independent categories of institutional investment confirmed within the applicable radius thresholds.

## Tier Score Labels

The V2 scoring methodology assigns scored clusters to three tiers based on aggregate score:

**T3 Apex** — Score ≥ 700. The top-tier designation. A T3 Apex cluster meets the full Primary plus Secondary co-occurrence threshold and has sufficient score from Tertiary proximity and Primary Target sales productivity to clear the 700-point threshold. T3 Apex clusters represent the highest-priority Development Site candidates in the dataset.

**T2 Hub** — Score ≥ 450. The mid-tier designation. A T2 Hub cluster has confirmed Primary-Secondary co-occurrence and score contributions from additional factors — Tertiary proximity, high Primary Target sales per square foot, or Secondary multiplicity — sufficient to clear 450 points. T2 Hub clusters are qualified candidates requiring further site availability assessment.

**T1 Valid** — Score ≥ 150. The entry-level designation. A T1 Valid cluster has Primary Target presence with partial co-location confirmation. T1 Valid clusters may qualify if site availability and Tertiary proximity factors are confirmed in the Transaction Summary Report process.

## Radius Threshold Conventions

**1.0 km threshold** — Applied to Primary and Secondary Target co-occurrence. A 1.0 km radius at Regional Market spatial scales corresponds to the shared site infrastructure zone of a co-anchored power centre. Secondary Targets within 1.0 km of a Primary Target are treated as operating within the same commercial node rather than as independently located operators.

**3.0 km threshold** — A recalibrated radius applied when Fifth-Degree Clusters exceed 10% of all Primary Target entries in the dataset. When the top cluster tier contains more than 10% of all entries, the Tertiary proximity threshold tightens from 5.0 km to 3.0 km and the Primary-Secondary threshold tightens from 1.0 km to below 1.0 km. The recalibration preserves the discriminating power of the cluster hierarchy.

**5.0 km threshold** — Applied to Tertiary Target co-occurrence under the standard calibration. A 5.0 km radius captures the geographic catchment of an institutional employer (university or medical centre) that influences professional tenancy demand in the surrounding area without requiring co-location on the same commercial node.

## Dataset Output Metrics

**Primary Target** — In the Woodfine co-location dataset, a Walmart Supercentre operating in a given geography. Each Primary Target entry is associated with a city or municipality name, population figure, sales per square foot, and a global ranking position relative to all other Primary Target entries in the dataset.

**Sales per Square Foot** — The retail productivity metric used to rank Primary Targets within the dataset. Sales per square foot reflects consumer purchasing intensity within the trade area and serves as the primary sorting criterion for identifying the highest-priority Development Site candidates and for generating the Optimum Mosaic demographic analysis.

**Global Position** — The rank of a Primary Target by sales per square foot relative to all Primary Target entries across all three datasets (Canada, United States, Mexico). A Primary Target in the top decile of global position is both a high-performing local node and a high-performing site relative to the full North American dataset.

**Scored Cluster** — A geo-located node that has met the Primary Target criteria and has been assigned a cluster degree and tier score based on the co-occurrence of Secondary and Tertiary Targets at the applicable radius thresholds. The term appears in GIS coverage reports to describe the total count of evaluated nodes in a given geography.
