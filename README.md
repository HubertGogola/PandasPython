# ⚽ Polish Football Data Analysis – Pure Pandas Project

This project presents a complete football match data analysis of the Polish Ekstraklasa league using **only the Pandas library in Python**.

It was built with a clear constraint in mind: **no use of external libraries (like NumPy, Matplotlib, Seaborn, or SciPy)**.  
The goal was to master the essential `pandas` functions to explore, group, merge, filter, and summarize real-world football data in a clean and replicable way.

---

## 🎯 Project Objective

> **Demonstrate full data analysis capabilities using only `pandas`, with a focus on football match data.**

Specifically:
- Gain deeper familiarity with Pandas functions (e.g., `.groupby()`, `.merge()`, `.iloc`, etc.)
- Build a clean and consistent pipeline of data exploration
- Derive useful football stats without relying on visualization libraries or Jupyter widgets

---

## 📁 Dataset Overview

- File: `POL.xlsx` (loaded via `pd.read_excel`)
- Matches from Polish Ekstraklasa league (multiple seasons)
- Contains: dates, teams, scores (home/away), match outcomes, time of matches, and betting odds (`PSCH`, `PSCA`, `PSCD`)

---

## 🧠 Key Techniques Used

The following Pandas functions were extensively applied in this project:

| Function         | Description                                     | Usage Count |
|------------------|--------------------------------------------------|-------------|
| `.groupby()`     | Aggregation by team, season, or match time       | 12×         |
| `.merge()`       | Combining goal totals with points per team       | 2×          |
| `.value_counts()`| Counting matches per team (home/away)           | 2×          |
| `.iloc[]`        | Selecting rows by position/index                 | 4×          |
| `.loc[]`         | Selecting rows by condition                      | 1×          |
| `df[...] = ...`  | Creating new columns (e.g., total goals)         | 4×          |
| `read_excel()`   | Reading the original Excel file                  | 1×          |

> No visualizations (`.plot()`, `matplotlib`, `seaborn`) were used intentionally.

---

## 📊 Analyses Performed

- Total and average goals by season
- Home vs away performance
- Most goals in a single match
- Most goal-heavy teams
- Distribution of match times (e.g. when most goals were scored)
- Team points based on match results (3/1/0 system)
- Join/merge operations to compare stats across dimensions

---

## 🧩 Example: Combining Goals + Points via `merge()`

```python
team_stats = pd.merge(
    total_goals.rename('GoalsScored'),
    home_points.rename('HomePoints'),
    left_index=True,
    right_index=True,
    how='inner'
)
