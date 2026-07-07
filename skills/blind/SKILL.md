---
name: blind
description: "Use when the user invokes /blind, asks \"what am I missing\", \"what are my blind spots\", \"poke holes in this\", \"what could go wrong\", or before committing to a plan, decision, architecture, launch, or estimate. Dispatcher that runs a structured blind-spot audit using the companion blind-* framework skills."
---

# Blind — Blind-Spot Audit Dispatcher

## Overview

You cannot see your own blind spots by introspecting harder — that is what makes them blind spots (Pronin's introspection illusion). This skill routes to real, research-backed frameworks that surface them from the outside: from data, from others, from inversion, from base rates.

**Core principle: enrich the information environment; never trust "it looks right."**

## How to Run an Audit

1. **Classify the target** — what is being audited?
2. **Pick 2–4 frameworks** from the routing table (never all; depth beats coverage). Rows list frameworks in priority order — apply the first ones first. A single-framework row (e.g. Chesterton's Fence) may run alone; the 2–4 rule caps, it doesn't force padding. Target matches multiple rows → use the row for the *primary object* (a plan with a deadline is still a plan), then pull one framework from the secondary row if it isn't already covered.
3. **Load each routed skill and follow its procedure** — via the Skill tool where installed, else read its SKILL.md from this skill set. The dispatcher carries no framework procedures itself; do not improvise a framework from memory. Routed skill unavailable → say so in the Residual and substitute the nearest row-mate.
4. **Report findings ranked by severity** = expected damage × plausibility (premortem's rubric, applied audit-wide), each tagged with the framework that surfaced it.
5. **End with the residual**: what the audit could NOT check (that list is itself a finding).

## Routing Table

| Target | Frameworks (in order) |
|---|---|
| Plan / project / launch | blind-premortem, blind-outside-view, blind-unknown-unknowns |
| Decision / choice between options | blind-inversion, blind-consider-the-opposite, blind-red-team |
| Belief / conclusion / diagnosis | blind-falsification, blind-consider-the-opposite, blind-bias-blind-spot |
| Estimate / forecast / deadline | blind-outside-view, blind-calibration, blind-premortem |
| Data / metrics / evidence | blind-survivorship-bias, blind-falsification |
| Argument / position / debate | blind-steelman, blind-red-team |
| Legacy code / existing process ("why is this here?") | blind-chestertons-fence |
| Self-assessment / skill judgment | blind-dunning-kruger, blind-johari-window, blind-bias-blind-spot |
| Docs / teaching / API design / UX copy | blind-curse-of-knowledge |
| Reasoning chain / "obviously X" | blind-ladder-of-inference |

Ambiguous target → default to blind-premortem + blind-inversion + blind-unknown-unknowns.

## Output Format

```
## Blind-Spot Audit: [target]
Frameworks applied: [list]

### Findings (severity-ranked)
1. **[finding]** — via [framework].
   Evidence: [...]
   Mitigation: [...]

### Residual (what this audit could not see)
- [unchecked assumption / missing data / voice not in the room]
```

## Rules

- **Never skip the residual section.** An audit that claims completeness is itself a blind spot.
- **Findings need evidence or a test**, not vibes. "Might be risky" is not a finding; "fails when X because Y" is.
- **If all frameworks return nothing, say so** — and flag that null results from self-audit are weak evidence (you are still the one looking).

## Common Mistakes

- Running every framework shallowly instead of 2–4 deeply.
- Auditing the plan you wish you had, not the actual artifact/files/data.
- Treating the audit as done when it confirms the existing plan — confirmation is a smell, not a pass.
