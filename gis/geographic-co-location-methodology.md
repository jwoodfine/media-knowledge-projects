---
schema: foundry-doc-v1
title: "Geographic Co-Location Methodology"
slug: geographic-co-location-methodology
category: gis
type: topic
content_type: topic
quality: complete
short_description: "The five-degree cluster system Woodfine uses to score retail node proximity — combining Primary (Walmart Supercentre), Secondary (Home Depot, Costco), and Tertiary (universities, medical centres) target co-occurrence at defined radius thresholds — to rank potential development sites by validated anchor strength."
status: stable
bcsc_class: current-fact
last_edited: 2026-07-01
editor: pointsav-engineering
language_protocol: PROSE-TOPIC
source_refs:
  - "bfe6fb6bbb557fd15bdb7ffd53bce60e527911eb7658c906df5b69813bdb8747"
paired_with: geographic-co-location-methodology.es.md
cites: []
---

The **Geographic Co-Location Methodology** is the spatial analysis discipline Woodfine Management Corp. applies to identify and rank potential Development Sites across its three primary jurisdictions. The methodology scores retail nodes by the proximity and combination of anchor retailers operating in the geography, producing a ranked dataset of sites in which development investment is validated by the demonstrable commercial commitments of institutional retailers rather than by speculative demographic projections.

The methodology produces five cluster degrees, each representing a more refined level of anchor co-occurrence. Higher-degree clusters indicate that a geography has attracted multiple categories of institutional commercial investment — a compound validation of market conditions that exceeds the threshold any single anchor produces alone.

## The Five-Degree Cluster System

The five cluster degrees are constructed from two radius thresholds: a 1.0 km threshold applied to Primary and Secondary Target co-occurrence, and a 5.0 km threshold applied to Tertiary Target proximity. Each degree builds on the prior.

**First-Degree Cluster** — A Primary Target site (Walmart Supercentre) with either of the two Secondary Targets (Home Depot or Costco Wholesale) located within 1.0 km of each other. This is the baseline Qualified Investment indicator: the co-presence of a volume grocery operator and a major home improvement or membership warehouse operator within 1.0 km confirms that the geography meets the site thresholds of two institutionally distinct retail operators.

**Second-Degree Cluster** — A First-Degree Cluster with either Tertiary Target (a post-secondary institution or a major medical centre) located within 5.0 km. The addition of a Tertiary Target introduces a demand source for professional services tenancy that is structurally independent of the retail node — a university or hospital draws professional staff, patient populations, and academic visitors who represent the primary target tenant base for Woodfine Professional Centres.

**Third-Degree Cluster** — A Primary Target with both Secondary Targets (Home Depot and Costco) within 1.0 km of each other. The requirement that both secondary operators be present at the 1.0 km radius is a materially higher bar than the First-Degree standard. Home Depot and Costco independently validate a geography through their own site selection processes; their simultaneous presence confirms that multiple institutional operators have evaluated the same geography against their independent criteria and reached the same conclusion.

**Fourth-Degree Cluster** — A Third-Degree Cluster with either Tertiary Target within 5.0 km. The combination of both secondary operators plus an institutional tertiary demand source represents a geography in which retail, professional, and institutional activities have converged.

**Fifth-Degree Cluster** — A Third-Degree Cluster with both Tertiary Targets within 5.0 km. Fifth-Degree Clusters are the highest-conviction sites in the dataset. The simultaneous presence of Walmart, Home Depot, Costco, a post-secondary institution, and a major medical centre within the respective radius thresholds marks a geography that has independently attracted five categories of institutional commercial commitment.

## Radius Calibration

The 1.0 km threshold for Primary-Secondary co-occurrence reflects the operational reality of power centre site design: retailers in the same commercial node or corridor are typically within this distance of each other, and proximity at this radius confirms shared site infrastructure rather than coincidental geographical proximity. The 5.0 km threshold for Tertiary co-occurrence reflects the wider catchment pattern of institutional employers. A university or major hospital does not anchor a power centre — it anchors a geography. Five kilometres is a drive time of approximately five to eight minutes in a Regional Market context, within the commute tolerance of professional services tenants.

If Fifth-Degree Clusters account for more than 10% of all Primary Target entries in the full dataset, the thresholds are recalibrated: the Tertiary proximity threshold tightens from 5.0 km to 3.0 km, and the Primary-Secondary threshold tightens from 1.0 km to below 1.0 km. This recalibration mechanism prevents the top cluster tier from becoming too large to be operationally useful as a site selection filter.

## Dataset Output Metrics

For each Primary Target entry, the geographic co-location output records: the city, town, or municipality of the Primary Target; the population of the surrounding community; the sales per square foot of the Primary Target; and the global ranking of that Primary Target by sales per square foot across all Primary Target entries in the dataset. No additional demographic categories are included in the geographic co-location output — demographic profiling is a separate analytical step addressed by the Optimum Mosaic methodology.

The output is then ranked to balance cluster degree, Primary-Secondary co-occurrence, and the absolute sales per square foot of the Primary Target. The ranking produces the site shortlist from which Woodfine engages real estate professionals in each identified market to assess land availability and development timeline.

## Required Site Count by Jurisdiction

The site shortlist requirements are calibrated to the planned capital raises and construction timelines of each Direct-Hold Solution. For Canada, the required development potential is 26 sites across equity and three debt financings over years one through eight and beyond. For the United States, the requirement is 52 sites over the same period. For Mexico, 26 sites.

Because not every high-ranked Primary Target will have available land adjacent to its site, and some available sites will carry rezoning or permitting timelines extending three to seven years, the site shortlist must exceed the required development count by at least a factor of two. A dataset that identifies 26 Required sites for Canada must therefore produce at least 52 shortlisted candidates — one required site for every two shortlisted.

Three separate datasets are maintained, one per jurisdiction, reflecting the distinct retail landscapes of Canada, the United States, and Mexico.
