---
name: blind-outside-view
description: Use when making any estimate, forecast, deadline, budget, or "how long will this take" judgment, or when a plan's success case is built from its own specifics. Applies Kahneman & Lovallo's outside view / reference class forecasting against the planning fallacy.
---

# Outside View

## Overview

Kahneman & Lovallo (1993, *Management Science*); Kahneman & Tversky's planning fallacy (1979); operationalized as Reference Class Forecasting (Flyvbjerg, 2006, mandated for UK/Danish megaprojects). The **inside view** builds a forecast from the case's specifics — your plan, your steps, your skill — and systematically fails, because the specifics you can see exclude the disruptions you can't (the unknown unknowns are, by construction, not in your scenario). The **outside view** ignores the specifics and asks: **what happened to everyone else who did roughly this?**

The blind spot: "this case is different" feels true for *every* case, which is exactly why base rates beat scenarios.

## When to Use

- Any time/cost/effort estimate ("2 hours", "by Friday", "one sprint")
- Predicting success odds of a launch, refactor, migration, startup, diet
- A plan justified entirely by its own internal logic
- Reviewing someone's confident single-point estimate

## The Procedure (Reference Class Forecasting)

1. **Pick the reference class**: projects/tasks like this one, done by people like the doer — not by you-on-your-best-day. ("Auth system migrations at small teams", not "this migration".)
2. **Get the distribution**: what's the typical outcome, the spread, the failure rate? Use your own history first (git log, past estimates vs. actuals, ERRORS.md-style records) — past-self is the closest reference class.
3. **Anchor on the base rate**, then adjust for specifics *sparingly* — only for verified, unusual facts, and less than feels right.
4. **Report a range, not a point** (best / realistic / worst), with the realistic case at the reference-class typical — not at your scenario's smooth path.

## Quick Reference

| Inside-view tell | Outside-view fix |
|---|---|
| "My plan has 4 steps at ~30min each" | "Similar tasks historically took 2–3× the step-sum" |
| "This time is different because…" | Different for everyone; adjust ≤20% and only on verified facts |
| Single-point estimate | Range + base-rate anchor |
| No comparable cases considered | Force 3 comparables before estimating |

## Common Mistakes

- Choosing a flattering reference class ("times everything went smoothly").
- Taking the base rate, then adjusting all the way back to the inside view. The anchor must do real work.
- Using the outside view on others' plans but the inside view on your own (see blind-bias-blind-spot).
- Predicting the best case and calling it "realistic". The typical case IS the realistic case.
