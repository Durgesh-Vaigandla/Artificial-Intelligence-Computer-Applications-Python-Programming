# Unit II – Day 2 (2 Hours)
## Functions in Python — Complete Guide for Pharmacy Students

---

## 🎯 Session Goals
By the end of this session, you will be able to:
- Explain what a function is and why functions exist
- Define and call your own functions
- Use parameters and arguments correctly
- Return single and multiple values from functions
- Use default parameter values
- Understand variable scope — local vs global
- Use docstrings to document your functions
- Understand lambda (anonymous) functions
- Apply everything practically by building a reusable pharmaceutical function library

---

## ⏱️ Session Plan (2 Hours)

| Time | Block | Topic |
|------|-------|-------|
| 0:00 – 0:05 | — | Recap of Day 1 (conditions + loops), session overview |
| 0:05 – 1:00 | **THEORY** | Why functions → defining → parameters → return → default args → scope → docstrings → lambda |
| 1:00 – 1:55 | **PRACTICAL** | Build a complete pharmaceutical calculator function library |
| 1:55 – 2:00 | — | Recap + Q&A |

> 💬 **How to use this document:** Read all of Part A before touching a keyboard. Every concept in functions builds on the previous one — if you jump to Part B without understanding scope or return values, the programs won't make sense when something goes wrong.

---
---
---

# 🅰️ PART A — THEORY

---

# SECTION 1 — What is a Function and Why Does It Exist?

## 1.1 The Problem Functions Solve

After Day 1, you can write programs that make decisions and repeat actions. But something is still missing. Look at this program:

```python
# Patient 1 — Rahul
weight1 = 72
bmi1 = weight1 / (1.72 ** 2)
if bmi1 < 18.5:
    category1 = "Underweight"
elif bmi1 < 25:
    category1 = "Normal"
elif bmi1 < 30:
    category1 = "Overweight"
else:
    category1 = "Obese"
print(f"Rahul: BMI = {bmi1:.1f} — {category1}")

# Patient 2 — Priya
weight2 = 58
bmi2 = weight2 / (1.60 ** 2)
if bmi2 < 18.5:
    category2 = "Underweight"
elif bmi2 < 25:
    category2 = "Normal"
elif bmi2 < 30:
    category2 = "Overweight"
else:
    category2 = "Obese"
print(f"Priya: BMI = {bmi2:.1f} — {category2}")
```

This works, but it has a critical problem: **the same logic is written twice**. For 10 patients, it would be written 10 times. If the BMI thresholds changed (because guidelines updated), you'd need to find and fix 10 places. Miss one — and you have a bug that could affect patient care.

> 💬 "This is called the DRY principle — **Don't Repeat Yourself**. Repeating the same logic in multiple places is how bugs get introduced and how systems become unmaintainable. Functions solve this."

## 1.2 What a Function Does

> A **function** is a named, reusable block of code that performs a specific task. You define it once, then call it by name as many times as you need, from anywhere in your program.

```python
# Define ONCE
def calculate_bmi(weight, height):
    return weight / (height ** 2)

# Call MANY TIMES
bmi_rahul = calculate_bmi(72, 1.72)
bmi_priya = calculate_bmi(58, 1.60)
bmi_suresh = calculate_bmi(85, 1.68)
```

Three patients, one calculation — zero repetition. If the formula changes, you fix it in **one place**.

## 1.3 The Pharmacy Analogy

| Pharmacy | Functions |
|----------|-----------|
| A drug **formulation** | A function **definition** |
| The **manufacturing process** written in the SOP once | The function body — written once |
| **Dispensing** the drug to multiple patients | **Calling** the function with different inputs |
| Drug takes **input materials**, produces an **output product** | Function takes **parameters**, produces a **return value** |

> 💬 "You don't re-write the SOP for Paracetamol every time you make a new batch. You follow the same procedure with each batch's specific input materials. A Python function works the same way — same procedure, different input data each time you call it."

---
---

# SECTION 2 — Defining and Calling a Function

## 2.1 The Syntax

