---
schema: foundry-doc-v1
title: "Regional market definition"
slug: regional-market-definition
short_description: "Spatial containers on the location intelligence map — how settlements with co-location presence differ from Regional Markets, and why coverage is not market strength."
category: markets
index_group: coverage-methodology
type: concept
content_type: topic
quality: complete
status: stable
audience: customer-woodfine
bcsc_class: public-disclosure-safe
language: en
language_protocol: PROSE-TOPIC
last_edited: 2026-08-26
editor: pointsav-engineering
paired_with: markets/regional-market-definition.es.md
cites: []
---

The Woodfine location intelligence map organises co-location clusters into two spatial containers. The **settlement with co-location presence** is a coverage statistic; the **Regional Market** is a tighter object reserved for settlements with meaningful concentrations of co-located retail. A third, coarser container — the **Metro Market** — provides context at the major-metropolitan level. This article defines each object, states the rule that produces it, and distinguishes between what each count measures and what it does not.

## The two objects currently called Regional Markets

The pipeline resolves each co-location cluster to an incorporated municipal or CSD polygon via a point-in-polygon assignment against TIGER 2023 places for the US, GISCO LAU 2021 plus GADM GBR for the EU and UK, with rural co-locations resolving to their containing municipality. A settlement becomes a Regional Market object the moment **one** co-location falls inside its polygon.

Under this permissive rule, the count of Regional Market objects approximates the count of distinct settlements that contain any co-location at all. At the 2026-05-22 build, the pipeline produced approximately **3,011 settlements** (North America and EU/UK) with co-location presence. Of those, **2,986** were published in the live dataset and **2,942** carried the high-confidence geocoding flag.

Coverage has grown substantially since that build. As of the most recent full processing run (2026-08-06), the live dataset carries **12,689** Regional Market objects across **24 countries**. Of those, **12,578** — about 99% — carry the high-confidence flag. The permissive rule itself is unchanged; the growth reflects dataset expansion, not a floor change.

That is a coverage statistic. It records how widely the tracked anchor chains are observed. It does not identify where retail demand actually concentrates. A floor of one co-location admits every town with a single qualifying co-location on exactly the same terms as a metropolitan area with dozens.

## The distinction: coverage versus market

Two failure modes follow from conflating coverage with market:

**Single-anchor settlements dominate the population.** A town with one qualifying co-location is, under the current rule, the same object class as a metro holding many. The label "Regional Market" implies concentrated retail demand; the rule admits the single-anchor case. The headline count is therefore inflated by exactly the cases that carry the least decision value for site selection or investment.

**The count reads as an artefact of the floor, not the geography.** A reviewer can move the count up or down simply by arguing the floor, which is the classic sign that the threshold — not the data — is doing the work. This is the same failure class as the clustering parameter sensitivity documented in [[catchment-ranking-methodology|the catchment ranking methodology]], where parameter sweeps move the North American cluster count across a wide range without any change to the underlying retailer data.

The geocoding-confidence field does not resolve this. It is geocoding precision — specifically the quality of the boundary assignment — not market quality. It must not be presented as a ranking or a quality signal.

## Composition floors: anchor composition, not count

**A count-based floor — a minimum *number* of co-locations within a polygon — is not the right fix.** A settlement can clear a count floor of one and still be a genuinely strong market, if its single co-location cluster is itself a convergence of multiple independent anchor categories — a hypermarket, a hardware retailer, and a warehouse club within one tight cluster is already a T1 by the tier system's own definition (see [[about-regional-markets-system|Regional Markets Intelligence System]]), and a T1 is exactly the concentrated-demand signal the term "market" is supposed to carry. Conversely, a settlement that clears a count floor of two by holding two separate, single-anchor (T3) clusters is not obviously stronger than the single-T1 case a count floor would exclude. Counting *how many* co-location events a settlement has and counting *how strong* each one is are different questions, and only the second one is what "Regional Market" should mean. Composition — the anchor-category mix *within* a cluster — is already captured correctly by the T1/T2/T3 tier classification; a floor built on cluster count instead of cluster tier repeats the exact coverage-versus-market conflation described above.

The object split below still holds. A permissive coverage catalog is a legitimate, honestly-labelled thing to publish, separate from a claim about market strength. But the tighter object's floor should be tier-based (e.g., "contains at least one T1 cluster"), not count-based.

### Settlement with co-location presence

- **Definition.** Any incorporated municipal or CSD polygon that contains at least one co-location.
- **Count.** 12,689 as of the most recent full processing run (2026-08-06; NA plus EU/UK). Stated as a coverage statistic with the honest gloss: *"12,689 settlements across 24 countries contain at least one observed co-location, as of the most recent full processing run."*
- **Role.** Coverage map, footprint claim, and the base set from which the tighter object is drawn. Not the headline market count.

### Regional Market

A settlement is promoted to Regional Market when its co-location clusters clear a stated **tier-based** floor, not a count floor. For example: "contains at least one T1 cluster." This ties the term to cluster *strength* rather than cluster *count*. It correctly admits the single-strong-cluster case and correctly excludes the many-weak-clusters case that a count floor would get backwards.

