# British Airways Predictive Modeling Project
![pngegg](https://github.com/user-attachments/assets/43493925-a983-424f-a6e6-c0e07586d2c9)

# Intoduction:

This project focuses on building a predictive model for British Airways, provided via the Forage job simulation platform. The aim is to analyze historical customer booking data and develop a machine learning model that predicts the likelihood of a customer completing a booking.

# Goals

* Perform exploratory data analysis (EDA) to extract business insights.

* Handle class imbalance in the target variable.

* Build and compare multiple classification models.

* Evaluate models with appropriate metrics.

* Identify and analyze important features.

# Feature Engineering: Frequency Encoding

To handle high-cardinality categorical features effectively, I applied frequency encoding. This technique replaces each category with the frequency or proportion of its occurrence in the dataset.

Applied columns:

* route (799 unique values)

* booking_origin (104 unique values)

This encoding helps preserve information while avoiding the dimensionality issues of one-hot encoding.

# Train-Test Split Strategy: StratifiedShuffleSplit

To ensure consistent class distribution during model training and evaluation, I used StratifiedShuffleSplit with n_splits=1 and test_size=0.2. This maintains the same proportion of the target variable (booking_complete) in both train and test sets.

Why StratifiedShuffleSplit?

Maintains class balance (important for imbalanced data)

# Handling Class Imbalance

I applied Random Under Sampling only on the training data to ensure equal representation of both classes (booked vs not booked). The test set was kept imbalanced to reflect real-world conditions, making the evaluation more realistic

# Models Evaluated

I evaluated the following classification models:

* Logistic Regression

* Decision Tree Classifier

* Random Forest Classifier

* XGBoost Classifier

# Model Evaluation Criteria

Given the business goal of identifying customers who are likely to complete their bookings, I prioritized Recall.

"Better to flag more potential bookers even if a few false positives are included."

I also considered:

* F1 Score

* Average Precision (AP) Score

Best Model: XGBoost Classifier

* Highest Recall

* AP Score: 0.35 (indicates moderate prediction performance)

# Key Insights from Feature Importance

The most influential features:

* booking_origin

* sales_channel

* purchase_lead

These features provide valuable business insights and can guide:

* Marketing strategies

* Personalized communication

* Product offering optimizations

# Summary

Balanced training data using under sampling

Preserved imbalanced test set for realistic evaluation

Explored multiple models; XGBoost performed best

Focused on Recall due to business needs

Booking origin and sales channel are highly predictive features
