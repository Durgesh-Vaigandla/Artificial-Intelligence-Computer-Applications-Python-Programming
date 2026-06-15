# Unit IV – Day 3 (2 Hours)
## Pandas — DataFrames, Data Cleaning & Healthcare Dataset Analysis

---

## 🎯 Session Goals
By the end of this session, students will be able to:
- Use Pandas Series and DataFrames to work with healthcare data
- Read CSV and Excel files into Python
- Clean data — handle missing values, filter, and sort healthcare datasets

---

## ⏱️ Session Plan (2 Hours)

| Time | Topic |
|------|-------|
| 0:00 – 0:10 | Recap Day 2 |
| 0:10 – 0:40 | Pandas Series & DataFrames |
| 0:40 – 1:10 | Reading CSV / Excel + exploring data |
| 1:10 – 1:50 | Data cleaning — missing values, filtering |
| 1:50 – 2:00 | Recap + Q&A |

---

## 1. Introduction to Pandas

```bash
pip install pandas openpyxl
```

```python
import pandas as pd
```

> 💬 "If NumPy is the engine, Pandas is the steering wheel. It makes data analysis readable, fast, and practical."

---

## 2. Pandas Series

> A **Series** is a one-dimensional labeled array — like a single column.

```python
import pandas as pd

# Blood pressure readings with patient labels
bp_readings = pd.Series(
    [130, 145, 118, 160, 122, 138],
    index=["P001", "P002", "P003", "P004", "P005", "P006"]
)

print(bp_readings)
print(f"\nAverage BP: {bp_readings.mean():.1f}")
print(f"Max BP    : {bp_readings.max()}")
print(f"High BP patients:\n{bp_readings[bp_readings > 140]}")
```

---

## 3. Pandas DataFrames

> A **DataFrame** is a two-dimensional table — rows and columns, like a spreadsheet.

```python
data = {
    "PatientID": ["P001", "P002", "P003", "P004", "P005"],
    "Name": ["Rahul", "Priya", "Suresh", "Anitha", "Mohan"],
    "Age": [45, 32, 60, 28, 52],
    "Weight": [72, 58, 85, 55, 78],
    "Glucose": [110, 92, 145, 88, 160],
    "BP_Systolic": [130, 118, 145, 108, 155],
    "Diagnosis": ["Hypertension", "Normal", "Diabetes", "Normal", "Diabetes"]
}

df = pd.DataFrame(data)
print(df)
```

### Exploring the DataFrame

```python
print(df.shape)          # (5, 7) — rows, columns
print(df.columns)        # Column names
print(df.dtypes)         # Data types
print(df.describe())     # Statistics summary
print(df.head(3))        # First 3 rows
```

---

## 4. Reading CSV & Excel Files

### Read CSV

```python
# Read a healthcare CSV file
df = pd.read_csv("patients.csv")
print(df.head())
print(df.info())
```

### Read Excel

```python
df = pd.read_excel("pharmacy_data.xlsx", sheet_name="Sheet1")
print(df.head())
```

### Save Back to CSV

```python
df.to_csv("cleaned_patients.csv", index=False)
```

---

## 5. Data Cleaning

### Checking for Missing Values

```python
# Create sample data with missing values
import numpy as np

data_with_missing = {
    "PatientID": ["P001", "P002", "P003", "P004", "P005"],
    "Name": ["Rahul", "Priya", None, "Anitha", "Mohan"],
    "Age": [45, None, 60, 28, 52],
    "Glucose": [110, 92, 145, None, 160],
    "BP_Systolic": [130, 118, None, 108, 155],
}

df = pd.DataFrame(data_with_missing)

# Check missing values
print("Missing values per column:")
print(df.isnull().sum())
```

### Handling Missing Values

```python
# Option 1: Drop rows with missing values
df_dropped = df.dropna()

# Option 2: Fill missing values with mean
df["Age"] = df["Age"].fillna(df["Age"].mean())
df["Glucose"] = df["Glucose"].fillna(df["Glucose"].median())

# Option 3: Fill with a specific value
df["Name"] = df["Name"].fillna("Unknown")
df["BP_Systolic"] = df["BP_Systolic"].fillna(120)   # default normal

print("\nAfter cleaning:")
print(df)
print("\nMissing values after cleaning:")
print(df.isnull().sum())
```

---

## 6. Filtering & Sorting Healthcare Data

```python
# Full patient dataset
df = pd.DataFrame({
    "PatientID": ["P001", "P002", "P003", "P004", "P005", "P006"],
    "Name": ["Rahul", "Priya", "Suresh", "Anitha", "Mohan", "Kavitha"],
    "Age": [45, 32, 60, 28, 52, 67],
    "Glucose": [110, 92, 145, 88, 160, 200],
    "BP_Systolic": [130, 118, 145, 108, 155, 170],
    "Diagnosis": ["Hypertension", "Normal", "Diabetes", "Normal", "Diabetes", "Diabetes"]
})

# Filter: Diabetic patients only
diabetic = df[df["Diagnosis"] == "Diabetes"]
print("Diabetic Patients:")
print(diabetic[["Name", "Age", "Glucose"]])

# Filter: High glucose (>120)
high_glucose = df[df["Glucose"] > 120]
print("\nHigh Glucose Patients:")
print(high_glucose[["Name", "Glucose"]])

# Filter: Senior patients with hypertension or diabetes
risk_seniors = df[(df["Age"] > 50) & (df["Diagnosis"] != "Normal")]
print("\nAt-Risk Senior Patients:")
print(risk_seniors)

# Sort by glucose level (highest first)
sorted_df = df.sort_values("Glucose", ascending=False)
print("\nPatients by Glucose (highest first):")
print(sorted_df[["Name", "Glucose", "Diagnosis"]])
```

---

## 7. Summary Statistics by Group

```python
# Average glucose by diagnosis group
print("Average Glucose by Diagnosis:")
print(df.groupby("Diagnosis")["Glucose"].mean())

# Count patients per diagnosis
print("\nPatient Count by Diagnosis:")
print(df["Diagnosis"].value_counts())
```

---

## 🧠 Key Takeaways

1. **Series** = one column of data with labels
2. **DataFrame** = full table — rows and columns
3. `read_csv()` / `read_excel()` — loads real data files into Python
4. `isnull()`, `fillna()`, `dropna()` — essential data cleaning tools
5. Filtering with conditions (`df[df["col"] > value]`) finds specific patient groups

---

## 💻 Practice Exercises

**Exercise 1:** Create a DataFrame of 8 patients with columns: Name, Age, Weight, Glucose, BP. Calculate mean glucose and mean BP.

**Exercise 2:** Introduce 3 missing values into your DataFrame. Fill them using mean/median. Verify no missing values remain.

**Exercise 3:** Filter your DataFrame to find:
- All patients with glucose > 140
- Patients older than 50 AND BP > 140
- Sort by age, youngest first

**Exercise 4:** Save your cleaned DataFrame to a CSV file. Read it back and confirm the data is intact.
