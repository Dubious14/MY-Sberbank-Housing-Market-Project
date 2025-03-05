# MY-Sberbank-Housing-Market-Project
Machine learning project - House Price Prediction
Welcome to the House Price Prediction repository! This project focuses on predicting housing prices in the Sberbank Russian Housing Market dataset. By applying rigorous data preprocessing, tailored feature engineering, and a two-model approach (separating Investment and Owner-Occupied properties), we achieve a strong predictive performance, culminating in an RMSLE of approximately 0.333 on the private leaderboard.

Overview:
1. Data Preprocessing & Feature Engineering
  Missing Values: Imputed based on location (e.g., sub_area) and property-specific attributes (e.g., material).
  Outlier Handling: Used residual analysis (with Interquartile Range) to remove extreme cases that skew the model.
  Log Transformation: Converted target price_doc to log_price_doc to address right-skewed distribution.
  Time Features: Extracted year, month, and seasonal information to capture temporal price trends.
  Segmentation: Split data into Investment vs. Owner-Occupied categories after discovering distinct distributions.
2. Model Development
   XGBoost: Chosen for its robust performance on structured data and built-in overfitting controls.
  Two-Model Strategy: Separate models for Investment and Owner-Occupied properties for better specialization.
  Time-Based Cross-Validation: Ensured realistic performance estimates by respecting the chronological order of data.
3. Hyperparameter Tuning
   Optuna: Leveraged Bayesian optimization to systematically explore parameter configurations.
   Early Stopping & Regularization: Prevented overfitting by monitoring validation metrics and tuning parameters like max_depth, learning_rate, subsample, and colsample_bytree.
4. Results
   Final RMSLE: ~0.333 on the private leaderboard, significantly improved from the baseline (~0.355).
