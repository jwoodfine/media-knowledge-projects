---
schema: foundry-doc-v1
title: "Co-location target hierarchy"
slug: co-location-target-hierarchy
category: site-selection
index_group: anchors-and-tenants
type: topic
content_type: topic
quality: complete
short_description: "The signals the co-location dataset looks for and the role each plays — a hypermarket anchor, category-dominant co-anchors, and civic institutions — and why the current tier system requires each one independently rather than summing them into a score."
status: stable
audience: customer-woodfine
bcsc_class: current-fact
last_edited: 2026-09-04
editor: pointsav-engineering
language_protocol: PROSE-TOPIC
source_refs:
  - "bfe6fb6bbb557fd15bdb7ffd53bce60e527911eb7658c906df5b69813bdb8747"
paired_with: co-location-target-hierarchy.es.md
cites: []
---

No single strong signal qualifies a development site. A hypermarket with exceptional sales does not make a site on its own; neither does a hospital, nor a warehouse club. The **co-location target hierarchy** names the distinct commercial and institutional signals Woodfine's co-location dataset looks for, and the role each one plays in validating a geography. Since May 2026 those signals are tested as separate conditions that must each pass. They are not summed into a single score in which a strong reading on one offsets a weak reading on another.

The hierarchy reflects the observed sequencing of commercial development in [[about-regional-markets-system|Regional Markets]]. A hypermarket anchor establishes the node. Category-dominant co-anchors follow it. Civic institutions confirm that an institutional employment base is present in the surrounding geography. Each stage supplies a different piece of evidence, and none of them substitutes for another.

## Target roles are not cluster tiers

Two vocabularies meet in this subject, and confusing them is the most common misreading.

**Target roles** — primary, secondary, tertiary — describe what the platform looks for and why it looks for it. **Cluster tiers** — Regional, District, Local, and Fringe — describe what a cluster was found to be once every condition has been tested. A cluster in which all three target roles are present can still fall to the lowest tier if its catchment reach is inadequate.

The tier labels and what they mean are set out in [[co-location-tier-nomenclature|tier nomenclature]]. The conditions a cluster must clear to earn each tier are set out in [[catchment-ranking-methodology|the catchment ranking methodology]]. This article covers the inputs to those conditions, not the conditions themselves.

## Primary target — the hypermarket anchor

The primary target is the large-format combined grocery and general merchandise store. It is not simply the largest format a chain operates. It is the format an operator deploys only where it has validated consumer demand sufficient to justify a combined grocery and general merchandise investment at full institutional scale.

### Infrastructure sequencing

The hypermarket serves as the primary target because of what it builds. When an operator commits to a hypermarket in a geography, it installs the road access improvements, utility connections, and site preparation that other commercial operators need in order to follow. Hardware and warehouse-club operators do not, as a matter of observed site-selection behaviour, typically precede the hypermarket into a market. They arrive after it has validated and prepared the commercial node.

In the dataset the primary target is also the seed record: a candidate cluster is identified from a hypermarket-class anchor and described outward from it. The four anchor classes the composition condition recognises — hypermarket, lifestyle, hardware, and warehouse — are defined in [[retail-brand-family-taxonomy|the retail brand family taxonomy]].

### Sales per square foot ranks; it does not qualify

Sales per square foot for each hypermarket entry is the primary ranking metric for individual primary-target records. It is a direct proxy for consumer demand intensity: a store with high sales per square foot operates in a trade area where purchasing volume is concentrated.

It carries no weight in whether a cluster clears a tier condition. It enters later, in the [[co-location-ranking-system|ranking step]] that orders already-qualified clusters into a site shortlist. Keeping the two apart matters. A top-ranked hypermarket in a geography that fails a catchment or civic condition still does not produce a qualified cluster.

## Secondary targets — the co-anchors

Secondary targets are the category-dominant operators that follow the hypermarket into a node. Each validates a different segment of consumer and commercial demand.

**Hardware** anchors — large-format home improvement retailers serving both residential consumers and trade contractors — confirm that a geography supports a trade contractor base. Electricians, plumbers, general contractors, and renovation specialists serve both residential and commercial construction. Their presence indicates a Regional Market with an active construction supply chain, which correlates with readiness for commercial real estate development.

