# Telecom Customer Churn Analysis using Power BI

A comprehensive **Customer Churn Analysis Dashboard** built in **Microsoft Power BI** to help telecom companies identify customers at risk of leaving and support data-driven customer retention strategies.

---

## Author

**Khaja Ahmed Junaid**

**GitHub:** https://github.com/khajajunaid

---

## Project Overview

Customer retention is one of the most important challenges in the telecom industry. Acquiring new customers is significantly more expensive than retaining existing ones. This project analyzes customer behavior to identify churn patterns and provides actionable insights through an interactive Power BI dashboard.

The dashboard enables business stakeholders to:

* Monitor customer churn rate
* Analyze customer demographics
* Understand account-related churn factors
* Evaluate service subscription trends
* Identify high-risk customer segments
* Support proactive customer retention strategies

---

## Business Problem

The telecom company's retention team wanted to move from a reactive approach to a proactive customer retention strategy.

### Objectives

* Identify customers likely to churn
* Understand key drivers behind customer churn
* Visualize customer behavior using interactive dashboards
* Enable management to make informed business decisions

---

## Dataset

* **Source:** Forage Telecom Customer Churn Dataset
* **Format:** Microsoft Excel
* **Rows:** 7,043
* **Columns:** 23

The dataset contains:

* Customer Demographics
* Account Information
* Service Subscriptions
* Billing Details
* Customer Churn Status

---

## Technology Used

* Microsoft Power BI
* Power Query
* DAX
* Microsoft Excel

---

## Skills Demonstrated

* Data Cleaning
* Data Transformation
* Data Standardization
* Data Modeling
* DAX Calculations
* Dashboard Design
* Business Intelligence
* Data Visualization

---

## Data Preparation

The dataset was cleaned and transformed using **Power Query**.

### Data Cleaning

* Corrected data types
* Renamed columns
* Standardized payment method names
* Removed inconsistencies
* Prepared data for modeling

### Additional Columns

Two calculated columns were created:

**Citizenship Status**

```DAX
CitizenshipStatus =
IF(
    ChurnDataset[SeniorCitizen] = 0,
    "Young Citizen",
    "Senior Citizen"
)
```

**Churn Status**

```DAX
ChurnStatus =
IF(
    ChurnDataset[Churn] = "Yes",
    "Churned",
    "Retained"
)
```

---

## Data Modeling

After cleaning, the dataset was modeled in Power BI using appropriate relationships to support efficient reporting and DAX calculations.

---

## DAX Measures

### Total Customers

```DAX
Total Customers =
COUNT(ChurnDataset[CustomerID])
```

### Churned Customers

```DAX
Churned Customers =
CALCULATE(
    COUNTA(ChurnDataset[CustomerID]),
    ChurnDataset[Churn] = "Yes"
)
```

### Retained Customers

```DAX
Retained Customers =
CALCULATE(
    COUNTA(ChurnDataset[CustomerID]),
    ChurnDataset[Churn] = "No"
)
```

### Churn Rate

```DAX
Churn Rate =
DIVIDE(
    [Churned Customers],
    [Total Customers]
)
```

### Monthly Revenue Loss

```DAX
Monthly Revenue Loss =
CALCULATE(
    SUM(ChurnDataset[MonthlyCharges]),
    ChurnDataset[Churn] = "Yes"
)
```

### Revenue Loss Percentage

```DAX
Revenue Loss % =
DIVIDE(
    [Monthly Revenue Loss],
    SUM(ChurnDataset[MonthlyCharges]),
    0
)
```

### Payment Mode

```DAX
Payment Mode =
IF(
    OR(
        ChurnDataset[PaymentMethod] = "Electronic Check",
        ChurnDataset[PaymentMethod] = "Mailed Check"
    ),
    "Manual",
    "Automatic"
)
```

---

## Dashboard Pages

### 1. Customer Demographics

Analyzes churn based on:

* Gender
* Senior Citizens
* Partner Status
* Dependents

---

### 2. Account Details

Provides insights into:

* Contract Type
* Tenure
* Monthly Charges
* Total Charges
* Payment Method
* Paperless Billing
* Administrative Tickets
* Technical Support Tickets

---

### 3. Customer Services

Analyzes customer subscriptions including:

* Phone Service
* Multiple Lines
* Internet Service
* Online Security
* Online Backup
* Device Protection
* Tech Support
* Streaming TV
* Streaming Movies

---

## Key Insights

* Overall customer churn rate is approximately **27%**.
* Customers with **Month-to-Month contracts** have the highest churn.
* Long-term contract customers show significantly higher retention.
* Customers using **Fiber Optic Internet** experience higher churn compared to other internet services.
* Customers without **Online Security** or **Tech Support** are much more likely to leave.
* Manual payment methods are associated with higher churn.
* Recently acquired customers are at greater risk of cancellation.

---

## Business Recommendations

* Encourage customers to upgrade to **One-Year** and **Two-Year** contracts.
* Offer retention discounts to Month-to-Month customers.
* Promote **Automatic Payment** options.
* Increase awareness of **Online Security** and **Tech Support** services.
* Launch targeted retention campaigns for high-risk customer segments.
* Improve customer support for Fiber Optic users to reduce churn.

---

## Project Outcomes

This dashboard enables stakeholders to:

* Monitor churn trends in real time
* Identify high-risk customers
* Improve customer retention strategies
* Reduce revenue loss
* Support data-driven business decisions

---

## Repository Structure

```
Telecom-Customer-Churn-Analysis/
│
├── Dataset/
├── PowerBI Dashboard/
├── Project Images/
├── README.md
└── Telecom Customer Churn.pbix
```

---

## Future Improvements

* Integrate Machine Learning models for churn prediction.
* Connect to live databases for real-time reporting.
* Build executive KPI dashboards.
* Implement customer segmentation using RFM analysis.
* Add predictive analytics and forecasting.

---

## License

This project is intended for learning, portfolio, and demonstration purposes.

---

### Connect

**Author:** Khaja Ahmed Junaid

**GitHub:** https://github.com/khajajunaid