```python
def function_name(parameter1, parameter2):
    """Optional docstring — describes what this function does."""
    # function body — the code that runs when called
    return result
```

| Part | Role |
|------|------|
| `def` | Keyword that tells Python: "I'm defining a function" |
| `function_name` | The name you'll use to call it — use lowercase with underscores |
| `(parameter1, parameter2)` | The inputs the function expects — called parameters in the definition |
| `:` | Marks the start of the function body, just like if/for/while |
| Indented body | The code that runs every time the function is called |
| `return` | Sends a value back to wherever the function was called from |

## 2.2 A Minimal Example

```python
def greet_patient(name):
    print(f"Welcome, {name}! Please proceed to the pharmacy counter.")

greet_patient("Priya")      # calling the function with "Priya" as input
greet_patient("Rahul")      # calling again with different input
greet_patient("Suresh")     # and again
```

Output:
```
Welcome, Priya! Please proceed to the pharmacy counter.
Welcome, Rahul! Please proceed to the pharmacy counter.
Welcome, Suresh! Please proceed to the pharmacy counter.
```

The function runs three times, but the body is written only once.

## 2.3 Functions Without Parameters

Not all functions need inputs:

```python
def show_separator():
    print("=" * 45)

def pharmacy_header():
    show_separator()
    print("     AAVANTO PHARMACY SYSTEM")
    show_separator()

pharmacy_header()
```

---
---

# SECTION 3 — Parameters and Arguments

## 3.1 Parameters vs Arguments — The Exact Distinction

These two words are often used interchangeably, but they mean different things:

- **Parameter** — the variable name listed inside the parentheses in the function **definition**
- **Argument** — the actual value passed to the function when you **call** it

```python
def calculate_dose(weight, dose_per_kg):   # weight, dose_per_kg are PARAMETERS
    return weight * dose_per_kg

result = calculate_dose(70, 15)            # 70 and 15 are ARGUMENTS
```

When the call is made, Python binds: `weight = 70` and `dose_per_kg = 15` — the arguments fill the parameter slots.

## 3.2 Positional Arguments

Arguments are matched to parameters by their **position** — the first argument goes to the first parameter, second to second, and so on.

```python
def drug_info(name, dose, frequency):
    print(f"Drug: {name} | Dose: {dose}mg | Frequency: {frequency}")

drug_info("Metformin", 500, "twice daily")
# name = "Metformin", dose = 500, frequency = "twice daily"
```

Order matters — calling `drug_info(500, "twice daily", "Metformin")` would assign the wrong values to the wrong parameters.

## 3.3 Keyword Arguments

You can also pass arguments by explicitly naming which parameter they belong to. This removes the position dependency:

```python
drug_info(dose=500, name="Metformin", frequency="twice daily")
# Same result — the names route each argument to the correct parameter
```

Keyword arguments improve readability and reduce errors, especially with functions that have many parameters.

## 3.4 Mixing Positional and Keyword Arguments

You can mix both, but positional arguments must come **before** keyword arguments:

```python
drug_info("Metformin", dose=500, frequency="twice daily")   # ✅ valid
drug_info(dose=500, "Metformin", frequency="twice daily")   # ❌ SyntaxError
```

---
---

# SECTION 4 — The return Statement

## 4.1 What return Does

> `return` sends a value **out** of the function, back to the point in the program where the function was called. Without a `return`, the function produces `None`.

```python
def calculate_dose(weight, dose_per_kg):
    total = weight * dose_per_kg
    return total              # sends total back to the caller

dose = calculate_dose(60, 15)
print(dose)                   # 900 — the returned value, now stored in 'dose'
```

## 4.2 The Function Body Stops at return

As soon as Python hits a `return` statement, the function exits immediately — any code after it in the same function does NOT run:

```python
def check_dose_safety(dose):
    if dose > 4000:
        return "⚠️ UNSAFE — exceeds 4000mg daily maximum"
    if dose < 0:
        return "⚠️ INVALID — dose cannot be negative"
    return "✅ Safe"    # only reaches here if both checks above passed

print(check_dose_safety(5000))   # ⚠️ UNSAFE — exceeds 4000mg daily maximum
print(check_dose_safety(-100))   # ⚠️ INVALID — dose cannot be negative
print(check_dose_safety(500))    # ✅ Safe
```

