# Netflix Layout Decisions

## 1. Home Screen
The Home screen prioritizes personalized recommendations and Continue Watching because these are frequently used content discovery and access functions. This is backed directly by the earlier research finding that Continue Watching acts as users' default safety net when undecided.

## 2. Navigation
Primary navigation contains the most important destinations: Home, Movies, TV Shows, Search and My Netflix. These map to the top-level sections with the strongest card-sort agreement (see `Research/Card_Sorting.md`), so the nav reflects how users actually group features rather than an internal engineering structure.

## 3. Search
Search is given prominent placement because users frequently use it to find specific movies and shows. It's kept as its own top-level destination — reachable in one tap — rather than nested inside another section, matching the Search Movie journey (`User_Journeys/Search_Movie_Flow.png`).

## 4. Movie Details
The movie details screen places the Play button prominently because starting playback is the primary user action. My List is placed immediately next to it as the secondary action, since saving-for-later is the next most common intent at this screen.

## 5. My Netflix
Saved and previously watched content is grouped under My Netflix (Continue Watching, My List, Downloads, Watch History) to reduce navigation complexity — the card sort showed these consistently clustering together as "my stuff," distinct from the general content catalog.

## 6. SmartPick
SmartPick is designed to reduce decision fatigue by allowing users to select mood, available time and genre before receiving recommendations. This directly targets the "Choice Overload" and "Too many choices, long browsing time" pain points identified in the Find & Watch a Movie journey, and is the same design opportunity carried over from the earlier research case study.

## Traceability
Every decision above follows the same chain used throughout this repository: **card-sort evidence → site map placement → journey friction point → wireframe layout.** Nothing here is a stylistic preference — each choice has a specific research finding or agreement score backing it, documented in the linked files.
