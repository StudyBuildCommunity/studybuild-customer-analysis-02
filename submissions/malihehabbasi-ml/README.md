# Project 02 - Customer Behavior Analysis

## Project Title

**Customer Behavior Analysis**

## Business Problem

The goal of this project was to use the cleaned customer dataset from Project 01 to answer several practical business questions.

The company wants to make better decisions about:

- where to spend its marketing budget
- which customers are most valuable
- which customers may be at risk of leaving
- whether discounts are associated with higher sales
- how customers can be segmented
- where the main revenue opportunities and risks are

The main idea of this project was not only to calculate numbers or create charts. The goal was to connect the results to possible business decisions.

---

## Dataset Description

The analysis was performed using the cleaned customer dataset produced in Project 01.

The final analysis dataset contains:

- **60 customers**
- **18 columns**

The dataset contains customer information such as:

- Customer ID
- First name
- Gender
- Age
- City
- Province
- Signup date
- Membership tier
- Purchase count
- Average order value
- Total spending
- Days since last purchase
- Payment method
- Device
- Discount usage
- Returned items
- Satisfaction score
- Inferred gender

The dataset is customer-level rather than transaction-level, so the analysis focuses mainly on customer behavior and summarized purchasing activity.

---

## Tools and Libraries

The project was completed using Python and Jupyter Notebook.

Main libraries:

- pandas
- NumPy
- Matplotlib

The cleaned data from Project 01 was used as the input for this analysis.

---

# Analysis Steps

## 1. Overall Customer and Sales Status

The first step was to calculate the main management KPIs.

### Results

| Metric | Result |
|---|---:|
| Total customers | 60 |
| Total purchases | 1,060 |
| Total revenue | 203,068.12 |
| Average spending per customer | 3,384.47 |
| Average purchase value | 191.57 |
| Average satisfaction | 2.98 / 5 |
| Return rate | 23.68% |

The store generated more than 203k in total spending across 60 customers.

The average satisfaction score was about 2.98 out of 5, which means there is clear room for improving customer experience.

The return rate of 23.68% is also important. It means that returned items represent a relatively large part of the purchasing activity and should not be ignored when making growth decisions.

---

## 2. Choosing One City for the Marketing Budget

The city comparison considered:

- number of customers
- number of purchases
- total revenue
- average spending
- customer satisfaction
- return rate

A simple normalized score was created from these six indicators so that the decision was not based only on total revenue.

### Selected city: Mashhad

Mashhad received the highest overall city score:

- City score: **0.831**
- Customers: **11**
- Purchases: **249**
- Revenue: **43,197.58**
- Average spending per customer: **3,927.05**
- Satisfaction: **2.91**
- Return rate: **11.65%**

Mashhad also had the highest total revenue among the analyzed cities and the highest number of purchases.

One important reason for selecting Mashhad is the relatively low return rate compared with most other cities. This gives the city a stronger overall profile instead of relying only on revenue.

### Decision

If the company can choose only one city for a marketing campaign, **Mashhad is the strongest choice based on the scoring approach used in this project**.

### Risk

The main limitation is that the score uses equal weights for the six indicators. A different weighting strategy could produce a different ranking.

---

## 3. Top 10 Customers for the Loyalty Campaign

A loyalty score was created using:

- total spending
- purchase count
- recency
- satisfaction

The weights were:

- 40% spending
- 30% purchase frequency
- 20% recency
- 10% satisfaction

The top 10 customers were then selected using this score.

The selected customers were:

| Customer ID | Name | City | Membership | Purchases | Total Spending | Days Since Last Purchase | Satisfaction |
|---|---|---|---|---:|---:|---:|---:|
| 1057 | Maryam | Ahvaz | Bronze | 31 | 13,532.74 | 82 | 4 |
| 1044 | Mina | Shiraz | Gold | 33 | 14,354.34 | 165 | 2 |
| 1009 | Kimia | Karaj | Silver | 34 | 11,615.42 | 232 | 2 |
| 1059 | Ali | Isfahan | Gold | 31 | 8,898.55 | 224 | 5 |
| 1012 | Arash | Mashhad | Gold | 27 | 11,731.50 | 224 | 2 |
| 1004 | Sina | Mashhad | Gold | 23 | 6,121.45 | 40 | 4 |
| 1033 | Neda | Tabriz | VIP | 24 | 5,521.20 | 112 | 5 |
| 1014 | Reza | Tabriz | VIP | 31 | 3,353.89 | 97 | 4 |
| 1023 | Ali | Mashhad | Bronze | 31 | 3,851.44 | 170 | 4 |
| 1017 | Parsa | Ahvaz | VIP | 30 | 3,239.40 | 135 | 4 |

