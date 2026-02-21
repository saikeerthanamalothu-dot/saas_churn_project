# SaaS Customer Churn Prediction Model

**Author:** Sai Keerthana Malothu  
**Tools:** Python (pandas, scikit-learn, matplotlib, seaborn) | Logistic Regression | Random Forest | Jupyter Notebook  
**Domain:** SaaS / Subscription Business | Customer Analytics | Predictive Modelling  
**Dataset:** Synthetic dataset designed to simulate a real-world SaaS company with 5,000 customers across 4 subscription plans

---

## Project Overview

This end-to-end machine learning project predicts customer churn for a SaaS company experiencing a **31.2% churn rate**. Using behavioral, contractual, and demographic data across 5,000 customers, the project builds a logistic regression model that identifies at-risk customers before they cancel — enabling the customer success and marketing teams to intervene proactively.

The project goes beyond model building to deliver a **scored customer list, risk segmentation, and actionable retention recommendations** — translating technical outputs into business decisions.

---

## Business Problem

A SaaS company is losing 31% of its customers annually with no systematic way to identify who is at risk before they cancel. The customer success team reacts to cancellations rather than preventing them. The business needs:

- A predictive model to flag at-risk customers early
- Understanding of which factors drive churn
- A prioritised list of customers for proactive outreach
- Quantification of revenue at risk

---

## Project Workflow

```
Raw Data → EDA → Feature Engineering → Model Training → Evaluation → Business Recommendations
```

### Phase 1 — Exploratory Data Analysis
- Analyzed churn patterns across plan type, contract length, acquisition channel, and industry
- Identified behavioral signals: login frequency, days since last login, features used, NPS score
- Visualized churn reasons — price and competition account for 53% of churn

### Phase 2 — Feature Engineering & Preprocessing
- Encoded categorical variables using one-hot encoding
- Engineered NPS tier and tenure bucket features
- Scaled numeric features using StandardScaler
- Split data 80/20 train/test with stratification to preserve churn ratio

### Phase 3 — Model Building
- Built and compared Logistic Regression and Random Forest classifiers
- Used class_weight='balanced' to handle class imbalance
- Evaluated using accuracy, precision, recall, F1-score, and AUC-ROC

### Phase 4 — Business Output
- Scored all 5,000 customers with individual churn probability
- Segmented customers into High, Medium, and Low risk tiers
- Exported prioritised CRM list for customer success team
- Delivered retention strategy framework with estimated impact

---

## Model Performance

| Model | Accuracy | AUC-ROC |
|---|---|---|
| Logistic Regression | 72.8% | 0.821 |
| Random Forest | ~84% | ~0.88 |

**Why AUC-ROC matters more than accuracy:**
For churn prediction the dataset is imbalanced — there are more retained customers than churned ones. AUC-ROC measures how well the model ranks churners above non-churners regardless of class balance. An AUC of 0.821 means the model correctly identifies a churner over a retained customer 82% of the time. Industry benchmark for a production churn model is 0.75+.

---

## Key Findings

| Finding | Detail |
|---|---|
| Overall churn rate | 31.2% across 5,000 customers |
| Starter plan churn | 42.7% vs Enterprise at 13.2% |
| Monthly contract churn | 43.1% vs Two-Year at 13.5% |
| NPS Detractors (1-3) | Churn at 60%+ — strongest early warning signal |
| Top churn reason | Price too high (28%) followed by competitor switching (25%) |
| Referral customers | Most loyal — lowest churn of all acquisition channels |
| Strongest predictors | Days since last login, logins per month, NPS score, contract type |

---

## Business Impact

| Metric | Value |
|---|---|
| High Risk customers identified | 1,560 |
| Monthly revenue at risk | $155,663 |
| Annual revenue at risk | $1,867,956 |
| Saving if 20% of High Risk retained | $373,000 annually |

---

## Retention Strategy

