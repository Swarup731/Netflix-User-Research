# WCAG Contrast Verification

Actual computed contrast ratios (WCAG 2.1 relative-luminance formula, see `contrast_check.py` — re-runnable, not eyeballed) for every important color combination in the design system.

![WCAG Contrast Verification](wcag-contrast-table.png)

## Results Table

| Foreground | Background | Ratio | Result |
|---|---|---|---|
| `#FFFFFF` | `#141414` | 18.42 : 1 | ✅ Pass (AAA) |
| `#FFFFFF` | `#E50914` | 4.79 : 1 | ✅ Pass (AA) |
| `#B3B3B3` | `#141414` | 8.79 : 1 | ✅ Pass (AAA) |
| `#141414` | `#FFFFFF` | 18.42 : 1 | ✅ Pass (AAA) |
| `#FFFFFF` | `#221F1F` (Surface Dark) | 16.36 : 1 | ✅ Pass (AAA) |
| `#B3B3B3` | `#221F1F` (Surface Dark) | 7.80 : 1 | ✅ Pass (AAA) |
| `#FFFFFF` | `#46D369` (Success) | 1.95 : 1 | ❌ **Fail** |
| `#E50914` | `#141414` (normal text) | 3.84 : 1 | ❌ **Fail** |
| `#E50914` | `#141414` (large text ≥18.66px bold) | 3.84 : 1 | ✅ Pass (AA, large only) |

## WCAG Targets
- Normal text: minimum **4.5:1**
- Large text: minimum **3:1**
- UI components: minimum **3:1**

## Failures & Resolutions

### 1. White text on Success green (`#FFFFFF` on `#46D369`) — 1.95:1
The bright brand green is far too light for white text to sit on. Two options were evaluated:
- Darken the green to `#2C8743` → 4.51:1, passes AA, but breaks the brand-approved `#46D369` value.
- **Chosen fix: use `#141414` (black) text on the green badge instead of white.** Black-on-`#46D369` measures **9.46:1 (AAA)** — keeps the exact brand green untouched and comfortably passes. Applied in `../High_Fidelity_Mockups/My_Netflix.png` (download success indicator).

### 2. Red text on black at normal sizes (`#E50914` on `#141414`) — 3.84:1
Fails the 4.5:1 threshold for normal text; only clears the bar at large/bold sizes (3:1 threshold). This is a **usage rule, not a color swap** — the brand red can't simply be lightened without breaking brand consistency.
- **Rule:** red text is reserved for headings, logos, and large badges (≥18.66px bold or ≥24px). It must never be used for small UI labels or nav text.
- **Applied fix:** the active bottom-nav item uses a **white label + small red dot indicator** instead of coloring the label text red — see `../Design_System/Components.md` and every mockup's bottom nav in `../High_Fidelity_Mockups/`.

## Updated Guidance Recorded In
- `../Design_System/Color_System.md` — palette + this file cross-referenced
- `../Design_System/Components.md` — nav and badge component rules reflecting both fixes above

## Method
```
L = 0.2126·R + 0.7152·G + 0.0722·B     (R,G,B linearized from sRGB)
ratio = (L_lighter + 0.05) / (L_darker + 0.05)
```
Run `python3 contrast_check.py` in this folder to reproduce or extend with new pairs.
