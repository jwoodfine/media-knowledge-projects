---
schema: foundry-doc-v1
title: "Spend and population estimation: provenance and assumptions"
slug: spend-population-provenance
category: gis
index_group: data-overview-and-sources
type: concept
content_type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: PROSE-TOPIC
last_edited: 2026-09-04
editor: pointsav-engineering
short_description: "Provenance chain behind catchment population and spend estimates — Kontur Population, H3 aggregation, and per-capita multipliers, with their stated weaknesses."
paired_with: gis/spend-population-provenance.es.md
cites: []
---

The Woodfine location intelligence map presents two synthesised demographic surfaces for every co-location cluster: a catchment population and an estimated annual retail spend. Both are decision-grade inputs — a site-selection analyst or a capital allocator will read them as measurements. They are not measurements. They are layered model estimates built on open data. This article documents exactly how those two surfaces are produced, what they assume, where they are weakest, and how their uncertainty is — and is not yet — communicated.

## The estimation chain

The spend figure shown on a cluster is the output of three sequential modelling steps. None of the error introduced at each step is currently propagated forward into the displayed value.

### Step 1 — Population: Kontur Population, H3-native

Population originates from **Kontur Population** (CC BY 4.0), delivered per country at **H3 resolution 8** — a finer hexagon grid than the resolution-7 level catchments are ultimately aggregated to. Because Kontur's population values are already bound to hexagon geometry at source, there is no raster-to-hexagon reprojection step and no dasymetric redistribution model in this stage of the chain; the modelling assumptions that produce Kontur's own resolution-8 figures are Kontur's, not this pipeline's, and are not independently documented here.

### Step 2 — Aggregation to H3 resolution 7

Each resolution-8 cell is resolved to its containing **resolution-7 parent hexagon** (average area approximately 5.16 km²), and population values are summed across every resolution-8 child sharing that parent. Catchment population is the sum of resolution-7 cell populations over the cells whose centroids fall inside a cluster's distance rings.

### Step 3 — Spend: per-capita multiplier

Estimated annual spend is **population × a per-capita expenditure multiplier**, applied per country and per retail category (grocery, hardware, wholesale). The multipliers are proxies derived from national household-expenditure surveys — BLS Consumer Expenditure Survey for the US, Statistics Canada Household Expenditures for Canada, Eurostat Household Budget Survey for the EU member countries, and INEGI for Mexico.

### The uniform-per-capita assumption

The single most consequential simplification is: **every resident of a country is assigned the same per-capita spend, regardless of where they live.** A household in central London and a household in a Welsh market town receive the identical grocery multiplier. The model has no income, age, household-size, or cost-of-living variation below the national level.

This assumption is defensible as a baseline — it is transparent, requires only one authoritative survey per country, and does not pretend to a granularity the inputs cannot support. But it breaks in predictable ways:

- High-income metropolitan areas are systematically understated. A cluster in an affluent catchment carries the national-average multiplier and therefore reports less spend than the area actually commands.
- Lower-income regions are systematically overstated by the same mechanism.
- The error is spatially correlated, not random. Because it tracks the local income gradient, it does not cancel out across a catchment; it biases the entire trade-area total in one direction.

A future pipeline version is intended to vary the multiplier sub-nationally using local income data — US ACS median household income by tract, Statistics Canada census income, Eurostat regional income at NUTS-2/NUTS-3 — replacing the flat national constant. Until that ships, the uniform assumption holds and is stated in the Method modal.

### False-precision risk

Each step above has its own error, and they compound. The current pipeline carries no error term through any step. A spend figure is emitted and rendered as a single scalar.

The discipline that follows is therefore a presentation rule: **the map must not display false-precision figures.** A modelled spend estimate of $147,382,901 implies measurement accuracy the model does not have. Spend is shown rounded to a band the model can defend — for example "~$150M annual grocery spend" or a range — and labelled as an estimate. Catchment population follows the same rule: "~140,000 people" rather than "139,847."

### The modifiable-areal-unit problem

