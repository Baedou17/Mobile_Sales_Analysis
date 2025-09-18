# Mobile_Sales_Analysis

## Overview
_The goal of this project was to analyze mobile phone sales data to uncover trends in pricing, brand performance, and customer preferences._

---
## Content
Project Overview | Data Sources | Tools Used | Table Outlay | Query Language(SQL) | Visualization

---
## Project Overview:
(insert here)

## Data Source:
www.kaggle.com/dataset

---
## Tools Used
+ Pivot Table / Charts
+ Power BI
+ SQL

## Table Outlay
TransactionID	| Date | MobileModel |	Brand |	Price |	UnitsSold	| TotalRevenue |	CustomerAge |	CustomerGender |	Location	| PaymentMethod
|---|---|----|----|----|----|----|----|---|----|---|
|79397f68-61ed-4ea8-bcb2-f918d4e6c05b	|06/01/2024	|direction	|Green Inc	|1196.95	|85	|28002.8	|32	|Female	|Port Erik	|Online|
|4f87d114-f522-4ead-93e3-f336402df6aa	|05/04/2024	|right	|Thomas-Thompson	|1010.34	|64	|2378.82	|55	|Female	|East |Linda	|Credit Card|
|6750b7d6-dcc5-48c5-a76a-b6fc9d540fe1	|13/02/2024	|summer	|Sanchez-Williams	|400.8	95	|31322.56	|57	|Male	|East |Angelicastad	|Online|

## Query Language (SQL):
Some of the query languages to retrieve records are displayed here
```SQL
---Categorize the data into Silver, Gold, and Diamond.---
SELECT *,
CASE
	WHEN price < 500 THEN 'Silver'
	WHEN price BETWEEN 500 AND 1000 THEN 'Gold'
	ELSE 'Diamond'
END AS 'Category'
FROM mobile_sales;
```
```SQL
---Retrieve all female customers who bought goods above 900.---
SELECT * FROM mobile_sales
WHERE CustomerGender = 'Female'
	AND Price > 900;
```
```SQL
---Retrieve the sales by payment method, arranging from largest to smallest amount.---
SELECT PaymentMethod, SUM(TotalRevenue) AS Sales 
FROM mobile_sales
GROUP BY PaymentMethod
ORDER BY Sales DESC;
```
```SQL
---Retrieve the most expensive brand.---
SELECT max(Price) AS Price, Brand FROM mobile_sales
group by Brand
order by Price DESC
limit 1;
```
```SQL
---How many brands are there?---
SELECT COUNT(DISTINCT Brand) AS No_Of_Brand FROM mobile_sales;
```
## Power BI Dashboard
<img width="1217" height="658" alt="Screenshot (12)" src="https://github.com/user-attachments/assets/4148b246-468c-4745-aa62-4200ba312a0a" />
