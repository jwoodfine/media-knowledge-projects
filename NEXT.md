# NEXT.md — content-wiki-projects

> **Scope: this repo only.** Cross-repo and workspace-level open
> items live at `~/Foundry/NEXT.md`.

Last updated: 2026-05-20.

---

## Currently open

### Stage 6 promotion pending (5 commits)

5 commits ahead of origin/main. Content-only — no binary rebuild required.
Promote via `~/Foundry/bin/promote.sh` from within this directory (or the
Command Session equivalent).

| Commit | Author | What |
|---|---|---|
| `b138b99` | Jennifer | PJ2: expand 5 country co-location index stubs; fix ES paired_with bug |
| `2cb58df` | Jennifer | PJ5: slug normalization on comms release |
| `2ec3a8f` | Jennifer | PJ3: short_description added to all 26 EN+ES articles |
| `78db55b` | Peter | PJ7: leapfrog-facts.yaml link_slug prefix fix |
| `6765be0` | Jennifer | PJ1: methodology tier table corrected |

### PJ2 — country indices: full ranked tables pending GIS data

The 5 non-Canada country indices (Italy, Mexico, Nordics, Poland, Spain) now have
substantive market-profile content and Provenance blocks. The full per-site ranked
tables remain deferred to [gis.woodfinegroup.com](https://gis.woodfinegroup.com).
When GIS platform data is available for export, return here to fill in the site tables
matching the Canada article format.

### D10 — wikilink validation pass (blocked on Stage 6 + binary rebuild)

After the monorepo Stage 6 + binary rebuild runs (Command Session scope), run a
validation pass to confirm all bare-slug wikilinks in projects-wiki articles resolve
correctly via the P0-C resolver. Estimated: ~30-min pass.

---

## Recently closed

- **PJ1** (`6765be0`) — methodology tier table corrected to match 12-rank matrix
- **PJ2** (`b138b99`) — 5 country index stubs expanded; ES frontmatter bug fixed
- **PJ3** (`2ec3a8f`) — short_description added to all 26 EN+ES articles
- **PJ4** — heading audit: clean, no changes needed
- **PJ5** (`2cb58df`) — comms release slug normalized
- **PJ6** — bilingual parity verified: all EN articles have ES pairs
- **PJ7** (`78db55b`) — leapfrog-facts.yaml link_slug prefix fixed
- **PJ8** — BCSC review: no violations found
- **CLAUDE.md missing** — created 2026-05-20 (this session)

## Pointers

- Workspace-level open items: `~/Foundry/NEXT.md`
- Workspace changelog: `~/Foundry/CHANGELOG.md`
- BCSC disclosure rule: `~/Foundry/AGENT.md` §Hard rules
