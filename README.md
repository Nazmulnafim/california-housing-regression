# California Housing Price Prediction using Machine Learning

This project presents an end-to-end machine learning workflow for predicting California housing prices using the California Housing dataset from Scikit-learn. The notebook demonstrates data understanding, exploratory data analysis (EDA), feature engineering, preprocessing with pipelines, model training, hyperparameter tuning, feature selection, and model evaluation.

---

## Project Overview

The objective of this project is to predict the **median house value (MedHouseVal)** based on several housing and demographic features, including:

- Median Income
- House Age
- Average Rooms
- Average Bedrooms
- Population
- Average Occupancy
- Latitude
- Longitude

Since the target variable is continuous, this is a **Supervised Regression** problem.

---

## Dataset

**Source:** California Housing Dataset (`sklearn.datasets.fetch_california_housing()`)

The dataset contains housing information collected from California census data.

### Features

| Feature | Description |
|----------|-------------|
| MedInc | Median income in block group |
| HouseAge | Median house age |
| AveRooms | Average number of rooms |
| AveBedrms | Average number of bedrooms |
| Population | Block population |
| AveOccup | Average household occupancy |
| Latitude | Latitude coordinate |
| Longitude | Longitude coordinate |

**Target Variable**

- **MedHouseVal** – Median House Value

---

# Project Workflow

The notebook follows a complete machine learning pipeline:

- Business Understanding
- Dataset Loading
- Exploratory Data Analysis (EDA)
- Data Cleaning
- Feature Engineering
- Data Splitting
- Outlier Analysis
- Baseline Linear Regression
- Ridge Regression
- Lasso Regression
- Hyperparameter Tuning (GridSearchCV)
- Data Preprocessing using Pipelines
- Cross Validation
- Feature Selection
- Model Comparison

---

# Exploratory Data Analysis

The project includes:

- Dataset information
- Summary statistics
- Missing value analysis
- Duplicate checking
- Correlation heatmap
- Distribution plots
- Histograms
- Boxplots
- Skewness analysis

### Key Findings

- Median Income has the strongest positive correlation with house prices.
- Average Occupancy has a negative correlation with the target.
- The target variable is right-skewed and capped at 5.
- HouseAge is also capped at its maximum value.
- High-income observations were treated as valid observations instead of erroneous outliers.

---

# Feature Engineering

Two new features were created to improve model performance.

### RoomsPerBedroom

Represents the ratio of average rooms to average bedrooms and provides an estimate of household size.

### PopulationDensity

Represents the population density of each block group.

---

# Data Cleaning

The notebook performs:

- Missing value inspection
- Duplicate checking
- Data type verification

The dataset contained:

- No missing values
- No duplicate records

---

# Outlier Analysis

Instead of removing extreme values using IQR or Z-score methods, the notebook performs an analysis of each feature individually.

Observations include:

- High-income values are realistic and therefore retained.
- Average rooms and population exhibit right-skewed distributions.
- Log transformation is applied where appropriate.
- No aggressive outlier removal was performed because it negatively affected model performance.

---

# Machine Learning Models

The following regression models were implemented:

- Linear Regression
- Ridge Regression
- Lasso Regression

---

# Hyperparameter Tuning

GridSearchCV was used to optimize the Ridge Regression model.

---

# Data Preprocessing

Scikit-learn Pipelines were used to create a reproducible preprocessing workflow.

The preprocessing pipeline includes:

- Log Transformation
- Feature Scaling (StandardScaler)
- Model Training

---

# Model Evaluation

The models were evaluated using multiple regression metrics, including:

- R² Score
- Mean Absolute Error (MAE)
- Mean Squared Error (MSE)
- Root Mean Squared Error (RMSE)

Cross-validation was also performed to evaluate model generalization.

---

# Feature Selection

Feature selection was conducted to compare model performance using different subsets of features.

The notebook also discusses why a model with the highest R² score is not always the best model, emphasizing the importance of:

- Generalization
- Cross-validation
- Prediction error (MAE/RMSE)
- Model complexity

---

# Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn

---

# Repository Structure

```
california-housing-preprocessing/
│
├── data/
│   └── README.md
│
├── figures
    └── correlation.png
    └── feature importance.png
    └── histogram.png
│
├── notebooks/
│   └── california_housing_analysis.ipynb
│
├── LICENSE
├── README.md
└── requirements.txt
```

---

# Key Learning Outcomes

- End-to-end regression workflow
- Exploratory Data Analysis
- Feature Engineering
- Data Cleaning
- Log Transformation
- Machine Learning Pipelines
- Ridge & Lasso Regression
- Hyperparameter Tuning
- Cross Validation
- Feature Selection
- Model Evaluation

---

# Results

The notebook compares multiple regression models and preprocessing strategies to determine the most effective approach for predicting California housing prices.

One important finding is that **retaining the original data distribution (without aggressive outlier removal) resulted in better Linear Regression performance**, indicating that many extreme observations represented genuine housing characteristics rather than erroneous data.

---

## Author

**Mohammad Nazmul Islam**