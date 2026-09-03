# Contributing

Thanks for considering a contribution to `scaffold`. This is a small pack of three skills for creating and reviewing standing context files. Contributions are welcome, but the bar is "does this fit the pack's purpose," not "is this a good idea in general."

## Before you start

- **Bug in an existing skill?** Open an issue with a concrete example: what the skill produced, and what you expected instead.
- **New skill idea?** Open an issue first. The three skills here share a purpose (standing context files an agent reads before acting on a repo); a new skill needs to fit that purpose, not just be generally useful.
- **Design questions** are worth raising as an issue before writing code. See `AGENTS.md` for the boundaries already decided.

## Making a change

1. Fork and branch from `main`.
2. If you're editing an existing skill, keep its overall structure and mode-detection pattern intact unless you're proposing a structural change (raise that as an issue first).
3. If you're adding a new skill, follow the layout convention in `AGENTS.md`: one directory under `skills/<name>/`, frontmatter `name:` matching the directory name.
4. Update `README.md`'s skill table in the same change.

## Quality bar

Each skill here should read as generic, source-repo-agnostic guidance: no assumptions specific to any one project, no absolute paths, no leaked internal references. This isn't enforced by CI (the pack itself has none, by design), but a PR that introduces project-specific leakage will be asked to fix that before merge.

## Releasing

Releases are cut by the **Release** workflow (`.github/workflows/release.yml`), not by hand. It creates the tag and the GitHub release together, with the release notes taken from `CHANGELOG.md`.

1. In the PR that ships the change, add a `## [x.y.z] - YYYY-MM-DD` block at the top of `CHANGELOG.md` and a matching `[x.y.z]: https://github.com/robcsaszar/scaffold/releases/tag/vx.y.z` link at the bottom.
2. Set the same version in `.claude-plugin/plugin.json` and `.claude-plugin/marketplace.json`. All three must agree.
3. Merge to `main`.
4. Run the workflow with the tag and target:

   ```sh
   gh workflow run release.yml -f tag=vx.y.z -f target=main
   ```

   or from the Actions tab: **Release → Run workflow**, tag `vx.y.z`, target `main`.

The workflow fails before creating anything if `CHANGELOG.md` has no heading for the requested version. Do not `git tag` or `gh release create` manually; a tag that exists before the workflow runs makes it fail, and a release created by hand skips the changelog check.

## What won't be merged

- Skills that require a specific tech stack or framework to be useful; these three are intentionally stack-agnostic.
- Source-repo-specific assumptions leaking into a skill's guidance.

## Questions

Open an issue. There's no separate chat or forum for this project.
