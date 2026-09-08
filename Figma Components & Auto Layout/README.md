# Netflix UI Design System — Study Repository

A running design-system build based on Netflix's interface, developed week by week as part of a UI/UX design course. Each week adds a layer: from foundational grid/typography principles to a full component library with tokens.

## Structure

```
repo/
├── README.md                          ← you are here
├── Components.md                      ← Week 3 overview: grid, spacing, type scale
├── Component_Library/                 ← Week 4: master components, auto-layout, states, tokens
│   ├── README.md
│   ├── Master_Components.md
│   ├── Auto_Layout_Specs.md
│   ├── Component_States.md
│   ├── Responsive_Card_Templates.md
│   ├── Spacing_Tokens.md
│   └── assets/
│       ├── master_components.svg
│       ├── autolayout_stress_test.svg
│       ├── component_states.svg
│       ├── responsive_cards.svg
│       └── spacing_tokens.svg
```

## Progress

| Week | Topic | Status |
|---|---|---|
| 3 | UI Design Principles & Grid Systems | ✅ Complete |
| 4 | Figma Components & Auto Layout | ✅ Complete |

## Full Story — Pipeline So Far

1. **Week 3** established the visual foundation: an 8pt baseline grid, a modular type scale, and Netflix's dark-surface color relationships (background, elevated surface, primary text, secondary text, brand red, focus white).
2. **Week 4** turns that foundation into reusable, interactive building blocks:
   - Master components for every repeating UI element (cards, buttons, nav items, chips, list rows)
   - Auto Layout rules so components hold up under real content (short vs. long titles, 1 vs. 3-digit match scores)
   - Explicit Default / Hover / Active / Focus / Disabled states — including Focus, which matters specifically for Netflix's TV/remote navigation mode where there's no mouse hover
   - Responsive card templates showing what stays fixed (component identity) vs. what changes (density, columns) across breakpoints
   - A documented spacing token scale tying every gap/padding value in the system back to a single 4px base unit

See `Component_Library/README.md` for the Week 4 breakdown in detail.
