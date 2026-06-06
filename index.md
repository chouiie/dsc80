---
layout: default
title: "What Types of Recipes Are Healthier?"
---

# 🥗 What Types of Recipes Tend to Be Healthier?

**Chau Nguyen · DSC 80 · UCSD · Food.com Recipes Dataset**

---

## 📌 Introduction

This project investigates the **Food.com Recipes & Ratings dataset** (83,782 recipes) to answer one question:

> **Which recipe categories provide the most protein and the fewest carbohydrates per serving?**

| Column | Description |
|---|---|
| `nutrition` | List: `[calories, total_fat_pdv, sugar_pdv, sodium_pdv, protein_pdv, saturated_fat_pdv, carbohydrates_pdv]` |
| `protein_pdv` | Protein as % daily value |
| `carbohydrates_pdv` | Carbohydrates as % daily value |
| `calories` | Total calories per serving |
| `tags` | Tag list used to classify recipes into categories |
| `minutes` | Preparation and cook time |
| `n_steps` | Number of steps in the recipe |
| `n_ingredients` | Number of distinct ingredients |
| `avg_rating` | Mean user rating (1–5) from the interactions table |

---

## 🧹 Data Cleaning and Exploratory Data Analysis

1. **Unpacked the nutrition column** — parsed string-encoded list into seven named columns using `ast.literal_eval`.
2. **Parsed recipe tags** — same parsing to enable category membership checks.
3. **Created binary category indicators** — one `is_<category>` column per category (meat, vegetables, seafood, desserts, salads, breakfast).
4. **Merged average ratings** — replaced 0-ratings with `NaN`, computed per-recipe means, left-joined onto recipes table.

| name | minutes | n_steps | calories | protein_pdv | carbohydrates_pdv | avg_rating |
|---|---|---|---|---|---|---|
| 1 brownies in the world best ever | 40 | 10 | 138.4 | 3.0 | 6.0 | 4.00 |
| 1 in canada chocolate chip cookies | 45 | 12 | 595.1 | 13.0 | 26.0 | 5.00 |
| 412 broccoli casserole | 40 | 6 | 194.8 | 22.0 | 3.0 | 5.00 |
| millionaire pound cake | 120 | 7 | 878.3 | 20.0 | 39.0 | 5.00 |
| 2000 meatloaf | 90 | 17 | 267.0 | 29.0 | 2.0 | 5.00 |

### 📊 Univariate Analysis — Distribution of Protein

<iframe src="assets/plots/protein_dist.html" width="100%" height="425" frameborder="0"></iframe>

Protein (% DV) is heavily right-skewed. Most recipes deliver under 50% DV with a long tail of high-protein dishes.

### 📊 Bivariate Analysis — Protein by Category

<iframe src="assets/plots/protein_by_category.html" width="100%" height="425" frameborder="0"></iframe>

Meat and seafood have dramatically higher protein. Median protein for meat is ~45% DV — nearly double vegetables and four times desserts.

### 📋 Interesting Aggregates

| Category | Mean Protein (% DV) | Mean Carbs (% DV) | Mean Calories |
|---|---|---|---|
| Meat | 63.8 | 9.9 | 510.7 |
| Seafood | 57.5 | 8.7 | 407.9 |
| Vegetables | 26.0 | 10.6 | 333.1 |
| Breakfast | 24.0 | 13.2 | 365.8 |
| Salads | 19.3 | 8.7 | 309.4 |
| Desserts | 12.1 | 18.9 | 441.1 |

---

## 🔎 Assessment of Missingness

Three columns have missing values: `name` (1), `description` (70), `avg_rating` (2,609 — 3.1%).

**NMAR Analysis:** `description` is likely **NMAR**. Contributors who invest less effort are less likely to write a description — driven by unobserved contributor effort, not any observable column.

### Does `avg_rating` missingness depend on `n_steps`?

- **H₀:** Distribution of `n_steps` is the same whether `avg_rating` is missing or not.
- **H₁:** Recipes with missing `avg_rating` have a different mean `n_steps`.
- **Test statistic:** Difference in mean `n_steps` (missing − not missing) · **α = 0.05**

