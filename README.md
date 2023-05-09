### Abstract

Binary classification is a fundamental problem in data science and machine learning. The objective of this project was to predict hotel reservation cancellations using a provided dataset. 

In the Data Science section, exploratory data analysis was conducted to understand the dataset, followed by feature engineering where we created asdditonal predictive features and a preprocessing step involving an imputer for missing values and a one-hot encoder scaler for categorical variables. The XGBoost (XGB) algorithm was then utilized to build three different variants of the model, including a baseline model, a tuned model with grid search, and an imbalanced data weighted model. The tuned model with hyperparameters {'learning_rate': 0.5, 'n_estimators': 300} demonstrated the highest performance. Finally, I discussed some of pros and cons of the models built and the model learning outcomes. 

In the Engineering section, we establish the MLOPs workflow that supports the training and prediction pipeline, utilizing the tuned XGB model obtained from the data science offline experimentation. The MLOPs pipeline is comprised of three stages: preprocessing (Imputer and Encoder) with adjustable feature parameters for training and prediction, training and evaluation with configurable threshold logic and evaluation metrics, and prediction on the entire dataset using the latest promoted model.

Keywords: Binary Classification, XGBoost, Class Imbalance, MLOPs Pipeline.