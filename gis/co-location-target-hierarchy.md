---
schema: foundry-doc-v1
title: "Co-Location Target Hierarchy"
slug: co-location-target-hierarchy
category: gis
type: topic
content_type: topic
quality: complete
short_description: "The three-tier target classification Woodfine uses in its geographic co-location dataset — Primary (Walmart Supercentre), Secondary (Home Depot, Costco), Tertiary (universities, medical centres) — defining which retailers and institutions qualify at each tier and why each tier's presence validates a potential Development Site."
status: stable
bcsc_class: current-fact
last_edited: 2026-07-01
editor: pointsav-engineering
language_protocol: PROSE-TOPIC
source_refs:
  - "bfe6fb6bbb557fd15bdb7ffd53bce60e527911eb7658c906df5b69813bdb8747"
paired_with: co-location-target-hierarchy.es.md
cites: []
---

The **Co-Location Target Hierarchy** is the three-tier classification system that structures Woodfine Management Corp.'s geographic co-location dataset. Each tier assigns a category of retail operator or institutional employer to the role it plays in validating a potential Development Site. The hierarchy reflects the observed sequencing of commercial development in Regional Markets: Primary Targets anchor the retail node, Secondary Targets follow the Primary, and Tertiary Targets confirm that an institutional demand base for professional services tenancy is present in the geography.

## Primary Target: Walmart Supercentre

The Primary Target in the Woodfine dataset is the Walmart Supercentre format. A Walmart Supercentre is a large-format combined grocery and general merchandise store. It is not simply the largest format in the Walmart chain — it is the format that Walmart deploys in markets where it has validated sufficient consumer demand to justify a combined grocery and general merchandise investment at full institutional scale.

The Walmart Supercentre serves as the Primary Target because of its role in establishing commercial infrastructure for a Regional Market. When Walmart commits to building a Supercentre in a geography, it simultaneously installs the road access improvements, utility connections, and site preparation that other commercial operators need to follow. Home Depot and Costco, as a matter of observed site selection behavior, do not typically precede Walmart in a given market — they follow after Walmart has validated and prepared the commercial node.

The sales per square foot figure for each Walmart Supercentre in the dataset is the primary ranking metric for individual Primary Target entries. Sales per square foot is a direct proxy for consumer demand intensity: a Supercentre with high sales per square foot operates in a trade area where consumer purchasing volume is concentrated, confirming that the commercial node is performing above the threshold required to attract the Secondary Targets.

## Secondary Targets: Home Depot and Costco Wholesale

The two Secondary Targets are The Home Depot and Costco Wholesale. Both are large-format category-dominant retailers that validate specific segments of consumer and commercial demand.

**Home Depot** operates large-format home improvement stores targeting both residential consumers and trade contractors. Its presence in a Regional Market confirms that the geography supports a trade contractor base — electricians, plumbers, general contractors, and renovation specialists — that serves both residential and commercial construction activity. For Woodfine's development purposes, the presence of a Home Depot indicates a Regional Market with active construction supply chain activity, which correlates with commercial real estate development readiness.

**Costco Wholesale** operates membership warehouse stores targeting consumers with the purchasing capacity and household scale to justify annual membership fees. The Costco membership threshold acts as an implicit income and household-size screen: markets where Costco operates profitably are markets where consumer disposable income meets or exceeds the threshold for discretionary warehouse purchasing. For Woodfine, the presence of a Costco confirms the income profile of the surrounding trade area at a level consistent with the demographic characteristics of the target tenant base for Professional Centres.

Secondary Targets receive a 1.0 km co-occurrence threshold because their presence at this distance from the Primary Target indicates shared site infrastructure, not coincidental proximity. Home Depot and Costco in a distinct location 1.5 km away from a Walmart Supercentre may reflect independent commercial development rather than a co-anchored power centre. Within 1.0 km, the physical proximity confirms that the operators share a commercial node.

## Tertiary Targets: Universities and Medical Centres

The two Tertiary Target categories are post-secondary educational institutions (universities and colleges) and major medical centres. Both generate sustained, institutionally-anchored demand for professional services tenancy in the surrounding geography.

**Universities and colleges** are employers of administrative, research, clinical, and facilities staff who require professional services — legal, accounting, financial advisory, medical, and dental — in the vicinity of their daily work location. They also attract the graduate and professional student populations who enter the professional services economy in the surrounding Regional Market. A post-secondary institution within 5.0 km of a power centre node is a confirmed source of professional tenancy demand that is not dependent on the retail anchor's own commercial performance.

**Major medical centres** — large hospitals and integrated health complexes — are among the most stable institutional employers in any Regional Market. Medical centre campuses attract affiliated physician practices, specialist clinics, diagnostic imaging operators, and pharmaceutical retailers that require dedicated leaseholds. The density of healthcare-related professional tenancy associated with a major medical centre makes it a reliable predictor of demand for the Professional Centres building type.

The 5.0 km threshold for Tertiary co-occurrence reflects the fact that Tertiary Targets anchor a geography, not a single commercial node. A university or hospital draws a professional catchment from the wider Regional Market, not just from the power centre parcel. Five kilometres in a Regional Market driving environment corresponds to a short commute — within the practical tolerance of professional tenants who may work at the medical centre but seek dental, legal, or financial services within a few minutes of their workplace.

## Hierarchy Sequencing and Market Validation

The hierarchy is designed to capture the sequential validation logic that institutional commercial operators apply in Regional Markets. A geography that supports a Walmart Supercentre with high sales per square foot has already demonstrated consumer purchasing volume. A geography where Home Depot and Costco have followed Walmart has demonstrated that three independent institutional retailers found the same market conditions attractive under their respective site selection criteria. A geography where a university or medical centre is also present within 5.0 km has further demonstrated that the market supports institutional employment at a scale that generates professional services demand independent of the retail node.

Each tier adds an independent validation signal that is not correlated with the others. Walmart validates consumer volume. Home Depot and Costco validate purchasing capacity and trade activity. Universities and medical centres validate professional tenancy demand. The Five-Degree Cluster system aggregates these independent signals into a composite score.
