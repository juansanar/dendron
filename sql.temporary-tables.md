---
id: refwwxyuk3qargttsckilxv
title: Temporary Tables in SQL
desc: ''
updated: 1676186325381
created: 1676179905058
tags:
    - sql
    - join
    - data-aggregation
---

# What is temporary Table?

A database table that is created and exists temporarily on a database server. These are some examples of when a temporary table is useful:

- Dealing with multiple tables in which you are performing calculation on at the same time.
- You have to deal with a query that needs to join several tables.
    - You could join the two or three tables having the fewest number of entries and store their output in a temporary table and then join to other larger tables.
- In cases when you have a large number of records in a table and you need to work with a small susbet of those records repeatedly to complete calculations or other analysis.
    - This removes the need of filtering the data over and over to return the subset (it only needs to be fitered once).

> LPT: Temporary tables make query code less complicated, more organized, and easier to understand

# How to create temporary tables?

- The `WITH` clause: creates a type of temporary tables that is queriable multiple times without adding a table to the databse.
```sql
WITH temp_table AS(
    SELECT
        ColA, ColB,...
    FROM
        existing_Table
    WHERE --of needed
)
```
- The `SELECT INTO` clause: copies data from one table into a new table, but doesn’t add the new table to the database. It’s useful if you want to make a copy of a table with a specific condition.
    - **bigquery does not recognize `SELECT INTO`.**
- The `CREATE TABLE` clause: good option when several people need to access the same temp table. This statement adds the table into the database. 
