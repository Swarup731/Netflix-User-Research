# Loaders & Progress Indicators

Three distinct patterns, each used for a different kind of wait — matching the wait to the right indicator is the actual design decision here, not just "add a spinner."

## 1. Spinner (indeterminate, short waits)
**Used for:** SmartPick's "Finding something to watch…" and the Episode Player's "Loading episode…" — both simulate roughly 900ms–1200ms delays with an unknown/variable completion time.

**Spec:** 34px circular spinner, 3px stroke, `#3A3A3A` track with `#E50914` (brand red) as the active arc, 0.8s linear rotation, paired with a one-line status label in `#B3B3B3` explaining what's happening ("Finding something great…" not just a bare spinner) — per the Week 3 writing guidance, an empty/waiting state should say what's happening, not leave the person guessing.

## 2. Determinate Progress Bar (known duration/quantity)
**Used for:** the "Simulate download" action on My Netflix.

**Spec:** 6px track, `#333333` background, `#E50914` fill, animates from 0% to 100% width over 1.4s. Unlike the spinner, this is used specifically because a download has a real, trackable quantity (bytes/percentage) — using an indeterminate spinner for a downloadable file would hide information the person actually has a right to see (how much longer).

**Completion signal:** a small `#46D369` (Success token) checkmark badge appears on the downloaded card once the bar completes — reusing the exact success-state pattern documented in `../Component_Library/Component_States.md` and the color decision from `../Accessibility/WCAG_Contrast.md` (black icon glyph on the green badge, not white, for contrast).

## 3. Skeleton / Shimmer (content-shaped loading)
**Spec:** `background: linear-gradient(90deg, #222 25%, #2c2c2c 37%, #222 63%)` animated across a 400% background-size over 1.3s, applied to the same shape as the real content it stands in for (defined in the CSS as `.skeleton` and available for use on card rows or search results while data is fetching).

**Why this exists as a third pattern, not just "more spinners":** a spinner replacing an entire content area (e.g. the whole search results list) creates a jarring pop-in once content loads, because nothing about the spinner hints at what's coming or where it'll appear. A skeleton shape in the exact size/position of the real content preserves layout stability — nothing jumps around once the real cards replace the skeletons.

## Matching Indicator to Wait — Summary Table
| Situation | Indicator | Why |
|---|---|---|
| Unknown-duration action with a clear single outcome (SmartPick result, episode load) | Spinner + status label | Short, indeterminate, one thing to wait for |
| Trackable quantity over time (download) | Determinate progress bar | Person has a right to see real progress |
| Data fetch that will populate a known layout (search results, content rows) | Skeleton/shimmer | Preserves layout, previews shape of what's coming |

## Where to See Each Live
All three are functional (not just illustrated) in `interactive-prototype.html`: tap the SmartPick FAB → "Find Something to Watch" for the spinner, tap "Simulate download" on My Netflix for the progress bar, and see `.skeleton` in the CSS for the shimmer pattern ready to apply to any async content area.
