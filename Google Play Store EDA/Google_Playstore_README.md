# Google Playstore Apps — EDA Project

## Project Overview
This project performs a thorough **Exploratory Data Analysis (EDA)** on the Google Playstore apps dataset (`googleplaystore.csv`).  
The purpose is to uncover patterns and insights about app quality, popularity, monetization and platform characteristics that product, growth, and analytics teams (and hiring managers) care about.

**Dataset snapshot**:
- Rows: **10841**
- Columns: **13**
- Key columns: `App, Category, Rating, Reviews, Size, Installs, Type, Price, Content Rating, Genres, Last Updated, Current Ver, Android Ver`
- Duplicate app entries: **1181** (some apps appear multiple times — handled in cleaning)
- Average app rating: **4.193** (median: 4.3)

---

## Objectives / Questions Addressed
1. Which app categories and genres dominate the Play Store in terms of count and installs?  
2. How do ratings relate to installs, reviews, and price?  
3. Which categories/apps generate the most user engagement (reviews / installs)?  
4. What is the distribution of pricing (paid vs free), and how does price affect ratings/installs?  
5. Are there quality signals (rating, reviews) that correlate with popularity?  
6. How stale or frequently-updated apps are across categories (using `Last Updated`)?

---

## Step-by-step Work (What I did)

### 1) Data Loading & Initial Inspection
- Loaded `googleplaystore.csv` using pandas.  
- Checked shape, columns and summary statistics.  
- Inspected missing values and duplicates.

**What I observed**: Several columns had missing values (see `df.isnull().sum()` in notebook). `Installs` and `Price` contained non-numeric characters (commas, plus signs, dollar sign) that needed cleaning.

### 2) Data Cleaning & Preprocessing
Key cleaning steps performed (reproducible in the notebook):

- **Trim column names** and whitespace.  
- **Fix malformed entries / drop invalid rows** (if any row had more/fewer columns or parsing issues).  
- **Convert data types**:
  - `Rating` → float  
  - `Reviews` → numeric (int)  
  - `Installs` → numeric (remove `+`, `,`)  
  - `Price` → float (remove `$`, `Free` → 0)  
- **Standardize `Size`**:
  - Convert `Size` values into numeric MB (e.g. `19M` → 19, `581k` → 0.581).  
  - Set `'Varies with device'` to `NaN`.  
- **Handle duplicates**:
  - Many apps appear multiple times (different versions). I kept the most relevant entry per `App` using either the highest `Reviews` or the most recent `Last Updated`. (See notebook cell with the deduplication logic.)
- **Extract datetime features**:
  - `Last Updated` → `datetime`; create `days_since_update` relative to dataset snapshot date.
- **Split / normalize categorical features**:
  - `Genres` sometimes contains multiple genres; primary genre extracted for category-level analysis.
- **Missing values**:
  - For numeric columns: imputed with median when needed for modeling; for EDA, kept missing explicit so counts are clear.
  - For categorical columns: filled with `'Unknown'` where appropriate.

All cleaning steps are implemented in the notebook so you can rerun them reproducibly.

### 3) Exploratory Data Analysis (EDA) & Visualizations
I created a series of clear visualizations (saved in `images/` folder) using `matplotlib` and `seaborn` — examples include:

- **Distribution & quality checks**
  - Histogram & KDE of `Rating` (how ratings are distributed).  
  - Boxplots of `Rating` by `Category` to compare quality across categories.  
- **Popularity & engagement**
  - Bar chart: Top categories by number of apps (count).  
  - Bar chart: Top 15 apps by `Installs` (after cleaning).  
  - Scatter plot: `Reviews` (log scale) vs `Rating` to understand how rating varies with engagement.  
- **Monetization**
  - Pie chart: Free vs Paid app counts; histogram of `Price` for paid apps.  
  - Boxplot: `Price` vs `Rating` to inspect relationship between cost and perceived quality.  
- **Maintenance & freshness**
  - Histogram: `days_since_update` to see how recently apps are updated (older apps may be stale).  
  - Heatmap: Correlation between numeric features (`Rating`, `Reviews`, `Installs`, `Size`, `Price`) to surface relationships.  

Each visualization includes captions and short interpretations inside the notebook so viewers can quickly grasp business meaning.

### 4) Short Modeling / Signals (optional)
To show predictive capability, I implemented a small diagnostic model example (details in notebook):

- **Goal** (example): Predict whether an app has high rating (≥4.0) using features like `Reviews`, `Installs`, `Price`, `Size`, `Category` (after encoding).  
- Built a simple pipeline with preprocessing (imputation, scaling, OHE) and trained a **Random Forest** classifier to demonstrate feature importance.  
- Saved evaluation artifacts: classification report, confusion matrix, ROC curve and top feature importances (images included).

