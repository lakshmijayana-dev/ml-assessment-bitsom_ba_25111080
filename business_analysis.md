(a) ML Problem
Target variable:
Number of items sold (sales volume)
Input features:
Store location (urban/rural)
Footfall
Promotion type
Customer demographics
Competition density
Month/season
Type of ML problem:
 Regression problem (because we predict a number)
Justification:
We are predicting how many items will be sold → numerical output → regression.

(b) Why items sold > revenue?
Revenue can change due to price differences
Items sold shows actual demand
Promotions affect quantity more than price

Principle:
Choose a target variable that directly represents the business goal.

(c) Better modelling strategy
Instead of one global model:

 Use store-specific models OR
 Use one model with store ID as feature

Why?
Different locations behave differently.

B2. Data and EDA Strategy (10 marks)
(a) Data joining + final dataset

Write:

Join tables using:
Store ID
Date
Final dataset grain:
 One row = one store per month
Aggregations:
Total monthly sales
Average footfall
Promotion used
Festival/holiday flag
(b) EDA (very important)

Write at least 4:

Sales vs Promotion type
Check which promotion works best
Sales over time (monthly trend)
Identify seasonality
Footfall vs sales
Check correlation
Store location vs sales
Urban vs rural performance

 Use graphs like bar chart, line chart.

(c) Imbalance problem (80% no promotion)

Answer:

Model may learn mostly “no promotion”
Poor prediction for promotion cases

 Solution:

Balance data (sampling)
Use weighted models
Evaluate separately for promotions

B3. Model Evaluation & Deployment (12 marks)
(a) Train-test split

Write:

Use time-based split
Train: first 2 years
Test: last 1 year

 Random split is wrong because:

It breaks time order
Causes data leakage

 Metrics:

RMSE
MAE
(b) Feature importance explanation

Write:

Check feature importance from model

Example:

December → festival season → loyalty points work
March → low demand → discount works

 Explain results using:

Seasonality
Customer behavior
(c) Deployment steps

Write:

Save model (pickle/joblib)
Every month:
Prepare new data
Input into model
Generate promotion recommendations

 Monitoring:

Track prediction accuracy
Check drop in performance

 Retrain when:

Accuracy decreases
Data pattern changes