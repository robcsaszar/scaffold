# AGENTS.md

## Mission

This repo publishes the `scaffold` skill pack: three skills for creating and reviewing the standing context files (AGENTS.md, CONTEXT.md, DESIGN.md) an AI agent reads before working on a codebase. There is no build, no tests, no runtime of its own. The deliverable is the contents of `skills/*`, each copied in from a source repo (Orakl) where they are used and refined, then published here for anyone to install. Changes should be judged by: would a stranger who installs one of these skills into an unrelated project get correct, generic guidance out of it?

## Layout convention

- One directory per skill under `skills/<name>/`, `name:` in frontmatter matching the directory name exactly.
- Each skill's full directory ships as-is: `SKILL.md` plus any `references/` it depends on. Don't split a skill across a partial copy.
- No skill in this pack ships a `scripts/` directory. If a future update adds one, add a SAFETY.md documenting it in the same change (see how `ai-forge`, a sibling pack, handles this).

## Judgment boundaries

NEVER:
- Never let a copied skill's content leak repo-specific references back to Orakl (or any other single source project). A published skill needs to read as generic guidance, not one project's internal notes.
- Never remove a skill without asking first: this repo's whole value is the stable set of three, and removing one is a breaking change for anyone who installed it.

ASK:
- Ask before changing the license or copyright holder.
- Ask before adding a fourth skill that doesn't fit the "standing context file" shape the other three share.

ALWAYS:
- When re-syncing a skill from its source, re-run the orakl-leakage grep (`grep -rni "orakl"` across `skills/`) before publishing, and flag any hits rather than silently editing them out.
- When adding, removing, or renaming a skill: update the table in [`README.md`](README.md) in the same change.

## Adding a skill

1. Copy the full skill directory from its source, not just `SKILL.md`.
2. Grep the copy for source-repo-specific leakage (project name, absolute paths) before publishing.
3. Add a row to the table in `README.md`.
4. Decide whether it ships a `scripts/` directory; if so, add `SAFETY.md` describing what the script does.