This pattern — returning early when a problem is found — is called a **guard clause**, and it keeps your logic clean and readable.

## 4.3 Returning Multiple Values

Python functions can return more than one value, separated by commas. The caller receives them as a **tuple**:

```python
def analyse_bmi(weight, height):
    bmi = round(weight / (height ** 2), 1)

    if bmi < 18.5:
        category = "Underweight"
    elif bmi < 25:
        category = "Normal"
    elif bmi < 30:
        category = "Overweight"
    else:
        category = "Obese"

    return bmi, category    # returning two values

# Unpacking both return values into two variables
bmi_value, bmi_category = analyse_bmi(68, 1.65)
print(f"BMI: {bmi_value} — {bmi_category}")
```

## 4.4 Functions That Don't Return a Value

If a function doesn't have a `return` statement (or has a bare `return` with no value), it returns `None`:

```python
def print_label(patient, drug, dose):
    print(f"Patient: {patient}")
    print(f"Drug:    {drug} {dose}mg")
    # no return — this function just prints; it doesn't produce a value

result = print_label("Rahul", "Metformin", 500)
print(result)    # None
```

---
---

# SECTION 5 — Default Parameter Values

## 5.1 What Default Values Do

> A **default parameter value** is used when the caller doesn't provide an argument for that parameter. This makes the argument optional.

```python
def create_prescription_label(patient_name, drug, dose=500, frequency="twice daily"):
    print(f"Patient   : {patient_name}")
    print(f"Drug      : {drug} {dose}mg")
    print(f"Frequency : {frequency}")
    print("-" * 30)
```

Now this function can be called in multiple ways:

```python
# All defaults accepted
create_prescription_label("Rahul", "Metformin")
# Patient   : Rahul
# Drug      : Metformin 500mg
# Frequency : twice daily

# Overriding one default
create_prescription_label("Priya", "Amoxicillin", 250)
# Patient   : Priya
# Drug      : Amoxicillin 250mg
# Frequency : twice daily

# Overriding both defaults
create_prescription_label("Suresh", "Ibuprofen", 400, "three times daily")
# Patient   : Suresh
# Drug      : Ibuprofen 400mg
# Frequency : three times daily
```

## 5.2 The Rule for Default Values — Position Matters

Default parameters must always come **after** non-default parameters in the definition:

```python
# ✅ Correct — non-defaults first, defaults last
def drug_label(patient_name, drug, dose=500, frequency="twice daily"):
    pass

# ❌ SyntaxError — can't have a default before a non-default
def drug_label(dose=500, patient_name, drug):
    pass
```

---
---

# SECTION 6 — Variable Scope (Local vs Global)

## 6.1 What is Scope?

> **Scope** defines where in your program a variable is visible and usable. Python has two main scopes: **local** (inside a function) and **global** (outside all functions).

## 6.2 Local Variables

Variables created **inside** a function only exist within that function. They are created when the function is called and destroyed when the function ends:

```python
def calculate_dose(weight):
    dose = weight * 15    # 'dose' is a LOCAL variable
    return dose

result = calculate_dose(60)
print(result)    # 900 — fine, result was returned

print(dose)      # ❌ NameError — 'dose' doesn't exist outside the function
```

## 6.3 Global Variables

Variables created **outside** all functions are global — visible everywhere in the program:

```python
hospital_name = "Aavanto Hospital"   # global variable

def print_prescription_header():
    print(f"Hospital: {hospital_name}")   # can read the global variable
    print("PRESCRIPTION")

print_prescription_header()
print(hospital_name)    # also accessible here
```

## 6.4 Modifying a Global Variable from Inside a Function

By default, assigning to a variable inside a function creates a **new local** variable, not modifying the global. To modify a global, you must declare it with the `global` keyword:

```python
total_prescriptions = 0    # global counter

def process_prescription():
    global total_prescriptions
    total_prescriptions += 1    # now modifying the global
    print(f"Prescription #{total_prescriptions} processed")

process_prescription()
process_prescription()
print(f"Total today: {total_prescriptions}")    # 2
```

