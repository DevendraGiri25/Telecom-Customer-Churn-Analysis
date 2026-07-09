# 📉 Customer Churn Analysis — Telecom Industry

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=for-the-badge&logo=python&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-4C72B0?style=for-the-badge&logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)

---

## 📌 Project Overview

An end-to-end **Exploratory Data Analysis (EDA)** project analyzing customer churn behavior in a telecom company. Using a dataset of **7,043 customers** across 21 features, this project uncovers the key drivers of customer churn through statistical analysis, feature engineering, and data visualization.

The analysis identifies high-risk customer segments and delivers actionable recommendations to help the business reduce churn rate from **26.54%** through targeted retention strategies.

> 📊 **Sample Visualizations**

| Churn Distribution | Churn by Contract Type |
|---|---|
| ![Churn Distribution](images/output_14_0.png) | ![Contract Churn](images/output_29_0.png) |

---

## 🚨 Business Problem

Customer churn is one of the most expensive problems in the telecom industry. Acquiring a new customer costs **5–7x more** than retaining an existing one. Despite this, many telecom companies lack clarity on:

- **Which customer segments are most likely to churn?**
- **Does contract type, tenure, or payment method influence churn?**
- **Are demographic factors (gender, senior citizen status, dependents) meaningful churn predictors?**
- **What early warning signals can help retention teams intervene before a customer leaves?**

Without data-driven answers to these questions, retention teams apply generic strategies that waste budget and miss the highest-risk customers.

---

## 🎯 Objective

To perform a comprehensive exploratory data analysis that:

- Quantifies the **overall churn rate** and its distribution across customer segments
- Identifies the **top drivers of churn** across demographic, service, and behavioral dimensions
- Surfaces **actionable insights** for the retention and marketing teams
- Delivers **11 targeted visualizations** that make findings accessible to non-technical stakeholders

---

## 🗂️ Dataset

| Attribute | Detail |
|-----------|--------|
| **Source** | Telecom Customer Churn Dataset |
| **Records** | 7,043 customers |
| **Features** | 21 columns |
| **Target Variable** | Churn (Yes / No) |

### Feature Categories

| Category | Features |
|----------|----------|
| **Demographics** | gender, SeniorCitizen, Partner, Dependents |
| **Account Info** | tenure, Contract, PaperlessBilling, PaymentMethod, MonthlyCharges, TotalCharges |
| **Services** | PhoneService, MultipleLines, InternetService, OnlineSecurity, OnlineBackup, DeviceProtection, TechSupport, StreamingTV, StreamingMovies |
| **Target** | Churn |

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|------|---------|
| **Python 3** | Core programming language |
| **Pandas** | Data loading, cleaning, manipulation, and feature engineering |
| **NumPy** | Numerical operations and array handling |
| **Matplotlib** | Base plotting and chart customization |
| **Seaborn** | Statistical visualizations — countplots, histograms, heatmaps |
| **Jupyter Notebook** | Interactive analysis and documentation environment |

---

## 🔍 Analysis Process

### Step 1 — Data Loading & Initial Exploration
- Loaded dataset using Pandas (`pd.read_csv`)
- Inspected shape, data types, column names, and first/last rows
- Identified 21 features including 17 categorical and 4 numerical columns
- Confirmed dataset contains **7,043 rows × 21 columns**

### Step 2 — Data Cleaning & Preprocessing
- Checked for null values and missing data across all columns
- Converted `SeniorCitizen` from binary (0/1) to categorical (No/Yes) for consistency
- Handled `TotalCharges` column — converted from object to numeric, filled missing values
- Verified no duplicate `customerID` records existed
- Standardized categorical values for consistent grouping

### Step 3 — Feature Engineering
- Created **contract type buckets** — Month-to-month, One year, Two year
- Engineered **tenure bands** to segment customers by relationship length
- Derived churn rate percentage per segment for comparative analysis
- Separated numerical and categorical columns for targeted analysis

### Step 4 — Exploratory Data Analysis (EDA)
- Analyzed churn distribution across all 17 categorical features
- Examined numerical feature distributions (tenure, MonthlyCharges, TotalCharges)
- Built cross-tabulations between churn and key features
- Investigated correlation between tenure and churn probability

### Step 5 — Data Visualization (11 Charts)
- Bar charts for churn count by gender, contract, payment method
- Pie chart for overall churn rate distribution
- Histogram for tenure distribution by churn status
- Distribution plots for all categorical features
- Grouped bar charts for multi-dimensional comparisons

### Step 6 — Insight Generation & Recommendations
- Ranked churn drivers by impact magnitude
- Translated statistical findings into business recommendations
- Documented actionable strategies for each high-risk segment

---

## 💡 Key Insights

### 1. 📊 Overall Churn Rate — 26.54%
- **5,174 customers (73.46%)** stayed vs **1,869 customers (26.54%)** churned
- Over 1 in 4 customers is leaving — significantly above industry average of 15–20%
- Immediate intervention required for high-risk segments

![Churn Pie Chart](images/output_14_0.png)

---

### 2. 📋 Contract Type — #1 Churn Driver
- **Month-to-month customers** show a churn count of **1,655 vs 2,220 retained** — a churn rate of **~43%**
- **One-year contracts**: only **166 churned vs 1,307 retained** — churn rate of **~11%**
- **Two-year contracts**: only **48 churned vs 1,647 retained** — churn rate of just **~3%**
- **Key takeaway**: Every month a customer stays on month-to-month, churn risk remains 14x higher than two-year contract holders

