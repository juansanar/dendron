---
id: atprstctuf668wwzeord76e
title: Tips to clean data in spreadhseets
desc: ''
updated: 1675064258131
created: 1673679546283
tags:
  - data-cleaning
  - spreadhsheets
---

# Numbers/String to Date

Google Sheets stores all dates as integer numbers. Not sequences of a day, month, and year as we got used to seeing, but simple integers (and time is kept as decimals):

- 1 for December 31, 1899 (aka epoch)
- 2 for January 1, 1900
- 102 for April 11, 1900 (100 days after January 1, 1900) and so on.

Unlike Excel that cannot store dates as negative numbers, in Google, for dates prior to December 31, 1899, the numbers will be negative.

**When dealing with dates in a Google Spreadsheets, keep in mind the spreashsett's locale. In the case of the US, dates will be treated as MM/DD/YYYY, while in another place such as the UK, the date format is DD/MM/YYYY**

> To change the spreadhseet locale, go to File > Spreadsheet settings In the same menu, the time zone can be specified.

String can be converted into a data by selecting the desired cells and going to *Format > Number*

Another way to format dates is by using the function `QUERY()`:

For the following table
![](/assets/images/2023-01-13-23-17-08.png)

Changing the date format in `column B` can be achieved with

`=QUERY(A1:C7, "SELECT * FORMAT B 'dd-mm-yyyy (ddd)'")`
- `A1:C7` equals the selection range
- `SELECT *` requests to return all columns
- `FORMAT B 'dd-mm-yyyy (ddd)`, formats the date

Reference special code for dates

Code | 	Description	| Example |
- | - | -|
d	 | Day without a leading zero for 1-9 |	7
dd	 | Day with a leading zero for 1-9	| 07
ddd	 | Day as an abbreviation |	Wed
dddd | 	Day as a full name	| Wednesday
m (if not preceded or followed by hours or seconds) | Month without a leading zero | 8
mm (if  | not preceded or followed by
hours or seconds) | Month with a leading zero | 08
mmm	 | Month as an abbreviation |	Aug
mmmm | 	Month as a full name | August
mmmmm | First letter of the month | A
y or yy | Two digit year | 19
yyy or yyyy | Full numeric year |	2019

> [Source and more info](https://www.ablebits.com/office-addins-blog/google-sheets-change-date-format/)

> For [Excel](https://www.ablebits.com/office-addins-blog/excel-convert-text-to-number/)

# Date to Numbers

To convert a date to a number use the *Format* menu (*Format > Number*) or the function `DATEVALUE()`.

# Date to Text

Use the function `TEXT()`.
- Syntax: `TEXT(number, format)`
- Example: For `=TEXT("8/17/2019","YYYY-MM-DD")`
    * ![](/assets/images/2023-01-13-23-36-42.png)

# String to Numbers

Use the function `VALUE()`. For cases of a currency number/text, use the function `TO_PURE_NUMBER()`.

To remove "," from numbers, use `REGEXTRACT()`

> [Source](https://productivityspot.com/convert-text-to-numbers-google-sheets/)

# Combining Columns

Use the `CONCATENATE()` function to append strings (this allows adding spaces `" "` or any other separator or `string`), and use `=CONCAT()` to concatenate two values.

> Columns can also be split using the "Data" menu (Data > Split text to columns). This usees the space (i.,e " ") to split the text into columns.

# Numbers to Percentage

Use the `TO_PERCENT()` function.

> [Source](https://support.google.com/docs/answer/3094284?hl=en)

# Handling Strings

- `LEN()`: Obtain length of string.
- `FIND()`: Returns the index of a given a character/string. It is case-sensitive.
- `RIGHT()`: Returns all the string values **right** from a given index.
  - Syntax: `=RIGHT([Column], [index])`
- `LEFT()`: Returns all the string values **left** from a given index (inclusive)
  - Syntax: `=LEFT([Column], [index])`

# `VLOOKUP()`

`VLOOKUP()` finds a value in a given column that corresponds to the explcit expression to match within a specified range. Before using `VLOOKUP()` **make sure your data is cleaned/prepared**. Use functions such as `VALUE()`, `CONVERT()` or `TRIM()` to make sure entries are consistent and assigned to their respective data types or formats.

- Syntax: `=VLOOKUP([value], [range],[column number], TRUE/FALSE)`
  - `FALSE` = match must be exact.
  - `TRUE` = approximate match.
- Limitations:
  - It only returns the first match it finds.
  - It can only return a value from the data to the right; it can't look left.
    - >You want the column that matches the search key in a VLOOKUP formula to be on the left side of the data. VLOOKUP only looks at data to the right after a match is found. In other words, the index for VLOOKUP indicates columns to the right only. This may require you to move columns around before you use VLOOKUP.
    - Workaround: Copy and paste a column to the left of the data you want to look at. That way, the lookup value is in the leftmost column and the data you want is to the right of it.
  - Failing to lock the reference array can lead to erroneous return values. To lock, use the `$`.

# `XLOOKUP()`

Introduced in August 2022 in Google Sheets (and in 2019 in Excel), `XLOKUP()` function returns the values in the result range based on the position where a match was found in the lookup range. If no match is found, it returns the closest match. In other words, it can replace all the other `LOOKUP` methods.

- Syntax: `XLOOKUP(search_key, lookup_range, result_range, missing_value, match_mode, search_mode)`
  - `search_key`: The value to search for. For example, 42, "Cats", or B24.
  - `lookup_range`: The range to consider for the search. This range must be a singular row or column.
  - `result_range`: The range to consider for the result. This range's row or column size should be the same as the lookup_range, depending on how the lookup is done.
  - `missing_value`: [OPTIONAL -'#N/A' by default] The value to return if no match is found.
  - `match_mode`: [OPTIONAL - 0 by default] The manner in which to find a match for the search_key.
    - 0 is for an exact match.
    - 1 is for an exact match or the next value that is greater than the search_key.
    - -1 is for an exact match or the next value that is lesser than the search_key.
    - 2 is for a wildcard match.
  - `search_mode`: [OPTIONAL - 1 by default] The manner in which to search through the lookup_range.
    - 1 is to search from the first entry to the last.
    - -1 is to search from the last entry to the first.
    - 2 is to search through the range with binary search. The range needs to be sorted in ascending order first.
    - -2 is to search through the range with binary search. The range needs to be sorted in descending order first.

### Notes
If result_range is more than one row or column, then the output will be the entire row/column at the index a match was found in the lookup_range.