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

1. **Fan out in parallel where the agent supports subagents** (e.g. the Agent tool): one subagent per framework, each given (a) the full text of that framework's SKILL.md, (b) the target, (c) a **ground-truth brief**, (d) the instruction to return only evidence-backed findings or an explicit "no finding". This keeps coverage from costing depth. No subagent support → run the frameworks sequentially yourself; do not skip any.
   - **The ground-truth brief** (dispatcher computes it once, before fan-out): the canonical numbers about the target (counts, sizes, dates — measured, not recalled), what was already verified and *where that evidence lives* (subagents cannot see the conversation; without this they re-litigate or deny verification that happened), and the **baseline** — what was already true before the audited change. Lenses attack the brief; they don't get to rediscover it wrong.
   - **Subagents are read-only.** Say it explicitly, and also warn them: any files that appear in shared scratch space mid-audit may be artifacts written by a sibling lens, not evidence about the target. Citing a sibling's helper script as "the author's known-bug notes" is cross-agent contamination — a documented failure of this skill.
2. **Load each skill's actual procedure** — via the Skill tool where installed, else read its SKILL.md from this skill set. The dispatcher carries no framework procedures itself; do not improvise a framework from memory. A framework unavailable → name it in the Residual.
3. **Merge and dedupe**: the same blind spot surfaced by several frameworks is ONE finding tagged with all of them. Before treating this as convergence, check whether the frameworks cite the *same* underlying evidence/quote or genuinely *different* evidence. Same subagent model + same target text + differently-named lenses can produce correlated pattern-matching, not independent corroboration — only raise severity for the latter; label the former "same-model repetition" and leave severity unchanged.
   - **Fact-check before ranking.** Any finding that contradicts the ground-truth brief or documented run output gets re-verified by the dispatcher against the primary source (the file, the command, the log) before it enters the report. Lenses drift on numbers — three lenses counting the same thing will return three counts; the dispatcher owns the canonical number and corrects findings to it. Debunked findings go in a short "debunked" list (they show the failure mode is live), not in the findings.
   - **Baseline attribution.** Every finding must state whether the defect was *caused by the audited change* or *predates it*. Pre-existing problems are reportable — often the most valuable output — but a pre-existing problem attributed to the change is the most common false HIGH this skill produces.
4. **Report findings ranked by severity** = expected damage × plausibility (premortem's rubric, applied audit-wide, qualitative — not a computed number). State the one-clause rationale for each severity call, not just the label.
5. **End with the residual**: what the audit could NOT check (that list is itself a finding). Frameworks that returned "no finding" are listed there in one line. Apply the self-audit caveat to *every* finding, not just nulls — "evidence-backed" is still self-reported by the same run until someone spot-checks the cited quote against the real target.
6. **Deliver as a file, not a chat wall of text.** Write the report to a markdown file (name it so repeat audits don't collide, e.g. `blind-audit-<target-slug>-<date>.md`). In Claude Code, additionally render it via the Artifact tool as HTML for a scannable, severity-ranked view — long full-sweep output read as an undifferentiated wall of text is a known failure mode of this skill.
7. **This audit informs a human decision — it does not auto-approve, auto-fix, or auto-block anything.** Findings are inputs to the reader's judgment.

### Quick mode — `/blind quick <target>`

Time-boxed pass: pick 2–4 frameworks from the routing table below (never all — depth beats coverage; rows list frameworks in priority order; a single-framework row may run alone — the 2–4 rule caps, it doesn't force padding; target matches multiple rows → use the row for the *primary object*, then pull one framework from the secondary row). Steps 2–7 as above.

## Routing Table (quick mode)

| Target | Frameworks (in order) |
|---|---|
| Plan / project / launch | blind-premortem, blind-outside-view, blind-unknown-unknowns |
| Decision / choice between options | blind-inversion, blind-consider-the-opposite, blind-red-team |
| Architecture / "why does this exist" design choice | blind-chestertons-fence, blind-inversion, blind-outside-view |
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

Write this to a file (and, in Claude Code, also render it as an HTML artifact — see Rule 6). Do not just print it into the conversation.

```
## Blind-Spot Audit: [target]
Frameworks applied: [list] — [N] independent findings, [M] same-model-repetition notes

### Findings (severity-ranked)
1. **[finding, one plain-English sentence — no framework jargon in the headline]** (via [framework]; convergent with [framework2] only if evidence differs, else "same-model repetition, not corroboration").
   Evidence: [...]
   Severity: [low/med/high] — [one clause: expected damage, one clause: plausibility]
   Mitigation: [...]

### Residual (what this audit could not see)
- [unchecked assumption / missing data / voice not in the room — specific, not a hedge]
- Self-audit caveat: this audit graded its own evidence; nothing here was spot-checked by an outsider or a second model.
```

## Rules

- **Never skip the residual section.** An audit that claims completeness is itself a blind spot.
- **Findings need evidence or a test**, not vibes. "Might be risky" is not a finding; "fails when X because Y" is.
- **If all frameworks return nothing, say so** — and flag that null results from self-audit are weak evidence (you are still the one looking).
- **Findings must be legible without prior knowledge of the framework's name.** Lead with plain English; the framework name is a citation, not the headline. A reader who's never heard of the Johari Window should still be able to act on the finding.
- **Deliver as a file/artifact, not a chat dump.** See Rule 6 above.

## Common Mistakes

- Running every framework shallowly instead of 2–4 deeply.
- Auditing the plan you wish you had, not the actual artifact/files/data.
- Treating the audit as done when it confirms the existing plan — confirmation is a smell, not a pass.
- Misattributing pre-existing state to the audited change — measure the baseline first; it's the most common false HIGH (observed: three lenses blamed a merge for 11 GB of repo clones that predated it).
- Trusting lens arithmetic — different lenses return different counts for the same thing; the dispatcher recomputes canonical numbers from the primary source (observed drift: 168/176/182/226 for one count).
- Letting subagents write files: sibling lenses then cite those artifacts as target evidence (observed: two lenses cited a helper script another lens had just written, calling it the author's "known-bug notes").
- Omitting verification evidence from the fan-out brief — lenses that can't see the conversation will report "verification never happened" for verification that happened in-session.
