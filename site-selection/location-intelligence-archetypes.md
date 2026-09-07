---
schema: foundry-doc-v1
title: "Location intelligence co-location archetypes"
slug: location-intelligence-archetypes
category: site-selection
index_group: strategy-and-investment-thesis
type: topic
content_type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: PROSE-TOPIC
last_edited: 2026-09-04
editor: pointsav-engineering
short_description: "Three co-location archetypes — Retail Centres, Urban Fringe, and Commuter — identifying distinct commercial clustering patterns across 18 countries in North America and Europe."
paired_with: site-selection/location-intelligence-archetypes.es.md
---

The Location Intelligence platform identifies retail and commercial gravity
through three co-location archetypes: Retail Centres, Urban Fringe, and
Commuter. Each archetype describes a distinct clustering pattern that
reflects a different type of commercial activity and a different
relationship to the surrounding urban geography.

## The three archetypes

| Name | Anchor type | Status |
|------|-------------|--------|
| Retail Centres | Predicate-gate composition test — grocery hypermarket plus hardware/warehouse/lifestyle anchor combinations | Live — Regional/District/Local/Fringe tier pipeline |
| Urban Fringe | Hardware + trade-supply ecosystem (MRO, tool rental, builders merchant, auto parts) | Live — production co-location pipeline across three tiers |
| Commuter | Regional transit anchor (airport, rail, bus) + park-and-ride + car rental/hotel enrichment | Live — production co-location pipeline across three tiers |

Retail Centres is the base map product — the foundation of the
site-selection dataset. Urban Fringe and Commuter are overlay archetypes
that identify adjacent market structures not captured by grocery-anchored
clustering.

---

## Retail Centres

Retail Centres clusters represent grocery-anchored commercial co-locations,
assigned to one of four tiers by a predicate-gate test — each tier requires
every listed condition to pass, not an additive score against a threshold.
The gate definitions are set out in full in the
[[catchment-ranking-methodology|catchment ranking methodology]], which is
the canonical statement of the tier logic; what follows summarises what
distinguishes each tier.

### Tier definitions

**Tier 1 — Regional:** A Hypermarket anchor paired with a Warehouse or
Lifestyle anchor; catchment population among the highest in its country in
both the primary and secondary zones; a hospital serving a regional catchment
within the civic ring; and no substantial trade-area overlap with a stronger
cluster.

**Tier 2 — District:** A Hypermarket anchor plus a Hardware or Warehouse
anchor; strong but sub-Regional catchment population, matched by comparable
reach on at least one spend category; a hospital serving at least a
district-level catchment within the civic ring.

**Tier 3 — Local:** A Hardware or Warehouse anchor; catchment population at
or above the country median; a hospital of any kind within the civic ring.

**Tier 4 — Fringe:** All clusters that do not pass the Tier 1, 2, or 3 gates.

The anchor classes — Hypermarket (large-format grocery), Lifestyle, Hardware,
and Warehouse — are defined in the
[[retail-brand-family-taxonomy|retail brand-family taxonomy]].
Neighbourhood-format grocery chains are deliberately excluded: their density
would generate false-positive clusters rather than genuine anchor
convergence.

### Dataset shape and coverage

The production dataset is heavily weighted toward the lower tiers. Fringe
clusters outnumber the three qualifying tiers combined, each successive tier
down is materially larger than the one above it, and Regional clusters are a
small fraction of the total. Coverage spans seven headline countries — the
United States, Mexico, Spain, Germany, Canada, France, and Great Britain —
plus additional markets not yet broken out individually. Tier boundaries are
periodically re-tuned as anchor-chain coverage and the underlying retail
footprint change.

---

## Urban Fringe

Urban Fringe clusters identify concentrations of hardware and
industrial-supply retailers in the absence of grocery anchors. These sites
occupy the urban fringe — a band of distance beyond the immediate metro core
but short of standalone-market territory — and tend to cluster around
highway interchanges in areas with adjacent industrial landuse.

### Definition

An Urban Fringe candidate is a location where one or more hardware retailers
are present, no grocery hypermarket is within the cluster span, and the site
sits within the Urban Fringe metro-distance band. The typical built form is a
multi-storey warehouse or light-manufacturing building, distinct from the
one-storey big-box format of the retail park.

Urban Fringe locations serve trades contractors, light-manufacturing
operators, and just-in-time logistics tenants — not general retail
consumers.

### Co-location signals

**Essential:**

| Signal | Rationale |
|--------|-----------|
| Highway interchange nearby | Truck ingress and egress |
| Sufficient population within a short drive | Manufacturing and logistics labour |
| Industrial landuse adjacent | Zoning compatibility |

**Significant:**

| Signal | Rationale |
|--------|-----------|
| Air cargo airport within reach | Electronics and components, rapid replenishment |
| Freight rail nearby | Just-in-time component delivery |
| Transit corridor nearby | Workforce access |

**Disqualifying:** Dense residential immediately adjacent; flood plain;
heritage conservation zone; location inside a Retail Centres cluster.

