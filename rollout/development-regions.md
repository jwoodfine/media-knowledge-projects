---
schema: foundry-doc-v1
title: "Development regions"
slug: development-regions
category: rollout
index_group: development-regions-and-site-register
type: concept
content_type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: PROSE-TOPIC
last_edited: 2026-09-04
editor: pointsav-engineering
short_description: "Geographic and jurisdictional zones segmenting market data, regulatory context, and site-selection scope for co-location evaluation and compliance."
paired_with: development-regions.es.md
cites: []
---

Every co-location candidate is evaluated inside a declared development region — a bounded geographic and jurisdictional envelope that scopes market data, regulatory context, and site selection. Within each region's envelope, compliance postures are applied and market intelligence accumulates. Regions are not delivery territories; they are analytical and operational boundaries that shape how development decisions are made.

## Purpose

A programme operating across multiple jurisdictions cannot apply a single regulatory posture or a single set of market-data assumptions universally. A Canadian deployment operating under NI 51-102 continuous-disclosure obligations faces different requirements than a deployment operating under equivalent US or European regimes. A co-location opportunity that satisfies Canadian jurisdictional constraints may not satisfy requirements elsewhere, and vice versa.

Development regions encode this jurisdictional specificity at the planning level. When a site-selection process is initiated, it declares the target region. The co-location scoring, and the compliance-posture review, are all scoped to that region's envelope.

## Region composition

Each development region is defined by three components:

**Jurisdictional envelope.** The set of legal and regulatory frameworks that apply within the region. For Canadian regions, this includes the applicable provincial securities regulator, the NI 51-102 continuous-disclosure framework, and any relevant data-handling provisions. Data residency and disclosure practice are scoped to the declared framework list.

**Geographic boundary.** The physical geography within which co-location facilities and sites are considered. Geographic boundaries do not always align with jurisdictional ones — a Canadian regulatory envelope may encompass sites in multiple provinces, each with distinct market characteristics.

**Market data scope.** The data sources and market indices that feed the intelligence pipeline for the region. Real estate market data, economic indicators, and demographic signals are region-scoped because their informational content is jurisdictionally bounded. An index relevant to the British Columbia market is not structurally applicable to Alberta market decisions. The [[about-regional-markets-system|Regional Markets intelligence system]] — including the [[atlas-top-400-north-america|Top 400 Regional Markets]] lists — is the primary such index: a development region's market-data scope determines which Regional Markets are in play for site selection within it.

## Relationship to the co-location methodology

Development-region definitions are the framework within which site-selection scoring operates. When a site-selection process is initiated, it specifies a development region; scoring then searches within that region's geographic boundary, applies its jurisdictional rules, and returns a classified candidate list scoped to that region.

Development regions are stable definitions that change infrequently — when a new regulatory framework comes into effect, when coverage expands to a new geography, or when a jurisdictional boundary changes. Site-selection scoring is the runtime consumer of those definitions.

## Planned expansion

The development-regions model is intended to support expansion beyond Canada as the programme grows. New regions are added through a governed process: the jurisdictional envelope, geographic boundary, and market-data scope must each be declared before the region is used in any deployment decision. Regions under definition are indicated as planned until all three components are formally specified.

## See also

- [[rollout-index|Planned Development Program]] — the country-by-country rollout programme within which regional deployment decisions are made
- [[about-regional-markets-system|Regional Markets Intelligence System]] — the qualification methodology behind the market-data scope
- [[atlas-top-400-north-america|Top 400 Regional Markets — North America]]
- [[atlas-top-400-europe|Top 400 Regional Markets — Europe]]
