# Usability Test Script

## Test Objective
Validate whether the interactive prototype (`../Prototype/interactive-prototype.html`) actually solves the core research problem — "users spend too much time deciding what to watch" — and surface any navigation errors before treating the design as finalized.

## Participants
6 participants, recruited against the same criteria as the original research (`../Research/Research_Objectives.md`): active or lapsed streaming subscribers, mixed ages 20s–40s, mixed device familiarity. 3 participants had seen an earlier low-fidelity wireframe version; 3 had not, to check whether prior exposure changed performance.

## Session Format
- **Method:** Moderated, remote, screen-shared, think-aloud
- **Duration:** ~20 minutes per session
- **Tool:** Prototype opened directly in the participant's browser (no Figma account required)
- **Moderator role:** Read each task instruction verbatim, start a timer on the participant's first tap after hearing the task, stop it on task completion or after a 2-minute cap, and log every wrong tap as a navigation error without correcting the participant mid-task.

## Pre-Test Script (read aloud)
> "Thanks for helping test this. This is a prototype for a streaming app redesign — I'm testing the design, not you, so if something's confusing that's really useful information, not a mistake on your part. I'll give you a few small tasks one at a time. Please talk through what you're looking at and what you expect to happen as you go. There are no wrong answers — if you get stuck, that's exactly what I need to see."

## Tasks

### Task 1 — Browse & Watch (Discovery)
> "Imagine you've just opened the app with a bit of free time. Find something to watch and start playing it."
**Success criteria:** reaches the video player state (via Home → card → Movie Details → Play, or Continue Watching → Play).
**Watch for:** hesitation time on Home before the first tap; whether they try Search instead of browsing.

### Task 2 — Targeted Search
> "Now imagine you know exactly what you want: a comedy movie in Hindi. Find one."
**Success criteria:** reaches Search, activates both the Comedy genre chip and the Hindi language chip, and selects a result.
**Watch for:** whether they notice chips are independently toggleable, or expect a single combined filter.

### Task 3 — Account Navigation
> "You want to change your subscription plan. Show me how you'd get there."
**Success criteria:** opens the profile drawer and locates "Subscription."
**Watch for:** whether they find the profile icon at all, and whether they try the bottom nav first.

### Task 4 — Guided Discovery (SmartPick)
> "You have about 30 minutes and want something relaxing — but you don't want to scroll around looking. See if the app can just tell you what to watch."
**Success criteria:** discovers and uses the SmartPick feature (via the FAB) without being told its name, selects Relaxed + 30 min, and reaches a recommendation.
**Watch for:** whether the floating action button is noticed unprompted — this task is the direct usability test of the SmartPick design opportunity from `../Design_Opportunity/Netflix_SmartPick.md`.

### Task 5 — Recovery
> "Close whatever's open and go back to where you started."
**Success criteria:** dismisses any open drawer/modal and returns to Home.
**Watch for:** whether they tap the scrim, look for a close button, or try the device back gesture (not supported in this prototype — worth noting if attempted).

## Post-Test Questions
1. On a scale of 1–5, how easy was it to find something to watch overall?
2. Was there any moment you felt unsure what to do next? Which task?
3. Did you notice the SmartPick feature before Task 4 asked about it?
4. Anything you expected to work differently than it did?

## Data to Log Per Task
Recorded in `Usability_Test_Results.md` / `Usability_Test_Data.xlsx`: completion time (seconds), success/fail/partial, number of navigation errors (wrong taps before reaching the goal), and a one-line qualitative note.
