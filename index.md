---
layout: default
title: "What Types of Recipes Are Healthier?"
---

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,300;0,400;0,500;0,700;1,300;1,400&family=Roboto+Mono:wght@400;600&display=swap');

:root {
  --pink-50:  #fff0f6;
  --pink-100: #ffe0ee;
  --pink-200: #ffb3d1;
  --pink-400: #f472b6;
  --pink-500: #ec4899;
  --pink-600: #db2777;
  --pink-700: #be185d;
  --ink:      #1f1225;
  --muted:    #7d4e6a;
  --border:   #f0c6dc;
  --warm:     #fff7fb;
  --cream:    #fffafd;
  --green:    #166534;
  --red:      #991b1b;
  --blue:     #1d4ed8;
}

*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

body {
  background: var(--cream);
  color: var(--ink);
  font-family: 'Roboto', Arial, sans-serif;
  font-size: 17px;
  line-height: 1.75;
}

/* ── Header ── */
.site-header {
  background: linear-gradient(135deg, #db2777 0%, #f472b6 50%, #fb7eb5 100%);
  padding: 3rem 2rem 2.5rem;
  text-align: center;
  position: relative;
  overflow: hidden;
}
.site-header::before {
  content: '🍽️';
  position: absolute;
  font-size: 8rem;
  opacity: 0.08;
  top: -1rem;
  left: 2rem;
}
.site-header::after {
  content: '🥗';
  position: absolute;
  font-size: 7rem;
  opacity: 0.08;
  bottom: -1rem;
  right: 2rem;
}
.site-header .kicker {
  font-family: 'Roboto Mono', monospace;
  font-size: 0.72rem;
  letter-spacing: 0.18em;
  text-transform: uppercase;
  color: #ffe4f0;
  margin-bottom: 0.75rem;
}
.site-header h1 {
  font-family: 'Roboto', Arial, sans-serif;
  font-size: clamp(1.7rem, 5vw, 3rem);
  font-weight: 700;
  color: #fff;
  line-height: 1.2;
  max-width: 820px;
  margin: 0 auto 1rem;
}
.site-header .byline {
  font-style: italic;
  color: #ffe0ee;
  font-size: 0.95rem;
  font-weight: 300;
}

/* ── Nav ── */
.toc-nav {
  background: var(--pink-700);
  padding: 0.65rem 2rem;
  display: flex;
  flex-wrap: wrap;
  gap: 0.3rem 1.2rem;
  justify-content: center;
}
.toc-nav a {
  font-family: 'Roboto', Arial, sans-serif;
  font-size: 0.78rem;
  font-weight: 500;
  letter-spacing: 0.06em;
  text-transform: uppercase;
  color: #ffd6ea;
  text-decoration: none;
  padding: 0.2rem 0;
  border-bottom: 2px solid transparent;
  transition: color 0.2s, border-color 0.2s;
}
.toc-nav a:hover { color: #fff; border-color: #fff; }

/* ── Content ── */
.content { max-width: 860px; margin: 0 auto; padding: 3rem 1.5rem 5rem; }

/* ── Section headers ── */
.section-header {
  display: flex;
  align-items: center;
  gap: 0.8rem;
  margin: 3.5rem 0 1.25rem;
  padding-bottom: 0.6rem;
  border-bottom: 3px solid var(--pink-200);
}
.section-header .step-label {
  font-family: 'Roboto Mono', monospace;
  font-size: 0.65rem;
  font-weight: 600;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  color: #fff;
  background: var(--pink-500);
  padding: 0.25rem 0.6rem;
  border-radius: 999px;
  white-space: nowrap;
}
.section-header h2 {
  font-family: 'Roboto', Arial, sans-serif;
  font-size: 1.6rem;
  font-weight: 700;
  color: var(--pink-700);
}

h3 {
  font-family: 'Roboto', Arial, sans-serif;
  font-size: 1.1rem;
  font-weight: 700;
  color: var(--pink-600);
  margin: 2rem 0 0.65rem;
}

p { margin-bottom: 1rem; }

/* ── Stats row ── */
.stats-row {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
  margin: 1.5rem 0 2rem;
}
.stat-card {
  background: linear-gradient(135deg, var(--pink-500), var(--pink-600));
  border-radius: 12px;
  padding: 1.1rem 1.4rem;
  flex: 1;
  min-width: 140px;
  color: #fff;
  box-shadow: 0 4px 12px rgba(219,39,119,0.25);
}
.stat-card .num {
  font-family: 'Roboto', Arial, sans-serif;
  font-size: 2rem;
  font-weight: 700;
  line-height: 1;
}
.stat-card .label {
  font-size: 0.72rem;
  font-weight: 500;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  opacity: 0.85;
  margin-top: 0.3rem;
}

/* ── Column table ── */
.col-table {
  width: 100%;
  border-collapse: collapse;
  font-size: 0.88rem;
  margin: 1.2rem 0 1.8rem;
  border-radius: 8px;
  overflow: hidden;
  border: 1px solid var(--border);
}
.col-table th {
  font-family: 'Roboto', Arial, sans-serif;
  font-size: 0.72rem;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  font-weight: 700;
  background: var(--pink-600);
  color: #fff;
  padding: 0.6rem 1rem;
  text-align: left;
}
.col-table td {
  padding: 0.55rem 1rem;
  border-bottom: 1px solid var(--border);
  vertical-align: top;
}
.col-table tr:nth-child(even) td { background: var(--pink-50); }
.col-table code {
  font-family: 'Roboto Mono', monospace;
  font-size: 0.78rem;
  background: var(--pink-100);
  color: var(--pink-700);
  padding: 0.1em 0.35em;
  border-radius: 4px;
}

/* ── Cleaning steps ── */
.cleaning-steps { margin: 1rem 0 1.5rem; }
.cleaning-step {
  display: flex;
  gap: 1rem;
  margin-bottom: 1rem;
  align-items: flex-start;
}
.step-num {
  font-family: 'Roboto', Arial, sans-serif;
  font-size: 0.78rem;
  font-weight: 700;
  background: var(--pink-500);
  color: #fff;
  width: 1.8rem;
  height: 1.8rem;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
  margin-top: 0.15rem;
  box-shadow: 0 2px 6px rgba(236,72,153,0.35);
}
.step-text { flex: 1; }

/* ── DataFrame head ── */
.df-head {
  overflow-x: auto;
  margin: 1.2rem 0 1.8rem;
  border: 1px solid var(--border);
  border-radius: 10px;
  box-shadow: 0 2px 8px rgba(219,39,119,0.08);
}
.df-head table {
  border-collapse: collapse;
  font-size: 0.77rem;
  font-family: 'Roboto Mono', monospace;
  white-space: nowrap;
  min-width: 100%;
}
.df-head th {
  background: var(--pink-600);
  color: #fff;
  padding: 0.45rem 0.9rem;
  text-align: left;
  font-weight: 600;
}
.df-head td {
  padding: 0.4rem 0.9rem;
  border-bottom: 1px solid var(--border);
}
.df-head tr:nth-child(even) td { background: var(--pink-50); }

/* ── Plot embed ── */
.plot-wrap {
  background: #fff;
  border: 1px solid var(--border);
  border-radius: 10px;
  overflow: hidden;
  margin: 1.2rem 0 0.5rem;
  box-shadow: 0 2px 10px rgba(219,39,119,0.08);
}
.plot-wrap iframe {
  width: 100%;
  height: 420px;
  border: none;
  display: block;
}
.plot-caption {
  font-size: 0.83rem;
  color: var(--muted);
  font-style: italic;
  margin: 0.4rem 0 1.8rem;
  padding-left: 0.75rem;
  border-left: 3px solid var(--pink-300, #f9a8d4);
}

/* ── Agg table ── */
.agg-table {
  width: 100%;
  border-collapse: collapse;
  font-size: 0.88rem;
  margin: 1.2rem 0 0.5rem;
  border-radius: 10px;
  overflow: hidden;
  border: 1px solid var(--border);
}
.agg-table th {
  font-family: 'Roboto', Arial, sans-serif;
  font-size: 0.68rem;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  font-weight: 700;
  background: var(--pink-600);
  color: #fff;
  padding: 0.55rem 1rem;
  text-align: right;
}
.agg-table th:first-child { text-align: left; }
.agg-table td {
  padding: 0.6rem 1rem;
  border-bottom: 1px solid var(--border);
  text-align: right;
}
.agg-table td:first-child {
  text-align: left;
  font-weight: 500;
}
.agg-table tr:nth-child(even) td { background: var(--pink-50); }
.agg-table .best  { color: var(--green); font-weight: 700; }
.agg-table .worst { color: var(--red);   font-weight: 700; }

/* ── Callout boxes ── */
.callout {
  border-left: 4px solid var(--pink-500);
  background: var(--pink-50);
  padding: 1rem 1.2rem;
  margin: 1.2rem 0 1.6rem;
  border-radius: 0 8px 8px 0;
  font-size: 0.92rem;
}
.callout.orange { border-color: #f97316; background: #fff7ed; }
.callout.green  { border-color: #16a34a; background: #f0fdf4; }
.callout strong.tag {
  display: block;
  margin-bottom: 0.4rem;
  font-family: 'Roboto Mono', monospace;
  font-size: 0.68rem;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  color: var(--pink-600);
}

/* ── Hypothesis cards ── */
.hyp-cards { display: flex; flex-wrap: wrap; gap: 1rem; margin: 1.5rem 0; }
.hyp-card {
  flex: 1; min-width: 240px;
  border: 1px solid var(--border);
  border-radius: 12px;
  overflow: hidden;
  box-shadow: 0 2px 10px rgba(219,39,119,0.1);
}
.hyp-card-head {
  background: linear-gradient(135deg, var(--pink-600), var(--pink-500));
  color: #fff;
  padding: 0.65rem 1rem;
  font-family: 'Roboto', Arial, sans-serif;
  font-size: 0.75rem;
  font-weight: 700;
  letter-spacing: 0.05em;
  text-transform: uppercase;
}
.hyp-card-body { padding: 1.1rem; background: #fff; }
.hyp-card-body .metric {
  font-family: 'Roboto', Arial, sans-serif;
  font-size: 1.8rem;
  font-weight: 700;
  color: var(--pink-600);
  line-height: 1;
  margin-bottom: 0.3rem;
}
.hyp-card-body .metric.orange { color: #ea580c; }
.hyp-card-body .verdict {
  font-family: 'Roboto Mono', monospace;
  font-size: 0.7rem;
  color: var(--green);
  letter-spacing: 0.08em;
  text-transform: uppercase;
  margin-top: 0.6rem;
  font-weight: 600;
}
.hyp-card-body p { font-size: 0.85rem; color: var(--muted); margin: 0.35rem 0 0; }

/* ── Results table ── */
.results-table {
  width: 100%;
  border-collapse: collapse;
  font-size: 0.85rem;
  margin: 1.5rem 0;
  border-radius: 10px;
  overflow: hidden;
  border: 1px solid var(--border);
}
.results-table th {
  font-family: 'Roboto', Arial, sans-serif;
  font-size: 0.68rem;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  font-weight: 700;
  background: var(--pink-600);
  color: #fff;
  padding: 0.55rem 0.9rem;
  text-align: left;
}
.results-table td {
  padding: 0.6rem 0.9rem;
  border-bottom: 1px solid var(--border);
}
.results-table tr:nth-child(even) td { background: var(--pink-50); }
.results-table .reject { color: var(--green); font-weight: 600; }

/* ── Footer ── */
.site-footer {
  background: linear-gradient(135deg, var(--pink-700), var(--pink-600));
  color: #ffd6ea;
  text-align: center;
  padding: 2rem;
  font-family: 'Roboto', Arial, sans-serif;
  font-size: 0.82rem;
  margin-top: 4rem;
  letter-spacing: 0.05em;
}
.site-footer .emoji-row {
  font-size: 1.4rem;
  margin-bottom: 0.5rem;
  letter-spacing: 0.2em;
}

@media (max-width: 600px) {
  .stats-row, .hyp-cards { flex-direction: column; }
  .section-header { flex-wrap: wrap; }
}
</style>

<header class="site-header">
  <div class="kicker">DSC 80 · Food.com Recipes Dataset · Fall 2024</div>
  <h1>What Types of Recipes Tend to Be Healthier?</h1>
  <p class="byline">An investigation into protein and carbohydrate content across recipe categories &nbsp;·&nbsp; Chau Nguyen</p>
</header>

<nav class="toc-nav">
  <a href="#introduction">Introduction</a>
  <a href="#cleaning">Data Cleaning</a>
  <a href="#eda">Exploratory Analysis</a>
  <a href="#missingness">Missingness</a>
  <a href="#hypothesis">Hypothesis Testing</a>
</nav>

<div class="content">

<!-- ══════════════════════════════════════════════════════════ STEP 1 -->
<div class="section-header" id="introduction">
  <span class="step-label">Step 1</span>
  <h2>🌸 Introduction</h2>
</div>

<p>
  With social media full of competing dietary advice — high-protein, low-carb, plant-based, keto —
  it can be hard to know which types of food are actually nutritionally dense. This project uses the
  <strong>Food.com Recipes &amp; Ratings dataset</strong> to answer one concrete question:
</p>

<div class="callout">
  <strong class="tag">💡 Central Question</strong>
  Which recipe categories on Food.com tend to be healthier — specifically, which categories provide the most protein and the fewest carbohydrates per serving?
</div>

<p>
  Understanding this matters for anyone trying to eat well. Protein content is a proxy for satiety
  and muscle maintenance, while carbohydrate density (especially from sugar) is closely linked to
  metabolic health. By mapping these nutrients across recipe categories, we can offer data-driven
  guidance on which cuisine types to seek out or limit.
</p>

<div class="stats-row">
  <div class="stat-card"><div class="num">83,782</div><div class="label">Recipes</div></div>
  <div class="stat-card"><div class="num">731,927</div><div class="label">Interactions</div></div>
  <div class="stat-card"><div class="num">6</div><div class="label">Categories analysed</div></div>
  <div class="stat-card"><div class="num">7</div><div class="label">Nutrition columns</div></div>
</div>

<h3>📋 Relevant Columns</h3>

<table class="col-table">
  <thead>
    <tr><th>Column</th><th>Description</th></tr>
  </thead>
  <tbody>
    <tr><td><code>nutrition</code></td><td>A list encoding <em>[calories, total_fat_pdv, sugar_pdv, sodium_pdv, protein_pdv, saturated_fat_pdv, carbohydrates_pdv]</em> — all % Daily Value except calories.</td></tr>
    <tr><td><code>protein_pdv</code></td><td>Protein content as % of daily recommended value. Extracted from <code>nutrition</code>.</td></tr>
    <tr><td><code>carbohydrates_pdv</code></td><td>Carbohydrate content as % daily value. Extracted from <code>nutrition</code>.</td></tr>
    <tr><td><code>calories</code></td><td>Total calories per serving. Extracted from <code>nutrition</code>.</td></tr>
    <tr><td><code>tags</code></td><td>A list of descriptive tags (e.g. <code>'meat'</code>, <code>'desserts'</code>, <code>'low-carb'</code>) used to classify recipes into categories.</td></tr>
    <tr><td><code>minutes</code></td><td>Total preparation and cook time in minutes.</td></tr>
    <tr><td><code>n_steps</code></td><td>Number of steps in the recipe instructions.</td></tr>
    <tr><td><code>n_ingredients</code></td><td>Number of distinct ingredients used.</td></tr>
    <tr><td><code>avg_rating</code></td><td>Mean user rating (1–5) across all interactions, merged from the interactions table.</td></tr>
  </tbody>
</table>

<!-- ══════════════════════════════════════════════════════════ STEP 2 -->
<div class="section-header" id="cleaning">
  <span class="step-label">Step 2</span>
  <h2>🧹 Data Cleaning</h2>
</div>

<p>The raw data required several cleaning steps before analysis was possible:</p>

<div class="cleaning-steps">
  <div class="cleaning-step">
    <div class="step-num">1</div>
    <div class="step-text"><strong>Unpack the nutrition column.</strong> Each row stored nutrition as a Python-list string like <code>"[138.4, 10.0, 50.0, 3.0, 3.0, 19.0, 6.0]"</code>. We used <code>ast.literal_eval</code> to parse each string into a real list and then split the seven values into separate, named columns (<code>calories</code>, <code>protein_pdv</code>, <code>carbohydrates_pdv</code>, etc.). This made every nutrient directly queryable and plottable.</div>
  </div>
  <div class="cleaning-step">
    <div class="step-num">2</div>
    <div class="step-text"><strong>Parse recipe tags.</strong> The <code>tags</code> column was also stored as a string representation of a list. We applied the same parsing step so we could search for category membership (e.g. whether a recipe has the tag <code>'meat'</code>).</div>
  </div>
  <div class="cleaning-step">
    <div class="step-num">3</div>
    <div class="step-text"><strong>Create binary category indicators.</strong> For each of the six food categories of interest (<em>meat, vegetables, seafood, desserts, salads, breakfast</em>), we created a binary column <code>is_&lt;category&gt;</code> (1 = recipe has that tag, 0 = it does not). Recipes can belong to multiple categories simultaneously.</div>
  </div>
  <div class="cleaning-step">
    <div class="step-num">4</div>
    <div class="step-text"><strong>Merge in average ratings.</strong> Ratings of 0 in the interactions table represent "no rating given" (not an actual score), so we replaced them with <code>NaN</code> before computing the per-recipe mean. We then left-joined these averages onto the recipes table on the recipe <code>id</code>, preserving all 83,782 recipes even those with no interactions.</div>
  </div>
</div>

<h3>📊 Cleaned DataFrame (first 5 rows)</h3>

<div class="df-head">
  <table>
    <thead>
      <tr><th>name</th><th>minutes</th><th>n_steps</th><th>calories</th><th>protein_pdv</th><th>carbohydrates_pdv</th><th>avg_rating</th></tr>
    </thead>
    <tbody>
      <tr><td>1 brownies in the world best ever</td><td>40</td><td>10</td><td>138.4</td><td>3.0</td><td>6.0</td><td>4.00</td></tr>
      <tr><td>1 in canada chocolate chip cookies</td><td>45</td><td>12</td><td>595.1</td><td>13.0</td><td>26.0</td><td>5.00</td></tr>
      <tr><td>412 broccoli casserole</td><td>40</td><td>6</td><td>194.8</td><td>22.0</td><td>3.0</td><td>5.00</td></tr>
      <tr><td>millionaire pound cake</td><td>120</td><td>7</td><td>878.3</td><td>20.0</td><td>39.0</td><td>5.00</td></tr>
      <tr><td>2000 meatloaf</td><td>90</td><td>17</td><td>267.0</td><td>29.0</td><td>2.0</td><td>5.00</td></tr>
    </tbody>
  </table>
</div>

<!-- ══════════════════════════════════════════ EDA -->
<div class="section-header" id="eda">
  <span class="step-label">Step 2 cont.</span>
  <h2>🔍 Exploratory Data Analysis</h2>
</div>

<h3>📈 Univariate Analysis — Distribution of Protein</h3>

<div class="plot-wrap">
  <iframe src="assets/plots/protein_dist.html" loading="lazy"></iframe>
</div>
<p class="plot-caption">
  The distribution of protein (% DV) is heavily right-skewed. The vast majority of recipes deliver under 50% DV of protein, with a long tail of high-protein dishes. This skew reflects the breadth of Food.com: most recipes are side dishes, desserts, or snacks, with a smaller subset of protein-heavy mains.
</p>

<h3>📦 Bivariate Analysis — Protein by Recipe Category</h3>

<div class="plot-wrap">
  <iframe src="assets/plots/protein_by_category.html" loading="lazy"></iframe>
</div>
<p class="plot-caption">
  Meat and seafood recipes show dramatically higher protein distributions than plant-based or dessert categories. The median protein for meat recipes sits around 45% DV — nearly double that of vegetables (≈22%) and almost four times that of desserts (≈8%). This visual already hints strongly at the answer to our central question.
</p>

<h3>🍱 Interesting Aggregates</h3>

<p>Grouping by category and computing mean nutritional values reveals a clear protein-carb trade-off across recipe types:</p>

<table class="agg-table">
  <thead>
    <tr>
      <th>Category</th>
      <th>Mean Protein (% DV)</th>
      <th>Mean Carbs (% DV)</th>
      <th>Mean Calories</th>
    </tr>
  </thead>
  <tbody>
    <tr><td>Meat</td>      <td class="best">63.8</td> <td>9.9</td>              <td>510.7</td></tr>
    <tr><td>Seafood</td>   <td class="best">57.5</td> <td>8.7</td>              <td>407.9</td></tr>
    <tr><td>Vegetables</td><td>26.0</td>              <td>10.6</td>             <td>333.1</td></tr>
    <tr><td>Breakfast</td> <td>24.0</td>              <td>13.2</td>             <td>365.8</td></tr>
    <tr><td>Salads</td>    <td>19.3</td>              <td>8.7</td>              <td>309.4</td></tr>
    <tr><td>Desserts</td>  <td class="worst">12.1</td><td class="worst">18.9</td><td>441.1</td></tr>
  </tbody>
</table>
<p class="plot-caption">
  Meat and seafood dominate on protein while keeping carbohydrates low. Salads are surprisingly low-carb but also low-protein. Desserts are the clear outlier: lowest protein and highest carbohydrates — the least nutritionally dense category by both metrics.
</p>

<!-- ══════════════════════════════════════════════════════════ STEP 3 -->
<div class="section-header" id="missingness">
  <span class="step-label">Step 3</span>
  <h2>🔎 Assessment of Missingness</h2>
</div>

<h3>🔬 NMAR Analysis</h3>

<p>
  After merging, three columns contain missing values: <code>name</code> (1 missing),
  <code>description</code> (70 missing), and <code>avg_rating</code> (2,609 missing — 3.1% of recipes).
</p>

<p>
  We believe <code>description</code> is likely <strong>NMAR (Not Missing At Random)</strong>.
  Contributors who invest less effort in their recipe submission — perhaps submitting quickly or
  casually — are also less likely to write a description. The missingness is driven by an
  unobserved characteristic of the contributor (effort or engagement level), not by any column
  we can observe in the dataset. To make this missingness MAR, we would need additional data
  such as a contributor's historical activity level, profile completeness score, or total number
  of recipes submitted.
</p>

<h3>Missingness Dependency: Does <code>avg_rating</code> depend on <code>n_steps</code>?</h3>

<div class="callout purple">
  <strong class="tag">⚙️ Permutation Test Setup</strong>
  <strong>Null hypothesis:</strong> The distribution of <code>n_steps</code> is the same whether <code>avg_rating</code> is missing or not.<br>
  <strong>Alternative:</strong> Recipes with missing <code>avg_rating</code> have a different mean <code>n_steps</code>.<br>
  <strong>Test statistic:</strong> Difference in mean <code>n_steps</code> (missing − not missing).<br>
  <strong>Significance level:</strong> α = 0.05
</div>

<div class="plot-wrap">
  <iframe src="assets/plots/missingness_nsteps.html" loading="lazy"></iframe>
</div>
<p class="plot-caption">
  The observed difference (1.49 more steps for recipes with missing ratings) falls far into the tail of the null distribution. With a p-value &lt; 0.001, we reject the null: <strong>the missingness of <code>avg_rating</code> is dependent on <code>n_steps</code></strong>, making it MAR. Longer, more complex recipes appear less likely to receive ratings — perhaps users interact more with simpler, quicker recipes.
</p>

<p>
  We also tested whether missingness of <code>avg_rating</code> depends on <code>n_ingredients</code>.
  That permutation test yielded a p-value &gt; 0.05, meaning we fail to reject the null —
  <strong>missingness appears independent of <code>n_ingredients</code></strong>.
  This gives us confidence that the dependency observed with <code>n_steps</code> is specific to
  recipe complexity (steps), not simply to recipe size (ingredients).
</p>

<!-- ══════════════════════════════════════════════════════════ STEP 4 -->
<div class="section-header" id="hypothesis">
  <span class="step-label">Step 4</span>
  <h2>🧪 Hypothesis Testing</h2>
</div>

<p>
  Our EDA suggested two strong patterns: meat recipes are high in protein, and dessert recipes are
  high in carbohydrates. We now test whether these patterns are statistically significant or could
  plausibly arise by chance.
</p>

<h3>Test 1 — Meat Recipes and Protein</h3>

<div class="callout">
  <strong class="tag">⚗️ Hypotheses &amp; Setup</strong>
  <strong>H₀:</strong> Meat and non-meat recipes have the same mean protein (% DV). Any observed difference is due to random chance.<br>
  <strong>H₁:</strong> Meat recipes have a <em>higher</em> mean protein (% DV) than non-meat recipes.<br>
  <strong>Test statistic:</strong> Mean protein of meat recipes − mean protein of non-meat recipes.<br>
  <strong>Significance level:</strong> α = 0.05 &nbsp;|&nbsp; <strong>Method:</strong> Permutation test (2,000 shuffles)
</div>

<p>
  We chose a permutation test because we are comparing two groups drawn from the same dataset and
  want to avoid assuming any particular parametric distribution for protein content (which is
  heavily right-skewed). The one-sided alternative is justified by our EDA, which showed meat
  recipes above all other categories on protein.
</p>

<div class="plot-wrap">
  <iframe src="assets/plots/hyp_test1.html" loading="lazy"></iframe>
</div>
<p class="plot-caption">
  The observed difference of +41.70% DV (meat mean: 65.34% vs. non-meat mean: 23.64%) is completely outside the null distribution — not a single permutation produced a difference this large. The p-value is effectively 0.
</p>

<h3>Test 2 — Dessert Recipes and Carbohydrates</h3>

<div class="callout orange">
  <strong class="tag">⚗️ Hypotheses &amp; Setup</strong>
  <strong>H₀:</strong> Dessert and non-dessert recipes have the same mean carbohydrates (% DV). Any observed difference is due to random chance.<br>
  <strong>H₁:</strong> Dessert recipes have a <em>higher</em> mean carbohydrates (% DV) than non-dessert recipes.<br>
  <strong>Test statistic:</strong> Mean carbs of dessert recipes − mean carbs of non-dessert recipes.<br>
  <strong>Significance level:</strong> α = 0.05 &nbsp;|&nbsp; <strong>Method:</strong> Permutation test (2,000 shuffles)
</div>

<div class="plot-wrap">
  <iframe src="assets/plots/hyp_test2.html" loading="lazy"></iframe>
</div>
<p class="plot-caption">
  The observed difference of +9.66% DV (desserts: 21.89% vs. non-desserts: 12.23%) likewise falls entirely outside the simulated null distribution. The p-value is effectively 0.
</p>

<h3>🎯 Summary of Results</h3>

<div class="hyp-cards">
  <div class="hyp-card">
    <div class="hyp-card-head">Test 1 · Meat vs. Non-Meat</div>
    <div class="hyp-card-body">
      <div class="metric">+41.70% DV</div>
      <p>Observed difference in mean protein</p>
      <p><strong>p-value:</strong> &lt; 0.001</p>
      <div class="verdict">💖 Reject H₀</div>
    </div>
  </div>
  <div class="hyp-card">
    <div class="hyp-card-head">Test 2 · Desserts vs. Non-Desserts</div>
    <div class="hyp-card-body">
      <div class="metric orange">+9.66% DV</div>
      <p>Observed difference in mean carbohydrates</p>
      <p><strong>p-value:</strong> &lt; 0.001</p>
      <div class="verdict">💖 Reject H₀</div>
    </div>
  </div>
</div>

<table class="results-table">
  <thead>
    <tr><th>Test</th><th>Observed Statistic</th><th>p-value</th><th>Conclusion</th></tr>
  </thead>
  <tbody>
    <tr>
      <td>Meat vs. Non-Meat — Protein</td>
      <td>+41.70% DV</td>
      <td>&lt; 0.001</td>
      <td class="reject">Reject H₀ — meat recipes have significantly higher protein</td>
    </tr>
    <tr>
      <td>Desserts vs. Non-Desserts — Carbs</td>
      <td>+9.66% DV</td>
      <td>&lt; 0.001</td>
      <td class="reject">Reject H₀ — dessert recipes have significantly higher carbohydrates</td>
    </tr>
  </tbody>
</table>

<div class="callout green">
  <strong class="tag">✅ Conclusion</strong>
  At the α = 0.05 significance level, both null hypotheses are rejected. The data are consistent with the alternative hypotheses in both cases: meat recipes provide significantly more protein, and dessert recipes contain significantly more carbohydrates. These patterns are very unlikely to be explained by random chance alone. Note that as observational analyses on a self-selected dataset, we cannot establish causation — but the nutritional differences across categories are real and substantial.
</div>

</div><!-- /.content -->

<footer class="site-footer">
  <div class="emoji-row">🍖 🥗 🍰 🐟 🥚 🥙</div>
  DSC 80 Final Project &nbsp;·&nbsp; Chau Nguyen &nbsp;·&nbsp; Food.com Recipes Dataset
</footer>