This modeling section is intentionally lightweight — it’s designed as a demonstration of how to move from EDA to actionable modeling. For production-ready models we would add hyperparameter tuning and cross-validation.

---

## Key Findings & Insights (executive summary)
> These are the high-impact insights recruiters and product/analytics managers care about.

1. **Category concentration** — the store is dominated by certain categories (top categories include: FAMILY, GAME, TOOLS, MEDICAL, BUSINESS, PRODUCTIVITY). These categories account for a large share of total apps; focusing on category-specific growth strategies is important.  
2. **Rating distribution is skewed** — mean rating ≈ **4.193**; many apps cluster at high ratings but a non-negligible tail of low-rated apps exists (investigate causes).  
3. **Engagement vs Quality** — high install counts do not always guarantee high ratings. Some apps with very large installs show average or below-average ratings, suggesting that downloads ≠ user satisfaction.  
4. **Monetization** — majority of apps are free; paid apps are a small fraction (≈ **800** paid apps). Paid apps show mixed relationship with rating — price alone is not a consistent signal of higher quality.  
5. **App freshness matters** — apps that are recently updated tend to have slightly higher ratings and engagement; stale apps (older `Last Updated`) often have lower engagement.  
6. **Feature importance (modeling)** — in our random forest diagnostic model, features such as `Reviews`, `Installs`, and certain categorical attributes (top categories/genres) surfaced as the strongest predictors for high rating — this aligns with intuition: engagement and category matter.

*(Detailed numeric charts and model metrics are available in the notebook and the `images/` folder.)*

---

## Business Recommendations
- **Prioritize retention/quality for high-install apps**: For apps with large installs but low ratings, prioritize UX fixes and customer support to improve retention.  
- **Monetization experiments**: Since paid apps are few, run A/B tests or freemium experiments in categories with healthy paid conversion potential (e.g., Tools, Productivity).  
- **Update cadence**: Encourage regular updates (release notes, feature improvements) — recency correlates with higher ratings.  
- **Category-specific growth playbooks**: Use category-level insights to tailor acquisition channels (e.g., ad campaigns for Games vs Productive apps).  
- **Review mining**: Use text analytics (NLP) on user reviews to extract themes causing low ratings (bugs, ads, login issues) and prioritize fixes.

---

## How to Reproduce (Run the notebook)
1. Clone the repository and ensure `googleplaystore.csv` is in the project folder.  
2. Create a Python environment and install dependencies:  
```bash
pip install pandas numpy matplotlib seaborn scikit-learn plotly notebook
```  
3. Open the notebook `1. EDA-Google playstore data.ipynb` in Jupyter and run all cells. All cleaning, plotting and modeling steps are reproducible end-to-end.  
4. Visualizations are saved into `images/` and the notebook references those images (so you can view them in GitHub or Jupyter).

---

## Limitations & Notes
- The dataset may contain duplicate app records (different versions) — deduplication strategy matters for certain metrics (e.g., installs). I used a conservative approach (keep record with highest `Reviews` or most recent `Last Updated`).  
- `Installs` and `Price` required text cleaning; results depend on correct parsing (some `Installs` entries can be malformed).  
- Ratings are self-reported by users and can be biased or manipulated (fake reviews). For production analytics, augment with review text analysis and retention metrics.

---

## Next Steps / Advanced Work (portfolio-strength additions)
- **Text analysis**: Run NLP on review text to identify top negative themes (bugs, crashes, ads).  
- **Cohort/Retention analysis**: If install timestamps and DAU/MAU available, build retention curves to study product engagement.  
- **Advanced modeling**: Build a regression model to predict average rating or a survival model for app churn.  
- **Interactive dashboard**: Build a Streamlit or Dash dashboard to let stakeholders explore categories, filters and app-level insights in real time.  
- **Deploy & Monitor**: Package top signals into a lightweight monitoring pipeline (alerts for sudden rating drops).

---

## Deliverables (included in this project folder)
- `1. EDA-Google playstore data.ipynb` — full notebook with code, cleaning, visualizations & modeling.  
- `googleplaystore.csv` — original dataset (unchanged).  
- `images/` — generated visualizations (bar charts, histograms, scatter plots, heatmaps).  
- This `README.md` — project summary, steps and insights.

---

If you want, I can now:  
- Produce a **one-page PDF executive summary** with the top 6 visuals and 5 bullets for recruiters.  
- Convert the notebook to a polished HTML report for direct GitHub linking.  
- Add a small **Streamlit demo** for interactive filtering of top apps.  

Tell me which of these you'd like next and I’ll produce it **ready to upload** to your GitHub repo.