**Warehouse** anchors — membership warehouse clubs — act as an implicit income and household-size screen. A membership fee is a threshold: markets where a club operates profitably are markets where consumer disposable income supports discretionary warehouse purchasing. Their presence confirms a trade-area income profile consistent with the tenant base Professional Centres are built for.

**Lifestyle** anchors — the large-format home and furnishings format — are recognised in the same co-anchor role, and appear in the composition condition for the highest tier alongside a hypermarket.

### Proximity means a shared node, not a shared market

A co-anchor counts toward composition only when it is close enough to the primary target to be sharing the same commercial node — the same access roads, the same servicing, the same parcel assembly. A hardware store several kilometres away may reflect independent commercial development rather than a co-anchored [[power-centres|power centre]]. Physical proximity is what distinguishes the two.

The distance conventions that draw that line are engineering parameters of the platform, re-tuned between rebuilds as anchor-chain coverage changes. They are not published here.

## Tertiary targets — civic institutions

Tertiary targets are institutional employers that generate sustained demand for professional services tenancy in the surrounding geography, independent of the retail node's own commercial performance.

**Major medical centres** — large hospitals and integrated health complexes — are among the most stable institutional employers in any Regional Market. A medical centre campus attracts affiliated physician practices, specialist clinics, diagnostic imaging operators, and pharmaceutical retailers, all of which require dedicated leaseholds. That density of healthcare-related professional tenancy makes a medical centre a reliable predictor of demand for the Professional Centres building type.

Hospitals are classified by role — major general hospitals with emergency departments, secondary hospitals and specialist centres, and general practice or walk-in clinics. The civic condition tightens moving up the tiers: the highest tier requires a regionally classified hospital, and clinic-grade facilities do not satisfy the conditions for the upper tiers.

**Universities and colleges** employ administrative, research, clinical, and facilities staff who require legal, accounting, financial advisory, medical, and dental services near their daily work location. They also produce the graduate and professional populations who enter the professional services economy of the surrounding market. University and college locations are captured in the same civic layer as hospitals and inform the demand case for professional tenancy. In the current tier definitions they do not, on their own, satisfy a civic condition — the civic gates test hospital classification.

### The civic ring is wider than the node

A civic institution anchors a geography rather than a parcel. A hospital draws its professional catchment from the wider Regional Market, not from the power centre site. The civic condition is therefore tested over a wider ring than the composition condition, on the reasoning that a professional tenant may work at the medical centre and still seek dental, legal, or financial services within a short drive of it. That ring is a platform parameter and is not published here.

## Why these are conditions, not a score

Each role supplies evidence the others cannot. A hypermarket validates consumer volume. Hardware and warehouse co-anchors validate trade activity and household purchasing capacity. A regionally classified hospital validates institutional employment that does not depend on retail performance at all.

Because the signals are independent, they are not interchangeable — and a system that adds them together implicitly treats them as though they were. That is the reasoning behind the change made in May 2026. Until then the platform assigned tiers on a points-based scale that summed composition, count, diversity, civic depth, and an overlap penalty into a single number. A cluster could reach a high tier on a strong reading of one term while lacking the catchment reach or civic infrastructure that tier was meant to signal.

Under the current system each condition is tested on its own, and a cluster earns a tier only when every condition for that tier passes. Partial strength does not accumulate. The retired scale and its numeric labels no longer describe any current cluster.

## What the hierarchy does not determine

The target hierarchy is one input among several. Two further conditions sit outside it entirely: a cluster's catchment rank against other clusters in its own country, derived from the zones described in [[od-catchment-methodology|the distance-band methodology]], and its spatial independence from stronger nearby clusters.

It is also not a demographic profile. The co-location output records the community, its population, and the primary target's sales performance and ranking. Demographic profiling is a separate analytical step, addressed by the [[optimum-mosaic-demographic-profiling|Optimum Mosaic methodology]].

## See also

- [[geographic-co-location-methodology]]
- [[catchment-ranking-methodology]]
- [[co-location-anchors]]
