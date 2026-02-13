# 1. Regression Model
## Features
 1. product_id
 2. cabtype
 3. source
 4. destination
 5. surge_multiplier
 6. name
 7. **hour_of_day** : the time when the ride is called affects the price.
 8. is_weekend
 9. day_of_week
 8. is_rush_hour
## Label
- Price
# 2. Classification Model
## Features
 Similar to the regression model
## Label
- high_cost
### Model Evaluation & Comparison

#### Comparison of Regression and Classification Outcomes
Linear regression predicts continuous ride prices, achieving an R² of 0.5182 (moderate explanatory power) and MSE of 34.59, indicating reasonable but imperfect accuracy on the test set. Logistic regression classifies high- versus low-cost rides (threshold: median price), yielding 77.16% accuracy. The confusion matrix reveals 53,018 true negatives (low-cost correctly identified), 18,831 false positives, 20,262 false negatives, and 79,069 true positives, showing balanced but imperfect discrimination.

| Metric                  | Regression (Price Prediction) | Classification (High/Low Cost) |
|-------------------------|-------------------------------|--------------------------------|
| Primary Metric         | R² = 0.5182                  | Accuracy = 0.7716             |
| Error Metric           | MSE = 34.59                  | Confusion Matrix: [[53,018, 18,831], [20,262, 79,069]] |
| Interpretation         | Captures ~52% of price variance; suitable for estimates | Effective binary separation, though with notable misclassifications |

Regression supports precise forecasting, while classification aids categorical decisions but discards price granularity.

#### Influence of Data Quality on Both Models
The dataset's scale aids robustness, but real-world noise (e.g., unmodeled traffic or outliers in surges) likely contributes to the moderate R² and ~23% classification error. Clean preprocessing mitigated issues, yet imbalances in derived features (e.g., rush hours) may inflate MSE and false positives.

#### Most Influential Feature
Distance remains dominant, with the highest coefficient in both models.

#### Ethical concerns
##### One Potential Unfair Pricing Behavior
- Surge pricing mechanisms
##### One Real-World Risk of Deploying This Model
- Not accurate enough
##### One Limitation of the Dataset
- Lacks real-time weather data