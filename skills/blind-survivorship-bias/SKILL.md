---
name: blind-survivorship-bias
description: Use when analyzing metrics, user feedback, success stories, benchmarks, churn, error logs, or any dataset — before drawing conclusions. Applies Abraham Wald's WWII bomber insight: the data you have was filtered by a survival process, and the filter is the finding.
---

# Survivorship Bias

## Overview

Abraham Wald (Statistical Research Group, WWII): commanders wanted to armor bombers where returning planes showed bullet holes. Wald inverted it — **the returning planes survived those hits; armor where the survivors are clean**, because planes hit there never came back. The holes you can see mark the survivable damage. The dataset "planes we can inspect" was silently filtered by the very outcome under study.

**Every dataset arrived through a filter. Analyzing the data without modeling the filter analyzes the survivors, not the population.**

## When to Use

- User feedback / NPS / reviews (only non-churned, non-silent users respond)
- Error logs and crash reports (crashes that prevent reporting don't report)
- "What do successful X do?" pattern studies (failures did those things too — unobserved)
- Benchmarks, case studies, testimonials, A/B results, retention metrics
- Any conclusion of the form "our users want…" / "top performers all…"

## The Procedure

1. **Name the filter**: what process decided which data points reached you? (Self-selection, churn, crash-before-report, publication, sales pipeline.)
2. **Describe the ghosts**: who/what would NOT appear? Estimate the invisible population's size — sometimes it dwarfs the visible one.
3. **Ask Wald's question**: does the conclusion flip if the missing data is systematically different? (Armor the clean spots.) If churned users hated the feature that survey-respondents love, the survey is inverted evidence.
4. **Hunt one ghost directly**: interview churned users, log the failure path, find companies that did the same playbook and died. One recovered non-survivor is worth 100 more survivors.

## Quick Reference

| Visible data | Invisible counterpart to check |
|---|---|
| Feature requests from active users | Why departed users left |
| Errors in the log | Failures that never reached logging |
| Practices of successful founders/projects | Same practices among the failed |
| 5-star and 1-star reviews | The silent middle who just left |
| Long-tenured employees love the culture | Everyone who quit in year one |

## Common Mistakes

- Adding more survivor data to fix a survivorship problem (bigger N, same filter).
- Treating absence from the data as absence in reality ("no complaints about X" — or no channel that captures them?).
- Studying only failures instead (reverse survivorship) — you need both tails to find what actually discriminates.