Both surfaces are aggregated to the H3 resolution-7 grid before catchment sums are taken. The modifiable-areal-unit problem (MAUP) is the well-established result that statistics computed over areal units change when the unit's size or boundary changes. Two consequences for this map:

- **Scale effect.** Rolling up Kontur's resolution-8 cells to the approximately 5.16 km² resolution-7 hexagon smooths the population surface. A different target resolution would produce different catchment totals for the same rings, because the hexagon lattice intersects the distance rings differently at each resolution.
- **Edge effect.** A distance ring slices through hexagons at its boundary. A cell is counted as fully in or fully out based on its centroid, so the catchment total is sensitive to exactly how the hexagon lattice falls relative to the ring.

MAUP is not a defect to be fixed; it is an inherent property of any areal aggregation. The obligation is to acknowledge it in the Method modal and to avoid over-interpreting small differences between clusters. The magnitude of the MAUP effect at resolution 7 for the distance rings in use has not yet been quantified; a sensitivity sweep across resolutions 6, 7, and 8 is a documented gap.

## Confidence and how it is shown

### What confidence already exists

The pipeline already computes a per-market **confidence flag** in `regional-markets.json`. This flag is a function of regional name-resolution quality, not POI or census data-ingestion quality. It is downgraded specifically where the name-resolution pipeline falls back to an administrative boundary name rather than resolving a colloquial, settlement-level place name.

At the 2026-05-22 build, 2,942 of 2,986 Regional Market objects carried the high-confidence flag. Coverage has grown substantially since. As of the most recent full processing run (2026-08-06), the live `regional-markets.json` carries 12,689 Regional Market objects across 24 countries. Of those, 12,578 — about 99% — carry the high-confidence flag. The resolution logic is unchanged; the growth reflects dataset expansion, not a rule change. Despite this, the flag is not yet rendered anywhere — the map draws every cluster at full opacity with an identical marker, so a lower-confidence estimate is visually indistinguishable from a higher-confidence one.

### How confidence is intended to be encoded

The cartographic intention is to make confidence a visual channel on the tier dot, not buried in the modal:

- **Opacity** — lower-confidence clusters rendered at reduced fill opacity so the reader's eye is drawn to the estimates most strongly evidenced.
- **Hollow versus filled markers** — a hollow (stroke-only) dot for lower-confidence clusters and a filled dot for higher-confidence ones is an unambiguous, colour-independent encoding that survives colour-vision deficiency and does not collide with the ordinal tier ramp.

Whichever channel is adopted, it must be explained in the legend so the reader knows a faint or hollow dot means "lower confidence," not "lower tier."

## Source register

The on-map provenance line and the Data / Method modal both derive from this register.

### On-map provenance line

A persistent line on the map face, in the form:

> Data: Kontur Population CC-BY, OSM — updated [build month] · Method ⓘ

OpenStreetMap attribution is a licence obligation under ODbL and remains present separately from the provenance line.

### Data sources

| Source | Role | Vintage | Licence |
|---|---|---|---|
| Kontur Population | H3-native gridded population, resolution 8 — Step 1 of the spend chain | 2023 per-country release | CC BY 4.0 |
| OpenStreetMap | Retail and civic POI locations defining the clusters | Continuously updated; snapshot per build | ODbL 1.0 — © OpenStreetMap contributors |
| Overture Maps — Places | Global POI theme for anchor resolution | 2026 release | CDLA-Permissive-2.0 — © Overture Maps Foundation |
| Overture Maps — Addresses | Street-address backfill for null-address POI records | Release 2026-04-15.0 | ODbL 1.0 — © Overture Maps Foundation contributors |
| BLS Consumer Expenditure Survey | US per-capita spend multiplier proxy | Latest published | US federal public data |
| Statistics Canada — Household Expenditures | Canada per-capita spend multiplier proxy | Latest survey | StatCan Open Licence — adapted from Statistics Canada data; not an endorsement |
| Eurostat — Household Budget Survey | EU per-capita spend multiplier proxy | Latest HBS | CC BY 4.0 — © European Union, 1995–2026 |
| INEGI | Mexico spend proxy and business registry | Latest | INEGI Terms of Free Use |

