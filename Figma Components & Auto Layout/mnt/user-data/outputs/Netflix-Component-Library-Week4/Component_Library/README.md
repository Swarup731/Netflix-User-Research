# Component Library — Week 4

Figma deliverable: a responsive UI component library for a Netflix-style application, covering master components, Auto Layout, interactive states, responsive card assembly, and spacing tokens.

## Contents

| File | Task | Covers |
|---|---|---|
| [Master_Components.md](./Master_Components.md) | 1 | Inventory of reusable master components and their layer structure |
| [Auto_Layout_Specs.md](./Auto_Layout_Specs.md) | 2 | Auto Layout direction, resizing, padding, and gap per component |
| [Component_States.md](./Component_States.md) | 3 | Default / Hover / Active / Focus / Disabled definitions |
| [Responsive_Card_Templates.md](./Responsive_Card_Templates.md) | 4 | Card assembly across mobile / tablet / desktop breakpoints |
| [Spacing_Tokens.md](./Spacing_Tokens.md) | 5 | 4px-base spacing scale and where it's used |

## Milestone Checklist

- [x] Master UI components created (9 components)
- [x] Auto Layout applied and stress-tested against short/long content
- [x] Interactive variants defined: hover, active, focus (+ disabled)
- [x] Responsive card templates assembled from component instances
- [x] Spacing variables and tokens documented
- [x] Component Library README + top-level README updated

## Design Principle Behind This Week

Every artifact here follows one rule: **a component's identity should never change, only its configuration.** A `Card/Movie` component is the same component on mobile, tablet, and desktop — what changes is the frame it sits in (grid columns, gaps) and its own Auto Layout resizing (hug vs. fill), never its underlying structure. This is what makes the library "responsive" in Figma terms rather than just "three different mockups that happen to look similar."