An alternative, and analytically stronger, floor is a **demand threshold**. Under this approach a Regional Market clears a stated catchment population or estimated annual spend threshold, tying the term to demand rather than supply density. This depends on the catchment and spend surfaces being trustworthy first (see [[trade-area-methodology|the trade-area methodology]] and [[spend-population-provenance|the spend and population provenance]] write-ups). Adoption is appropriate once those surfaces carry their uncertainty framing.

Whichever floor is chosen, **the resulting Regional Market count must be re-derived and published alongside the floor and the rule that produced it**. The count is not meaningful without both printed next to it.

If no floor is adopted, the minimum acceptable change is renaming. That means dropping "Regional Market" for the permissive object and calling it "settlements with co-location presence" on the map face, in the platform's documentation, and in this TOPIC. The term "market" carries an implied claim of concentrated demand that the one-co-location rule does not support on its own. Per the correction above, though, a single co-location *can* support that claim if its tier is high enough.

## The Top-400 co-locations — a qualifying set, not a ranking

The Top-400 is a list of co-locations, not Regional Markets, produced per region. North America is one region; Europe (UK, Nordics, Continental) is another; the list is cut at 400 per region. Each row carries a Regional Market column for context. It is the spine of the platform's detail view, presented in a fixed order that is not an asserted rank.

**No rank or score is published against any co-location in the Top-400.** Entry is decided by anchor composition, not by a numeric score: a co-location qualifies when it clears one of three composition gates — a hypermarket anchor with at least two of {hardware, price club, lifestyle, electronics, sport}; a hypermarket-plus-hardware anchor pair across at least two distinct clusters; or that same hypermarket-plus-hardware condition applied to a geographically isolated co-location. A composite score exists internally to support selection but is never surfaced to a reader. See [[about-regional-markets-system|Regional Markets Intelligence System]] for the full qualification method.

## Metro Market

The Metro Market is a coarser, contextual container: a major metropolitan area on a published reference list (US MSA/CBSA, Canadian CMA). A Regional Market nests inside at most one Metro Market and is never dissolved into it. Metro Market is context only — it is never the co-location or ring zoom level and never a breadcrumb level. Raising the Regional Market floor does not affect the Metro Market layer.

## What does not change

The boundary resolution rule is not altered by any floor change: Sherwood Park resolves to its containing polygon (Strathcona County) under the uniform "one rule, no exceptions" boundary policy confirmed 2026-05-22. A prior settlement-specific geocoding override for that settlement was removed and is not reinstated.

One wiki TOPIC per Regional Market remains the article unit, with a section per co-location inside it. Raising the Regional Market floor reduces the number of stub TOPICs, since single-anchor settlements no longer generate a thin market article. That is a content-quality improvement.

## Counts stated honestly

Every count below is reported with the rule that produced it. Figures are as of the most recent build referenced in the artifact registry and must be re-derived whenever the floor or the boundary set changes.

| Object | Rule | Count | What it measures |
|---|---|---|---|
| Settlements with co-location presence | ≥1 co-location in polygon | ~3,011 (NA + EU/UK, 2026-05-22 build) | Coverage and footprint |
| Regional Markets (tier-based floor, corrected recommendation) | ≥1 T1 cluster | To be re-derived on adoption | Concentrated co-location, correctly admitting single-strong-cluster markets |
| Published RM objects (gateway, 2026-05-30 build) | Permissive rule (≥1 co-location), unchanged | 4,436 (2026-05-30 build, 18 countries — see [[about-regional-markets-system|Regional Markets Intelligence System]]) | Coverage; grown by dataset expansion, not by a floor change |
| Published RM objects (gateway, most recent full processing run) | Permissive rule (≥1 co-location), unchanged | 12,689 (2026-08-06 build, 24 countries) | Coverage; grown by dataset expansion, not by a floor change |
| Top-400 co-locations (per region) | Composition gates (internal score, not published) | 400 NA + 400 EU | Qualifying candidate sites, not a ranked list; adopted per the recommendation above |

Two honesty notes belong in the platform's documentation alongside this table:

- The Regional Market count under a tier-based floor will differ from the raw settlement count in both directions — it drops many weak, low-tier settlements but keeps every single-cluster T1 settlement a naive count floor would have excluded. Neither direction is a regression; a tier-based count is simply a different, more defensible measurement than either the raw coverage count or a count-based floor.
- The geocoding-confidence field is geocoding precision, not market quality, and is not a ranking variable.

## See also

- [[about-regional-markets-system|Regional Markets Intelligence System]] — the full dataset, tier system, and qualification method this article's definitions build on
- [[catchment-ranking-methodology]] — how tiers and the planned strength score are computed for each co-location inside a Regional Market
- [[trade-area-methodology]] — how the trade area for each co-location is defined
- [[spend-population-provenance]] — the estimation chain for population and spend figures attributed to each co-location
