# Unit V – Day 3 (2 Hours)
## AI in Drug Discovery, Healthcare Analytics & Mini Project

---

## 🎯 Session Goals
- Understand AI and ML applications in drug discovery and clinical decision support
- Build the Unit V capstone: a Pharmaceutical Data Analysis mini-project
- Consolidate the full course with a real end-to-end Python program

---

## ⏱️ Session Plan (2 Hours)

| Time | Topic |
|------|-------|
| 0:00 – 0:10 | Recap Day 2 |
| 0:10 – 0:40 | AI & ML in pharmacy — concepts + examples |
| 0:40 – 1:00 | Intro to mini-project |
| 1:00 – 1:50 | Build mini-project together |
| 1:50 – 2:00 | Course wrap-up + Q&A |

---

## 1. AI & Machine Learning in Drug Discovery

### Traditional vs AI-Assisted Drug Discovery

| Stage | Traditional | AI-Assisted |
|-------|-------------|-------------|
| Target identification | Years of lab research | AI scans genomic data in hours |
| Compound screening | Test one by one | AI screens millions virtually |
| Clinical prediction | Trial and error | ML predicts success probability |
| Time to market | 10–15 years | Potentially 3–5 years |
| Cost | $2.6 billion avg | Significantly reduced |

### Real AI Tools in Pharmacy & Healthcare

| Tool | What it does |
|------|-------------|
| **AlphaFold (DeepMind)** | Predicts 3D protein structures — critical for drug targets |
| **IBM Watson for Oncology** | Recommends cancer treatment plans from literature |
| **AtomNet (Atomwise)** | Screens drug candidates using deep learning |
| **Insilico Medicine** | AI-generated drug molecule design |
| **Google Health** | Detects diabetic retinopathy from eye scans |

---

## 2. Healthcare Analytics — What ML Actually Does

### Types of ML Problems in Healthcare

**Classification** — "Which category does this patient belong to?"
```
Input: age, glucose, BMI, BP
Output: Diabetic / Non-Diabetic
```

**Regression** — "What value will this be?"
```
Input: patient data, drug dose
Output: predicted plasma concentration
```

**Clustering** — "Which patients are similar?"
```
Input: patient records
Output: risk groups (low / medium / high)
```

### Rule-Based AI vs Machine Learning

```python
# Rule-based (what we built in Unit II)
def classify_diabetes(glucose):
    if glucose >= 126:
        return "Diabetic"
    elif glucose >= 100:
        return "Pre-diabetic"
    else:
        return "Normal"

# Machine Learning approach (concept)
# model = train(patient_data, labels)  # learns rules from thousands of patients
# prediction = model.predict(new_patient)  # applies learned rules
```

> 💬 "Rule-based AI uses rules WE write. Machine Learning lets the computer DISCOVER the rules from data. With thousands of patients, ML finds patterns a human would miss."

---

## 3. Clinical Decision Support — Python Simulation

```python
# Simulated CDSS — Risk Score Calculator
def calculate_patient_risk(age, bmi, glucose, bp_systolic, is_smoker, is_diabetic):
    score = 0
    reasons = []

    if age > 60:
        score += 2
        reasons.append("Age > 60")
    if bmi > 30:
        score += 2
        reasons.append("Obese (BMI > 30)")
    if glucose > 126:
        score += 3
        reasons.append("Diabetic glucose level")
    elif glucose > 100:
        score += 1
        reasons.append("Pre-diabetic glucose level")
    if bp_systolic > 140:
        score += 2
        reasons.append("Hypertension")
    if is_smoker:
        score += 2
        reasons.append("Smoker")
    if is_diabetic:
        score += 2
        reasons.append("Known diabetic")

    if score >= 7:
        risk = "HIGH"
    elif score >= 4:
        risk = "MODERATE"
    else:
        risk = "LOW"

    return score, risk, reasons

# Test
score, risk, reasons = calculate_patient_risk(
    age=65, bmi=32, glucose=148, bp_systolic=155,
    is_smoker=False, is_diabetic=True
)

print(f"Risk Score : {score}")
print(f"Risk Level : {risk}")
print(f"Factors    : {', '.join(reasons)}")
```

