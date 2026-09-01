# Netflix User Research & Customer Persona Case Study

A UX case study on Netflix: user research → personas → pain points → card sorting → information architecture → user journeys → wireframes → design opportunity. Everything lives in one repository so the story stays coherent end to end.

## ⚠️ Data Disclosure
The interview data, findings, card-sorting results, empathy maps, and personas in this repository are **synthesized examples**, not results from real conducted research — built to demonstrate the full UX pipeline end to end. Full detail and replacement instructions are in [`Research/Research_Objectives.md`](Research/Research_Objectives.md). Before submitting this as a genuine deliverable, replace the example data with your own research.

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
├── Documentation/
│   └── Layout_Decisions.md
│
├── Problem_Statements/
│   └── Problem_Statements.md
│
├── Design_Opportunity/
│   └── Netflix_SmartPick.md
│
└── Slides/
    ├── Netflix_User_Research_Case_Study.pptx
    └── build_deck.js
```

## The Full Story
```
User Research → Personas → Pain Points → Card Sorting → Information Architecture
    → User Journeys → Wireframes → Design Opportunity (SmartPick)
```
Every stage feeds the next: research findings identified pain points (choice overload, search inflexibility) → card sorting turned features into evidence-backed categories → those categories became the site map → the site map's sections anchor the 3 core user journeys → the journeys' friction points determined which 5 screens got wireframed → and `Documentation/Layout_Decisions.md` plus `05-layout-decisions` write out that full reasoning chain.

## Key Milestone Outputs
- 📊 **Slides:** [`Slides/Netflix_User_Research_Case_Study.pptx`](Slides/Netflix_User_Research_Case_Study.pptx)
- 🗺️ **Site Map:** [`Information_Architecture/Site_Map.md`](Information_Architecture/Site_Map.md)
- 🧭 **User Journeys:** [`User_Journeys/`](User_Journeys/)
- ✏️ **Wireframes:** [`Wireframes/`](Wireframes/)
- 📝 **Layout Decisions:** [`Documentation/Layout_Decisions.md`](Documentation/Layout_Decisions.md)

## How to Publish This Repo
```bash
cd Netflix-User-Research
git init
git add .
git commit -m "Netflix UX case study: research, IA, user journeys, wireframes"
git branch -M main
git remote add origin https://github.com/<your-username>/<your-repo-name>.git
git push -u origin main
```
Then submit the resulting GitHub repo URL as your milestone link.
