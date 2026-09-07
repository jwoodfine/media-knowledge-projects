---
schema: foundry-doc-v1
slug: atlas-top-400-north-america
title: "Top 400 Regional Markets — North America"
language: en
language_protocol: PROSE-TOPIC
category: markets
type: reference
index_group: the-top-400-markets
content_type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
short_description: "The 400 North American Regional Markets published from a 1,121-market qualifying pool — 298 United States, 56 Canadian, 46 Mexican. No rank or score is published."
paired_with: markets/atlas-top-400-north-america.es.md
last_edited: 2026-09-06
editor: editorial
---

Four hundred North American markets clear the co-location composition gates and are published in
this set. They are drawn from a qualifying pool of 1,121 across three countries: 298 in the United
States, 56 in Canada, and 46 in Mexico. A *Regional Market* is a named settlement whose retail
co-location clusters together satisfy an anchor-composition test. Markets enter this set by that
test, not by a published rank or score.

The set identifies commercial markets outside the metropolitan cores that institutional
metro-market research already covers, and outside genuinely rural areas. It is produced separately
from lists of metro cores and standalone secondary cities. The two continents are scored and
selected as two series, not one combined list.

## Country breakouts

All three countries have a dedicated country page as of 2026-09-06:
[[atlas-united-states|United States]], [[atlas-canada|Canada]], and [[atlas-mexico|Mexico]]. Each
lists that country's own entries with the metropolitan reference point and cluster composition for
every market. The Mexico page was added on 2026-09-06, closing the last gap in country coverage for
this set. The separate [[atlas-co-location-index-mexico|Mexico co-location index]] covers the
underlying anchor network but is not a filtered view of this set.

This page carries the continental summary. It does not repeat the four hundred individual entries,
which are read a country at a time on the pages above.

## Definition and Scope

A North American Regional Market qualifies when it meets the composition test set out below,
applied to the union of all co-location clusters within a single named settlement. The settlement
must be a named, legally incorporated place or equivalent administrative unit whose name differs
from that of its metropolitan reference point.

The geographic coherence constraint requires that all co-location clusters within a single named
settlement lie within a 200-kilometre bounding box. Settlements failing this constraint are
name-collision aggregations and are excluded.

The metropolitan reference point recorded for each market is the nearest major metropolitan centre
in the framework's continental reference set. The distance is a straight-line measurement, not a
drive-time or commuting estimate. It is not a claim that the market functions as a commuter suburb
of that centre, and it is not a qualification threshold — distance is recorded, not gated.

## Qualification Method

No rank or score is published for any market in this set. A market qualifies under one of three
composition gates. A **Regional Market** carries a hypermarket anchor plus at least two of
{hardware, price club, lifestyle, electronics, sport}, unioned across the market's member clusters.
A **District Anchor** carries a hypermarket and hardware anchor with no other optional category,
across at least two distinct clusters. A **Standalone Regional Centre** meets that same condition in
a market isolated from any other qualifying market beyond the outer geographic band.

Of the four hundred North American entries, 382 qualify as Regional Markets and 18 as Standalone
Regional Centres — nine in Mexico, five in Canada, and four in the United States. No North American
entry qualifies as a District Anchor. The standalone class is where the set reaches genuinely
isolated regional centres rather than settlements in a metropolitan orbit.

Selection from the qualifying pool takes the highest-scoring 400 per continent, with no per-country
budget. A small per-country minimum floor prevents a country with real qualifying markets from being
excluded outright, but does not otherwise affect ordering. A composite score supports that selection
internally and is never surfaced to a reader. The published order is alphabetical, not ordinal. The
per-country counts below are therefore an observed result of the cutoff, not a quota.

Catchment population and consumer-spend figures accompany each market as descriptive context. They
take no part in selection. Population is negatively correlated with the composition score in every
country tested, so selecting on population would systematically replace genuine regional markets
with dense metro-fringe suburbs.

