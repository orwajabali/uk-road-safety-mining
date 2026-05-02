# 🚦 UK Road Safety — Data Mining & Pattern Discovery

Mining **8.6 million accident records** from the UK's national road safety database to uncover hidden patterns, identify high-risk conditions, and generate actionable safety recommendations using the full Knowledge Discovery in Databases (KDD) pipeline.

---

## 🎯 What This Project Does

Applies end-to-end data mining on real government data to answer:
> *"What combination of conditions most consistently leads to road accidents — and what can authorities do about it?"*

---

## 🔬 Approach

**1. Data Wrangling**
- Handled 36-column dataset with ~29 features disguised as numerical but representing categories
- Decoded proprietary `-1` missing value convention; converted types accordingly
- Engineered time-of-day and speed-category features

**2. Exploratory Analysis**
- Univariate and multivariate analysis across accident severity, road type, weather, time, and geography
- Identified peak accident hours, high-risk road types, and seasonal trends

**3. Association Rule Mining**
- One-hot encoded categorical features → Apriori algorithm (`support ≥ 0.9`, `confidence ≥ 0.9`)
- Surfaced interpretable rules ranked by lift, support, and confidence
- Translated top rules into concrete policy recommendations

---

## 💡 Sample Insight

> **Rule:** *Non-trunk road + No carriageway hazards → No special site conditions* (confidence: ~98%)
>
> **Takeaway:** Road surface quality alone is a weak predictor of accidents. Driver behavior and vehicle factors matter more — suggesting safety budgets should shift toward behavioral interventions rather than infrastructure alone.

---

## 🛠️ Tech Stack

`Python` · `pandas` · `NumPy` · `Matplotlib` · `Seaborn` · `SciPy` · `mlxtend`

---

## 📁 Key Files

| File | Description |
|---|---|
| `Final_Project.ipynb` | Full analysis — EDA, preprocessing, rule mining |
| `data_subset_2016_2020.ipynb` | Subset extraction script (2016–2020 from 40-year dataset) |
| `Accident_Key.xlsx` | Feature codebook — maps numerical codes to categories |

> Raw dataset: [UK Road Safety Open Data](https://www.data.gov.uk/dataset/cb7ae6f0-4be6-4935-9277-47e5ce24a11f/road-safety-data) (not included — 1.2 GB)

---

## 📊 Scale

| Metric | Value |
|---|---|
| Full dataset | 8.6M rows · 36 features · 40 years |
| Analysis window | 2016–2020 |
| Missing value handling | Multi-strategy (imputation + removal) |
| Rules generated | High-confidence itemsets via Apriori + FP-Growth |
