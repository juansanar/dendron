---
id: 9p51ninc5xpi6epz24r3dym
title: Joins in SQL
desc: ''
updated: 1675507936189
created: 1675502150173
tags:
    - sql
    - join
    - data-aggregation
---
## What is a `JOIN`

A SQL clause that is used to combine rows from two or more tables based on a related column.

- Primary keys refernce columns in which values is unique to that tables
- Foreing keys are primary keys in other tables.

## Common `JOIN`s

![](/assets/images/2023-02-04-02-32-26.png)

- Inner: Returns records with matching values in each table. For the records to appear on the result table, key values would havet to be in both tables. `JOIN` defaults to `INNER JOIN`.
- Left: Returns records from the left table and only the matching records from the right table.
> The table mention first is the left table, the table mentioned seconds is right.
- Right: Opposite from left join.
- Outer: Combines both tables and returns all values in both tables. `FULL OUTER JOIN` nin bigquery.