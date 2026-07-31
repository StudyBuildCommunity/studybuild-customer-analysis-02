# 📊 StudyBuild – Project 02: Customer Behavior Analysis

> **Role:** Junior Data Analyst  
> **Client:** E-commerce Company (Simulated)  
> **Status:** ✅ Completed & Merged  
> **Date:** July 31, 2026

---

## 📌 Executive Summary

As a Junior Data Analyst at an e-commerce company, I was tasked with transforming raw customer transaction data into **actionable business intelligence**. The CEO needed clear answers to five critical questions to make data-driven decisions about marketing budget, customer retention, discount strategies, and revenue growth.

Using **Python (pandas, numpy, matplotlib)** and a cleaned dataset of **60 customers**, I performed:

- **RFM-style segmentation** – identifying high-value customers
- **Churn risk analysis** – detecting at-risk customers based on recency
- **Multi‑metric city scoring** – selecting the best city for marketing campaigns
- **Discount effectiveness** – comparing spending behavior with/without discounts
- **Pareto (80/20) analysis** – assessing revenue concentration
- **Executive dashboard** – delivering 3 key visualizations for the CEO
- **Actionable recommendations** – each backed by evidence, action, and KPI

All findings are presented in this report, supported by **4 clear visualizations**, and directly linked to business decisions.

---

## 🗂️ Repository Structure

```
studybuild-customer-analysis-02/
├── dataset/                          # Raw & cleaned data
├── submissions/
│   └── mohammad-hussein-dev/
│       ├── project02_analysis.ipynb  # Full analysis notebook
│       ├── README.md                 # This report
│       ├── cleaned_dataset.xlsx      # Final cleaned dataset
│       └── charts/                   # 4 key visualizations (PNG)
│           ├── dashboard_ceo.png
│           ├── city_analysis.png
│           ├── discount_analysis.png
│           └── pareto_analysis.png
├── LICENSE
└── README.md                         # Repository root
```

---

## 🧠 Methodology Overview

| Step | Technique | Purpose |
| :--- | :--- | :--- |
| 1 | **EDA & Data Cleaning** | Handling missing values, duplicates, and outliers |
| 2 | **RFM Scoring** (Recency, Frequency, Monetary) | Quantify customer value |
| 3 | **Pareto Analysis** | Check if 20% of customers drive 80% of revenue |
| 4 | **Churn Risk Identification** | Flag customers with high value but long inactivity |
| 5 | **City Performance Scoring** | Score cities on 5 metrics (Revenue, Count, Satisfaction, Return Rate, Transactions) |
| 6 | **Discount Impact** | Compare spending, satisfaction, and return rates between discount vs. non‑discount groups |
| 7 | **Customer Segmentation** | Rule‑based grouping (Champions, Loyal, At‑Risk, Needs Attention) |
| 8 | **Executive Dashboard** | Select 3 most valuable charts for CEO decision‑making |
| 9 | **Business Recommendations** | Evidence‑based actions with clear KPIs |

All code is reproducible and documented in the accompanying Jupyter Notebook.

---

## 📊 Key Findings at a Glance

| Metric | Value |
| :--- | :--- |
| **Total Customers** | 60 |
| **Total Revenue** | \$89,450 |
| **Avg Spend per Customer** | \$1,490.83 |
| **Avg Order Value** | \$94.50 |
| **Avg Satisfaction Score** | 3.8 / 5.0 |
| **Return Rate** | 8.2% |
| **Revenue Concentration (Top 20%)** | **76%** of total revenue |
| **At‑Risk Customers** | 12 customers (no purchase in >90 days) |
| **Discount Impact** | Discount users spent **23% more** on average than non‑discount users |
| **Best City for Marketing** | **Tehran** (highest combined score across all metrics) |

---

## 🔍 Detailed Analysis & Visualizations

### 1. Executive Dashboard – CEO Overview *(Question 8)*

This dashboard is designed for the CEO’s 5‑minute review. It compresses the most critical metrics into one view.

![Executive Dashboard](submissions/mohammad-hussein-dev/charts/dashboard_ceo.png)

- **What it shows:** Total revenue, customer count, average spend, satisfaction distribution, and return rate.
- **Why it matters:** The CEO can immediately assess the health of the business without reading through tables or code.
- **Decision:** If average satisfaction drops below 3.5, initiate a customer service audit. If return rate exceeds 10%, review supplier quality.

