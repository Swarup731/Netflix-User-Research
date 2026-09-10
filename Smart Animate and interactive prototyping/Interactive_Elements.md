# Interactive Elements — Drawers, Overlays & Floating Headers

Three interactive surface types, all live and functional in `interactive-prototype.html`.

## 1. Floating Header (Home screen)
**Behavior:** transparent over the hero art at scroll position 0; once the user scrolls past ~30px, it gains a solid, blurred dark background and shrinks its vertical padding.

| State | Background | Padding | Trigger |
|---|---|---|---|
| Top (default) | transparent | 14px vertical | Scroll position ≤ 30px |
| Scrolled | `rgba(20,20,20,.92)` + blur | 8px vertical | Scroll position > 30px |

**Why:** at the top of Home, the header should stay out of the way of the hero art (matches the Week 3 mockup). Once scrolled into the content rows, a transparent header would sit illegibly over card thumbnails — the solid+blur background keeps the logo and icons legible without permanently costing vertical space.

## 2. Profile Drawer (side panel)
**Trigger:** tap the profile icon in the Home header.
**Behavior:** slides in from the right edge (280px wide), paired with a scrim that dims the rest of the screen to 55% black. Tapping the scrim (anywhere outside the drawer) or the explicit "Close" row dismisses it.

**Contents:** Manage Profiles, Subscription, Settings, Language, Help — the same items specified under **Profile** in `../Information_Architecture/Site_Map.md`, confirming the drawer is this app's implementation of that IA node rather than a new, undocumented menu.

## 3. SmartPick Modal (bottom sheet overlay)
**Trigger:** tap the SmartPick floating action button (FAB) on Home.
**Behavior:** slides up from the bottom, replacing the screen's normal bottom nav visually (it sits above everything) without navigating away from Home. Contains the mood/time selectors from `../High_Fidelity_Mockups/SmartPick.png`, then swaps its own internal content to a loader and finally a result — all without closing and reopening the sheet.

## 4. Episode Player Overlay
**Trigger:** tap Play or any episode row on Movie Details.
**Behavior:** same bottom-sheet mechanism as SmartPick (shared pattern, not a one-off), immediately shows a loading spinner, then swaps to a "Now Playing" state after a simulated delay.

## Design Rule: One Overlay Mechanism, Reused
Both bottom-sheet overlays (SmartPick, Episode Player) share the exact same open/close mechanics, easing, and scrim behavior — see `Smart_Animate_Transitions.md`. This is deliberate: a person only has to learn what a bottom sheet does once, and every place the app uses one behaves identically. The Profile Drawer uses a visually distinct mechanism (side slide-in, not bottom sheet) specifically *because* it's a different kind of thing — persistent account navigation, not a transient in-context action — and that structural difference is worth signaling through motion, not hidden by reusing the same pattern for everything.

## Floating Header vs. Overlay — Not the Same Thing
The floating header changes its own appearance in response to scroll; it never covers other content or requires a scrim, and it's always part of the base screen. Overlays (drawer, modals) sit in a separate stacking layer above the screen and always pair with a scrim. Keeping these conceptually distinct in the code (`.floating-header` vs `.scrim`/`.drawer`/`.modal`) mirrors how they should be modeled as distinct Figma prototype interactions: one is a per-screen state change, the other is an overlay layer.
