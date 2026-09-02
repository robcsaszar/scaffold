# Changelog

All notable changes to this project are documented here. Format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/); versioning follows [SemVer](https://semver.org/).

## [0.7.0] - 2026-09-01

### Added

- `ai-agents-dot-md`: Create mode now asks what is branch-only (release, migration, single-package steps) and pushes it behind a pointer instead of inlining it in the always-loaded root file. Step 3 states how to word a pointer — trigger first, target second, one trigger per situation — how to pick and repeat a leading word for each recurring behaviour, and that closure definitions state demand (`every changed model has a migration and a test`) alongside the exit code.
- `ai-agents-dot-md`: Validate step and Review-mode anti-pattern checklist gain five checks: no-op sentences the agent obeys by default, bare pointers with no trigger, scattered concepts, sediment (lines about fixed friction), and branch-only detail inlined at root. Two matching NEVER entries with paired INSTEADs.
- `ai-agents-dot-md/references/knowledge-base.md`: six new sections — The Two Loads, Information Hierarchy (ladder, branch test, co-location, sprawl), Context Pointers (with weak/strong table), Completion Criteria (clarity and demand, premature completion), Leading Words, Pruning (single source of truth, environment-as-cache, relevance and sediment, the no-op test). Pointer and no-op rows added to the ignored/works tables, three items to the Auditing Checklist, and a pointer acid test.
- `ai-context-dot-md`: Create mode's analysis questions now include the cache rule (write only what the agent cannot find by looking), Language is framed as one canonical term per concept with the _Avoid_ list retiring synonyms, and child links are written situation first, path second. Validate gains two checks and Review mode's anti-pattern checklist three: bare child pointer, cache lines, scattered term.
- `ai-context-dot-md/references/knowledge-base.md`: three new sections — Language as Leading Words, The Environment Is a Source of Truth, Child Links Are Pointers (with weak/strong table) — and two anti-pattern rows. The template and example Children entries now show the trigger-first form.
- `ai-design-dot-md`: every don't in the Do's and Don'ts section names the do that replaces it, and Phase 5 checks for it. Updating an existing DESIGN.md now drops prose for tokens no longer defined in the YAML and reports which lines went.

### Changed

- `ai-agents-dot-md`: Pink Elephant principle now says when a prohibition is still warranted and to pair it with the positive target.
- `ai-context-dot-md`: Review mode's freshness check is stated as actions against the working tree instead of naming navigation skills this plugin does not ship. The Do NOT Load section keeps only its two conditional entries; the two that restated the Step 2 and Step 3 triggers are gone.

## [0.6.0] - 2026-08-14

### Added

- `ai-agents-dot-md`, `ai-context-dot-md`: Review mode now applies its findings. After presenting the score it offers `(a)ll / (s)elect by number / (n)one`, edits the file one numbered item at a time, then re-scores and reports the new grade beside the old one. Previously both modes stopped at recommendations, so the deliverable was a report rather than a better file — `ai-design-dot-md` was the only one of the three that actually wrote an update.
- Both apply steps preserve every line the review did not flag, and skip the offer when the content arrived inline rather than as a path or the file is not writable. `ai-context-dot-md` additionally verifies what replaced a stale path before rewriting it, since deleting the line trades a wrong fact for a missing one.

### Changed

- `ai-agents-dot-md`: `references/example.md` was never referenced from the body and could not be loaded. It now has an explicit conditional load trigger (when the user asks what a finished AGENTS.md looks like, or for JS/TS monorepos — it is a turborepo + pnpm worked example).

## [0.5.0] - 2026-07-10

### Added

- Initial release: ai-agents-dot-md, ai-context-dot-md, and ai-design-dot-md skills.

[0.7.0]: https://github.com/robcsaszar/scaffold/releases/tag/v0.7.0
[0.6.0]: https://github.com/robcsaszar/scaffold/releases/tag/v0.6.0
[0.5.0]: https://github.com/robcsaszar/scaffold/releases/tag/v0.5.0
