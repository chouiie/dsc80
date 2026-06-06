---
layout: default
title: "What Types of Recipes Are Healthier?"
---

<style>
@import url('https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,700;0,900;1,700&family=DM+Sans:ital,wght@0,300;0,400;0,500;1,300&family=DM+Mono:wght@400;500&display=swap');

:root {
  --bg:       #f5f2eb;
  --surface:  #edeadf;
  --ink:      #1a1a14;
  --muted:    #6b6656;
  --border:   #d4cfbf;
  --accent:   #2d5016;
  --accent2:  #8b4513;
  --gold:     #c8922a;
  --red:      #8b1a1a;
  --green:    #1a4d2e;
  --white:    #faf9f5;
  --mono:     'DM Mono', monospace;
}

*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

body {
  background: var(--bg);
  color: var(--ink);
  font-family: 'DM Sans', sans-serif;
  font-size: 17px;
  line-height: 1.8;
}

/* ── HERO ── */
.hero {
  background: var(--ink);
  color: var(--bg);
  padding: 5rem 2rem 4rem;
  position: relative;
  overflow: hidden;
}
.hero::before {
  content: '';
  position: absolute;
  inset: 0;
  background: repeating-linear-gradient(
    -45deg,
    transparent,
    transparent 40px,
    rgba(255,255,255,0.018) 40px,
    rgba(255,255,255,0.018) 41px
  );
}
.hero-inner {
  max-width: 860px;
  margin: 0 auto;
  position: relative;
}
.hero-kicker {
  font-family: var(--mono);
  font-size: 0.68rem;
  letter-spacing: 0.2em;
  text-transform: uppercase;
  color: var(--gold);
  margin-bottom: 1.5rem;
  display: flex;
  align-items: center;
  gap: 0.8rem;
}
.hero-kicker::before {
  content: '';
  display: block;
  width: 2rem;
  height: 1px;
  background: var(--gold);
}
.hero h1 {
  font-family: 'Playfair Display', serif;
  font-size: clamp(2.4rem, 6vw, 4.2rem);
  font-weight: 900;
  line-height: 1.08;
  color: #faf9f5;
  max-width: 680px;
  margin-bottom: 1.8rem;
}
.hero h1 em {
  font-style: italic;
  color: var(--gold);
}
.hero-sub {
  font-size: 1rem;
  font-weight: 300;
  color: #b8b4a4;
  max-width: 520px;
  line-height: 1.7;
}
.hero-meta {
  margin-top: 2.5rem;
  display: flex;
  flex-wrap: wrap;
  gap: 2rem;
  border-top: 1px solid rgba(255,255,255,0.1);
  padding-top: 1.8rem;
}
.hero-meta-item {
  font-family: var(--mono);
  font-size: 0.72rem;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  color: #7a7568;
}
.hero-meta-item strong {
  display: block;
  font-family: 'DM Sans', sans-serif;
  font-size: 1.1rem;
  font-weight: 500;
  color: #d4d0c4;
  letter-spacing: 0;
  text-transform: none;
  margin-top: 0.2rem;
}

/* ── NAV ── */
.sitenav {
  background: var(--surface);
  border-bottom: 1px solid var(--border);
  padding: 0 2rem;
  position: sticky;
  top: 0;
  z-index: 100;
}
.sitenav-inner {
  max-width: 860px;
  margin: 0 auto;
  display: flex;
  flex-wrap: wrap;
  gap: 0;
}
.sitenav a {
  font-family: var(--mono);
  font-size: 0.65rem;
  letter-spacing: 0.12em;
  text-transform: uppercase;
  color: var(--muted);
  text-decoration: none;
  padding: 0.9rem 0.9rem;
  border-bottom: 2px solid transparent;
  transition: color 0.15s, border-color 0.15s;
  white-space: nowrap;
}
.sitenav a:hover { color: var(--ink); border-color: var(--accent); }

/* ── MAIN CONTENT ── */
.content {
  max-width: 860px;
  margin: 0 auto;
  padding: 4rem 1.5rem 6rem;
}

/* ── SECTION MARKER ── */
.section-marker {
  margin: 5rem 0 2rem;
  display: grid;
  grid-template-columns: auto 1fr;
  align-items: start;
  gap: 1.2rem;
}
.section-marker:first-child { margin-top: 0; }
.step-tag {
  font-family: var(--mono);
  font-size: 0.6rem;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  color: var(--white);
  background: var(--accent);
  padding: 0.3rem 0.65rem;
  border-radius: 2px;
  margin-top: 0.55rem;
  white-space: nowrap;
}
.section-marker h2 {
  font-family: 'Playfair Display', serif;
  font-size: 2rem;
  font-weight: 700;
  color: var(--ink);
  line-height: 1.2;
  border-bottom: 2px solid var(--border);
  padding-bottom: 0.7rem;
}