The three cluster tiers referenced below describe progressively richer combinations of retail anchor
categories. *Tier 1* (T1) clusters contain a hypermarket — Walmart Supercenter, Target, Meijer, or
H-E-B among them — a home-improvement warehouse such as Home Depot or Lowe's, and a warehouse club
such as Costco, Sam's Club, or BJ's. *Tier 2* (T2) clusters contain a hypermarket and a hardware
anchor without a warehouse club. *Tier 3* (T3) clusters contain a single recognised anchor category.

## Cluster Composition

The four hundred North American markets carry 708 co-location clusters between them — 479 Tier 1,
75 Tier 2, and 154 Tier 3 — an average of 1.77 clusters per market. Tier 1 presence is near
universal: 397 of the four hundred markets carry at least one Tier 1 cluster, and only two carry
Tier 3 clusters alone.

Mexico is the exception to that pattern in composition rather than in qualification. Its 46 markets
carry 54 Tier 1 clusters but 58 Tier 3 clusters — the only country in either continental set where
Tier 3 clusters outnumber Tier 1.

## Geography

The set spans 110 distinct metropolitan reference points. Vancouver is the reference point for 13
entries and Toronto for 12 — the two largest, both Canadian, in a set that is three-quarters United
States markets. Baltimore carries 10, and Boston, Minneapolis, Montreal, Mexico City, and Nashville
between eight and nine each.

Recorded reference distances run from 12 to 694 kilometres, with a median of 81. Just under half the
set — 198 of 400 markets — sits within 80 kilometres of its reference point, and 109 sits beyond
150. Mexico accounts for much of the long tail, with a median reference distance of 152 kilometres
against 75 for the United States and 90 for Canada.

## Country Breakdown

Counts are the published result of the continental cutoff. The qualifying-pool column shows how many
markets in each country cleared a composition gate before the 400-market cap was applied.

| Country | Markets | Qualifying pool | T1 | T2 | T3 | Median reference distance |
|---|---|---|---|---|---|---|
| [[atlas-united-states|United States]] | 298 | 916 | 348 | 59 | 79 | 75 km |
| [[atlas-canada|Canada]] | 56 | 112 | 77 | 13 | 17 | 90 km |
| [[atlas-mexico|Mexico]] | 46 | 93 | 54 | 3 | 58 | 152 km |
| **Total** | **400** | **1,121** | **479** | **75** | **154** | — |

The United States publishes 298 of 916 qualifying markets — under a third of its pool, the deepest
reserve in either continental set. Canada and Mexico publish roughly half of theirs.

## Catchment Data Coverage

Catchment population and consumer-spend figures are recorded for all four hundred North American
markets. There are no country-level gaps on this continent, in contrast to the European set. Of the
four hundred, 192 figures are computed as a deduplicated union of catchment cells across a market's
member clusters, and 208 fall back to the strongest member cluster's own figures. Each record
discloses which method applied.

## Data Sources and Methodology

Co-location data is drawn from OpenStreetMap (ODbL licence) filtered by Wikidata chain identifiers,
supplemented by civic-anchor records from the Overture Maps Foundation Places dataset (CDLA
Permissive 2.0). Cluster boundaries are computed in two passes over the anchor locations.

The published set is a curated editorial selection derived from the live Regional Markets layer. It
does not replace or alter that layer, which remains unranked and uncurated at its full qualifying
count.

For full methodology, see [[about-regional-markets-system|Regional Markets Intelligence System]].
The European equivalent list is at [[atlas-top-400-europe|Top 400 Regional Markets — Europe]].

---

*Reference data from the 2026-08-07 dataset build (298 United States, 56 Canadian, and 46
Mexican markets; a September 2026 rebuild superseded an earlier, incomplete selection of 369,
23, and 8 respectively). Sources: OpenStreetMap contributors (ODbL); Overture Maps Foundation
(CDLA Permissive 2.0).*

## See Also

- [[about-regional-markets-system|Regional Markets Intelligence System]]
- [[co-location-methodology|Co-location Methodology]]
- [[co-location-tier-system|Co-location Tier System]]
