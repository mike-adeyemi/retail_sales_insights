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
