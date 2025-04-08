# 🚀 **Project 4: Prediction of Property Ratings in New York Using Airbnb Data and Machine Learning**

## 📌 **Project Overview**

The aim of this project is to **predict Airbnb review scores** using various machine learning models. The goal is to identify key factors that influence an Airbnb's user ratings, providing insights for both hosts and potential guests.

[TABLEAU WORKBOOK](https://public.tableau.com/app/profile/david.ruvalcaba4154/viz/Project_4_visualization_17439881426360/Historia1?publish=yes)

---

## 🔍 **Data Preprocessing**

The dataset includes information on thousands of Airbnb listings, with features such as:

 **Target Variable:**

  - review category: The overall review score given by guests.

 **Feature Variables:**

 - prices: The nightly price of the listing and the service fee.

 - Location: based features (neighbourhood, latitude, longitude)

 - Property characteristics: (room type, instant booking, construction year, cancellation policy)

 - Availability: The availability of the place (min. nights, availability throughout the year)

 - Host details (host id, host name, airbnb id, airbnb rules)

 **Data Cleanup:**

We used pandas to clean the CSV making the following changes:

 - Droped columns related to host details since they aren't required for the model.

 - Removed rows with null or empty values and filled NaN values with 0.

 - Standarized values in 'neighbourhood', 'neighbourhood group'.

 - Created a reusable function to remove symbols and convert those values into integers.

---

## 🏗️ **Model Selection & Training**

Several models were tested to predict Airbnb review scores. The primary focus was to find a model with the ability to handle non-linearity and interactions between variables.

 **Model Used:**

 We used several models like Linear Regression, LightGBM, and XGBoost; but their accuracy performance were all below 50%.
 The only model that was capable of performing  close to a 75% mark was Random Forest Regression with an initial accuracy of
 55% and a final accuracy of 65% after optimization.

 **Training Details and Optimization:**

 - The numbers in review category were turned into categorical labels.

 - Removed lowest categories and high-price values that could become outlires to avoid making noise into the model.

 - The dataset was split into training (80%) and testing (20%).

 - Hyperparameters were added to optimize the model.

 - Selected most important features and retrained the model to optimize the model even further.

---

## 📈 **Results**

We experimented with a range of machine learning models to predict Airbnb review scores. Our results are summarized below:

* **Linear Regression** performed poorly, with an R² score of **-0.0025**, indicating that the model failed to explain the variance in the data. It had a **33% accuracy** and misclassified most review categories, making it unsuitable for this classification task.

* **LightGBM** showed moderate performance with an accuracy of **46%**. While slightly better than Linear Regression, it still struggled to differentiate between categories with high precision and recall.

* **XGBoost** improved upon LightGBM, reaching an accuracy of **54%**. It provided balanced results across all categories but lacked the robustness and consistency required for practical applications.

* **Random Forest** emerged as the most reliable model. The initial model achieved **62% accuracy**, and after feature selection and hyperparameter tuning, we improved performance to **65%**, making it the best-performing model in this project.

Interestingly, an **early optimized version of Random Forest** showed reduced accuracy (**45%**) due to suboptimal feature selection. However, a re-optimized feature set corrected this and boosted accuracy to **65%**, showing the importance of proper feature engineering.

A version of the model trained on **balanced data** (equal distribution of review categories) reached **61%** accuracy, showing stable but slightly reduced performance, possibly due to downsampling.

---

## 🚀 **Findings and Recommendations**

**Key Findings**

* **Model Selection Matters:** Traditional models like Linear Regression are not well-suited for this classification problem due to the non-linear relationships and categorical target variable. Tree-based models, especially Random Forest, are better equipped to handle complex interactions in the data.

* **Feature Importance:** The most influential features for predicting review scores were price, location-based variables, room type, cancellation policy, and availability metrics. Removing low-impact features and focusing on highly informative ones significantly boosted model performance.

* **Feature Engineering Drives Accuracy:** Initially, the model used 17 features. Expanding to 23 features yielded minimal improvement, while exceeding that caused performance to drop. Ultimately, narrowing the model to 19 high-impact features with strong predictive power led to the highest accuracy.

* **Optimization Trade-Offs:** The most challenging aspect of this project was finding the right balance between model complexity and interpretability. Over-tuning or adding irrelevant features caused accuracy to fluctuate, underscoring the importance of careful, data-driven optimization.


## 📝 **Project Files**

**Key files in this project:**

* Clean Optimized Model.ipynb – A clean notebook containing all models used and all methods for optimization.

* data_clean.ipynb – A notebook using pandas to clean the initial CSV.

* Data folder - A folder containg all of the CSV's used in the process.

* Tableau Story - A Tableau story containing visualizations and explanation of the model.


