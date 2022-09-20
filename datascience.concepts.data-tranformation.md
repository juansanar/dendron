---
id: 7hxf5mz04jsyoe0u1nrfgor
title: Data Tranformation
desc: ''
updated: 1663527602922
created: 1663526887889
---

# Examples of data Transformation

Data transformation usually involves:

- Adding, copying, or replicating data 
- Deleting fields or records 
- Standardizing the names of variables
- Renaming, moving, or combining columns in a database
- Joining one set of data with another
- Saving a file in a different format. For example, saving a spreadsheet as a comma separated values (CSV) file.

# Why transform data?

- Data **organization**: better organized data is easier to use
- Data **compatibility**: different applications or systems can then use the same data
- Data **migration**: data with matching formats can be moved from one system to another
- Data **merging**: data with the same organization can be merged together
- Data **enhancement**: data can be displayed with more detailed fields 
- Data **comparison**: apples-to-apples comparisons of the data can then be made

# Wide v.s Long Data Transformation?

All the data included in the [[long |datascience.concepts.data-tables#long-data]] format is also in the [[wide |datascience.concepts.data-tables#wide-data]] format. But wide data is easier to read and understand. That is why data analysts typically transform long data to wide data more often than they transform wide data to long data. The following table summarizes when each format is preferred:

| Wide data is preferred when| Long data is preferred when|
|-|-|
|Creating talbles and charts with a few variables aboiut each subject|Storing a lot of variables about each subject. For example, 60 years worth of interest rates for each bank|
|Comparing straightforward line graphs|Performing advanced statistical analysis or graphing|