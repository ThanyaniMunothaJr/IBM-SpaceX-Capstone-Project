# SpaceX Falcon 9 First Stage Landing Prediction

**Applied Data Science Capstone**

## Project Overview

SpaceX advertises Falcon 9 launches at $62 million, while competitors charge upwards of $165 million. Much of that savings comes from SpaceX's ability to reuse the first stage of the rocket — but only when it lands successfully.

This project builds a complete data science pipeline to answer one central question: **can we predict whether the Falcon 9 first stage will land successfully, using data available before launch?** A reliable answer to that lets us estimate the cost of a launch, which is useful if a competing company wants to bid against SpaceX.

The workflow covers the full data science lifecycle: data collection, wrangling, exploratory data analysis, interactive visual analytics, and predictive modeling.

## Key Findings

- Trained and tuned four classification models (Logistic Regression, SVM, Decision Tree, KNN) with `GridSearchCV`. The **Decision Tree classifier performed best**, reaching **94.4% accuracy** on the held-out test set.
- Launch success climbed steadily after 2013 as SpaceX refined its landing techniques.
- **KSC LC-39A** has the highest per-site success ratio (~82%) of the three launch locations in the dataset.
- Payload mass, orbit type, and flight number all show a visible relationship with landing success.

## Repository Contents

| File | Description |
|---|---|
| `jupyter-labs-spacex-data-collection-api.ipynb` | Collects launch data from the SpaceX v4 REST API |
| `jupyter-labs-webscraping.ipynb` | Scrapes and parses the Wikipedia Falcon 9 launch table with BeautifulSoup |
| `labs-jupyter-spacex-Data wrangling.ipynb` | Cleans the combined dataset and engineers the binary landing outcome label |
| `edadataviz.ipynb` | Exploratory data analysis using Matplotlib/Seaborn visualizations |
| `jupyter-labs-eda-sql-coursera_sqllite.ipynb` | Exploratory data analysis using SQL queries against a SQLite database |
| `lab_jupyter_launch_site_location.ipynb` | Interactive Folium map of launch sites and outcomes |
| `SpaceX Machine Learning Prediction Part_5.ipynb` | Builds, tunes, and evaluates the classification models |
| `Task1.png`, `Task2.png`, `Task3 & 4.png` | Screenshots of the Plotly Dash dashboard |
| `Data_Science_Capstone_Project_Report.pdf` | Final presentation summarizing the full project |

## Methodology

1. **Data Collection** — Combined two sources for robustness: the SpaceX REST API and a scraped Wikipedia table, both filtered to Falcon 9 launches (excluding Falcon 1).
2. **Data Wrangling** — Derived a binary `Class` label (1 = successful landing, 0 = unsuccessful) from the landing outcome column, and handled missing values.
3. **EDA (Visualization + SQL)** — Explored relationships between flight number, payload mass, launch site, orbit type, and landing success.
4. **Interactive Visual Analytics** — Built a Folium map of launch sites colored by outcome, and a Plotly Dash dashboard with dropdown and payload-range filtering.
5. **Predictive Analysis** — Standardized features, split the data 80/20, and used `GridSearchCV` (cv=10) to tune four classifiers, selecting the best by test-set accuracy and confusion matrix.

## Tools & Libraries

`Python` · `pandas` · `NumPy` · `Matplotlib` · `Seaborn` · `SQLite` · `BeautifulSoup` · `Folium` · `Plotly Dash` · `scikit-learn`

## Results Summary

| Model | Cross-Validation Accuracy | Test Accuracy |
|---|---|---|
| Logistic Regression | 84.6% | 83.3% |
| SVM | 84.8% | 83.3% |
| **Decision Tree** | **95.0%** | **94.4%** |
| KNN | 84.8% | 83.3% |

## Author

**Thanyani Munotha**
Part of the IBM Data Science Professional Certificate on Coursera.
