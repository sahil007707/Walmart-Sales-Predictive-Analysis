# 🛒 Walmart Sales Predictive Analysis

A comprehensive machine learning and data analysis project on historical Walmart store data. This project includes data cleaning, exploratory data analysis (EDA), feature engineering, regression modeling, and classification modeling to predict weekly sales and identify high-sales scenarios.

---

## 📂 Dataset Overview

The dataset contains historical sales data for 45 Walmart stores located in different regions, including features such as:

- `Store_Number`: Unique store identifier
- `Date`: Weekly sales date
- `Weekly_Sales`: Target variable representing weekly revenue
- `Holiday_Flag`: Indicates whether the week includes a holiday
- `Temperature`, `Fuel_Price`, `CPI`, `Unemployment`: Economic indicators
- `Month`, `Day`, `Weekday`, `Week`: Date-based features extracted from `Date`

---

## 🧼 Data Cleaning

- Removed commas and converted `Weekly_Sales` and `CPI` to `float`
- Converted `Date` to `datetime` format
- Filled missing values using forward fill
- Removed duplicate rows
- Normalized column names by stripping whitespace

---

## 🔍 Exploratory Data Analysis (EDA)

- Distribution plots of numerical features using `seaborn` and `matplotlib`
- Time-series analysis of total weekly sales
- Boxplots of sales by `Store_Number` and `Holiday_Flag`
- Correlation heatmap to understand feature relationships
- Interactive plots using `plotly` for departmental analysis

---

## 🛠 Feature Engineering

- Extracted date components: `Month`, `Day`, `Weekday`, `Week`, `Year`
- Encoded `Holiday_Flag` as binary
- Created a new binary classification target: `High_Sales` (1 if above median)

---

## 🤖 Machine Learning Models

### 🔢 Regression Models (Target: `Weekly_Sales`)
- **Linear Regression**
- **Random Forest Regressor**

📊 **Metrics**:
- Root Mean Squared Error (RMSE)
- R² Score

### 🧮 Classification Model (Target: `High_Sales`)
- **Random Forest Classifier**

📊 **Metrics**:
- Accuracy Score
- Classification Report (Precision, Recall, F1-score)
- Confusion Matrix

---

## 🔮 Predictions

You can use new data to predict:
- **Weekly Sales Amount** using the regression model
- **Sales Class (High/Low)** using the classifier model

```python
# Sample input for prediction
new_data = pd.DataFrame([{
    'Store_Number': 5,
    'Holiday_Flag': 0,
    'Temperature': 70.2,
    'Fuel_Price': 3.45,
    'CPI': 211.45,
    'Unemployment': 7.8,
    'Month': 6,
    'Day': 15,
    'Weekday': 2,
    'Week': 24
}])

# Predict sales
predicted_sales = rf.predict(scaler.transform(new_data))
predicted_class = clf.predict(new_data)
