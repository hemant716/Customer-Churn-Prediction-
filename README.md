# 📉 Customer Churn Prediction App

An end-to-end Machine Learning project that predicts customer churn probability using customer demographics, account details, service subscriptions, and billing information.

The project focuses not only on predictive modeling, but also on the complete ML lifecycle including:

- Exploratory Data Analysis (EDA)
- Data preprocessing
- Feature engineering
- Model training & evaluation
- Class imbalance handling
- Threshold optimization
- Model explainability with SHAP
- Deployment using Streamlit




# 📊 Dataset

This project uses the **Telco Customer Churn Dataset** from Kaggle.

### Dataset Link
https://www.kaggle.com/datasets/blastchar/telco-customer-churn

### Dataset Information

- 7043 customer records
- 21 features
- Binary classification problem

### Feature Categories

#### Customer Demographics
- Gender
- Senior Citizen
- Partner
- Dependents

#### Account Information
- Tenure
- Contract Type
- Payment Method
- Paperless Billing

#### Services
- Internet Service
- Online Security
- Tech Support
- Streaming TV
- Device Protection
- Phone Service

#### Billing Information
- Monthly Charges
- Total Charges

### Target Variable
- Churn

---

# 🛠 Tech Stack

- Python
- Pandas
- NumPy
- Scikit-learn
- XGBoost
- SHAP
- Matplotlib
- Streamlit
- Joblib

---

# 📂 Project Structure

```text
customer-churn-prediction/
│
├── data/
│   └── WA_Fn-UseC_-Telco-Customer-Churn.csv
│
├── models/
│   ├── logistic_regression.pkl
│   ├── random_forest.pkl
│   └── xgboost_model.pkl
│
├── notebooks/
│   ├── eda.ipynb
│   └── model_experiments.ipynb
│
├── src/
│   ├── data_preprocessing.py
│   ├── feature_engineering.py
│   ├── train.py
│   ├── evaluate.py
│   ├── predict.py
│   └── explainability.py
│
├── app.py
├── requirements.txt
└── README.md
```

---

# ⚙️ Machine Learning Pipeline

## 🔹 Numerical Features

- Tenure
- MonthlyCharges
- TotalCharges

### Processing
- Missing value imputation
- Standard scaling

---

## 🔹 Categorical Features

- Gender
- Contract Type
- Payment Method
- Internet Service
- Service-related features

### Processing
- Missing value imputation
- One-hot encoding

---

## 🔹 Preprocessing Pipeline

A Scikit-learn `ColumnTransformer` was used to create a clean and reproducible preprocessing workflow.

The pipeline ensures:

- Consistent preprocessing
- Prevention of data leakage
- Easier deployment
- Reproducibility

---

# 🤖 Models Used

## 🔹 Logistic Regression

- Baseline interpretable model
- High recall performance
- Effective for identifying churn customers

---

## 🔹 Random Forest

- Ensemble learning model
- Captures non-linear relationships
- Balanced precision and recall

---

## 🔹 XGBoost

- Gradient boosting model
- Handles class imbalance efficiently
- Strong predictive performance with regularization

---

# ⚖️ Class Imbalance Handling

Since churn prediction is an imbalanced classification problem, imbalance handling techniques were applied:

- Stratified train-test split
- `scale_pos_weight` for XGBoost
- Threshold optimization
- Evaluation using Recall and F1-score

---

# 📈 Model Performance

| Model | ROC-AUC | F1 Score | Precision | Recall |
|------|------|------|------|------|
| Logistic Regression | 0.86 | 0.64 | 0.52 | 0.84 |
| Random Forest | 0.85 | 0.65 | 0.56 | 0.78 |
| XGBoost | 0.85 | 0.63 | 0.55 | 0.75 |

---

# 📌 Why Accuracy Was Not Used

Customer churn prediction is an imbalanced classification problem.

Using Accuracy alone can be misleading because a model may predict the majority class well while failing to identify churn customers.

Therefore, the project prioritizes:

- Recall
- F1-score
- ROC-AUC

to better evaluate business impact.

---

# ⚖️ Threshold Optimization

Instead of using the default probability threshold of `0.5`, multiple thresholds were evaluated to optimize:

- Precision
- Recall
- F1-score

This allows businesses to customize churn sensitivity based on retention strategy.

---

# 🔍 Model Explainability with SHAP

SHAP (SHapley Additive Explanations) was used to interpret predictions and improve transparency.

## SHAP Capabilities

- Global feature importance
- Individual prediction explanations
- Feature contribution visualization

---

# 📊 Key SHAP Insights

- Low tenure increases churn risk
- Month-to-month contracts strongly increase churn probability
- Higher monthly charges correlate with churn
- Lack of tech support and online security increases churn likelihood

---

# 📊 Business Insights

## 📌 Contract Type
Customers with month-to-month contracts show the highest churn probability.

## 📌 Customer Tenure
New customers are significantly more likely to churn.

## 📌 Monthly Charges
Higher monthly charges correlate with increased churn risk.

## 📌 Internet Service
Customers using fiber optic internet tend to churn more frequently.

## 📌 Value-added Services
Customers without:
- Online Security
- Tech Support
- Device Protection

are more likely to churn.

---

# 💡 Business Recommendations

Based on model insights:

- Encourage long-term contracts through incentives
- Offer bundled service packages
- Target high-risk customers with retention campaigns
- Focus retention efforts on low-tenure customers
- Promote value-added services like tech support

---

# 🌐 Streamlit Deployment

The application is deployed using Streamlit and allows users to:

- Input customer information
- Predict churn probability in real time
- View prediction confidence
- Understand predictions using SHAP explainability

---



# ▶️ Installation

## Clone Repository

```bash
git clone https://github.com/hemant716/Customer-Churn-Prediction-.git
```

---

## Navigate to Project Folder

```bash
cd customer-churn-prediction
```

---

## Create Virtual Environment

### Windows

```bash
python -m venv myenv
myenv\Scripts\activate
```

### Mac/Linux

```bash
python3 -m venv myenv
source myenv/bin/activate
```

---

## Install Dependencies

```bash
pip install -r requirements.txt
```

---

# ▶️ Run Streamlit App

```bash
streamlit run app.py
```




# 📌 Conclusion

This project demonstrates how to build a production-ready Machine Learning system that combines:

- Predictive analytics
- Business understanding
- Explainability
- Real-time deployment

The project highlights the importance of going beyond model accuracy to deliver actionable business insights and interpretable AI solutions.

---

# 👨‍💻 Author

Hemant Vaidya


