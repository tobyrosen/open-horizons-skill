---
name: open-horizons
description: "Pre-closure checkpoint for research, capability assessment, and knowledge-gathering tasks. Use before declaring any research complete, any skill review done, any gap analysis finished, or any 'I've looked at everything' statement. Triggers when you feel ready to wrap up — that feeling is the signal to run this skill first."
category: meta
---

# Open Horizons

The pre-closure checkpoint. Run this before declaring any research, capability scan, or gap analysis done.

The feeling of being ready to close is the trigger. That sense of "I've covered the main things" is exactly when this skill activates.

---

## The Core Problem

Agents anchor on the resources in front of them. When given a list of 18 URLs, the agent analyzes those 18 and declares the work done — without asking whether better resources exist elsewhere. When given a topic, the agent finds answers and stops — without asking what questions it didn't think to ask.

This produces outputs that are correct within a narrow frame and incomplete outside it.

The pattern has a name: **closure bias**. It is not laziness. It is a systematic tendency to minimize open loops. The fix is a forced protocol that re-opens loops before they close.

---

## When to Run This Skill

Run before any of these statements:

- "I've looked at the main options"
- "There aren't any skills for this"
- "That covers it"
- "Ready to move on"
- "Nothing else comes to mind"
- "The analysis is complete"
- "Done with the research"

If you are about to say something like these, run this skill first.

Do NOT wait for the user to invoke it. This skill is self-triggered.

---

## The Five Checks

Work through all five before closing. Do not skip.

### Check 1: Unchecked Sources

Name every source category you have NOT consulted.

Examples of source categories:
- GitHub repos not in the list you were given
- Community forums (Reddit, Discord, Slack communities)
- Official documentation
- Competitor or adjacent-domain tools
- The user's own history and past decisions
- Teammates or team members you haven't asked
- Primary sources vs secondary sources you've been using

For each unchecked category: is there a reason you skipped it, or did you just not think of it?

If you skipped it without a reason, go check it before closing.

### Check 2: The Stakeholder Gap

Who has context you don't?

The person who assigned the task may know things about scope, direction, and constraints that are not in any file you can read. Teammates know the current state of their own work.

Before closing: name one thing the project owner or a teammate might know that would change your findings. If you can name it, surface it rather than assuming your findings are complete.

### Check 3: The Inversion Test

Ask: what would make everything you just found wrong or irrelevant?

Examples:
- "The skills I found assume we're growing clients. The user said they're shifting away from clients. How many of these skills are now irrelevant?"
- "The skills I found require MCPs we don't have. How many of these actually work in our environment?"
- "I searched for existing skills. But what if the right answer is to build something new that doesn't exist yet?"

If the inversion surfaces something important, update the findings before closing.

### Check 4: Sufficient vs Exhaustive

Label your output honestly — it is one of these two:

**Sufficient:** Covers the highest-value items. Known gaps exist but are low-priority or out of scope. Good enough to act on.

**Exhaustive:** Comprehensive coverage. Would require significant additional work to find anything this missed.

Most outputs are Sufficient, not Exhaustive. That is fine — but say so explicitly. "This covers the main options; I have not reviewed the largest community skills repository (4,500+ skills) or several domain-specific collections" is an honest, useful statement. "Done" is not.

### Check 5: The Next Vector

Before closing, name one research direction you haven't followed that could yield value.

You do not have to follow it now. But name it. Log it. If it's worth following, propose it.

If you genuinely cannot name one, the work may actually be exhaustive. That is rare.

---

## Output Format

After running the five checks, close with:

```
Status: [Sufficient / Exhaustive]
Unchecked sources: [list or "none identified"]
Stakeholder gap: [what the project owner or a teammate might know / "none identified"]
Inversion result: [what would make this wrong / "no significant inversions found"]
Next vector: [one unexplored direction / "none identified"]
```

This does not need to be long. Four lines is fine. The point is forcing the honest accounting.

---

## The Failure Mode This Skill Prevents

**Without this skill:**
Agent analyzes 8 of 90+ available skills from a repo, finds 3 to install, reports "done." 90+ skills remain unreviewed. No gaps flagged.

**With this skill:**
Agent completes the 8-skill review, runs this check, names "this repository has 90+ total skills, I only looked at ~8 of them" as an unchecked source, names "a larger community repository has 4,500+ I haven't touched" as a next vector, and labels the output "Sufficient — not Exhaustive." The user can then decide whether to push further or close.

---

## Notes

This skill applies to every session. It is not domain-specific.

It is most critical for:
- Capability assessments and skill reviews
- Research tasks with open-ended scope
- Gap analyses
- Any task where "I don't know what I don't know" is the real risk

It is less critical for:
- Mechanical execution tasks (deploy this, move this file, create this task)
- Tasks with fully defined scope
- Tasks where you received explicit stop criteria from the user
