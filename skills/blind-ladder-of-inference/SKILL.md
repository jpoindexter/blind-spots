---
name: blind-ladder-of-inference
description: Use when a conclusion feels obvious, when debugging why two people see the same facts differently, when "clearly" or "obviously" appears in reasoning, or when tracing how a belief was formed from raw data. Applies Chris Argyris's Ladder of Inference.
---

# Ladder of Inference

## Overview

Chris Argyris (Harvard, 1970s; popularized in Senge's *The Fifth Discipline*): between raw observable data and the action you take, you climb an invisible ladder —

1. Observable data (everything available)
2. **Selected** data (what you noticed)
3. Meanings added (interpretation)
4. Assumptions made
5. Conclusions drawn
6. Beliefs adopted
7. Action taken

Two blind spots: the climb is instant and unconscious, and the **reflexive loop** — your existing beliefs control which data you select at step 2, so every trip up the ladder reinforces the last one. You experience your conclusions as "just seeing what's there."

## When to Use

- "Obviously the bug is in X" / "clearly the user wants Y" — obviousness is a ladder smell
- Disagreements where both sides cite "the facts"
- Debugging a wrong prior conclusion: find which rung failed
- Reviewing an inherited diagnosis before acting on it

## The Procedure (climb down)

1. **State the conclusion**, then descend: what assumptions is it standing on? What interpretation? What *selected* data?
2. **Recover the discarded data**: what did you NOT select? (The log lines you skimmed past, the passing tests, the disconfirming user quote.) The selection step is where most blind spots live.
3. **Test the load-bearing rung**: for each assumption, ask "is this observable, or added?" Convert added meaning back into a checkable question.
4. **Make your ladder visible to others** ("I'm concluding X because I noticed A and assumed B — what am I missing?") and ask for theirs. Argyris: advocacy paired with inquiry.

## Quick Reference

| Rung smell | Check |
|---|---|
| "Obviously / clearly / of course" | Descend — which rung makes it obvious? |
| Conclusion arrived instantly | Selection bias at rung 2 — list unselected data |
| Same data, different conclusions | Compare ladders rung by rung, not conclusions |
| Belief older than current evidence | Reflexive loop — re-select from raw data |

## Common Mistakes

- Debating at the conclusions rung ("you're wrong") instead of comparing selected data. Conclusions can't be reconciled; ladders can.
- Climbing down one rung and stopping — assumptions usually stack 2–3 deep.
- Treating your selected data as "the data." Selection already happened before you noticed anything.
