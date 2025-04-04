# Random Forest Model

## Test 1

*Mean Absolute Error (MAE) = 1.49*

Interpretation: On average, the predicted Airbnb price is off by $1.49 from the actual price.
Comparison to Linear Regression: A lower MAE means better predictions. An MAE close to zero is ideal.

*Mean Squared Error (MSE) = 254.63*

Interpretation: The squared average difference between actual and predicted prices.
Comparison to Linear Regression: Since errors are squared, large mistakes are penalized more. A lower MSE is better.

*R² Score = 0.9977*

Interpretation: This tells us how much of the variation in price is explained by the model.
Comparison to Linear Regression:

R² = 1 means a perfect prediction.

R² = 0 means the model is no better than just predicting the average price every time.

Your model has R² = 0.9977, which means 99.77% of the variation in Airbnb prices is explained by your features.

This is extremely high, suggesting that the model is doing an excellent job at predicting price.

*Key Findings from Your Feature Importance Results:*

Service Fee (99.75%) → The dominant factor influencing price.

Latitude & Longitude (~0.03%) → Location matters, but not as much as expected.

Number of Reviews (0.027%) → Slight impact.

Construction Year (0.024%) → Slight impact.

Neighborhoods (Many close to 0%) → Some neighborhoods have minimal influence.

## How good is RFM Test 1?


