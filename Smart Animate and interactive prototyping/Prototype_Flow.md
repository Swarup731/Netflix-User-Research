# Prototype Flow — Connected Screens

## ⚠️ About "In Figma"
This environment has no Figma access. Instead of Figma's prototype connections (screen → screen with a trigger and transition), the exact same flow is built as **real, working navigation** in [`interactive-prototype.html`](interactive-prototype.html) — open it in any browser and every arrow below is a clickable connection, not a static mockup. Rebuilding this in Figma means recreating each connection listed here as a prototype link with the noted trigger and transition.

![Prototype Screen Flow](prototype-flow.png)

## Connections

| From | Trigger | To | Transition |
|---|---|---|---|
| Home | Tap search icon (header) | Search | Slide + fade (0.32s) |
| Home | Tap any content card | Movie Details | Slide + fade (0.32s) |
| Home | Tap profile icon | Profile Drawer (overlay) | Slide-in from right (0.32s) |
| Home | Tap SmartPick FAB | SmartPick Modal (overlay) | Slide-up from bottom (0.34s) |
| Home | Tap bottom nav "My Netflix" | My Netflix | Slide + fade (0.32s) |
| Search | Tap a search result | Movie Details | Slide + fade (0.32s) |
| Movie Details | Tap back arrow | Home | Slide + fade (reverse) |
| Movie Details | Tap Play or an episode row | Episode Player (overlay) | Slide-up + loading state |
| SmartPick Modal | Tap "Find Something to Watch" | Finding Result (in-place) | Loader → fade-in reveal |
| Finding Result | Tap "Play Now" | Movie Details | Modal closes, base screen navigates |
| My Netflix | Tap back nav items | Home / Search | Slide + fade |

## Why Overlays Aren't Separate "Screens"
The Profile Drawer, SmartPick Modal, and Episode Player are deliberately **not** modeled as full screen-to-screen navigations — they're overlays on top of the current screen (see `Interactive_Elements.md`). This matters for the flow: closing the SmartPick modal returns you to exactly where you were on Home, scroll position and all, rather than "navigating back" to a fresh Home screen. That distinction is why the diagram marks them with dashed lines rather than solid ones.

## Root Screen & Entry Points
**Home** is the root/entry screen. From it, every other screen and overlay is reachable within one interaction — consistent with the "reduce time to find something to watch" objective from the Week 3 style guide's brand overview.
