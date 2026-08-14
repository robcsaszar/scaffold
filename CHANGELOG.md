# Changelog

All notable changes to this project are documented here. Format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/); versioning follows [SemVer](https://semver.org/).

## [0.6.0] - 2026-08-14

### Added

- `ai-agents-dot-md`, `ai-context-dot-md`: Review mode now applies its findings. After presenting the score it offers `(a)ll / (s)elect by number / (n)one`, edits the file one numbered item at a time, then re-scores and reports the new grade beside the old one. Previously both modes stopped at recommendations, so the deliverable was a report rather than a better file — `ai-design-dot-md` was the only one of the three that actually wrote an update.
- Both apply steps preserve every line the review did not flag, and skip the offer when the content arrived inline rather than as a path or the file is not writable. `ai-context-dot-md` additionally verifies what replaced a stale path before rewriting it, since deleting the line trades a wrong fact for a missing one.

### Changed

- `ai-agents-dot-md`: `references/example.md` was never referenced from the body and could not be loaded. It now has an explicit conditional load trigger (when the user asks what a finished AGENTS.md looks like, or for JS/TS monorepos — it is a turborepo + pnpm worked example).

## [0.5.0] - 2026-07-10

### Added

- Initial release: ai-agents-dot-md, ai-context-dot-md, and ai-design-dot-md skills.

[0.5.0]: https://github.com/robcsaszar/scaffold/releases/tag/v0.5.0
