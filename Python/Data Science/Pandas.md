
## 🧩 **1. Importing Pandas**

```python
import pandas as pd
```

---

## 📈 **2. Series**

A **Series** is like a **column** in a spreadsheet or a **1D array** with labels.

### ➤ Creating a Series

```python
import pandas as pd

# From list
s1 = pd.Series([10, 20, 30, 40])

# From list with custom index
s2 = pd.Series([10, 20, 30], index=['a', 'b', 'c'])

# From dictionary
s3 = pd.Series({'a': 10, 'b': 20, 'c': 30})

# From scalar value
s4 = pd.Series(5, index=['x', 'y', 'z'])
```

### ➤ Accessing Data

```python
s1[0]        # By position
s2['a']      # By label
s2[['a', 'c']]   # Multiple elements
s1[1:3]      # Slicing
```

### ➤ Series Attributes

```python
s1.index      # Index labels
s1.values     # Data values
s1.dtype      # Data type
s1.size       # Number of elements
```

### ➤ Series Operations

```python
s1 + 5
s1 * 2
s1 + s2        # Element-wise addition (by index)
s1.mean()
s1.max()
s1.min()
s1.sum()
```

---

## 🧮 **3. DataFrame**

A **DataFrame** is a **2D labeled data structure** (like a table with rows & columns).

### ➤ Creating DataFrames

```python
import pandas as pd

# From dictionary of lists
data = {'Name': ['Aman', 'Bela', 'Chirag'],
        'Marks': [85, 90, 95],
        'Age': [17, 18, 17]}
df1 = pd.DataFrame(data)

# From list of lists
df2 = pd.DataFrame([[1, 'A'], [2, 'B'], [3, 'C']],
                   columns=['ID', 'Letter'])

# From dictionary of Series
df3 = pd.DataFrame({'A': pd.Series([1, 2, 3]),
                    'B': pd.Series([4, 5, 6])})
```

---

## 🔍 **4. Viewing Data**

```python
df1.head()        # First 5 rows
df1.tail(2)       # Last 2 rows
df1.shape         # (rows, columns)
df1.columns       # Column labels
df1.index         # Row labels
df1.dtypes        # Data types of columns
df1.info()        # Summary info
df1.describe()    # Statistical summary
```

---

## 🧭 **5. Accessing / Selecting Data**

```python
# Column selection
df1['Name']
df1[['Name', 'Marks']]

# Row selection
df1.loc[0]          # By label
df1.iloc[1]         # By integer index

# Specific value
df1.loc[0, 'Marks']
df1.iloc[1, 2]

# Conditional selection
df1[df1['Marks'] > 85]
df1[df1['Name'] == 'Bela']
```

---

## ✏️ **6. Modifying DataFrame**

```python
df_exams = pd.read_csv('StudentsPerformance.csv')
df_exams
```

|     | gender | race/ethnicity | parental level of education | lunch        | test preparation course | math score | reading score | writing score |
| --- | ------ | -------------- | --------------------------- | ------------ | ----------------------- | ---------- | ------------- | ------------- |
| 0   | female | group B        | bachelor's degree           | standard     | none                    | 72         | 72            | 74            |
| 1   | female | group C        | some college                | standard     | completed               | 69         | 90            | 88            |
| 2   | female | group B        | master's degree             | standard     | none                    | 90         | 95            | 93            |
| 3   | male   | group A        | associate's degree          | free/reduced | none                    | 47         | 57            | 44            |
| 4   | male   | group C        | some college                | standard     | none                    | 76         | 78            | 75            |
| ... | ...    | ...            | ...                         | ...          | ...                     | ...        | ...           | ...           |
| 995 | female | group E        | master's degree             | standard     | completed               | 88         | 99            | 95            |
| 996 | male   | group C        | high school                 | free/reduced | none                    | 62         | 55            | 55            |
| 997 | female | group C        | high school                 | free/reduced | completed               | 59         | 71            | 65            |
| 998 | female | group D        | some college                | standard     | completed               | 68         | 78            | 77            |
| 999 | female | group D        | some college                | free/reduced | none                    | 77         | 86            | 86            |
### ➤ Adding Columns

```python
df1['Grade'] = ['B', 'A', 'A+']
```

#### Using `assign()` to add multiple columns(best practice):
```python
df_exams = df_exams.assign(col1=data1, col2=data2)
```
It returns a new object (a copy) with all the original columns in addition to the new ones
#### `insert()`
Inserts a new column at a specific position or index
```python
series1 = pd.Series(np.random.randint(1,100,size=1000), index=np.arange(0,1000))
df_exams.insert(1,'test',series1)
# def_exams.insert(position_of_new_column, column_name, column_data)
df_exams
```
Output:

