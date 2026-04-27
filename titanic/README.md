# 🚢 Titanic Survival Prediction

## Overview
Predict whether a passenger survived the Titanic sinking based on demographic and travel information.  
This is a binary classification task using the classic Titanic dataset.

**File**: `titanic.Rmd` (or `.ipynb`)

---

## Data
- **Source**: Kaggle – Titanic: Machine Learning from Disaster  
  [https://www.kaggle.com/c/titanic/data](https://www.kaggle.com/c/titanic/data)
- **Files**: `train.csv`, `test.csv`
- **Features**: Passenger class (Pclass), sex, age, siblings/spouses (SibSp), parents/children (Parch), fare, embarkation port, etc.

---

## Exploratory Analysis
- First-class passengers had the highest survival rate; third-class the lowest.
- Women tended to have higher fares, reflecting higher-class cabins, and the “women-first” evacuation principle further increased their survival chances.

---

## Evaluation Metrics
Since the dataset is nearly balanced:
- **F1 Score** – harmonic mean of precision and recall  
- **ROC-AUC** – ability to distinguish between survived and deceased at different thresholds

Precision, Recall, and F1 are defined as:

- **Precision** = TP / (TP + FP)
- **Recall** = TP / (TP + FN)
- **F1 Score** = 2 × (Precision × Recall) / (Precision + Recall)

---

## Models & Results

| Model | F1 Score | ROC-AUC | Accuracy |
|-------|----------|---------|----------|
| K-Nearest Neighbours (KNN) | 0.585 | 0.671 | 0.698 |
| Support Vector Machine (SVM) | 0.204 | 0.827 | 0.183 |
| Neural Network (NN) | **0.770** | **0.881** | **0.814** |

### KNN
- Confusion Matrix: TP=46, TN=130, FP=57, FN=35  
- Moderate performance, not suitable as a predictive model.

### SVM
- Confusion Matrix: TP=75, TN=144, FP=28, FN=21  
- Better than KNN but still low F1 score.

### Neural Network
- Achieved the best F1 score (0.77) and ROC-AUC (0.881)  
- Recommended as the final model for this classification task.

---

## Key Insights
- Social class significantly affected survival – first-class passengers had the highest survival rate.
- Gender also played a major role due to the “women-first” evacuation order.
- Higher fares were associated with upper-class cabins and better survival odds.

---


