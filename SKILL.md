---
name: hana-lead-scoring
description: |
  Lead scoring and cold outreach generation for Hana healthcare sales. 
  
  TRIGGERS - Use this skill when user requests:
  - Score/analyze/prioritize healthcare leads or prospects
  - Find wedges/angles/personalization for outreach
  - Generate cold emails for healthcare contacts
  - Process CSV files of leads or contacts
  - Research companies/people for sales outreach
  - Anything mentioning "BHT", "Hana", "Matteo", or healthcare sales
  
  KEYWORDS: lead scoring, cold email, wedge, outreach, healthcare sales, behavioral health, addiction, dental, EHR, patient engagement, BHT attendees
---

# Hana Lead Scoring & Outreach

Score healthcare leads and generate personalized cold outreach using Matteo's proven frameworks.

## Tools Required

- **Web search**: For `/find-wedge` research
- **File operations**: For `/score-leads-bulk` CSV processing
- **Python**: For scoring calculations (optional, can do manually)

## Commands

| Command | Purpose | When to Use |
|---------|---------|-------------|
| `/score-lead` | Score single lead (0-100) | Have one lead to evaluate |
| `/score-leads-bulk` | Process CSV with scores | Have spreadsheet of leads |
| `/generate-outreach` | Create cold email(s) | Ready to write emails |
| `/find-wedge` | Deep research for angles | Need better personalization |

## Quick Start

### Scoring a Lead
```
/score-lead Company: Acme Health, Name: Jane Doe, Title: CEO, Vertical: Behavioral Health
```

### Processing CSV
```
/score-leads-bulk leads.csv --min-score=60
```

### Generating Email
```
/generate-outreach Name: John, Company: HealthTech, Vertical: Dental --type=platform
```

## Scoring Formula

```
SCORE = Title (0-30) + Vertical (0-25) + Company Type (0-20) + Bonuses (0-25)
```

| Score | Priority | Action |
|-------|----------|--------|
| 80-100 | 🔥 Hot | Immediate personalized outreach |
| 60-79 | 🟡 Warm | Prioritize for next batch |
| 40-59 | 🟠 Moderate | Include in campaigns |
| 20-39 | 🔵 Cool | Low priority |
| 0-19 | ⚪ Cold | Skip |

## Wedge Hierarchy

1. **Personal Story** — From LinkedIn bio/posts (BEST)
2. **Company-Specific** — From news/funding/hiring
3. **Vertical** — Industry pain point (FALLBACK)

## Email Types

- **Platform**: Short (<100 words), for tech companies, partnership angle
- **Sequence**: 4-touch campaign for clinics/health systems

## References

Load these as needed:

| File | Contents |
|------|----------|
| `references/scoring-criteria.md` | Full scoring weights, regex patterns, disqualifiers |
| `references/wedge-patterns.md` | Complete wedge library with examples |
| `references/email-frameworks.md` | Templates, voice guide, anti-patterns |
| `references/config.md` | Customizable settings (events, competitors, thresholds) |

## Error Handling

- **Missing required fields**: Request minimum data (name, company, title)
- **Unrecognized vertical**: Default to "Digital Health" (15 points), flag for review
- **No wedge found**: Use vertical fallback, never send without a wedge
- **Invalid email**: Set score to 0, mark as disqualified
- **Empty CSV**: Return error with expected format

