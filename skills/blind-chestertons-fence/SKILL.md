---
name: blind-chestertons-fence
description: "Use before deleting code, removing a check, simplifying a process, dropping a config flag, or removing anything that \"serves no purpose\" — especially in unfamiliar or legacy systems. Applies Chesterton's Fence (G.K. Chesterton, 1929): don't remove it until you know why it's there."
---

# Chesterton's Fence

## Overview

G.K. Chesterton (*The Thing*, 1929): a reformer finds a fence across a road and says "I don't see the use of this; let us clear it away." The intelligent reformer answers: "**If you don't see the use of it, I certainly won't let you clear it away. Go and find out the use of it — then I may allow you to destroy it.**"

The blind spot is asymmetric visibility: a thing's *cost* is visible now; its *purpose* may only be visible under conditions you haven't seen (the leap-year bug, the one enterprise client, the race that happens under load). "I can't see a reason" is a statement about your visibility, not about the reason.

## When to Use

- Deleting "dead" code, "redundant" checks, "pointless" retries, "legacy" branches
- Simplifying a process/workflow you didn't design
- Removing config flags, feature gates, timeouts, sleeps, locks, defensive copies
- Onboarding into a codebase and itching to clean up

## The Procedure

1. **Assume competence**: someone paid a cost to build this. Start from "this solved a problem" — the burden of proof is on removal.
2. **Excavate the origin**: `git log -p --follow` the lines, read the commit message, linked issue, PR discussion. Search the tracker for the filename. Ask the author if reachable.
3. **Reconstruct the trigger condition**: what input/load/date/client would exercise this? If you can name it, test whether it's still possible.
4. **Then decide with evidence**:
   - Reason found + still applies → keep (document it inline so the next person doesn't repeat this).
   - Reason found + obsolete → remove, citing the evidence in the commit.
   - No reason findable after real excavation → removable, but behind the cheapest safety net (flag, revertable commit, canary) — absence of evidence was your judgment call.

## Quick Reference

| Tell | Move |
|---|---|
| "This does nothing" | `git log --follow` before delete |
| "Weird workaround, probably cargo cult" | Find the bug it worked around; check if fixed upstream |
| Magic sleep/retry/limit | Reconstruct the failure it absorbs |
| "Nobody knows why this exists" | That's a documentation task AND a removal blocker |

## Common Mistakes

- Treating the principle as "never remove anything" — Chesterton's point is *sequencing*: understand, THEN remove freely. Fence-worship is the opposite failure.
- Excavating for 30 seconds, finding nothing, and proceeding as if cleared. The search must be proportional to the blast radius.
- Removing five fences in one commit — when something breaks, you can't tell which fence held the goat.
