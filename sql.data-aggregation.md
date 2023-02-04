---
id: dpsz1e2p1nczda8qijcg05y
title: Data Aggregation
desc: ''
updated: 1675539713479
created: 1674981391517
tags:
    - sql
    - join
    - data-aggregation
---

# What does Data Aggregation provide?

Data aggregation allows to identify trends, make comparisons, and gain insights that are not possible to obtain when analyzing elements on their own by gathering multiple sources.

`JOIN`s are way to aggregate data in SQL. See more [[here | sql.concepts.joins]].

Another way to aggreagate data using SQL is using subqueries and Common Table Expressions (CTE)

## What is a subquery?

A subquery is a query within a query. An iner query executes first, followed by an outer query. Subqueries can also be executed within `FROM` and `WHERE` clauses. 

### Some subquery rules

- There are a few rules that subqueries must follow:
- Subqueries must be enclosed within parentheses
- A subquery can have only one column specified in the SELECT clause. But if you want a subquery to compare multiple columns, those columns must be selected in the main query.
- Subqueries that return more than one row can only be used with multiple value operators, such as the IN operator which allows you to specify multiple values in a WHERE clause.
- A subquery can’t be nested in a SET command. The SET command is used with UPDATE to specify which columns (and values) are to be updated in a table.

## The `HAVING` clause

Allows you to add a filter to your query instead of the underlying table that can only be used with aggregate functions. In this way, it only returns records that meet your specific conditions.

## The `CASE` clause

Returns records with your conditions by allowing you to include if/then statement in your query.

