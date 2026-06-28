# Age_group_Prediction_XGBModel
Overview

This project develops an end-to-end Machine Learning pipeline to classify individuals into one of two age groups:

Adult (0): Age below 65 years
Senior (1): Age 65 years and above

The project focuses on data preprocessing, feature engineering, handling missing values, class imbalance, and training an optimized XGBoost classifier to predict the target class from health-related attributes.

Dataset

The dataset consists of two files:

train.csv – Training dataset containing feature values and target labels.
test.csv – Testing dataset containing feature values without target labels.
Features
Feature	Description
SEQN	Unique respondent identifier
RIAGENDR	Gender
PAQ605	Physical activity questionnaire response
BMXBMI	Body Mass Index (BMI)
LBXGLU	Fasting Blood Glucose
DIQ010	Diabetes questionnaire response
LBXGLT	Oral Glucose Tolerance Test
LBXIN	Insulin Level

Target Variable

age_group
Adult → 0
Senior → 1
Project Workflow
1. Exploratory Data Analysis (EDA)
Dataset inspection
Missing value analysis
Correlation analysis
Distribution analysis
Feature importance visualization
2. Data Preprocessing
Handled missing values using:
Median imputation for numerical features
Mode imputation for categorical features
Replaced missing values in PAQ605 with category 7
Removed unnecessary columns
Checked for duplicate records
3. Feature Engineering

Created BMI categorical features based on WHO BMI classification:

Underweight
Normal
Overweight
Obesity Class I
Obesity Class II
Obesity Class III

Applied One-Hot Encoding to:

BMI Categories
PAQ605
DIQ010
4. Feature Scaling

Applied RobustScaler to numerical features:

BMXBMI
LBXGLU
LBXGLT
LBXIN

RobustScaler was selected because it is less sensitive to outliers.

5. Handling Class Imbalance

The training dataset contained significantly more Adult samples than Senior samples.

To improve minority class prediction:

Experimented with XGBoost's scale_pos_weight
Compared multiple class weights
Selected the configuration that produced the most balanced predictions
6. Machine Learning Model

Algorithm used:

XGBoost Classifier

Model optimization included:

Hyperparameter experimentation
Class weight tuning
Feature importance analysis
Libraries Used
Python
NumPy
Pandas
Matplotlib
Seaborn
Scikit-learn
XGBoost
Key Techniques Used
Exploratory Data Analysis (EDA)
Missing Value Imputation
Feature Engineering
One-Hot Encoding
Robust Scaling
Class Imbalance Handling
XGBoost Classification
Feature Importance Analysis
Results
Successfully built an end-to-end machine learning pipeline.
Performed comprehensive preprocessing and feature engineering.
Improved minority class prediction through class weight tuning.
Generated predictions for the unseen test dataset and created a competition-ready submission file.
Future Improvements
Hyperparameter tuning using GridSearchCV or RandomizedSearchCV
Cross-validation for model evaluation
Probability threshold optimization
Comparison with CatBoost, LightGBM, and Random Forest
SHAP analysis for model explainability
Author

K. Kasi Viswanath Sharma

Mechanical Engineering Undergraduate | Machine Learning Enthusiast
NIT Warangal
