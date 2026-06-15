# Unit V – Day 1 (2 Hours)
## NumPy for Scientific Computing & Data Visualization with Matplotlib

---

## 🎯 Session Goals
By the end of this session, students will be able to:
- Use NumPy for advanced scientific computations on pharmaceutical data
- Create line plots and scatter plots using Matplotlib
- Visualize concentration-time profiles and dissolution data

---

## ⏱️ Session Plan (2 Hours)

| Time | Topic |
|------|-------|
| 0:00 – 0:10 | Recap Unit IV |
| 0:10 – 0:40 | NumPy scientific operations |
| 0:40 – 2:00 | Matplotlib — line plots, scatter plots |

---

## 1. NumPy Scientific Operations

```bash
pip install numpy matplotlib
```

```python
import numpy as np
import matplotlib.pyplot as plt
```

### Array Operations (Recap + Extend)

```python
# Pharmacokinetic data
time = np.array([0, 0.5, 1, 2, 4, 6, 8, 12, 24])         # hours
concentration = np.array([0, 4.2, 8.5, 12.3, 10.1, 7.2, 4.8, 1.9, 0.3])  # mg/L

print(f"Peak Concentration: {np.max(concentration)} mg/L")
print(f"Time to Peak      : {time[np.argmax(concentration)]} hrs")
print(f"AUC (Trapezoid)   : {np.trapz(concentration, time):.2f} mg·h/L")
print(f"Mean Concentration: {np.mean(concentration):.2f} mg/L")
```

### Generating Smooth Curves for PK Profiles

```python
# One-compartment model: C(t) = C0 * e^(-k*t)
C0 = 12.3      # peak concentration (mg/L)
k = 0.15       # elimination rate constant (1/hr)

time_smooth = np.linspace(0, 24, 100)   # 100 points from 0 to 24 hours
conc_smooth = C0 * np.exp(-k * time_smooth)

print("First 5 predicted concentrations:", conc_smooth[:5].round(2))
```

---

## 2. Matplotlib — Line Plots

### Basic Line Plot

```python
plt.figure(figsize=(8, 5))
plt.plot(time, concentration, marker='o', color='blue', linewidth=2, label='Drug A')
plt.title("Concentration-Time Profile")
plt.xlabel("Time (hours)")
plt.ylabel("Plasma Concentration (mg/L)")
plt.legend()
plt.grid(True)
plt.show()
```

### Smooth PK Curve

```python
plt.figure(figsize=(9, 5))

# Actual data points
plt.scatter(time, concentration, color='red', zorder=5, label='Observed Data')

# Smooth model curve
plt.plot(time_smooth, conc_smooth, color='blue', linewidth=2, label='PK Model (1-compartment)')

# Therapeutic range
plt.axhline(y=8, color='green', linestyle='--', label='MEC (8 mg/L)')
plt.axhline(y=11, color='orange', linestyle='--', label='MTC (11 mg/L)')

plt.fill_between(time_smooth, 8, 11, alpha=0.1, color='green', label='Therapeutic Window')

plt.title("Pharmacokinetic Profile with Therapeutic Window")
plt.xlabel("Time (hours)")
plt.ylabel("Plasma Concentration (mg/L)")
plt.legend()
plt.grid(True)
plt.tight_layout()
plt.show()
```

> 💬 "The area between MEC and MTC is the therapeutic window. AI systems use this kind of data to recommend optimal dosing intervals."

---

## 3. Dissolution Study Visualization

```python
# Dissolution data for 3 formulations
time_points = np.array([0, 5, 10, 15, 20, 30, 45, 60])   # minutes
formulation_A = np.array([0, 25, 48, 65, 75, 85, 92, 97])
formulation_B = np.array([0, 15, 32, 50, 62, 75, 88, 94])
formulation_C = np.array([0, 35, 58, 72, 82, 91, 95, 98])

plt.figure(figsize=(9, 6))
plt.plot(time_points, formulation_A, marker='s', label='Formulation A', color='blue')
plt.plot(time_points, formulation_B, marker='^', label='Formulation B', color='red')
plt.plot(time_points, formulation_C, marker='o', label='Formulation C', color='green')

plt.axhline(y=80, color='gray', linestyle='--', label='80% Dissolution Target')

plt.title("Dissolution Profile — Three Tablet Formulations")
plt.xlabel("Time (minutes)")
plt.ylabel("Drug Dissolved (%)")
plt.legend()
plt.grid(True)
plt.tight_layout()
plt.show()
```

---

## 4. Scatter Plots

### Dose vs Response

```python
doses = np.array([50, 100, 150, 200, 250, 300, 400, 500])
response = np.array([10, 22, 38, 54, 67, 78, 85, 88])     # % effect

plt.figure(figsize=(8, 5))
plt.scatter(doses, response, color='purple', s=80, zorder=5)
plt.title("Dose-Response Relationship")
plt.xlabel("Dose (mg)")
plt.ylabel("Effect (%)")
plt.grid(True)
plt.tight_layout()
plt.show()
```

### Patient BMI vs Glucose Scatter

```python
import pandas as pd

data = {
    "Name": ["Rahul", "Priya", "Suresh", "Anitha", "Mohan", "Kavitha", "Vijay", "Suma"],
    "BMI": [28.5, 22.3, 31.2, 21.5, 30.8, 25.6, 27.1, 29.4],
    "Glucose": [110, 88, 145, 92, 160, 102, 118, 135],
    "Diabetic": [False, False, True, False, True, False, False, True]
}

df = pd.DataFrame(data)

colors = ['red' if d else 'blue' for d in df["Diabetic"]]

plt.figure(figsize=(8, 5))
plt.scatter(df["BMI"], df["Glucose"], c=colors, s=100)
plt.axhline(y=126, color='orange', linestyle='--', label='Diabetes threshold (126 mg/dL)')
plt.title("BMI vs Fasting Glucose in Patients")
plt.xlabel("BMI")
plt.ylabel("Fasting Glucose (mg/dL)")
plt.legend(["Diabetes threshold", "Diabetic", "Non-Diabetic"])
plt.grid(True)
plt.tight_layout()
plt.show()
```

---

## 🧠 Key Takeaways

1. NumPy `trapz()` calculates AUC — key metric in pharmacokinetics
2. `np.linspace()` generates smooth time points for model curves
3. Line plots show trends over time — essential for PK and dissolution studies
4. Scatter plots show relationships — dose-response, BMI-glucose correlations
5. Adding reference lines (MEC, MTC, thresholds) makes charts clinically meaningful

---

## 💻 Practice Exercises

**Exercise 1:** Plot a concentration-time graph for a drug with C0 = 15 mg/L and k = 0.12. Show the therapeutic window (MEC = 6, MTC = 13).

**Exercise 2:** Create a dissolution profile for two tablet formulations you design. Which one reaches 80% faster?

**Exercise 3:** Create a scatter plot of 10 patients' ages vs blood pressure. Add a reference line at BP = 140 (hypertension threshold).
