# 📉 Customer Churn Analytics & Retention Insights

[![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?logo=python&logoColor=white)](notebooks/)
[![Pandas](https://img.shields.io/badge/Data%20Analysis-Pandas%20%7C%20Seaborn-150458?logo=pandas&logoColor=white)](notebooks/)
[![Jupyter](https://img.shields.io/badge/Notebook-Jupyter-F37626?logo=jupyter&logoColor=white)](notebooks/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Author](https://img.shields.io/badge/Author-Akash-blueviolet?logo=github)](https://github.com/akash3005-arc)

An exploratory analytics project examining how **customer churn changes over time**, which customer segments are most at risk, and which factors are most strongly associated with attrition across **<N> customer records**.

---

## 📌 Executive Summary

Customer churn directly erodes recurring revenue, and acquiring a new customer typically costs more than retaining an existing one. Understanding *when* customers leave and *who* is likely to leave helps businesses design targeted retention strategies.

This project delivers an end-to-end analytics workflow:
1. **Data Cleaning & Preparation** - handling missing values, fixing data types, and removing duplicates.
2. **Exploratory Data Analysis (EDA)** - univariate, bivariate, and multivariate analysis of churn drivers.
3. **Churn-over-Time Analysis** - tracking how churn rate evolves across tenure / time periods.
4. **Segment Comparison** - comparing churned vs. retained customers across demographics, services, and billing.
5. **Reporting** - visuals and summaries saved for stakeholders.

---

## 🏗️ Analysis Pipeline

```
+-----------------------------------------------------------------------+
|                     Raw Customer Dataset (datasets/)                  |
|              (<N> customers, <M> features, Churn label)               |
+-----------------------------------------------------------------------+
                                  |
                                  v
+-----------------------------------------------------------------------+
|                    Data Cleaning & Preprocessing                      |
|   - Missing value handling   - Type conversion   - Deduplication      |
+-----------------------------------------------------------------------+
                                  |
                                  v
+-----------------------------------------------------------------------+
|                     Exploratory Data Analysis                         |
|   - Churn distribution       - Churn over time / tenure               |
|   - Feature vs. churn plots  - Correlation & segment analysis         |
+-----------------------------------------------------------------------+
                                  |
                                  v
+-----------------------------------------------------------------------+
|                    Reports & Insights (reports/)                      |
|   - Charts, summaries, retention recommendations                      |
+-----------------------------------------------------------------------+
```

---

## 📂 Repository Structure

```
.
├── datasets/       # Raw and/or cleaned customer data
├── notebooks/      # Jupyter notebooks for cleaning, EDA and analysis
├── reports/        # Generated charts, summaries and findings
└── README.md       # Project documentation
```

---

## 📖 Data Dictionary

The dataset contains **7,043 rows** across **21 attributes**:

| Column Name | Data Type | Description | Analytical Relevance |
|:---|:---|:---|:---|
| `customerID` | `object` | Unique customer identifier | Primary key |
| `gender` | `object` | Customer gender | Demographic segmentation |
| `SeniorCitizen` | `int64` | Whether the customer is a senior citizen (`1` = Yes, `0` = No) | Demographic segmentation |
| `Partner` | `object` | Whether the customer has a partner | Household profile |
| `Dependents` | `object` | Whether the customer has dependents | Household profile |
| `tenure` | `int64` | Number of months the customer has stayed with the company | Churn-over-time analysis |
| `PhoneService` | `object` | Whether the customer has phone service | Service adoption |
| `MultipleLines` | `object` | Whether the customer has multiple phone lines | Service adoption |
| `InternetService` | `object` | Internet service type (DSL, Fiber optic, No) | Service segmentation |
| `OnlineSecurity` | `object` | Whether the customer has online security add-on | Add-on retention effect |
| `OnlineBackup` | `object` | Whether the customer has online backup add-on | Add-on retention effect |
| `DeviceProtection` | `object` | Whether the customer has device protection | Add-on retention effect |
| `TechSupport` | `object` | Whether the customer has tech support | Add-on retention effect |
| `StreamingTV` | `object` | Whether the customer streams TV | Service usage |
| `StreamingMovies` | `object` | Whether the customer streams movies | Service usage |
| `Contract` | `object` | Contract term (Month-to-month, One year, Two year) | Retention segmentation |
| `PaperlessBilling` | `object` | Whether the customer uses paperless billing | Billing behavior |
| `PaymentMethod` | `object` | Payment method used | Payment preference |
| `MonthlyCharges` | `float64` | Amount charged to the customer monthly | Pricing sensitivity |
| `TotalCharges` | `object` | Total amount charged to date (stored as text; convert to numeric) | Customer lifetime value |
| `Churn` | `object` | Whether the customer left (`Yes` / `No`) | **Target variable** |

> **Note:** `TotalCharges` is read as `object`, so convert it before analysis:
> ```python
> df["TotalCharges"] = pd.to_numeric(df["TotalCharges"], errors="coerce")
> ```

---

## 🔍 Core Analysis Questions

### 1. Overall Churn Rate
What proportion of customers have churned, and how balanced is the dataset?

### 2. Churn Over Time
How does the churn rate change across tenure or time periods? When are customers most likely to leave?

### 3. Churn by Customer Segment
How does churn differ across demographics, contract types, services, and payment methods?

### 4. Billing & Pricing Impact
Do higher monthly charges correlate with higher churn?

### 5. Feature Correlations
Which variables are most strongly associated with churn?

### 6. Retention Opportunities
Which segments should be prioritized for retention campaigns?

---


## 🚀 Setup & Execution Guide

### 1. Clone the Repository
```bash
git clone https://github.com/akash3005-arc/Customer-Churn-Analytics.git
cd Customer-Churn-Analytics
```

### 2. Python Environment Setup
```bash
# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install pandas numpy matplotlib seaborn jupyter
```

### 3. Run the Notebooks
```bash
jupyter notebook
```
Open the notebooks in the `notebooks/` folder and run the cells in order. Outputs are saved to `reports/`.

---

## 🔮 Future Enhancements
- Predictive churn modeling (Logistic Regression, Random Forest, XGBoost)
- Customer segmentation via clustering
- Interactive dashboard (Power BI / Streamlit)

---

## 👤 Author & Developer

**Akash**
- **GitHub**: [@akash3005-arc](https://github.com/akash3005-arc)

---

## 📄 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details. *(Add a `LICENSE` file to the repo, or remove this section and the badge.)*