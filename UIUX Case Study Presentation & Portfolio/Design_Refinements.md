# Design Refinements — From Findings to Fixes

Three changes made directly to `../Prototype/interactive-prototype.html`, each tracing to a specific finding in `../Usability_Testing/Usability_Test_Results.md`, prioritized by the ranking in `Usability_Metrics.md`.

## ⚠️ About "Refine the Figma Prototype"
These refinements were applied as real code edits to the working HTML prototype (the closest equivalent available without Figma access) rather than to a `.fig` file — each entry below is specific enough to apply as the equivalent Figma component/variant edit.

## Refinement 1 (Priority: Worst-ranked) — SmartPick Discoverability

**Finding:** Task 4 had the lowest success rate (50%). 3 of 6 participants didn't notice the floating action button unprompted; one who did find it wasn't sure what the sparkle icon meant.

**Root cause:** an icon-only FAB with no label assumes the icon is self-explanatory. Sparkle (✨) doesn't unambiguously mean "personalized recommendations" to someone seeing it for the first time.

**Fix applied:**
- Added a text label pill ("Try SmartPick ✨") that appears next to the FAB briefly on load and again after ~7 seconds of inactivity if SmartPick hasn't been opened yet — a one-time discovery nudge, not a persistent label (which would clutter the Home screen every visit).
- Added a descriptive `aria-label` ("Open SmartPick — get a personalized recommendation") so the button's purpose is stated explicitly for screen readers too, not just sighted users glancing at the label pill.

**Before / after (code):**
```diff
- <button class="fab" onclick="openSmartPick()" aria-label="Open SmartPick">✨</button>
+ <div class="fab-label" id="fab-label">Try SmartPick ✨</div>
+ <button class="fab" onclick="openSmartPick()" aria-label="Open SmartPick — get a personalized recommendation">✨</button>
```
Plus a `showFabLabel()` timer that fades the label in/out and permanently stops once `openSmartPick()` has been called once (`smartPickOpened = true`), so returning users aren't nagged after they've already discovered the feature.

**Not changed:** the FAB's position, color, and icon itself — the metrics didn't suggest the button was hard to *see* (visual contrast against the dark background is fine), only hard to *understand*. Changing position or color would have addressed a problem that wasn't actually the one observed.

## Refinement 2 (Priority: Poor-ranked, shared root cause) — Drawer Close Affordance

**Finding:** Task 3 had 2 outright failures and Task 5 (Recovery) showed the identical confusion in the same 2 participants — both tried tapping the drawer's edges looking for a close control, missing the text-only "Close ✕" row at the bottom of the list.

**Root cause:** the only close affordance was a list row visually identical in style to the navigable items above it (Manage Profiles, Subscription, etc.), so it didn't read as a distinct control — and it required scrolling to the bottom of the drawer to find.

**Fix applied:** added an explicit circular ✕ button fixed to the top-right corner of the drawer — the position most people expect a "close this panel" control, and visually distinct (filled circle, no list styling) from the navigable menu items below it. The original bottom "Close ✕" row was left in place as a secondary option rather than removed, since it wasn't the problem — its *singularity* was.

**Before / after (code):**
```diff
  <div class="drawer" id="home-drawer">
+   <button class="drawer-close" onclick="closeDrawer()" aria-label="Close menu">✕</button>
    <h3>Account</h3>
```

## Refinement 3 (Priority: Poor-ranked) — Search Chip Multi-Select Clarity

**Finding:** Task 2 had a 67% success rate with the highest tied error count (1.17 avg). Two participants (P3, P6) treated genre chips as single-select — tapping Comedy then Action expecting the second tap to replace the first, then noticing both were active and being unsure if that was intended.

**Root cause:** filter chips with no visual grouping or explanatory text give no signal about whether they're single-select (like radio buttons) or multi-select (like checkboxes) — both patterns are common enough elsewhere that people bring either mental model in.

**Fix applied:** added a one-line hint directly above the genre chip row: *"Tap to combine filters — multiple can be active at once."* This is a deliberately minimal fix — it doesn't change the chip component itself (from `../Component_Library/Master_Components.md`'s `Chip/Filter`), because the interaction model (multi-select) is the right one for this use case; participants just needed to be told.

**Before / after (code):**
```diff
  <div class="label-sm">Genre</div>
+ <div class="chip-hint">Tap to combine filters — multiple can be active at once</div>
  <div class="chips"> ... </div>
```

## What Was Deliberately Not Changed
- **Browse & Watch (Task 1)** — 100% success, 4.5 ease score. No changes; touching a component performing this well risks regressions for no measurable benefit, per the ranking rationale in `Usability_Metrics.md`.
- **The underlying chip data model** — still multi-select. The fix is explanatory, not structural, because the structure tested fine once explained (both confused participants completed the task after the hint would have been visible).
- **FAB position/color** — see Refinement 1's "Not changed" note above.

## Suggested Next-Round Test
Re-run Tasks 2–4 with a fresh set of participants against this refined prototype, specifically checking whether the FAB label nudge and chip hint are noticed *before* participants get stuck (not just whether they succeed after already being confused) — the true test of a discoverability fix is fewer people needing it in the first place, not full recovery after the fact.