h3 {
  font-family: 'DM Sans', sans-serif;
  font-size: 0.72rem;
  font-weight: 500;
  letter-spacing: 0.16em;
  text-transform: uppercase;
  color: var(--muted);
  margin: 2.5rem 0 0.8rem;
}

p { margin-bottom: 1.1rem; color: var(--ink); }

/* ── STAT ROW ── */
.stat-row {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(130px, 1fr));
  gap: 1px;
  background: var(--border);
  border: 1px solid var(--border);
  border-radius: 4px;
  overflow: hidden;
  margin: 1.8rem 0;
}
.stat-cell {
  background: var(--white);
  padding: 1.4rem 1.2rem;
  text-align: center;
}
.stat-cell .num {
  font-family: 'Playfair Display', serif;
  font-size: 2rem;
  font-weight: 700;
  color: var(--accent);
  line-height: 1;
  display: block;
}
.stat-cell .lbl {
  font-family: var(--mono);
  font-size: 0.6rem;
  letter-spacing: 0.14em;
  text-transform: uppercase;
  color: var(--muted);
  margin-top: 0.4rem;
  display: block;
}

/* ── TABLES ── */
table {
  width: 100%;
  border-collapse: collapse;
  font-size: 0.875rem;
  margin: 1.2rem 0 1.8rem;
  background: var(--white);
  border: 1px solid var(--border);
  border-radius: 4px;
  overflow: hidden;
}
thead tr {
  background: var(--ink);
  color: var(--bg);
}
thead th {
  font-family: var(--mono);
  font-size: 0.6rem;
  letter-spacing: 0.14em;
  text-transform: uppercase;
  font-weight: 500;
  padding: 0.7rem 1rem;
  text-align: left;
}
tbody td {
  padding: 0.6rem 1rem;
  border-bottom: 1px solid var(--border);
  vertical-align: top;
}
tbody tr:last-child td { border-bottom: none; }
tbody tr:nth-child(even) td { background: var(--surface); }
code {
  font-family: var(--mono);
  font-size: 0.8rem;
  background: var(--surface);
  color: var(--accent2);
  padding: 0.1em 0.4em;
  border-radius: 3px;
  border: 1px solid var(--border);
}
.best  { color: var(--green); font-weight: 600; }
.worst { color: var(--red);   font-weight: 600; }
.pass  { color: var(--green); font-weight: 600; }

/* ── CALLOUT ── */
.callout {
  border-left: 3px solid var(--accent);
  background: var(--white);
  padding: 1.1rem 1.3rem;
  margin: 1.4rem 0 1.8rem;
  border-radius: 0 4px 4px 0;
  font-size: 0.93rem;
}
.callout.amber { border-color: var(--gold); }
.callout.red   { border-color: var(--red);  }
.callout-label {
  font-family: var(--mono);
  font-size: 0.6rem;
  letter-spacing: 0.16em;
  text-transform: uppercase;
  color: var(--accent);
  margin-bottom: 0.5rem;
  display: block;
}
.callout.amber .callout-label { color: var(--gold); }
.callout.red   .callout-label { color: var(--red);  }

/* ── NUMBERED STEPS ── */
.steps { margin: 1rem 0 1.5rem; }
.step  {
  display: grid;
  grid-template-columns: 2rem 1fr;
  gap: 1rem;
  margin-bottom: 1rem;
  align-items: start;
}
.step-n {
  font-family: var(--mono);
  font-size: 0.72rem;
  font-weight: 500;
  color: var(--white);
  background: var(--ink);
  width: 2rem;
  height: 2rem;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
  margin-top: 0.2rem;
}
.step p { margin: 0; }

/* ── RESULTS CARDS ── */
.cards {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 1px;
  background: var(--border);
  border: 1px solid var(--border);
  border-radius: 4px;
  overflow: hidden;
  margin: 1.6rem 0;
}
.card {
  background: var(--white);
  padding: 1.4rem 1.3rem;
}
.card-head {
  font-family: var(--mono);
  font-size: 0.58rem;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  color: var(--muted);
  margin-bottom: 0.8rem;
}
.card-num {
  font-family: 'Playfair Display', serif;
  font-size: 2.1rem;
  font-weight: 700;
  color: var(--accent);
  line-height: 1;
}
.card-num.amber { color: var(--gold);  }
.card-num.red   { color: var(--red);   }
.card p { font-size: 0.85rem; color: var(--muted); margin: 0.4rem 0 0; }
.card .verdict {
  font-family: var(--mono);
  font-size: 0.6rem;
  letter-spacing: 0.12em;
  text-transform: uppercase;
  color: var(--green);
  margin-top: 0.6rem;
  display: block;
}

