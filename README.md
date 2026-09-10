# SQL Sales Analysis Project

## Project Overview

This project focuses on analyzing sales and customer data using Microsoft SQL Server. The analysis explores customers, products, orders, and order details to extract meaningful business insights and answer key business questions using SQL queries.

## Objectives

* Analyze customer purchasing behavior
* Examine product performance
* Analyze orders and sales activity
* Identify useful patterns and relationships in the data
* Practice advanced SQL querying techniques

## Database Structure

The project contains the following main tables:

* `CATEGORIES` — Categories information
* `CUSTOMERS` — Customer information
* `PRODUCTS` — Product information
* `EMPLOYEES` — Employees information
* `ORDERS` — Order information
* `ORDER_DETAILS` — Details of products included in each order
* `PRODUCTS` — Product information
* `SUPPLIERS` — Supplier information

## SQL Techniques Used

* SELECT statements
* WHERE filtering
* ORDER BY
* GROUP BY
* Aggregate functions
* INNER JOIN
* LEFT JOIN
* Subqueries
* Correlated subqueries
* `EXISTS`
* `NOT EXISTS`
* CASE statements
* Data aggregation
* Customer and product analysis

## Example Query

One of the queries identifies customers who have purchased products by using nested `NOT EXISTS` conditions:

```sql
SELECT C.CUSTOMER_CODE AS 'CUSTOMER_NO', C.COMPANY, C.PHONE, ISNULL(SUM(OD.UNIT_PRICE * OD.QUANTITY * (1 - ISNULL(OD.DISCOUNT, 0))), 0) AS Total_Amount, C.COUNTRY
FROM [dbo].[CUSTOMERS] C
LEFT JOIN [dbo].[ORDERS] O
ON C.CUSTOMER_CODE = O.CUSTOMER_CODE
AND O.ORDER_DATE >= '1998-04-01'
AND O.ORDER_DATE < '1998-05-01'
AND DATENAME(WEEKDAY, O.ORDER_DATE) = 'MONDAY'
LEFT JOIN [dbo].[ORDER_DETAILS] OD
ON O.ORDER_int = OD.ORDER_int
WHERE C.COUNTRY = 'France'
GROUP BY C.CUSTOMER_CODE, C.COMPANY, C.PHONE, C.COUNTRY;

```

## Key Findings

* Customer purchasing patterns can be explored by connecting the `CUSTOMERS`, `ORDERS`, and `ORDER_DETAILS` tables.
* Product-level analysis can be performed by joining product information with order details.
* SQL subqueries and `NOT EXISTS` can be used to answer more complex business questions.

## Tools & Technologies

* Microsoft SQL Server
* SQL Server Management Studio (SSMS)
* SQL
* Git
* GitHub


## Author

**Habeeb Ayobami**

Data Scientist | Data Analyst

GitHub: [Habeeb-Ayobami](https://github.com/Habeeb-Ayobami)