---

### 2. City Performance – Marketing Budget Allocation *(Question 2)*

![City Analysis](submissions/mohammad-hussein-dev/charts/city_analysis.png)

- **What it shows:** A multi‑metric comparison of 5 cities across revenue, customer count, average spend, satisfaction, and return rate.
- **Why it matters:** The company has a limited budget and can only advertise in **one city**. This chart provides a 360‑degree view, not just revenue.
- **Decision:** **Tehran** is the optimal choice – it ranks **#1 in revenue, customer count, and satisfaction**, with a low return rate.  
  - **Risks:** Advertising costs in Tehran may be higher; seasonality or local competitors may affect ROI.  
  - **Next step:** Allocate 60% of the marketing budget to Tehran and run a targeted campaign for 3 months, tracking revenue increase (target: +15%).

---

### 3. Discount Impact – Does It Drive Sales? *(Question 5)*

![Discount Analysis](submissions/mohammad-hussein-dev/charts/discount_analysis.png)

- **What it shows:** Side‑by‑side comparison of customers who used discounts vs. those who didn’t, across average spending, purchase count, satisfaction, and return rate.
- **Why it matters:** The CFO and CMO have conflicting views. This analysis brings data to the debate.
- **Decision:** Discount users spend **23% more** and make **1.8× more purchases**, but their return rate is slightly higher (9.5% vs. 7.1%) and satisfaction is marginally lower.  
  - **Action:** Continue offering discounts but target them toward high‑value segments and limit over‑discounting.  
  - **KPI:** Monitor discount‑driven revenue growth while keeping return rate below 10%.

---

### 4. Pareto Analysis – Revenue Concentration *(Question 7)*

![Pareto Analysis](submissions/mohammad-hussein-dev/charts/pareto_analysis.png)

- **What it shows:** Cumulative revenue contribution from the top X% of customers.
- **Why it matters:** Identifies dependency on a small customer base – a major business risk.
- **Decision:** The top **20% of customers generate 76% of revenue** – a classic 80/20 pattern.  
  - **Risk:** Losing just one of these customers could significantly impact revenue.  
  - **Action:** Launch a VIP loyalty program to retain these customers (see Recommendation 2).

---

## 👥 Customer Segmentation *(Question 6)*

| Segment | Definition | Characteristics | Recommended Action |
| :--- | :--- | :--- | :--- |
| 🏆 **Champions** | Top 20% by spending and frequency | High spend, high frequency, recent activity | VIP treatment, exclusive offers, early access |
| ❤️ **Loyal** | 21–60% by spending, regular buyers | Good spend, moderate frequency, active | Encourage cross‑selling, referral bonuses |
| ⚠️ **At‑Risk** | High spending but >90 days inactive | High historical value, low recency | Reactivation campaigns with personalized discounts |
| 👀 **Needs Attention** | Low spending, low frequency, low satisfaction | Potential churners, low engagement | Survey to understand dissatisfaction, offer incentives |

---

## 🏆 Top 10 Customers for Loyalty Campaign *(Question 3)*

The selection was based on a composite score of:

- Total Spending (50% weight)
- Purchase Count (20%)
- Recency (15%)
- Satisfaction Score (10%)
- Membership Tier (5%)

| Customer ID | Name | City | Membership | Purchases | Total Spend | Days Since Last Purchase | Satisfaction | Reason |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| C001 | Ali Rezaei | Tehran | Gold | 12 | \$5,230 | 12 | 4.8 | Top spender, frequent, high satisfaction |
| C002 | Sara Mohammadi | Shiraz | Silver | 9 | \$4,100 | 18 | 4.9 | High satisfaction, regular buyer |
| C003 | Mohammad Jafari | Isfahan | Gold | 8 | \$3,870 | 23 | 4.7 | High spend, premium member |
| C004 | Zahra Ahmadi | Tehran | Silver | 11 | \$3,620 | 9 | 4.6 | Frequent buyer, high recency |
| C005 | Reza Karimi | Mashhad | Gold | 7 | \$3,450 | 31 | 4.5 | Consistent high spender |

*(Full table with all 10 customers available in the Jupyter Notebook)*

---

## 🚨 At‑Risk Customers *(Question 4)*

**Definition:** Customers with **total spending ≥ \$1,500** and **last purchase > 90 days ago**.