> 💬 "Avoid using `global` heavily — it makes programs harder to understand and debug. Prefer passing data in through parameters and getting it back through return values. Only use global for genuine program-wide state like counters or configuration settings."

---
---

# SECTION 7 — Docstrings — Documenting Your Functions

## 7.1 What is a Docstring?

> A **docstring** is a string literal placed immediately after the `def` line, inside the function. It documents what the function does, what its parameters are, and what it returns. It's not just a comment — Python stores it as part of the function, accessible with `help()`.

```python
def calculate_creatinine_clearance(age, weight, serum_creatinine, gender="male"):
    """
    Calculates creatinine clearance using the Cockcroft-Gault formula.

    Parameters:
        age (int)               : Patient age in years
        weight (float)          : Patient weight in kilograms
        serum_creatinine (float): Serum creatinine level in mg/dL
        gender (str)            : 'male' or 'female' (default: 'male')

    Returns:
        float: Estimated creatinine clearance in mL/min
    """
    crcl = ((140 - age) * weight) / (72 * serum_creatinine)
    if gender.lower() == "female":
        crcl *= 0.85
    return round(crcl, 1)

# See the docstring
help(calculate_creatinine_clearance)

# Use the function
result = calculate_creatinine_clearance(65, 70, 1.2, "male")
print(f"CrCl: {result} mL/min")
```

> 💬 "In a real hospital pharmacy software team, every function must have a docstring. When a new pharmacist-programmer joins and reads the code six months later, the docstring is what tells them what `calculate_creatinine_clearance` expects — without needing to read every line of logic inside it."

---
---

# SECTION 8 — Lambda Functions

## 8.1 What is a Lambda?

> A **lambda** is an anonymous, one-expression function. It's useful for short, throwaway calculations where writing a full `def` block feels excessive.

### Syntax

```python
lambda parameters: expression
```

### Full def vs lambda — Direct Comparison

```python
# Using def
def mg_to_mcg(mg):
    return mg * 1000

# Equivalent lambda
mg_to_mcg = lambda mg: mg * 1000

# Both work identically
print(mg_to_mcg(2))    # 2000
```

### Practical Pharmacy Uses

```python
# Unit conversions as lambdas
mg_to_mcg         = lambda mg: mg * 1000
mcg_to_mg         = lambda mcg: mcg / 1000
kg_to_lbs         = lambda kg: kg * 2.205
celsius_to_fahr   = lambda c: (c * 9/5) + 32

print(mg_to_mcg(500))        # 500000 mcg
print(celsius_to_fahr(37))   # 98.6°F

# Sorting a list of patients by age using a lambda as the sort key
patients = [
    {"name": "Rahul", "age": 45},
    {"name": "Priya", "age": 32},
    {"name": "Suresh", "age": 60},
]

sorted_patients = sorted(patients, key=lambda p: p["age"])
for p in sorted_patients:
    print(f"{p['name']}: {p['age']}")
```

> 💬 "Use lambda for short, simple operations. If the logic needs more than one expression, use a proper `def` — don't try to squeeze complex logic into a lambda. Readability is more important than brevity."

---
---
---

# 🅱️ PART B — PRACTICAL

> 💬 We are now going to build a **Pharmaceutical Function Library** — a collection of well-named, properly documented, reusable functions covering the most common pharmacy calculations. By the end, this library is a real tool you can reuse in every future Python program.

---

## PRACTICAL 1 — BMI Calculator with Classification

**Goal:** Build a two-function pair where one calculates, one classifies — and they work together.

