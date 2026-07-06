# Task 5 - Exploratory Data Analysis (EDA)
**Data Analyst Internship | DataX Labs**

## Objective
Extract insights from a dataset using visual and statistical exploration (EDA).

## Dataset
**Titanic Passenger Dataset** (`titanic.csv`) - 891 rows, 15 columns.
Chosen because it contains both numeric columns (Age, Fare, SibSp, Parch, Pclass) and
categorical columns (Sex, Embarked, Class), making it ideal for practicing every EDA
technique required in this task.

Source: [seaborn-data GitHub repository](https://github.com/mwaskom/seaborn-data)

## Tools Used
- Python
- Pandas
- Matplotlib
- Seaborn
- Jupyter Notebook

## What I Did
1. Loaded the dataset and inspected it using `.info()`, `.describe()`, and `.value_counts()`.
2. Performed **univariate analysis** using histograms (Age, Fare, Survived, Pclass distributions).
3. Performed **bivariate analysis** using boxplots (Age by Class, Fare by Survival) and a scatterplot (Age vs Fare).
4. Performed **multivariate analysis** using a pairplot and a correlation heatmap across all numeric features.
5. Checked correlation and multicollinearity between numeric features.
6. Wrote observations under every visual.
7. Summarized all key findings at the end of the notebook and in the PDF report.

## Key Findings
- Only **38.4%** of passengers survived overall.
- **Sex** was the strongest survival factor: women survived at **74.2%** vs men at **18.9%**.
- **Passenger class** mattered heavily: 1st class survival was **63.0%** vs **24.2%** in 3rd class.
- **Fare and Class** are strongly negatively correlated (**-0.55**).
- **Fare** is heavily right-skewed (skewness ≈ 4.79); median is a better summary than mean.
- **Age** (~20% missing) and **Deck** (~77% missing) have significant missing data.
- No serious multicollinearity was found among numeric features (all correlations within ±0.55).

## Repository Contents
| File | Description |
|------|-------------|
| `EDA_Task5.ipynb` | Full Jupyter Notebook with code, charts, and written observations |
| `EDA_Report_Task5.pdf` | PDF report summarizing all findings with charts |
| `titanic.csv` | Dataset used for the analysis |
| `images/` | All charts exported as PNG files |

## Interview Questions & Answers

**1. Which plots do you use to check correlation?**
Scatterplots (for two variables) and a correlation heatmap (for many variables at once) via `sns.heatmap(df.corr())`.

**2. How do you handle skewed data?**
Apply a transformation such as log, square root, or Box-Cox to reduce skew, or use the median instead of the mean as a summary statistic. Here, Fare (skew ≈ 4.79) would benefit from a log transform before modeling.

**3. How to detect multicollinearity?**
Check the correlation matrix/heatmap for high correlations (typically above 0.8 or below -0.8) between independent variables, or calculate the Variance Inflation Factor (VIF) for a more formal test.

**4. What are univariate, bivariate, and multivariate analyses?**
- Univariate: analyzing a single variable (e.g., a histogram of Age).
- Bivariate: analyzing the relationship between two variables (e.g., Age vs Fare scatterplot).
- Multivariate: analyzing relationships across three or more variables at once (e.g., a pairplot or heatmap).

**5. Difference between heatmap and pairplot?**
A heatmap shows a matrix of correlation *values* between all numeric columns in one compact grid. A pairplot shows the actual *scatterplots* (and distributions) between every pair of numeric columns, giving a more detailed but larger visual.

**6. How do you summarize your insights?**
By combining statistical summaries (`.describe()`, correlations) with visual patterns from the charts, then writing short, plain-language observations under each chart and a final consolidated summary section.

**7. What is EDA and why is it important?**
EDA (Exploratory Data Analysis) is the process of investigating a dataset to understand its structure, patterns, relationships, and anomalies before formal modeling. It's important because it reveals data quality issues, guides feature selection, and prevents building models on flawed assumptions.
