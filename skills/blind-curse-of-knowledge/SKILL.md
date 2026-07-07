---
name: blind-curse-of-knowledge
description: Use when writing docs, error messages, onboarding, tutorials, API designs, UX copy, or teaching — or when something you built seems self-explanatory. Applies the curse of knowledge (Camerer, Loewenstein & Weber 1989; Newton's tappers-and-listeners 1990): expertise makes you unable to simulate not-knowing.
---

# Curse of Knowledge

## Overview

Camerer, Loewenstein & Weber (1989, *JPE*): once you know something, you **cannot accurately simulate the mind of someone who doesn't** — better-informed traders couldn't ignore their extra information even when profit depended on it. Elizabeth Newton (1990): "tappers" tapping songs predicted listeners would name the tune ~50% of the time; actual rate: **2.5%**. The tapper hears the melody in their head; the listener hears knocking.

**Your design/docs/API are the taps. You hear the melody. The user hears knocking — and you cannot hear the knocking anymore.**

## When to Use

- Writing documentation, READMEs, error messages, commit messages, tutorials
- Designing APIs, CLIs, onboarding flows, empty states
- "It's self-explanatory" / "users will figure it out" / "the name makes it obvious"
- Expert reviewing beginner-facing material (worst-case pairing)

## The Procedure

1. **Inventory the invisible prerequisites**: list what a reader must already know for this to make sense (vocabulary, mental model, context, prior steps). The items you almost didn't list are the curse — they've become "not knowledge, just reality" to you.
2. **Rebuild from the reader's actual state**, not yours-minus-a-bit: what do they see FIRST, what will they try FIRST, what does this error message mean if you don't know the internals?
3. **Test on a real non-knower** — the only reliable decurse. A newcomer attempting the task cold beats ten expert reviews (see blind-johari-window: this is Blind-quadrant data). No human available → a fresh model session with zero context is a cheap proxy.
4. **Write to the failure point**: wherever the non-knower stalled, that's where the melody was silently playing in your head. Fix that spot, re-test.

## Quick Reference

| Curse tell | Fix |
|---|---|
| "Obviously / simply / just" in docs | Each one hides a prerequisite — unpack or delete |
| Error message names internal state | Rewrite from the user's visible world + next action |
| Doc explains what it does, not when/why you'd want it | You know the context; the reader doesn't — add it |
| "No one asked questions" | Silence ≠ clarity (see blind-survivorship-bias — confused users leave) |

## Common Mistakes

- Simulating a beginner by dumbing down your view — you can't unknow; get an actual outsider (the whole finding is that simulation fails).
- Testing on colleagues who share your context. They hear the same melody.
- Adding MORE text as the fix. The curse usually hides missing *prerequisite framing*, not missing detail — one sentence of "what this is and when you need it" beats three paragraphs of how.
