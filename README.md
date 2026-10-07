## Global Retail Performance Dashboard by Manas Gupta

### Instructions to setup mysql on your local computer

1. Follow step in this video to install mysql on your local computer
https://www.youtube.com/watch?v=WuBcTJnIuzo

1. SQL database dump is in db_dump.sql file above. Download `db_dump.sql` file to your local computer and import it as per instructions given in the tutorial video

### Data Analysis Using SQL

1. Show all customer records

    `SELECT * FROM customers;`

1. Show total number of customers

    `SELECT count(*) FROM customers;`

1. Show transactions for Chennai market (market code for chennai is Mark001)

    `SELECT * FROM transactions WHERE market_code='Mark001';`

1. Show distinct product codes that were sold in chennai

    `SELECT DISTINCT product_code FROM transactions WHERE market_code='Mark001';`

1. Show transactions where currency is US dollars

    `SELECT * FROM transactions WHERE currency='USD';`

1. Show transactions in 2020 join by date table

    `SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date = date.date WHERE date.year = 2020;`

1. Show total revenue in year 2020

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date = date.date WHERE date.year = 2020 AND (transactions.currency = 'INR' OR transactions.currency = 'USD');`
	
1. Show total revenue in year 2020, January Month

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date = date.date WHERE date.year = 2020 AND date.month_name = 'January' AND (transactions.currency = 'INR' OR transactions.currency = 'USD');`

1. Show total revenue in year 2020 in Chennai

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date = date.date WHERE date.year = 2020 AND transactions.market_code = 'Mark001';`