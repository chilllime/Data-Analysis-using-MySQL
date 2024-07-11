# Data-Analysis-using-MySQL

Atliq is a hardware company dealing with computer peripherals and components, the company wants to insights for data such as top selling products, customer behaviour, 


Data Analysis using MySQL:

1.Top Selling Products  

query='''select p.product_code,sum(t.sales_amount) as totalSales from
transactions t
inner join products p on t.product_code=p.product_code
group by t.product_code 
order by totalSales desc
limit 5'''

2.Sales trend by month

query='''SELECT d.month_name, SUM(sales_amount) AS total_sales
FROM transactions t
INNER JOIN date d ON t.order_date = d.cy_date 
GROUP BY d.month_name
ORDER BY d.month_name;

3.Sales Volume by each Customer in year 2020

query='''SELECT c.custmer_name,sum(t.sales_qty) AS sales_volume
FROM customers c
JOIN transactions t
ON t.customer_code = c.customer_code
WHERE year(order_date) = 2020
GROUP BY c.custmer_name
ORDER BY sales_volume DESC
'''

4. Total Sales by Market in 2020

query='''SELECT m.markets_name,sum(t.sales_amount) as total_sales FROM
transactions t 
INNER JOIN markets m ON t.market_code=m.markets_code
WHERE year(t.order_date)='2020'
GROUP BY m.markets_name
ORDER BY total_sales desc;

