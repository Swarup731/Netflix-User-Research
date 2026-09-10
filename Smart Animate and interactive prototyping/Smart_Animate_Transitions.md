# Smart Animate — State Transitions

## ⚠️ About Figma's Smart Animate
Figma's Smart Animate interpolates matching layers between two frames automatically (position, size, rotation, opacity) when layer names match across both. This environment can't produce that natively, so each transition below is implemented as real CSS transitions in `interactive-prototype.html` that reproduce the same *effect* Smart Animate would — and is specified precisely enough to rebuild as actual Smart Animate connections in Figma (matching layer names included).

## Transition Catalog

### 1. Screen-to-screen navigation (Home → Search / Movie Details / My Netflix)
| Property | Figma Smart Animate Setting | CSS Equivalent (implemented) |
|---|---|---|
| Easing | Ease Out | `ease` |
| Duration | 300ms | 320ms |
| Matched layers | Bottom nav bar (persists, only active-state changes) | `.bottom-nav` stays in the DOM structure identically across screens; only `.active` class + red dot move |
| Non-matched layers | Cross-fade in/out | New screen fades in + slides 24px → 0 |

**Why the bottom nav "moves" instead of re-rendering:** Smart Animate's real power is recognizing the nav bar as the *same* layer across frames and smoothly moving/updating just the active-indicator dot, rather than the whole bar disappearing and reappearing. The prototype reproduces this by never destroying the nav — it's structurally present on every screen, only the active class changes.

### 2. Card → Movie Details (shared element continuity)
| Property | Setting |
|---|---|
| Trigger | Tap |
| Matched layer | Card thumbnail → Movie Details hero art (same gradient/color carried forward) |
| Duration | 320ms, Ease Out |
| Effect | The tapped card's color scheme reappears as the hero background on Movie Details, giving the impression the card "expanded" into the detail screen, even though it's technically a new screen |

### 3. Drawer open/close
| Property | Setting |
|---|---|
| Trigger | Tap (open) / Tap outside or "Close" (close) |
| Animation | Move In from the right (not Smart Animate — a dedicated Figma prototype transition type) |
| Duration | 320ms, Ease Out (custom bezier `cubic-bezier(.2,.8,.2,1)` in the CSS implementation for a slight overshoot-free deceleration) |
| Scrim | Fades in/out in sync (0 → 55% black), same duration |

### 4. Modal open/close (SmartPick, Episode Player)
| Property | Setting |
|---|---|
| Trigger | Tap (open) / Tap outside or explicit close (close) |
| Animation | Move In from the bottom |
| Duration | 340ms, custom ease (same bezier as the drawer, for a consistent "how overlays move" language across the whole app) |

### 5. Loading → Content reveal (within a modal, no screen change)
| Property | Setting |
|---|---|
| Trigger | Automatic, after a simulated network delay (900ms–1200ms) |
| Matched layers | None — spinner is fully replaced by result content |
| Transition | Fade in (300ms) rather than Smart Animate, since there's no shared geometry between a spinner and a result card |

## Consistency Rule
All screen-to-screen transitions use the same 300–320ms Ease Out timing; all overlay open/close transitions use the same custom bezier. This isn't arbitrary — using two consistent "vocabularies" (one for navigating, one for overlays) is what makes the difference between a screen change and a temporary overlay legible to the user without them having to think about it, reinforcing the flow distinction made in `Prototype_Flow.md`.
