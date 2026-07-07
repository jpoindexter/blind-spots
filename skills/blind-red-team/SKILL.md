---
name: blind-red-team
description: Use when a group or a single reasoner has reached consensus quickly, when reviewing a plan everyone likes, when unanimous agreement appears, or when security/robustness of a design must be tested. Applies institutionalized dissent — red teaming, devil's advocacy, and the Israeli "tenth man" doctrine.
---

# Red Team / Tenth Man

## Overview

Consensus is a blind-spot amplifier: Janis's groupthink studies (1972) showed cohesive groups suppress dissent precisely when stakes are highest. The fix is not "be more open-minded" — it's **structural**: assign someone the *job* of attacking the position. Origins: the Vatican's advocatus diaboli (1587), military red teams, and the Israeli intelligence "tenth man" doctrine post-Yom Kippur 1973 — if nine agree, the tenth is *obligated* to argue the contrary, because unanimity itself is evidence of a selection failure somewhere.

**Dissent must be a role, not a personality trait — roles survive social pressure; volunteers don't.**

## When to Use

- Decision reached fast with no serious objections raised
- Plans where everyone stands to benefit from believing it works
- Security, reliability, or adversarial surfaces (the attacker IS a red team; pre-empt them)
- Solo work: you've reviewed your own output and found it good

## The Procedure

1. **Commission the attack explicitly**: "Your job is to make the strongest case this fails/is wrong/gets breached." Success for the red team = finding holes, so finding holes is now loyal behavior.
2. **Give the red team the real artifact** — actual code, actual plan, actual data. Attacking a summary produces summary-grade findings.
3. **Attack the load-bearing claims, not the periphery.** Force the red team to name the plan's 2–3 critical assumptions and target those.
4. **Blue team responds to findings with evidence, not reassurance.** "We considered that" requires showing where.
5. **Record unresolved attacks** as explicit accepted risks with owners.

## Solo/Agent Variant

Spawn a genuinely separate pass (subagent, second model, or a fresh session without your reasoning in context) prompted ONLY to refute — never "review this" (reviews drift to approval), always "find the strongest case this is wrong." A red team that shares your full context inherits your selection bias (see blind-ladder-of-inference).

## Common Mistakes

- Rotating devil's advocacy as a token ritual where the advocate performs mild objections everyone rebuts — Nemeth (2001): *authentic* dissent stimulates better thinking; performed dissent doesn't. The advocate needs real license and real stakes.
- Red-teaming once, patching, and not re-attacking the patch.
- Letting the plan's author play their own red team with full context — that tests memory, not the plan.
- Treating unanimous agreement as strength. Under the tenth-man doctrine it's a trigger condition.
