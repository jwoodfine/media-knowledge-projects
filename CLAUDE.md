@~/Foundry/AGENT.md

# media-knowledge-projects — Repo Guide

> **State:** active | **Last updated:** 2026-06-26
> **Role:** Totebox sub-clone under project-knowledge cluster
> **Workspace AGENT.md takes precedence on conflict.**

---

## Repo scope

Wiki content for the Woodfine Projects knowledge base
(projects.woodfinegroup.com). Articles cover:

- Co-location methodology and ranking system
- Regional site indices (North America, Europe)
- Asset architecture standards
- BIM methodology
- GIS data standards
- Release communications (`comms/` subdirectory)

No project registry, no Cargo workspace.

**Category layout (2026-06-26).** Converted from flat layout to category
directories as part of the jennifer-to-wiki backfill initiative (see
BRIEF-jennifer-to-wiki-backfill.md in project-editorial). Six categories
with bilingual MOC pages:

| Category | Scope |
|---|---|
| `co-location/` | Anchor taxonomy, floor plates, BOMA, ADI, site scoring |
| `architecture/` | Architectural styles in CRE evaluation context |
| `markets/` | Bloomberg/WSJ office + retail research summaries |
| `urban/` | Commuter patterns, gateway cities, demographic methodology |
| `gis/` | GIS data sources, coverage, provenance (articles pending D4/project-jennifer review) |
| `reference/` | Terminology, glossary from projects.csv |

Existing flat `topic-*.md` articles remain at root until migrated via
alias-based `git mv` (pending alias engine verification with Command).
New articles authored as part of backfill go directly into categories.
`comms/` subdirectory unchanged.

---

## Commit flow

- Branch: `main`
- Commits via `~/Foundry/bin/commit-as-next.sh "<message>"`
- Stage 6 promotion from Command Session via `~/Foundry/bin/promote.sh`
- Do not `git push` directly — all pushes go through promote.sh

---

## Artifacts produced here

All files are **TOPIC-*** or **COMMS-*** artifacts:
- `topic-*.md` / `topic-*.es.md` → project-editorial gateway → media-knowledge-projects
- `comms/text-*.md` → project-editorial gateway (release communications)

Self-contained content repo — stage directly to this repo; no `drafts-outbound/` needed.

---

## File conventions

- Frontmatter: `schema: foundry-doc-v1`, `language_protocol: PROSE-TOPIC` (EN),
  `TRANSLATE-ES` (ES), `bcsc_class: current-fact`
- All articles: bilingual pair required (`paired_with:` field in both directions)
- Category values: one of the 6 defined categories above (for new articles); legacy `governance` on existing flat articles until migrated
- Slug: inside categories uses bare slug without `topic-` prefix (e.g., `slug: co-location-methodology`); existing flat articles keep `topic-*` slug until migrated

---

## Known gotchas

- `paired_with:` YAML key was missing in 5 ES country index stubs (fixed PJ2 `b138b99`).
  If adding new ES files, double-check `paired_with:` is keyed, not a bare line.
- Comms releases use `text-{topic}-{YYYY-MM}` slug pattern (no `-release` suffix).
- Canada co-location index is `quality: complete` with a full ranked table.
  Other country indices defer ranked tables to gis.woodfinegroup.com.
