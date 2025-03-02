
# Portfolio: Retail Sales Insights

# Table of Contents
-	[Objective](#objective)
-	[Data Source](#data-source)
-	[Stages](#stages)
-	[Design](#design)
-	[Mockup](#dashboard-mockup)
-	[Tools](#tools) 
-	[Development](#development)
-	[Pseudocode](#pseudocode)
-	[Data Cleaning](#data-cleaning)
-	[Data Quality Checks](#data-quality-checks)
-	[Visualization](#visualization)
-	[Results](#results)
-	[Key Metrics](#key-metrics-&-insights)
-	[DAX Measures](#dax-measures)
-	[Analysis](#analysis)
-	[Findings](#findings)
-	[Validation](#validation)
-	[Discovery](#discovery)
-	[Recommendations](#recommendations)
-	[Potential ROI](#potential-roi)
-	[Potential Courses of Action](#potential-courses-of-action)
-	[Conclusion](#conclusion)

# Objective

- #### Key Pain Point?

To analyze supermarket sales data, identify trends, and provide actionable insights into revenue, customer behavior, and branch performance.

**Ideal Solution?**

To develop a Power BI dashboard that offers deep insights into sales trends, customer purchasing behavior, and product performance to support data-driven decision-making.

## User Story

As a Business Analyst, I need a comprehensive dashboard to analyze sales trends, customer behavior, and product performance, allowing the company to optimize its business strategy and increase revenue.

### 1. Data Understanding

# Dataset Overview
#### The dataset contains:

- **Invoice Details:** Unique transaction records.
- **Branch & City Information:** Location of transactions.
- **Customer Demographics:** Type (Member/Normal) and gender.
- **Product Line:** Categories of purchased items.
- **Sales Metrics:** Quantity, tax, total revenue.
- **Payment Method:** Cash, E-wallet, Credit card.

### Data Source
The data is sourced from an [Excel extract](https://www.kaggle.com/datasets/mohamedelaziz/supermarket-sales), with influencer performance metrics collected for analysis.


# Stages
-	Design
- Development
- Testing
- Analysis

   
# Design
### Dashboard Components Required
-	Key Business Questions Answered:
1.	What are the total sales revenue and profit?
2.	Which branches generate the most revenue?
3.	Which products are the best sellers?
4.	What are the key sales trends over time?
5.	Who are the top customers by spending?

### Dashboard Visuals:
1.	KPI Scorecards (Total Sales, Profit, Revenue Growth)
2.	Sales Trend Analysis (Line Charts)
3.	Store Performance (Bar Charts, Heatmaps)
4.	Product Performance (Treemaps, Tables)
5.	Customer Analysis (Pie Charts, Segmentations)
   
## Dashboard mockup
The dashboard layout follows best practices for usability, featuring:
-	A clean, intuitive layout
-	Filters and slicers for dynamic analysis
-	Visual elements highlighting key insights


### Tools
|Tool|	Purpose|
|-|-|
|Power BI|	Data Visualization|
|Excel	|Initial Data Exploration|
|GitHub|	Project Documentation & Version Control|

# Development
### Pseudocode
- What's the general approach in creating this solution from start to finish?
  
1.	Load data from Kaggle to Excel into Power BI.
2.	Clean the data (handle missing values, correct data types, etc.).
3.	Create relationships between tables for accurate reporting.
4.	Develop Power BI visuals and dashboards.
5.	Apply DAX measures for KPI calculations.
6.	Perform testing and validation.
7.	Publish dashboard and document insights.

### Data Cleaning
- This is the stage where you have a scan of what's in the data, errors, inconcsistencies, bugs, weird and corrupted characters etc
-	Removed null values in key performance fields.
-	Ensured all columns have appropriate data types.
-	Checked for and removed duplicate records.
-	Retained only relevant columns.

# Testing
# Data Quality Checks
**1. Row Count Check:** Validate the total number of transactions.

**2. Column Count Check:** Ensure all required fields are present.

**3. Data Type Validation:** Confirm correct formats for numerical and categorical fields.

**4. Missing & Duplicate Checks:**
- Identify null/missing values.
- Remove duplicate transactions.


# Visualization
### Results
- What does the dashboard look like?
  
  [Retail Sales Insights.pdf](https://github.com/user-attachments/files/19044742/Retail.Sales.Insights.pdf)

1.	Total Revenue & Profit Trends
2.	Top-Selling Products by Revenue & Quantity
3.	Customer Segmentation & Buying Patterns
4.	Branch Performance Analysis


# Key Metrics & Insights
## A. Sales Performance Analysis
- **Total Revenue:** £322.97K
- **Total Sales Quantity:** 5.51K items
- **Gross Income:** £15.38K
- **Cost of Goods Sold (COGS):** £307.6K


# DAX Measures

### 1. Total Sales
```sql
Total Sales = SUM(sales_summary[Total_Sales])
```
### 2. Total Profit
```sql
Total Profit = SUM(sales_summary[Total_Profit])
```
### 3. Average Sales per Transaction
```sql
Avg Sales per Transaction = DIVIDE([Total Sales], COUNT(sales_summary[Total_Transactions]))
```
### 4. Profit
```sql
Profit = SUM('Retail Sales Insights'[Total]) - SUM('Retail Sales Insights'[COGS])
```

## Calculated Column

### 1. Sales Hour
```sql
Hour = HOUR('Retail Sales Insights'[Time])
```
### 2. Time of the Day
```sql
TimeoftheDay = 
SWITCH(
    TRUE(),
    'Retail Sales Insights'[Hour] >= 6 && 'Retail Sales Insights'[Hour] < 12, "Morning",
    'Retail Sales Insights'[Hour] >= 12 && 'Retail Sales Insights'[Hour] < 18, "Afternoon",
    'Retail Sales Insights'[Hour] >= 18 && 'Retail Sales Insights'[Hour] < 24, "Evening",
    "Night"
)
```

### Analysis Approach:
- Calculate **total revenue per product line**.
- Identify the **highest and lowest revenue-generating categories**.
- Compute **gross margin %** to evaluate profitability per category.

|Product Line	|Total Revenue (£)	|% of Total Sales|
|-|-|-|
|Food and Beverages|	56,144.84|	17.4%|
| Sports and Travel|	55,122.83	|17.1%|
| Electronic Accessories|	54,337.53|	16.8%|
| Fashion Accessories	|54,305.90	|16.8%|
| Home and Lifestyle	|53,861.91|	16.7%|
| Health and Beauty|	49,193.74	|15.2%|

🔹 Insight: Food & Beverages and Sports & Travel are the top revenue-generating categories.
  
### Output
![image](https://github.com/user-attachments/assets/42a27de8-7aee-479e-b2a5-8a8b16716753)


## B. Customer Analysis
**Spending Behavior**
- **Average Transaction Value per Customer Type**:

 - **Members**: £328 per transaction
 - **Normal Customers:** £318 per transaction
 - **Members spend slightly more per purchase**.
   
- **Gender-based Sales Distribution:**

 - **Female Customers**: 51.98%
 - **Male Customers:** 48.02%
 - **Almost equal split in purchasing behavior**.
🔹 **Insight**: Membership customers contribute higher per-transaction revenue, suggesting that **loyalty programs** are effective.

**Peak Shopping Times**
|Time of Day|	Transaction Count|
|-|-|
|Morning|	191|
|Afternoon|	359.5|
|Evening	|528|

🔹 **Insight**: The highest number of transactions occurs in the **evening,** suggesting the need for **targeted promotions and staffing adjustments**.

# C. Branch Performance
**Revenue & Profitability by Branch**

|Branch|	Total Revenue (£)|	Profit (£)|
|-|-|-|
|C|	110.57K|	5.27K|
|A|	106.20K|	5.06K|
|B|	106.20K|	5.06K|

🔹 **Insight**: **Branch C has the highest revenue and profit.** Further investigation is needed into:

- **Customer demographics** at each branch.
- **Product line popularity** per branch.
- **Operational efficiencies** in high-performing locations.

  
# D. Payment Method Analysis
|Payment Method|	Total COGS (£)|
|-|-|
|Cash|	106.86K|
|E-Wallet	|104.76K|
|Credit Card	|95.97K|

🔹 **Insight: Cash is the most preferred payment method**, indicating potential for increased digital payment adoption.

### Output
![image](https://github.com/user-attachments/assets/855ac6a6-8ac0-42c5-8c71-f723f268c55a)





### Validation & Discovery
•	Revenue trends showed seasonal fluctuations, with peak sales in January.
•	Certain product categories had high returns (Food and Beverages), impacting profitability.

# Recommendations
#### A. Optimize Product Strategy
- **Increase stock and marketing** for high-selling categories like **Food & Beverages and Sports & Travel**.
- **Analyze lower-performing categories** (Health & Beauty) to improve sales strategies.

#### B. Improve Customer Engagement
- Enhance membership programs to capitalize on the higher spending of members.
- Run evening-specific promotions to maximize revenue during peak shopping hours.

#### C. Branch-Level Strategy
- Leverage insights from Branch C’s success to improve performance at Branches A & B.
- Evaluate branch-specific product demand to optimize inventory distribution.

#### D. Digital Payment Adoption
Encourage E-wallet and Credit Card usage through discounts and cashback offers.


#### Potential ROI & Action Plan
-	Implementing these insights is projected to increase revenue by 10-15%.
-	Next Steps:
1.	Roll out customer engagement initiatives.
2.	Adjust inventory strategies based on sales performance.
3.	Continue refining the dashboard with new KPIs.

## Conclusion
The Power BI dashboard provides critical insights into sales trends, customer behavior, and branch performance. By leveraging data-driven decisions, the company can optimize its strategy to improve revenue and customer satisfaction.



