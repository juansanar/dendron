---
id: f6upch53s6rniwfjd0za9yq
title: Data Cleaning Queries with SQL
desc: ''
updated: 1674976261208
created: 1667458199169
tags:
  - data-cleaning
  - sql
---

# Functions

- `SUBSTR()`: Takes an `attribute` and the position of the starting character, and number of characters. 
- Example: `SUBSTR(country, 1, 2) = 'US'`.
    - This takes the first letter two letters (starts at the first letters, for a total of two letters) of the strings in `country` and evaluates them to 'US'.
- `CONTAINS_SUBSTR()`: Performs a normalized, case-insensitive search to see if a value exists as a substring in an expression. Returns `TRUE` if the value exists, otherwise returns `FALSE`.
- `TRIM()`: Remove leading, trailing, and repeated spaces in data.
- `DISTINCT`: Including `DISTINCT` in the `SELECT` statement removes duplicates.
- `CAST()`: Converts anything from one data type to another.
    - Form: `CAST(attribute AS data-type)`
        -  Typecasting: Converting data from one type to another. For example from `STRING` to `FLOAT64` or `DATETIME` to `DATE`.
- `CONCAT()`: Adds string together to create new text strings that can be used as unique keys.
    - Example: `CONCAT(attribute1, "_", attribute2)` will lead to `"value in attribute1_value in attribute2"`.
- `COALESCE`: Returns non-null values in a list.
    - `COALESCE(atribute1, attribute2) AS new_attribute`. If `attribute1` is null, it provides the value from `attribute2`.
- `CASE`: The `CASE` statement goes through one or more conditions and returns a value as soon as a condition is met.
    - Form:
    ```sql
    SELECT ...
    CASE
        WHEN attribute = "value" THEN "new value"
        ELSE attribute
        END AS new_attribute
    FROM ...
    ```