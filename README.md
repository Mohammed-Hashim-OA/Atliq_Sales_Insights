AtliQ Sales Insights Dashboard

A comprehensive Business Intelligence project designed to analyze sales performance, customer behavior, product performance, and regional revenue trends using SQL and Power BI

This project transforms raw sales transaction data into actionable business insights through data modeling, DAX measures, and interactive visualizations.

--------------------------------------------------------------------------------------------------------------------------------------------------------

🚀Project Overview

The objective of this project is to help stakeholders understand:

- Overall Revenue Performance
- Sales Quantity Trends
- Regional Sales Distribution
- Top Performing Customers
- Top Selling Products
- Revenue Trends Across Time
- Business Growth Opportunities


The project follows a complete Data Analytics workflow:

Raw Data
    ↓
MySQL Database
    ↓
SQL Analysis
    ↓
Power BI Data Transformation
    ↓
Star Schema Modeling
    ↓
DAX Measures
    ↓
Interactive Dashboard
    ↓
Business Insights

----------------------------------------------------------------------------------------------------------------------------

🛠 Tools & Technologies Used

| Tool        | Purpose                 |
|-------------|-------------------------|
| MySQL       | Data Storage & Analysis |
| SQL         | Data Querying           |
| Power BI    | Data Visualization      |
| Power Query | Data Transformation     |
| DAX         | Measure Creation        |
| Excel/CSV   | Data Source             |

--------------------------------------------------------------------------------------------------------------------------------------

📂 Dataset Information

The dataset contains:

- Customer Information
- Product Information
- Sales Transactions
- Markets/Regions
- Date Information

--------------------------------------------------------------------------------------------------------------------------------------------------------

🔍 SQL Data Analysis

The data was first imported into MySQL for exploratory analysis.


- Show All Customers
SELECT * FROM customers;


- Total Customers
SELECT COUNT(*) FROM customers;


- Chennai Transactions
SELECT * FROM transactions WHERE market_code='Mark001';


- Distinct Products Sold in Chennai
SELECT DISTINCT product_code FROM transactions WHERE market_code='Mark001';


- Transactions in USD
SELECT * FROM transactions WHERE currency='USD';


- Revenue Generated in 2020
SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date WHERE date.year=2020;


- Revenue Generated in January 2020
SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date WHERE date.year=2020  AND date.month_name='January';


- Revenue Generated in Chennai
SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date WHERE date.year=2020 AND transactions.market_code='Mark001';


----------------------------------------------------------------------------------------------------------------------------------------------------------------

🧹 Data Cleaning & Transformation

Before visualization, the dataset was cleaned and transformed using Power Query.

- Transformations Performed

✔ Removed invalid records

✔ Standardized currency values

✔ Cleaned inconsistent transaction entries

✔ Verified relationships between tables

✔ Created normalized sales amount column

✔ Prepared data for analytical reporting

### Currency Conversion Logic

PowerQuery
= Table.AddColumn(#"Filtered Rows","norm_amount", each if [currency] = "USD" or [currency] = "USD#(cr)" then [sales_amount] * 75 else [sales_amount], type any)


⭐ Data Modeling

To improve dashboard performance and maintain best practices, the data model was redesigned into a **Star Schema**.

Benefits of Star Schema

- Faster Query Performance
- Improved Dashboard Responsiveness
- Better Scalability
- Cleaner Relationships
- Simplified Reporting Structure


 📐 DAX Measures Created

- Total Revenue
Total Revenue =,SUM(transactions[norm_amount])


- Sales Quantity
Sales Quantity = SUM(transactions[sales_qty])


These measures were used across multiple dashboard visuals and KPI cards.



📊 Dashboard Features

1️⃣ KPI Cards

Provides a quick snapshot of business performance.

Metrics
- Total Revenue
- Total Sales Quantity

- Results
Total Revenue : 984.87M
Sales Quantity : 2M


2️⃣ Interactive Year Slicer
Implemented a dynamic year filter allowing users to analyze data across:
- 2017
- 2018
- 2019
- 2020

This improves user experience and enables year-wise comparison.


3️⃣ Revenue Trend Analysis
A line chart was created to monitor:
- Revenue Trends
- Sales Quantity Trends

Business Value

- Detect growth patterns
- Identify seasonal trends
- Monitor revenue fluctuations


4️⃣ Revenue by Region
Analyzes revenue contribution across different regions.

Key Finding

Delhi NCR contributes the highest revenue among all markets.


5️⃣ Sales Quantity by Region
Displays quantity sold across regions.

Business Value

- Identify high-demand markets
- Compare market performance
- Support sales strategy decisions


6️⃣ Top 5 Customers Analysis
Highlights customers generating the highest revenue.

Business Value

- Customer Retention
- Revenue Optimization
- Relationship Management

7️⃣ Top 5 Products Analysis

Displays the highest revenue-generating products.

Business Value

- Product Performance Evaluation
- Inventory Planning
- Marketing Strategy Support



📈 Key Business Insights

Revenue Distribution

- Delhi NCR is the leading contributor to overall revenue.


Customer Contribution

- A small group of customers contributes significantly to total sales revenue.


Product Performance

- Top-selling products generate the majority of business revenue.


Revenue Trends

- Revenue patterns indicate opportunities for demand forecasting and business planning.

----------------------------------------------------------------------------------------------------------------------------------------------

🎯 Skills Demonstrated

- SQL Querying
- Data Cleaning
- Data Transformation
- Data Modeling
- Star Schema Design
- Power BI Development
- DAX Calculations
- Data Visualization
- Dashboard Design
- Business Intelligence
- Analytical Thinking


💡 Future Improvements
- Customer Segmentation Analysis
- Profitability Dashboard
- Forecasting Using Time Series Analysis
- Advanced DAX Calculations
- Drill-through Reports
- Dynamic KPI Comparisons


------------------------------------------------------------------------------------------------------------------
👨‍💻 Author

Mohammed Hashim O A

Aspiring Data Analyst | Power BI Developer | SQL Enthusiast

Skills

- Power BI
- SQL
- Python
- Excel
- Data Visualization
- Data Analysis
- Business Intelligence

#Connect With Me

https://www.linkedin.com/in/mohammed--hashim
https://github.com/Mohammed-Hashim-OA

------------------------------------------------------------------------------------------------
⭐ Support

If you found this project useful, please consider giving it a ⭐ on GitHub.

Project Outcome

This dashboard enables stakeholders to make data-driven decisions by providing clear visibility into sales performance, customer trends, product success, and regional growth opportunities through an interactive Business Intelligence solution.
