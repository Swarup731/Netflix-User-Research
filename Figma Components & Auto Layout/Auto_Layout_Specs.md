# Task 2 — Auto Layout Specifications

Every master component uses Auto Layout at its root frame. Below are the exact settings per component, plus a stress test proving they hold at both content extremes.

![Auto Layout Stress Test](./assets/autolayout_stress_test.svg)

## Per-Component Settings

| Component | Direction | Resizing | Padding | Gap |
|---|---|---|---|---|
| **Button/Primary** | Horizontal | Width: Hug contents · Height: Hug contents | 12 / 24 (V/H) | 8 |
| **Button/Secondary** | Horizontal | Width: Hug contents · Height: Hug contents | 12 / 24 (V/H) | 8 |
| **Input/Search** | Horizontal | Width: Fill container · Height: Hug contents | 12 / 16 (V/H) | 12 |
| **Chip/Filter** | Horizontal | Width: Hug contents · Height: Hug contents | 8 / 20 (V/H) | 0 |
| **Chip/Time** | Horizontal | Width: Hug contents · Height: Hug contents | 8 / 20 (V/H) | 0 |
| **Card/Movie** | Vertical | Width: Fixed (grid-driven) · Height: Hug contents | 0 / 0, inner text block: 8 / 12 | 8 |
| **ListItem/Episode** | Horizontal | Width: Fill container · Height: Hug contents | 8 / 12 (V/H) | 16 |
| **Nav/Item row** | Horizontal | Width: Fill container · Height: Hug contents | 0 / 0 | 32 |
| **SelectableRow/Mood** | Horizontal | Width: Fill container · Height: Hug contents | 12 / 16 (V/H) | 12 |

## Stress Test — Why This Matters

Two failure modes Auto Layout is meant to prevent:

1. **Short content leaving dead space** — a fixed-width button sized for "Find Something to Watch" looks wrong around "Play." Hug-width fixes this: the button always wraps its content with consistent padding, regardless of label length.
2. **Long content breaking the layout** — a fixed-width row item sized for a 4-word episode title will either clip or overflow a 40-word title. Fill-width + text set to "Hug height" lets the text wrap onto a second line and pushes the row taller instead of breaking.

The diagram above shows this at both extremes for `Button/Primary` (2-word vs. 6-word label, same hug-width behavior) and `ListItem/Episode` (short vs. long title, same fill-width row expanding vertically).

## Nesting Behavior

Auto Layout frames nest cleanly: a `Row` component (horizontal Auto Layout, fixed height, gap 16) contains multiple `Card/Movie` instances (each fixed-width, hug-height). Because the Row's height is set to **Hug contents**, if a Card ever grows taller (e.g. a two-line title pushes its own height up), the Row grows to match automatically — no manual resizing needed anywhere in the hierarchy.