```python
def calculate_bmi(weight_kg, height_m):
    """
    Calculates Body Mass Index.

    Parameters:
        weight_kg (float): Patient weight in kg
        height_m (float) : Patient height in metres

    Returns:
        float: BMI rounded to 1 decimal place
    """
    bmi = weight_kg / (height_m ** 2)
    return round(bmi, 1)


def classify_bmi(bmi):
    """
    Classifies a BMI value into WHO weight status categories.

    Parameters:
        bmi (float): The BMI value

    Returns:
        str: Weight status category
    """
    if bmi < 18.5:
        return "Underweight"
    elif bmi < 25.0:
        return "Normal"
    elif bmi < 30.0:
        return "Overweight"
    else:
        return "Obese"


# --- Test the pair ---
weight = float(input("Weight (kg): "))
height = float(input("Height (m): "))

bmi      = calculate_bmi(weight, height)
category = classify_bmi(bmi)

print(f"\nBMI      : {bmi}")
print(f"Category : {category}")
```

**Now extend it yourself:** Add a third function `bmi_recommendation(category)` that returns a dietary/lifestyle recommendation string based on the BMI category.

---

## PRACTICAL 2 — Dosage Calculator with Safety Check

**Goal:** Use guard clauses, default parameters, and multiple returns.

```python
# Maximum safe single dose by drug (mg)
DOSE_LIMITS = {
    "paracetamol" : 1000,
    "ibuprofen"   : 800,
    "amoxicillin" : 1000,
    "metformin"   : 1000,
}

def calculate_dose(weight_kg, dose_per_kg, drug_name="unknown", max_single_dose=None):
    """
    Calculates total drug dose from weight and checks against safety limits.

    Parameters:
        weight_kg (float)    : Patient weight in kg
        dose_per_kg (float)  : Dose in mg per kg body weight
        drug_name (str)      : Drug name for database lookup (default: 'unknown')
        max_single_dose (int): Optional manual override for max dose

    Returns:
        tuple: (calculated_dose: float, capped: bool, warning: str)
    """
    if weight_kg <= 0:
        return None, False, "❌ Invalid weight — must be greater than 0"

    if dose_per_kg <= 0:
        return None, False, "❌ Invalid dose per kg — must be greater than 0"

    calculated = round(weight_kg * dose_per_kg, 1)

    # Determine the cap
    cap = max_single_dose or DOSE_LIMITS.get(drug_name.lower())

    capped  = False
    warning = ""

    if cap and calculated > cap:
        warning  = f"⚠️  Dose capped from {calculated}mg to max {cap}mg"
        calculated = cap
        capped = True

    return calculated, capped, warning


# --- Test ---
print("=" * 50)
print("      DOSE CALCULATOR")
print("=" * 50)

name    = input("Patient Name  : ")
drug    = input("Drug          : ")
weight  = float(input("Weight (kg)   : "))
per_kg  = float(input("Dose (mg/kg)  : "))

dose, was_capped, warn = calculate_dose(weight, per_kg, drug)

if dose is None:
    print(f"\n{warn}")
else:
    print(f"\nPatient : {name}")
    print(f"Drug    : {drug.capitalize()}")
    print(f"Dose    : {dose} mg")
    if warn:
        print(warn)
    else:
        print("✅ Within safe limit")
```

---

## PRACTICAL 3 — Unit Conversion Library

**Goal:** Build a clean set of conversion functions with lambda and def versions.

