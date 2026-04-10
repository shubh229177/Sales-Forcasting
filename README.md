# Walmart Weekly Sales Forecasting

## Project Overview

This project aims to predict weekly sales for Walmart stores using historical data and machine learning techniques. The objective is to analyze the impact of different factors such as economic indicators, seasonal trends, and store-level variations, and build models that can accurately forecast future sales.

---

## Dataset Description

The dataset contains weekly sales data for 45 Walmart stores along with additional features:

* **Store**: Unique store identifier
* **Date**: Week of sales
* **Weekly_Sales**: Target variable representing total weekly sales
* **Holiday_Flag**: Indicates whether the week includes a holiday (1 or 0)
* **Temperature**: Weekly temperature
* **Fuel_Price**: Fuel price during the week
* **CPI**: Consumer Price Index
* **Unemployment**: Unemployment rate

---

## Data Preprocessing

The following preprocessing steps were performed:

1. Verified dataset integrity:

   * No missing values
   * No duplicate records

2. Converted the `Date` column into datetime format.

3. Extracted additional time-based features:

   * Year
   * Month
   * Day
   * Week number

4. Removed the original `Date` column after feature extraction.

---

## Feature Engineering

* **Input Features (X):**

  * Store, Holiday_Flag, Temperature, Fuel_Price, CPI, Unemployment
  * Year, Month, Day, Week

* **Target Variable (Y):**

  * Weekly_Sales

---

## Train-Test Split

The dataset was split using an 80-20 ratio:

* Training set: 5148 samples
* Testing set: 1287 samples

---

## Models Implemented

### 1. Linear Regression

A baseline model assuming a linear relationship between features and sales.

**Performance:**

* MAE: ~432,598
* RMSE: ~521,596

The model did not perform well due to the non-linear nature of the dataset.

---

### 2. Random Forest Regressor

An ensemble learning method using multiple decision trees to capture non-linear relationships.

**Performance:**

* MAE: ~53,857
* RMSE: ~105,898

This model significantly improved prediction accuracy compared to linear regression.

---

### 3. XGBoost Regressor

A gradient boosting model optimized for performance and handling complex patterns.

**Performance:**

* MAE: ~49,606
* RMSE: ~86,146

This model achieved the best performance among all models.

---

## Model Evaluation

Evaluation metrics used:

* Mean Absolute Error (MAE)
* Root Mean Squared Error (RMSE)

Example predictions:

| Actual Sales | Predicted Sales |
| ------------ | --------------- |
| 1,138,800    | 1,097,649       |
| 1,304,850    | 1,366,540       |
| 1,769,296    | 1,859,389       |

The predicted values are close to actual values, indicating strong model performance.

---

## Visualization

### Feature Importance

Feature importance was analyzed using both Matplotlib and Plotly. This helps in understanding which variables have the most influence on sales prediction.

### Actual vs Predicted

Scatter plots were used to compare actual vs predicted values:

* A close alignment along the diagonal indicates accurate predictions.
* XGBoost shows strong alignment, confirming good model performance.

---

## Key Insights

* Linear Regression is not suitable for this dataset due to its inability to capture non-linear relationships.
* Tree-based models perform significantly better.
* XGBoost provides the most accurate and stable predictions.
* Time-based features (Month, Week) improve model performance.
* Economic indicators such as CPI and Unemployment contribute to prediction quality.

---

## Conclusion

The project demonstrates that ensemble learning methods, especially XGBoost, are effective for sales forecasting tasks involving complex and non-linear data. The final model achieves a low error margin relative to the scale of the data, making it reliable for practical use.

---

## Future Improvements

* Hyperparameter tuning for Random Forest and XGBoost
* Incorporating lag features for better time-series modeling
* Using time-series specific models such as ARIMA or LSTM
* Applying cross-validation instead of a single train-test split
* Experimenting with feature scaling and transformation

---

## How to Run

1. Install required libraries:

   * pandas
   * numpy
   * matplotlib
   * plotly
   * scikit-learn
   * xgboost

2. Execute the workflow:

   * Load dataset
   * Perform preprocessing
   * Train models
   * Evaluate performance
   * Visualize results

---

## Project Structure

* Data loading and preprocessing
* Feature engineering
* Model training (Linear Regression, Random Forest, XGBoost)
* Evaluation and comparison
* Visualization (feature importance and prediction analysis)

---

## Author

This project was developed as part of a machine learning practice task focusing on regression modeling, feature engineering, and model comparison using real-world data.
