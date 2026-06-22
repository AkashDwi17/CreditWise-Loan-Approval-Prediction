# 💳 CreditWise - Intelligent Loan Approval Prediction System

## 🚀 Project Overview

CreditWise is an end-to-end Machine Learning project developed to predict whether a loan application should be approved or rejected based on an applicant's financial profile, credit history, employment details, and demographic information.

The objective of this project was to build a reliable loan approval prediction system while understanding the factors that influence lending decisions. Instead of focusing only on model accuracy, the project emphasizes data preprocessing, exploratory data analysis, feature engineering, model comparison, and business insights.

---

## 🎯 Business Problem

Financial institutions process thousands of loan applications every day. Manual evaluation can be time-consuming and inconsistent.

The goal of this project is to assist loan approval decisions by analyzing applicant information and predicting the likelihood of loan approval.

Such a system can help:

* Reduce manual verification effort
* Improve decision consistency
* Identify high-risk applicants
* Accelerate loan processing
* Support data-driven lending decisions

---

## 📊 Dataset Overview

The dataset contains information about **1000 loan applicants** and includes:

### Financial Features

* Applicant Income
* Coapplicant Income
* Savings
* Existing Loans
* Loan Amount
* Collateral Value
* Debt-to-Income Ratio (DTI)

### Personal Features

* Age
* Gender
* Marital Status
* Dependents
* Education Level

### Employment Features

* Employment Status
* Employer Category

### Loan Information

* Loan Purpose
* Loan Term
* Property Area

### Target Variable

**Loan Approved**

* Yes
* No

---

## 🔍 Project Approach

Instead of directly training a model, a structured Machine Learning workflow was followed:

### 1. Data Understanding

The dataset was analyzed to understand:

* Data types
* Missing values
* Feature distributions
* Statistical summaries

This helped identify data quality issues before model training.

---

### 2. Handling Missing Values

The dataset contained missing values across multiple columns.

#### Numerical Features

Mean Imputation was applied using:

```python
SimpleImputer(strategy="mean")
```

#### Categorical Features

Most Frequent Imputation was applied using:

```python
SimpleImputer(strategy="most_frequent")
```

Result:

✅ No missing values remained in the dataset.

---

### 3. Exploratory Data Analysis (EDA)

EDA was performed to understand relationships between applicant attributes and loan approval.

Key analyses included:

* Loan approval distribution
* Education level distribution
* Income analysis
* Credit score analysis
* Outlier detection
* Correlation analysis

### Key Observations

✔ Higher Credit Scores were strongly associated with loan approval.

✔ Applicants with lower Debt-to-Income Ratios had a greater probability of approval.

✔ Applicant Income positively influenced approval probability.

---

### 4. Feature Selection

The Applicant_ID column was removed because it is a unique identifier and does not contribute to prediction.

---

### 5. Feature Encoding

Machine Learning models require numerical inputs.

#### Label Encoding

Applied to:

* Education_Level
* Loan_Approved

#### One-Hot Encoding

Applied to:

* Employment_Status
* Marital_Status
* Loan_Purpose
* Property_Area
* Gender
* Employer_Category

This ensured that categorical variables could be used effectively without introducing artificial ordering.

---

### 6. Correlation Analysis

A correlation heatmap was generated to identify important predictors.

#### Strongest Positive Correlation

**Credit Score (+0.451)**

Applicants with higher credit scores were more likely to receive loan approval.

#### Strongest Negative Correlation

**DTI Ratio (-0.445)**

Applicants with high debt obligations relative to income were less likely to be approved.

---

### 7. Feature Scaling

Features existed on different numerical scales.

Examples:

* Income → Thousands
* Credit Score → Hundreds
* DTI Ratio → Decimals

StandardScaler was applied to normalize feature values before training.

```python
StandardScaler()
```

---

## 🤖 Model Development

Three Machine Learning algorithms were trained and compared.

### Logistic Regression

Chosen because:

* Simple and interpretable
* Effective for binary classification
* Strong baseline model

### K-Nearest Neighbors (KNN)

Chosen because:

* Distance-based classification approach
* Useful for comparison with linear models

### Gaussian Naive Bayes

Chosen because:

* Fast training
* Computationally efficient
* Performs well on structured datasets

---

## 🚀 Feature Engineering

To improve performance, additional features were created.

### DTI Ratio Squared

```python
DTI_Ratio_sq = DTI_Ratio ** 2
```

Purpose:

Capture non-linear effects of debt burden.

### Credit Score Squared

```python
Credit_Score_sq = Credit_Score ** 2
```

Purpose:

Enhance the impact of strong credit histories.

### Income Log Transformation

```python
Applicant_Income_log = np.log1p(Applicant_Income)
```

Purpose:

Reduce skewness and improve distribution quality.

---

## 📈 Model Performance

### Before Feature Engineering

| Model               | Accuracy |
| ------------------- | -------- |
| Logistic Regression | 86.5%    |
| KNN                 | 76.0%    |
| Naive Bayes         | 86.5%    |

### After Feature Engineering

| Model               | Accuracy |
| ------------------- | -------- |
| Logistic Regression | 88.0%    |
| KNN                 | 78.5%    |
| Naive Bayes         | 86.5%    |

---

## 🏆 Best Model

### Logistic Regression

Final Performance:

| Metric    | Score  |
| --------- | ------ |
| Accuracy  | 88.0%  |
| Precision | 78.46% |
| Recall    | 83.60% |
| F1 Score  | 80.95% |

### Why Logistic Regression?

Although Naive Bayes achieved similar accuracy, Logistic Regression provided:

* Higher Recall
* Better F1 Score
* Better Generalization
* Easier Interpretability

Therefore, Logistic Regression was selected as the final model.

---

## 💡 Key Learnings

Through this project I gained practical experience in:

* Data Cleaning
* Missing Value Handling
* Exploratory Data Analysis
* Feature Engineering
* Feature Encoding
* Feature Scaling
* Model Evaluation
* Model Comparison
* Business-Oriented Machine Learning

---

## 🔮 Future Improvements

Future enhancements may include:

* Random Forest
* XGBoost
* LightGBM
* Hyperparameter Tuning
* Cross Validation
* SHAP Explainability
* Streamlit Dashboard
* Flask API Deployment
* Real-Time Loan Prediction System

---

## 🛠️ Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-Learn
* Jupyter Notebook

---

## ▶️ Installation

```bash
git clone https://github.com/AkashDwi17/CreditWise-Loan-Approval-Prediction.git

cd CreditWise-Loan-Approval-Prediction

pip install -r requirements.txt

jupyter notebook
```

Open:

```bash
credit_wise.ipynb
```

Run all cells.

---

## 👨‍💻 Author

Akash Dwivedi

GitHub: https://github.com/AkashDwi17

LinkedIn: https://www.linkedin.com/in/akash-dwivedi-b53a2324b/

---

⭐ If you found this project useful, consider starring the repository.
