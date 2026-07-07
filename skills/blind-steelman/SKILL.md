---
name: blind-steelman
description: Use when disagreeing with a position, dismissing an alternative approach, writing a comparison or decision record, or when an opposing view seems obviously wrong. Applies steelmanning and Bryan Caplan's Ideological Turing Test — you understand a position only when its holders would accept your statement of it.
---

# Steelman / Ideological Turing Test

## Overview

The inverse of strawmanning: before rejecting a position, construct its **strongest** version — stronger than its actual advocates managed, if possible. The test of success is Bryan Caplan's **Ideological Turing Test** (2011): state the opposing position such that its genuine holders couldn't distinguish you from one of their own. If you can't pass, you don't yet understand what you're rejecting — you're rejecting your own compressed sketch of it, and whatever the sketch dropped is your blind spot.

**"Obviously wrong" usually means "compressed until wrong." The lossy compression is yours.**

## When to Use

- Dismissing an alternative: library, architecture, strategy, interpretation ("Redux is overkill", "they just don't get it")
- Writing decision records / trade-off comparisons (the rejected option deserves its best case on record)
- Any disagreement where the other side contains smart people — the disagreement itself is evidence you're missing their inputs
- Reviewing your own past decision that now looks obviously right

## The Procedure

1. **Write the position as its smartest advocate would** — their strongest arguments, their evidence, the values and constraints that make it rational. No "some people think…"; write it in first person, from inside.
2. **Run the Turing test**: would an actual proponent sign off on your rendering? If reachable, literally ask. If not, compare against the best published advocacy — did you include their best points or only the quotable weak ones?
3. **Locate the crux**: with the steelman standing, find the *specific* premise where you actually diverge (a fact? a value weight? a predicted outcome?). Disagreements shrink to cruxes; blind spots live in the difference between the crux and what you originally attacked.
4. **Then judge.** Rejecting a steelman you built is informative. Rejecting a strawman is noise.

## Quick Reference

| Tell | Fix |
|---|---|
| "They just want / they just don't understand…" | No "just" — write their full model |
| Can state your side's evidence but not theirs | You have a conclusion, not an understanding |
| Rejected option gets 1 line in the ADR | Give it its best paragraph before rejecting |
| Their position seems to have no upside | You've compressed it to caricature — decompress |

## Common Mistakes

- Steelmanning into a position they don't hold ("what you SHOULD be arguing is…") — that fails the Turing test too; fidelity first, charity second.
- Performing the steelman then judging on the original strawman anyway. The verdict must cite the steelman's crux.
- Reserving steelmanning for opponents' views only. Steelman the option YOU rejected last month before building on that rejection.
