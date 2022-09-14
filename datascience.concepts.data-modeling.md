---
id: s16wa5oyhmeqz7epvhan0wh
title: Data Modeling
desc: ''
updated: 1663116926279
created: 1663050840808
tags:
    - data-science
    - data-analysis
    - data-modeling
---

Data models help keep data consistent and enable people to map out how data is organized

# What is data modeling?

**Data modeling** is the process of creating diagrams that visually represent how data is *organized* and *structured*.  These visual representations are called **data models**. *You can think of data modeling as a blueprint of a house*. At any point, there might be electricians, carpenters, and plumbers using that blueprint. Each one of these builders has a different relationship to the blueprint, but they all need it to understand the overall structure of the house. Data models are similar; different users might have different data needs, but the data model gives them an understanding of the structure as a whole.

# Levels of data modeling

![](/assets/images/2022-09-12-23-35-52.png)

1. **Conceptual data modeling** gives a high-level view of the data structure, such as how data interacts across an organization. For example, a conceptual data model may be used to define the business requirements for a new database. *A conceptual data model doesn't contain technical details*. 

1. **Logical data modeling** focuses on the *technical details* of a database such as relationships, attributes, and entities. For example, a logical data model defines how individual records are uniquely identified in a database. But it doesn't spell out actual names of database tables. That's the job of a physical data model.

1. **Physical data modeling** depicts how a database operates. A physical data model defines all entities and attributes used; for example, *it includes table names, column names, and data types for the database*.

> More info [here](https://www.1keydata.com/datawarehousing/data-modeling-levels.html)

| Conceptual | Logical | Physical |
| - | - | - |
|![](/assets/images/2022-09-13-17-54-17.png)| ![](/assets/images/2022-09-13-17-53-04.png)| ![](/assets/images/2022-09-13-17-53-59.png)|


# Data Modeling Techniques

- Entity Relationship Diagram (ERD).
     - visual way to understand the relationship between entities in the data model.
- Unified Modeling Language (UML) diagram
    - Very detailed diagrams that describe the structure of a system by showing the system's entities, attributes, operations, and their relationships.

    > More info [here](https://dataedo.com/blog/basic-data-modeling-techniques)