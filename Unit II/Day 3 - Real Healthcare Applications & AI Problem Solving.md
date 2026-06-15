# Unit II – Day 3 (2 Hours)
## Real Healthcare Applications — Dosage, BMI & Prescription Systems

---

## 🎯 Session Goals
By the end of this session, students will be able to:
- Build complete healthcare mini-applications in Python
- Combine conditions, loops, and functions into real programs
- Understand AI-assisted problem solving concepts

---

## ⏱️ Session Plan (2 Hours)

| Time | Topic |
|------|-------|
| 0:00 – 0:10 | Recap of Unit II so far |
| 0:10 – 0:40 | Dosage calculation system |
| 0:40 – 1:10 | Prescription management program |
| 1:10 – 1:40 | AI-assisted problem solving intro |
| 1:40 – 2:00 | Recap + Q&A |

---

## 1. Complete Dosage Calculation System

```python
# ============================================
# DOSAGE CALCULATION SYSTEM
# ============================================

def get_dose_per_kg(drug_name):
    """Returns standard dose per kg for known drugs"""
    drug_doses = {
        "paracetamol": 15,
        "ibuprofen": 10,
        "amoxicillin": 25,
        "metformin": 500,    # flat dose, not per kg
    }
    return drug_doses.get(drug_name.lower(), None)

def calculate_total_dose(weight, dose_per_kg):
    return weight * dose_per_kg

def check_max_dose(dose, drug_name):
    max_doses = {
        "paracetamol": 4000,
        "ibuprofen": 2400,
        "amoxicillin": 3000,
    }
    max_d = max_doses.get(drug_name.lower(), float('inf'))
    if dose > max_d:
        return False, max_d
    return True, max_d

# --- Main Program ---
print("=== DOSAGE CALCULATOR ===")
name = input("Patient name: ")
weight = float(input("Weight (kg): "))
drug = input("Drug name: ").lower()

dose_per_kg = get_dose_per_kg(drug)

if dose_per_kg is None:
    print(f"⚠️ Drug '{drug}' not in database. Consult reference.")
else:
    total = calculate_total_dose(weight, dose_per_kg)
    safe, max_dose = check_max_dose(total, drug)

    print(f"\n--- Prescription for {name} ---")
    print(f"Drug          : {drug.capitalize()}")
    print(f"Weight        : {weight} kg")
    print(f"Dose per kg   : {dose_per_kg} mg/kg")
    print(f"Calculated dose: {total} mg")

    if not safe:
        print(f"⚠️ Exceeds max dose of {max_dose} mg — cap at {max_dose} mg")
    else:
        print("✅ Dose is within safe limits")
```

---

## 2. Unit Conversion System

```python
# ============================================
# PHARMACEUTICAL UNIT CONVERTER
# ============================================

def convert(value, from_unit, to_unit):
    conversions = {
        ("mg", "mcg"): 1000,
        ("mcg", "mg"): 0.001,
        ("mg", "g"): 0.001,
        ("g", "mg"): 1000,
        ("kg", "lbs"): 2.205,
        ("lbs", "kg"): 0.4536,
        ("celsius", "fahrenheit"): None,   # special case
        ("fahrenheit", "celsius"): None,
    }

    if from_unit == "celsius" and to_unit == "fahrenheit":
        return (value * 9/5) + 32
    elif from_unit == "fahrenheit" and to_unit == "celsius":
        return (value - 32) * 5/9

    factor = conversions.get((from_unit, to_unit))
    if factor:
        return value * factor
    else:
        return "Conversion not supported"

# Usage
print(convert(500, "mg", "mcg"))           # 500000 mcg
print(convert(37, "celsius", "fahrenheit")) # 98.6°F
print(convert(70, "kg", "lbs"))            # 154.35 lbs
```

---

## 3. Prescription Management Program

```python
# ============================================
# SIMPLE PRESCRIPTION MANAGER
# ============================================

prescriptions = []

def add_prescription(patient, drug, dose, frequency, days):
    prescription = {
        "patient": patient,
        "drug": drug,
        "dose": dose,
        "frequency": frequency,
        "days": days,
        "total_tablets": frequency * days
    }
    prescriptions.append(prescription)
    print(f"✅ Prescription added for {patient}")

def view_prescriptions():
    if not prescriptions:
        print("No prescriptions on record.")
        return
    print("\n=== ALL PRESCRIPTIONS ===")
    for i, p in enumerate(prescriptions, 1):
        print(f"\n{i}. Patient : {p['patient']}")
        print(f"   Drug    : {p['drug']} {p['dose']}mg")
        print(f"   Freq    : {p['frequency']}x daily for {p['days']} days")
        print(f"   Tablets : {p['total_tablets']} total")

def find_patient(name):
    results = [p for p in prescriptions if p["patient"].lower() == name.lower()]
    if results:
        for p in results:
            print(f"Found: {p['drug']} {p['dose']}mg for {p['patient']}")
    else:
        print(f"No prescription found for '{name}'")

# --- Main ---
add_prescription("Rahul", "Amoxicillin", 500, 3, 7)
add_prescription("Priya", "Paracetamol", 500, 3, 5)
add_prescription("Suresh", "Metformin", 500, 2, 30)

view_prescriptions()
find_patient("Priya")
```

---

## 4. Introduction to AI-Assisted Problem Solving

### What does "AI-assisted" mean in programming context?

> AI-assisted = using algorithms/rules/data to make decisions automatically, without manual checking every case.

### Example: Rule-Based Drug Interaction Checker

```python
# Simple rule-based system (precursor to AI)
interaction_rules = {
    ("warfarin", "aspirin"): "HIGH RISK — Bleeding",
    ("metformin", "alcohol"): "RISK — Lactic acidosis",
    ("ssri", "maoi"): "CRITICAL — Serotonin syndrome",
    ("ciprofloxacin", "antacid"): "MODERATE — Reduced absorption",
}

def check_interaction(drug1, drug2):
    key1 = (drug1.lower(), drug2.lower())
    key2 = (drug2.lower(), drug1.lower())

    if key1 in interaction_rules:
        return interaction_rules[key1]
    elif key2 in interaction_rules:
        return interaction_rules[key2]
    else:
        return "No known major interaction"

# Usage
d1 = input("Drug 1: ")
d2 = input("Drug 2: ")
result = check_interaction(d1, d2)
print(f"Interaction: {result}")
```

> 💬 **Tell students:** "This is a rule-based system — the earliest form of AI in medicine. Modern AI does the same thing but learns rules from millions of patient records instead of us manually entering them."

---

## 🧠 Key Takeaways

1. Real applications combine functions + conditions + loops
2. Dictionaries are powerful for drug databases and lookup tables
3. Lists store collections (patient records, prescription history)
4. Rule-based systems are the bridge between programming and AI
5. Python can already simulate basic clinical decision support

---

## 💻 Unit II Final Exercise

Build a **"Patient Health Dashboard"** that:
1. Takes patient name, age, weight, height
2. Calculates BMI + classifies it
3. Calculates dose for a given drug
4. Checks for one known drug interaction
5. Prints a summary report

This is your **Unit II capstone program.**
