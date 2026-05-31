# TMDB Movies Profitability Analysis
### What makes a movie financially successful?

---

## Business Problem

The global film industry spends billions annually on production — yet most movies fail to turn a profit. This project analyzes **8,293 movies** from the TMDB dataset to answer the question every producer, investor, and streaming platform needs to understand:

**What actually drives movie profitability — and what does not?**

---

## Dataset

| Detail | Value |
|--------|-------|
| Source | TMDB Movies Dataset |
| Raw Size | ~10,800 movies |
| After Cleaning | 8,293 movies |
| Key Metric | Inflation-adjusted profit & ROI |

### Key Features Used

| Feature | Description |
|---------|-------------|
| `budget_adj` | Inflation-adjusted production budget |
| `revenue_adj` | Inflation-adjusted box office revenue |
| `profit` | Revenue minus budget (engineered) |
| `roi` | Return on investment (engineered) |
| `popularity` | Audience engagement score |
| `release_year` | Year of theatrical release |
| `director` | Movie director(s) |
| `main_genre` | Primary genre (engineered from multi-genre strings) |

---

## Project Workflow

```
1. Data Cleaning & Validation
         ↓
2. Feature Engineering (Profit, ROI, Main Genre)
         ↓
3. Exploratory Data Analysis (EDA)
         ↓
4. Visualization & Pattern Discovery
         ↓
5. Key Findings & Business Recommendations
```

---

## Data Cleaning & Feature Engineering

Key preparation steps:
- Removed movies with zero or missing budget and revenue values
- Converted and validated all numerical columns
- Created two new analytical features:
  - **Profit** = `revenue_adj - budget_adj`
  - **ROI** = `profit / budget_adj`
- Extracted `main_genre` from multi-genre strings
- Filtered directors with fewer than 5 movies to ensure statistical relevance

---

## Exploratory Data Analysis

### Budget & Revenue Trend Over the Years

![Average Budget Over the Years](Average%20Budget%20Over%20the%20Years.png)

Movie budgets have increased dramatically over the decades — but higher spending does not guarantee proportionally higher returns.

---

### Average Profit Over the Years

![Average Profit Over the Years](Average%20Profit%20Over%20the%20Years.png)

Profit trends reveal that the most profitable eras in cinema do not always align with the highest-budget periods.

---

### Budget vs Revenue

![Budget vs Revenue](Budget%20vs%20Revenue.png)

Higher budgets generally lead to higher revenues — but with significantly increasing financial risk. The relationship is positive but not linear.

---

### Budget & Revenue Distribution

![Budget and Revenue](Budget%26%20Revenue.png)

Revenue distribution is heavily right-skewed — a small number of blockbusters generate disproportionate profits.

---

### Average Profit by Genre

![Average Profit by Genre](Average%20Profit%20by%20Genre.png)

Profitability varies significantly across genres. High-budget genres are not always the most profitable — ROI often tells a very different story.

---

### Top 10 Directors by Average Profit

![Top 10 Directors by Average Profit](Top%2010%20Directors%20by%20Average%20Profit.png)

Directors with consistent track records deliver significantly higher average profits — indicating that the human factor matters as much as the budget.

---

### Popularity vs Profit

![Popularity vs Profit](Popularity%20vs%20Profit.png)

Popularity shows a weak to moderate positive correlation with profit. A popular movie is more likely to be profitable — but popularity alone is not a reliable predictor.

---

### Correlation Heatmap

![Correlation Heatmap](Correlation%20Heatmap.png)

Budget and revenue are the strongest correlated variables. Popularity has a weaker relationship with financial performance than commonly assumed.

---

## Key Findings

| Finding | Insight |
|---------|---------|
| Budget vs Profit | Higher budgets increase revenue but also increase financial risk — ROI often decreases at very high budgets |
| Director Consistency | Directors with 5+ movies show measurable patterns — some consistently outperform industry averages |
| Genre ROI | Animation and Family genres often deliver the highest ROI despite not having the largest budgets |
| Popularity | Weak to moderate correlation with profit — virality does not guarantee financial success |
| Budget Inflation | Movie budgets have tripled since the 1980s but average profit margins have not grown proportionally |

---

## Business Recommendations

**1. Prioritize ROI over Raw Revenue**
Gross revenue is a vanity metric. A $50M film returning $150M is more strategically valuable than a $200M film returning $400M.

**2. Back Consistent Directors**
Historical data shows that director track record is a stronger predictor of profitability than genre or budget level alone.

**3. Rethink the Blockbuster Formula**
Mid-budget films in high-ROI genres consistently outperform mega-budget productions on a returns basis.

**4. Use Popularity as a Signal, Not a Guarantee**
Pre-release popularity is useful for marketing planning but should not drive production budget decisions.

---

## Limitations

- Marketing and distribution costs are not included in the dataset
- Popularity scores are captured at a single point in time
- Results may reflect English-language and US market bias
- Some temporal bias remains in older inflation-adjusted data

---

## Tools & Technologies

| Tool | Usage |
|------|-------|
| Python | Core analysis language |
| Pandas & NumPy | Data cleaning and feature engineering |
| Matplotlib & Seaborn | All visualizations |
| Jupyter Notebook | Development environment |

---

## Project Structure

```
tmdb-movies/
│
├── tmdb-movies.ipynb                        <- Main analysis notebook
├── tmdb_movies_data.csv                     <- Source dataset
├── Average Budget Over the Years.png
├── Average Profit Over the Years.png
├── Average Profit by Genre.png
├── Budget vs Revenue.png
├── Budget& Revenue.png
├── Correlation Heatmap.png
├── Popularity vs Profit.png
├── Top 10 Directors by Average Profit.png
└── README.md
```

---

## How to Run

```bash
# 1. Clone the repo
git clone https://github.com/RaniaMofeed/tmdb-movies.git

# 2. Install requirements
pip install pandas numpy matplotlib seaborn jupyter

# 3. Open the notebook
jupyter notebook tmdb-movies.ipynb
```

---

*Analysis by **Rania Mofeed** | [LinkedIn](https://www.linkedin.com/in/raniamofeed) | [GitHub](https://github.com/RaniaMofeed)*
