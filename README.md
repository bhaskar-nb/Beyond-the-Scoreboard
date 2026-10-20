# 🏏 Beyond the Scoreboard: Cricket Strategy Intelligence

### An Interactive Power BI Analysis of ICC Men's Cricket World Cup Data (2003–2023)

Beyond the Scoreboard is a cricket analytics project built with Power BI to explore batting performance, scoring patterns, and wicket-taking trends across six editions of the ICC Men's Cricket World Cup.

The project transforms ball-by-ball cricket data into interactive dashboards that allow users to investigate tournament-level trends, compare teams, and explore performance across different innings phases.

---

## 📊 Dashboard Preview

### 1. World Cup Overview

Explore scoring patterns, tournament-level run totals, innings phases, and team batting performance.

![World Cup Overview](Images/Batting%20Overview.png)

### 2. Bowling Intelligence

Explore wicket-taking patterns across World Cup editions, innings phases, and bowling teams.

![Bowling Intelligence](Images/Bowling%20Overview.png)

---

## 🎯 Business Problem

Traditional cricket scorecards summarize match results and individual performances. However, ball-by-ball data provides opportunities to explore scoring and wicket-taking patterns in greater detail.

This project investigates how historical World Cup data can be used to understand:

- How aggregate scoring varies across tournament editions.
- How runs are distributed across innings phases.
- Which teams have accumulated the most runs.
- How wicket-taking totals vary across editions and phases.
- How teams compare across different stages of an innings.

The goal is to make historical cricket data easier to explore through interactive visual analytics.

---

## ✨ Project Features

### Batting Intelligence
- Total runs, runs off the bat, and extras.
- Tournament-level scoring comparisons.
- Runs by innings phase.
- Top 10 teams by aggregate runs.
- Scoring patterns across World Cup editions.
- Interactive World Cup Edition and Batting Team slicers.

### Bowling Intelligence
- Wicket-related KPI measures.
- Wickets by World Cup edition.
- Wickets by innings phase.
- Top 10 bowling teams by the report's credited-wicket measure.
- Team-level comparison across innings phases.
- Interactive World Cup Edition and Bowling Team slicers.

### Interactive Exploration
- Tournament-level filtering.
- Team-level filtering.
- Consistent dark-themed dashboard design.
- Purple, magenta, and lavender visual styling.

---

## 🗂️ Project Structure

```text
Beyond-the-Scoreboard/
│
├── Dataset/
│   └── all_matches.csv
│
├── Images/
│   ├── Batting Overview.png
│   └── Bowling Overview.png
│
├── docs/
│   ├── project_documentation.md
│   ├── data_dictionary.md
│   └── insights.md
│
├── Beyond the Scoreboard.pbix
├── README.md
└── .gitignore
```

---

## 📁 Dataset Overview

The project uses the `all_matches.csv` ball-by-ball dataset.

| Attribute | Details |
|---|---|
| Initial records | 141,258 |
| Original columns | 27 |
| Distinct matches | 265 |
| Distinct batting teams | 18 |
| Distinct venues | 70 |
| Tournament editions | 2003, 2007, 2011, 2015, 2019, 2023 |

The analysis uses delivery-level records to examine aggregate scoring and wicket-taking patterns.

**Dataset note:** Before redistributing the source CSV through GitHub, verify its original source, license, and redistribution permissions.

---

## 🛠️ Tools and Technologies

- **Power BI Desktop** — Dashboard development and data visualization.
- **Power Query** — Data cleaning, transformation, and calculated columns.
- **DAX** — Measures and analytical calculations.
- **CSV** — Source data format.

---

## 🔄 Data Preparation

Power Query was used to prepare the source data for analysis.

Key transformations included:

- Deriving over numbers from the original ball identifier.
- Grouping overs into Powerplay, Middle Overs, and Death phases.
- Calculating total runs from runs off the bat and extras.
- Creating chronological World Cup year labels.
- Adding a numeric sort column for innings phases.
- Removing selected unnecessary columns.

The report groups overs as follows:

| Phase | Over numbers |
|---|---|
| Powerplay | 0–9 |
| Middle Overs | 10–39 |
| Death | 40–49 |

---

## 📈 Key Analytical Questions

The dashboards help explore the following questions:

1. How does aggregate scoring vary across World Cup editions?
2. How are runs distributed across innings phases?
3. Which teams have accumulated the highest aggregate run totals?
4. How do phase-level scoring totals vary across tournaments?
5. How do recorded wicket totals vary across editions and innings phases?
6. How do bowling teams compare across different innings phases?

The dashboard supports descriptive analysis. It does not currently claim to predict match outcomes or determine optimal cricket strategies.

---

## 📚 Documentation

Detailed project documentation is available in the `docs/` directory.

- [Project Documentation](docs/project_documentation.md)
- [Data Dictionary](docs/data_dictionary.md)
- [Analytical Insights](docs/insights.md)

---

## ⚠️ Data and Metric Limitations

- Aggregate team totals may be affected by differences in the number of matches played.
- Total delivery records should not be interpreted as legal deliveries.
- Total dismissals and bowler-credited wickets are different measures.
- Bowling-related calculations must be validated against dismissal types before being interpreted as definitive cricket statistics.
- Dataset redistribution permissions should be checked before publishing the original CSV.

---

## 🚀 Future Improvements

Potential extensions include:

- Comparing scoring rates across innings phases.
- Analyzing team performance per match.
- Validating wicket attribution and dismissal categories.
- Comparing bowling effectiveness using legal deliveries or overs bowled.
- Investigating partnerships and innings progression.
- Expanding the analysis with additional match-level context.

---

## 👤 Author

**Bhaskar Nakka**

Computer Science Engineering Graduate | Aspiring Data Engineer

- GitHub: [bhaskar-nb](https://github.com/bhaskar-nb)
- LinkedIn: [Bhaskar Nakka](https://www.linkedin.com/in/bhaskar-nakka/)

---

## ⭐ Project Summary

Beyond the Scoreboard demonstrates how Power BI, Power Query, and DAX can transform ball-by-ball cricket data into interactive visual analysis.

The project provides a foundation for exploring historical World Cup scoring and wicket-taking patterns beyond traditional scorecards.