![Contract Churn](images/output_29_0.png)

---

### 3. 📅 Tenure — Early Months Are Critical
- Churn is **heavily concentrated in the first 1–5 months** of tenure
- Months 1–3 show the highest orange (churn) bars in the histogram
- Customers who survive past month 10 show dramatically lower churn probability
- Long-tenure customers (60–72 months) are highly loyal with near-zero churn
- **Key takeaway**: The first 90 days are the highest-risk window — onboarding and early engagement programs are critical

![Tenure Distribution](images/output_26_1.png)

---

### 4. 💳 Payment Method — Electronic Check is a Red Flag
- **Electronic check** users: **1,071 churned vs 1,294 retained** — churn rate of **~45%**
- **Mailed check**: only 308 churned — churn rate of **~19%**
- **Bank transfer (automatic)**: only 258 churned — churn rate of **~17%**
- **Credit card (automatic)**: only 232 churned — churn rate of **~15%**
- **Key takeaway**: Electronic check users churn at 3x the rate of automatic payment users — migrating customers to auto-pay should be a retention priority

![Payment Method Churn](images/output_34_0.png)

---

### 5. 👤 Gender — No Significant Impact
- Female churn: **939** | Male churn: **930** — nearly identical
- Gender is **not a meaningful churn predictor** for this telecom company
- Retention strategies should not be segmented by gender

![Gender Churn](images/output_18_0.png)

---

### 6. 👥 Dependents — Customers Without Dependents Churn More
- **4,933** customers have no dependents vs **2,110** with dependents
- Customers without dependents show higher churn propensity
- Families with dependents tend to value service stability and churn less

![Dependents](images/output_24_0.png)

---

### 7. 💑 Partner Status — Singles Are Higher Risk
- Customers without a partner: **3,641** vs with partner: **3,402**
- Single customers show slightly higher churn tendency
- Bundled family plans could serve as a retention tool for single customers

![Partner](images/output_25_0.png)

---

### 8. 📦 Distribution Across All Features
- **PhoneService**: 90%+ of customers have phone service — low differentiator
- **Fiber Optic** internet users show higher churn than DSL users
- **No OnlineSecurity, TechSupport, or DeviceProtection** correlates with higher churn
- Customers without add-on services are significantly more likely to leave

![All Features Distribution](images/output_32_1.png)

---

## 📋 Business Recommendations

| Priority | Recommendation | Target Segment | Expected Impact |
|----------|---------------|----------------|-----------------|
| 🔴 High | Offer incentives to convert month-to-month customers to annual contracts | Month-to-month, tenure < 6 months | Reduce churn by ~15% |
| 🔴 High | Launch 90-day onboarding program with dedicated support | New customers (tenure 0–3 months) | Reduce early churn by ~20% |
| 🟠 Medium | Incentivize switch from electronic check to auto-payment | Electronic check users | Reduce payment-related churn by ~10% |
| 🟠 Medium | Bundle OnlineSecurity + TechSupport at discounted rate | Customers with no add-ons | Increase stickiness and ARPU |
| 🟡 Low | Develop loyalty rewards program for customers at 12-month milestone | All segments | Improve long-term retention |

---

## 📁 Project Structure

```
Customer-Churn-Analysis/
│
├── 📓 customer_churn_analysis.ipynb    # Main Jupyter Notebook
├── 📂 data/
│   └── customer_churn.csv              # Raw dataset
├── 📂 images/
│   ├── output_12_0.png                 # Churn count bar chart
│   ├── output_14_0.png                 # Churn pie chart
│   ├── output_18_0.png                 # Churn by gender
│   ├── output_20_0.png                 # Churn by SeniorCitizen
│   ├── output_21_0.png                 # SeniorCitizen distribution
│   ├── output_24_0.png                 # Dependents distribution
│   ├── output_25_0.png                 # Partner distribution
│   ├── output_26_1.png                 # Tenure histogram by churn
│   ├── output_29_0.png                 # Churn by contract type
│   ├── output_32_1.png                 # All features distribution
│   └── output_34_0.png                 # Churn by payment method
└── 📄 README.md                        # Project documentation
```

---

## 🚀 How to Run This Project

### 1. Clone the repository
```bash
git clone https://github.com/DevendraGiri25/Customer-Churn-Analysis.git
cd Customer-Churn-Analysis
```

### 2. Install required libraries
```bash
pip install pandas numpy matplotlib seaborn jupyter
```

### 3. Launch Jupyter Notebook
```bash
jupyter notebook customer_churn_analysis.ipynb
```

### 4. Run all cells
- Go to **Kernel → Restart & Run All**
- All 11 visualizations will regenerate automatically

---

## 📈 Results Summary

| Metric | Value |
|--------|-------|
| Total Customers Analyzed | 7,043 |
| Overall Churn Rate | 26.54% |
| Highest Risk Segment | Month-to-month + Tenure < 3 months |
| Highest Risk Payment Method | Electronic Check (45% churn rate) |
| Safest Contract Type | Two-year (3% churn rate) |
| Visualizations Generated | 11 |
| Features Analyzed | 21 |

---

## 🤝 Connect With Me

**Devendra Giri**
- 💼 [LinkedIn](https://www.linkedin.com/in/devendragiri25)
- 🐙 [GitHub](https://github.com/DevendraGiri25)
- 📧 devendragiri1225@gmail.com

---

⭐ **If you found this project useful, please give it a star!** It helps others discover the project.

---

*Built with 💙 using Python | Pandas | Matplotlib | Seaborn | Jupyter Notebook*
