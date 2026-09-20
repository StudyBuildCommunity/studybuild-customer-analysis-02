# Project-02-Customer-Analysis

## Analyzing Customer Behavior for Business Insights

---
[![Python](https://img.shields.io/badge/Python-3.12%2B-blue.svg)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)

In this project, we analyze customer behavior using the cleaned data prepared in the previous project. The analysis focuses on answering key business questions, identifying meaningful patterns in customer behavior, and generating actionable insights to support data-driven decision-making.

---

## Project Overview

### Business Context
The company wants to better understand its customers' purchasing behavior in order to identify important patterns, discover business opportunities, and support data-driven decision-making.

### Objective
The main objective of this project is to:

- Analyze customer purchasing behavior
- Identify meaningful patterns and trends
- Discover potential business problems and opportunities
- Answer key business questions
- Generate actionable insights to support better decision-making

### Target Audienc

This analysis is intended for:

- Chief Executive Officer (CEO)
- Sales and Marketing Teams
- Technical and Data Teams

---

## Business Questions

This project attempts to answer the following questions:

1. Who are the store's customers?
2. Which cities show the greatest potential for future marketing investment?
3. Which customers should be prioritized for the loyalty program?
4. How are discounts, device types, and payment methods associated with customer purchasing behavior?
5. Which high-value customers may be at risk of becoming inactive?

---

## Dataset

### Dataset Description

The dataset contains information about [total_spending, purchase_count, last_purchase_days, memebership_tier, etc.].
- **Source:** StudyBulid
- **Dataset purpose:** Educational
- **Number of rows:** 60
- **Number of columns:** 17
- **Unit of analysis:** Each row represents one customer


### Data Dictionary

| Column | Description | Data Type |
|---|---|---|
| `customer_id` | Unique identifier assigned to each customer. | Integer |
| `first_name` | Customer's first name. | Text |
| `gender` | Customer's gender. | Categorical |
| `age` | Customer's age in years. | Integer |
| `city` | Customer's city of residence. | Categorical |
| `province` | Customer's province or region of residence. | Categorical |
| `signup_date` | Date on which the customer registered. | Date |
| `membership_tier` | Customer's membership or loyalty-program level. | Categorical |
| `purchase_count` | Total number of recorded purchases made by the customer. | Integer |
| `avg_order_value` | Average monetary value of the customer's orders in USD. | Numeric |
| `total_spending` | Total recorded spending by the customer in USD. | Numeric |
| `last_purchase_days` | Number of days since the customer's most recent purchase, calculated as of the data reference date. | Integer |
| `payment_method` | Payment method used by the customer. | Categorical |
| `device` | Device used by the customer to make purchases. | Categorical |
| `discount_used` | Indicates whether the customer used a discount. | Boolean |
| `returned_items` | Number of items returned by the customer from 1 to 5. | Integer |
| `satisfaction_score` | Customer satisfaction score based on the available rating scale. | Numeric |



### Data Quality Checks

The following checks were performed:
- Missing values : None
- Duplicate records : None
- Invalid or negative values : None
- Incorrect data types : None
- Outliers : None
- Inconsistent or negative values : None
- Incorrect data types : None
- Inconsistent Data Quality Results : None

---


## Tools and Technologies

The project was developed using:
- Python
- Pandas
- Matplotlib
- Seaborn
- Jupyter Notebook


---

## Analysis Workflow

The analysis followed these main steps:
Data cleaning and preprocessing were completed in the previous project. In this project, the cleaned dataset was used to analyze customer behavior and answer the defined business questions.

1. Loading the cleaned dataset.
2. Reviewing the dataset structure and available variables.
3. Exploring customer characteristics and purchasing behavior.
4. Comparing customer behavior across relevant groups.
5. Creating visualizations to present the main findings.
6. Interpreting the results in a business context.
7. Summarizing the key insights and potential next steps.


### 1. Data Preparation

Data cleaning and preprocessing were completed in the previous project. This project uses the cleaned customer-level dataset as its starting point and does not repeat the data-cleaning process.

The cleaned dataset was loaded and reviewed to confirm its structure, available variables, and suitability for customer behavior analysis.

The dataset structure was reviewed by checking the number of rows and columns, data types, missing values, and the available customer-level metrics.


### 2. Feature Engineering

The analysis used:
- Group-by analysis
- Distribution analysis
- Cohort analysis
- RFM analysis
- Customer segmentation
- Hypothesis testing

## Metric Definitions

The main metrics are defined as follows:

| Metric | Definition | Formula | Unit | Notes |
|---|---|---|---|---|
| Customer Count | Number of unique customers included in the dataset. | `COUNT(DISTINCT customer_id)` | Customers | Each row represents one customer. |
| Average Recorded Spending per Customer | Total recorded customer spending divided by the number of unique customers in the analyzed dataset or group. | `SUM(total_spending) / COUNT(DISTINCT customer_id)` | Currency units per customer | Describes spending for customers represented in the data. It should not be interpreted as period-specific ARPU unless the revenue definition, user population, and reporting period are established. |


---
## Key Performance Indicators

| KPI | Value | Interpretation |
|---|---:|---|
| Total Customers | `60` | Size of the analyzed customer base. |
| Total Recorded Spending | `201986` | Total customer spending recorded in the dataset. |
| Average Customer Spending | `3366` | Average spending per customer. |
| Discount Usage Rate | `43.33%` | Share of customers who used a discount. |
| Inactive Customer Rate | `25.00%` | Share of customers exceeding the defined inactivity threshold. |

---
## Key Findings


### Finding 1: Customer Profile Overview

- Customers aged **56 and above** form the largest age group in the dataset.
- Male customers account for **58.33%** of the customer base.
- **Gold** is the most common membership tier, representing **31%** of customers.
- **Android** is the most common recorded device category, accounting for **36%** of customers.
- **Online Wallet** is the most common recorded payment method, associated with **38.33%** of customers.

### Finding 2: Customer Behavior by City

**Isfahan** with 5 customers representing 8.33% of the total customer base, stands out in the analyzed dataset for :

- The highest average spending per customer: $4,395, approximately 30.1% higher than the overall average of $3,377.

- The highest average customer satisfaction score: 4.4 out of 5, which is 1.42 points higher than the overall average of 2.98.

- Given the small number of customers in Isfahan, these findings should be interpreted with caution and may not represent the behavior of all customers in the city.


**Tabriz** with 12 customers, representing 20% ​​of the total customer base stands out in the analyzed dataset for :

- The average number of days since their last purchase is 227, whereas the estimated figure for the entire customer base is 198 days. This indicates that customers in Tabriz have been inactive for approximately 29 days longer than the overall average


**Mashhasd** had 11 customers, representing 18.33% of the total customer base, and recorded the highest total spending among all cities at $43,197. However, its average spending per customer was $3,927, approximately 10.6% lower than Isfahan’s $4,395. This indicates that Mashhad’s leading position in total spending was mainly driven by its larger customer base rather than higher spending per customer.



## Limitations

This project has the following limitations:
- **Small dataset:** The dataset contains only 60 customers. Findings should therefore be treated as exploratory and may not generalize to a broader customer population.
- **Observational data:** The analysis is based on observed customer attributes and behaviors rather than a controlled experiment. Therefore, the results indicate associations and do not establish causal relationships.
- **Aggregated customer-level data:** Each row represents a customer rather than an individual transaction. This limits the ability to analyze purchase timing, transaction-level behavior, customer journeys, and changes in behavior over time.
- **Inactivity proxy:** Inactivity is defined using a threshold for `last_purchase_days`. This is an operational proxy and does not confirm customer churn or permanent loss of a customer.


---

## 📁 Repository Structure
```text
ali-ashrafi/
│
├── .gitignore
├── requirements.txt
├── README.md
│
├── data/
│   ├── raw/
│   │   └── first_dataset.xlsx
│   └── processed/
│       └── cleaned_customers.xlsx
│
└── notebooks/
└── 01_data_cleaning_ali-ashrafi.ipynb
```
---

## 🚀 Quickstart & Reproducibility

**1. Clone the Repository**

```bash
git clone https://github.com/<your-username>/ecommerce-data-cleaning.git
cd ecommerce-data-cleaning
```


**2.Environment Setup**


```bash
#Create a virtual environment
python -m venv venv
```
```bash
#Activate the virtual environment

#On Linux / WSL:
source venv/bin/activate

#On Windows (PowerShell):
.\venv\Scripts\Activate.ps1
```
```bash
#Install exact locked dependencies
pip install -r requirements.txt
```

**3. Run the Pipeline**
Launch Jupyter Lab/Notebook and execute the cleaning workflow:

```bash
jupyter notebook notebooks/cleaned_dataset_ali_ashrafi.ipynb
```

## Getting Started

```bash
# 1. Create and activate a virtual environment
python -m venv .venv
source .venv/bin/activate        # Linux / macOS
.venv\Scripts\activate           # Windows

# 2. Install dependencies
pip install -r requirements.txt

# 3. Launch Jupyter Lab
jupyter lab notebook/analysis_notebook_clean.ipynb
```


## 🛠️ Built With 
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white)


## 👤 Author & Contact
  * 🐙 **GitHub:** [@ali-ashrafi](https://github.com/ali-ashrafi)
  * ✉️ **Email:** [eng.a.ashrafi@gmail.com](mailto:your.email@gmail.com)
  * 📍 **Location:** Iran *(Open to Relocation / Remote)*







