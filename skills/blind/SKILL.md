---
name: blind
description: "Use when the user invokes /blind (full sweep of all frameworks against the current context) or /blind quick (routed 2-4 framework pass), asks \"what am I missing\", \"what are my blind spots\", \"poke holes in this\", \"what could go wrong\", or before committing to a plan, decision, architecture, launch, or estimate. Dispatcher that runs a structured blind-spot audit using the companion blind-* framework skills."
---

# Blind — Blind-Spot Audit Dispatcher

## Overview

You cannot see your own blind spots by introspecting harder — that is what makes them blind spots (Pronin's introspection illusion). This skill routes to real, research-backed frameworks that surface them from the outside: from data, from others, from inversion, from base rates.

**Core principle: enrich the information environment; never trust "it looks right."**

## How to Run an Audit

**Resolve the target first**: an explicit argument if given; otherwise the active work in the current conversation (the plan/code/decision most recently under discussion). State the resolved target in one line before auditing.

### Default mode — full sweep (bare `/blind` or `/blind <target>`)

Run **ALL 16 companion blind-* framework skills** against the target.

1. **Fan out in parallel where the agent supports subagents** (e.g. the Agent tool): one subagent per framework, each given (a) the full text of that framework's SKILL.md, (b) the target, (c) the instruction to return only evidence-backed findings or an explicit "no finding". This keeps coverage from costing depth. No subagent support → run the frameworks sequentially yourself; do not skip any.
2. **Load each skill's actual procedure** — via the Skill tool where installed, else read its SKILL.md from this skill set. The dispatcher carries no framework procedures itself; do not improvise a framework from memory. A framework unavailable → name it in the Residual.
3. **Merge and dedupe**: the same blind spot surfaced by several frameworks is ONE finding tagged with all of them (convergence raises its severity).
4. **Report findings ranked by severity** = expected damage × plausibility (premortem's rubric, applied audit-wide).
5. **End with the residual**: what the audit could NOT check (that list is itself a finding). Frameworks that returned "no finding" are listed there in one line — a null from a self-directed audit is weak evidence, not clearance.

### Quick mode — `/blind quick <target>`

Time-boxed pass: pick 2–4 frameworks from the routing table below (rows list frameworks in priority order; a single-framework row may run alone — the 2–4 rule caps, it doesn't force padding; target matches multiple rows → use the row for the *primary object*, then pull one framework from the secondary row). Steps 2–5 as above.

## Routing Table (quick mode)

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

Ambiguous target in quick mode → default to blind-premortem + blind-inversion + blind-unknown-unknowns, or escalate to the full sweep.

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
