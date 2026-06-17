# 📊 E-Commerce Data Analytics and Machine Learning Project

![Python](https://img.shields.io/badge/Python-3.10-blue)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-green)
![NumPy](https://img.shields.io/badge/NumPy-Numerical%20Computing-orange)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Machine%20Learning-red)
![Status](https://img.shields.io/badge/Project-Completed-success)

---

# 📌 Project Overview

This project demonstrates a complete Data Analytics and Machine Learning workflow on an E-Commerce dataset. The project focuses on extracting business insights through data cleaning, exploratory data analysis (EDA), statistical analysis, visualization, outlier detection, and predictive modeling.

The project helps understand customer purchasing behavior, sales trends, order performance, and business metrics while implementing machine learning algorithms for prediction and classification tasks.

---

# 🎯 Project Objectives

The primary objectives of this project are:

- Understand and explore the dataset.
- Clean and preprocess raw business data.
- Handle missing values effectively.
- Perform statistical analysis.
- Detect anomalies and outliers.
- Visualize customer and sales patterns.
- Build predictive machine learning models.
- Evaluate model performance using appropriate metrics.

---

# 📂 Dataset Description

The dataset contains information related to customer orders and transactions from an e-commerce platform.

### Important Features

| Feature | Description |
|----------|-------------|
| Date | Order Date |
| Quantity | Number of Products Purchased |
| UnitPrice | Price Per Product |
| TotalPrice | Total Order Value |
| CouponCode | Applied Discount Coupon |
| PaymentMethod | Payment Method Used |
| OrderStatus | Current Order Status |
| ReferralSource | Customer Acquisition Source |
| ItemsInCart | Number of Items Added to Cart |

---

# ⚙️ Project Workflow

## 1️⃣ Data Loading and Understanding

The dataset was imported using Pandas.

Initial analysis included:

- Viewing dataset dimensions
- Checking column names
- Examining data types
- Generating descriptive statistics
- Identifying missing values

Example:

```python
df.head()
df.info()
df.describe()
```

---

## 2️⃣ Data Cleaning

Data cleaning is one of the most important steps in the analytics process.

### Missing Value Analysis

Missing values were identified using:

```python
df.isnull().sum()
```

### CouponCode Missing Value Handling

Different techniques were applied:

### Method 1: Removing Missing Records

```python
df.dropna()
```

### Method 2: Replacing Missing Values

```python
df['CouponCode'].fillna('None')
```

### Method 3: Forward Fill

```python
df['CouponCode'].fillna(method='ffill')
```

---

## 3️⃣ Data Standardization

Coupon codes were standardized using:

```python
df['CouponCode'].str.strip().str.title()
```

Benefits:

- Removes extra spaces
- Improves consistency
- Enhances data quality

---

# 📈 Statistical Analysis

Statistical measures were calculated for important numerical variables.

### Quantity Analysis

Computed:

- Mean
- Median
- Mode
- Standard Deviation

### UnitPrice Analysis

Computed:

- Mean
- Median
- Mode
- Standard Deviation

### TotalPrice Analysis

Computed:

- Mean
- Median
- Mode
- Standard Deviation

Purpose:

- Understand central tendency
- Measure variability
- Identify business trends

---

# 🔍 Correlation Analysis

Correlation analysis was performed to identify relationships among numerical variables.

```python
df.corr()
```

Benefits:

- Identifies strongly related variables
- Helps in feature selection
- Supports machine learning modeling

---

# 📉 Rolling Average Analysis

Time-series smoothing was performed using:

### 7-Day Rolling Average

```python
rolling(window=7)
```

### 14-Day Rolling Average

```python
rolling(window=14)
```

Purpose:

- Trend analysis
- Sales forecasting support
- Noise reduction

---

# 🚨 Outlier Detection

Outlier detection helps identify unusual business transactions.

---

## IQR Method

Applied to:

- Quantity
- UnitPrice
- TotalPrice

Formula:

```text
IQR = Q3 - Q1
```

Outlier Boundaries:

```text
Lower Bound = Q1 - 1.5 × IQR

Upper Bound = Q3 + 1.5 × IQR
```

---

## Z-Score Method

Applied to:

- TotalPrice
- ItemsInCart

Formula:

```text
Z = (X - Mean) / Standard Deviation
```

Threshold:

```text
|Z| > 3
```

Transactions exceeding this threshold were flagged as outliers.

---

# 📊 Data Visualization

Several visualizations were created to better understand business patterns.

---

## Histogram

Used for:

- UnitPrice Distribution
- ItemsInCart Distribution
- TotalPrice Distribution

Purpose:

- Understand data spread
- Identify skewness
- Detect unusual values

---

## Bar Chart

Visualized:

- Payment Method Distribution

Purpose:

- Identify preferred payment methods

---

## Pie Charts

Created for:

### Order Status Distribution

Shows:

- Delivered Orders
- Pending Orders
- Cancelled Orders

### Referral Source Distribution

Shows customer acquisition channels.

---

## Scatter Plot

Visualized:

```text
Quantity vs TotalPrice
```

Purpose:

- Identify purchasing behavior
- Detect trends and anomalies

---

## Violin Plot

Visualized:

```text
OrderStatus vs TotalPrice
```

Purpose:

- Understand price distribution across order statuses

---

## Box Plot

Visualized:

```text
PaymentMethod vs TotalPrice
```

Purpose:

- Compare transaction values across payment methods

---

## Heatmap

Generated using:

```python
sns.heatmap()
```

Purpose:

- Visualize correlations
- Detect strong relationships

---

# 🤖 Machine Learning Models

The project includes both Regression and Classification tasks.

---

# Model 1: Linear Regression

### Objective

Predict:

```text
TotalPrice
```

### Features Used

- Quantity
- UnitPrice
- ItemsInCart

### Algorithm

```python
LinearRegression()
```

### Evaluation Metrics

#### R² Score

Measures model accuracy.

#### Mean Absolute Error (MAE)

Measures average prediction error.

---

# Model 2: Logistic Regression

### Objective

Predict order success.

Target Variable:

```text
Is_successful
```

Defined as:

```text
Delivered = 1
Others = 0
```

### Features Used

- Quantity
- UnitPrice
- TotalPrice
- ItemsInCart

### Algorithm

```python
LogisticRegression()
```

### Evaluation Metrics

- Accuracy
- Precision
- Recall
- F1 Score

---

# 📊 Model Evaluation

The machine learning models were evaluated using standard metrics.

### Regression Metrics

- R² Score
- Mean Absolute Error (MAE)

### Classification Metrics

- Accuracy
- Precision
- Recall
- F1 Score

These metrics help determine how effectively the models predict outcomes.

---

# 📌 Key Business Insights

The project provides insights such as:

✔ Customer purchasing behavior

✔ Impact of coupon codes

✔ Popular payment methods

✔ Revenue distribution

✔ Sales trends over time

✔ Outlier transactions

✔ Customer acquisition channels

✔ Order success patterns

---

# 🛠️ Technologies Used

### Programming Language

- Python

### Libraries

- Pandas
- NumPy
- Matplotlib
- Seaborn
- SciPy
- Scikit-Learn

---

# 📦 Installation

Install required libraries:

```bash
pip install pandas numpy matplotlib seaborn scipy scikit-learn openpyxl
```

---

# 📂 Project Structure

```text
Ecommerce-Data-Analytics/
│
├── DecodeLabs_DS_Intern_1.ipynb
├── Dataset for Data Analytics.xlsx
├── README.md
├── requirements.txt
└── Documentation.md
```

---

# ▶️ Running the Project

Launch Jupyter Notebook:

```bash
jupyter notebook
```

Open:

```text
DecodeLabs_DS_Intern_1.ipynb
```

Run all cells sequentially.

---

# 🚀 Future Improvements

Potential enhancements include:

- Advanced Feature Engineering
- Random Forest Regression
- XGBoost Models
- Customer Segmentation
- Sales Forecasting
- Interactive Power BI Dashboard
- Streamlit Web Application
- Real-Time Analytics Dashboard

---

# 📚 Learning Outcomes

This project demonstrates practical implementation of:

- Data Cleaning
- Exploratory Data Analysis (EDA)
- Statistical Analysis
- Correlation Analysis
- Rolling Averages
- Outlier Detection
- Data Visualization
- Linear Regression
- Logistic Regression
- Machine Learning Evaluation

---

# 🏆 Project Achievements

✅ Complete Data Analytics Workflow

✅ Data Cleaning and Preprocessing

✅ Statistical Analysis

✅ Correlation Analysis

✅ Outlier Detection

✅ Interactive Visualizations

✅ Regression Modeling

✅ Classification Modeling

✅ Business Insight Generation

---

# 👨‍💻 Author

### Kartik Singh Parihar

**Data Science Intern Project**

**E-Commerce Data Analytics and Machine Learning**

---

# ⭐ If you found this project useful, consider giving it a star on GitHub!
