# Experiment 15
## Visualize Pharmaceutical Data Using Python and Matplotlib

**Software Used:** Jupyter Notebook (Python + Matplotlib + Pandas)

---

## 🎯 Objective

To create line plots, scatter plots, bar charts, and a multi-panel dashboard visualizing pharmaceutical data — concentration-time profiles, dissolution studies, and patient health metrics — using Matplotlib.

---

## 🧠 Why This Experiment Matters

A number sitting in a spreadsheet rarely tells the full story — a graph does. This final experiment combines everything from Units I–V: Python fundamentals, Pandas data handling, and now visualization, to produce the kind of charts used in real pharmacokinetic studies, dissolution testing, and clinical dashboards.

---

## 🛠️ Step-by-Step Procedure

### Step 1: Open Jupyter Notebook
1. Create a new notebook: `pharma_visualization.ipynb`

### Step 2: Import Required Libraries
```python
import matplotlib.pyplot as plt
import numpy as np
import pandas as pd
```

### Step 3: Plot 1 — Concentration-Time Profile (Line Plot)
```python
time = np.array([0, 0.5, 1, 2, 4, 6, 8, 12, 24])
concentration = np.array([0, 4.2, 8.5, 12.3, 10.1, 7.2, 4.8, 1.9, 0.3])

plt.figure(figsize=(8, 5))
plt.plot(time, concentration, marker='o', color='blue', linewidth=2)
plt.axhline(y=8, color='green', linestyle='--', label='MEC (8 mg/L)')
plt.axhline(y=11, color='orange', linestyle='--', label='MTC (11 mg/L)')
plt.title("Concentration-Time Profile")
plt.xlabel("Time (hours)")
plt.ylabel("Plasma Concentration (mg/L)")
plt.legend()
plt.grid(True)
plt.tight_layout()
plt.show()
```
Run this cell — you should see a curve rising and falling, with two horizontal reference lines marking the therapeutic window.

### Step 4: Plot 2 — Dissolution Study (Multiple Line Comparison)
```python
time_min = [0, 5, 10, 15, 20, 30, 45, 60]
brand_A   = [0, 22, 45, 63, 73, 84, 91, 96]
generic_B = [0, 18, 38, 55, 65, 77, 86, 91]

plt.figure(figsize=(8, 5))
plt.plot(time_min, brand_A, marker='o', label='Brand A', linewidth=2)
plt.plot(time_min, generic_B, marker='s', label='Generic B', linewidth=2)
plt.axhline(y=80, color='black', linestyle='--', label='80% Target')

plt.title("Dissolution Profile Comparison")
plt.xlabel("Time (minutes)")
plt.ylabel("Drug Dissolved (%)")
plt.legend()
plt.grid(True)
plt.tight_layout()
plt.show()
```

### Step 5: Plot 3 — Dose-Response Scatter Plot
```python
doses = np.array([50, 100, 150, 200, 250, 300, 400, 500])
response = np.array([10, 22, 38, 54, 67, 78, 85, 88])

plt.figure(figsize=(7, 5))
plt.scatter(doses, response, color='purple', s=80)
plt.title("Dose-Response Relationship")
plt.xlabel("Dose (mg)")
plt.ylabel("Effect (%)")
plt.grid(True)
plt.tight_layout()
plt.show()
```

### Step 6: Plot 4 — Adverse Drug Reaction Bar Chart
```python
drugs = ["Paracetamol", "Amoxicillin", "Metformin", "Ibuprofen", "Aspirin"]
adr_count = [120, 85, 60, 140, 95]

plt.figure(figsize=(8, 5))
bars = plt.bar(drugs, adr_count, color=['#e74c3c','#3498db','#2ecc71','#f39c12','#9b59b6'])

for bar, count in zip(bars, adr_count):
    plt.text(bar.get_x() + bar.get_width()/2, bar.get_height() + 2, str(count), ha='center')

plt.title("ADR Reports by Drug (Annual)")
plt.xlabel("Drug Name")
plt.ylabel("Number of ADR Reports")
plt.xticks(rotation=20)
plt.tight_layout()
plt.show()
```

### Step 7: Plot 5 — Patient Health Dashboard (Multi-Panel Subplot)
```python
df = pd.DataFrame({
    "Patient": ["P1","P2","P3","P4","P5","P6"],
    "Glucose": [88, 145, 160, 92, 110, 200],
    "BP":      [118, 145, 160, 108, 130, 170],
})

fig, axes = plt.subplots(1, 2, figsize=(12, 5))

axes[0].bar(df["Patient"], df["Glucose"],
            color=['red' if g > 126 else 'steelblue' for g in df["Glucose"]])
axes[0].axhline(y=126, color='red', linestyle='--', label='Diabetes threshold')
axes[0].set_title("Fasting Glucose")
axes[0].set_ylabel("mg/dL")
axes[0].legend()

axes[1].bar(df["Patient"], df["BP"],
            color=['red' if b > 140 else 'steelblue' for b in df["BP"]])
axes[1].axhline(y=140, color='red', linestyle='--', label='Hypertension threshold')
axes[1].set_title("Systolic Blood Pressure")
axes[1].set_ylabel("mmHg")
axes[1].legend()

plt.suptitle("Patient Health Dashboard", fontsize=14, fontweight='bold')
plt.tight_layout()
plt.show()
```

### Step 8: Save Each Chart as an Image File
```python
# Re-run with savefig added, e.g. for the dashboard:
fig, axes = plt.subplots(1, 2, figsize=(12, 5))

axes[0].bar(df["Patient"], df["Glucose"],
            color=['red' if g > 126 else 'steelblue' for g in df["Glucose"]])
axes[0].set_title("Fasting Glucose")

axes[1].bar(df["Patient"], df["BP"],
            color=['red' if b > 140 else 'steelblue' for b in df["BP"]])
axes[1].set_title("Systolic Blood Pressure")

plt.suptitle("Patient Health Dashboard")
plt.tight_layout()
plt.savefig("patient_dashboard.png", dpi=150)
plt.show()

print("✅ Saved as patient_dashboard.png")
```

### Step 9: Save Your Notebook
- File → Save and Checkpoint
- Filename: `pharma_visualization.ipynb`

---

## ✅ Expected Output

Five distinct, properly labelled visualizations — a PK line plot, a dissolution comparison line plot, a dose-response scatter plot, an ADR bar chart, and a two-panel patient health dashboard — with at least one chart exported as a `.png` image file.

---

## 📝 Viva/Record Questions

1. Why is a line plot more appropriate than a bar chart for a concentration-time profile?
2. What does the `axhline()` function do, and why was it used to mark MEC/MTC?
3. In Step 7, what does the list comprehension `['red' if g > 126 else 'steelblue' for g in df["Glucose"]]` actually do?
4. Why might a hospital prefer exporting a chart as `.png` rather than just leaving it inside a Jupyter Notebook?

---

## 🔁 Practice Variation

Create a pie chart showing the proportion of patients in each `Glucose_Status` category (Normal / Pre-diabetic / Diabetic) using the dataset from Experiment 14.
