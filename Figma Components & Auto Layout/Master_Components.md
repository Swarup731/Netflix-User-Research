# Task 1 — Master UI Components

9 master components created in Figma, each promoted from a local frame to a **main component** (◇ diamond icon) so every instance stays linked and updates propagate from a single source of truth.

![Master Components Reference](./assets/master_components.svg)

## Component Inventory

| Component | Layer Structure | Used In (Week 3 mockups) |
|---|---|---|
| **Button/Primary** | `Frame (Auto Layout) → Icon (optional) + Label` | Hero "Play" CTA, modal confirm actions |
| **Button/Secondary** | `Frame (Auto Layout, stroke) → Icon (optional) + Label` | "+ My List", "More Info" |
| **Input/Search** | `Frame (Auto Layout) → Icon + Text field + Clear icon` | Top nav search |
| **Chip/Filter** | `Frame (Auto Layout, pill radius) → Label` | Genre filter row |
| **Card/Movie** | `Frame → Thumbnail (fill) + Overlay (on hover) + Title + Match badge` | Every content row |
| **ListItem/Episode** | `Frame (Auto Layout, horizontal) → Thumbnail + Text block (title + duration) + Play icon` | Episode picker |
| **Nav/Item** | `Frame (Auto Layout) → Icon/Label` | Top nav bar |
| **SelectableRow/Mood** | `Frame (Auto Layout, vertical) → Icon + Label + Selection indicator` | Onboarding "what are you in the mood for" |
| **Chip/Time** | `Frame (Auto Layout, pill radius) → Label` | "Under 30 min" type filters in row headers |

## Build Notes

- Every component uses **Auto Layout** at the top frame level (see `Auto_Layout_Specs.md`) — none are static, fixed-size frames. This is what allows the same component to hold a 4-word title and a 12-word title without manual resizing.
- Icons are nested component instances (from an icon set), not flattened vectors, so a global icon swap propagates through every button/nav item at once.
- Color and text values reference **Figma Variables**, not hardcoded hex/px — see `Spacing_Tokens.md` for the full token list. This means a single "Surface/Elevated" variable update recolors every card, chip, and input at once.
- Components are organized under a `Master/` page in the Figma file, grouped into sections (`Buttons`, `Inputs & Chips`, `Cards & Lists`, `Navigation`) so instances panel search stays clean as the library grows.

## Why These 9

These are the components that appear **more than once** across the Week 3 mockups — the threshold used to decide "master component" vs. "one-off frame." A footer or a single hero banner, which appear exactly once, were left as regular frames rather than turned into components, since componentizing a one-off adds maintenance overhead with no reuse benefit.
