# 🩺 Age Group Classification using Machine Learning

## 📌 Overview

This project presents an end-to-end Machine Learning pipeline to classify individuals into one of two age groups using health-related and lifestyle attributes.

The objective is to predict whether a person belongs to:

* **Adult (0)** – Age below 65 years
* **Senior (1)** – Age 65 years and above

The project covers the complete machine learning workflow, including data preprocessing, exploratory data analysis (EDA), feature engineering, handling class imbalance, model training using XGBoost, and generating predictions for unseen test data.

---

## 📂 Dataset

The dataset consists of two files:

* **train.csv** – Training dataset containing feature values and target labels.
* **test.csv** – Testing dataset containing feature values without target labels.

### Features

| Feature  | Description                              |
| -------- | ---------------------------------------- |
| SEQN     | Unique respondent identifier             |
| RIAGENDR | Gender                                   |
| PAQ605   | Physical activity questionnaire response |
| BMXBMI   | Body Mass Index (BMI)                    |
| LBXGLU   | Fasting Blood Glucose                    |
| DIQ010   | Diabetes questionnaire response          |
| LBXGLT   | Oral Glucose Tolerance Test              |
| LBXIN    | Insulin Level                            |

### Target Variable

| Class  | Label |
| ------ | ----- |
| Adult  | 0     |
| Senior | 1     |

---

# 🔍 Exploratory Data Analysis (EDA)

The following analyses were performed before model development:

* Dataset exploration
* Missing value analysis
* Correlation analysis
* Distribution analysis
* Outlier detection
* Feature importance visualization

---

# ⚙️ Data Preprocessing

The following preprocessing steps were applied:

* Handled missing values

  * Median imputation for numerical features
  * Mode imputation for categorical features
* Replaced missing values in **PAQ605** with category **7**
* Removed unnecessary features
* Checked for duplicate records
* Prepared data for model training

---

# 🛠 Feature Engineering

### BMI Categorization

BMI values were converted into categorical features based on WHO classification:

* Underweight
* Normal
* Overweight
* Obesity Class I
* Obesity Class II
* Obesity Class III

### One-Hot Encoding

Applied One-Hot Encoding to:

* BMI Categories
* PAQ605
* DIQ010

---

# 📊 Feature Scaling

Numerical features were scaled using **RobustScaler**.

Scaled features:

* BMXBMI
* LBXGLU
* LBXGLT
* LBXIN

RobustScaler was selected because it is less sensitive to outliers than standard normalization techniques.

---

# ⚖️ Handling Class Imbalance

The dataset contained a significantly higher number of Adult samples compared to Senior samples.

To improve prediction performance for the minority class:

* Experimented with different **scale_pos_weight** values in XGBoost
* Compared multiple class-weight configurations
* Selected the best-performing configuration based on prediction behavior

---

# 🤖 Machine Learning Model

Model used:

* **XGBoost Classifier**

The model was trained after completing preprocessing, feature engineering, and scaling.

Experiments included:

* Hyperparameter tuning
* Class weight tuning
* Feature importance analysis

---

# 📈 Feature Importance

Feature importance was analyzed to understand which variables contributed the most to prediction.

Some of the most influential features included:

* Physical Activity (PAQ605)
* Body Mass Index (BMI)
* Oral Glucose Tolerance (LBXGLT)
* Insulin Level (LBXIN)
* Blood Glucose (LBXGLU)

---

# 🧰 Technologies Used

* Python
* NumPy
* Pandas
* Matplotlib
* Seaborn
* Scikit-learn
* XGBoost

---

# 📁 Project Structure

```text
Age_Group_Classification/
│
├── train.csv
├── test.csv
├── submission.csv
├── Age_Group_Classification.ipynb
├── README.md
```

---

# 🚀 How to Run

1. Clone the repository

```bash
git clone https://github.com/your-username/Age_Group_Classification.git
```

2. Install dependencies

```bash
pip install -r requirements.txt
```

3. Open the Jupyter Notebook

```bash
jupyter notebook
```

4. Run all cells sequentially to reproduce the results.

---

# 📊 Results

The project successfully demonstrates:

* Data preprocessing
* Missing value handling
* Feature engineering
* Handling class imbalance
* Training an XGBoost classifier
* Generating predictions on unseen test data
* Creating a competition-ready submission file

---

# 🔮 Future Improvements

Possible future enhancements include:

* GridSearchCV for hyperparameter optimization
* Cross-validation
* Threshold optimization
* Comparison with CatBoost and LightGBM
* SHAP-based model interpretability

---

# 👨‍💻 Author

**K. Kasi Viswanath Sharma**

B.Tech Mechanical Engineering
National Institute of Technology Warangal

**Interests:** Machine Learning • Deep Learning • Data Science • Mechanical Engineering
