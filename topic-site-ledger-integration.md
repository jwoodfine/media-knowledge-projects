---
schema: foundry-doc-v1
title: "Site Ledger Integration"
slug: topic-site-ledger-integration
aliases:
  - topic-site-ledger-integration
category: governance
type: reference
content_type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: PROSE-TOPIC
last_edited: 2026-05-06
editor: pointsav-engineering
short_description: "Operational link binding each physical construction site to an isolated digital archive container, maintaining immutable audit records from groundbreak through commissioning."
paired_with: topic-site-ledger-integration.es.md
cites:
  - ni-51-102
  - osc-sn-51-721
---

Every active Woodfine development site generates an immutable digital audit trail maintained by the PointSav platform — the legal record of construction milestones, inspection outcomes, and schedule variances that investors and regulators can independently verify. Each site maps to its own isolated archive; events on the physical site generate records that cannot be overwritten after entry. The ledger records compliance with the [[topic-asset-architecture-standard|Asset Architecture Standard]] from the moment of acquisition (gated by the [[topic-zoning-acquisition-rules|zoning acquisition rules]]) through commissioning.

## The digital container model

Each site is assigned an independent archive container — not a shared database with other sites. Isolation is structural: a data event affecting one site's archive cannot affect another. This mirrors the Direct-Hold financial architecture, where each asset is a legally isolated vehicle. Site-level isolation means that a development problem at one site — cost overrun, contractor default, inspection failure — cannot contaminate the audit record of another.

## Daily progress logging

Site managers generate daily progress logs that document construction milestones, material deliveries, inspection outcomes, and schedule variances. These logs are committed to the digital container as flat files — plain-text records with date-stamped entries. The flat-file format ensures the records are readable by any system for the full life of the asset, without dependency on proprietary database software.

Once committed, entries are immutable. A daily log for a given date cannot be overwritten or corrected — corrections are new entries with an explicit amendment notation. This immutability is the audit property: the record reflects what was documented at the time, not a retrospective rewrite.

## Verifiable construction audits

The accumulation of daily logs across the construction period constitutes a verifiable audit trail. An investor, a regulatory body, or a future buyer can reconstruct the development history from the ledger without relying on the developer's self-reported account. The records exist independently of the developer's ongoing custody.

This transparency is a fiduciary output of the Fiduciary Data Mandate — the obligation to maintain mathematical ownership of investor-relevant data extends to construction records for assets held in the Direct-Hold portfolio.

## See also

- [[topic-zoning-acquisition-rules]] — pre-acquisition verification that triggers the ledger
- [[topic-asset-architecture-standard]] — structural specification that the ledger records compliance with

---

*Copyright © 2026 Woodfine Capital Projects Inc. Licensed under [Creative Commons Attribution 4.0 International](https://creativecommons.org/licenses/by/4.0/).*
