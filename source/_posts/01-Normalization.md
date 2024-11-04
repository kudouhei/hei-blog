---
title: Normalization and Standardization
date: 2024-11-04 12:15:55
tags:
- Data
categories:
- Data
---

## Normalization
Normalization refers to processing feature data into a dimensionless, bounded range, typically within [0,1] or [−1,1]. In statistics, normalization helps unify the distribution characteristics of a sample. When normalized within [0,1], it represents a probability distribution, while within [−1,+1], it resembles a coordinate distribution.

Normalization scales data to a specific range, like \([0,1]\) or \([-1,1]\). Common methods:
- **Rescaling**: \[ x' = \frac{x - \text{min}(x)}{\text{max}(x) - \text{min}(x)} \]
- **Mean normalization**: \[ x' = \frac{x - \text{mean}(x)}{\text{max}(x) - \text{min}(x)} \]

## Standardization
Transforms data by subtracting the mean and dividing by variance:
\[
x' = \frac{x - \overline{x}}{\sigma}
\]
Standardization does not alter data distribution.

## Z-score
Z-score is a statistical measurement that describes a value's relationship to the mean of a group of values. The Z-score is a way to figure out how far away a piece of data is from the average of a group, measured in standard deviations.
\[
z = \frac{x - \mu}{\sigma}
\]
where 
- z = Z-score
- x = the value being evaluated
- μ = the mean
- σ = the standard deviation

## QA
### 1. Why Standardize or Normalize?

- **Purpose**: To make features on different scales comparable without altering data distribution. For example, in a function like \( y = x_1 + x_2 + 7 \), if \( x_1 \) ranges from \([0,1]\) and \( x_2 \) from \([0,10000]\), then \( x_2 \) will dominate without scaling.
- **Gradient Descent**: Normalization/standardization speeds up convergence in gradient descent optimization.

### 2. Data Types to Avoid Scaling

Sparse data should not be scaled, as scaling it would turn sparse (mostly zero) vectors into dense ones, altering their meaning significantly.

### 3. When to Use Standardization or Normalization?

- Use **Normalization** if strict range requirements apply.
- Choose **Standardization** when data contains outliers, involves distance-based similarity, or requires dimensionality reduction.

### 4. Is Scaling Always Necessary?

Not always. Models that don’t measure distance or rely on variable distribution (e.g., decision trees, probability models) generally don’t require scaling.