### Production status

Urban Fringe classification is production-grade. Hardware retailers serve as
the profiled proxy anchor, and the trade-supply clustering was validated
before the classification was promoted to production.

The dataset spans thousands of clusters across the 18 display countries,
concentrated most heavily in the United States with meaningful coverage
across several other North American and European markets.

Clusters are distributed across the three tiers in the expected shape: a
small minority reach the Full Trade Hub tier, a larger share reach the
Established tier, and the majority sit in the Emerging/Thin tier. That
lower-tier-heavy distribution is expected — a full trade hub combining MRO,
tool rental, builders merchant, and auto parts is a legitimately rare
combination.

Some Urban Fringe clusters sit close enough to a grocery hypermarket to
function as dual-use commercial parks — valid Urban Fringe co-locations
that also include grocery retail.

---

## Commuter

Commuter clusters identify commercial concentrations near regional airports
and intercity train stations that sit in a Commuter belt beyond the
immediate metro core but short of standalone-market distance. The defining
demand pattern is park-and-fly or park-and-train travel: residents of a
Regional Market drive to a transit node, park, and travel to the Metro
Market.

### Definition

A Commuter candidate is a regional transit node — airport or intercity train
station — within the Commuter metro-distance band. Nodes closer than that
band are classified as suburban rather than regional; nodes beyond it are
considered standalone markets with a separate metro relationship.

The defining commercial signal at a Commuter location is car rental. Auto
parts, fuel stations, quick-service restaurants, and convenience stores are
secondary signals.

### Co-location signals

**Essential:**

| Signal | Rationale |
|--------|-----------|
| Regional transit anchor nearby | Airport or intercity station with direct metro service |
| Metro isolation within the Commuter band | Defines the regional relationship |
| Regional or District Retail Centres cluster nearby | Same population generates parking demand |
| Sufficient regional population | Minimum demand for multi-storey parking |

**Significant:**

| Signal | Rationale |
|--------|-----------|
| Car rental nearby | Arriving travellers require transport |
| Hotel cluster nearby | Business travel and multi-day parking |
| Second transit mode nearby | Multi-modal integration |

**Disqualifying:** Major hub within the immediate metro core; population
below a minimum viable threshold; no direct metro service.

### Production status

Commuter classification is production-grade. Park-and-ride records serve as the
primary geographic anchor — actual car-to-transit transition points
distributed independently of rail network geometry. Transit modes are
enrichment signals; car rental and hotel presence define commercial
maturity. Related transit-mode categories are grouped together before
tiering, to prevent related modes from inflating an apparent multi-modal
signal.

Clusters are distributed across three tiers. A Regional Hub tier combines
multi-modal access with a full commercial ecosystem. A Transit Interchange
tier combines transit with at least one commercial signal. A larger Transit
Node tier is where transit is present but commercial opportunity remains to
be proven out.

Commercial enrichment draws on the major car rental and hotel chains active
in each market, reflected in the current dataset.

### Major hub filter

Airports adjacent to a major Retail Centres cluster are excluded as likely
major commercial hubs. The largest international airports generate their
own retail gravity and do not exhibit the park-and-transit pattern the
archetype is built to find; the adjacency filter removes them.

### Planned enhancements

The following are planned, not current capability:

- Airport passenger-volume data, intended to replace the current
  adjacency-based hub proxy with a direct traffic-based classifier
- A parking-operator directory covering the major operators active in each
  market

---

## Map integration

Urban Fringe and Commuter are available as overlay layers alongside the core
Retail Centres view, so a reviewer can see Urban Fringe and Commuter
candidates together with the base retail-cluster map. Commuter candidates
are further distinguished as integrated — near a Regional or District Retail
Centres cluster — or standalone, consistent with the Commuter definition
above.

## Data Sources

Map and location data © [OpenStreetMap contributors](https://www.openstreetmap.org/copyright) / [ODbL](https://opendatacommons.org/licenses/odbl/).

## See also

- [[catchment-ranking-methodology|Catchment Ranking Methodology]] — the canonical statement of the Retail Centres tier gates
- [[co-location-methodology|Co-location Methodology]] — the anchor-composition test that drives Retail Centres tier assignment
- [[co-location-ranking-system|Co-location Ranking System]] — how Retail Centres clusters are ordered within a country
- [[retail-brand-family-taxonomy|Retail Brand-Family Taxonomy]] — the anchor classes referenced throughout
- [[about-regional-markets-system|Regional Markets Intelligence System]] — the 400-market set built on Retail Centres cluster data
- [[atlas-top-400-north-america|Top 400 Regional Markets — North America]] — qualifying set of suburban-regional Retail Centres markets in NA
- [[atlas-top-400-europe|Top 400 Regional Markets — Europe]] — qualifying set of suburban-regional Retail Centres markets in EU
- [[od-catchment-methodology|Distance-Band Methodology]] — how demand zones are measured around each cluster centroid
