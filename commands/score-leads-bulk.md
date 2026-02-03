---
description: Process a CSV file of leads with scores, wedges, and prioritization
argument-hint: path/to/leads.csv [--min-score=60] [--output=scored.csv]
---

# /score-leads-bulk

## Purpose
Process entire CSV of leads: score each, identify wedges, output prioritized list.

## Arguments
- Input CSV path (required)
- --output: Output file path (default: scored_leads.csv)
- --min-score: Minimum score threshold (default: 40)
- --limit: Max leads to output

## Output CSV Columns
Original columns + score, priority, wedge_type, wedge_line, recommended_template, vertical_detected

## Instructions
1. Load CSV, detect encoding
2. Map columns (see config.md)
3. Score each lead per scoring-criteria.md
4. Find wedges per wedge-patterns.md
5. Sort by score descending
6. Filter by --min-score
7. Output CSV + summary stats

## Summary Stats
- Score distribution (Hot/Warm/Moderate/Cool/Cold)
- Top verticals
- Wedge quality breakdown
- Top 5 leads
