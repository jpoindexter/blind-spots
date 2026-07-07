---
name: blind-inversion
description: Use when a problem is stuck when approached directly, when defining success criteria, when designing for reliability/safety, or when a goal is vague ("make it good"). Applies Jacobi's inversion as practiced by Charlie Munger — solve problems backward: avoid the failure instead of chasing the success.
---

# Inversion

## Overview

Carl Gustav Jacobi's maxim "*man muss immer umkehren*" (invert, always invert), operationalized by Charlie Munger: many problems are easier solved backward. Instead of "how do I achieve X?", ask "**what would guarantee NOT-X — and how do I avoid all of that?**" Munger: "All I want to know is where I'm going to die, so I'll never go there." Forward thinking samples from paths to success (huge, fuzzy space); inversion enumerates paths to failure (smaller, sharper space) — and failure paths are where blind spots hide, because nobody was looking there.

## When to Use

- Vague goals: "make this fast/clean/reliable/good" → invert to the concrete badness to eliminate
- Stuck on a direct approach
- Designing guardrails, reviews, checklists, on-call runbooks
- Evaluating a decision: before asking "why will this work?", ask "what would make this a disaster?"

## The Procedure

1. **State the goal**, then flip it: write the anti-goal explicitly ("users churn immediately", "the migration corrupts data", "nobody can read this code").
2. **Enumerate reliable ways to achieve the anti-goal.** Be a competent saboteur: how would you *ensure* churn / corruption / unreadability? Concrete mechanisms, not categories.
3. **Audit the current plan against the sabotage list.** Every mechanism the plan doesn't block is a finding.
4. **Convert to avoidance rules.** Often the entire deliverable: a short "never do these" list beats a long "try to do these" list.

## Worked Example

Goal: "onboarding should convert well" (fuzzy) → Invert: "how would I guarantee signups abandon?" → require credit card before value, 12-field form, confirmation email that lands in spam, empty state with no next action → check the actual flow for each → three concrete fixes, found in minutes.

## Common Mistakes

- Inverting the goal but not the *thinking* — listing generic risks instead of asking "how would I deliberately cause this?" The saboteur stance is the tool.
- Stopping at avoidance when the direct path was fine — inversion complements forward planning, it doesn't replace it.
- Abstract anti-goals ("bad UX"). Invert to mechanisms you could actually execute; if you couldn't do it on purpose, you can't check for it.
