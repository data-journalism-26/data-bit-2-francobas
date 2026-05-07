# Who watches the pollsters?

**Data Bit 2 — Data Journalism**  
**Author:** Franco Bastida  
**Date:** May 2026  

---

This data story examines how polling conflicts of interest shaped perceptions of Hungary’s 2026 recent election, and how removing conflict-flagged pollsters substantially alters the competitiveness of the race.

The project combines polling data scraped from Wikipedia, manually pollster vetting, and publication-style interactive graphics presented in a lightweight HTML layout.

## Core arguments

1. **Some pollsters consistently projected a tighter race** than the final election outcome suggested.  
2. **Conflicts of interest were publicly traceable** and could therefore be incorporated into election modeling.  
3. **Polling itself could become part of the political contest**, especially in polarized systems where institutional credibility is limited.

---

## Technique

- **Programmatic work:** Python (`pandas`, `BeautifulSoup`, `matplotlib`, `statsmodels`) for scraping, cleaning, smoothing and visualization  
- **Polling extraction:** Wikipedia polling table scraped with BeautifulSoup  
- **Trend modeling:** LOWESS-smoothed polling averages for major Hungarian parties  
- **Pollster vetting:** Manual Excel-based review of 13 Hungarian polling firms and institutional affiliations  
- **Interactive presentation:** HTML/CSS article layout with JavaScript chart toggle for GitHack  
- **Design principles:** publication-style typography, muted gridlines, minimal axis clutter, annotation-driven storytelling, direct comparison between modeled datasets  

---

## Repository Structure

```text
├── README.md                         
├── index.html                         # article & layout
├── hungary-polling.ipynb              # scraping, modeling & chart notebook
│
├── figures/
│   ├── hungary_trend_with_excluded.png
│   └── hungary_trend_without_excluded.png
│
└── data/
    ├── pollster-backgroundcheck.xlsx
```

---

## Methodology

- Polling data was scraped from Wikipedia’s opinion polling table for the 2026 Hungarian parliamentary election.
- Polling periods were standardized to the final date of fieldwork.
- Polls whose fieldwork ended after April 5, 2026 were excluded to create a pre-election cutoff (one-week).
- Two datasets were created:
  > one including all pollsters

  > one excluding firms flagged for conflicts of interest
- Polling trends were smoothed using LOWESS averages rather than raw rolling means.

Note: The pollster vetting process relied on a manually researched Excel checklist assessing institutional affiliations, ownership structures and publicly documented political ties.

---

## GitHack view

**[Read the article here](https://raw.githack.com/data-journalism-26/data-bit-2-francobas/main/index.html)**