These customers were selected because they combine high spending and/or frequent purchases with relatively good recent activity and satisfaction.

One important observation is that not all top customers are currently highly satisfied. This means that a loyalty campaign should not only reward them but also monitor their experience.

---

## 4. Customers at Risk of Churn

For this analysis, a customer was considered at risk when both conditions were true:

- total spending was in the top 25%
- days since the last purchase was also in the top 25%

The thresholds were:

- Spending threshold: **4,213.12**
- Inactivity threshold: **273.75 days**

This produced **3 at-risk customers**:

| Customer ID | Name | City | Spending | Days Since Last Purchase | Satisfaction |
|---|---|---|---:|---:|---:|
| 1010 | Arash | Karaj | 7,241.47 | 276 | 1 |
| 1035 | Arash | Tabriz | 5,918.21 | 365 | 3 |
| 1053 | Sina | Tehran | 5,805.54 | 320 | 1 |

These customers are important because they have already generated relatively high revenue but have not purchased for a long time.

### Recommendation

The company should create a targeted win-back campaign for these customers.

The campaign should be more personalized than a general discount campaign and should focus on bringing these customers back before they are completely lost.

A useful KPI would be the **reactivation rate**, measured as the percentage of at-risk customers who make another purchase after the campaign.

---

## 5. Discount Analysis

Customers who used discounts were compared with customers who did not.

| Metric | No Discount | Discount Used |
|---|---:|---:|
| Customers | 34 | 26 |
| Average spending | 3,768.58 | 2,882.17 |
| Average purchase count | 17.79 | 17.50 |
| Average satisfaction | 2.76 | 3.27 |
| Return rate | 23.97% | 23.30% |

The customers who did not use discounts had higher average spending:

**3,768.58 vs 2,882.17**

The average purchase count was also slightly higher for the non-discount group:

**17.79 vs 17.50**

Discount users had higher average satisfaction:

**3.27 vs 2.76**

Their return rate was slightly lower:

**23.30% vs 23.97%**

### Interpretation

Based on this dataset, there is **no evidence that discounts increased sales**.

In fact, the non-discount group had higher average spending and slightly higher purchase frequency.

However, this analysis is descriptive and does not prove that discounts reduce spending. Customers who use discounts may already be different from customers who do not use them.

A controlled experiment or additional customer-level information would be needed to estimate the causal effect of discounts.

---

## 6. Customer Segmentation

Customers were segmented using simple rule-based conditions based on:

- total spending
- purchase count
- recency

The final segments were:

| Segment | Customers | Revenue | Average Spending | Avg. Purchases | Avg. Satisfaction | Avg. Days Since Last Purchase |
|---|---:|---:|---:|---:|---:|---:|
| Potential Growth | 35 | 109,446.03 | 3,127.03 | 17.46 | 3.17 | 173.54 |
| Loyal Customers | 7 | 31,039.31 | 4,434.19 | 26.57 | 3.57 | 123.71 |
| Champions | 2 | 27,887.08 | 13,943.54 | 32.00 | 3.00 | 123.50 |
| At Risk | 3 | 18,965.22 | 6,321.74 | 18.00 | 1.67 | 320.33 |
| Needs Attention | 13 | 15,730.48 | 1,210.04 | 11.15 | 2.46 | 289.85 |

### Interpretation

**Champions** are the smallest but highest-value group. Only 2 customers are in this segment, but their average spending is almost 14k.

**Loyal Customers** show strong repeat purchasing and relatively good satisfaction.

**At Risk** customers have high spending but very long inactivity and the lowest average satisfaction among the high-value groups. They deserve immediate retention attention.

**Needs Attention** customers have lower spending, fewer purchases, long inactivity, and lower satisfaction. They should receive low-cost engagement campaigns before the company invests heavily in them.

