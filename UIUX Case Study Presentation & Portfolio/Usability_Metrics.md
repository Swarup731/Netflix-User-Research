# Usability Metrics — Ranked

![Usability Metrics Ranked](usability-metrics.png)

## Ranking Method
Tasks are ranked worst-to-best by a composite read of all four metrics (success rate weighted most heavily, then ease score, then error count, then time) — not by any single number in isolation. Time alone would be misleading here: Task 4 (SmartPick) and Task 2 (Search) have similar average times, but Task 4's 50% success rate is a materially worse outcome than Task 2's 67%.

## Ranked Table
| Rank | Task | Avg Time | Success Rate | Avg Nav Errors | Ease Score /5 | Priority |
|---|---|---|---|---|---|---|
| 1 (worst) | Guided Discovery (SmartPick) | 38.3s | 50% | 1.17 | 3.3 | 🔴 Worst |
| 2 | Targeted Search | 36.7s | 67% | 1.17 | 3.2 | 🟠 Poor |
| 3 | Account Navigation | 23.7s | 67% | 1.0 | 3.0 | 🟠 Poor |
| 4 | Recovery | 9.5s | 83% | 0.5 | 4.0 | 🔵 OK |
| 5 (best) | Browse & Watch | 13.8s | 100% | 0.17 | 4.5 | 🟢 Best |

## What "Priority" Drives
This ranking is the direct input to `Design_Refinements.md` — the two lowest-ranked tasks (SmartPick discoverability, Search chip model) get addressed first, Account Navigation's close-button confusion is addressed as a shared root cause with Recovery, and Browse & Watch is explicitly **not** touched, because changing a component that's already testing at 100% success / 4.5 ease risks introducing regressions for no measurable gain.

## Reading the Ease Score Bars
The ease score is the participant's own 1–5 rating from the post-test questionnaire (`Usability_Test_Script.md`, question 1, asked per-task informally during debrief), not a derived metric — it's included precisely because it can diverge from the objective numbers. Task 5 (Recovery) has a fairly high ease score (4.0) despite a below-100% success rate, because the two participants who struggled attributed it entirely to "not seeing a close button" rather than feeling the interaction itself was hard — a distinction only a subjective score surfaces.

## Cross-Reference
Raw per-participant data: [`Usability_Test_Data.xlsx`](Usability_Test_Data.xlsx) · Narrative findings: [`Usability_Test_Results.md`](Usability_Test_Results.md) · Resulting design changes: [`Design_Refinements.md`](Design_Refinements.md)
