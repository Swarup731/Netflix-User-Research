# Components

Core reusable UI components used across the wireframes and high-fidelity mockups, built from the tokens in `Color_System.md` and `Typography.md`.

## Buttons
| Component | Fill | Text | Radius | Notes |
|---|---|---|---|---|
| Primary Button | `#FFFFFF` | `#141414` | 4px | Highest-emphasis action (Play) |
| Secondary Button | transparent, `#B3B3B3` border | `#FFFFFF` | 4px | Medium-emphasis action (+ My List) |
| Primary CTA (Red) | `#E50914` | `#FFFFFF` | 4px | Used for SmartPick's "Find Something to Watch" — the single most important action on that screen |

## Inputs
| Component | Fill | Border | Placeholder Text |
|---|---|---|---|
| Search Field | `#221F1F` | none (or `#333333` on focus) | `#B3B3B3` |

## Cards
| Component | Fill | Notes |
|---|---|---|
| Movie/Show Card | image thumbnail, `#221F1F` fallback | 4px radius, no border; hover/focus state adds a `#FFFFFF` outline (Focus/Interactive token) |
| Episode List Item | `#221F1F` | Row card, thumbnail + title + duration |
| Success/Download Badge | `#46D369` fill, `#141414` text/icon | Text on this badge must be **black**, not white — white fails WCAG contrast on this shade of green (1.95:1). See `../Accessibility/WCAG_Contrast.md`. |

## Navigation
| Component | Active State | Inactive State |
|---|---|---|
| Bottom Nav Item | `#FFFFFF` label + small `#E50914` indicator dot | `#B3B3B3` label |

> Note: active nav items use a **white label + red indicator dot**, not red text — see `../Accessibility/WCAG_Contrast.md` for why red text fails at small sizes on the black background.

## Filter Chips
| State | Fill | Text | Border |
|---|---|---|---|
| Inactive | transparent | `#FFFFFF` | `#B3B3B3` |
| Active | `#E50914` | `#FFFFFF` | none |

## Where These Appear
All of the above are visible in context across `../High_Fidelity_Mockups/` (Home, Search, Movie Details, My Netflix, SmartPick).
