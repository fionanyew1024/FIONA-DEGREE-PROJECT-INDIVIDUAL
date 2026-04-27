# 🚢 Titanic Survival Prediction

## Overview
Predict whether a passenger survived the Titanic sinking based on demographic and travel information.  
This is a classic binary classification problem used to practice data cleaning, feature engineering, and model evaluation.

**File**: `titanic.ipynb` (or `.Rmd`)  

---

## Data
- **Source**: Kaggle – Titanic: Machine Learning from Disaster  
- **Files**:  
  - `train.csv` – labeled training set (891 passengers)  
  - `test.csv` – unlabeled test set (418 passengers)  
  - `gender_submission.csv` – example submission format  
- **Features**: Pclass, Sex, Age, SibSp, Parch, Fare, Embarked, etc.

---

## Methods

### 1. Data Cleaning
- Handle missing values:  
  - `Age` → median / mean imputation (by Pclass or title)  
  - `Embarked` → mode imputation  
  - `Cabin` → dropped or converted to “has_cabin” flag  

### 2. Feature Engineering
- Extract titles (Mr, Mrs, Miss, Master, etc.) from `Name`  
- Create family size = `SibSp + Parch + 1`  
- Create “is alone” flag  
- Bin Age and Fare into categories  

### 3. Exploratory Analysis
- Survival rate by gender, class, age group  
- Visualizations: bar plots, heatmaps, pair plots  

### 4. Modeling
- Algorithms tested:  
  - Logistic Regression  
  - Random Forest  
  - Gradient Boosting (XGBoost / LightGBM)  
- Evaluation metrics: Accuracy, Precision, Recall, F1-score, ROC-AUC  
- Cross-validation (e.g., 5-fold)

### 5. Final Model
- Best model: Random Forest (or XGBoost)  
- Accuracy on validation set: ~82%  
- Feature importance: Sex, Pclass, Age, Fare  

---

## Results
| Model | Accuracy (CV) | Kaggle Score |
|-------|---------------|---------------|
| Logistic Regression | 0.78 | 0.77 |
| Random Forest | 0.82 | 0.79 |
| XGBoost | 0.83 | 0.80 |

**Key insights**:  
- Women and children had significantly higher survival rates.  
- First-class passengers were more likely to survive.  

---

## How to Run

### Requirements (Python)
```bash
pip install pandas numpy matplotlib seaborn scikit-learn xgboost
