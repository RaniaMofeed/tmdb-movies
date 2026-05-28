# Movie Profitability Analysis (TMDB Dataset)

## Project Overview
This project analyzes movie data from the TMDB dataset to understand what drives movie profitability.

Using exploratory data analysis (EDA), feature engineering, and data visualization, the project answers key business-driven questions related to budgets, genres, directors, popularity, and trends over time. 

The goal is to extract **actionable insights** that could help production companies, investors, or streaming platforms make data-informed decisions.

## Business Questions
The analysis focuses on answering the following questions:
* Which directors consistently make profitable movies?
* Which movie genres are the most profitable?
* Does a higher budget lead to higher revenue?
* Does popularity correlate with profit?
* Are recent movies more profitable than older ones?
* How has movie budget changed over the years?

---

## Dataset
* **Source:** TMDB Movies Dataset
* **Initial size:** ~10,800 movies
* **Final size after cleaning:** 8,293 movies

### Key Features Used
| Feature | Description |
| :--- | :--- |
| `budget_adj` | Inflation-adjusted budget |
| `revenue_adj` | Inflation-adjusted revenue |
| `profit` | Revenue minus budget |
| `roi` | Return on investment |
| `popularity` | Audience popularity metric |
| `release_year` | Year of release |
| `director` | Movie director(s) |
| `main_genre` | Engineered feature for primary category |

---

##  Data Cleaning & Preparation
Key data preparation steps included:
1. **Filtering:** Removing movies with missing or zero budgets/revenues.
2. **Validation:** Converting data types and validating numerical columns.
3. **Handling Noise:** Removing unrealistic values and handling missing metadata.
4. **Feature Creation:** Generating new analytical features:
    * **Profit**
    * **ROI**
    * **Main Genre** (extracted from multi-genre strings)

---

##  Feature Engineering
New features were engineered to support deeper insights:
* **Profit Formula:** $profit = revenue\_adj - budget\_adj$
* **ROI Formula:** $ROI = \frac{profit}{budget\_adj}$
* **Consistency Check:** Filtering directors with a minimum number of movies (e.g., 5+) to ensure statistical relevance.

---

##  Exploratory Data Analysis (EDA)

###  Directors & Profitability
* Directors with multiple movies were analyzed to avoid "one-hit" bias.
* Average profit per director was calculated for those with at least 5 movies.
> **Insight:** Some directors consistently deliver high average profits, indicating strong decision-making and audience alignment.

###  Genre Analysis
* Profitability varies significantly across genres.
> **Insight:** High-budget genres are not always the most profitable—ROI often tells a different story.

###  Budget vs. Revenue
* Scatter plots and log-scale visualizations were used to identify trends.
> **Insight:** Higher budgets generally lead to higher revenues, but with significantly increasing financial risk.

###  Popularity vs. Profit
* Correlation analysis was performed between audience engagement and financial success.
> **Insight:** Popularity shows a weak to moderate positive correlation with profit; popular movies are more likely, but not guaranteed, to be profitable.

###  Trends Over Time
* Movie budgets have increased significantly over the years.
> **Insight:** Higher budgets over time do not always translate into proportionally higher profits.

---

##  Limitations
* **Marketing Costs:** Marketing and distribution costs are not included in the dataset.
* **Snapshot Data:** Popularity is measured at a single point in time.
* **Regional Bias:** Results may vary by specific global regions and markets.
* **Temporal Bias:** While inflation-adjusted, some temporal biases remain in older data.

---

##  Key Takeaways
1. **Strategy > Spend:** Profitability depends on strategy, not just budget size.
2. **Metric Priority:** ROI is more informative than raw profit alone.
3. **The Human Factor:** Genre and director consistency matter more than isolated successes.
4. **Risk Management:** Data-driven decision-making can significantly reduce financial risk in production.

---

##  Tools & Technologies
* **Language:** Python
* **Data Handling:** Pandas & NumPy
* **Visualization:** Matplotlib & Seaborn
* **Environment:** Jupyter Notebook
