# Netflix User Research & Customer Persona Case Study

A UX case study on Netflix: user research → personas → pain points → card sorting → information architecture → user journeys → wireframes → design opportunity. Everything lives in one repository so the story stays coherent end to end.

## ⚠️ Data Disclosure
The interview data, findings, card-sorting results, empathy maps, and personas in this repository are **synthesized examples**, not results from real conducted research — built to demonstrate the full UX pipeline end to end. Full detail and replacement instructions are in [`Research/Research_Objectives.md`](Research/Research_Objectives.md). Before submitting this as a genuine deliverable, replace the example data with your own research.

**On Figma:** the high-fidelity mockups in `Mockups/` were built as coded SVG artifacts (this environment has no Figma access), styled precisely to the tokens in `Design_System/`. Each includes an `.svg` source that imports cleanly into Figma as editable vectors if a native `.fig` file is required — see `Mockups/README.md`.

## Repository Structure

```
Netflix-User-Research/
│
├── README.md
│
├── Research/
│   ├── Research_Objectives.md
│   ├── Interview_Questionnaire.md
│   ├── Interview_Data.xlsx
│   ├── Research_Findings.md
│   └── Card_Sorting.md
│
├── Empathy_Maps/
│   ├── Binge_Watcher.md
│   ├── Casual_Viewer.md
│   └── Content_Explorer.md
│
├── Personas/
│   ├── Persona_Binge_Watcher.md
│   ├── Persona_Casual_Viewer.md
│   └── Persona_Explorer.md
│
├── Information_Architecture/
│   ├── Site_Map.md
│   └── Netflix_Site_Map.png
│
├── User_Journeys/
│   ├── README.md
│   ├── Find_Movie_Flow.png
│   ├── Search_Movie_Flow.png
│   └── SmartPick_Flow.png
│
├── Wireframes/
│   ├── Home_Wireframe.jpg
│   ├── Search_Wireframe.jpg
│   ├── Movie_Details_Wireframe.jpg
│   ├── My_Netflix_Wireframe.jpg
│   └── SmartPick_Wireframe.jpg
│
├── Design_System/
│   ├── Color_System.md
│   ├── Typography.md
│   ├── Components.md
│   ├── color-swatch.png
│   └── typography-scale.png
│
├── Layout_Grids/
│   ├── Layout_Grid.md
│   ├── Desktop_12_Column.png / .svg
│   └── Mobile_4_Column.png / .svg
│
├── Component_Library/
│   ├── README.md
│   ├── Master_Components.md
│   ├── Auto_Layout_Specs.md
│   ├── Component_States.md
│   ├── Responsive_Card_Templates.md
│   ├── Spacing_Tokens.md
│   └── *.png                       (visual references for each)
│
├── Prototype/
│   ├── README.md
│   ├── interactive-prototype.html  (real, working, clickable prototype)
│   ├── Prototype_Flow.md
│   ├── Smart_Animate_Transitions.md
│   ├── Interactive_Elements.md
│   ├── Loaders_Progress_Indicators.md
│   └── prototype-flow.png
│
├── Usability_Testing/
│   ├── README.md
│   ├── Usability_Test_Script.md
│   ├── Usability_Test_Results.md
│   ├── Usability_Test_Data.xlsx
│   ├── Usability_Metrics.md
│   ├── Design_Refinements.md
│   └── usability-metrics.png
│
├── Final_Case_Study/
│   ├── README.md
│   ├── Netflix_UX_Case_Study.md     (full written case study)
│   ├── Netflix_UX_Case_Study_Final.pptx  (12-slide portfolio deck)
│   └── build_deck.js
│
├── High_Fidelity_Mockups/
│   ├── README.md
│   ├── Home.png / .svg
│   ├── Search.png / .svg
│   ├── Movie_Details.png / .svg
│   ├── My_Netflix.png / .svg
│   └── SmartPick.png / .svg
│
├── Accessibility/
│   ├── WCAG_Contrast.md
│   ├── wcag-contrast-table.png
│   └── contrast_check.py
│
├── Documentation/
│   └── Layout_Decisions.md
│
├── Problem_Statements/
│   └── Problem_Statements.md
│
├── Design_Opportunity/
│   └── Netflix_SmartPick.md
│
├── Slides/
│   ├── Netflix_User_Research_Case_Study.pptx
│   └── build_deck.js
│
└── Style_Guide/
    └── Netflix_UX_Style_Guide.pdf     (9-page compiled style guide)
```