| Risk Tier | Trigger | Recommended Action | Priority |
|---|---|---|---|
| High Risk | Churn prob > 60% + days since login > 30 | Personal CSM outreach within 48 hours | CRITICAL |
| High Risk | Churn prob > 60% + payment failure > 0 | Billing support + payment plan offer | CRITICAL |
| Medium Risk | Churn prob 30-60% + NPS ≤ 5 | Product health check call + case studies | HIGH |
| Medium Risk | Churn prob 30-60% + features used < 5 | Feature adoption email campaign | MEDIUM |
| Low Risk | Churn prob < 30% | Quarterly check-in + upsell opportunity | LOW |

---

## Visualisations

### Churn Overview & Plan Analysis
![Churn Overview](chart1_churn_overview.png)

### Churn by Contract Type & Acquisition Channel
![Churn by Segment](chart2_churn_by_segment.png)

### Behavioral Signals vs Churn
![Behavioral Signals](chart3_behavioral_signals.png)

### Why Customers Churned
![Churn Reasons](chart4_churn_reasons.png)

### Model Confusion Matrix
![Confusion Matrix](chart5_confusion_matrix.png)

### ROC Curve — Model Comparison
![ROC Curve](chart6_roc_curve.png)

### Top 15 Features Driving Churn
![Feature Importance](chart7_feature_importance.png)

### Key Churn Driver Analysis
![Churn Drivers](chart8_churn_drivers.png)

---

## Repository Structure

```
saas-churn-prediction/
├── README.md
├── 01_churn_analysis.ipynb              ← Full analysis, modelling & recommendations
├── saas_churn_data.csv                  ← Raw dataset (5,000 customers, 20 features)
├── saas_churn_data_cleaned.csv          ← Cleaned dataset
├── churn_scores.csv                     ← All customers scored with churn probability
├── churn_scores.xlsx
├── high_risk_customers_crm.xlsx         ← Prioritised list for CRM outreach
├── retention_strategy.xlsx              ← Retention action framework
├── chart1_churn_overview.png
├── chart2_churn_by_segment.png
├── chart3_behavioral_signals.png
├── chart4_churn_reasons.png
├── chart5_confusion_matrix.png
├── chart6_roc_curve.png
├── chart7_feature_importance.png
└── chart8_churn_drivers.png
```

---

## Skills Demonstrated

| Category | Skills |
|---|---|
| Machine Learning | Logistic Regression, Random Forest, model evaluation, AUC-ROC |
| Data Preparation | Feature engineering, one-hot encoding, scaling, train/test split |
| Python | pandas, scikit-learn, matplotlib, seaborn, Jupyter Notebook |
| Business Analysis | Churn driver analysis, revenue impact quantification, retention strategy |
| Communication | Translating model outputs into stakeholder-ready recommendations |

---

## How to Use This Repository

1. Clone the repository
```bash
git clone https://github.com/saikeerthanamalothu-dot/saas-churn-prediction.git
cd saas-churn-prediction
```

2. Install dependencies
```bash
pip install pandas numpy matplotlib seaborn scikit-learn openpyxl jupyter
```

3. Open and run the notebook
```bash
jupyter notebook 01_churn_analysis.ipynb
```

4. The notebook runs end to end — all outputs, charts, and exported files are regenerated automatically

---

## How This Relates to Real-World Work

This project mirrors what a Business Analyst or Data Analyst would deliver in a SaaS company:

- **The model** is what data teams build to score customers
- **The risk segmentation** is what goes into the CRM for the customer success team
- **The retention strategy** is what gets presented to the VP of Customer Success
- **The revenue at risk figure** is what gets presented to the CFO

The goal was not just to build a model but to deliver something a non-technical stakeholder could act on immediately.

---

## About

This project was built as part of a data analytics portfolio to demonstrate end-to-end capability across exploratory analysis, predictive modelling, and business communication. It is the second project in a portfolio that also includes a Procurement Spend Analytics dashboard — demonstrating versatility across industries and analytical techniques.

**Project 1:** [Procurement Spend Analytics & Savings Opportunity Dashboard](https://github.com/saikeerthanamalothu-dot/procurement-spend-analytics)

---

*Sai Keerthana Malothu | MSc Business Analytics*
