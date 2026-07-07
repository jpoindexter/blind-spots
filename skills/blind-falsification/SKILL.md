---
name: blind-falsification
description: "Use when testing a hypothesis, debugging, validating a fix, designing experiments or test suites, or when checks keep passing. Applies Popper's falsification and Wason's 2-4-6 task — a test that can't fail isn't a test, and confirming instances prove little."
---

# Falsification

## Overview

Karl Popper (*Logik der Forschung*, 1934): a claim earns credibility only from surviving attempts to **refute** it — confirming instances are cheap and unbounded. Wason's 2-4-6 experiment (1960) showed the default human strategy: given a rule to discover, people propose only sequences their hypothesis says are valid, receive "yes" after "yes", and announce the wrong rule with confidence. They never propose a sequence their hypothesis says should FAIL.

**The blind spot: a green test you designed to pass tells you almost nothing. The information is in the test designed to fail.**

## When to Use

- Verifying a bug fix ("it works now")
- Any hypothesis about system behavior, user behavior, or root cause
- Writing tests for new code
- A validation process that has never rejected anything

## The Procedure

1. **State the claim so it CAN fail**: "the fix works" → "with input X the output is Y, and with pre-fix conditions Z it would have errored." Unfalsifiable claims ("should be more robust") get rewritten or discarded.
2. **Design the killer test first**: what observation would prove this claim *wrong*? Run that, not (only) the demo of it working. For a bug fix: reproduce the original failure, confirm it's gone, AND confirm the test fails again when the fix is reverted.
3. **Probe the boundary (2-4-6 lesson)**: test cases your hypothesis says should FAIL — negative cases, edge inputs, the adjacent case that shouldn't work. If everything you try passes, you're only sampling inside your hypothesis.
4. **Weight survival, not confirmation count**: 10 confirming runs < 1 serious refutation attempt survived. Track which it was.

## Quick Reference

| Situation | Falsification move |
|---|---|
| "Fix verified — it works now" | Revert fix → test must fail → unrevert |
| Hypothesis about the root cause | Predict something it forbids; check that |
| All tests green | Add the test that SHOULD fail (wrong input, boundary) |
| "Can't reproduce" | Define what observation would count as reproduced |

## Common Mistakes

- Running the happy path 5 times and calling it verification — that's Wason's trap with extra steps.
- Writing tests after the code that assert whatever the code currently does (confirmation encoded as CI).
- Protecting a hypothesis with ad-hoc patches each time it's contradicted ("it only fails when…") — Popper's mark of pseudo-science; two patches means the hypothesis is dead.
- Demanding falsification only of claims you dislike (see blind-consider-the-opposite).