The largest group is **Potential Growth**, with 35 customers. This group represents a large opportunity because improvements in purchasing frequency or spending could produce a meaningful revenue increase.

---

## 7. Pareto Analysis

The top 20% of customers were used to measure revenue concentration.

There are 60 customers, so the top 20% contains **12 customers**.

These 12 customers generate:

**50.73% of total revenue**

### Interpretation

The dataset does not follow a classic 80/20 pattern.

The top 20% of customers generate about half of the revenue rather than 80%.

This means that revenue is concentrated to some degree, but the company is not completely dependent on a very small group of customers.

The risk is therefore lower than in a very concentrated 80/20 situation, but high-value customers should still be protected because losing them can have a noticeable effect on revenue.

---

# Three Main Management Charts

For a short management presentation, the three most useful charts from this analysis are:

### 1. Revenue by City

This chart supports the decision about where to allocate the marketing budget.

Mashhad has the highest total revenue and the strongest combined city score.

### 2. High-Value Customers at Risk

This chart highlights customers who have high historical spending but have been inactive for a long time.

It helps management focus retention efforts instead of treating every customer equally.

### 3. Customer Segment Distribution

This chart shows the size of each behavioral group.

It is especially useful because the largest group is Potential Growth, while the high-value Champions group is very small.

---

# Business Recommendations

## Recommendation 1 - Focus the first marketing test on Mashhad

### Evidence

Mashhad received the highest city score of **0.831** and generated **43,197.58** in revenue with **249 purchases** and a return rate of only **11.65%**.

### Action

Run the first targeted marketing campaign in Mashhad and use this campaign as a controlled test.

### KPI

Track:

- campaign revenue
- number of purchases
- new or reactivated customers
- return rate
- customer satisfaction

---

## Recommendation 2 - Run a targeted win-back campaign for high-value inactive customers

### Evidence

Only **3 customers** meet the at-risk definition, and each has high historical spending combined with more than 273 days since the last purchase.

### Action

Contact these customers with personalized offers or service recovery messages instead of sending a general promotion to the whole customer base.

### KPI

Track:

- reactivation rate
- repeat purchase rate
- recovered revenue
- satisfaction after reactivation

---

## Recommendation 3 - Do not increase discounts for all customers

### Evidence

Customers who used discounts had lower average spending:

**2,882.17 vs 3,768.58**

The non-discount group also had slightly higher average purchase frequency.

### Action

Instead of giving discounts to everyone, test targeted discounts for selected segments and compare their results with a control group.

### KPI

Track:

- incremental revenue
- purchase frequency
- return rate
- profit per campaign

---

# Dataset Limitations

There are several limitations that should be considered before making strong business decisions.

1. The dataset is relatively small, with only 60 customers.

2. The data is customer-level rather than transaction-level, so detailed product and order analysis is not possible.

3. Profit information is not available. High spending does not necessarily mean high profit.

4. Shipping cost is not available.

5. Exact order dates are not available, so detailed monthly or weekly sales trends cannot be analyzed.

6. Product category information is not available.

7. Customer acquisition source is not available.

8. Advertising cost is not available, so marketing return on investment cannot be calculated.

9. The discount analysis is observational. Differences between the two groups do not prove that discounts caused differences in spending.

Useful additional columns would include:

- profit per order
- shipping cost
- product category
- exact order date
- customer acquisition source
- advertising cost
- membership date
- order-level transaction data

---

# Conclusion

The analysis shows that the company has a customer base of 60 customers and total recorded spending of 203,068.12.

The main findings are:

- **Mashhad** is the strongest city for the single-city marketing budget under the scoring method used.
- **10 customers** were selected for the loyalty campaign using a weighted value and engagement score.
- **3 customers** were identified as high-value and inactive enough to be considered at risk of churn.
- Customers who used discounts had lower average spending than customers who did not use discounts, so the current data does not support a simple claim that discounts increase sales.
- **Potential Growth** is the largest segment with 35 customers, which represents a large opportunity for increasing engagement.
- The top 20% of customers generate **50.73% of revenue**, so revenue concentration exists but does not follow a strict 80/20 pattern.

The most important point is that the analysis gives the company several specific areas to act on: focus the first marketing test on Mashhad, protect valuable inactive customers, and use targeted rather than universal discounts.

## Author

Maliheh Abbasi

## Date

August 2026
