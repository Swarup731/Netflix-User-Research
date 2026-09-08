# Task 3 — Component States: Hover, Active, Focus

Built as **Variants** (a `State` component property: `default / hover / active / focus / disabled`) rather than separate one-off components, so state changes are just a property swap on a single instance — not a different component to manage.

![Component States](./assets/component_states.svg)

## State Definitions

| State | Trigger | Visual Change | Token Used |
|---|---|---|---|
| **Default** | — | Base appearance | `Surface/Elevated`, `Text/Primary` |
| **Hover** | Mouse pointer over element | Slight scale (1.0 → 1.05 on cards), background lightens one step, cursor pointer | `Surface/Elevated-Hover` |
| **Active** | Mouse/touch pressed down | Scale settles back down (1.0), background darkens one step — gives tactile "pressed" feedback | `Surface/Elevated-Active` |
| **Focus** | Keyboard tab / remote-control navigation lands on element | Visible outline ring, no reliance on color alone | `Focus/Interactive (#FFFFFF)`, 2px offset ring |
| **Disabled** | Element not currently interactive | Reduced opacity (~40%), no hover/active response | `Text/Disabled` |

## Why Focus Gets Its Own Treatment

Hover is a mouse-only concept. Netflix's actual interface runs on TVs and remote controls as much as it does on a mouse-driven browser — there is no hover state when navigating with a D-pad. **Focus** is the state that matters there, so it's treated as a first-class variant, not an afterthought bolted onto hover styling.

The focus ring uses the `Focus/Interactive` white token verified for WCAG contrast against both light and dark surfaces during Week 3's color audit — this diagram places it on dark backgrounds specifically because a white-on-white ring on a light mockup background was nearly invisible in an earlier draft, which is the actual failure mode worth designing against.

## Applied To

- `Button/Primary`, `Button/Secondary` — full 5-state set
- `Chip/Filter`, `Chip/Time` — full 5-state set (no disabled variant needed in practice, omitted from Figma to avoid an unused variant)
- `Card/Movie` — hover (scale + play icon overlay + info reveal) and focus (ring) only; no "active/pressed" state since cards navigate rather than toggle
- `Nav/Item` — hover (underline appears) and focus (ring) only
