# Usability Test Results

> **Note on data:** As with the rest of this repository, these are synthesized results, not a live study — see `../Research/Research_Objectives.md` for the standing data disclosure. Full raw log: [`Usability_Test_Data.xlsx`](Usability_Test_Data.xlsx).

## Session Overview
6 participants × 5 tasks = 30 task attempts, run against `../Prototype/interactive-prototype.html` following the script in `Usability_Test_Script.md`.

## Raw Results Summary

| Participant | Prior Exposure | Task 1 | Task 2 | Task 3 | Task 4 (SmartPick) | Task 5 |
|---|---|---|---|---|---|---|
| P1 | No | ✅ 14s | ✅ 38s (1 err) | ✅ 22s (1 err) | ⚠️ 46s (2 err) | ✅ 6s |
| P2 | Yes | ✅ 9s | ✅ 25s | ✅ 11s | ✅ 19s | ✅ 4s |
| P3 | No | ✅ 21s (1 err) | ⚠️ 52s (3 err) | ❌ 41s (3 err) | ❌ 58s (2 err) | ✅ 15s (1 err) |
| P4 | No | ✅ 12s | ✅ 33s (1 err) | ✅ 19s | ✅ 35s (1 err) | ✅ 8s |
| P5 | Yes | ✅ 10s | ✅ 28s | ✅ 13s | ✅ 21s | ✅ 5s |
| P6 | No | ✅ 17s | ⚠️ 44s (2 err) | ❌ 36s (2 err) | ⚠️ 51s (2 err) | ⚠️ 19s (2 err) |

✅ Success · ⚠️ Partial (completed with confusion/hints) · ❌ Fail (did not complete within 2-minute cap)

## Key Observations

### 1. Task 1 (Browse & Watch) performed exactly as intended
100% success, lowest average time (13.8s), highest ease score (4.5/5). Continue Watching being the first row on Home — a direct carry-through from the original research finding — did its job.

### 2. Task 4 (SmartPick) had the lowest success rate (50%) and second-highest error count
Both participants who failed or needed hints specifically didn't notice the floating action button unprompted. P4's comment — *"I found it but wasn't sure what the sparkle icon meant"* — and P1's post-test note that they didn't recognize SmartPick before being told about it both point to the same root cause: **the FAB is visible but not self-explanatory.** This is the most actionable finding from the whole test, because SmartPick is the feature most directly tied to solving the "choice overload" research problem — if people don't find it, it can't do its job.

### 3. Task 3 (Account Navigation) had the second-lowest ease score (3.0/5) and 2 outright failures
Both participants who struggled tried the bottom navigation bar first, expecting an account/profile tab there, before eventually finding the profile icon in the header. P6 additionally got stuck *inside* the drawer — once open, there was no obvious explicit close control beyond a text row at the bottom, which two participants missed entirely (they tried tapping the drawer's edges).

### 4. Prior wireframe exposure correlated with faster, cleaner completion
P2 and P5 (both previously exposed) had zero navigation errors across all 5 tasks and the fastest average times. This isn't a design flaw — it's expected that familiarity helps — but it's worth flagging so the metrics in `Usability_Metrics.md` aren't read as if all 6 participants were equally naive to the design.

### 5. Recovery (Task 5) mostly worked, but inherited Task 3's close-button confusion
The two participants who struggled with Task 3's drawer close also struggled identically on Task 5 — confirming this is one root issue (unclear close affordance), not two separate problems.

## Summary Table (from Task Summary sheet)
| Task | Avg Time | Success Rate | Avg Nav Errors | Ease Score |
|---|---|---|---|---|
| 1. Browse & Watch | 13.8s | 100% | 0.17 | 4.5 |
| 2. Targeted Search | 36.7s | 67% | 1.17 | 3.2 |
| 3. Account Navigation | 23.7s | 67% | 1.0 | 3.0 |
| 4. Guided Discovery (SmartPick) | 38.3s | 50% | 1.17 | 3.3 |
| 5. Recovery | 9.5s | 83% | 0.5 | 4.0 |

Ranked and visualized in `Usability_Metrics.md`.