/* ── PLOT EMBED ── */
.plot-wrap {
  background: var(--white);
  border: 1px solid var(--border);
  border-radius: 4px;
  overflow: hidden;
  margin: 1.2rem 0 0.4rem;
}
.plot-wrap iframe {
  width: 100%;
  height: 430px;
  border: none;
  display: block;
}
.plot-cap {
  font-size: 0.82rem;
  color: var(--muted);
  font-style: italic;
  margin: 0.4rem 0 1.8rem;
  padding-left: 1rem;
  border-left: 2px solid var(--border);
  line-height: 1.6;
}

/* ── DF TABLE ── */
.df-wrap {
  overflow-x: auto;
  margin: 1.2rem 0 1.8rem;
  border: 1px solid var(--border);
  border-radius: 4px;
}
.df-wrap table {
  margin: 0;
  border: none;
  border-radius: 0;
  white-space: nowrap;
  min-width: 100%;
  font-size: 0.77rem;
  font-family: var(--mono);
}

/* ── FOOTER ── */
.site-footer {
  background: var(--ink);
  color: #7a7568;
  text-align: center;
  padding: 2.5rem;
  font-family: var(--mono);
  font-size: 0.68rem;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  margin-top: 4rem;
}
.site-footer strong { color: #b8b4a4; }

@media (max-width: 640px) {
  .hero h1 { font-size: 2rem; }
  .section-marker { grid-template-columns: 1fr; }
  .step-tag { width: fit-content; }
  .sitenav-inner { gap: 0; }
  .sitenav a { font-size: 0.58rem; padding: 0.8rem 0.6rem; }
}
</style>

<header class="hero">
  <div class="hero-inner">
    <div class="hero-kicker">DSC 80 &nbsp;·&nbsp; Food.com Recipes Dataset &nbsp;·&nbsp; Spring 2026</div>
    <h1>What Types of Recipes<br><em>Tend to Be Healthier?</em></h1>
    <p class="hero-sub">
      A data science investigation into protein, carbohydrates, and calorie content
      across Food.com recipe categories — from hypothesis to predictive model.
    </p>
    <div class="hero-meta">
      <div class="hero-meta-item">Author<strong>Chau Nguyen</strong></div>
      <div class="hero-meta-item">Dataset<strong>Food.com Recipes</strong></div>
      <div class="hero-meta-item">Rows<strong>83,782</strong></div>
      <div class="hero-meta-item">Course<strong>DSC 80 · UCSD</strong></div>
    </div>
  </div>
</header>

<nav class="sitenav">
  <div class="sitenav-inner">
    <a href="#intro">Introduction</a>
    <a href="#cleaning">Data Cleaning</a>
    <a href="#eda">EDA</a>
    <a href="#missingness">Missingness</a>
    <a href="#hypothesis">Hypothesis</a>
    <a href="#prediction">Prediction</a>
    <a href="#baseline">Baseline</a>
    <a href="#final-model">Final Model</a>
    <a href="#fairness">Fairness</a>
  </div>
</nav>

<div class="content">

<!-- ═══════════════════════════════════════ STEP 1: INTRODUCTION -->
<div class="section-marker" id="intro">
  <span class="step-tag">Step 01</span>
  <h2>Introduction</h2>
</div>

<p>
  Social media is saturated with competing dietary advice — high-protein, low-carb, keto,
  plant-based. But which recipe categories actually live up to these claims, and which ones
  quietly deliver more sugar than substance? This project uses the
  <strong>Food.com Recipes &amp; Ratings dataset</strong> to answer one concrete question:
</p>

<div class="callout">
  <span class="callout-label">Central Question</span>
  Which recipe categories on Food.com tend to be healthier — specifically, which categories
  provide the most protein and the fewest carbohydrates per serving?
</div>

<p>
  Understanding this matters for anyone trying to eat with intention. Protein content is a
  reliable proxy for satiety and muscle maintenance; carbohydrate density (especially from
  sugar) is closely linked to metabolic health. By mapping these nutrients across recipe
  categories, we can offer data-driven guidance on which cuisine types to prioritise or limit.
</p>

<div class="stat-row">
  <div class="stat-cell"><span class="num">83,782</span><span class="lbl">Recipes</span></div>
  <div class="stat-cell"><span class="num">731,927</span><span class="lbl">Interactions</span></div>
  <div class="stat-cell"><span class="num">6</span><span class="lbl">Categories</span></div>
  <div class="stat-cell"><span class="num">7</span><span class="lbl">Nutrition columns</span></div>
</div>

<h3>Relevant Columns</h3>

| Column | Description |
|---|---|
| `nutrition` | Encoded list: `[calories, total_fat_pdv, sugar_pdv, sodium_pdv, protein_pdv, saturated_fat_pdv, carbohydrates_pdv]` |
| `protein_pdv` | Protein as % of daily recommended value. Extracted from `nutrition`. |
| `carbohydrates_pdv` | Carbohydrates as % daily value. Extracted from `nutrition`. |
| `calories` | Total calories per serving. Extracted from `nutrition`. |
| `tags` | Descriptive tag list (e.g. `'meat'`, `'desserts'`, `'low-carb'`) used to classify recipes. |
| `minutes` | Total preparation and cook time in minutes. |
| `n_steps` | Number of steps in the recipe instructions. |
| `n_ingredients` | Number of distinct ingredients used. |
| `avg_rating` | Mean user rating (1–5) across all interactions, merged from the interactions table. |

<!-- ═══════════════════════════════════════ STEP 2: DATA CLEANING -->
<div class="section-marker" id="cleaning">
  <span class="step-tag">Step 02</span>
  <h2>Data Cleaning and Exploratory Data Analysis</h2>
</div>

<p>The raw data required four cleaning steps before analysis could begin:</p>

<div class="steps">
  <div class="step">
    <span class="step-n">1</span>
    <p><strong>Unpack the nutrition column.</strong> Each row stored nutrition as a Python-list string like <code>"[138.4, 10.0, 50.0, 3.0, 3.0, 19.0, 6.0]"</code>. We used <code>ast.literal_eval</code> to parse each string and split the seven values into separate, named columns (<code>calories</code>, <code>protein_pdv</code>, <code>carbohydrates_pdv</code>, etc.), making every nutrient directly queryable.</p>
  </div>
  <div class="step">
    <span class="step-n">2</span>
    <p><strong>Parse recipe tags.</strong> The <code>tags</code> column was also stored as a string representation of a list. We applied the same parsing step so we could search for category membership (e.g. whether a recipe has the tag <code>'meat'</code>).</p>
  </div>
  <div class="step">
    <span class="step-n">3</span>
    <p><strong>Create binary category indicators.</strong> For each of the six food categories of interest — <em>meat, vegetables, seafood, desserts, salads, breakfast</em> — we created a binary column <code>is_&lt;category&gt;</code>. Recipes can belong to multiple categories simultaneously.</p>
  </div>
  <div class="step">
    <span class="step-n">4</span>
    <p><strong>Merge in average ratings.</strong> Ratings of 0 represent "no rating given," so we replaced them with <code>NaN</code> before computing per-recipe means. We then left-joined these averages onto the recipes table, preserving all 83,782 recipes including those with no interactions.</p>
  </div>
</div>

<h3>Cleaned DataFrame — First 5 Rows</h3>

<div class="df-wrap">

| name | minutes | n_steps | calories | protein_pdv | carbohydrates_pdv | avg_rating |
|---|---|---|---|---|---|---|
| 1 brownies in the world best ever | 40 | 10 | 138.4 | 3.0 | 6.0 | 4.00 |
| 1 in canada chocolate chip cookies | 45 | 12 | 595.1 | 13.0 | 26.0 | 5.00 |
| 412 broccoli casserole | 40 | 6 | 194.8 | 22.0 | 3.0 | 5.00 |
| millionaire pound cake | 120 | 7 | 878.3 | 20.0 | 39.0 | 5.00 |
| 2000 meatloaf | 90 | 17 | 267.0 | 29.0 | 2.0 | 5.00 |

</div>

<h3>Univariate Analysis — Distribution of Protein</h3>

<div class="plot-wrap">
  <iframe src="assets/plots/protein_dist.html" loading="lazy"></iframe>
</div>
<p class="plot-cap">
  Protein (% DV) is heavily right-skewed: the vast majority of recipes deliver under 50% DV,
  with a long tail of high-protein dishes. This reflects the breadth of Food.com — most recipes
  are sides, desserts, or snacks, with a smaller subset of protein-heavy mains.
</p>

<h3>Bivariate Analysis — Protein by Category</h3>

<div class="plot-wrap">
  <iframe src="assets/plots/protein_by_category.html" loading="lazy"></iframe>
</div>
<p class="plot-cap">
  Meat and seafood recipes show dramatically higher protein distributions than plant-based or
  dessert categories. Median protein for meat recipes sits around 45% DV — nearly double
  that of vegetables (≈22%) and almost four times that of desserts (≈8%).
</p>

<h3>Interesting Aggregates — Mean Nutrition by Category</h3>

<p>Grouping by category and computing mean nutritional values reveals a clear protein–carb trade-off:</p>

| Category | Mean Protein (% DV) | Mean Carbs (% DV) | Mean Calories |
|---|---|---|---|
| Meat | **63.8** | 9.9 | 510.7 |
| Seafood | **57.5** | 8.7 | 407.9 |
| Vegetables | 26.0 | 10.6 | 333.1 |
| Breakfast | 24.0 | 13.2 | 365.8 |
| Salads | 19.3 | 8.7 | 309.4 |
| Desserts | 12.1 | **18.9** | 441.1 |

<p class="plot-cap">
  Meat and seafood dominate on protein while keeping carbohydrates low. Desserts are the
  clear outlier — lowest protein and highest carbohydrates, the least nutritionally dense
  category by both metrics.
</p>

<!-- ═══════════════════════════════════════ STEP 3: MISSINGNESS -->
<div class="section-marker" id="missingness">
  <span class="step-tag">Step 03</span>
  <h2>Assessment of Missingness</h2>
</div>

<h3>NMAR Analysis</h3>

<p>
  After merging, three columns contain missing values: <code>name</code> (1 missing),
  <code>description</code> (70 missing), and <code>avg_rating</code> (2,609 missing — 3.1%).
</p>

<p>
  We believe <code>description</code> is likely <strong>NMAR (Not Missing At Random)</strong>.
  Contributors who invest less effort in their submission are also less likely to write a
  description. The missingness is driven by an unobserved characteristic — contributor effort
  or engagement level — not by any column we can observe. To make this MAR, we would need
  additional data such as a contributor's total submissions or profile completeness score.
</p>

<h3>Missingness Dependency — Does <code>avg_rating</code> depend on <code>n_steps</code>?</h3>

<div class="callout">
  <span class="callout-label">Permutation Test Setup</span>
  <strong>H₀:</strong> The distribution of <code>n_steps</code> is the same whether <code>avg_rating</code> is missing or not.<br>
  <strong>H₁:</strong> Recipes with missing <code>avg_rating</code> have a different mean <code>n_steps</code>.<br>
  <strong>Test statistic:</strong> Difference in mean <code>n_steps</code> (missing − not missing). &nbsp;·&nbsp; <strong>α = 0.05</strong>
</div>

<div class="plot-wrap">
  <iframe src="assets/plots/missingness_nsteps.html" loading="lazy"></iframe>
</div>
<p class="plot-cap">
  The observed difference (1.49 more steps for recipes with missing ratings) falls far into
  the tail of the null distribution. p-value &lt; 0.001 — we reject the null. The missingness
  of <code>avg_rating</code> is dependent on <code>n_steps</code>, making it MAR. Longer,
  more complex recipes appear less likely to receive ratings.
</p>

<p>
  We also tested whether missingness of <code>avg_rating</code> depends on
  <code>n_ingredients</code>. That test yielded p &gt; 0.05 — we fail to reject the null.
  Missingness appears <strong>independent of ingredient count</strong>, confirming the
  dependency is specific to recipe complexity (steps), not size (ingredients).
</p>

<!-- ═══════════════════════════════════════ STEP 4: HYPOTHESIS -->
<div class="section-marker" id="hypothesis">
  <span class="step-tag">Step 04</span>
  <h2>Hypothesis Testing</h2>
</div>

<p>
  Our EDA suggested two strong patterns: meat recipes are high in protein, and dessert recipes
  are high in carbohydrates. We test whether these patterns are statistically significant or
  could plausibly arise by chance.
</p>

<h3>Test 1 — Do Meat Recipes Have Higher Protein?</h3>

<div class="callout">
  <span class="callout-label">Hypotheses &amp; Setup</span>
  <strong>H₀:</strong> Meat and non-meat recipes have the same mean protein (% DV). Any difference is due to chance.<br>
  <strong>H₁:</strong> Meat recipes have a <em>higher</em> mean protein (% DV) than non-meat recipes.<br>
  <strong>Test statistic:</strong> Mean protein (meat) − Mean protein (non-meat).<br>
  <strong>Method:</strong> Permutation test (2,000 shuffles) &nbsp;·&nbsp; <strong>α = 0.05</strong>
</div>

<p>
  We chose a permutation test because we are comparing two groups from the same dataset and
  want to avoid distributional assumptions — protein (% DV) is heavily right-skewed. The
  one-sided alternative is justified by our EDA, which already showed meat above all other
  categories on protein.
</p>

<div class="plot-wrap">
  <iframe src="assets/plots/hyp_test1.html" loading="lazy"></iframe>
</div>
<p class="plot-cap">
  The observed difference of +41.70% DV (meat mean: 65.34% vs. non-meat mean: 23.64%) is
  completely outside the null distribution — not a single permutation produced a difference
  this large. The p-value is effectively 0.
</p>

<h3>Test 2 — Do Dessert Recipes Have Higher Carbohydrates?</h3>

<div class="callout amber">
  <span class="callout-label">Hypotheses &amp; Setup</span>
  <strong>H₀:</strong> Dessert and non-dessert recipes have the same mean carbohydrates (% DV). Any difference is due to chance.<br>
  <strong>H₁:</strong> Dessert recipes have a <em>higher</em> mean carbohydrates (% DV).<br>
  <strong>Test statistic:</strong> Mean carbs (desserts) − Mean carbs (non-desserts).<br>
  <strong>Method:</strong> Permutation test (2,000 shuffles) &nbsp;·&nbsp; <strong>α = 0.05</strong>
</div>

<div class="plot-wrap">
  <iframe src="assets/plots/hyp_test2.html" loading="lazy"></iframe>
</div>
<p class="plot-cap">
  The observed difference of +9.66% DV (desserts: 21.89% vs. non-desserts: 12.23%) likewise
  falls entirely outside the simulated null distribution. The p-value is effectively 0.
</p>

<h3>Summary of Results</h3>

| Test | Observed Statistic | p-value | Conclusion |
|---|---|---|---|
| Meat vs. Non-Meat — Protein | +41.70% DV | &lt; 0.001 | Reject H₀ — meat recipes have significantly higher protein |
| Desserts vs. Non-Desserts — Carbs | +9.66% DV | &lt; 0.001 | Reject H₀ — dessert recipes have significantly higher carbohydrates |

<div class="callout">
  <span class="callout-label">Conclusion</span>
  At α = 0.05, both null hypotheses are rejected. The data are consistent with the alternative
  hypotheses in both cases: meat recipes provide significantly more protein, and dessert recipes
  contain significantly more carbohydrates. These patterns are very unlikely to be explained by
  random chance. As observational analyses on a self-selected dataset, we cannot establish
  causation — but the nutritional differences across categories are real and substantial.
</div>

<!-- ═══════════════════════════════════════ STEP 5: PREDICTION PROBLEM -->
<div class="section-marker" id="prediction">
  <span class="step-tag">Step 05</span>
  <h2>Framing a Prediction Problem</h2>
</div>

<div class="callout">
  <span class="callout-label">Prediction Problem</span>
  Can we predict how many <strong>calories</strong> a recipe contains using only information
  available at the time the recipe is submitted — before any nutritional analysis is done?
</div>

<p>
  This is a <strong>regression</strong> problem. The response variable is <code>calories</code>,
  a continuous numeric value. We chose calories because they are the most universally tracked
  nutritional metric, and an accurate estimate from recipe metadata alone would be genuinely
  useful for home cooks, diet-tracking apps, and food-logging platforms.
</p>

<p>
  <strong>Evaluation metric: RMSE.</strong> We prefer RMSE over MAE because calories sit on
  an interpretable absolute scale, and RMSE's squared-error structure penalises large mistakes
  more heavily — a 500-calorie prediction error is qualitatively worse than a 50-calorie one,
  and should be penalised accordingly.
</p>

<p>
  <strong>Time-of-prediction justification.</strong> When a recipe is submitted to Food.com,
  the author provides the ingredient list, instructions, tags, and preparation time — but not
  a nutritional label. Our baseline features (<code>n_ingredients</code>, <code>n_steps</code>,
  <code>minutes</code>, <code>category</code>) are all known at submission time. In the Final
  Model we additionally include macro PDV values (fat, sugar, protein, carbohydrates), which
  a diligent author could look up from ingredient packaging before posting.
</p>

<div class="stat-row">
  <div class="stat-cell"><span class="num">Regression</span><span class="lbl">Problem type</span></div>
  <div class="stat-cell"><span class="num">calories</span><span class="lbl">Response variable</span></div>
  <div class="stat-cell"><span class="num">RMSE</span><span class="lbl">Eval metric</span></div>
  <div class="stat-cell"><span class="num">80 / 20</span><span class="lbl">Train / test split</span></div>
</div>

<!-- ═══════════════════════════════════════ STEP 6: BASELINE MODEL -->
<div class="section-marker" id="baseline">
  <span class="step-tag">Step 06</span>
  <h2>Baseline Model</h2>
</div>

<p>
  The baseline uses <strong>Linear Regression</strong> within a single <code>sklearn</code>
  <code>Pipeline</code> with three features:
</p>

| Feature | Type | Encoding |
|---|---|---|
| `n_ingredients` | Quantitative | StandardScaler |
| `n_steps` | Quantitative | StandardScaler |
| `category` | Nominal | OneHotEncoder (7 levels) |

<p>
  The <code>category</code> column assigns each recipe its single most-specific tag
  (meat, seafood, desserts, breakfast, salads, vegetables, other). Quantitative features
  are standardised so LinearRegression coefficients are not dominated by scale differences.
</p>

<div class="cards">
  <div class="card">
    <div class="card-head">Train RMSE</div>
    <div class="card-num">~320 cal</div>
    <p>Linear Regression on training set</p>
  </div>
  <div class="card">
    <div class="card-head">Test RMSE</div>
    <div class="card-num amber">~325 cal</div>
    <p>Linear Regression on held-out test set</p>
  </div>
</div>

<p>
  A test RMSE of ~325 calories is <strong>not adequate</strong>. The average recipe has
  roughly 400 calories, making this an ~80% relative error. The model captures broad
  category-level differences but cannot distinguish caloric density within categories —
  a 5-ingredient salad and a 5-ingredient cheesecake look identical to this model.
</p>

<div class="plot-wrap">
  <iframe src="assets/plots/baseline_resid.html" loading="lazy"></iframe>
</div>
<p class="plot-cap">
  The residual plot shows a strong fan shape: errors grow as predicted calories increase,
  indicating that the model systematically under-predicts high-calorie recipes. This signals
  that we need features more directly tied to caloric content.
</p>

<!-- ═══════════════════════════════════════ STEP 7: FINAL MODEL -->
<div class="section-marker" id="final-model">
  <span class="step-tag">Step 07</span>
  <h2>Final Model</h2>
</div>

<p>
  The final model uses a <strong>Random Forest Regressor</strong> with two engineered features
  on top of an expanded feature set, all within a single <code>Pipeline</code>.
</p>

<h3>Engineered Features</h3>

<div class="steps">
  <div class="step">
    <span class="step-n">1</span>
    <p><strong><code>log_minutes</code></strong> — log-transform of preparation time. Cook time is heavily right-skewed. A log-transform compresses the long tail so the model treats the difference between a 10-minute and 30-minute recipe similarly to the difference between a 180-minute and 540-minute one — a proportional relationship that better reflects how time relates to caloric complexity.</p>
  </div>
  <div class="step">
    <span class="step-n">2</span>
    <p><strong><code>fat_x_protein</code></strong> — interaction term (total_fat_pdv × protein_pdv). Fat contributes ~9 kcal/g; protein ~4 kcal/g. Recipes that are simultaneously high-fat <em>and</em> high-protein (ribeye steak, salmon with butter sauce) occupy a distinct calorie tier that neither feature alone can identify. Their product creates a new signal dimension that a linear model cannot derive on its own.</p>
  </div>
</div>

<h3>Full Feature Set</h3>

| Feature | Type | Transformation |
|---|---|---|
| `n_ingredients` | Quantitative | StandardScaler |
| `n_steps` | Quantitative | StandardScaler |
| `minutes` | Quantitative | StandardScaler |
| `total_fat_pdv` | Quantitative | StandardScaler |
| `protein_pdv` | Quantitative | StandardScaler |
| `carbohydrates_pdv` | Quantitative | StandardScaler |
| `sugar_pdv` | Quantitative | StandardScaler |
| `saturated_fat_pdv` | Quantitative | StandardScaler |
| `log_minutes` | Quantitative (engineered) | StandardScaler |
| `fat_x_protein` | Quantitative (engineered) | StandardScaler |
| `category` | Nominal | OneHotEncoder (7 levels) |

<h3>Hyperparameter Search</h3>

<p>
  We used <strong>GridSearchCV with 3-fold cross-validation</strong>, scored by negative RMSE,
  over the following grid:
</p>

| Hyperparameter | Values Searched | Rationale |
|---|---|---|
| `n_estimators` | 100, 200 | More trees reduce variance; 200 stabilises a forest on 65k rows |
| `max_depth` | 10, 20, None | Controls overfitting; unlimited depth risks memorising training data |
| `min_samples_leaf` | 1, 4 | Higher values regularise the tree and smooth noisy splits |

<div class="callout">
  <span class="callout-label">Best Hyperparameters (3-fold CV)</span>
  <code>n_estimators=200</code>, <code>max_depth=20</code>, <code>min_samples_leaf=1</code>
</div>

<h3>Performance Comparison</h3>

<div class="cards">
  <div class="card">
    <div class="card-head">Baseline Test RMSE</div>
    <div class="card-num amber">~325 cal</div>
    <p>Linear Regression · 3 features</p>
  </div>
  <div class="card">
    <div class="card-head">Final Test RMSE</div>
    <div class="card-num">~85 cal</div>
    <p>Random Forest · 11 features + 2 engineered</p>
    <span class="verdict">↓ ~240 cal improvement</span>
  </div>
</div>

<p>
  The improvement comes primarily from adding macronutrient PDV features — fat, sugar, and
  carbohydrate content are direct physical drivers of caloric value. The engineered
  <code>fat_x_protein</code> interaction further helps the forest identify the high-calorie-density
  tier of protein-rich, fatty dishes.
</p>

<div class="plot-wrap">
  <iframe src="assets/plots/predicted_vs_actual.html" loading="lazy"></iframe>
</div>
<p class="plot-cap">
  Predicted vs. actual calories for the test set. Points cluster tightly along the perfect
  prediction diagonal for recipes under 1,000 calories — the most common range. Some scatter
  remains for very high-calorie recipes (&gt;1,500 cal), which are rare in training data
  and inherently harder to predict.
</p>

<div class="plot-wrap">
  <iframe src="assets/plots/feature_importance.html" loading="lazy"></iframe>
</div>
<p class="plot-cap">
  Feature importances from the Random Forest. Macronutrient PDV columns dominate, confirming
  that fat and sugar content are the strongest calorie signals. The engineered
  <code>fat_x_protein</code> interaction ranks among the top features, validating our
  feature-engineering rationale.
</p>

<!-- ═══════════════════════════════════════ STEP 8: FAIRNESS -->
<div class="section-marker" id="fairness">
  <span class="step-tag">Step 08</span>
  <h2>Fairness Analysis</h2>
</div>

<p>
  A low overall RMSE can mask systematic bias. If the model is far less accurate for
  high-calorie recipes, it could mislead users tracking intake from calorie-dense foods —
  the exact meals where accurate estimates matter most.
</p>

<div class="callout red">
  <span class="callout-label">Fairness Test Setup</span>
  <strong>Group X (low-calorie):</strong> Recipes with calories ≤ test-set median.<br>
  <strong>Group Y (high-calorie):</strong> Recipes with calories > test-set median.<br>
  <strong>Metric:</strong> RMSE.<br>
  <strong>H₀:</strong> The model is fair. Its RMSE for low-calorie and high-calorie recipes is roughly the same; any observed difference is due to random chance.<br>
  <strong>H₁:</strong> The model is unfair. Its RMSE is higher for high-calorie recipes.<br>
  <strong>Test statistic:</strong> RMSE(high-cal) − RMSE(low-cal). &nbsp;·&nbsp; <strong>α = 0.05</strong> &nbsp;·&nbsp; 2,000 permutations.
</div>

<div class="cards">
  <div class="card">
    <div class="card-head">RMSE — Low-Calorie Recipes</div>
    <div class="card-num">~55 cal</div>
    <p>Calories ≤ test-set median</p>
  </div>
  <div class="card">
    <div class="card-head">RMSE — High-Calorie Recipes</div>
    <div class="card-num amber">~115 cal</div>
    <p>Calories > test-set median</p>
  </div>
</div>

<div class="plot-wrap">
  <iframe src="assets/plots/fairness_perm.html" loading="lazy"></iframe>
</div>
<p class="plot-cap">
  The observed RMSE difference (red dashed line) falls far to the right of every simulated
  null difference. The p-value is effectively 0 (&lt; 0.001).
</p>

<h3>Conclusion</h3>

<p>
  We <strong>reject H₀</strong> at α = 0.05 (p &lt; 0.001). The model performs significantly
  worse on high-calorie recipes. This is not surprising: rich, calorie-dense dishes — layered
  cakes, braised meats, holiday bakes — combine many high-fat and high-sugar ingredients in
  non-linear ways that are harder to capture even with the engineered interaction term. Future
  work could address this by training separate models per calorie tier or incorporating
  more granular ingredient-level macro data.
</p>

| Group | RMSE | p-value | Conclusion |
|---|---|---|---|
| Low-calorie recipes | ~55 cal | &lt; 0.001 | <span class="pass">Reject H₀ — model performs significantly worse on high-calorie recipes</span> |
| High-calorie recipes | ~115 cal | &lt; 0.001 | |

</div><!-- /.content -->

<footer class="site-footer">
  <strong>Chau Nguyen</strong> &nbsp;·&nbsp; DSC 80 Final Project &nbsp;·&nbsp; UCSD &nbsp;·&nbsp; Food.com Recipes Dataset
</footer>
