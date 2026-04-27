# 🚴 Bike Sharing Demand Prediction (Regression Analysis)

## 📌 Project Overview
This project focuses on analyzing the Bike Sharing dataset to identify key factors influencing daily rental demand and to build predictive models for forecasting bike usage.

The analysis emphasizes both model performance and feature selection, aiming to understand which variables drive demand.

---

## ❓ Business Questions

- What factors significantly affect daily bike rental demand?
- How do weather and seasonal variables impact usage?
- Which variables are most important in predicting demand?
- Can we build an accurate regression model?

---

## 📊 Dataset

- Source: UCI Bike Sharing Dataset (day.csv)
- Target variable: `cnt` (daily bike rental count)

### Key Features:
- Temperature (`temp`, `atemp`)
- Humidity (`hum`)
- Wind speed (`windspeed`)
- Season, month, weekday
- Weather situation (`weathersit`)
- Working day / holiday indicators

---

## 🧠 Methodology

### 1. Data Preprocessing
- Converted categorical variables into factors
- Checked data structure and summary statistics

### 2. Exploratory Data Analysis (EDA)
- Correlation analysis using heatmap
- Identified relationships between numeric variables

### 3. Train-Test Split
- 70% training / 30% testing split

### 4. Modeling Approaches

#### Linear Regression
- Built baseline regression model
- Interpreted coefficients for business understanding

#### Backward Elimination
- Removed insignificant variables
- Optimized model based on statistical significance

#### Lasso Regression (glmnet)
- Applied regularization for feature selection
- Reduced model complexity

#### Random Forest
- Captured non-linear relationships
- Compared performance with linear models

---

## 📈 Model Evaluation

- RMSE (Root Mean Squared Error)
- Model comparison across:
  - Linear Regression
  - Lasso Regression
  - Random Forest

---

## 💡 Key Insights

- Temperature is one of the strongest drivers of bike demand  
- Weather conditions significantly impact usage (especially poor weather)  
- Working days and seasonal patterns influence demand behavior  
- Some variables become less important after feature selection (Lasso / backward elimination)  

---

## 🛠 Tools & Technologies

- R
- glmnet (Lasso Regression)
- randomForest
- corrplot
- caTools (train-test split)
- car (VIF for multicollinearity)

---

## 📂 Files

- `210422078 cw.Rmd` → Full analysis workflow  
- `day.csv` → Dataset  
- `report.pdf` → Final report  

---

## ✅ Conclusion

This project demonstrates:
- Application of regression models to real-world data  
- Feature selection techniques (Backward Elimination & Lasso)  
- Comparison between linear and non-linear models  
- Ability to interpret model results for business insights  

---

## 🎯 Key Learning

- Importance of feature selection in improving model performance  
- Trade-off between interpretability (Linear Model) and performance (Random Forest)  
- Impact of multicollinearity and how to address it  
