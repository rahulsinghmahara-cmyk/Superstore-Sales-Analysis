# Superstore Sales Analysis

## Project Overview

This project is a sales and profitability analysis of the Superstore dataset. I built this project to practice and demonstrate how I would approach a real-world data analysis task from raw data to business insights.

The analysis was completed using PostgreSQL for data exploration and analysis, followed by Power BI for visualization and dashboard development.

The main focus of the project was to understand sales performance, profitability, customer contribution, regional performance, category performance, and changes in sales over time.

The project follows a simple workflow:

**Data → SQL Analysis → Business Insights → Power BI Dashboard**

---

## Business Questions

The analysis was designed around questions that a business or sales team might ask:

- What are the total sales, profit, orders, and quantity sold?
- Which categories generate the most sales and profit?
- Which subcategories are the most and least profitable?
- Which customers contribute the most sales?
- Which regions perform better in terms of sales and profit?
- How does profit margin differ across categories and regions?
- How are sales changing over time?
- Which months and years show stronger or weaker performance?
- How does discounting affect profitability?
- Where are the major sources of losses?

---

## Dataset

The project uses the Superstore sales dataset.

Important fields used in the analysis include:

- Order Date
- Customer ID
- Customer Name
- Product
- Category
- Sub-Category
- Region
- Sales
- Quantity
- Discount
- Profit

The dataset contains 9,994 transaction-level records.

---

# SQL Analysis

PostgreSQL was used to explore, validate, and analyze the dataset before building the Power BI dashboard.

The SQL analysis was organized into separate files based on the type of analysis.

### 1. Data Quality Checks

File:

`SQL/01_data_quality.sql`

The first step was to understand the quality and structure of the data.

Checks included:

- Total number of rows
- Unique orders
- Duplicate Order IDs
- NULL values in important columns
- Date range
- Number of unique customers
- Sales range
- Quantity range
- Profit range

This helped confirm that the dataset was suitable for analysis.

---

### 2. KPI Analysis

File:

`SQL/02_kpi_analysis.sql`

The main business KPIs were calculated using SQL:

- Total Sales
- Total Profit
- Total Orders
- Total Quantity Sold
- Overall Profit Margin

Key results:

| KPI | Value |
|---|---:|
| Total Sales | $2,297,201.07 |
| Total Profit | $286,397.79 |
| Unique Orders | 5,009 |
| Total Quantity | 37,873 |
| Profit Margin | 12.47% |

---

### 3. Category and Subcategory Analysis

File:

`SQL/03_category_analysis.sql`

I compared sales and profitability across categories and subcategories.

The analysis included:

- Sales by category
- Profit by category
- Sales and profit together
- Profit margin by category
- Subcategory profitability
- Top profitable subcategories
- Loss-making subcategories
- Categories with profit above a selected threshold

One important finding was that Technology generated the highest sales and profit, while Furniture had relatively strong sales but much lower overall profit.

---

### 4. Customer Analysis

File:

`SQL/04_customer_analysis.sql`

Customer-level analysis was used to understand which customers contribute the most to the business.

The analysis included:

- Total sales by customer
- Top 5 customers by sales
- Customers with more than 10 orders
- Customers with average sales above $500
- Customer sales by region
- Customer contribution as a percentage of overall sales
- Overall customer ranking
- Customer ranking within each region

This section also introduced window functions such as `RANK()`.

---

### 5. Regional Analysis

File:

`SQL/05_regional_analysis.sql`

The regional analysis compared performance across the four regions.

The analysis included:

- Sales by region
- Profit by region
- Sales and profit together
- Profit margin by region
- Category performance within each region
- Loss-making regions
- Top customer within each region

This helped identify differences between sales performance and actual profitability across regions.

---

### 6. Time-Based Analysis

File:

`SQL/06_time_analysis.sql`

Time-based analysis was used to understand how sales changed throughout the business period.

The analysis included:

- Sales by year
- Profit by year
- Yearly sales and profit
- Monthly sales
- Monthly sales and profit
- Month-over-month sales change
- Year-over-year sales change
- Year-over-year sales percentage change

