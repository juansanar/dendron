---
id: gplwvncyye8kkf66la3fflu
title: Calculations in SQL
desc: ''
updated: 1675666818268
created: 1675660183569
---

Syntax:

```sql
SELECT
    columnA,
    columnB,
    columnA {operator} columnB AS columnX
```
> {operator} can be "+", "-", "*", "/", "%" (modulo, return the remainder of a division)

If using the `+` operator, the result would like:

columnA | columnB | columnX
-|-|-|
A1|B1|A1 + B1
A2|B2|A2 + B2
An|Bn|An + Bn

> Calculations in SQL are aggregation operations are will require the use of the `GROUP BY` clause.

## `GROUP BY`

A command that groups rows that have the same values from a table into summary rows. Goes at the end of the query.

## `EXTRACT`

Allows to extract a part of `date` value.
- Syntax: `EXTRACT([DAY, MONTH, or YEAR] FROM [DATE FIELD])`
    - All in caps.