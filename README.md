# Customer Risk Analysis Dashboard (Power BI)

https://app.powerbi.com/view?r=eyJrIjoiYzJjYjgzNmQtZGMxOS00NWM3LTk1NmQtZDZhOWNiNjc0ZmI0IiwidCI6IjgyMGVlMTdmLTc3YTYtNDIxNi05NTIxLTlhODBmNmU1NzEwOCJ9&pageName=17c1340eb3a99cded69f

## 📌 Project Overview
This project focuses on identifying customers with elevated churn risk in a retail banking context.
The dashboard is designed to support **targeted retention actions** by segmenting customers into risk levels and highlighting the key drivers behind churn risk.

Unlike high-level reporting dashboards, this analysis emphasizes **actionability and prioritization**.

---

## 🎯 Business Objective
- Identify customers with high likelihood of churn
- Understand the main drivers contributing to customer risk
- Quantify the financial exposure associated with high-risk customers
- Enable data-driven retention strategies

---

## 📊 Dashboard: Customer Risk Analysis

[![Customer Risk Analysis](screenshots/customer_risk_analysis.png)](https://github.com/janijutt/Customer-Risk-Analysis-Powerbi/blob/main/Project%20SS.png)

### Key Components
- **Risk Segmentation**: Customers classified into High, Medium, and Low risk groups
- **Risk Drivers**: Analysis of activity status and product ownership across risk levels
- **Financial Exposure**: Balance held by high-risk customers

---

**## 🔍 Key Insights**
- Inactive customers represent a disproportionately large share of the high-risk segment
- Customers holding only one product show significantly higher churn risk
- High-risk customers hold a meaningful portion of total account balances, indicating material financial exposure

---

## 🧠 Risk Scoring Approach
Customer risk was calculated using a transparent, rule-based scoring model incorporating:
- Customer activity status
- Credit score thresholds
- Product ownership
- Age-based behavioral patterns

This approach ensures interpretability and aligns with real-world business decision-making.

---

## 🛠 Tools & Technologies
- Power BI Desktop
- DAX (calculated columns & measures)
- Data modeling & visualization
- Risk segmentation logic

---

## ▶️ How to Use
1. Download the PBIX file from the `/pbix` folder
2. Open with **Power BI Desktop**
3. If prompted, update the data source to point to `/data/bank_churn_sample.csv`

---

## 📂 Repository Contents
- /pbix – Power BI dashboard file  
- /data – Sample dataset (anonymized)  
- /screenshots – Dashboard image  
- /dax – Key risk-related measures and calculations

- ## 📌 Data Disclaimer
The dataset used in this project is a **synthetic (dummy) dataset** created solely for learning and demonstration purposes.
It does **not** represent real customer data and contains **no personally identifiable information (PII)**.

The structure, distributions, and relationships were designed to closely resemble real-world banking churn scenarios, enabling realistic analysis and dashboard design.
