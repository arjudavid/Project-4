# Script Results Report

## Objective of the Analysis

**Purpose:**  
The goal of this analysis is to evaluate and compare machine learning models for classifying data into distinct categories (`'A'`, `'B'`, `'C'`, etc.) based on input features. By identifying the best-performing model, this analysis provides actionable insights for accurate predictions and decision-making.

**Target Prediction:**  
The target variable represents categorical classes derived from numeric ratings. These ratings are mapped to categories as follows:  
- **Rating >= 4.5:** `'A'`  
- **Rating >= 4.0:** `'B'`  
- **Rating >= 3.5:** `'C'`  
- **Rating >= 3.0:** `'D'`  
- **Rating < 3.0:** `'F'`

This mapping ensures consistency in predictions and allows for meaningful comparisons across models.

---

## Models Evaluated (in Script Order)

| **Model**                        | **Description**                                         | **Accuracy** |
|-----------------------------------|---------------------------------------------------------|--------------|
| **Linear Regression**             | Predictions rounded and mapped to categories.           | 33.26%       |
| **LightGBM**                      | Gradient boosting tuned for depth and learning rate.    | 46.30%       |
| **XGBoost**                       | Boosting-based model offering improved robustness.      | 53.35%       |
| **Random Forest**                 | Ensemble model using 300 estimators for stability.      | 61.61%       |
| **Optimized Random Forest**       | Tuned Random Forest for depth and sample splits.        | 46.11%       |
| **Optimized Feature Set**         | Random Forest using selected important features.        | **65.00%**   |
| **Balanced Random Forest (SMOTE)**| Random Forest trained on balanced data via SMOTE.       | 60.96%       |

---

## Methodology

1. **Data Preparation:**  
   - Features (`X`) and target (`y`) were split into training and testing datasets.
   - The `LabelEncoder` was used to transform categorical labels into numerical format where necessary.

2. **Model Training and Testing:**  
   - Each model was trained using the training set and tested against the testing set.
   - Custom adjustments were applied, such as rounding predictions (Linear Regression) or applying SMOTE to balance data (Balanced Random Forest).

3. **Evaluation:**  
   - Accuracy was the primary metric used to evaluate model performance.  
   - All predictions were mapped back to their original categorical labels for interpretability.

---

## Summary and Recommendations

### Best Performing Model
The **Optimized Feature Set model** achieved the highest accuracy at **65.00%**, making it the most reliable for classification tasks based on the dataset provided.

### Recommendations
1. **Deploy the Optimized Feature Set Model:**  
   This model is suitable for immediate use due to its superior accuracy and efficient use of selected features.

2. **Future Improvements:**  
   - **Feature Engineering:** Add new features or refine existing ones to further enhance predictions.  
   - **Hyperparameter Tuning:** Explore advanced optimization techniques for boosting and ensemble models.  
   - **Data Enhancement:** Consider improving class distributions through advanced balancing methods like adaptive SMOTE.  
   - **Validation:** Regularly validate the model using updated datasets to ensure long-term reliability.

---

