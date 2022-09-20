---
id: fl5cb0v27d0l22wf9kpgdd3
title: Data Integrity
desc: ''
updated: 1663563232631
created: 1663561898969
---

# What is data integrity?

The accuracy, completeness, consistency, and trustworthiness of data throughout its [[ lifecycle | datascience.concepts.data-life-cycle#the-six-stages-of-the-data-life-cycle-google]].

# Challenges in data integrity

- Data replication: The process of storing data in multiple locations. It can lead to inconsistencies due to analyst not using a synced system of record.
- Data transfer: The process of copying data from storage to memory, or from one computer to another. If the data transfer is interrupted and/or accumulate errors (e.g., date formats when importing, gene names as dates, etc.), it can lead to gaps (e.g., missed values).
- Data manipulation: The process of changing data to make it more organized and easier to read.

> The Data Warehoiuse or Data Engineering team keeps data integrity in a company

> A good analysis depends on the integrity of the data, and data integrity usually depends on using a common format

No matter where your data comes from, always be sure to check that it is valid, complete, and clean before you begin any analysis.

![](/assets/images/2022-09-18-21-43-47.png)

# Data constraints and examples

Constraints are criteria that determine the validity of data. Here are some examples

| Data constraint | Definition | Examples
|-|-|-|
**Data type**| Values must be of a certain type: date, number, percentage, Boolean, etc.| If the data type is a date, a single number like 30 would fail the constraint and be invalid|
**Data reange** | Values must fall between predefined maximun and minimum values | If teh data range is 10-20, a value of 30 would fail the constraint and be invalid|
**Mandatory**|Values can’t be left blank or empty | If age is mandatory, that value must be filled in|
**Unique** | Values can't have a duplicate | Two people can't save the same mobile phone number within the same service area|
**Regular expression (regex) patterns| Values must match a prescribed pattern| A phone number must match ###-###-#### (no other characters allowed)|
**Cross-field validation** | Certain conditions or multiple fields must be satisfied| Values are percentages and values from multiple fields must add up to 100%|
**Primary key**|(Databases only) value must be unique per column|A database table can’t have two rows with the same primary key value. A primary key is an identifier in a database that references a column in which each value is unique|
**Set-membership**|(Databases only) values for a column must come from a set of discrete values |Value for a column must be set to Yes, No, or Not Applicable|
**Foreign-key**|(Databases only) values for a column must be unique values coming from a column in another table|In a U.S. taxpayer database, the State column must be a valid state or territory with the set of acceptable values defined in a separate States table|
**Accuracy** | The degree to which the data conforms to the actual entity being measured or described|If values for zip codes are validated by street location, the accuracy of the data goes up|
**Completeness**|The degree to which the data contains all desired components or measures|If data for personal profiles required hair and eye color, and both are collected, the data is complete.|
**Consistency**|The degree to which the data is repeatable from different points of entry or collection| If a customer has the same address in the sales and repair databases, the data is consistent.
