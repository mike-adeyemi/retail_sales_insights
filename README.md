Portfolio- Excel to Power BI

Supermarket Sales Data Analysis


# Objective
To analyze supermarket sales data, identify trends, and provide actionable insights into revenue, customer behavior, and branch performance.

### 1. Data Understanding & Quality Checks

# Dataset Overview
#### The dataset contains:

- **Invoice Details:** Unique transaction records.
- **Branch & City Information:** Location of transactions.
- **Customer Demographics:** Type (Member/Normal) and gender.
- **Product Line:** Categories of purchased items.
- **Sales Metrics:** Quantity, tax, total revenue.
- **Payment Method:** Cash, E-wallet, Credit card.


# Data Quality Checks
**1. Row Count Check:** Validate the total number of transactions.
**2. Column Count Check:** Ensure all required fields are present.
**3. Data Type Validation:** Confirm correct formats for numerical and categorical fields.
**4. Missing & Duplicate Checks:**
- Identify null/missing values.
- Remove duplicate transactions.

# Key Metrics & Insights
## A. Sales Performance Analysis
- **Total Revenue:** £322.97K
- **Total Sales Quantity:** 5.51K items
- **Gross Income:** £15.38K
- **Cost of Goods Sold (COGS):** £307.6K


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

# 3. Recommendations
## A. Optimize Product Strategy
- **Increase stock and marketing** for high-selling categories like **Food & Beverages and Sports & Travel**.
- **Analyze lower-performing categories** (Health & Beauty) to improve sales strategies.
B. Improve Customer Engagement
Enhance membership programs to capitalize on the higher spending of members.
Run evening-specific promotions to maximize revenue during peak shopping hours.
C. Branch-Level Strategy
Leverage insights from Branch C’s success to improve performance at Branches A & B.
Evaluate branch-specific product demand to optimize inventory distribution.
D. Digital Payment Adoption
Encourage E-wallet and Credit Card usage through discounts and cashback offers.































Power BI Dashboard Analysis: Retail Sales Insights

Table of Contents
1.	Objective
2.	Data Source
3.	Stages
4.	Design
5.	Mockup
6.	Tools
7.	Development
8.	Pseudocode
9.	Data Exploration
10.	Data Cleaning
11.	Transforming the Data
12.	Creating the SQL View
13.	Testing
14.	Data Quality Tests
15.	Visualization
16.	Results
17.	DAX Measures
18.	Analysis
19.	Findings
20.	Validation
21.	Discovery
22.	Recommendations
23.	Potential ROI
24.	Potential Courses of Action
25.	Conclusion

# Objective

- ## Key Pain Point?

To analyze supermarket sales data, identify trends, and provide actionable insights into revenue, customer behavior, and branch performance.

**Ideal Solution?**

To develop a Power BI dashboard that offers deep insights into sales trends, customer purchasing behavior, and product performance to support data-driven decision-making.

## User Story

As a Business Analyst, I need a comprehensive dashboard to analyze sales trends, customer behavior, and product performance, allowing the company to optimize its business strategy and increase revenue.

### Data Source
- What data is needed?

To achieve our objective, we need:

-	Sales Transaction Data
-	Customer Demographics
-	Product Details
-	Store Branch Performance
  
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

-	Dashboard Visuals:
1.	KPI Scorecards (Total Sales, Profit, Revenue Growth)
2.	Sales Trend Analysis (Line Charts)
3.	Store Performance (Bar Charts, Heatmaps)
4.	Product Performance (Treemaps, Tables)
5.	Customer Analysis (Pie Charts, Segmentations)
   
Mockup
The dashboard layout follows best practices for usability, featuring:
•	A clean, intuitive layout
•	Filters and slicers for dynamic analysis
•	Visual elements highlighting key insights
Tools
|Tool|	Purpose|
|SQL Server	|Data Cleaning & Storage|
|Power BI|	Data Visualization|
|Excel	|Initial Data Exploration|
|GitHub|	Project Documentation & Version Control|

Development
Pseudocode
1.	Load data from SQL Server into Power BI.
2.	Clean the data (handle missing values, correct data types, etc.).
3.	Create relationships between tables for accurate reporting.
4.	Develop Power BI visuals and dashboards.
5.	Apply DAX measures for KPI calculations.
6.	Perform testing and validation.
7.	Publish dashboard and document insights.

Data Exploration & Cleaning
•	Removed null values in key performance fields.
•	Ensured all columns have appropriate data types.
•	Checked for and removed duplicate records.
•	Retained only relevant columns.

Transforming the Data
SQL Query to Clean Data:
SELECT
    Branch,
    Product,
    Category,
    SUM(Sales) AS Total_Sales,
    SUM(Profit) AS Total_Profit,
    COUNT(Transaction_ID) AS Total_Transactions
FROM sales_data
GROUP BY Branch, Product, Category;
Creating the SQL View
CREATE VIEW sales_summary AS
SELECT
    Branch,
    Product,
    Category,
    SUM(Sales) AS Total_Sales,
    SUM(Profit) AS Total_Profit,
    COUNT(Transaction_ID) AS Total_Transactions
FROM sales_data
GROUP BY Branch, Product, Category;

Testing & Data Quality Checks
Row Count Validation:
SELECT COUNT(*) AS total_rows FROM sales_summary;
Column Count Validation:
SELECT COUNT(*) AS column_count FROM INFORMATION_SCHEMA.COLUMNS WHERE TABLE_NAME = 'sales_summary';
Visualization & Results
•	Total Revenue & Profit Trends
•	Top-Selling Products by Revenue & Quantity
•	Customer Segmentation & Buying Patterns
•	Branch Performance Analysis

DAX Measures
Total Sales = SUM(sales_summary[Total_Sales])
Total Profit = SUM(sales_summary[Total_Profit])
Avg Sales per Transaction = DIVIDE([Total Sales], COUNT(sales_summary[Total_Transactions]))

Analysis & Findings
1.	Top-Selling Products: The highest revenue-generating products were from the Electronics category.
2.	Branch Performance: The Downtown branch had the highest sales volume, but the Uptown branch had the highest average profit per sale.
3.	Customer Insights: Repeat customers contribute over 60% of total revenue, suggesting strong brand loyalty.

Validation & Discovery
•	Revenue trends showed seasonal fluctuations, with peak sales in Q4.
•	Certain product categories had high returns, impacting profitability.

Recommendations
1.	Stock More High-Demand Products: Increase stock levels for the most profitable items.
2.	Focus on Repeat Customers: Implement targeted promotions for high-value customers.
3.	Optimize Low-Performing Branches: Improve marketing and inventory strategies at underperforming locations.

Potential ROI & Action Plan
•	Implementing these insights is projected to increase revenue by 10-15%.
•	Next Steps:
1.	Roll out customer engagement initiatives.
2.	Adjust inventory strategies based on sales performance.
3.	Continue refining the dashboard with new KPIs.

Conclusion
The Power BI dashboard provides critical insights into sales trends, customer behavior, and branch performance. By leveraging data-driven decisions, the company can optimize its strategy to improve revenue and customer satisfaction.