---

## 4. Mini Project — Pharmaceutical Data Analyzer

### Experiment 14 & 15 from Syllabus

```python
# ============================================================
# PHARMACEUTICAL DATA ANALYZER
# Mini Project — Unit V Capstone
# ============================================================

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

# --- Step 1: Load / Create Dataset ---
data = {
    "PatientID": ["P001","P002","P003","P004","P005","P006","P007","P008","P009","P010"],
    "Name":      ["Rahul","Priya","Suresh","Anitha","Mohan","Kavitha","Vijay","Suma","Ravi","Meena"],
    "Age":       [45, 32, 61, 28, 52, 67, 38, 55, 43, 60],
    "Weight":    [72, 58, 85, 55, 78, 68, 74, 63, 80, 70],
    "Height":    [1.72, 1.60, 1.68, 1.58, 1.75, 1.63, 1.70, 1.55, 1.78, 1.62],
    "Glucose":   [110, 92, 145, 88, 160, 200, 98, 135, 105, 178],
    "BP":        [130, 118, 145, 108, 155, 170, 122, 148, 128, 162],
    "Drug":      ["Metformin","None","Metformin","None","Metformin","Insulin",
                  "None","Metformin","None","Insulin"]
}

df = pd.DataFrame(data)

# --- Step 2: Calculate BMI ---
df["BMI"] = (df["Weight"] / df["Height"]**2).round(1)

def classify_bmi(bmi):
    if bmi < 18.5: return "Underweight"
    elif bmi < 25: return "Normal"
    elif bmi < 30: return "Overweight"
    else: return "Obese"

df["BMI_Category"] = df["BMI"].apply(classify_bmi)

# --- Step 3: Classify Glucose ---
def classify_glucose(g):
    if g >= 126: return "Diabetic"
    elif g >= 100: return "Pre-diabetic"
    else: return "Normal"

df["Glucose_Status"] = df["Glucose"].apply(classify_glucose)

# --- Step 4: Summary Statistics ---
print("=" * 50)
print("   PHARMACEUTICAL DATA ANALYSIS REPORT")
print("=" * 50)
print(f"\nTotal Patients: {len(df)}")
print(f"\nGlucose Statistics:")
print(f"  Mean  : {df['Glucose'].mean():.1f} mg/dL")
print(f"  Max   : {df['Glucose'].max()} mg/dL")
print(f"  Min   : {df['Glucose'].min()} mg/dL")

print(f"\nGlucose Status Distribution:")
print(df["Glucose_Status"].value_counts().to_string())

print(f"\nBMI Category Distribution:")
print(df["BMI_Category"].value_counts().to_string())

print(f"\nDrug Prescriptions:")
print(df["Drug"].value_counts().to_string())

# --- Step 5: High Risk Patients ---
print("\n⚠️  HIGH RISK PATIENTS (Glucose > 140 AND BP > 140):")
high_risk = df[(df["Glucose"] > 140) & (df["BP"] > 140)]
if high_risk.empty:
    print("  None identified.")
else:
    for _, row in high_risk.iterrows():
        print(f"  {row['Name']} — Glucose: {row['Glucose']}, BP: {row['BP']}, Drug: {row['Drug']}")

# --- Step 6: Visualizations ---
fig, axes = plt.subplots(2, 2, figsize=(14, 10))
fig.suptitle("Pharmaceutical Patient Data Dashboard", fontsize=15, fontweight='bold')

# Plot 1: Glucose by Patient
colors_g = ['red' if g >= 126 else 'orange' if g >= 100 else 'steelblue' for g in df["Glucose"]]
axes[0, 0].bar(df["Name"], df["Glucose"], color=colors_g)
axes[0, 0].axhline(y=126, color='red', linestyle='--', label='Diabetic (126)')
axes[0, 0].axhline(y=100, color='orange', linestyle='--', label='Pre-diabetic (100)')
axes[0, 0].set_title("Fasting Glucose by Patient")
axes[0, 0].set_ylabel("Glucose (mg/dL)")
axes[0, 0].tick_params(axis='x', rotation=45)
axes[0, 0].legend(fontsize=8)

# Plot 2: Blood Pressure
colors_bp = ['red' if b > 140 else 'steelblue' for b in df["BP"]]
axes[0, 1].bar(df["Name"], df["BP"], color=colors_bp)
axes[0, 1].axhline(y=140, color='red', linestyle='--', label='Hypertension (140)')
axes[0, 1].set_title("Systolic Blood Pressure")
axes[0, 1].set_ylabel("BP (mmHg)")
axes[0, 1].tick_params(axis='x', rotation=45)
axes[0, 1].legend(fontsize=8)

# Plot 3: BMI Scatter vs Age
bmi_colors = {'Underweight': 'blue', 'Normal': 'green', 'Overweight': 'orange', 'Obese': 'red'}
for cat, color in bmi_colors.items():
    mask = df["BMI_Category"] == cat
    axes[1, 0].scatter(df[mask]["Age"], df[mask]["BMI"], label=cat, color=color, s=80)
axes[1, 0].axhline(y=25, color='orange', linestyle='--', alpha=0.6)
axes[1, 0].axhline(y=30, color='red', linestyle='--', alpha=0.6)
axes[1, 0].set_title("BMI vs Age")
axes[1, 0].set_xlabel("Age")
axes[1, 0].set_ylabel("BMI")
axes[1, 0].legend(fontsize=8)

# Plot 4: Glucose Status Pie
status_counts = df["Glucose_Status"].value_counts()
axes[1, 1].pie(status_counts, labels=status_counts.index,
               autopct='%1.0f%%', colors=['red','orange','steelblue'], startangle=90)
axes[1, 1].set_title("Glucose Status Distribution")

plt.tight_layout()
plt.show()

# --- Step 7: Save Report ---
df.to_csv("patient_analysis_report.csv", index=False)
print("\n✅ Report saved to patient_analysis_report.csv")
```

