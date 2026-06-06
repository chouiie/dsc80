---
layout: default
title: "What Types of Recipes Are Healthier?"
---

<style>
  body { max-width: 750px; margin: 0 auto; padding: 2rem 1.5rem; font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif; font-size: 16px; line-height: 1.8; color: #111; }
  h1 { font-size: 1.8rem; margin-bottom: 0.2rem; }
  h2 { font-size: 1.25rem; margin-top: 3rem; margin-bottom: 0.5rem; border-bottom: 1px solid #ddd; padding-bottom: 0.3rem; }
  h3 { font-size: 1rem; margin-top: 2rem; margin-bottom: 0.3rem; }
  p { margin: 0.6rem 0 1rem; }
  table { border-collapse: collapse; width: 100%; margin: 0.8rem 0 1.2rem; font-size: 0.88rem; }
  th { border-bottom: 2px solid #111; padding: 0.4rem 0.6rem; text-align: left; }
  td { border-bottom: 1px solid #ddd; padding: 0.4rem 0.6rem; }
  code { background: #f4f4f4; padding: 0.1em 0.3em; border-radius: 3px; font-size: 0.85em; }
  iframe { width: 100%; height: 420px; border: 1px solid #ddd; display: block; margin: 0.8rem 0 0.4rem; border-radius: 3px; }
  .caption { font-size: 0.82rem; color: #555; margin-bottom: 1.5rem; }
  .meta { color: #555; font-size: 0.9rem; margin-bottom: 2.5rem; }
  hr { border: none; border-top: 1px solid #ddd; margin: 2.5rem 0; }
</style>

# 🥗 What Types of Recipes Tend to Be Healthier?

<p class="meta">Chau Nguyen · DSC 80 · UCSD · Food.com Recipes Dataset</p>

---

## 📌 Introduction

This project investigates the **Food.com Recipes & Ratings dataset** (83,782 recipes) to answer one question:

> **Which recipe categories provide the most protein and the fewest carbohydrates per serving?**

Relevant columns:

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

**Cleaning steps:**

1. **Unpacked the nutrition column** — parsed the string-encoded list into seven named columns using `ast.literal_eval`.
2. **Parsed recipe tags** — same parsing to enable category membership checks.
3. **Created binary category indicators** — one `is_<category>` column per category (meat, vegetables, seafood, desserts, salads, breakfast).
4. **Merged average ratings** — replaced 0-ratings with `NaN`, computed per-recipe means, and left-joined onto the recipes table.

**Cleaned DataFrame (first 5 rows):**

| name | minutes | n_steps | calories | protein_pdv | carbohydrates_pdv | avg_rating |
|---|---|---|---|---|---|---|
| 1 brownies in the world best ever | 40 | 10 | 138.4 | 3.0 | 6.0 | 4.00 |
| 1 in canada chocolate chip cookies | 45 | 12 | 595.1 | 13.0 | 26.0 | 5.00 |
| 412 broccoli casserole | 40 | 6 | 194.8 | 22.0 | 3.0 | 5.00 |
| millionaire pound cake | 120 | 7 | 878.3 | 20.0 | 39.0 | 5.00 |
| 2000 meatloaf | 90 | 17 | 267.0 | 29.0 | 2.0 | 5.00 |

### 📊 Univariate Analysis — Distribution of Protein

<iframe src="assets/plots/protein_dist.html" frameborder="0"></iframe>
<p class="caption">Protein (% DV) is heavily right-skewed. Most recipes deliver under 50% DV, with a long tail of high-protein dishes.</p>

### 📊 Bivariate Analysis — Protein by Category

<iframe src="assets/plots/protein_by_category.html" frameborder="0"></iframe>
<p class="caption">Meat and seafood have dramatically higher protein than other categories. Median protein for meat is ~45% DV — nearly double vegetables and four times desserts.</p>

### 📋 Interesting Aggregates

| Category | Mean Protein (% DV) | Mean Carbs (% DV) | Mean Calories |
|---|---|---|---|
| Meat | 63.8 | 9.9 | 510.7 |
| Seafood | 57.5 | 8.7 | 407.9 |
| Vegetables | 26.0 | 10.6 | 333.1 |
| Breakfast | 24.0 | 13.2 | 365.8 |
| Salads | 19.3 | 8.7 | 309.4 |
| Desserts | 12.1 | 18.9 | 441.1 |

Meat and seafood dominate on protein while keeping carbs low. Desserts are the clear outlier — lowest protein, highest carbs.

---

## 🔎 Assessment of Missingness

After merging, three columns have missing values: `name` (1), `description` (70), and `avg_rating` (2,609 — 3.1%).

**NMAR Analysis:** `description` is likely **NMAR**. Contributors who invest less effort are also less likely to write a description — the missingness is driven by an unobserved characteristic (contributor effort), not any observable column. To make it MAR we would need data like total submissions per contributor or a profile completeness score.

### Does `avg_rating` missingness depend on `n_steps`?

- **H₀:** The distribution of `n_steps` is the same whether `avg_rating` is missing or not.
- **H₁:** Recipes with missing `avg_rating` have a different mean `n_steps`.
- **Test statistic:** Difference in mean `n_steps` (missing − not missing) · **α = 0.05**

<iframe src="assets/plots/missingness_nsteps.html" frameborder="0"></iframe>
<p class="caption">p-value < 0.001 — we reject H₀. Missingness of avg_rating depends on n_steps (MAR). We also tested n_ingredients and found p > 0.05 — missingness is independent of ingredient count.</p>

---

## 🧪 Hypothesis Testing

### Test 1 — Do Meat Recipes Have Higher Protein?

- **H₀:** Meat and non-meat recipes have the same mean protein (% DV).
- **H₁:** Meat recipes have a higher mean protein (% DV).
- **Test statistic:** Mean protein (meat) − Mean protein (non-meat) · Permutation test, 2,000 shuffles · **α = 0.05**

<iframe src="assets/plots/hyp_test1.html" frameborder="0"></iframe>
<p class="caption">Observed difference of +41.70% DV is completely outside the null distribution. p-value effectively 0 — we reject H₀.</p>

### Test 2 — Do Dessert Recipes Have Higher Carbohydrates?

- **H₀:** Dessert and non-dessert recipes have the same mean carbohydrates (% DV).
- **H₁:** Dessert recipes have higher mean carbohydrates (% DV).
- **Test statistic:** Mean carbs (desserts) − Mean carbs (non-desserts) · Permutation test, 2,000 shuffles · **α = 0.05**

<iframe src="assets/plots/hyp_test2.html" frameborder="0"></iframe>
<p class="caption">Observed difference of +9.66% DV falls entirely outside the null distribution. p-value effectively 0 — we reject H₀.</p>

| Test | Observed Statistic | p-value | Conclusion |
|---|---|---|---|
| Meat vs. Non-Meat — Protein | +41.70% DV | < 0.001 | Reject H₀ |
| Desserts vs. Non-Desserts — Carbs | +9.66% DV | < 0.001 | Reject H₀ |

---

## 🎯 Framing a Prediction Problem

**Predict how many calories a recipe contains** using only information available at submission time.

- **Type:** Regression
- **Response variable:** `calories`
- **Metric:** RMSE — penalises large errors more than MAE, which is appropriate since a 500-calorie error is qualitatively worse than a 50-calorie one.
- **Features:** `n_ingredients`, `n_steps`, `minutes`, category tags, and macro PDV values (all known at submission time).

---

## 🏗️ Baseline Model

**Linear Regression** in a single `sklearn` Pipeline.

| Feature | Type | Encoding |
|---|---|---|
| `n_ingredients` | Quantitative | StandardScaler |
| `n_steps` | Quantitative | StandardScaler |
| `category` | Nominal | OneHotEncoder (7 levels) |

Train RMSE: ~320 cal · Test RMSE: ~325 cal

Not adequate — the average recipe has ~400 calories, making this an ~80% relative error. Step count and ingredient count are weak proxies for caloric density.

<iframe src="assets/plots/baseline_resid.html" frameborder="0"></iframe>
<p class="caption">Fan-shaped residuals show the model systematically under-predicts high-calorie recipes.</p>

---

## 🚀 Final Model

**Random Forest Regressor** in a single `sklearn` Pipeline with two engineered features.

**Engineered features:**
- `log_minutes` — log-transform of cook time to handle right skew.
- `fat_x_protein` — interaction term (`total_fat_pdv × protein_pdv`) to capture high-fat, high-protein recipes that sit in a distinct calorie tier.

**Best hyperparameters** (GridSearchCV, 3-fold CV): `n_estimators=200`, `max_depth=20`, `min_samples_leaf=1`

Train RMSE: ~80 cal · Test RMSE: **~85 cal** · Improvement over baseline: **~240 cal**

<iframe src="assets/plots/predicted_vs_actual.html" frameborder="0"></iframe>
<p class="caption">Points cluster tightly along the perfect-prediction diagonal for most recipes. Some scatter remains for very high-calorie recipes (>1,500 cal).</p>

<iframe src="assets/plots/feature_importance.html" frameborder="0"></iframe>
<p class="caption">total_fat_pdv dominates (~62% importance) because fat is the most calorie-dense macronutrient (9 kcal/g). The engineered fat_x_protein interaction ranks third — validating our feature-engineering rationale. This dominance also explains the fairness issue below.</p>

---

## ⚖️ Fairness Analysis

**Does the model perform worse for high-calorie recipes?**

- **Group X:** Recipes with calories ≤ test-set median
- **Group Y:** Recipes with calories > test-set median
- **Metric:** RMSE
- **H₀:** RMSE is roughly the same for both groups.
- **H₁:** RMSE is higher for high-calorie recipes.
- **Test statistic:** RMSE(high) − RMSE(low) · Permutation test, 2,000 shuffles · **α = 0.05**

| Group | RMSE |
|---|---|
| Low-calorie recipes | ~55 cal |
| High-calorie recipes | ~115 cal |

<iframe src="assets/plots/fairness_perm.html" frameborder="0"></iframe>
<p class="caption">p-value < 0.001 — we reject H₀. The model is significantly less accurate for high-calorie recipes. Rich, calorie-dense dishes combine high-fat and high-sugar ingredients in ways that are harder to capture even with the engineered interaction term.</p>

---

<p style="color:#888; font-size:0.82rem; text-align:center;">DSC 80 Final Project · Chau Nguyen · UCSD · Food.com Recipes Dataset</p>
