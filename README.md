# Sales_analytics
Sales analytics with PowerBI. Data is been gathered from Codebasics Github Repo - https://github.com/codebasics/DataAnalysisProjects/tree/master/1_SalesInsights#sales-insights-data-analysis-project

# Data Analysis Using SQL

1. Show all customer records

SELECT * FROM customers;

2. Show total number of customers

SELECT count(*) FROM customers;

3. Show transactions for Chennai market (market code for chennai is Mark001

SELECT * FROM transactions where market_code='Mark001';

4. Show distrinct product codes that were sold in chennai

SELECT distinct product_code FROM transactions where market_code='Mark001';

5. Show transactions where currency is US dollars

SELECT * from transactions where currency="USD"

6. Show transactions in 2020 join by date table

SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;

7. Show total revenue in year 2020,

SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";

8. Show total revenue in year 2020, January Month,

SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");

9. Show total revenue in year 2020 in Chennai

SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.market_code="Mark001";

# Data Analysis Using Power BI
10. Formula to create norm_amount column
= Table.AddColumn(#"Filtered Rows", "norm_amount", each if [currency] = "USD" or [currency] ="USD#(cr)" then [sales_amount]*75 else [sales_amount], type any)

Special Thanks to Mr. Dhaval Patel and codebasics for data and tutorial.

# Dashboard Preview
**Key Insights**
![image](https://github.com/Dataholic-16/AtliQ-Hardware-Sales-Insight/assets/135443003/e247202d-38bc-4c9b-aaeb-60f90be9e8b9)
**Profit Analysis**
![image](https://github.com/Dataholic-16/AtliQ-Hardware-Sales-Insight/assets/135443003/136846b3-b93a-4616-8b4c-db59763a343a)
**Performance Insights**
![image](https://github.com/Dataholic-16/AtliQ-Hardware-Sales-Insight/assets/135443003/c9989548-3e82-4529-b0c3-001367e422a1)