## The Full Story
```
User Research → Personas → Pain Points → Card Sorting → Information Architecture
    → User Journeys → Wireframes → Design System → Layout Grids → High-Fidelity Mockups
    → WCAG Accessibility Audit → PDF Style Guide → Master Components & Auto Layout
    → Component States → Responsive Card Templates → Spacing Tokens
    → Interactive Prototype (screen flows, Smart Animate, overlays, loaders)
    → Usability Testing → Ranked Metrics → Design Refinements → Final Case Study
```
Every stage feeds the next: research findings identified pain points → card sorting turned features into evidence-backed categories → those categories became the site map → the site map anchors the core user journeys → journey friction points determined which screens got wireframed → the wireframes' layout decisions were formalized into a design system and grid → that system was applied to 5 high-fidelity mockups → every color pairing used was WCAG-audited, with 2 real failures caught and fixed → the whole system compiled into a printable PDF style guide → every element in those mockups was formalized into a reusable master component with Auto Layout, interactive states, and token-bound spacing → those components were wired into a fully clickable interactive prototype → real usability testing on that prototype ranked task performance and surfaced two genuine weak points → three targeted refinements were applied directly back into the prototype → and the entire chain is compiled into one final case study and portfolio deck.

## Key Milestone Outputs
- 📊 **Slides (final portfolio deck):** [`Final_Case_Study/Netflix_UX_Case_Study_Final.pptx`](Final_Case_Study/Netflix_UX_Case_Study_Final.pptx)
- 📖 **Full written case study:** [`Final_Case_Study/Netflix_UX_Case_Study.md`](Final_Case_Study/Netflix_UX_Case_Study.md)
- 🗺️ **Site Map:** [`Information_Architecture/Site_Map.md`](Information_Architecture/Site_Map.md)
- 🧭 **User Journeys:** [`User_Journeys/`](User_Journeys/)
- ✏️ **Wireframes:** [`Wireframes/`](Wireframes/)
- 🎨 **Design System:** [`Design_System/`](Design_System/)
- 📐 **Layout Grids:** [`Layout_Grids/Layout_Grid.md`](Layout_Grids/Layout_Grid.md)
- 🧩 **Component Library (masters, auto layout, states, tokens):** [`Component_Library/`](Component_Library/)
- 🖼️ **High-Fidelity Mockups:** [`High_Fidelity_Mockups/`](High_Fidelity_Mockups/)
- ✅ **WCAG Accessibility Audit:** [`Accessibility/WCAG_Contrast.md`](Accessibility/WCAG_Contrast.md)
- 📕 **PDF Style Guide:** [`Style_Guide/Netflix_UX_Style_Guide.pdf`](Style_Guide/Netflix_UX_Style_Guide.pdf)
- 🎬 **Interactive Prototype:** [`Prototype/interactive-prototype.html`](Prototype/interactive-prototype.html)
- 🧪 **Usability Testing & Refinements:** [`Usability_Testing/`](Usability_Testing/)
- 📝 **Layout Decisions:** [`Documentation/Layout_Decisions.md`](Documentation/Layout_Decisions.md)

## Repository
**https://github.com/Swarup731/Netflix-User-Research**

## How to Publish This Repo
```bash
cd Netflix-User-Research
git init
git add .
git commit -m "Netflix UX case study: research, IA, user journeys, wireframes"
git branch -M main
git remote add origin https://github.com/Swarup731/Netflix-User-Research.git
git push -u origin main
```
Then submit the resulting GitHub repo URL as your milestone link.