```python
# --- Lambda conversions (simple, one-expression) ---
mg_to_mcg       = lambda mg   : round(mg * 1000, 3)
mcg_to_mg       = lambda mcg  : round(mcg / 1000, 3)
mg_to_g         = lambda mg   : round(mg / 1000, 4)
g_to_mg         = lambda g    : round(g * 1000, 2)
kg_to_lbs       = lambda kg   : round(kg * 2.205, 2)
lbs_to_kg       = lambda lbs  : round(lbs / 2.205, 2)
celsius_to_fahr = lambda c    : round((c * 9/5) + 32, 1)
fahr_to_celsius = lambda f    : round((f - 32) * 5/9, 1)


# --- Universal converter function ---
def convert_units(value, from_unit, to_unit):
    """
    Converts a pharmaceutical measurement between common units.

    Parameters:
        value (float)    : The quantity to convert
        from_unit (str)  : Source unit (mg, mcg, g, kg, lbs, C, F)
        to_unit (str)    : Target unit

    Returns:
        tuple: (converted_value: float, label: str) or (None, error_message: str)
    """
    converters = {
        ("mg",  "mcg"): mg_to_mcg,
        ("mcg", "mg") : mcg_to_mg,
        ("mg",  "g")  : mg_to_g,
        ("g",   "mg") : g_to_mg,
        ("kg",  "lbs"): kg_to_lbs,
        ("lbs", "kg") : lbs_to_kg,
        ("C",   "F")  : celsius_to_fahr,
        ("F",   "C")  : fahr_to_celsius,
    }

    key = (from_unit.strip(), to_unit.strip())
    func = converters.get(key)

    if func:
        return func(value), f"{value} {from_unit} = {func(value)} {to_unit}"
    else:
        return None, f"❌ Conversion from '{from_unit}' to '{to_unit}' not supported"


# --- Test ---
tests = [
    (500, "mg",  "mcg"),
    (2,   "g",   "mg"),
    (70,  "kg",  "lbs"),
    (37,  "C",   "F"),
    (98.6,"F",   "C"),
]

print("UNIT CONVERSION RESULTS:")
print("-" * 40)
for val, f, t in tests:
    _, label = convert_units(val, f, t)
    print(label)
```

---

## PRACTICAL 4 — Patient Risk Score Engine

**Goal:** Use multiple parameters, default values, and a calculated risk score returning both score and level.

```python
def calculate_patient_risk(age, bmi, glucose, systolic_bp,
                            is_smoker=False, is_diabetic=False,
                            has_kidney_disease=False):
    """
    Calculates a cardiovascular risk score for a patient.

    Parameters:
        age (int)               : Patient age in years
        bmi (float)             : Body Mass Index
        glucose (float)         : Fasting glucose in mg/dL
        systolic_bp (int)       : Systolic blood pressure in mmHg
        is_smoker (bool)        : Default False
        is_diabetic (bool)      : Default False
        has_kidney_disease (bool): Default False

    Returns:
        tuple: (score: int, risk_level: str, factors: list)
    """
    score   = 0
    factors = []

    if age > 60:
        score += 2
        factors.append(f"Age > 60 (+2)")

    if bmi >= 30:
        score += 2
        factors.append(f"BMI {bmi} — Obese (+2)")
    elif bmi >= 25:
        score += 1
        factors.append(f"BMI {bmi} — Overweight (+1)")

    if glucose > 126:
        score += 3
        factors.append(f"Glucose {glucose} mg/dL — Diabetic range (+3)")
    elif glucose > 100:
        score += 1
        factors.append(f"Glucose {glucose} mg/dL — Pre-diabetic (+1)")

    if systolic_bp > 140:
        score += 2
        factors.append(f"BP {systolic_bp} mmHg — Hypertensive (+2)")
    elif systolic_bp > 120:
        score += 1
        factors.append(f"BP {systolic_bp} mmHg — Elevated (+1)")

    if is_smoker:
        score += 2
        factors.append("Smoker (+2)")

    if is_diabetic:
        score += 2
        factors.append("Known diabetic (+2)")

    if has_kidney_disease:
        score += 3
        factors.append("Chronic kidney disease (+3)")

    if score >= 8:
        risk_level = "🔴 CRITICAL"
    elif score >= 5:
        risk_level = "🟠 HIGH"
    elif score >= 3:
        risk_level = "🟡 MODERATE"
    else:
        risk_level = "🟢 LOW"

    return score, risk_level, factors


# --- Test ---
print("=" * 55)
print("       PATIENT CARDIOVASCULAR RISK ASSESSMENT")
print("=" * 55)

score, level, factors = calculate_patient_risk(
    age=65, bmi=32.5, glucose=148, systolic_bp=158,
    is_smoker=False, is_diabetic=True, has_kidney_disease=False
)

print(f"\nRisk Score : {score}")
print(f"Risk Level : {level}")
print("\nContributing Factors:")
for f in factors:
    print(f"  • {f}")
```

---

## PRACTICAL 5 — Complete Pharmaceutical Function Library (Capstone)

**Goal:** Combine everything — call multiple functions in sequence to produce a full patient report.

