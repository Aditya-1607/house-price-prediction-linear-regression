# Activity 2: Simple House Price Prediction

<p align="center">
  <img src="https://img.shields.io/badge/Course-ADPC509-blue" alt="Course">
  <img src="https://img.shields.io/badge/Unit-II%20Regression-purple" alt="Unit">
  <img src="https://img.shields.io/badge/Python-3.8%2B-blue" alt="Python">
  <img src="https://img.shields.io/badge/Scikit--Learn-Linear%20Regression-orange" alt="Scikit-learn">
</p>

## Academic Information

| Field | Details |
|---|---|
| **Course** | Machine Learning (`ADPC509`) |
| **Unit** | Unit II — Supervised Learning: Regression |
| **Activity** | Activity 2 — Simple House Price Prediction |
| **Department** | Artificial Intelligence & Data Science (AI & DS) |
| **Institution** | Zeal College of Engineering and Research, Pune |

---

## Contents

- [Project Overview](#project-overview)
- [Objectives](#objectives)
- [Repository Structure](#repository-structure)
- [Dataset Information](#dataset-information)
- [Workflow](#model-workflow)
- [Evaluation Metrics](#evaluation-metrics)
- [Technologies Used](#technologies-used)
- [How to Run](#how-to-run)
- [Conclusion](#conclusion)

---

## Project Overview

This activity demonstrates a basic supervised machine learning workflow using **Simple Linear Regression**. The model predicts median house prices using the average number of rooms in a dwelling.

> **Problem:** Can the average number of rooms (`RM`) help predict the median house value (`MEDV`)?

## Objectives

- Inspect the housing dataset and check data quality.
- Handle missing values and duplicate records.
- Select `RM` as the input feature and `MEDV` as the target.
- Visualize the relationship between room count and house price.
- Split the data into training and testing sets.
- Train a Simple Linear Regression model.
- Generate predictions and evaluate model performance.
- Predict the price for a sample house with 7 rooms.

---

## Repository Structure

```text
├── README.md
├── Activity2.ipynb
├── act2_boston_housing_raw.csv
└── act2_boston_housing_cleaned.csv
```

---

## Dataset Information

- **Dataset:** Boston Housing
- **Domain:** Urban Real Estate
- **Raw file:** `act2_boston_housing_raw.csv`
- **Cleaned file:** `act2_boston_housing_cleaned.csv`
- **Raw dataset size:** 506 rows × 13 columns
- **Cleaned dataset size:** 504 rows × 13 columns

### Input and Target Variables

| Variable | Column | Description |
|---|---|---|
| Input feature (`X`) | `RM` | Average number of rooms per dwelling |
| Target (`y`) | `MEDV` | Median value of owner-occupied homes, in $1,000s |

Only `RM` is used to train this single-feature model. The other columns remain in the CSV files for reference.

<details>
<summary><strong>View dataset feature descriptions</strong></summary>

| Feature | Description |
|---|---|
| `CRIM` | Per-capita crime rate by town |
| `ZN` | Proportion of residential land zoned for large lots |
| `INDUS` | Proportion of non-retail business acres per town |
| `CHAS` | Charles River dummy variable |
| `NOX` | Nitric oxides concentration |
| `RM` | Average number of rooms per dwelling |
| `AGE` | Proportion of owner-occupied units built before 1940 |
| `DIS` | Weighted distance to employment centres |
| `RAD` | Accessibility index for radial highways |
| `TAX` | Property-tax rate |
| `PTRATIO` | Pupil-teacher ratio by town |
| `LSTAT` | Percentage of lower-status population |
| `MEDV` | Median home value in $1,000s |

</details>

---

## Data Preparation

The raw dataset contains 506 records and 13 columns. The notebook checks for missing values and duplicate rows, removes rows with missing values using `dropna()`, removes duplicates using `drop_duplicates()`, and resets the index.

- **Rows before cleaning:** 506
- **Rows after cleaning:** 504
- **Columns:** 13

The cleaned dataset is saved as `act2_boston_housing_cleaned.csv`.

---

## Model Workflow

<details open>
<summary><strong>Step 1 — Select the input feature and target</strong></summary>

- `X = RM` — average number of rooms.
- `y = MEDV` — median house price in thousands of dollars.

</details>

<details>
<summary><strong>Step 2 — Visualize the relationship</strong></summary>

A scatter plot displays the relationship between the average number of rooms and median house price.

</details>

<details>
<summary><strong>Step 3 — Split the dataset</strong></summary>

The dataset is divided into:
- **80% training data**
- **20% testing data**

The split uses `random_state=42` for reproducibility.

</details>

<details>
<summary><strong>Step 4 — Train the Linear Regression model</strong></summary>

The model is trained using Scikit-learn's `LinearRegression`.

The regression model estimates the intercept and slope from the training data.

</details>

<details>
<summary><strong>Step 5 — Generate predictions</strong></summary>

The trained model predicts house prices for the test dataset. Actual and predicted values are displayed for comparison.

</details>

<details>
<summary><strong>Step 6 — Evaluate the model</strong></summary>

The model is evaluated using MAE, MSE, RMSE, and R².

</details>

<details>
<summary><strong>Step 7 — Predict a new example</strong></summary>

A sample prediction is made for a house with `RM = 7.0` rooms.

</details>

---

## Evaluation Metrics

| Metric | Meaning |
|---|---|
| **MAE** | Average absolute difference between actual and predicted values |
| **MSE** | Average squared prediction error |
| **RMSE** | Square root of MSE, expressed in the target's unit |
| **R² Score** | Proportion of target variance explained by the model |

The metric values are calculated when the notebook is executed and may depend on the dataset and train-test split.

---

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

---

## How to Run

### 1. Clone the Repository

```bash
git clone https://github.com/Aditya-1607/REPOSITORY-NAME.git
cd REPOSITORY-NAME
```

Replace `REPOSITORY-NAME` with the actual GitHub repository name.

### 2. Install Required Libraries

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

### 3. Launch the Notebook

```bash
jupyter notebook Activity2.ipynb
```

Keep both CSV files in the same folder as the notebook and run the cells from top to bottom.

---

## Activity Completion Checklist

- [x] Dataset loaded
- [x] Dataset inspected
- [x] Missing values checked and handled
- [x] Duplicate records checked and removed
- [x] Input feature and target selected
- [x] Scatter plot created
- [x] Train-test split performed
- [x] Linear Regression model trained
- [x] Predictions generated
- [x] Evaluation metrics calculated
- [x] Actual vs Predicted plot created
- [x] New house price predicted

---

## Conclusion

A Simple Linear Regression model is used to estimate median house prices from the average number of rooms. Model performance is measured using MAE, MSE, RMSE, and R². Since house prices depend on several factors, using only room count limits the model's predictive ability. A model using multiple features may provide better predictions.
