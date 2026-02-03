---
description: Score a single healthcare lead and identify wedges for personalized outreach
argument-hint: Company: X, Name: Y, Title: Z, Vertical: W
---

# /score-lead

## Purpose
Analyze a single lead, calculate score (0-100), identify best wedge, recommend outreach approach.

## Input Requirements
**Required**: name, company, title
**Recommended**: vertical, linkedinDescription, email

## Output
SCORE: 0-100
PRIORITY: Hot/Warm/Moderate/Cool/Cold
WEDGE_TYPE: Personal Story/Company-Specific/Vertical  
WEDGE_LINE: personalized angle
RECOMMENDED_TEMPLATE: Platform/Sequence

## Instructions
1. Parse lead data
2. Check disqualifiers (scoring-criteria.md)
3. Calculate: Title(30) + Vertical(25) + Company(20) + Bonus(25)
4. Find wedge (wedge-patterns.md)
5. Template: Platform=tech, Sequence=clinics