```python
# ---- Reuse functions from Practicals 1–4 ----
# (calculate_bmi, classify_bmi, calculate_dose, convert_units,
#  calculate_patient_risk — defined in previous practicals)


def print_patient_report(name, age, weight_kg, height_m,
                          glucose, systolic_bp, drug, dose_per_kg,
                          is_diabetic=False, is_smoker=False):
    """
    Generates a complete patient pharmaceutical assessment report.

    Combines BMI analysis, dose calculation, and risk scoring
    into a single formatted output.
    """
    bmi, bmi_cat = analyse_bmi(weight_kg, height_m)
    dose, capped, dose_warn = calculate_dose(weight_kg, dose_per_kg, drug)
    score, risk, factors = calculate_patient_risk(
        age, bmi, glucose, systolic_bp,
        is_diabetic=is_diabetic, is_smoker=is_smoker
    )

    weight_lbs = kg_to_lbs(weight_kg)

    print("=" * 55)
    print(f"  PATIENT REPORT — {name.upper()}")
    print("=" * 55)
    print(f"  Age         : {age} years")
    print(f"  Weight      : {weight_kg} kg  ({weight_lbs} lbs)")
    print(f"  BMI         : {bmi}  ({bmi_cat})")
    print(f"  Glucose     : {glucose} mg/dL")
    print(f"  BP (Systolic): {systolic_bp} mmHg")
    print("-" * 55)
    print(f"  Prescribed  : {drug.capitalize()}")
    print(f"  Dose Calc.  : {dose} mg")
    if dose_warn:
        print(f"  {dose_warn}")
    print("-" * 55)
    print(f"  Risk Score  : {score}  |  Risk Level: {risk}")
    print("  Risk Factors:")
    for f in factors:
        print(f"    • {f}")
    print("=" * 55)


# --- Run ---
print_patient_report(
    name="Suresh Kumar",
    age=65, weight_kg=82, height_m=1.70,
    glucose=155, systolic_bp=160,
    drug="paracetamol", dose_per_kg=15,
    is_diabetic=True, is_smoker=False
)
```

---

## 🧠 Complete Session Key Takeaways

1. **Functions** eliminate repeated code — define once, call anywhere, fix in one place
2. **Parameters** are the input variables listed in the definition; **arguments** are the actual values passed during the call
3. **Positional arguments** are matched by order; **keyword arguments** are matched by name
4. **return** sends a value out of the function; without it, the function returns `None`
5. **Multiple return values** are returned as a tuple and can be unpacked in one line
6. **Guard clauses** — returning early when invalid input is detected — keep functions clean
7. **Default parameter values** make arguments optional, simplifying calls for common cases
8. **Local variables** exist only inside the function; **global variables** exist everywhere; prefer passing data through parameters rather than relying on globals
9. **Docstrings** document your functions — essential for maintainability in any real healthcare software project
10. **Lambda functions** are anonymous, one-expression shortcuts for simple conversions and sort keys

---

## ❓ Q&A Discussion

- "What is the difference between a parameter and an argument? Give a pharmacy example."
- "If a function has no `return` statement, what does it return, and how could this cause a bug?"
- "Why should you avoid using too many global variables in a pharmacy program?"
- "When would you use a lambda instead of writing a full `def` function?"

---

## 💻 Practice Exercises

**Exercise 1 — Creatinine Clearance:** Write a function `creatinine_clearance(age, weight, creatinine, gender="male")` using the Cockcroft-Gault formula. Include a proper docstring. Test with at least 3 patients.

**Exercise 2 — Prescription Label:** Write a function `print_label(patient, drug, dose, frequency="twice daily", doctor="unknown")` that prints a formatted prescription label. Use default values for the last two parameters.

**Exercise 3 — Drug Lookup:** Write a function `requires_prescription(drug_name)` that takes a drug name and returns `True` if it requires a prescription, `False` if it's OTC. Use a dictionary of at least 8 drugs inside the function.

**Exercise 4 — Lambda Library:** Write five unit-conversion lambdas not already covered in Practical 3: mL to L, L to mL, g/dL to mg/dL, days to hours, hours to minutes. Test each one.