### Countries covered

The population layer covers United States, Canada, Mexico, Spain, France, Germany, Great Britain, Italy, Netherlands, Austria, Poland, Greece, and Portugal — 13 countries at the current pipeline version. This is a subset of the platform's broader co-location footprint, which spans 24 countries as of the most recent full processing run (2026-08-06). See [[co-location-intelligence-overview]] for full country coverage.

**Open discrepancy, not resolved here:** the per-capita spend multiplier table below carries Denmark and Iceland rather than Spain and Italy — a different 13-country set than the population layer's own coverage above. Whether the spend multipliers genuinely apply to a different country set (e.g. a separate household-survey source with its own coverage) or the table is simply stale is not established by this article; flagged for the pipeline owner rather than silently reconciled.

### Per-capita annual spend multipliers

Multipliers are annual per-capita expenditure proxies expressed in local currency. They are Step-3 inputs and are not currency-normalised.

| Country | Grocery | Hardware | Wholesale | Currency |
|---|---|---|---|---|
| USA | $3,500 | $1,200 | $1,500 | USD |
| Canada | C$3,200 | C$1,100 | C$1,300 | CAD |
| Mexico | MX$18,000 | MX$3,500 | MX$2,500 | MXN |
| Great Britain | £2,800 | £850 | £900 | GBP |
| Germany | €2,900 | €950 | €1,000 | EUR |
| France | €3,100 | €900 | €1,000 | EUR |
| Netherlands | €2,700 | €1,000 | €1,100 | EUR |
| Austria | €3,000 | €950 | €1,000 | EUR |
| Portugal | €2,400 | €600 | €700 | EUR |
| Greece | €2,200 | €500 | €600 | EUR |
| Denmark | €3,500\* | €1,200\* | €1,100\* | DKK\* |
| Iceland | €4,000\* | €1,500\* | €1,500\* | ISK\* |
| Poland | PLN 8,000 | PLN 2,000 | PLN 2,500 | PLN |

**Currency note.** Because multipliers are in local currency and are not FX-normalised, cross-country spend comparisons are not directly meaningful. Rankings are most defensible within a single country or within the eurozone.

\* Denmark and Iceland are not eurozone members; their multipliers are shown here still denominated in euros pending re-derivation in DKK and ISK, and are not yet comparable to the eurozone figures above them.

## How to read a spend or population figure

1. **Population and spend are modelled estimates, not counts.** They are built from open data and carry the errors described above.
2. **Spend assumes everyone in a country spends the same per head.** Affluent catchments are understated; lower-income catchments are overstated. Local income variation is planned but not yet applied.
3. **Figures are rounded on purpose.** A round number signals an estimate; a precise-looking number would imply false accuracy.
4. **A faint or hollow dot means lower confidence,** not a lower tier.
5. **Small differences between clusters may be grid artefacts** (MAUP), not real differences. Compare orders of magnitude, not final digits.
6. **Spend is comparable within a country, not across currencies** until FX normalisation ships.

## Status summary

| Item | State |
|---|---|
| Kontur → H3 resolution-7 population surface | Shipped |
| Per-capita spend multipliers (13 countries) | Shipped |
| Confidence flag in `regional-markets.json` | Computed; not yet rendered |
| On-map provenance and vintage line | Planned |
| Data / Method modal with full source register and caveats | Planned |
| Confidence encoded on tier dots (opacity or hollow marker) | Planned |
| Per-estimate error propagation and ± bands | Planned |
| Sub-national income-varying spend multipliers | Planned |
| MAUP sensitivity sweep (resolutions 6, 7, 8) | Planned — gap, not yet quantified |
| FX normalisation for cross-country spend | Open question |

All forward-looking items above are stated as planned or intended; they describe the intended direction of the pipeline, not capabilities currently live on gis.woodfinegroup.com.

## See also

- [[trade-area-methodology]] — how the polygon over which population and spend are summed is defined
- [[catchment-ranking-methodology]] — how the spend figure feeds the planned strength score
- [[trade-area-data-sources]] — the population and spend data sources and per-capita multiplier table
