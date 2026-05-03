# Supply-Chain-Analysis
Analysing 172,765 e-commerce orders (2015–2018) to identify late delivery root causes, quantify $2.1M profit at risk, detect operational bottlenecks, and deploy a Random Forest model (74% accuracy) for predictive delay alerts.

# Supply Chain Delivery Performance Analysis

> Analysing 172,765 e-commerce orders (2015–2018) to identify late delivery root causes, quantify $2.1M profit at risk, detect operational bottlenecks, and deploy a Random Forest model (74% accuracy) for predictive delay alerts.

---

## 📋 Overview

This project presents a comprehensive end-to-end supply chain delivery performance analysis for a global e-commerce fulfilment operation. The analysis spans **January 2015 – January 2018**, covering **172,765 orders** across multiple international regions and product categories including sporting goods, fitness equipment, outdoor gear, footwear, and apparel.

The headline finding: **54.71% of all orders are delivered late**, costing the business **$2.1M in eroded profitability**. A Random Forest predictive model was built to flag at-risk orders before they ship, achieving **74% accuracy**.

---

## 📊 Key Metrics

| Metric | Value |
|--------|-------|
| Total Orders Analysed | 172,765 |
| Late Delivery Rate | 54.71% |
| On-Time Delivery Rate | 45.29% |
| Total Profit (profitable orders) | $7.5M |
| Profit at Risk (delayed orders) | $2.1M |
| Average Order Profit | $22.03 |
| 90th Percentile Delay | 3 days |
| Predictive Model Accuracy (RF) | 74% |

---

## 🔍 Analysis Sections

### 1. Profitability Analysis
- **80.7%** of orders are profitable; **18.7%** are loss-making
- **31%** of all orders arrive exactly 1 day late — the single largest delay cohort
- Mean profit per order is stable at ~$21–$23 across all delay levels, confirming the problem is **volume-driven**, not per-order economics

### 2. Bottleneck Detection
Delay percentage computed across six operational dimensions:

| Dimension | Key Finding |
|-----------|-------------|
| Shipping Mode | First Class: **100%** delay rate; Second Class: **79.8%**; Same Day: **0%** |
| Region | All regions cluster at **55–59%** — confirms a systemic company-wide issue |
| Customer Segment | Consumer, Corporate, Home Office all at **54.5–55.4%** — no preferential service |
| Department | Health & Beauty (**56.9%**) and Pet Shop (**56.6%**) lead delay rates |

### 3. Root Cause Analysis
Deep-dive on Central Africa (highest-delay region at 58.7%):
- First Class shipping: **100%** delay rate
- Second Class shipping: **82.8%** delay rate
- PAYMENT_REVIEW order status: **80.0%** delay rate
- PENDING order status: **69.1%** delay rate

### 4. Time-Based Delay Patterns
- Peak months: **August & September (55.4%)** and **December (55.2%)**
- Day-of-week variance: less than **1 percentage point** — not a meaningful lever
- Intra-day peak: **Hour 21 (57.1%)** — likely tied to processing cutoff windows

### 5. Machine Learning Model
- Algorithm: **Random Forest Classifier**
- Class imbalance handled via **SMOTE oversampling**
- Test set: 34,553 records

| Metric | On-Time (Class 0) | Late (Class 1) | Weighted Avg |
|--------|-------------------|----------------|--------------|
| Precision | 0.68 | 0.78 | 0.74 |
| Recall | 0.72 | 0.75 | 0.74 |
| F1-Score | 0.70 | 0.77 | 0.74 |
| Accuracy | — | — | **0.74** |

---

## 🎯 Strategic Recommendations

| Priority | Recommendation |
|----------|----------------|
| 🔴 High | Immediately audit First Class & Second Class shipping carrier SLAs |
| 🔴 High | Deploy the predictive alert system into the order management pipeline |
| 🔴 High | Resolve payment processing bottlenecks with automated escalation |
| 🟡 Medium | Develop seasonal surge capacity plans for Aug, Oct, Dec |
| 🟡 Medium | Default eligible orders to Standard Class (39.8% delay rate) |
| 🟡 Medium | Investigate high-delay departments (Outdoors, Golf) in Central Africa |
| 🟢 Low | Review pricing/discounts on the 18.7% loss-making order share |
| 🟢 Low | Retrain the predictive model quarterly; target >80% recall within 6 months |

---

## 🎯 Targets

| Area | Current State | Target |
|------|--------------|--------|
| Late Delivery Rate | 54.71% | < 30% within 12 months |
| First Class On-Time Rate | 0% | > 80% |
| Second Class On-Time Rate | 20.2% | > 60% |
| Predictive Model Accuracy | 74% | > 82% |
| Loss-Making Orders | 18.7% | < 12% |
| Profit at Risk | $2.1M | Reduce by 40% |

---

## 🛠️ Tools & Methods

- **Data Coverage:** January 2015 – January 2018
- **Orders Analysed:** 172,765
- **ML Algorithm:** Random Forest Classifier
- **Imbalance Handling:** SMOTE (Synthetic Minority Oversampling Technique)
- **Encoding:** Frequency encoding for categorical variables
- **Validation:** Stratified train/test split