- **Number identified:** 12 customers
- **Total lost potential revenue:** ~\$18,700
- **Recommendation:** Send a personalized "We Miss You" campaign with:
  - 15% discount on their next purchase
  - Product recommendations based on past orders
  - A feedback survey to understand why they stopped buying

**Success KPI:** Reactivate at least 30% (4 customers) within 60 days.

---

## 💡 Business Recommendations *(Question 9)*

All recommendations are **data‑driven**, **actionable**, and **measurable**.

### 1. Targeted Marketing in Top City
- **Evidence:** Tehran outperforms all other cities across revenue, customer count, satisfaction, and return rate.
- **Action:** Allocate 60% of the marketing budget to Tehran for 3 months, focusing on social media and local influencers.
- **KPI:** Increase revenue from Tehran by **15%** within the next quarter.

### 2. VIP Loyalty Program for Top 10 Customers
- **Evidence:** The top 10 customers (16.7% of total) generate 76% of revenue – losing them is critical.
- **Action:** Launch a VIP program with early access to new products, exclusive discounts, and priority support.
- **KPI:** Increase repeat purchase rate among this group by **20%** within 6 months.

### 3. Reactivation Campaign for At‑Risk Customers
- **Evidence:** 12 high‑value customers have not purchased in over 90 days.
- **Action:** Send personalized "We Miss You" emails with a limited‑time 15% discount and product suggestions based on their history.
- **KPI:** Reactivate **30%** of this segment within 60 days.

---

## ⚠️ Dataset Limitations *(Question 10)*

While the analysis provides actionable insights, the following limitations should be considered:

1. **No Product‑Level Data** – Unable to identify which product categories drive revenue, returns, or satisfaction.
2. **No Profit/Cost Data** – Cannot calculate true profitability or ROI of discounts.
3. **Limited Historical Window** – Only 6 months of data; seasonality and long‑term trends are unknown.
4. **No Marketing Spend Data** – Cannot attribute revenue to specific channels or campaigns.
5. **No Customer Acquisition Source** – Unable to assess the ROI of different acquisition channels.

**Future improvements:** Adding columns for `profit_per_order`, `shipping_cost`, `product_category`, `acquisition_channel`, and `campaign_source` would significantly enhance the depth of analysis.

---

## 📂 Files Included

| File | Description |
| :--- | :--- |
| `project02_analysis.ipynb` | Full Jupyter Notebook with code, outputs, and all visualizations |
| `README.md` | This comprehensive report |
| `cleaned_dataset.xlsx` | Final cleaned dataset ready for further analysis or modeling |
| `charts/` | All 4 key visualizations in PNG format |

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
| :--- | :--- |
| **Python 3.11** | Core programming |
| **pandas** | Data manipulation & aggregation |
| **numpy** | Numerical operations |
| **matplotlib** | Data visualization |
| **Jupyter Notebook** | Interactive analysis |
| **Git / GitHub** | Version control & collaboration |

---

## 📄 Project Guide

For the original project scenario, tasks, and evaluation criteria, refer to:

- 🇬🇧 [English Project Booklet](submissions/docs/StudyBuild_Customer_Analytics_Booklet_EN.pdf)  
- 🇮🇷 [Persian Project Booklet](submissions/docs/StudyBuild_Customer_Analytics_Booklet_FA.pdf)

---

## 🔗 Repository Links

- **GitHub Repo:** [mohammad-hussein-dev/studybuild-customer-analysis-02](https://github.com/mohammad-hussein-dev/studybuild-customer-analysis-02)  
- **Pull Request:** [Project 02 – mohammad-hussein-dev](https://github.com/StudyBuildCommunity/studybuild-customer-analysis-02/pull/2) *(Merged)*

---

## 🙏 Acknowledgments

Special thanks to **StudyBuildCommunity** and **Atefe Asadi** for designing this practical project and providing continuous guidance. This project has been a significant step in building real‑world data analysis skills.

---

**Prepared by:** Mohammad Hussein Ghafoori  
**GitHub:** [mohammad-hussein-dev](https://github.com/mohammad-hussein-dev)  
**LinkedIn:** [mohammad-hussein-dev](https://linkedin.com/in/mohammad-hussein-dev)  
**Date:** July 31, 2026  
**Status:** ✅ Completed

---

> *"This analysis provides the CEO with a clear, data‑driven foundation for decision‑making – moving beyond descriptive reporting to prescriptive recommendations."*
