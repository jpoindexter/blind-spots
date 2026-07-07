---
name: blind-johari-window
description: "Use when assessing self-knowledge, team dynamics, personal strengths/weaknesses, \"how do others see this\", or when someone is confident about themselves without external input. Applies the Johari Window (Luft & Ingham, 1955) to locate what others see that you cannot."
---

# Johari Window

## Overview

Joseph Luft & Harrington Ingham (1955): all knowledge about a person (or project, or codebase) splits on two axes — known/unknown to self × known/unknown to others — giving four quadrants:

| | Known to self | Unknown to self |
|---|---|---|
| **Known to others** | Open (Arena) | **Blind Spot** |
| **Unknown to others** | Hidden (Façade) | Unknown |

**The Blind quadrant can only shrink one way: feedback from others. No amount of introspection moves it.** The Unknown quadrant shrinks only through new shared experience (trying things neither party has seen).

## When to Use

- Self-assessments: "am I good at X", "is my code readable", "is this design clear"
- Team friction where each side is confident the other is the problem
- Any confidence about how one's work lands with others, formed without asking others

## The Procedure

1. **Map the four quadrants for the target.** Force at least one concrete entry per quadrant. An empty Blind quadrant means you haven't asked anyone — not that it's empty.
2. **Name the feedback sources** that could shrink the Blind quadrant (user, reviewer, test suite, analytics, a second model). Data from others is the only tool that works here.
3. **Pick the cheapest source and actually consult it** before finalizing the assessment.
4. **For the Unknown quadrant**, name one experiment that would expose new territory.

## Agent Application

For an AI agent, "others" = the user, tests, runtime output, logs, a second reviewer. Any claim about how output will be received (readability, clarity, usefulness) sits in the Blind quadrant until an external source confirms it.

## Common Mistakes

- Filling the Blind quadrant with guesses about what others think — that's the Open quadrant wearing a costume. Blind entries must come FROM others.
- Treating disclosure (shrinking Hidden) as the fix when the problem is Blind. Talking more ≠ learning more.
- Asking only people who share your context — they share your blind spots too (see blind-curse-of-knowledge).
