
# OPEN_ENDED_LAB-22F-BSAI-106 - House Price Prediction Project

## Project Overview

This project is a **machine learning-based house price prediction system** using a structured dataset of residential properties. The goal is to build predictive models that can estimate the sale price of houses based on various features, including numerical, categorical, and derived attributes. This project demonstrates the complete workflow from **data exploration and preprocessing** to **model training, evaluation, and visualization**.

---

## Dataset

* The dataset contains **1460 rows** and **81 columns**, with a mix of **numerical and categorical features**.
* Features include property characteristics like `LotArea`, `GrLivArea`, `Neighborhood`, `OverallQual`, `YearBuilt`, and more.
* Target variable: `SalePrice` (house sale price).
* Some columns, such as `PoolQC`, `MiscFeature`, `Alley`, and `Fence`, contain **high percentages of missing values** and were removed during preprocessing.

---

## Project Structure

```
OPEN_ENDED_LAB-22F-BSAI-106/
│
├── data/
│   ├── train.csv        # Main training dataset
│   ├── test.csv         # Optional testing dataset
│
├── notebooks/
│   ├── house_price_prediction.ipynb  # Jupyter Notebook with complete workflow
│
├── src/
│   ├── preprocessing.py  # Functions for data cleaning, missing value handling, outlier capping
│   ├── modeling.py       # Functions for model training (Linear Regression, Random Forest)
│
├── outputs/
│   ├── feature_importances.png  # Visualization of top features
│   ├── correlation_heatmap.png  # Correlation heatmap of numerical features
│   ├── actual_vs_predicted.png  # Scatter plot of actual vs predicted prices
│
├── requirements.txt     # Required Python libraries
├── README.md            # Project documentation
```

---

## Workflow

### 1. Data Exploration

* Displayed dataset shape, data types, and summary statistics.
* Checked for **missing values** and **duplicates**.
* Explored distributions of numerical features using histograms and box plots.
* Analyzed categorical features and their frequency counts.
* Generated a **correlation heatmap** to examine relationships among numerical features.

### 2. Data Preprocessing

* Dropped columns with **>50% missing values**.
* Imputed missing values:

  * **Numerical features:** median
  * **Categorical features:** mode
* Handled **outliers** in numerical features using the **IQR method**.
* Scaled numerical features and applied **one-hot encoding** to categorical variables using `ColumnTransformer` and `Pipeline`.

### 3. Model Training

* Split dataset into **training and testing sets** (80/20).
* Built and trained models:

  * **Linear Regression** for baseline predictions.
  * **Random Forest Regressor** to capture nonlinear relationships and interactions.
* Used **feature importance** from Random Forest to identify key predictors.

### 4. Model Evaluation

* For regression models, evaluated using:

  * Mean Absolute Error (MAE)
  * Mean Squared Error (MSE)
  * Root Mean Squared Error (RMSE)
  * R² score
* Visualized performance with:

  * Actual vs Predicted scatter plots
  * Feature importance bar charts
  * Correlation heatmaps
* For demonstration, discretized `SalePrice` into bins to create a **confusion matrix**.

---

## Key Findings

* Several features strongly influence house prices, including `GrLivArea`, `OverallQual`, and `Neighborhood`.
* Right-skewed distributions and outliers were present in numerical features like `LotArea` and `GrLivArea`.
* Linear Regression achieved an **R² of 0.88**, explaining 88% of variance in house prices.
* Random Forest performed better in handling nonlinear relationships and provided robust feature importance insights.
* High missing value columns were removed to improve data quality and prevent noise.

---

## Insights and Recommendations

* Consider **log-transforming skewed numerical features** to improve linear model performance.
* Random Forest and ensemble methods (like Gradient Boosting) are more effective for complex, nonlinear relationships in house price prediction.
* Feature engineering, such as combining correlated features or creating derived attributes, could further enhance model accuracy.
* Cross-validation is recommended to ensure **generalization and avoid overfitting**.

---

## Technologies & Libraries

* Python 3.x
* Libraries:

  * pandas, numpy, matplotlib, seaborn
  * scikit-learn (for preprocessing, modeling, evaluation)

---

## How to Run

1. Clone the repository:

```bash
git clone https://github.com/your-username/OPEN_ENDED_LAB-22F-BSAI-106.git
```

2. Install dependencies:

```bash
pip install -r requirements.txt
```

3. Open the notebook `house_price_prediction.ipynb` in Jupyter or Google Colab and run all cells.

---

## Conclusion

This project demonstrates a **full machine learning pipeline** for house price prediction, including data cleaning, preprocessing, modeling, evaluation, and visualization. While Linear Regression provides interpretability, Random Forest delivers higher accuracy by handling nonlinearities and complex interactions between features. The project also highlights the importance of handling missing data, outliers, and feature engineering for better predictive performance.

