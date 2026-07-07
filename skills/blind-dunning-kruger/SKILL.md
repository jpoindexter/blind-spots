---
name: blind-dunning-kruger
description: "Use when operating in an unfamiliar domain, when something \"looks right\" but hasn't been verified, when confidence is high without external checks, or when evaluating one's own competence at a task. Applies Kruger & Dunning (1999) — the skills needed to perform are the skills needed to judge performance."
---

# Dunning-Kruger — The Double Curse

## Overview

Kruger & Dunning (1999, *JPSP*): poor performers overestimate themselves not because they're arrogant, but because **the same skills required to produce a right answer are required to recognize one**. Incompetence carries a double curse — you fail AND you lack the ability to detect the failure. Corollary (often missed): top performers *under*estimate their relative standing because they assume tasks easy for them are easy for everyone (false consensus).

**In an unfamiliar domain, your error-detector is broken in exactly the places your generator is.**

## When to Use

- Working outside your (or the codebase's) established competence: new language, framework, domain, API
- Output "looks right" and you're about to ship on that signal
- Estimating your own accuracy: "I'm confident this is correct"
- Reviewing an expert's work in their domain, or a novice's confident claim

## The Procedure

1. **Rate domain familiarity honestly** (worked in it repeatedly / adjacent / new). New or adjacent → treat internal confidence as noise.
2. **Swap internal checks for external ones**: run the code, read the actual docs, execute the test, look up the current API. The "looks right" signal is only calibrated where competence already exists.
3. **Assume specific error types you can't see**: in new domains list the standard beginner traps (ask: "what do novices in X always get wrong?") and check each explicitly.
4. **Invert for expertise**: where you ARE strong, don't assume the reader/user shares it — spell out what feels obvious (see blind-curse-of-knowledge).

## Quick Reference

| Signal | Meaning |
|---|---|
| High confidence + unfamiliar domain | Double curse zone — verify externally |
| High confidence + familiar domain | Usable, still sample-check |
| "This was easy" in your specialty | Others likely find it hard — document more |
| Can't articulate how you'd detect an error | You can't detect it — get an external check |

## Common Mistakes

- Compensating with humility theater ("I might be wrong") while still shipping unverified work. The fix is verification, not hedging.
- Believing awareness of Dunning-Kruger exempts you from it (that's blind-bias-blind-spot).
- Applying it only to others. The finding is about the person doing the judging — currently you.
