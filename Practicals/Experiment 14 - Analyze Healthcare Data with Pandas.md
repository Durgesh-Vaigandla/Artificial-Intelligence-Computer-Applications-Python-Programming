# Experiment 14
## Analyze Healthcare Data Using Python and Pandas

**Software Used:** Jupyter Notebook (Python + Pandas)

---

## 🎯 Objective

To load, explore, clean, and analyze a healthcare dataset using the Pandas library — calculating summary statistics and identifying at-risk patients.

---

## 🧠 Why This Experiment Matters

Real pharmacy and hospital work increasingly involves analyzing patient datasets — checking trends in glucose levels, identifying high-risk patients, or summarizing a clinic's patient population. This experiment is your hands-on introduction to that exact workflow, building directly on Unit IV's Pandas content.

---

## 🛠️ Step-by-Step Procedure

### Step 1: Open Jupyter Notebook
1. Launch Jupyter Notebook
2. Create a new notebook: `healthcare_data_analysis.ipynb`

### Step 2: Import Required Libraries
```python
import pandas as pd
import numpy as np
```

### Step 3: Create the Dataset
For this experiment, we'll create a sample dataset directly in Python (in practice, you might load this from `patients.csv` exported in Experiment 12):

```python
data = {
    "PatientID": ["P001","P002","P003","P004","P005","P006","P007","P008","P009","P010"],
    "Name": ["Rahul","Priya","Suresh","Anitha","Mohan","Kavitha","Vijay","Suma","Ravi","Meena"],
    "Age": [45, 32, 61, 28, 52, 67, 38, 55, 43, 60],
    "Weight": [72, 58, 85, 55, 78, 68, 74, 63, 80, 70],
    "Height": [1.72, 1.60, 1.68, 1.58, 1.75, 1.63, 1.70, 1.55, 1.78, 1.62],
    "Glucose": [110, 92, 145, 88, 160, 200, 98, 135, 105, 178],
    "BP_Systolic": [130, 118, 145, 108, 155, 170, 122, 148, 128, 162],
}

df = pd.DataFrame(data)
print(df)
```

### Step 4: Explore the Dataset
```python
print("Shape (rows, columns):", df.shape)
print("\nColumn names:", df.columns.tolist())
print("\nData types:\n", df.dtypes)
print("\nFirst 5 rows:\n", df.head())
print("\nStatistical summary:\n", df.describe())
```

### Step 5: Check for Missing Values
```python
print("Missing values per column:")
print(df.isnull().sum())
```
(In this clean dataset, you should see zero missing values — proceed to Step 6 to intentionally introduce some for practice.)

### Step 6: Introduce and Handle Missing Data (Practice)
```python
# Introduce some missing values for practice
df_messy = df.copy()
df_messy.loc[2, "Glucose"] = np.nan
df_messy.loc[5, "BP_Systolic"] = np.nan

print("Missing values introduced:")
print(df_messy.isnull().sum())

# Fill missing values with column mean
df_messy["Glucose"] = df_messy["Glucose"].fillna(df_messy["Glucose"].mean())
df_messy["BP_Systolic"] = df_messy["BP_Systolic"].fillna(df_messy["BP_Systolic"].mean())

print("\nAfter cleaning:")
print(df_messy.isnull().sum())
```

### Step 7: Calculate BMI for Every Patient
```python
df["BMI"] = (df["Weight"] / (df["Height"] ** 2)).round(1)
print(df[["Name", "Weight", "Height", "BMI"]])
```

### Step 8: Classify Patients by Health Risk
```python
def classify_glucose(glucose):
    if glucose >= 126:
        return "Diabetic"
    elif glucose >= 100:
        return "Pre-diabetic"
    else:
        return "Normal"

df["Glucose_Status"] = df["Glucose"].apply(classify_glucose)
print(df[["Name", "Glucose", "Glucose_Status"]])
```

### Step 9: Filter — Find High-Risk Patients
```python
# Patients with both high glucose AND high blood pressure
high_risk = df[(df["Glucose"] > 140) & (df["BP_Systolic"] > 140)]
print("HIGH RISK PATIENTS:")
print(high_risk[["Name", "Age", "Glucose", "BP_Systolic"]])
```

### Step 10: Group and Summarize
```python
print("Average Glucose by Diagnosis Group:")
print(df.groupby("Glucose_Status")["Glucose"].mean().round(1))

print("\nPatient Count by Diagnosis:")
print(df["Glucose_Status"].value_counts())

print("\nOverall Summary:")
print(f"Average Age: {df['Age'].mean():.1f} years")
print(f"Average BMI: {df['BMI'].mean():.1f}")
print(f"Highest Glucose Reading: {df['Glucose'].max()} mg/dL ({df.loc[df['Glucose'].idxmax(), 'Name']})")
```

### Step 11: Sort and Export Results
```python
# Sort by glucose, highest first
sorted_df = df.sort_values("Glucose", ascending=False)
print(sorted_df[["Name", "Glucose", "Glucose_Status"]])

# Save the cleaned, analyzed dataset
df.to_csv("analyzed_patient_data.csv", index=False)
print("\n✅ Saved to analyzed_patient_data.csv")
```

### Step 12: Save Your Notebook
- File → Save and Checkpoint
- Ensure filename is `healthcare_data_analysis.ipynb`

---

## ✅ Expected Output

A complete analysis notebook showing: dataset exploration, missing-value handling, BMI calculation, glucose-based risk classification, filtered high-risk patient identification, grouped summary statistics, and a final exported CSV file.

---

## 📝 Viva/Record Questions

1. What is the difference between `df.head()` and `df.describe()`?
2. Why is `fillna()` with the column mean a reasonable strategy for missing glucose readings — and when might it NOT be appropriate?
3. What does the `&` operator do in the high-risk patient filter, compared to `and`?
4. What is the purpose of `groupby()` in Step 10?

---

## 🔁 Practice Variation

Add a `BMI_Category` column (Underweight/Normal/Overweight/Obese) using `.apply()` similar to Step 8, then find patients who are BOTH "Obese" AND "Diabetic" — a combined high-priority intervention group.
