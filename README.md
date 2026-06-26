# open-horizons

A Claude Code skill that acts as a pre-closure checkpoint for research, capability scans, and gap analyses. Run it before declaring any research task done.

## The Problem It Solves

Agents anchor on the resources in front of them. Given 18 URLs to analyze, the agent analyzes those 18 and declares "done" — without asking whether better resources exist elsewhere. This is **closure bias**: a systematic tendency to minimize open loops.

`open-horizons` forces a structured re-opening of those loops before they close.

## When It Activates

This skill is **self-triggered** — the agent runs it automatically before saying things like:

- "I've looked at the main options"
- "That covers it"
- "The analysis is complete"
- "Nothing else comes to mind"

## The Five Checks

1. **Unchecked Sources** — Name every source category you have NOT consulted. If you skipped it without a reason, go check it.
2. **Stakeholder Gap** — Who has context you don't? Name one thing the project owner or a teammate might know that would change your findings.
3. **Inversion Test** — What would make everything you just found wrong or irrelevant?
4. **Sufficient vs Exhaustive** — Label your output honestly. Most outputs are Sufficient, not Exhaustive. Say so.
5. **Next Vector** — Name one research direction you haven't followed that could yield value.

## Output

```
Status: [Sufficient / Exhaustive]
Unchecked sources: [list or "none identified"]
Stakeholder gap: [what someone might know that you don't / "none identified"]
Inversion result: [what would make this wrong / "no significant inversions found"]
Next vector: [one unexplored direction / "none identified"]
```

## Install

Copy `SKILL.md` to `~/.claude/skills/open-horizons/SKILL.md`.

## Example

```
# Running open-horizons after a skills review

Status: Sufficient
Unchecked sources: largest community skills repo (4,500+ skills not reviewed), Discord community channels
Stakeholder gap: User may know of internal tools that supersede external options
Inversion result: If the team is moving away from MCP-based tools, 6 of the 9 skills I found are irrelevant
Next vector: Check the full skills catalog — only reviewed ~8 of 90+ skills
```

## Category

`meta` — applies to every session and every domain. Not domain-specific.