| gender | test   | race/ethnicity | parental level of education | lunch              | test preparation course | math score | reading score | writing score | score1 | score2 |     |
| ------ | ------ | -------------- | --------------------------- | ------------------ | ----------------------- | ---------- | ------------- | ------------- | ------ | ------ | --- |
| 0      | female | 74             | group B                     | bachelor's degree  | standard                | none       | 72            | 72            | 74     | 74     | 39  |
| 1      | female | 5              | group C                     | some college       | standard                | completed  | 69            | 90            | 88     | 5      | 28  |
| 2      | female | 86             | group B                     | master's degree    | standard                | none       | 90            | 95            | 93     | 86     | 38  |
| 3      | male   | 68             | group A                     | associate's degree | free/reduced            | none       | 47            | 57            | 44     | 68     | 7   |
| 4      | male   | 35             | group C                     | some college       | standard                | none       | 76            | 78            | 75     | 35     | 79  |
### ➤ Adding Rows

```python
new_row = {'Name': 'Deep', 'Marks': 88, 'Age': 18, 'Grade': 'A'}
df1 = pd.concat([df1, pd.DataFrame([new_row])], ignore_index=True)
```

### ➤ Updating Values

```python
df1.loc[0, 'Marks'] = 89
```

### ➤ Deleting Columns / Rows

```python
df1.drop('Age', axis=1, inplace=True)    # Drop column
df1.drop(2, axis=0, inplace=True)        # Drop row
```

---

## 🔢 **7. Basic Operations**

```python
df1['Marks'].max()
df1['Marks'].min()
df1['Marks'].mean()
df1['Marks'].sum()
df1['Marks'].count()
```

---

## 🧮 **8. Sorting Data**

```python
df1.sort_values(by='Marks')              # Ascending
df1.sort_values(by='Marks', ascending=False)   # Descending
df1.sort_index(ascending=False)          # Sort by index
```

```python
# sort descending by multiple columns and update dataframe
df_exams.sort_values(['math score', 'reading score'], ascending=False, inplace=True)
```

sort descending with a key function
```python
df_exams.sort_values(['race/ethinicity'], ascending=True, key=lambda a:a.str.lower())
```

---

## 🪜 **9. Renaming**

```python
df1.rename(columns={'Marks': 'Score'}, inplace=True)
```

---

## 🧹 **10. Handling Missing Data**

```python
import numpy as np

df1.loc[1, 'Marks'] = np.nan

# Check missing values
df1.isnull()

# Fill missing values
df1.fillna(0, inplace=True)

# Drop rows with missing values
df1.dropna(inplace=True)
```

---

## 📂 **11. Importing & Exporting Data**

### ➤ CSV Files

```python
# Read CSV
df = pd.read_csv('data.csv')

# Write to CSV
df.to_csv('output.csv', index=False)
```

### ➤ Excel Files

```python
# Read Excel
df = pd.read_excel('data.xlsx')

# Write Excel
df.to_excel('output.xlsx', index=False)
```

---

## 🧠 **12. Common DataFrame Functions**

```python
df1.columns
df1.index
df1.shape
df1.values
df1.T             # Transpose
df1.sort_values(by='Marks')
df1.sample(2)     # Random rows
```

---

## ⚙️ **13. Applying Functions**

```python
df1['Marks'].apply(lambda x: x + 5)
```

---

## 🔗 **14. Merging / Concatenating DataFrames**

```python
dfA = pd.DataFrame({'ID': [1, 2], 'Name': ['Aman', 'Bela']})
dfB = pd.DataFrame({'ID': [1, 2], 'Marks': [85, 90]})

# Merge on common column
merged = pd.merge(dfA, dfB, on='ID')

# Concatenate vertically
df_concat = pd.concat([dfA, dfB], axis=0)
```

---

## 🧾 **15. Grouping and Aggregation**

```python
data = {'Name': ['Aman', 'Bela', 'Aman', 'Bela'],
        'Subject': ['Math', 'Math', 'Science', 'Science'],
        'Marks': [85, 90, 80, 95]}

df = pd.DataFrame(data)

df.groupby('Name')['Marks'].mean()
df.groupby('Subject')['Marks'].max()
```

### Count value method
|     | gender | race/ethnicity | parental level of education | lunch        | test preparation course | math score | reading score | writing score |
| --- | ------ | -------------- | --------------------------- | ------------ | ----------------------- | ---------- | ------------- | ------------- |
| 0   | female | group B        | bachelor's degree           | standard     | none                    | 72         | 72            | 74            |
| 1   | female | group C        | some college                | standard     | completed               | 69         | 90            | 88            |
| 2   | female | group B        | master's degree             | standard     | none                    | 90         | 95            | 93            |
| 3   | male   | group A        | associate's degree          | free/reduced | none                    | 47         | 57            | 44            |
| 4   | male   | group C        | some college                | standard     | none                    | 76         | 78            | 75            |
| ... | ...    | ...            | ...                         | ...          | ...                     | ...        | ...           | ...           |
```python
# counting gender elements by category
df_exams['gender'].value_counts()
```
```
female    518
male      482
Name: gender, dtype: int64
```

```python
# return the relative frequency (divide all values by the sum of values)
df_exams['gender'].value_counts(normalize=True)
```
```
female 0.518 
male 0.482 
Name: gender, dtype: float64
```

---

## 🧮 **16. Filtering with Multiple Conditions**

```python
df[(df['Marks'] > 85) & (df['Subject'] == 'Math')]
```

---

## 🧭 **17. Index Manipulation**

```python
df.set_index('Name', inplace=True)
df.reset_index(inplace=True)
```
