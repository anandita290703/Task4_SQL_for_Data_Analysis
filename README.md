# Task 4: SQL for Data Analysis

## Objective
Use SQL queries to analyze ecommerce data using joins, groupings, subqueries, views, and optimizations.

## Tools Used
- SQLite (via DB Browser)
- SQL

## Contents
- SQL Queries: `queries.sql`
- Screenshots of query outputs: `screenshots/`

## Key Concepts Used
- SELECT, WHERE, GROUP BY, ORDER BY
- JOINs (INNER, LEFT)
- Aggregate functions: SUM, COUNT
- Subqueries and Views
- Index creation for optimization

## Interview Questions Answered

1. **Difference between WHERE and HAVING**  
   - `WHERE` filters rows *before* grouping.  
   - `HAVING` filters *after* grouping.

2. **Types of Joins**
   - INNER JOIN, LEFT JOIN, RIGHT JOIN (if supported), FULL OUTER JOIN.

3. **Average Revenue Per User (ARPU)**  
   ```sql
   SELECT AVG(total_spent) 
   FROM (
       SELECT customer_id, SUM(quantity * price) AS total_spent
       FROM orders o
       JOIN order_items oi ON o.order_id = oi.order_id
       GROUP BY customer_id
   );