---

## 5. Course Wrap-Up — What You've Learned

| Unit | Skills Gained |
|------|--------------|
| **Unit I** | AI concepts, healthcare IT, Python basics, variables, strings |
| **Unit II** | Conditions, loops, functions, dosage calculators |
| **Unit III** | Data structures, NumPy, CSV files, databases |
| **Unit IV** | HTML, MySQL, MS Access, Pandas, data cleaning |
| **Unit V** | Visualization, PK profiles, AI concepts, full data pipeline |

> 💬 **Final message to students:**
> "You started this course not knowing what Python was. You are finishing it having built a pharmaceutical data analyzer, a patient information system, and clinical visualizations. These are real skills used in hospital software and pharmaceutical research today."

---

## 🧠 Final Key Takeaways

1. AI in pharmacy = drug discovery, CDSS, imaging, personalized medicine
2. ML learns patterns from data — we used rule-based approximations to understand the concept
3. A complete data pipeline: load → clean → analyze → visualize → report
4. Python + Pandas + Matplotlib = the core toolkit for healthcare data science

---

## 💻 Final Mini Project Submission Task

Extend the mini-project with:
1. Add 5 more patients of your own
2. Add a `Cholesterol` column and classify (Normal < 200, Borderline 200–239, High ≥ 240)
3. Add a 5th visualization — cholesterol bar chart
4. Save the final dashboard as an image using `plt.savefig("dashboard.png")`
5. Write a 10-line interpretation of what the data tells you about this patient group

**This is your course capstone submission.**
