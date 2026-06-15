# Unit II – Day 2 (2 Hours)
## Functions in Python — Healthcare Applications

---

## 🎯 Session Goals
By the end of this session, students will be able to:
- Define and call user-defined functions
- Pass arguments and return values
- Build reusable functions for dosage, BMI, and unit conversions

---

## ⏱️ Session Plan (2 Hours)

| Time | Topic |
|------|-------|
| 0:00 – 0:15 | Recap + Why functions? |
| 0:15 – 0:45 | Defining and calling functions |
| 0:45 – 1:20 | Arguments, return values |
| 1:20 – 1:50 | Healthcare function library exercise |
| 1:50 – 2:00 | Recap + Q&A |

---

## 1. Why Functions?

> "Don't repeat yourself. Write once, use everywhere."

### Without Functions (Bad Practice)

```python
# Patient 1
bmi1 = 70 / (1.75 ** 2)
print(f"BMI: {bmi1:.2f}")

# Patient 2
bmi2 = 55 / (1.60 ** 2)
print(f"BMI: {bmi2:.2f}")
```

### With Functions (Good Practice)

```python
def calculate_bmi(weight, height):
    return weight / (height ** 2)

print(calculate_bmi(70, 1.75))
print(calculate_bmi(55, 1.60))
```

> 💬 "Functions = reusable blocks of logic. Build once, call many times."

---

## 2. Defining & Calling Functions

### Basic Syntax

```python
def function_name(parameters):
    # logic
    return result
```

### Hello Function

```python
def greet_patient(name):
    print(f"Welcome, {name}! Please proceed to the pharmacy counter.")

greet_patient("Priya")
greet_patient("Suresh")
```

---

## 3. Functions with Arguments & Return Values

### Dosage Calculator Function

```python
def calculate_dose(weight_kg, dose_per_kg):
    total_dose = weight_kg * dose_per_kg
    return total_dose

dose = calculate_dose(60, 10)
print(f"Total Dose: {dose} mg")
```

### BMI Calculator

```python
def calculate_bmi(weight, height):
    bmi = weight / (height ** 2)
    return round(bmi, 2)

def classify_bmi(bmi):
    if bmi < 18.5:
        return "Underweight"
    elif bmi < 25:
        return "Normal"
    elif bmi < 30:
        return "Overweight"
    else:
        return "Obese"

# Usage
w = float(input("Weight (kg): "))
h = float(input("Height (m): "))

bmi = calculate_bmi(w, h)
category = classify_bmi(bmi)

print(f"BMI: {bmi} — {category}")
```

---

## 4. Default Arguments

```python
def drug_label(drug_name, dose=500, frequency="twice daily"):
    print(f"Drug: {drug_name} | Dose: {dose}mg | Frequency: {frequency}")

drug_label("Paracetamol")                         # uses defaults
drug_label("Amoxicillin", 250, "three times daily")  # custom values
```

---

## 5. Multiple Return Values

```python
def patient_risk_score(age, bmi, is_diabetic):
    score = 0
    if age > 60:
        score += 2
    if bmi > 30:
        score += 2
    if is_diabetic:
        score += 3

    if score >= 5:
        risk = "High"
    elif score >= 3:
        risk = "Moderate"
    else:
        risk = "Low"

    return score, risk

score, risk = patient_risk_score(65, 32, True)
print(f"Risk Score: {score} — Risk Level: {risk}")
```

---

## 6. Unit Conversion Functions

```python
def mg_to_mcg(mg):
    return mg * 1000

def mcg_to_mg(mcg):
    return mcg / 1000

def celsius_to_fahrenheit(c):
    return (c * 9/5) + 32

def kg_to_lbs(kg):
    return kg * 2.205

# Usage
print(mg_to_mcg(2))             # 2000.0 mcg
print(celsius_to_fahrenheit(37))  # 98.6°F (normal body temperature)
print(kg_to_lbs(70))            # 154.35 lbs
```

---

## 7. Mini Project: Pharmaceutical Calculator

```python
def calculate_dose(weight, dose_per_kg):
    return weight * dose_per_kg

def calculate_bmi(weight, height):
    return round(weight / height**2, 2)

def classify_bmi(bmi):
    if bmi < 18.5: return "Underweight"
    elif bmi < 25: return "Normal"
    elif bmi < 30: return "Overweight"
    else: return "Obese"

def convert_units(value, from_unit):
    if from_unit == "mg":
        return value * 1000, "mcg"
    elif from_unit == "kg":
        return value * 2.205, "lbs"

# --- Main Program ---
print("=== PHARMACEUTICAL CALCULATOR ===\n")
name = input("Patient Name: ")
weight = float(input("Weight (kg): "))
height = float(input("Height (m): "))

bmi = calculate_bmi(weight, height)
category = classify_bmi(bmi)
dose = calculate_dose(weight, 10)

print(f"\n--- Results for {name} ---")
print(f"BMI         : {bmi} ({category})")
print(f"Dose (10mg/kg): {dose} mg")
```

---

## 🧠 Key Takeaways

1. Functions make code reusable — define once, call anywhere
2. Arguments pass data into functions; `return` sends results out
3. Default arguments make functions flexible
4. Pharmacy logic — dosage, BMI, unit conversion — maps perfectly to functions

---

## 💻 Practice Exercises

**Exercise 1:** Write a function `creatinine_clearance(age, weight, creatinine)` using the Cockcroft-Gault formula.

**Exercise 2:** Create a `prescription_summary(name, drug, dose, frequency)` function that prints a formatted label.

**Exercise 3:** Write a function that takes a drug name and returns whether it requires a prescription or is OTC (use a simple lookup dictionary).