<iframe src="assets/plots/missingness_nsteps.html" width="100%" height="425" frameborder="0"></iframe>

p-value < 0.001 — reject H₀. Missingness depends on `n_steps` (MAR). Tested `n_ingredients` separately: p > 0.05, missingness is independent of ingredient count.

---

## 🧪 Hypothesis Testing

### Test 1 — Do Meat Recipes Have Higher Protein?

- **H₀:** Meat and non-meat recipes have the same mean protein (% DV).
- **H₁:** Meat recipes have higher mean protein.
- Permutation test, 2,000 shuffles · **α = 0.05**

<iframe src="assets/plots/hyp_test1.html" width="100%" height="425" frameborder="0"></iframe>

Observed difference +41.70% DV is completely outside the null distribution. p-value effectively 0 — reject H₀.

### Test 2 — Do Dessert Recipes Have Higher Carbohydrates?

- **H₀:** Dessert and non-dessert recipes have the same mean carbohydrates (% DV).
- **H₁:** Dessert recipes have higher mean carbohydrates.
- Permutation test, 2,000 shuffles · **α = 0.05**

<iframe src="assets/plots/hyp_test2.html" width="100%" height="425" frameborder="0"></iframe>

Observed difference +9.66% DV falls entirely outside the null distribution. p-value effectively 0 — reject H₀.

| Test | Observed Statistic | p-value | Conclusion |
|---|---|---|---|
| Meat vs. Non-Meat — Protein | +41.70% DV | < 0.001 | Reject H₀ |
| Desserts vs. Non-Desserts — Carbs | +9.66% DV | < 0.001 | Reject H₀ |

---

## 🎯 Framing a Prediction Problem

Predict how many **calories** a recipe contains using only information available at submission time.

- **Type:** Regression · **Response variable:** `calories` · **Metric:** RMSE

---

## 🏗️ Baseline Model

**Linear Regression** in a single `sklearn` Pipeline.

| Feature | Type | Encoding |
|---|---|---|
| `n_ingredients` | Quantitative | StandardScaler |
| `n_steps` | Quantitative | StandardScaler |
| `category` | Nominal | OneHotEncoder (7 levels) |

Train RMSE: ~320 cal · Test RMSE: ~325 cal — not adequate, ~80% relative error.

<iframe src="assets/plots/baseline_resid.html" width="100%" height="425" frameborder="0"></iframe>

Fan-shaped residuals show the model under-predicts high-calorie recipes.

---

## 🚀 Final Model

**Random Forest Regressor** with two engineered features: `log_minutes` (log-transform of cook time) and `fat_x_protein` (total_fat_pdv × protein_pdv interaction).

Best hyperparameters (GridSearchCV, 3-fold CV): `n_estimators=200`, `max_depth=20`, `min_samples_leaf=1`

Train RMSE: ~80 cal · Test RMSE: **~85 cal** · Improvement: **~240 cal**

<iframe src="assets/plots/predicted_vs_actual.html" width="100%" height="425" frameborder="0"></iframe>

<iframe src="assets/plots/feature_importance.html" width="100%" height="425" frameborder="0"></iframe>

`total_fat_pdv` dominates (~62% importance) — fat is the most calorie-dense macronutrient (9 kcal/g). The engineered `fat_x_protein` ranks third, validating our feature engineering.

---

## ⚖️ Fairness Analysis

Does the model perform worse for high-calorie recipes?

- **Group X:** calories ≤ test-set median · **Group Y:** calories > test-set median
- **H₀:** RMSE is the same for both groups · **H₁:** RMSE is higher for high-calorie recipes.
- Permutation test, 2,000 shuffles · **α = 0.05**

| Group | RMSE |
|---|---|
| Low-calorie | ~55 cal |
| High-calorie | ~115 cal |

<iframe src="assets/plots/fairness_perm.html" width="100%" height="425" frameborder="0"></iframe>

p-value < 0.001 — reject H₀. Model is significantly less accurate for high-calorie recipes.
