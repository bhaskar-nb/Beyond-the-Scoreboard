# Analytical Insights — Beyond the Scoreboard

## 1. Overview

This document outlines the analytical perspectives explored in the Beyond the Scoreboard Power BI project.

The project analyzes ball-by-ball data from six editions of the ICC Men's Cricket World Cup: 2003, 2007, 2011, 2015, 2019, and 2023.

The dashboards focus on scoring patterns, team-level batting performance, and wicket-taking trends across tournament editions and innings phases.

## 2. Scoring Trends Across World Cup Editions

**Dashboard visual:** Total Runs by World Cup Edition

This visual compares the aggregate runs recorded in each tournament edition.

It allows users to explore how total scoring differs between editions and identify tournaments with comparatively higher or lower aggregate run totals.

Aggregate totals should be interpreted in the context of the number of matches and deliveries represented in each edition.

## 3. Scoring Across Innings Phases

**Dashboard visual:** Runs by Innings Phase

The dashboard groups overs into three phases:

- Powerplay
- Middle Overs
- Death Overs

Comparing these phases helps users examine how runs are distributed throughout an innings.

The results can support further investigation into scoring patterns, although aggregate runs alone do not establish which phase is most efficient.

## 4. Team-Level Batting Performance

**Dashboard visual:** Top 10 Teams by Total Runs

This visual ranks teams by their aggregate runs across the selected dataset or filter context.

It allows users to compare cumulative batting output between teams.

The ranking represents total runs, not average runs per match, scoring rate, or batting efficiency. Teams with different numbers of matches may not be directly comparable using aggregate totals alone.

## 5. Scoring Patterns Across Editions and Phases

**Dashboard visual:** Scoring Patterns Across World Cup Editions

This line chart compares the aggregate runs recorded in different innings phases across World Cup editions.

It helps users explore how phase-level scoring totals vary between tournaments.

Further analysis using runs per over, scoring rates, and phase-level averages could provide a more balanced comparison of scoring performance.

## 6. Bowling Performance Across World Cup Editions

**Dashboard visual:** Wickets by World Cup Edition

This visual compares wicket totals across tournament editions.

It provides a starting point for examining how wicket-taking outcomes differ between tournaments.

Before drawing conclusions, the underlying wicket calculation must distinguish valid dismissals from delivery records that do not represent a dismissal.

## 7. Wicket-Taking Across Innings Phases

**Dashboard visual:** Wickets by Innings Phase

This visual compares recorded wicket totals across the Powerplay, Middle Overs, and Death phases.

It can help identify where dismissals occur most frequently in aggregate.

However, wicket totals alone do not establish bowling effectiveness. Comparisons should also consider overs bowled, legal deliveries, innings context, and dismissal attribution.

## 8. Team-Level Bowling Performance

**Dashboard visual:** Top 10 Bowling Teams by Wickets

This visual ranks bowling teams according to the report's bowler-credited wicket measure.

It allows users to compare cumulative wicket-taking totals across teams.

The ranking should be interpreted only after the measure has been validated against the source dismissal records and the rules for bowler-credited dismissals.

## 9. Team and Phase Comparison

**Dashboard visual:** Wicket-Taking Across Teams and Phases

The matrix compares teams across innings phases.

It allows users to investigate how each team's recorded wicket totals are distributed between the Powerplay, Middle Overs, and Death phases.

This view supports comparative exploration, but further analysis is required before concluding that a team performs better in a particular phase.

## 10. Interactive Exploration

The report includes slicers for:

- World Cup Edition
- Batting Team
- Bowling Team

These filters allow users to explore the dashboard from different tournament and team perspectives.

Visual interactions are configured to preserve selected overall team rankings where appropriate.

## 11. Verified Dataset-Level Observations

The following aggregate values were recorded during data validation:

| Metric | Value |
|---|---:|
| Total delivery records | 141,258 |
| Distinct matches | 265 |
| Distinct batting teams | 18 |
| Distinct venues | 70 |
| Runs off bat | 114,363 |
| Extras | 7,359 |
| Total runs | 121,722 |

The run totals reconcile:

`114,363 + 7,359 = 121,722`

These figures describe the unfiltered dataset.

They are dataset-level observations rather than evidence of individual team superiority or tournament trends.

## 12. Further Analytical Opportunities

Potential extensions include:

- Comparing runs per over across innings phases.
- Calculating scoring rates using legal deliveries.
- Comparing batting output per match rather than aggregate totals alone.
- Measuring wicket-taking rates per legal delivery or over.
- Separating bowler-credited dismissals from other dismissal types.
- Comparing phase-level performance across individual teams.
- Investigating how wickets lost relate to final innings totals.

## 13. Conclusion

Beyond the Scoreboard provides an interactive way to explore historical Cricket World Cup scoring and wicket-taking patterns.

The dashboards establish a foundation for deeper cricket analytics by combining tournament-level comparisons, phase-based analysis, team rankings, and interactive filtering.

Any strategic conclusions should be based on validated measures and appropriate comparisons rather than aggregate totals alone.