# Predictive Modeling of Bias in NYC Stop-and-Frisk Data

_An analytical framework to uncover and mitigate racial and socioeconomic biases in New York City stop-and-frisk incidents through machine learning and geospatial data integration._

## Table of Contents

1. [Description](#description)  
2. [Key Features](#key-features)  
3. [Tech Stack](#tech-stack)  
4. [Installation](#installation)  
5. [Data Sources](#data-sources)  
6. [Usage](#usage)  
7. [Project Structure](#project-structure)  
8. [Configuration](#configuration)

---

## Description

This project investigates systemic biases in the U.S. criminal justice system by analyzing 2023 NYPD stop-and-frisk records alongside neighborhood financial health and demographic datasets. We apply exploratory data analysis, geospatial mapping, and predictive modeling to:  

- Quantify racial and socioeconomic disparities in stops and arrests  
- Engineer features capturing neighborhood-level financial vulnerability  
- Train and evaluate interpretable classifiers (e.g., logistic regression, random forest) to predict arrest likelihood  
- Assess fairness using metrics such as Disparate Impact, Equal Opportunity Difference, and Demographic Parity  
- Provide actionable insights for policy-makers and advocacy groups aiming to reduce bias

## Key Features

- **Data Integration**: Merges stop-and-frisk incidents with neighborhood financial health indices and PUMA-level demographics.  
- **Exploratory Analysis**: Visualizations of stop outcomes by race, borough, and financial indicators.  
- **Feature Engineering**: Creation of composite financial vulnerability scores and geospatial join via precinct or PUMA codes.  
- **Predictive Modeling**: Implementation of logistic regression, random forest, and gradient boosting with hyperparameter tuning via GridSearchCV.  
- **Fairness Evaluation**: Computation of fairness metrics to detect and quantify bias across demographic groups.  
- **Geospatial Mapping**: Choropleth maps of arrest rates and financial health across NYC neighborhoods.

## Tech Stack

- **Language:** Python 3.8+  
- **Notebooks:** Jupyter Notebook (`INSY 662 Project.ipynb`)  
- **Libraries:** pandas, geopandas, numpy, scikit-learn, matplotlib, seaborn, folium, fairlearn  
- **Data:** stop-and-frisk CSV, Neighborhood Financial Health CSV, PUMA demographic CSV, racial disparities outcomes CSV

## Installation

1. **Clone the repository**:  
   ```bash
   git clone https://github.com/your-username/insy662-stopfrisk-bias.git
   cd insy662-stopfrisk-bias
   ```
2. **Set up a virtual environment**:  
   ```bash
   python -m venv venv
   source venv/bin/activate  # macOS/Linux
   venv\Scripts\activate  # Windows
   ```
3. **Install dependencies**:  
   ```bash
   pip install -r requirements.txt
   ```

## Data Sources

- **`Stop-and-Frisk 2023.csv`**: NYPD incident records including demographics, stop reasons, outcomes.  
- **`Neighborhood_Financial_Health.csv`**: PUMA-level financial health indicators (poverty rate, median income, access to services).  
- **`precinct-puma.csv`**: Mapping between police precincts and census PUMA codes.  
- **`racial_disparities_outcomes.csv`**: Pre-computed metrics on racial disparities from academic sources.

> Ensure all CSVs are placed in the `data/` directory before running analysis.

## Usage

1. **Open the notebook**:  
   ```bash
   jupyter notebook "INSY 662 Project.ipynb"
   ```
2. **Execute cells** in order:  
   - Data cleaning and merging  
   - Exploratory visualizations and geospatial plots  
   - Feature engineering and dataset splits  
   - Model training and evaluation  
   - Fairness metric computations  
   - Interpretability analysis and policy recommendations

## Project Structure

```
insy662-stopfrisk-bias/
├── README_INSY662.md        # This file
├── requirements.txt         # Python dependencies
├── data/                    # Raw and processed datasets
│   ├── Stop-and-Frisk 2023.csv
│   ├── Neighborhood_Financial_Health.csv
│   ├── precinct-puma.csv
│   └── racial_disparities_outcomes.csv
├── INSY 662 Project.ipynb   # Analysis notebook
└── figures/                 # Generated charts and maps
    ├── stop_rates_borough.png
    └── fairness_metrics.png
```

## Configuration

- **`random_state`**: Set a constant seed for reproducibility when splitting data and training models.  
- **`fairness_thresholds`**: Adjustable parameters in the fairness evaluation cell to test different bias tolerance levels.  
- **Map styling options**: Modify colormap and boundary definitions in the mapping functions as needed.