SQL functions used in this section included:

- `EXTRACT()`
- `DATE_TRUNC()`
- `LAG()`
- Common Table Expressions (CTEs)

This allowed the analysis to move beyond simple totals and look at changes in performance over time.

---

### 7. Advanced Analysis

File:

`SQL/07_advanced_analysis.sql`

The final SQL analysis combined several techniques to answer more detailed business questions.

It included:

- Top 3 customers within each region
- Top 5 subcategories by profit
- Customer sales contribution
- Profit margin by subcategory
- Average profit by discount level
- Loss-making orders
- Loss rate by subcategory
- Overall customer profitability

Techniques used included:

- CTEs
- Subqueries
- Window functions
- `RANK()`
- `CASE`
- `FILTER`
- Aggregations
- Profit margin calculations

---

# Power BI Dashboard

After completing the SQL analysis, I used Power BI to create an interactive dashboard.

### Power BI workflow

The Power BI process included:

1. Loading the Superstore dataset
2. Cleaning and preparing the data using Power Query
3. Creating calculated measures using DAX
4. Building KPI cards
5. Creating sales and profit visualizations
6. Analyzing monthly trends
7. Comparing categories
8. Comparing regions
9. Adding profit margin analysis
10. Designing the final dashboard layout

### Dashboard KPIs

The dashboard highlights four main KPIs:

- Total Sales
- Total Profit
- Profit Margin
- Unique Orders

### Dashboard Visuals

The final dashboard contains:

- Monthly Sales Trend
- Sales and Profit by Category
- Profit Margin by Category
- Sales and Profit by Region
- Profit Margin by Region

The dashboard was designed to keep the most important business information visible without making the report unnecessarily complicated.

---

# Key Insights

### Technology

Technology was the strongest category in terms of both sales and profit.

This suggests that high sales in this category were also supported by strong profitability.

### Furniture

Furniture generated substantial sales but produced significantly lower profit compared with Technology and Office Supplies.

This shows why looking only at sales can give an incomplete picture of business performance.

### Profitability

The overall profit margin was approximately 12.47%.

Looking at profit margin alongside sales helped provide more context about which areas were actually performing efficiently.

### Discounts

The analysis showed a clear relationship between higher discount levels and lower average profit.

At higher discount levels, average profit became negative, highlighting discounting as an area worth monitoring.

### Loss-Making Areas

Several subcategories contributed significantly to overall losses, including Binders, Tables, Machines, Bookcases, and Chairs.

This suggests that sales volume alone should not be used to judge product performance.

### Time Trends

Monthly and yearly analysis showed that sales performance changed over time rather than remaining constant.

Using month-over-month and year-over-year analysis made it easier to identify periods of growth and decline.

---

# Tools and Technologies

- PostgreSQL
- SQL
- Power BI
- Power Query
- DAX
- Excel
- GitHub

### SQL Skills

- SELECT
- WHERE
- GROUP BY
- HAVING
- ORDER BY
- Aggregate functions
- CASE
- CTEs
- Subqueries
- JOINs
- Window functions
- RANK()
- LAG()
- Date functions
- Conditional aggregation

### Power BI Skills

- Data cleaning with Power Query
- Data modeling
- DAX measures
- KPI cards
- Time-series analysis
- Category and regional analysis
- Dashboard design
- Business-focused visualization

---

# Project Structure

```text
Superstore-Sales-Analysis/
│
├── SQL/
│   ├── 01_data_quality.sql
│   ├── 02_kpi_analysis.sql
│   ├── 03_category_analysis.sql
│   ├── 04_customer_analysis.sql
│   ├── 05_regional_analysis.sql
│   ├── 06_time_analysis.sql
│   └── 07_advanced_analysis.sql
│
├── PowerBI/
│   └── Superstore_Sales_Analysis_PowerBI.pbix
│
├── Screenshots/
│   └── dashboard_screenshot.png
│
└── README.md