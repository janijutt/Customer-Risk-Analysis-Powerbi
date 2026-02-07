# Customer Risk Analysis – Key DAX Logic

This document outlines the core DAX calculations used in the **Customer Risk Analysis** Power BI dashboard.
The measures and calculated columns focus on identifying high-risk customers and supporting actionable retention insights.

> **Note:** The dataset used is synthetic and created for demonstration purposes only.  
> The analytical logic and dashboard design reflect real-world banking risk analysis practices.

---

## 📊 Base Measures

### Total Customers
```DAX
Total Customers =
DISTINCTCOUNT(bank[customer_id])
```

---

### Customer Count
```DAX
Customer Count =
DISTINCTCOUNT(bank[customer_id])
```

---

## 🔴 Churn Measures

### Churned Customers
```DAX
Churned Customers =
CALCULATE(
    COUNTROWS(bank),
    bank[churn] = 1
)
```

---

### Churn Rate %
```DAX
Churn Rate % =
DIVIDE(
    [Churned Customers],
    [Total Customers]
)
```

---

## ⚠️ Risk Scoring Logic

### Risk Score (Calculated Column)
```DAX
Risk Score =
IF(bank[active_member] = 0, 30, 0) +
IF(bank[credit_score] < 600, 25, 0) +
IF(bank[products_number] = 1, 20, 0) +
IF(bank[age] >= 36 && bank[age] <= 55, 15, 0)
```

---

### Risk Level (Calculated Column)
```DAX
Risk Level =
SWITCH(
    TRUE(),
    bank[Risk Score] >= 60, "High Risk",
    bank[Risk Score] >= 30, "Medium Risk",
    "Low Risk"
)
```

---

## 🚨 High-Risk Customer Metrics

### High-Risk Customers
```DAX
High Risk Customers =
CALCULATE(
    DISTINCTCOUNT(bank[customer_id]),
    bank[Risk Level] = "High Risk"
)
```

---

### High-Risk Share
```DAX
High Risk % =
DIVIDE(
    [High Risk Customers],
    [Total Customers]
)
```

---

### Average Balance – High Risk
```DAX
Avg Balance (High Risk) =
CALCULATE(
    AVERAGE(bank[balance]),
    bank[Risk Level] = "High Risk"
)
```

---

## 🧠 Supporting Dimensions

### Active Status
```DAX
Active Status =
IF(bank[active_member] = 1, "Active", "Inactive")
```

---

### Churn Status
```DAX
Churn Status =
IF(bank[churn] = 1, "Churned", "Retained")
```

---

## ✅ Summary

These DAX calculations support transparent risk scoring, customer segmentation, and executive-level decision making.
