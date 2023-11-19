# Bosch Production Line - Performance Prediction
## Overview
The goal of this Kaggle competition is to predict which parts in Bosch's production lines will fail quality control, represented by the 'Response' variable. The dataset is one of the largest in terms of the number of features, and the ground truth is highly imbalanced, making it a challenging problem.

### Dataset Description
The dataset consists of three types of files:

train_numeric.csv: Training set with numeric features (contains the 'Response' variable).
test_numeric.csv: Test set with numeric features (to predict the 'Response' for these Ids).
train_categorical.csv and test_categorical.csv: Training and test sets with categorical features.
train_date.csv and test_date.csv: Training and test sets with date features.
sample_submission.csv: A sample submission file in the correct format. Features are anonymized and named based on the production line, station, and feature number.

### Code Sections
Setup and Directory
The code starts by setting up the directory and importing necessary libraries.

Data Loading and Exploration
The training data is loaded and explored using a subset of the data for initial analysis.

Preprocessing Train Data
Feature Engineering - Date Data
Relevant date columns are identified and extracted to optimize reading time. Stations and features are then extracted from the date file.

Feature Engineering - Numerical Data
Columns with a missing ratio less than 0.5 are determined. PCA is implemented to reduce the dimensionality of numeric features.

Machine Learning Modeling
The data is split into training and validation sets, and a LightGBM classifier is trained. The model is evaluated using the Matthews Correlation Coefficient (MCC).

Model Persistence
The trained model and relevant data are saved for future use or reproducibility.

Preprocess Test Data
The test data is loaded and preprocessed, ensuring consistency with the training data preprocessing steps.

Test Data Prediction and Submission
Predictions are made on the test data, and a submission file is created.
