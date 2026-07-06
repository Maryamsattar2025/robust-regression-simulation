# robust-regression-simulation
# Robust Regression Under Outliers and Heavy-Tailed Noise

## Project Overview

This project compares three regression methods under simulated data scenarios where the standard assumptions of linear regression may be violated. In practice, real datasets can contain unusual observations, outliers, or heavy-tailed noise, and such features can strongly affect the performance of ordinary least squares regression. The aim of this project is to examine whether more robust regression methods provide better performance when the data are contaminated.

The project uses simulated data generated from a simple linear regression model and evaluates how three methods behave under clean and contaminated conditions.

## Regression Methods Compared

The following methods are compared in this project:

### 1. Ordinary Least Squares (OLS)

Ordinary least squares is the standard linear regression method. It estimates the regression line by minimizing the sum of squared residuals. OLS works well when the assumptions of the linear model are approximately satisfied, but it can be highly sensitive to outliers.

### 2. Huber Regression

Huber regression is a robust regression method that reduces the influence of extreme observations. It combines properties of squared loss and absolute loss, making it less sensitive to large outliers than OLS.

### 3. Quantile Regression

Quantile regression estimates conditional quantiles of the response variable. In this project, the median regression line is estimated using the 0.5 quantile. Median-based regression is often more robust to outliers than mean-based regression.

---

## Objective

The main objective of this project is to compare the performance of OLS, Huber regression, and Quantile regression under three different simulated scenarios:

1. **Clean Data**
   Data generated from a linear regression model with Gaussian noise.

2. **Heavy-Tailed Noise**
   Data generated from the same regression model, but with heavy-tailed noise instead of Gaussian noise.

3. **Outlier Contamination**
   Data generated from the linear model where a proportion of response values are contaminated with large outliers.

The project investigates how robust regression methods perform relative to OLS when the data deviate from ideal assumptions.

---

## Data-Generating Model

The simulated data are generated from the following linear regression model:

[
y = 3 + 2X + \varepsilon
]

where:

* (X) is the predictor variable
* (y) is the response variable
* (\varepsilon) is the random noise term

The predictor values are generated from a uniform distribution, while the noise distribution varies depending on the scenario.

---

## Simulated Scenarios

### Scenario 1: Clean Data

In the clean-data scenario, the noise term is generated from a Gaussian distribution. This corresponds to a setting in which the assumptions of ordinary linear regression are approximately satisfied.

### Scenario 2: Heavy-Tailed Noise

In the heavy-tailed scenario, the noise term is generated from a Student-t distribution with low degrees of freedom. This creates more extreme values than Gaussian noise and allows us to test the stability of the regression methods when the error distribution has heavy tails.

### Scenario 3: Outlier Contamination

In the outlier scenario, most observations are generated from the clean linear model, but a fraction of response values are deliberately shifted upward by a large amount. This introduces strong outliers and allows us to study how sensitive each regression method is to contamination.

---

## Evaluation Metrics

The regression methods are compared using the following metrics:

### RMSE (Root Mean Squared Error)

RMSE measures the average size of prediction errors, with larger errors penalized more heavily because of squaring.

### MAE (Mean Absolute Error)

MAE measures the average absolute prediction error and is less sensitive to very large errors than RMSE.

These metrics are computed separately for each regression method and each simulated scenario.

---

## Workflow of the Project

The notebook follows these main steps:

1. Import the required Python libraries
2. Define functions to generate the three simulated datasets
3. Visualize the datasets
4. Fit OLS, Huber regression, and Quantile regression
5. Evaluate each method using RMSE and MAE
6. Compare performance across scenarios
7. Plot regression fits and summarize the results
8. Interpret how robust methods behave under heavy-tailed noise and outliers

---

## Repository Structure

```text
robust-regression-simulation/
│
├─ robust_regression_simulation.ipynb
├─ README.md
├─ requirements.txt
└─ figures/
```

### File descriptions

* **robust_regression_simulation.ipynb**
  Main notebook containing data simulation, model fitting, evaluation, visualizations, and conclusions.

* **README.md**
  Project description, methodology, and instructions for use.

* **requirements.txt**
  List of Python libraries required to run the notebook.

* **figures/**
  Optional folder for storing plots exported from the notebook.

---

## Libraries Used

The project is implemented in Python using the following libraries:

* **NumPy** for numerical computations and random data generation
* **Pandas** for storing and displaying results
* **Matplotlib** for visualizations
* **scikit-learn** for OLS and Huber regression
* **statsmodels** for Quantile regression

---

## How to Run the Project

### 1. Clone or download the repository

You can either clone the repository using Git or download it as a ZIP file from GitHub.

### 2. Install the required libraries

Install the required packages using:

```bash
pip install -r requirements.txt
```

If you prefer, you can also install them manually:

```bash
pip install numpy pandas matplotlib scikit-learn statsmodels
```

### 3. Open the notebook

Launch Jupyter Notebook or JupyterLab and open:

`robust_regression_simulation.ipynb`

### 4. Run all cells

Run the notebook from top to bottom to:

* generate the datasets
* fit the regression models
* compute RMSE and MAE
* produce the plots and comparison tables

---

## Expected Findings

Although the exact results may vary slightly due to simulation, the overall pattern is expected to be:

* **OLS** performs well when the data are clean and approximately satisfy the standard regression assumptions.
* **Huber regression** is often more stable when outliers are present because it reduces the influence of extreme observations.
* **Quantile regression** can also provide robustness under contaminated data, especially when the response distribution is affected by outliers.

In general, robust methods are expected to become more competitive or outperform OLS when the data contain heavy-tailed noise or outliers.

---

## Statistical Interpretation

This project highlights an important statistical idea: **the choice of regression method should depend on the nature of the data and the assumptions one is willing to make**.

Ordinary least squares is efficient when the linear model assumptions hold, but it can be unstable when those assumptions are violated. Robust regression methods provide alternatives that are less sensitive to contamination and may produce more reliable results in non-ideal settings.

---

## Possible Extensions

This project can be extended in several ways:

* use multiple predictors instead of a single predictor
* increase the number of simulation scenarios
* vary the proportion of outliers
* compare additional robust methods such as RANSAC or Theil-Sen regression
* include train/test splits for predictive evaluation
* compare estimated coefficients across repeated simulations
* implement Bayesian or Student-t regression for a more advanced robust modeling approach

---

## Why This Project Is Relevant

This project is useful as a beginner-friendly portfolio project in **statistics, data analysis, and machine learning** because it demonstrates:

* understanding of regression modeling
* awareness of model assumptions
* ability to simulate data
* comparison of classical and robust statistical methods
* use of Python for statistical computing and visualization
* interpretation of results rather than only running code

It is also relevant for applications involving **statistical inference, robust methods, and machine learning**, where understanding the behavior of models under imperfect data conditions is important.

---

## Author Note

This project was developed as a small simulation-based study of robust regression methods. It is intended as a portfolio project to demonstrate practical implementation of regression analysis, robustness concepts, and model comparison in Python.
