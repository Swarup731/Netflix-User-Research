# Netflix UX Case Study — Full Compilation

A single narrative tying together every phase of this project, end to end. Each section links to the underlying deliverable rather than repeating it in full.

## ⚠️ Data Disclosure
This entire case study — interviews, card sorting, usability tests — uses synthesized example data built to demonstrate a complete, realistic UX pipeline, not a live study. See `Research/Research_Objectives.md` for the standing disclosure. Figma-specific deliverables (mockups, prototype, component library) were built as coded equivalents (SVG/HTML/CSS) since this environment has no Figma access — each relevant folder explains the substitution and how to rebuild natively in Figma.

## 1. The Problem
Research into how people use Netflix on mobile surfaced a consistent pattern: **users spend more time deciding what to watch than actually watching.** Interviews and card sorting pointed at five contributing causes — row overload, over-reliance on "Continue Watching" as a decision shortcut, low trust in recommendations, profile-switching friction, and a weak mobile-to-TV handoff.
→ Full detail: [`Research/Research_Findings.md`](Research/Research_Findings.md)

## 2. Who We Designed For
Three personas emerged from the research and its card-sorted patterns: **Rahul the Binge Watcher** (overwhelmed by choice), **Priya the Casual Viewer** (limited time, wants a quick confident pick), and **Arjun the Explorer** (wants niche/international content standard categories don't serve well).
→ [`Personas/`](Personas/) · [`Empathy_Maps/`](Empathy_Maps/)

## 3. From Features to Structure
An open and closed card sort turned a flat list of 22 app features into 7 evidence-backed navigation sections (Home, Movies, TV Shows, New & Popular, Search, My Netflix, Profile), replacing guesswork about what belongs where with actual agreement scores.
→ [`Research/Card_Sorting.md`](Research/Card_Sorting.md) · [`Information_Architecture/Site_Map.md`](Information_Architecture/Site_Map.md)

## 4. The Core Journeys
Three journeys were mapped end to end — Find & Watch a Movie, Search for a Specific Movie, and the mood-based SmartPick concept — each annotated with pain points and a design opportunity.
→ [`User_Journeys/`](User_Journeys/)

## 5. From Sketch to System
Low-fidelity paper-style wireframes for 5 core screens fed directly into a formal design system: a color palette (`#E50914` / `#141414` / `#221F1F` / `#46D369`), an 8-step typography scale, a 4px spacing scale, and 12-column desktop / 4-column mobile grids.
→ [`Wireframes/`](Wireframes/) · [`Design_System/`](Design_System/) · [`Layout_Grids/`](Layout_Grids/)

## 6. High-Fidelity Screens & Reusable Components
The design system was applied to 5 high-fidelity mockups (Home, Search, Movie Details, My Netflix, SmartPick), then formalized into 9 reusable master components with documented Auto Layout rules, interactive state variants (default/hover/active/focus/disabled), and token-bound spacing.
→ [`High_Fidelity_Mockups/`](High_Fidelity_Mockups/) · [`Component_Library/`](Component_Library/)

## 7. Verifying Accessibility
Every color pairing in active use was checked against WCAG 2.1 thresholds using the actual relative-luminance formula, not estimation. Two real failures were caught and fixed: white text on the success-green badge (switched to black text, 9.46:1) and red text on black at small sizes (restricted to large/bold contexts, with the active-nav pattern redesigned to a white label + red dot instead of red text).
→ [`Accessibility/WCAG_Contrast.md`](Accessibility/WCAG_Contrast.md)

## 8. Making It Interactive
The components and screens were wired into a genuinely interactive prototype — real screen navigation, Smart-Animate-equivalent transitions, a slide-in profile drawer, two bottom-sheet overlays (SmartPick, episode player), a scroll-aware floating header, and three distinct loading patterns (spinner, determinate progress bar, skeleton shimmer) matched to three different kinds of wait.
→ [`Prototype/interactive-prototype.html`](Prototype/interactive-prototype.html) — open directly in a browser, fully clickable.

## 9. Testing It on Real Tasks
6 participants ran 5 tasks each against the interactive prototype. Results were ranked by a composite of success rate, ease score, navigation errors, and time — surfacing SmartPick discoverability (50% success) and search filter clarity (67% success, highest error count) as the two weakest points, against a 100%-success, 4.5/5-ease baseline for basic browsing.
→ [`Usability_Testing/Usability_Test_Results.md`](Usability_Testing/Usability_Test_Results.md) · [`Usability_Testing/Usability_Metrics.md`](Usability_Testing/Usability_Metrics.md)

## 10. Closing the Loop
Three targeted refinements were made directly to the working prototype — a one-time SmartPick discovery nudge, an explicit drawer close button, and a filter-chip multi-select hint — each traced to a specific finding, with an explicit note on what was *not* changed and why (the well-performing Browse & Watch flow was left untouched).
→ [`Usability_Testing/Design_Refinements.md`](Usability_Testing/Design_Refinements.md)

## What This Project Demonstrates
A single, traceable chain from a research finding to a shipped interaction: "users spend too much time deciding what to watch" → card-sorted IA → a journey identifying the friction → a wireframed and componentized SmartPick screen → a WCAG-verified, interactive implementation → a usability test that found it wasn't yet discoverable → a specific fix, applied and documented. Every claim in this case study is one click away from the artifact that backs it.

## Repository Map
See the top-level [`README.md`](README.md) for the full folder structure and the complete "research → prototype → testing" pipeline diagram.

## Portfolio Presentation
A slide-formatted version of this same narrative, suitable for presenting live, is at [`Final_Case_Study/Netflix_UX_Case_Study_Final.pptx`](Final_Case_Study/Netflix_UX_Case_Study_Final.pptx).
