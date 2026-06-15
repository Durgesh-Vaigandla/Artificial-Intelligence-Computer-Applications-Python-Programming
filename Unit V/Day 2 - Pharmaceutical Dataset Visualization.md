# Unit V – Day 2 (2 Hours)
## Pharmaceutical Dataset Visualization — ADR Reports, PK & Dissolution

---

## 🎯 Session Goals
- Visualize ADR reports, PK profiles, and dissolution studies
- Interpret clinical meaning from graphs
- Build a multi-panel patient health dashboard

---

## ⏱️ Session Plan (2 Hours)

| Time | Topic |
|------|-------|
| 0:00 – 0:10 | Recap Day 1 |
| 0:10 – 0:45 | ADR report visualization |
| 0:45 – 1:20 | Multi-drug PK comparison |
| 1:20 – 1:50 | Dissolution study + patient dashboard |
| 1:50 – 2:00 | Recap + Q&A |

---

## 1. ADR Report Visualization

```python
import matplotlib.pyplot as plt
import numpy as np

drugs = ["Paracetamol", "Amoxicillin", "Metformin", "Ibuprofen", "Aspirin", "Atorvastatin"]
adr_count = [120, 85, 60, 140, 95, 45]

plt.figure(figsize=(10, 6))
bars = plt.bar(drugs, adr_count,
               color=['#e74c3c','#3498db','#2ecc71','#f39c12','#9b59b6','#1abc9c'])

for bar, count in zip(bars, adr_count):
    plt.text(bar.get_x() + bar.get_width()/2,
             bar.get_height() + 2, str(count), ha='center')

plt.title("ADR Reports by Drug (Annual)")
plt.xlabel("Drug Name")
plt.ylabel("Number of ADR Reports")
plt.xticks(rotation=30, ha='right')
plt.grid(axis='y', alpha=0.5)
plt.tight_layout()
plt.show()
```

### ADR by Category — Pie Chart

```python
categories = ["GI Effects", "Allergic", "CNS", "Liver Toxicity", "Cardiovascular", "Other"]
counts = [35, 25, 15, 10, 8, 7]

plt.figure(figsize=(7, 7))
plt.pie(counts, labels=categories, autopct='%1.1f%%', startangle=140)
plt.title("ADR Reports by Category")
plt.tight_layout()
plt.show()
```

> 💬 "GI effects are the most common because most drugs are taken orally and pass through the gut first."

---

## 2. Multi-Drug PK Comparison

```python
time = np.linspace(0, 24, 200)

def pk_profile(t, C0, k_abs, k_elim):
    return C0 * (np.exp(-k_elim * t) - np.exp(-k_abs * t))

drug_A = pk_profile(time, 15, 1.2, 0.15)   # Immediate release
drug_B = pk_profile(time, 12, 0.4, 0.10)   # Extended release

plt.figure(figsize=(10, 6))
plt.plot(time, drug_A, label='Immediate Release', color='blue', linewidth=2)
plt.plot(time, drug_B, label='Extended Release', color='green', linewidth=2, linestyle='--')
plt.axhline(y=5, color='gray', linestyle='-.', label='MEC (5 mg/L)')
plt.axhline(y=12, color='orange', linestyle='-.', label='MTC (12 mg/L)')
plt.fill_between(time, 5, 12, alpha=0.08, color='green')

plt.title("PK Profile: Immediate vs Extended Release")
plt.xlabel("Time (hours)")
plt.ylabel("Plasma Concentration (mg/L)")
plt.legend()
plt.grid(True, alpha=0.4)
plt.tight_layout()
plt.show()
```

> 💬 "Extended release stays in the therapeutic window longer — better compliance, once-daily dosing. This is exactly how clinical pharmacologists compare formulations before approving a generic."

---

## 3. Dissolution Study Analysis

```python
time_min = [0, 5, 10, 15, 20, 30, 45, 60]
brand_A   = [0, 22, 45, 63, 73, 84, 91, 96]
generic_B = [0, 18, 38, 55, 65, 77, 86, 91]
generic_C = [0, 12, 28, 44, 57, 70, 80, 87]

plt.figure(figsize=(9, 6))
plt.plot(time_min, brand_A,   marker='o', label='Brand A',   linewidth=2)
plt.plot(time_min, generic_B, marker='s', label='Generic B', linewidth=2)
plt.plot(time_min, generic_C, marker='^', label='Generic C', linewidth=2)
plt.axhline(y=80, color='black', linestyle='--', label='80% Target (Q)')
plt.axvline(x=30, color='gray',  linestyle=':',  alpha=0.6)

plt.title("Dissolution Profile — Paracetamol 500mg Tablets")
plt.xlabel("Time (minutes)")
plt.ylabel("Drug Dissolved (%)")
plt.legend()
plt.grid(True, alpha=0.4)
plt.tight_layout()
plt.show()
```

> 💬 "The Q-value test requires 80% dissolution by 30 minutes. Brand A and Generic B pass. Generic C fails — it would be rejected by regulators."

---

## 4. Patient Health Dashboard (3-Panel)

```python
import pandas as pd

df = pd.DataFrame({
    "Patient": ["P1","P2","P3","P4","P5","P6","P7","P8"],
    "Glucose":  [88, 145, 160, 92, 110, 200, 98, 135],
    "BP":       [118, 145, 160, 108, 130, 170, 122, 148],
    "BMI":      [22.3, 29.5, 31.8, 21.1, 27.4, 33.2, 24.6, 28.9]
})

fig, axes = plt.subplots(1, 3, figsize=(15, 5))

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

axes[2].bar(df["Patient"], df["BMI"],
            color=['orange' if b > 25 else 'green' for b in df["BMI"]])
axes[2].axhline(y=25, color='orange', linestyle='--', label='Overweight threshold')
axes[2].set_title("BMI")
axes[2].legend()

plt.suptitle("Patient Health Dashboard", fontsize=14, fontweight='bold')
plt.tight_layout()
plt.show()
```

---

## 🧠 Key Takeaways

1. Bar charts — compare drug ADR counts or patient health metrics
2. Pie charts — proportion breakdown of ADR categories
3. Line plots — PK and dissolution profiles over time
4. Multi-panel dashboards — see multiple health indicators at once
5. Color coding (red = abnormal) makes clinical data instantly readable

---

## 💻 Practice Exercises

**Exercise 1:** Create an ADR bar chart for 5 drugs. Which has the highest report count?

**Exercise 2:** Plot immediate vs extended release PK for any drug. Mark the therapeutic window.

**Exercise 3:** Build a 2-panel dashboard (Glucose + BP) for 6 patients. Color abnormal values red.
