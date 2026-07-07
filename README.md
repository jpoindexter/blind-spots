# blind-spots

**Agent skills for finding what you can't see.** 17 skills, each built on a real, citable framework from psychology, decision science, or engineering practice — packaged in the open [Agent Skills](https://agentskills.io) format so they install into Claude Code, Codex, Gemini CLI, Copilot, or any agent that reads `SKILL.md`.

The premise (Pronin's introspection illusion, Dunning's self-insight research): you cannot detect your own blind spots by thinking harder — detection requires changing the *information environment*: data from others, inverted questions, base rates, adversarial passes. Each skill operationalizes one such move.

## The `/blind` command

`blind` is the dispatcher. Invoke it on any plan, decision, belief, estimate, dataset, or argument and it routes to 2–4 of the framework skills below, runs them deeply, and reports severity-ranked findings **plus the residual — what the audit could not check**.

```
/blind this migration plan
/blind — what am I missing in this pricing decision?
```

## The skills

| Skill | Framework | Source |
|---|---|---|
| `blind` | Audit dispatcher | — |
| `blind-johari-window` | Johari Window | Luft & Ingham, 1955 |
| `blind-dunning-kruger` | Double curse of incompetence | Kruger & Dunning, 1999 |
| `blind-bias-blind-spot` | Bias blind spot / introspection illusion | Pronin, Lin & Ross, 2002 |
| `blind-ladder-of-inference` | Ladder of Inference | Argyris, 1970s |
| `blind-premortem` | Premortem / prospective hindsight | Klein, 2007; Mitchell et al., 1989 |
| `blind-inversion` | Inversion | Jacobi; Munger |
| `blind-outside-view` | Reference class forecasting | Kahneman & Lovallo, 1993; Flyvbjerg, 2006 |
| `blind-red-team` | Red team / tenth man doctrine | Janis, 1972; IDF post-1973 |
| `blind-consider-the-opposite` | Consider-the-opposite debiasing | Lord, Lepper & Preston, 1984 |
| `blind-falsification` | Falsificationism / 2-4-6 task | Popper, 1934; Wason, 1960 |
| `blind-survivorship-bias` | Survivorship bias | Wald, WWII SRG |
| `blind-chestertons-fence` | Chesterton's Fence | Chesterton, 1929 |
| `blind-unknown-unknowns` | Knowledge matrix | Johari-derived; Rumsfeld, 2002 |
| `blind-steelman` | Steelmanning / Ideological Turing Test | Caplan, 2011 |
| `blind-curse-of-knowledge` | Curse of knowledge / tappers & listeners | Camerer et al., 1989; Newton, 1990 |
| `blind-calibration` | Overconfidence calibration | Lichtenstein & Fischhoff, 1982; Alpert & Raiffa |

## Install

### Any agent (skills CLI)

```bash
npx skills add jpoindexter/blind-spots
```

### Claude Code (manual)

```bash
git clone https://github.com/jpoindexter/blind-spots.git
cp -R blind-spots/skills/* ~/.claude/skills/
```

Project-scoped instead: copy into `<project>/.claude/skills/`.

### Codex

```bash
cp -R blind-spots/skills/* ~/.agents/skills/
```

### Anything else

Each skill is a folder containing a single self-contained `SKILL.md` with YAML frontmatter (`name`, `description`) per the [Agent Skills specification](https://agentskills.io/specification). Copy the folders wherever your agent discovers skills, or paste a SKILL.md body directly into a system prompt.

## Verification status

- **Install path executed, not assumed**: `npx skills add` run against this repo — 17/17 skills found and installed (strict-YAML frontmatter validated with PyYAML; an earlier version lost 6 skills to unquoted colons in descriptions).
- **Behavior-tested**: the `blind` dispatcher and a 3-skill sample (falsification, outside-view, chestertons-fence) were run by fresh agents against realistic scenarios; the gaps they hit (routing tie-breaks, severity rubric, no-history fallback) are fixed in the current version.
- **Citations under external fact-check**: every named study and numeric figure is being verified against primary sources; corrections land as individual commits.

## Design notes

- **One framework per skill**, named and cited — no folk wisdom, no invented acronyms.
- **Descriptions state only triggering conditions** (when to fire), never the workflow — so agents read the body instead of shortcutting from the description.
- **Every skill ends with Common Mistakes**, including the failure mode of the skill itself (e.g. fence-worship for Chesterton's Fence, hedging-as-theater for calibration).
- Skills cross-reference each other by name; the dispatcher composes them.

## License

MIT
