---
id: ymqx9pdjmz4xaj9xfukij7g
title: Sample Size
desc: ''
updated: 1663831551044
created: 1663828692289
tags:
 - data-science
 - data-analysis
 - sample-size
 - sampling
---

# What is a sample?

A sample is a part of the population that is representative of the population.

Samples are extremely valuable and useful as assessing the population is often expensive and impossible to do when researching or surveying a topic.

# How to calculate the size of a sample?

If the population size is known, the conficence interval is knonw, and the [[margin of error|datascience.concepts.margin-of-error#how-to-calculate-the-margin-of-error]] is known, the sample size can be calculated as follows:

$Sample.size = \frac{\frac{z^2\times p(1-p)}{e^2}}{1+\frac{z^2\times p(1-p_)}{e^2N}}$

>
N = population size • e = Margin of error (percentage in decimal form) • z = z-score

The z-score is the number of standard deviations a given proportion is away from the mean. To find the right z-score to use, refer to the table below:

| Desired confidence interval | Z-score|
|-|-|
80%|1.28|
85%|1.44|
90%|1.65|
95%|1.96|
99%|2.58|