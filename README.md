# Statistical Analysis of Dot Balls in T20 Cricket

**Course:** Applied Analytics (MATH1324)
**Institution:** RMIT University
**Type:** Individual Statistical Analysis Project
**Author:** Sowmiya Kumar

---

## 📌 Project Overview

This project investigates **dot ball frequency in men’s T20 International cricket** using ball-by-ball data and formal statistical testing.
The analysis focuses on whether dot balls occur significantly more often during **Powerplay overs (1–6)** compared to **Non-Powerplay overs (7–20)**, and whether dot-ball pressure is associated with **match outcomes**.

The work combines **large-scale data wrangling**, **exploratory visualisation**, and **hypothesis-driven statistical testing**, presented as an **RMarkdown slideshow**.

---

## 🎯 Research Questions

1. **Primary question**

   > Is there a statistically significant difference in dot ball frequency between Powerplay and Non-Powerplay overs in men’s T20 Internationals?

2. **Secondary question**

   > Is dot ball usage associated with match outcomes in the second innings (successful vs unsuccessful chases)?

---

## 📂 Repository Structure

```
.
├── data/
│   └── ball_by_ball_it20.csv        # Raw Kaggle dataset (425k+ deliveries)
│
├── T20Analysis.rmd                  # RMarkdown analysis (code + narrative)
├── analysis_report.pdf              # Rendered presentation slides
│
├── README.md
```

---

## 📊 Dataset

* **Source:** Kaggle – Ball-by-Ball IT20
  [https://www.kaggle.com/datasets/jamiewelsh2/ball-by-ball-it20](https://www.kaggle.com/datasets/jamiewelsh2/ball-by-ball-it20)
* **Scope:** Men’s T20 Internationals
* **Size:** 425,119 deliveries
* **Features:** 35 ball-level variables (runs, extras, over, innings, dismissal info, match outcome indicators)

---

## 🧠 Methodology

### 1. Data Cleaning & Feature Engineering

* Filtered to **legal deliveries only**
* Enforced cricket-rule constraints:

  * Overs 1–20
  * `batter_runs ≤ 6`, `extra_runs ≤ 5`
* Engineered key variables:

  * `dot_ball` → no runs scored on a delivery
  * `over_type` → Powerplay (1–6) vs Non-Powerplay (7–20)
* Standardised categorical fields for consistency

---

### 2. Exploratory Analysis

* Computed dot ball percentages by:

  * Over
  * Over phase (Powerplay, Middle, Death)
  * Innings
* Visualised:

  * Dot ball trends across overs
  * Heatmaps of dot-ball pressure
  * Phase-wise comparisons
* Observed:

  * Highest dot ball pressure in early overs
  * Gradual reduction toward death overs
  * Slightly higher dot rates in second innings (chasing pressure)

---

### 3. Hypothesis Testing – Two-Proportion Test

**Test:** Two-sample test for equality of proportions

* **H₀:** Dot ball proportion is equal in Powerplay and Non-Powerplay overs
* **Hₐ:** Dot ball proportions differ

Method:

* Used `prop.test()` in R
* Estimated:

  * Proportions
  * 95% confidence interval
  * p-value

**Result:**

* p-value < 0.001
* Confidence interval does not include 0

✅ **Conclusion:** Dot balls are **significantly more frequent in Powerplay overs**.

---

### 4. Association with Match Outcomes

* Focused on **second-innings matches**
* Aggregated dot ball rates per match
* Categorised matches into:

  * High dot-ball usage
  * Low dot-ball usage (median split)
* Performed **Chi-Square Test of Independence** between:

  * Dot usage category
  * Match outcome (win/loss)

**Finding:**

* Strong, statistically significant association (p < 0.001)
* Teams facing fewer dot balls were more likely to win chases

---

## 📈 Key Results

* **Powerplay dot balls:** ~49%
* **Middle overs:** ~36%
* **Death overs:** ~31%
* **Statistical significance:** Strong evidence against equal proportions
* **Match impact:** Dot-ball pressure meaningfully relates to outcomes

---

## 🧰 Tech Stack

* **Language:** R
* **Libraries:**

  * dplyr
  * ggplot2
  * readr
  * lubridate
* **Output:**

  * RMarkdown slideshow (PDF)

---

## 📄 Artifacts

* 📊 **RMarkdown Analysis:** `T20Analysis.rmd`
* 📑 **Presentation Slides:** `analysis_report.pdf`
* 📁 **Dataset:** `data/ball_by_ball_it20.csv` (original source linked above)

---

## 📌 Notes

* Dataset is publicly available via Kaggle.
* Project completed as part of **Applied Analytics coursework at RMIT University**.
* Analysis is for educational and portfolio demonstration purposes only.


