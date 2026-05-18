# Repo layout — content-wiki-projects

Authoritative list of allowed top-level paths in this repository.
Files outside this allowlist must move; the rule is never loosened
to accommodate misplaced files. See
`~/Foundry/conventions/root-files-discipline.md` for the canonical
companion-file tier.

## Allowed root files

| File | Purpose | Required? |
|---|---|---|
| `README.md` | Public-facing English entry point | required |
| `README.es.md` | Spanish bilingual pair (per CLAUDE.md §6) | required if README.md present |
| `LICENSE` | Repository license; canonical text from `factory-release-engineering/licenses/` | required |
| `NOTICE` | Apache 2.0 attribution (if Apache-licensed) | required if LICENSE = Apache-2.0 |
| `SECURITY.md` | Security disclosure policy | required for public repos |
| `TRADEMARK.md` | Trademark policy (when distinct from LICENSE) | required for branded repos |
| `CODE_OF_CONDUCT.md` | Contributor code of conduct | required for public repos |
| `CLAUDE.md` | Repo-specific Claude Code guidance; ≤150 lines per CLAUDE.md size discipline | required |
| `NEXT.md` | Repo-scope hot items; ≤200 lines | optional |
| `CHANGELOG.md` | Version history per CLAUDE.md §7 | required for versioned repos |
| `index.md` | Wiki home page (lede-only per cluster convention) | required |
| `featured-topic.yaml` | Featured topic selection for wiki home | optional |
| `leapfrog-facts.yaml` | Leapfrog fact data for wiki rendering | optional |
| `reference-invariants.yaml` | Homepage reference invariants panel — three plain-English structural claims (engine Phase D) | optional |
| `glossary-projects.csv` | Projects glossary (canonical source of truth per cluster convention) | required |

## Allowed root directories

| Directory | Purpose |
|---|---|
| `.git/` | Git internal |
| `.agent/` | Engine-agnostic agent state (canonical; `.claude/` is a backward-compat symlink per AGENT.md) |
| `.github/` | GitHub CI / templates |
| `comms/` | Communications and public-facing copy (press releases, announcements) |

*All topic-*.md files live at root — no additional content subdirectories in wiki repos.*

## Allowed root content files (wiki-specific)

Wiki repos use a flat-file pattern. All content lives at the root as
named topic files. Allowed patterns:

| Pattern | Purpose |
|---|---|
| `topic-*.md` | Projects topic articles (English) |
| `topic-*.es.md` | Spanish bilingual pair for each topic |

## Misplacement procedure

Files found outside this allowlist:
1. Surface in `cleanup-log.md` (`.agent/rules/cleanup-log.md`)
2. Move via `git mv` to the correct location (or to `~/Foundry/`
   workspace root if cross-repo)
3. Reference the move in commit message
4. Do NOT loosen this allowlist to accommodate

## Schema

This file follows `foundry-repo-layout-v1` (informal). The cluster
manifest at `<cluster>/.agent/manifest.md` may impose tighter
constraints; this file's allowlist is the floor.
