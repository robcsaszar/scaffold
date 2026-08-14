# Changelog

All notable changes to this project are documented here. Format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/); versioning follows [SemVer](https://semver.org/).

## [0.6.0] - 2026-08-14

### Changed

- `ai-agents-dot-md`: `references/example.md` was never referenced from the body and could not be loaded. It now has an explicit conditional load trigger (when the user asks what a finished AGENTS.md looks like, or for JS/TS monorepos — it is a turborepo + pnpm worked example).

## [0.5.0] - 2026-07-10

### Added

- Initial release: ai-agents-dot-md, ai-context-dot-md, and ai-design-dot-md skills.

[0.5.0]: https://github.com/robcsaszar/scaffold/releases/tag/v0.5.0
