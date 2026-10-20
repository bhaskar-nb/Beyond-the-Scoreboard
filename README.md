# Beyond the Scoreboard: Cricket Strategy Intelligence

An interactive Power BI project exploring batting output, innings-phase scoring, and wicket-taking patterns across six editions of the ICC Men's Cricket World Cup (2003–2023).

## Dashboard Preview

### Batting Intelligence
![Batting Intelligence Dashboard](Images/Batting%20Overview.png)

Explore run totals, extras, tournament comparisons, phase-level scoring, and team batting totals.

### Bowling Intelligence
![Bowling Intelligence Dashboard](Images/Bowling%20Overview.png)

Explore recorded wicket patterns across tournaments, innings phases, and bowling teams. Bowling measures are documented as provisional pending dismissal-logic validation.

## Project Objectives

- Compare aggregate scoring across World Cup editions.
- Explore how runs are distributed across Powerplay, Middle Overs, and Death phases.
- Compare teams by aggregate runs in the selected dataset and filter context.
- Examine recorded wicket patterns across editions and innings phases.
- Build interactive report pages that make ball-by-ball data easier to explore.

## Key Performance Indicators

The following are dataset-level validation figures from the unfiltered source data, not slicer-dependent dashboard results.

| Metric | Value |
|---|---:|
| Delivery records | 141,258 |
| Distinct matches | 265 |
| Distinct batting teams | 18 |
| Distinct venues | 70 |
| Runs off bat | 114,363 |
| Extras | 7,359 |
| Total runs | 121,722 |

**Validation check:** Runs off bat + extras = total runs (114,363 + 7,359 = 121,722). Delivery records should not be interpreted as legal deliveries.

## Dashboard Analysis

### Batting Intelligence
- Total runs, runs off bat, and extras.
- Aggregate runs by World Cup edition.
- Runs by innings phase.
- Top 10 teams by aggregate runs.
- Scoring patterns across World Cup editions.

### Bowling Intelligence
- Recorded wicket measures by World Cup edition.
- Wickets by innings phase.
- Top 10 bowling teams by the report's credited-wicket measure.
- Team comparisons across innings phases.

Aggregate totals can be affected by differences in match counts and opportunities. The team rankings describe cumulative totals, not scoring rate or performance per match.

## Interactive Filters

The report includes slicers for:
- **World Cup Edition** on the batting and bowling pages.
- **Batting Team** on the batting page.
- **Bowling Team** on the bowling page.

Visuals and measures respond to the selected filter context according to the report's configured interactions.

## Dataset

The project uses `Dataset/all_matches.csv`, a ball-by-ball dataset containing 141,258 records and 27 original columns, as documented for this project.

| Attribute | Details |
|---|---|
| Tournament editions | 2003, 2007, 2011, 2015, 2019, 2023 |
| Match identifier | `match_id` |
| Team fields | `batting_team`, `bowling_team` |
| Runs fields | `runs_off_bat`, `extras` |
| Dismissal fields | `player_dismissed`, `wicket_type` |

The report groups overs using the project's calculated `Over_Number` field:

| Phase | Over numbers |
|---|---|
| Powerplay | 0–9 |
| Middle Overs | 10–39 |
| Death | 40–49 |

**Source and licensing note:** Verify the dataset's original source, license, and redistribution permissions before sharing the CSV publicly.

## Tools & Skills

- **Power BI Desktop** — report design and data visualization
- **Power Query** — data cleaning and transformations
- **DAX** — analytical measures
- **CSV** — source data format

Skills demonstrated include data preparation, KPI design, descriptive analysis, comparative analysis, dashboard development, and documenting metric limitations.

## Repository Structure

```text
Beyond-the-Scoreboard/
├── Dataset/
│   └── all_matches.csv
├── Images/
│   ├── Batting Overview.png
│   └── Bowling Overview.png
├── docs/
│   ├── project_documentation.md
│   ├── data_dictionary.md
│   └── insights.md
├── Beyond the Scoreboard.pbix
├── README.md
└── .gitignore
```

## How to Use

1. Download or clone this repository.
2. Open `Beyond the Scoreboard.pbix` in Power BI Desktop.
3. If Power BI prompts for the CSV location, update the source path to your local copy of `Dataset/all_matches.csv`.
4. Use the World Cup Edition and team slicers to explore the report.
5. Refer to the `docs/` directory for project documentation, field definitions, and analysis notes.

## Scope & Limitations

- This is descriptive analysis of six historical tournament editions, not a live cricket data product.
- Aggregate runs are not adjusted for matches played, legal deliveries, or other context unless a specific visual or measure states otherwise.
- Delivery-row count is not equivalent to legal balls bowled.
- Total dismissals and bowler-credited wickets are different. The bowling measures—especially credited wickets and wickets per match—require validation against dismissal types and the intended calculation before being interpreted as definitive cricket statistics.
- The project does not claim to predict match outcomes or identify optimal tactics.
- Dataset origin and redistribution permissions should be confirmed before public redistribution.

## Documentation

- [Project Documentation](docs/project_documentation.md)
- [Data Dictionary](docs/data_dictionary.md)
- [Analytical Insights](docs/insights.md)

## Author

**Bhaskar Nakka**  
Computer Science Engineering Graduate | Aspiring Data Engineer

- GitHub: [bhaskar-nb](https://github.com/bhaskar-nb)
- LinkedIn: [Bhaskar Nakka](https://www.linkedin.com/in/bhaskar-nakka/)

---

Beyond the Scoreboard demonstrates how Power BI, Power Query, and DAX can turn ball-by-ball cricket data into interactive historical analysis of batting and wicket-taking patterns.
