# Movies-Correlation

## Table of Contents
1. [Project Overview](#project-overview)
2. [Data Sources](#data-sources)
3. [Tools Used](#tools-used)
4. [Data Cleaning/Preparation](#data-cleaningpreparation)
5. [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
6. [Data Analysis](#data-analysis)
7. [Results/Findings](#resultsfindings)
8. [Recommendations](#recommendations)
9. [Limitations](#limitations)
10. [References](#references)

## Project Overview
This project analyzes a movie dataset to identify correlations between attributes such as budget, gross revenue, votes, and runtime. By leveraging Python, Pandas, NumPy, Seaborn, and Matplotlib, it cleans the data, converts categorical variables to numeric codes, and visualizes relationships through a correlation heatmap to uncover factors driving box office success.

## Data Sources
The dataset used in this project, movies.csv, includes detailed information on movies, such as:

- Movie details (name, rating, genre, year, release date, director, writer, star, country, company)
- Performance metrics (score, votes, budget, gross revenue, runtime)

## Tools Used
The project leverages a range of modern data analysis and visualization tools, including:

- **Programming Language:** Python 3 [https://www.python.org]
- **Libraries:**
pandas – data manipulation
numpy – numerical operations
matplotlib and seaborn – data visualization


- **Environment:** Jupyter Notebook [https://www.anaconda.com/products/distribution]

## Data Cleaning/Preparation
Key cleaning steps included:

- Loaded the dataset with error handling for file-not-found scenarios.
- Checked for missing values, identifying 28% missing in budget and 2% in gross.
- Imputed missing values in budget, gross, and runtime with their medians.
- Dropped rows with remaining missing values (e.g., score, votes).
- Converted categorical columns (name, rating, genre, released, director, writer, star, country, company) to numeric codes using astype('category') and cat.codes.
- Preserved the original DataFrame by creating a copy (df_numerized) for numerization.

## Exploratory Data Analysis (EDA)
The EDA focused on answering the following questions:

- What are the top-grossing movies in the dataset?
- How do numerical attributes (e.g., budget, gross, votes, runtime) correlate with each other?
- Are there significant relationships between movie features after converting categorical variables to numeric codes?

Visual tools, such as a correlation heatmap, were used to reveal patterns and relationships. 

## Data Analysis
### **Key Code and Features:**

- **Summary Statistics:** Sorted movies by gross revenue to identify top performers.
- **Numerization:** Converted categorical columns to numeric codes to enable correlation analysis.
- **Correlation Analysis:** Computed Pearson correlations for all features and visualized them with a heatmap.
- **Correlation Pairs:** Identified high correlations (absolute value > 0.5) to highlight significant relationships.

### ***Sample Code Snippet – Correlation Heatmap***
```python
import seaborn as sns
import matplotlib.pyplot as plt

# Compute correlation matrix
correlation_matrix = df_numerized.corr(method='pearson')

# Plot heatmap
plt.figure(figsize=(12, 8))
sns.heatmap(correlation_matrix, annot=True, cmap='coolwarm', fmt='.2f')
plt.title('Correlation Matrix for Movies')
plt.xlabel('Movie Features')
plt.ylabel('Movie Features')
plt.show()
```

## Results/Findings
The analysis yielded several significant insights:

- **High Correlations:** Strong positive correlations were found between budget and gross revenue, and between votes and gross, indicating that higher budgets and more audience engagement are associated with higher box office earnings.
- **Top-Grossing Movies:** Movies like Avatar and Avengers: Endgame topped the gross revenue list, driven by high budgets and votes.
- **Weak Correlations:** Categorical features (e.g., genre, director) showed weaker correlations with financial metrics after numerization, suggesting limited direct impact on gross revenue.

## Recommendations
Based on the analysis, the following recommendations are proposed:

- **Production Investment:** Studios should prioritize higher budgets for films targeting high box office returns, as budget strongly correlates with gross revenue.
- **Audience Engagement:** Focus on strategies to increase audience engagement (e.g., marketing to boost votes), as it correlates with higher earnings.
- **Data-Driven Decisions:** Use correlation insights to guide genre and casting decisions, though their direct impact may be limited.
- **Further Analysis:** Explore temporal trends or additional features (e.g., marketing spend) to enhance understanding of box office success.

## Limitations
While the analysis provides valuable insights, it is important to note the following limitations:

- **Missing Data:** Imputation of missing values in budget and gross may introduce bias.
- **Static Dataset:** The analysis lacks temporal trends, limiting insights into changing market dynamics.
- **Categorical Numerization:** Converting categorical variables to numeric codes may oversimplify relationships.
- **Limited Scope:** The dataset does not include external factors like marketing budgets or audience demographics.

## References

- Python Data Science Handbook by Jake VanderPlas – for techniques in data cleaning and analysis.
- Official documentation for Pandas, NumPy, Matplotlib, and Seaborn – [https://pandas.pydata.org] [https://numpy.org] [https://matplotlib.org] [https://seaborn.pydata.org]
- Dataset: movies.csv [https://kaggle.com]
