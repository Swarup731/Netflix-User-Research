# Card Sorting

> **Note on data:** As with the rest of this repository, no live card-sorting session was run — the results below are a synthesized worked example so the full IA pipeline (cards → categories → site map) is demonstrated end to end. Before treating this as real research, run the open sort with 5-8 real users and the closed sort with a fresh set, then replace the results below.

## Objective
Determine how Netflix users naturally group the app's features and content types, to inform a navigation structure that matches users' mental models rather than internal engineering categories.

## Participants
- **Open sort:** 6 participants (active Netflix subscribers, mixed device use, ages 20s–40s)
- **Closed sort:** 5 participants (different individuals from the open-sort group, same recruiting criteria)

## Cards Used
Home · Movies · TV Shows · New & Popular · My List · Continue Watching · Search · Profile · Notifications · Account · Subscription · Download · Settings · Help Center · Language · Parental Controls · Audio & Subtitles · Watch History · Genres · Recommendations · Trailers · Coming Soon

## Open Sorting Results
Participants were asked: *"Group these Netflix features into categories that make sense to you. You can create your own category names."*

| User-Created Category | Features |
|---|---|
| Discover | Home, Recommendations, New & Popular |
| Watch | Movies, TV Shows, Continue Watching |
| Saved | My List, Downloads |
| Account | Profile, Subscription, Settings |
| Search | Search, Genres |
| Support | Help Center |

Cards that didn't land consistently in one place across participants: **Notifications** (split between Account and Discover), **Trailers** (split between Watch and Discover), **Coming Soon** (split between Discover and Watch), **Parental Controls / Audio & Subtitles / Language** (most participants folded these into Account, 2 kept them as a separate "Playback settings" group).

## Closed Sorting Results
A fresh set of 5 participants sorted the same cards into predefined categories:

| Category | Features |
|---|---|
| Discover | Home, Recommendations, New & Popular, Trailers |
| Content | Movies, TV Shows, Genres |
| My Netflix | My List, Continue Watching, Downloads, Watch History |
| Account | Profile, Subscription, Settings, Notifications |
| Support | Help Center |
| Playback | Audio & Subtitles, Language |

Agreement was strongest for **Discover** and **My Netflix** (both 90%+); **Playback** as its own category had the weakest agreement (68%) — 2 of 5 participants placed Audio & Subtitles and Language under Account instead, treating them as settings rather than a distinct destination.

## Major Patterns
1. **"Finding something to watch" and "watching" are separate mental models.** Discover (browse/recommend) and Content (Movies/TV Shows/Genres) were consistently kept apart, even though both are "content."
2. **Personal/saved content clusters tightly.** My List, Continue Watching, Downloads, and Watch History were grouped together in both sorts with high agreement — users think of these as "my stuff," distinct from the general catalog.
3. **Playback-adjacent settings (language, subtitles, parental controls) are ambiguous.** Users are split on whether these belong with Account or deserve their own space — they're accessed rarely, but in a specific context (mid-setup or mid-playback).
4. **Search is tightly coupled with Genres**, not treated as a fully separate function — supporting a combined "Discover" entry point rather than a standalone top-level Search destination.

## Final IA Decisions
Based on the combined open + closed sort evidence, the navigation is organized into **7 top-level sections**, matching the structure carried into `Information_Architecture/Site_Map.md`:

1. **Home** — Continue Watching, Recommended For You, Trending, New Releases, Popular
2. **Movies** — Action, Comedy, Drama, Horror, Romance
3. **TV Shows** — Drama, Comedy, Crime, Reality, Documentary
4. **New & Popular** — Trending Now, New Releases, Coming Soon
5. **Search** — Search Movies, Search Shows, Genres, Actors
6. **My Netflix** — Continue Watching, My List, Downloads, Watch History
7. **Profile** — Account, Subscription, Settings, Language, Audio & Subtitles, Parental Controls, Help

Playback-related settings (Language, Audio & Subtitles, Parental Controls) were placed under **Profile** rather than given their own top-level section — the closed-sort agreement for a standalone "Playback" category was too weak (68%) to justify the added navigation complexity.
