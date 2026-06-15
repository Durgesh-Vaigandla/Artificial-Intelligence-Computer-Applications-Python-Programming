# Unit III – Day 2 (2 Hours)
## NumPy Arrays, File Handling & CSV Data

---

## 🎯 Session Goals
By the end of this session, students will be able to:
- Use NumPy for basic numerical computations on healthcare data
- Read and write CSV files using Python
- Handle structured healthcare datasets

---

## ⏱️ Session Plan (2 Hours)

| Time | Topic |
|------|-------|
| 0:00 – 0:10 | Recap Day 1 |
| 0:10 – 0:45 | NumPy arrays — intro + pharmacy use |
| 0:45 – 1:20 | Reading & writing CSV files |
| 1:20 – 1:50 | Working with a healthcare dataset |
| 1:50 – 2:00 | Recap + Q&A |

---

## 1. Introduction to NumPy

```bash
pip install numpy
```

```python
import numpy as np
```

> 💬 "NumPy is the engine behind all scientific computing in Python. Pandas, Matplotlib — all built on NumPy."

### Why NumPy over plain lists?

```python
# Plain list — slow
weights = [55, 70, 62, 80, 48]
doubled = [w * 2 for w in weights]

# NumPy — fast and clean
weights = np.array([55, 70, 62, 80, 48])
doubled = weights * 2    # No loop needed!
```

---

## 2. NumPy Arrays for Healthcare Data

### Creating Arrays

```python
# Blood glucose readings (mg/dL) over 7 days
glucose = np.array([95, 110, 88, 145, 102, 98, 120])

print("All readings:", glucose)
print("Average    :", np.mean(glucose))
print("Max        :", np.max(glucose))
print("Min        :", np.min(glucose))
print("Std Dev    :", np.std(glucose).round(2))
```

### Drug Concentration Over Time

```python
# Concentration-time profile (pharmacokinetics)
time_hours = np.array([0, 1, 2, 4, 6, 8, 12])
concentration = np.array([0, 8.5, 12.3, 10.1, 7.2, 4.8, 1.9])    # mg/L

print(f"Peak concentration: {np.max(concentration)} mg/L")
print(f"Time at peak: {time_hours[np.argmax(concentration)]} hours")
print(f"AUC (approx): {np.trapz(concentration, time_hours):.2f} mg·h/L")
```

### Boolean Filtering (Flagging Abnormal Values)

```python
glucose = np.array([95, 110, 88, 145, 102, 98, 120, 200, 75])

# Flag values above normal fasting (>100 mg/dL)
high_glucose = glucose[glucose > 100]
print("High glucose readings:", high_glucose)
print("Count above normal:", len(high_glucose))
```

---

## 3. File Handling — Reading & Writing Text Files

### Writing a File

```python
with open("patient_notes.txt", "w") as f:
    f.write("Patient: Rahul Sharma\n")
    f.write("Drug: Metformin 500mg\n")
    f.write("Notes: Monitor glucose weekly\n")

print("File written successfully")
```

### Reading a File

```python
with open("patient_notes.txt", "r") as f:
    content = f.read()
    print(content)
```

### Appending to a File

```python
with open("patient_notes.txt", "a") as f:
    f.write("Follow-up: 2 weeks\n")
```

---

## 4. CSV Files — Healthcare Datasets

### What is CSV?
> Comma-Separated Values — the most common format for healthcare data exchange.

### Writing a CSV File

```python
import csv

patients = [
    ["PatientID", "Name", "Age", "Weight", "Glucose", "BP_Systolic"],
    ["P001", "Rahul", 45, 72, 110, 130],
    ["P002", "Priya", 32, 58, 92, 118],
    ["P003", "Suresh", 60, 85, 145, 145],
    ["P004", "Anitha", 28, 55, 88, 110],
    ["P005", "Mohan", 52, 78, 160, 155],
]

with open("patients.csv", "w", newline="") as f:
    writer = csv.writer(f)
    writer.writerows(patients)

print("CSV file created")
```

### Reading a CSV File

```python
import csv

with open("patients.csv", "r") as f:
    reader = csv.DictReader(f)
    for row in reader:
        print(f"{row['Name']} — Glucose: {row['Glucose']} mg/dL")
```

### Filtering CSV Data

```python
with open("patients.csv", "r") as f:
    reader = csv.DictReader(f)
    print("\n=== HIGH GLUCOSE PATIENTS ===")
    for row in reader:
        if int(row["Glucose"]) > 120:
            print(f"⚠️ {row['Name']} — Glucose: {row['Glucose']} mg/dL")
```

---

## 5. Introduction to Database Concepts

### Key Terms

| Term | Meaning | Example |
|------|---------|---------|
| **Table** | Grid of rows + columns | Patient records table |
| **Record (Row)** | One complete entry | One patient's data |
| **Field (Column)** | One attribute | Age, Name, Drug |
| **Primary Key** | Unique identifier | PatientID |
| **Foreign Key** | Links to another table | PrescriptionID references PatientID |

### Example Structure

```
PATIENTS Table
--------------
PatientID (PK) | Name | Age | BloodGroup

PRESCRIPTIONS Table
-------------------
RxID (PK) | PatientID (FK) | Drug | Dose | Date
```

> 💬 "This is exactly how hospital software stores data. Every EHR system is built on databases like this."

---

## 🧠 Key Takeaways

1. NumPy makes numerical computations fast and clean — critical for lab data
2. `with open()` safely reads and writes files in Python
3. CSV is the standard format for sharing healthcare datasets
4. Database concepts (table, record, field, key) are fundamental to understanding hospital systems

---

## 💻 Practice Exercises

**Exercise 1:** Create a NumPy array of 10 blood pressure readings. Calculate mean, max, min. Print how many are above 140 (hypertensive).

**Exercise 2:** Write a CSV file with 5 drug records (DrugName, Dose, Category, RequiresPrescription). Read it back and print only prescription drugs.

**Exercise 3:** Read the patients.csv file and calculate the average glucose of all patients.
