# Telco Customer Churn Prediction 🚀

![Python](https://img.shields.io/badge/Python-3.12-blue)
![Library](https://img.shields.io/badge/Library-XGBoost-orange)
![Status](https://img.shields.io/badge/Status-Completed-green)

## 📌 Project Overview
This project aims to predict customer churn for a telecommunications company using Machine Learning. The goal is to identify customers who are likely to leave the service so the company can take proactive actions (retention campaigns).

We focused on a **"High Recall" strategy**, prioritizing the identification of as many churners as possible, even at the cost of some false alarms.

## 📂 Dataset
The dataset used in this project is the famous Telco Customer Churn dataset from Kaggle.
- **Source:** [Kaggle - Telco Customer Churn](https://www.kaggle.com/blastchar/telco-customer-churn)
- **Features:** Customer demographics, services (phone, internet, etc.), contract information, and billing details.
- **Target:** `Churn` (Yes/No).

## 🛠️ Tech Stack
- **Language:** Python 3.12
- **Data Manipulation:** Pandas, NumPy
- **Visualization:** Matplotlib, Seaborn
- **Machine Learning:** XGBoost, Scikit-Learn
- **Package Manager:** uv

## ⚙️ Installation & Usage

### Prerequisites
Make sure you have [uv](https://github.com/astral-sh/uv) installed (or use standard pip).

### 1. Clone the Repository
```bash
git clone https://github.com/giraycakr/costumer-churn-prediction.git
cd telco-churn-analysis
```
### 2. Install Dependencies
Using uv (Recommended):
```bash
uv sync
```
Or using standard pip:

```bash
pip install -r requirements.txt
```
### 3. Run the Notebook
Open the Jupyter Notebook to see the analysis and model training steps:
```bash
uv run jupyter notebook
```

## 📊 Methodology
1. Data Cleaning: Handled missing values in TotalCharges and merged redundant categories (e.g., "No internet service" -> "No").
2. Preprocessing: Applied One-Hot Encoding for categorical variables and MinMaxScaler for numerical features.
3. Modeling:
   - Baseline: Logistic Regression.
   - Advanced: Random Forest & XGBoost.
   - **Final Strategy**: XGBoost with scale_pos_weight to handle class imbalance.
4. Evaluation: Focused on Recall to minimize missed churners.

## 🏆 Results

| Metric | Score | Interpretation |
|------|------|----------------|
| Recall (Churn) | 83.0% | We successfully identify 83 out of every 100 churners |
| Accuracy | 71.6% | General accuracy (traded off for higher recall) |
| ROC-AUC | 83.7% | Strong ability to distinguish between churners and non-churners |

## 🔑 Key Insights (Why do they leave?)
Based on the XGBoost Feature Importance analysis:
1. **Contract Type:** Customers with "Month-to-month" contracts are highly likely to churn.
2. **Monthly Charges:** Higher bills correlate directly with higher churn rates.
3. **Tenure:** New customers (first 6 months) are the most vulnerable group.
4. **Fiber Optic:** Users with Fiber Optic internet show higher churn tendencies (likely due to service expectations vs. price).

## 👥 Team Members
- Aleyna Kılıç
- Girayhan Çakıroğlu
