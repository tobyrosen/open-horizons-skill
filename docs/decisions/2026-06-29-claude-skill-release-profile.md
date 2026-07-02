# Use Claude Skill Release Profile

Date: 2026-06-29
Status: accepted

## Context

`open-horizons` contains only `SKILL.md` plus public documentation. It has no executable helper code, package metadata, service runtime, schemas, or deployment surface.

## Decision

Use the `claude-skill` release profile. Keep the repo light and ship the skill as a GitHub Release asset.

## Consequences

The repo carries base release files, `SKILL.md`, `version.txt`, release-please config, and light profile workflows. It intentionally does not carry `SECURITY.md`, `CONTRIBUTING.md`, CODEOWNERS, issue templates, PR templates, package metadata, or heavyweight CI.

## Follow-up

Revisit only if the skill gains executable helper code or becomes part of a larger software package.
