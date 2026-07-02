# Agent Context

## What This Is

`open-horizons` is a pure Claude skill that acts as a pre-closure checkpoint for open-ended research, capability scans, skill reviews, and gap analyses.

## Why It Exists

Agents often anchor on the sources already in front of them and close the task as soon as the immediate list is processed. This skill gives Claude a forced protocol for reopening the search space before saying the work is complete, so the final answer can distinguish sufficient coverage from exhaustive coverage.

## Architecture

- Main entry point: `SKILL.md`
- Core files/directories:
  - `SKILL.md`: Claude-facing behavior contract, trigger conditions, five checks, output format, and examples.
  - `README.md`: public identity, install instructions, usage examples, release policy, and badge row.
  - `version.txt`: release-please version source for the skill bundle.
  - `docs/decisions/`: short release and design decision notes.
- Runtime/deployment shape: no executable code, package manager, network calls, config files, or generated assets. The released artifact is a Claude skill bundle containing the instruction file plus project metadata.

## Develop, Run, Test

```sh
cp SKILL.md ~/.claude/skills/open-horizons/SKILL.md
test -f README.md && test -f SKILL.md && test -f LICENSE && test -f version.txt
grep -q '^0\.1\.0$' version.txt
```

## Release Process

This repo follows the public software release standard:

- SemVer.
- Conventional Commits.
- release-please Release PRs.
- Toby-approved Release PR merge before publishing.
- GitHub Releases first; external registries only by explicit approval.

Release state is tracked in `version.txt`. `release-please-config.json` updates that file and `CHANGELOG.md`.

## Current State

Seeded for public release at `0.1.0`. The skill is GitHub-only: release-please may create GitHub Releases after a Release PR is approved and merged, and the expected release asset is a zip containing the skill and project metadata.

## Gotchas

- This is intentionally light. Do not add `SECURITY.md`, `CONTRIBUTING.md`, issue templates, CODEOWNERS, package metadata, or heavyweight workflows unless the repo grows executable helper code.
- The trigger is self-directed. The skill should run when the agent feels ready to close, even if the user did not explicitly invoke it.
- The output should be honest about scope. Most uses should say `Sufficient`, not `Exhaustive`.
- Behavior-changing edits to `SKILL.md` are product changes for release purposes.

## Decision Notes

Design decisions live in `docs/decisions/`.

Add a decision note when a choice affects public behavior, release shape, architecture, compatibility, security, publishing, or future maintenance.
