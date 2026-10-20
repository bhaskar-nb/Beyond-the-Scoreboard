# Beyond the Scoreboard: Cricket Strategy Intelligence

## 1. Project Overview

Beyond the Scoreboard is a Power BI analytics project that explores batting performance, scoring patterns, and wicket-taking trends across six editions of the ICC Men's Cricket World Cup, spanning 2003 to 2023.

The project transforms ball-by-ball cricket data into interactive dashboards to help users explore differences in scoring across tournament editions, innings phases, and teams.

The analysis focuses on understanding how runs are distributed throughout an innings and how wicket-taking patterns vary across World Cup editions and phases of play.

## 2. Business Problem

Traditional cricket scorecards focus primarily on match results, individual performances, and final scores. However, ball-by-ball data provides opportunities to investigate performance patterns at a more granular level.

This project explores how historical World Cup data can be used to answer questions such as:

- How has total scoring varied across World Cup editions?
- Which innings phase contributes the most runs?
- Which teams have accumulated the most runs across the selected editions?
- How do scoring patterns in powerplay, middle overs, and death overs compare?
- How do wicket-taking patterns vary across tournament editions and innings phases?
- Which bowling teams have recorded the highest number of wickets under the project's current measurement definition?

## 3. Project Objectives

- Analyze total runs across six World Cup editions.
- Compare scoring across powerplay, middle overs, and death overs.
- Rank teams by aggregate runs.
- Explore wicket-taking patterns across tournament editions and innings phases.
- Build interactive Power BI dashboards with tournament and team filters.
- Present cricket performance data through a consistent, easy-to-navigate visual design.

## 4. Dataset Overview

The project uses the `all_matches.csv` ball-by-ball dataset.

| Attribute | Description |
|---|---|
| Dataset file | `all_matches.csv` |
| Initial record count | 141,258 |
| Original column count | 27 |
| Tournament editions | 2003, 2007, 2011, 2015, 2019, 2023 |
| Match identifier | `match_id` |
| Batting team | `batting_team` |
| Bowling team | `bowling_team` |
| Runs off the bat | `runs_off_bat` |
| Extras | `extras` |
| Dismissed player | `player_dismissed` |
| Dismissal type | `wicket_type` |

The dataset contains ball-by-ball records, allowing performance to be analyzed at the delivery level.

## 5. Data Preparation

Power Query was used to prepare the dataset for analysis.

The documented transformations include:

- Creating `Over_Number` from the original `ball` field.
- Creating `Innings_Phase` to group overs into Powerplay, Middle Overs, and Death.
- Creating `Total_Runs` by adding `runs_off_bat` and `extras`.
- Creating `World_Cup_Year` to represent the tournament editions chronologically.
- Creating `Phase_Sort` to control the display order of innings phases.
- Removing selected unnecessary columns.

The innings phases are defined as follows:

| Phase | Over numbers |
|---|---|
| Powerplay | 0–9 |
| Middle Overs | 10–39 |
| Death | 40–49 |

These phase definitions are based on the project's calculated `Over_Number` field.

## 6. Dashboard Design

The Power BI report contains two analytical pages.

### 6.1 Batting Intelligence

The Batting Intelligence dashboard includes:

- Total Runs
- Runs off Bat
- Total Extras
- Total Matches
- Total Teams
- Total Venues
- Total Runs by World Cup Edition
- Runs by Innings Phase
- Top 10 Teams by Total Runs
- Scoring Patterns Across World Cup Editions

Interactive slicers allow users to filter by World Cup Edition and Batting Team.

![Batting Intelligence Dashboard](../Images/Batting%20Overview.png)

### 6.2 Bowling Intelligence

The Bowling Intelligence dashboard includes:

- Bowler Credited Wickets
- Wickets in Powerplay
- Wickets per Match
- Wickets in Death Overs
- Wickets by World Cup Edition and Innings Phase
- Wicket by Innings Phase
- Top 10 Bowling Teams by Wickets
- Wicket-Taking Across Teams and Phases
- Wickets by World Cup Edition

Interactive slicers allow users to filter by World Cup Edition and Bowling Team.

![Bowling Intelligence Dashboard](../Images/Bowling%20Overview.png)

**Calculation note:** Bowling-related measures require validation before their values should be interpreted as definitive cricket statistics. The displayed `Wickets per Match` measure, in particular, needs to be checked against the underlying dismissal records and its intended definition.

## 7. Measures and Calculations

The report uses DAX measures to calculate aggregate performance metrics.

Examples of the documented measures include:

- Total Runs
- Runs Off Bat
- Total Extras
- Total Deliveries
- Matches Analyzed
- Teams Analyzed
- Venues Analyzed
- Total Wickets
- Bowler Credited Wickets
- Wickets Per Match
- Wickets in Powerplay
- Wickets in Death Overs

The exact formulas and definitions should be documented in the data dictionary or a dedicated measures reference after the bowling calculations have been validated.

## 8. Tools and Technologies

- **Power BI Desktop** — Interactive dashboard development.
- **Power Query** — Data transformation and preparation.
- **DAX** — Measures and analytical calculations.
- **CSV** — Source data format.

## 9. Limitations

- The analysis is restricted to the six World Cup editions included in the dataset.
- Aggregate statistics do not explain every tactical or match-specific factor.
- The project does not currently claim to predict match outcomes or recommend optimal tactics.
- Bowling measures must be validated against dismissal types and the distinction between total dismissals and bowler-credited wickets.
- Findings depend on the completeness and accuracy of the source dataset.

## 10. Future Improvements

Potential extensions include:

- Validating all dismissal-related measures.
- Comparing batting and bowling performance under different match conditions.
- Analyzing partnerships and scoring rates.
- Investigating the relationship between wickets lost and innings totals.
- Adding more detailed team-level and match-level comparisons.

## 11. Conclusion

Beyond the Scoreboard demonstrates how ball-by-ball cricket data can be transformed into interactive analytical dashboards.

By examining scoring patterns, innings phases, teams, and wicket-taking trends across multiple World Cup editions, the project provides an interactive foundation for exploring historical cricket performance beyond final scores alone.