@~/Foundry/AGENT.md

# media-knowledge-projects — Repo Guide

> **State:** active | **Last updated:** 2026-05-20
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

This is a **flat content repo** — no project registry, no Cargo workspace.
All content is `topic-*.md` files (English canonical) paired with
`topic-*.es.md` (Spanish bilingual pair).

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
- Category values: `governance` (most articles), per `naming-convention.md §10`
- Slug: always matches filename without extension (e.g., `slug: topic-co-location-methodology`)

---

## Known gotchas

- `paired_with:` YAML key was missing in 5 ES country index stubs (fixed PJ2 `b138b99`).
  If adding new ES files, double-check `paired_with:` is keyed, not a bare line.
- Comms releases use `text-{topic}-{YYYY-MM}` slug pattern (no `-release` suffix).
- Canada co-location index is `quality: complete` with a full ranked table.
  Other country indices defer ranked tables to gis.woodfinegroup.com.
