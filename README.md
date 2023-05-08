# PowerBI_Sales_Analysis_Project


### Data Analysis Using SQL
--(1) Show total revenue in specific year
SELECT SUM(transactions.sales_amount) 
FROM transactions 
INNER JOIN date 
ON transactions.order_date = date.date 
where date.year=2020 and transactions.currency='INR\r' or transactions.currency='USD\r';

--(2) Show total revenue in specific month
SELECT SUM(transactions.sales_amount) 
FROM transactions 
INNER JOIN date 
ON transactions.order_date=date.date 
where date.year=2020 and date.month_name='January' and (transactions.currency='INR\r' or transactions.currency='USD\r');

--(3) Show total revenue in year 2020 in Chennai

SELECT SUM(transactions.sales_amount) 
FROM transactions 
INNER JOIN date 
ON transactions.order_date=date.date where date.year=2020 and transactions.market_code='Mark001';

--(4) Show transactions in 2020 join by date table

SELECT transactions.*, date.* 
FROM transactions 
INNER JOIN date 
ON transactions.order_date=date.date 
where date.year=2020;
	
--(5) Show total number of customers

SELECT count(*) FROM customers;

--(6) Show transactions for Chennai market (market code for chennai is Mark001)

SELECT * FROM transactions where market_code='Mark001';

--(7) Show distrinct product codes that were sold in chennai

SELECT distinct product_code FROM transactions where market_code='Mark001';

--(8) Show transactions where currency is US dollars

SELECT * from transactions where currency='USD';
