# Data Dictionary — Beyond the Scoreboard

## 1. Overview

This document describes the key source columns, calculated fields, and analytical measures used in the Beyond the Scoreboard Power BI project.

The project uses ball-by-ball data from six editions of the ICC Men's Cricket World Cup, spanning 2003–2023.

## 2. Source Dataset

| Property | Description |
|---|---|
| File | `all_matches.csv` |
| Format | CSV |
| Initial records | 141,258 |
| Original columns | 27 |
| Tournament editions | 2003, 2007, 2011, 2015, 2019, 2023 |
| Power BI table | `all_matches` |

Each row represents a delivery-level record in the source dataset.

## 3. Important Source Columns

| Column | Description | Analytical Purpose |
|---|---|---|
| `match_id` | Match identifier | Counting distinct matches |
| `season` | Original tournament season label | Identifying tournament editions |
| `ball` | Delivery or ball identifier | Deriving the over number |
| `batting_team` | Team batting on the delivery | Team-level batting analysis |
| `bowling_team` | Team bowling on the delivery | Team-level bowling analysis |
| `venue` | Match venue | Venue coverage |
| `runs_off_bat` | Runs scored off the bat | Batting run analysis |
| `extras` | Additional runs recorded on the delivery | Extras analysis |
| `player_dismissed` | Player recorded as dismissed | Dismissal analysis |
| `wicket_type` | Recorded dismissal type | Examining dismissal categories |

## 4. Calculated Columns

### 4.1 Over_Number

**Purpose:** Extract the over number from the original `ball` field.

```powerquery
Number.FromText(Text.BeforeDelimiter([ball], "."))
```

The calculated value is used to group deliveries into innings phases.

### 4.2 Innings_Phase

**Purpose:** Categorize overs into three analytical phases.

| Condition | Phase |
|---|---|
| `Over_Number < 10` | Powerplay |
| `Over_Number >= 10` and `Over_Number < 40` | Middle Overs |
| `Over_Number >= 40` | Death |

This grouping is used to compare scoring and wicket-taking patterns across innings phases.

### 4.3 Total_Runs

**Purpose:** Calculate the total runs recorded for each delivery.

```powerquery
[runs_off_bat] + [extras]
```

The column is aggregated in Power BI to calculate total runs.

### 4.4 World_Cup_Year

**Purpose:** Represent the six tournament editions using chronological year labels.

| Original Season | World Cup Year |
|---|---:|
| `2002/03` | 2003 |
| `2006/07` | 2007 |
| `2010/11` | 2011 |
| `2014/15` | 2015 |
| `2019` | 2019 |
| `2023/24` | 2023 |

### 4.5 Phase_Sort

**Purpose:** Control the display order of innings phases in Power BI visuals.

| Phase | Sort Value |
|---|---:|
| Powerplay | 1 |
| Middle Overs | 2 |
| Death | 3 |

The `Innings_Phase` column is sorted by `Phase_Sort`.

## 5. DAX Measures

The following measures are used in the report.

### 5.1 Total Runs

```dax
Total Runs = SUM('all_matches'[Total_Runs])
```

Calculates the sum of `Total_Runs`.

### 5.2 Runs Off Bat

```dax
Runs Off Bat = SUM('all_matches'[runs_off_bat])
```

Calculates the sum of runs scored off the bat.

### 5.3 Total Extras

```dax
Total Extras = SUM('all_matches'[extras])
```

Calculates the sum of recorded extras.

### 5.4 Total Deliveries

```dax
Total Deliveries = COUNTROWS('all_matches')
```

Counts rows in the table. This represents delivery records, not necessarily legal deliveries.

### 5.5 Matches Analyzed

```dax
Matches Analyzed =
DISTINCTCOUNT('all_matches'[match_id])
```

Counts distinct match identifiers.

### 5.6 Teams Analyzed

```dax
Teams Analyzed =
DISTINCTCOUNT('all_matches'[batting_team])
```

Counts distinct batting-team values in the current filter context.

### 5.7 Venues Analyzed

```dax
Venues Analyzed =
DISTINCTCOUNT('all_matches'[venue])
```

Counts distinct venue values in the current filter context.

## 6. Bowling Measures

The report includes measures for:

- Total Wickets
- Bowler Credited Wickets
- Wickets Per Match
- Wickets in Powerplay
- Wickets in Death Overs

These measures require validation against the source dismissal records before their formulas and results can be treated as definitive.

Total dismissals and bowler-credited wickets are different concepts because some dismissal types are not credited to the bowler.

The final definitions should document the exact DAX formulas used in the report and the dismissal types included or excluded.

## 7. Validation Checks

The following aggregate values were recorded during project preparation.

| Metric | Value |
|---|---:|
| Runs Off Bat | 114,363 |
| Total Extras | 7,359 |
| Total Runs | 121,722 |
| Delivery Records | 141,258 |
| Distinct Matches | 265 |
| Distinct Batting Teams | 18 |
| Distinct Venues | 70 |

The run totals reconcile:

`114,363 + 7,359 = 121,722`

These figures describe the unfiltered dataset and may differ from values displayed when report slicers are applied.

## 8. Filter Context

The report contains interactive slicers for:

- World Cup Edition
- Batting Team on the batting page
- Bowling Team on the bowling page

Measures and visuals may respond differently depending on the configured visual interactions.

## 9. Notes and Limitations

- `Total Deliveries` counts source rows and should not be interpreted as legal balls bowled.
- `Total Runs` includes runs off the bat and recorded extras.
- Innings-phase groupings follow the calculated over-number rules defined in Power Query.
- Bowling statistics should not be published as validated until the dismissal logic has been checked.
- The dataset's original source and redistribution terms should be established before distributing the CSV publicly.