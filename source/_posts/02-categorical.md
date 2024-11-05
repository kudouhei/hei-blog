---
title: Categorical features
date: 2024-11-05 21:56:18
tags:
- Data
categories:
- Data
mathjax: true
---

## Categorical features
Categorical features are broadly classified into two groups — nominal(no particular order), ordinal (order of the data matters).

### Nominal
Nominal features represent categories without any inherent order or ranking.

Examples:
- Colors (e.g., red, blue, green)
- Countries or regions
- Types of fruits (e.g., apple, banana, orange)
- gender

### Ordinal
Ordinal features represent categories with a meaningful order or ranking.

#### One Hot Encoding
One-hot encoding is a method of converting categorical variables into a format that can be provided to machine learning algorithms to improve prediction. It involves creating new binary columns for each unique category in a feature. Each column represents one unique category, and a value of 1 or 0 indicates the presence or absence of that category.

```
import pandas as pd  
df = pd.DataFrame({  
    'gender': ['male', 'female', 'male', 'female', 'other']  
})   
dummies = pd.get_dummies(df['gender'])  
```

```
OUTPUT:
No.  female  male  other  
0       0     1      0  
1       1     0      0  
2       0     1      0  
3       1     0      0  
4       0     0      1
```

#### Label encoding
Each unique category is assigned a unique integer, effectively converting categorical data into numerical values. Label encoding is suitable for categorical data where there is an inherent order or ranking among the categories.

```
from sklearn.preprocessing import LabelEncoder

categories = ['red', 'green', 'blue', 'red']
encoded_categories = label_encoder.fit_transform(categories)

print("Encoded categories:", encoded_categories) // 0 1 2 0
```

#### Count or Frequency encoding
Substitute the categories by the count of the observations that has that particular category in the dataset.

#### Binary encoding
Binary Encoding is similar to One-Hot Encoding, but instead of creating a separate column for each category, the categories are represented as binary digits.