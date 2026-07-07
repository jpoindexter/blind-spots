---
name: blind-premortem
description: Use before committing to a plan, launch, migration, deploy, estimate, or architecture — especially when the team is confident and aligned. Applies Gary Klein's premortem (prospective hindsight): assume the plan already failed, then explain why.
---

# Premortem

## Overview

Gary Klein (2007, *HBR*): before executing a plan, announce "**it is [future date]; the plan failed completely — spectacularly**. Take 3 minutes and write the history of that failure." This is prospective hindsight: Mitchell, Russo & Pennington (1989) found that assuming an outcome is *certain* (not merely possible) increases the ability to generate correct reasons for it by ~30%. It also legitimizes dissent — the confident room is now being asked FOR failure stories, so raising one is contribution, not disloyalty.

**"What could go wrong?" invites optimism. "It went wrong — why?" invites memory.**

## When to Use

- Just before locking a plan, schedule, or design (after planning, before commitment)
- Team/self fully aligned and confident — the exact condition that suppresses doubts
- Irreversible or expensive steps: migrations, launches, deletions, announcements
- NOT as a plan-killer — output feeds mitigation, not cancellation by default

## The Procedure

1. **Set the frame as certainty**: "It's six months out. The project failed so badly it's a case study. What happened?" — not "what might go wrong."
2. **Generate independently first.** Each participant (or each pass, if solo: run separate passes for people/tech/external/process causes) writes failure reasons alone before sharing — prevents anchoring on the first story.
3. **Collect ALL reasons, no rebuttals allowed** during collection. Defending the plan mid-premortem kills the exercise.
4. **Rank by expected damage × plausibility.** Pick the top 2–3.
5. **For each: mitigation, early-warning signal, or explicit accepted-risk entry.** A premortem that changes nothing was theater.

## Solo/Agent Variant

Run 4 framed passes over the failed-future prompt: (a) a human/user cause, (b) a technical cause, (c) an external/dependency cause, (d) a "the plan was executed perfectly and still failed" cause — the last one catches wrong-goal blind spots.

## Common Mistakes

- Softening to "what are the risks?" — that's a risk review, and it reliably produces the already-known list. The certainty framing is the mechanism; keep it.
- Only generating failures you already have mitigations for (comfort-zone dredging). At least one reason must be *new information*.
- Running it after commitment as a formality. Premortem exists to alter the plan while alteration is cheap.
- Treating a scary premortem as reason to abandon the plan — its job is to make the plan survivable, not to veto it.
