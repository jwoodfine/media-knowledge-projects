---
schema: foundry-doc-v1
title: "GIS North America Dataset — Site Pipeline Status (2026)"
slug: text-gis-north-america-dataset-2026
short_description: "Internal client communication on the North America co-location dataset status — current scored cluster counts by jurisdiction, active pipeline shortlist requirements, and the dataset calibration approach applied when Fifth-Degree Cluster concentration exceeds 10% of the Primary Target population."
category: comms
type: release-text
content_type: topic
status: active
audience: customer-woodfine
bcsc_class: current-fact
last_edited: 2026-07-01
editor: pointsav-engineering
language_protocol: PROSE-TOPIC
source_refs:
  - "bfe6fb6bbb557fd15bdb7ffd53bce60e527911eb7658c906df5b69813bdb8747"
paired_with: text-gis-north-america-dataset-2026.es.md
cites:
  - ni-51-102
  - osc-sn-51-721
---

**For internal use — Woodfine client communications**

---

The North America co-location dataset is maintained as three separate scored populations — Canada, the United States, and Mexico — each applying the five-degree cluster methodology to the Walmart Supercentre network in the applicable jurisdiction. Cluster degree and tier score (T3 Apex ≥ 700, T2 Hub ≥ 450, T1 Valid ≥ 150) are determined by the standard co-occurrence thresholds: 1.0 km Primary-Secondary radius, 5.0 km Tertiary radius.

---

**Pipeline requirements by jurisdiction:**

| Jurisdiction | Direct-Hold Solution | Required sites (equity + debt) | Minimum shortlist |
|---|---|---|---|
| Canada | Professional Centres Canada LP | 26 | 52 |
| United States | Professional Centres United States LP (planned) | 52 | 104 |
| Mexico | Professional Centres Mexico FIBRA (planned) | 26 | 52 |

The shortlist requirement is set at a minimum 2:1 ratio against the required development count to account for sites where adjacent land is unavailable or where permitting and production timelines extend beyond the applicable tolerance.

---

**Dataset calibration note:**

If Fifth-Degree Clusters — sites where both Secondary Targets (Home Depot and Costco) and both Tertiary Targets (post-secondary institution and major medical centre) are confirmed within the applicable radius thresholds — account for more than 10% of all Primary Target entries in a given jurisdiction's dataset, the radius thresholds are recalibrated downward. The Tertiary proximity threshold tightens from 5.0 km to 3.0 km; the Primary-Secondary threshold tightens from 1.0 km to below 1.0 km. This recalibration preserves the discriminating power of the top cluster tier across datasets of varying size and geographic density.

Calibration checks are performed each time the dataset is updated with new Primary Target sales per square foot data. The recalibration trigger has not been activated in the Canada, United States, or Mexico datasets as of the current reporting period.

---

**Sales per square foot update cadence:**

Primary Target sales per square foot rankings are updated annually or every second year to generate trend data and enable re-ranking of the full Primary Target population. Sales per square foot trends data, accumulated across update cycles, provides a longitudinal view of which regional markets are gaining or losing commercial productivity relative to the chain average — informing both the active pipeline prioritization and the monitoring register for sites where adjacent land was previously unavailable.

---

*All figures reflect current V2 scoring methodology. Cluster counts are subject to change as Primary Target network changes (new store openings, store closures, format conversions) are ingested into the dataset. Site pipeline counts reflect approved shortlist targets; individual site availability is assessed through the Transaction Summary Report process.*
