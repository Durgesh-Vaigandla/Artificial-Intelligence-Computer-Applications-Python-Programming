    # Unit I – Day 3 (2 Hours)
## Python for Healthcare — Installation, IDEs, Variables, Data Types, Operators, Input/Output, String Manipulation & Standard Libraries

---

## 🎯 Session Goals
By the end of this session, students will be able to:
- Install Python and set up Jupyter Notebook and VS Code
- Write and run Python programs in both IDEs
- Declare variables and identify correct data types
- Use all categories of operators with pharmacy examples
- Take user input and display formatted output
- Apply string manipulation techniques to drug and patient data
- Use standard libraries (math, datetime, random) for pharmaceutical calculations

---

## ⏱️ Session Plan (2 Hours)

| Time | Topic |
|------|-------|
| 0:00 – 0:05 | Recap of Day 2, session overview |
| 0:05 – 0:25 | Python installation + Jupyter Notebook + VS Code setup |
| 0:25 – 0:50 | Variables and Data Types — with pharmacy examples |
| 0:50 – 1:15 | Operators — arithmetic, comparison, logical, assignment |
| 1:15 – 1:35 | Input / Output operations and formatting |
| 1:35 – 1:55 | String manipulation techniques |
| 1:55 – 2:00 | Standard libraries intro + Recap |

---

---

# SECTION 1 — Python Installation & IDEs
## (0:05 – 0:25 | 20 minutes)

---

## 1.1 Why Python?

Before installing, students should understand why Python is the right choice for pharmaceutical sciences:

| Reason | Explanation |
|--------|-------------|
| **Readable syntax** | Reads like English — easy to learn even without programming background |
| **Free & open source** | No licensing cost — important for students and small clinics |
| **Massive library ecosystem** | NumPy, Pandas, Matplotlib, SciPy — all built for data analysis |
| **Used in industry** | Pfizer, AstraZeneca, Roche, AIIMS all use Python for research |
| **Versatile** | Used for data analysis, automation, web apps, AI/ML |
| **Community support** | Largest programming community in the world |

---

## 1.2 Installing Python

### Step 1: Download
Go to: **https://www.python.org/downloads/**
- Download the latest stable version (Python 3.x)
- Choose your operating system: Windows / macOS / Linux

### Step 2: Install on Windows
- Run the downloaded installer
- ✅ **IMPORTANT:** Check "Add Python to PATH" before clicking Install
- Click "Install Now"
- Wait for installation to complete

### Step 3: Verify Installation
Open Command Prompt (Windows) or Terminal (Mac/Linux):
```bash
python --version
```
Expected output: `Python 3.12.x`

Also verify pip (Python package installer):
```bash
pip --version
```

---

## 1.3 Jupyter Notebook — IDE for Learning & Data Analysis

### What is Jupyter Notebook?
> Jupyter Notebook is a web-based interactive environment where you can write Python code in "cells" and see the output immediately below each cell.

It is the **most popular tool** in data science, research, and teaching because:
- Code + output + notes all in one document
- Run one cell at a time — perfect for learning step by step
- Share notebooks with colleagues — they see code AND results
- Used in pharmaceutical research for data analysis reports

### Installing Jupyter Notebook
```bash
pip install notebook
```

### Launching Jupyter Notebook
```bash
jupyter notebook
```
This opens a browser window. Click "New" → "Python 3" to create a new notebook.

### Jupyter Notebook Interface — Key Concepts

```
┌─────────────────────────────────────────────────────────┐
│  Jupyter Notebook — my_pharmacy_analysis.ipynb          │
├─────────────────────────────────────────────────────────┤
│  [Markdown Cell]                                        │
│  # Drug Dosage Calculator                               │
│  This notebook calculates doses for pharmacy students.  │
├─────────────────────────────────────────────────────────┤
│  [Code Cell]                          [Run ▶]           │
│  weight = 70                                            │
│  dose_per_kg = 15                                       │
│  total_dose = weight * dose_per_kg                      │
│  print(total_dose)                                      │
├─────────────────────────────────────────────────────────┤
│  1050                             ← Output appears here │
├─────────────────────────────────────────────────────────┤
│  [Code Cell]                          [Run ▶]           │
│  # Next calculation here                                │
└─────────────────────────────────────────────────────────┘
```

**Cell types:**
- **Code cells** — Write and run Python code
- **Markdown cells** — Write formatted notes and headings

**Key shortcuts:**
- `Shift + Enter` — Run current cell and move to next
- `Ctrl + Enter` — Run current cell, stay in same cell
- `A` — Insert cell above (in command mode)
- `B` — Insert cell below (in command mode)
- `M` — Change cell to Markdown
- `Y` — Change cell to Code

---

## 1.4 VS Code — IDE for Building Applications

### What is VS Code?
> Visual Studio Code (VS Code) is a full-featured code editor — lightweight, fast, and highly customizable. Used by professional developers worldwide.

Best for: Writing Python scripts, building applications, working with files and databases.

### Installing VS Code
1. Download from: **https://code.visualstudio.com/**
2. Install for your operating system
3. Open VS Code
4. Go to Extensions (left sidebar, squares icon)
5. Search "Python" → Install the Microsoft Python extension
6. Search "Jupyter" → Install the Jupyter extension (allows notebooks inside VS Code)

### Running Python in VS Code
1. Create a new file: `File → New File → Save as dosage_calculator.py`
2. Write your Python code
3. Right-click → "Run Python File in Terminal"
   OR press `Ctrl + F5`

### Jupyter vs VS Code — When to Use Which?

| Situation | Use |
|-----------|-----|
| Learning Python for the first time | Jupyter Notebook |
| Analyzing a dataset step by step | Jupyter Notebook |
| Writing a pharmaceutical data report | Jupyter Notebook |
| Building a dosage calculator program | VS Code |
| Writing a program that reads CSV files | VS Code |
| Professional software development | VS Code |

> 💬 "For this course, we will use Jupyter Notebook for most exercises because you can see results immediately. When we build larger programs, we'll switch to VS Code."

---

## 1.5 First Python Program

In Jupyter Notebook, type in a code cell and press Shift+Enter:

```python
print("Hello, Pharmacy Students!")
print("Welcome to Python for Healthcare")
```

Output:
```
Hello, Pharmacy Students!
Welcome to Python for Healthcare
```

**What happened?**
- `print()` is a built-in Python function
- Everything inside the quotes is displayed on screen
- Python runs line by line, top to bottom

---

---

# SECTION 2 — Variables and Data Types
## (0:25 – 0:50 | 25 minutes)

---

## 2.1 What is a Variable?

> A **variable** is a named storage location in memory that holds a value. Think of it as a labelled container.

```python
# This creates a variable named 'drug_name' and stores "Paracetamol" in it
drug_name = "Paracetamol"

# This creates a variable named 'dose_mg' and stores 500 in it
dose_mg = 500
```

### Rules for Variable Names
- Must start with a letter or underscore (`_`)
- Cannot start with a number
- No spaces — use underscores instead (`drug_dose` not `drug dose`)
- Case sensitive: `Dose` and `dose` are different variables
- Cannot be a Python keyword (if, for, while, print, etc.)

```python
# ✅ Valid variable names
patient_name = "Rahul"
dose_mg = 500
_temp_value = 37.5
drug1 = "Amoxicillin"

# ❌ Invalid variable names
2drug = "Aspirin"        # starts with number
drug name = "Aspirin"    # contains space
for = 500                # 'for' is a Python keyword
```

---

## 2.2 Data Types in Python

Python automatically determines the type of a variable based on the value assigned.

### The 4 Core Data Types

---

### Type 1: Integer (int)
> Whole numbers — no decimal point

```python
patient_age = 45
tablet_count = 21
dose_mg = 500
ward_number = 3
days_of_treatment = 7

print(type(patient_age))    # <class 'int'>
```

**Pharmacy use cases:**
- Age, tablet count, number of doses per day, ward number, days of treatment

---

### Type 2: Float (float)
> Numbers with a decimal point

```python
drug_concentration = 12.5       # mg/L
bmi = 27.4
half_life_hours = 2.5
body_weight = 68.3              # kg
temperature = 37.2              # °C
dose_per_kg = 15.0              # mg/kg

print(type(drug_concentration))    # <class 'float'>
```

**Pharmacy use cases:**
- Drug concentrations, BMI, half-life, body weight, temperature, dose per kg

> 💬 "Always use float when the value can be a decimal. Blood glucose of 126.5 mg/dL stored as int becomes 126 — you lose precision. In pharmacy, precision matters."

---

### Type 3: String (str)
> Text — any sequence of characters enclosed in quotes (single or double)

```python
patient_name = "Rahul Sharma"
drug_name = 'Amoxicillin'
diagnosis = "Type 2 Diabetes Mellitus"
blood_group = "B+"
route_of_admin = "Oral"
dosage_form = "Film-coated tablet"
manufacturer = "Cipla Ltd."

print(type(patient_name))    # <class 'str'>
```

**Pharmacy use cases:**
- Patient name, drug name, diagnosis, instructions, manufacturer, warnings

**Strings can use single or double quotes:**
```python
name1 = "Priya"      # double quotes
name2 = 'Suresh'     # single quotes — both work the same
```

---

### Type 4: Boolean (bool)
> Can only be `True` or `False` — represents yes/no, on/off conditions

```python
requires_prescription = True
is_allergic_to_penicillin = False
is_pregnant = False
has_liver_disease = True
drug_in_stock = True
is_controlled_substance = False

print(type(requires_prescription))    # <class 'bool'>
```

**Pharmacy use cases:**
- Prescription requirement, allergy flags, contraindications, stock availability

---

## 2.3 Checking and Converting Data Types

### Checking Type
```python
dose = 500
conc = 12.5
name = "Metformin"
in_stock = True

print(type(dose))      # <class 'int'>
print(type(conc))      # <class 'float'>
print(type(name))      # <class 'str'>
print(type(in_stock))  # <class 'bool'>
```

### Type Conversion
```python
# String to Integer
age_text = "45"                  # This is a string — cannot do maths on it
age_number = int(age_text)       # Now it is an integer
print(age_number + 5)            # 50

# String to Float
dose_text = "500.5"
dose_number = float(dose_text)   # 500.5 as float

# Integer to Float
tablets = 3
tablets_float = float(tablets)   # 3.0

# Number to String (for display)
dose = 500
message = "Dose is " + str(dose) + " mg"
print(message)                   # Dose is 500 mg
```

> 💬 "When you use `input()` to ask a user to type something, Python always receives it as a string — even if they type 500. You must convert it: `dose = int(input('Enter dose: '))`"

---

## 2.4 Multiple Variable Assignment

```python
# Assign same value to multiple variables
systolic = diastolic = heart_rate = 0

# Assign different values in one line
drug, dose, frequency = "Metformin", 500, 2

print(drug)       # Metformin
print(dose)       # 500
print(frequency)  # 2
```

---

## 2.5 Pharmacy Variable Examples — Putting It Together

```python
# Complete patient medication record in variables
patient_name        = "Kavitha Reddy"       # str
patient_age         = 52                     # int
patient_weight_kg   = 68.5                   # float
is_diabetic         = True                   # bool
is_hypertensive     = True                   # bool
allergy             = "Sulfa drugs"          # str

drug_name           = "Metformin"            # str
dose_mg             = 500                    # int
doses_per_day       = 2                      # int
treatment_days      = 30                     # int
total_tablets       = doses_per_day * treatment_days   # 60

print(f"Patient: {patient_name}, Age: {patient_age}")
print(f"Drug: {drug_name} {dose_mg}mg — {doses_per_day}x daily for {treatment_days} days")
print(f"Total tablets to dispense: {total_tablets}")
print(f"Known allergy: {allergy}")
```

---

---

# SECTION 3 — Operators
## (0:50 – 1:15 | 25 minutes)

---

## 3.1 Arithmetic Operators

Used for mathematical calculations — essential for dosage, BMI, concentration calculations.

| Operator | Symbol | Example | Result |
|----------|--------|---------|--------|
| Addition | `+` | `500 + 250` | `750` |
| Subtraction | `-` | `1000 - 400` | `600` |
| Multiplication | `*` | `70 * 15` | `1050` |
| Division | `/` | `1050 / 3` | `350.0` |
| Floor Division | `//` | `1050 // 3` | `350` (no decimal) |
| Modulus | `%` | `1050 % 7` | `0` (remainder) |
| Exponent | `**` | `2 ** 3` | `8` |

### Pharmacy Arithmetic Examples

```python
# 1. Total Daily Dose
single_dose = 500           # mg
doses_per_day = 3
total_daily_dose = single_dose * doses_per_day
print(f"Total daily dose: {total_daily_dose} mg")   # 1500 mg

# 2. Dose per kg body weight
patient_weight = 68         # kg
dose_per_kg = 15            # mg/kg (Paracetamol paediatric dose)
calculated_dose = patient_weight * dose_per_kg
print(f"Calculated dose: {calculated_dose} mg")      # 1020 mg

# 3. BMI Calculation
weight = 68.5               # kg
height = 1.65               # metres
bmi = weight / (height ** 2)
print(f"BMI: {bmi:.2f}")                            # 25.18

# 4. Drug half-life — concentration remaining after 2 half-lives
initial_conc = 100          # mg/L
half_life = 4               # hours
time_elapsed = 8            # hours
concentration_remaining = initial_conc * (0.5 ** (time_elapsed / half_life))
print(f"Remaining concentration: {concentration_remaining} mg/L")   # 25.0 mg/L

# 5. How many full tablets from total dose
total_dose_needed = 750     # mg
tablet_strength = 250       # mg per tablet
tablets_needed = total_dose_needed // tablet_strength
print(f"Tablets needed: {tablets_needed}")           # 3 tablets
```

---

## 3.2 Comparison Operators

Return `True` or `False` — used in conditions and safety checks.

| Operator | Symbol | Meaning |
|----------|--------|---------|
| Equal to | `==` | Is left equal to right? |
| Not equal to | `!=` | Is left different from right? |
| Greater than | `>` | Is left greater than right? |
| Less than | `<` | Is left less than right? |
| Greater than or equal | `>=` | |
| Less than or equal | `<=` | |

### Pharmacy Examples

```python
patient_age = 17
max_daily_dose = 4000       # mg — Paracetamol
prescribed_dose = 4500      # mg

# Is dose safe?
print(prescribed_dose <= max_daily_dose)       # False — dose exceeded

# Is patient a minor?
print(patient_age < 18)                        # True — paediatric dosing needed

# Check glucose level
fasting_glucose = 130
print(fasting_glucose >= 126)                  # True — diabetic range

# Check blood pressure
systolic_bp = 135
print(systolic_bp == 120)                      # False — not normal
print(systolic_bp > 140)                       # False — not hypertensive
print(systolic_bp > 130)                       # True — elevated (pre-hypertensive)
```

---

## 3.3 Logical Operators

Combine multiple conditions together.

| Operator | Meaning | Result is True when |
|----------|---------|---------------------|
| `and` | Both conditions must be true | Both sides are True |
| `or` | At least one condition must be true | Either side is True |
| `not` | Reverses the condition | Condition is False |

### Pharmacy Examples

```python
is_pregnant = False
has_kidney_disease = True
is_diabetic = True
on_warfarin = True

# Drug contraindicated if EITHER condition present
contraindicated = is_pregnant or has_kidney_disease
print(f"Drug contraindicated: {contraindicated}")   # True

# High risk patient: diabetic AND on warfarin
high_risk = is_diabetic and on_warfarin
print(f"High risk: {high_risk}")                    # True

# Not pregnant (safe for this drug)
safe_for_this_drug = not is_pregnant
print(f"Safe to prescribe: {safe_for_this_drug}")   # True

# Complex condition — refer for specialist if high risk AND not being monitored
being_monitored = False
refer_to_specialist = high_risk and not being_monitored
print(f"Refer to specialist: {refer_to_specialist}")  # True
```

---

## 3.4 Assignment Operators

| Operator | Example | Equivalent To |
|----------|---------|---------------|
| `=` | `x = 10` | Assign 10 to x |
| `+=` | `x += 5` | `x = x + 5` |
| `-=` | `x -= 3` | `x = x - 3` |
| `*=` | `x *= 2` | `x = x * 2` |
| `/=` | `x /= 4` | `x = x / 4` |

### Pharmacy Example

```python
# Tracking doses remaining in a prescription
tablets_dispensed = 60

# Patient takes 2 tablets daily — after 3 days, reduce count
tablets_dispensed -= 6      # 60 - 6 = 54
print(f"Tablets remaining: {tablets_dispensed}")   # 54

# Drug concentration doubles if dose doubled
current_concentration = 5.0   # mg/L
current_concentration *= 2
print(f"New concentration: {current_concentration} mg/L")  # 10.0
```

---

---

# SECTION 4 — Input / Output Operations
## (1:15 – 1:35 | 20 minutes)

---

## 4.1 Output — print()

The `print()` function displays output to the screen.

```python
# Basic print
print("Amoxicillin 500mg")

# Print a variable
drug = "Metformin"
print(drug)

# Print multiple items
dose = 500
print("Drug:", drug, "| Dose:", dose, "mg")

# Print with end parameter (default is newline)
print("Taking ", end="")
print("Amoxicillin")    # Output: Taking Amoxicillin (on same line)

# Print empty line
print()
```

---

## 4.2 Formatted Output — f-strings (Most Important)

F-strings are the modern, clean way to embed variables inside text:

```python
patient_name = "Priya Nair"
drug = "Amoxicillin"
dose = 500
frequency = 3
days = 7

# f-string — put f before the quote, variables inside {}
print(f"Patient: {patient_name}")
print(f"Prescription: {drug} {dose}mg — {frequency} times a day for {days} days")
print(f"Total tablets: {frequency * days}")   # Can do maths inside {}
```

Output:
```
Patient: Priya Nair
Prescription: Amoxicillin 500mg — 3 times a day for 7 days
Total tablets: 21
```

### Formatting Numbers in f-strings

```python
bmi = 27.384627
concentration = 12.56789

print(f"BMI: {bmi:.2f}")              # 2 decimal places: 27.38
print(f"Concentration: {concentration:.1f} mg/L")   # 1 decimal: 12.6
print(f"Dose: {1050:,} mcg")          # Thousands comma: 1,050 mcg
```

---

## 4.3 Input — input()

The `input()` function pauses the program and waits for the user to type something.

```python
# Basic input — always returns a string
name = input("Enter patient name: ")
print(f"Hello, {name}!")
```

### Converting Input to Numbers

```python
# User types: 68
weight = float(input("Enter patient weight (kg): "))
height = float(input("Enter patient height (m): "))
age = int(input("Enter patient age: "))

bmi = weight / (height ** 2)
print(f"\nPatient Age: {age}")
print(f"Weight: {weight} kg | Height: {height} m")
print(f"BMI: {bmi:.2f}")
```

---

## 4.4 Practical Program — Patient Registration & Dosage

```python
# ============================================
# PATIENT REGISTRATION & DOSAGE CALCULATOR
# ============================================

print("=" * 45)
print("    PATIENT REGISTRATION FORM")
print("=" * 45)

# Collect patient details
patient_name  = input("Patient Name    : ")
age           = int(input("Age             : "))
weight        = float(input("Weight (kg)     : "))
height        = float(input("Height (m)      : "))
drug          = input("Drug Prescribed : ")
dose_per_kg   = float(input("Dose per kg (mg): "))
frequency     = int(input("Doses per day   : "))
days          = int(input("Treatment days  : "))

# Calculations
bmi            = weight / (height ** 2)
total_dose     = weight * dose_per_kg
total_tablets  = frequency * days

# Display Report
print("\n" + "=" * 45)
print("    PRESCRIPTION SUMMARY")
print("=" * 45)
print(f"Patient        : {patient_name.upper()}")
print(f"Age            : {age} years")
print(f"Weight         : {weight} kg")
print(f"BMI            : {bmi:.1f}")
print(f"Drug           : {drug.capitalize()}")
print(f"Dose           : {total_dose:.0f} mg per dose")
print(f"Frequency      : {frequency}x daily for {days} days")
print(f"Total tablets  : {total_tablets}")
print("=" * 45)
```

---

---

# SECTION 5 — String Manipulation Techniques
## (1:35 – 1:55 | 20 minutes)

---

## 5.1 What is a String?

> A **string** is a sequence of characters — letters, numbers, spaces, symbols — enclosed in quotes.

In pharmacy, strings are everywhere: patient names, drug names, dosage instructions, prescription labels, warnings, manufacturer details.

---

## 5.2 String Operations

### Length
```python
drug = "Paracetamol"
print(len(drug))           # 11
```

### Accessing Characters — Indexing
```python
drug = "Paracetamol"
#        0123456789 10

print(drug[0])      # P   — first character
print(drug[-1])     # l   — last character
print(drug[4])      # c
```

### Slicing — Extracting Parts of a String
```python
drug_code = "PCM-500-TAB-STRIP"

print(drug_code[0:3])      # PCM    — drug abbreviation
print(drug_code[4:7])      # 500    — dose
print(drug_code[8:11])     # TAB    — dosage form
print(drug_code[12:])      # STRIP  — packaging
print(drug_code[:3])       # PCM    — from start to index 3
print(drug_code[-5:])      # STRIP  — last 5 characters
```

---

## 5.3 String Methods

### Case Methods

```python
drug = "paracetamol"

print(drug.upper())          # PARACETAMOL
print(drug.lower())          # paracetamol
print(drug.capitalize())     # Paracetamol
print(drug.title())          # Paracetamol

patient = "RAHUL SHARMA"
print(patient.lower())       # rahul sharma
print(patient.title())       # Rahul Sharma
```

**Why it matters:** Input from users may come in any case. Always normalize before comparing:
```python
user_input = "AMOXICILLIN"
if user_input.lower() == "amoxicillin":
    print("Drug found in database")
```

---

### Search Methods

```python
instruction = "Take 1 tablet twice daily after meals"

print(instruction.find("tablet"))       # 7 — position where 'tablet' starts
print(instruction.count("l"))           # 4 — how many 'l' characters
print("daily" in instruction)           # True — check if word exists
print("injection" in instruction)       # False
print(instruction.startswith("Take"))   # True
print(instruction.endswith("meals"))    # True
```

---

### Modification Methods

```python
drug_label = "  Metformin 500mg  "
print(drug_label.strip())          # "Metformin 500mg" — removes surrounding spaces
print(drug_label.lstrip())         # Removes left spaces only
print(drug_label.rstrip())         # Removes right spaces only

warning = "Keep out of reach of children"
print(warning.replace("children", "patients"))  # Replace a word

# Split a string into a list
medicines = "Metformin, Amlodipine, Atorvastatin, Aspirin"
drug_list = medicines.split(", ")
print(drug_list)    # ['Metformin', 'Amlodipine', 'Atorvastatin', 'Aspirin']
print(drug_list[0]) # Metformin

# Join a list back into a string
joined = " | ".join(drug_list)
print(joined)       # Metformin | Amlodipine | Atorvastatin | Aspirin
```

---

## 5.4 Practical: Prescription Label Generator

```python
print("\n=== PRESCRIPTION LABEL GENERATOR ===\n")

# Input
patient  = input("Patient Name   : ").strip().title()
drug     = input("Drug Name      : ").strip().capitalize()
dose     = input("Dose (mg)      : ").strip()
freq     = input("Times per day  : ").strip()
days     = input("Duration (days): ").strip()
warnings = input("Warnings       : ").strip()
doctor   = input("Doctor Name    : ").strip().title()

# Format label
label = f"""
╔══════════════════════════════════════╗
║         PHARMACY PRESCRIPTION        ║
╠══════════════════════════════════════╣
║  Patient  : {patient:<26}║
║  Drug     : {drug:<26}║
║  Dose     : {dose + ' mg':<26}║
║  Take     : {freq + ' times daily for ' + days + ' days':<26}║
║  Warning  : {warnings:<26}║
║  Doctor   : Dr. {doctor:<23}║
╚══════════════════════════════════════╝
"""
print(label)
```

---

## 5.5 String Formatting — Other Methods

```python
# format() method (older style)
name = "Rahul"
dose = 500
print("Patient: {} — Dose: {} mg".format(name, dose))

# % formatting (oldest style — still seen in old code)
print("Patient: %s — Dose: %d mg" % (name, dose))

# f-string (modern — preferred)
print(f"Patient: {name} — Dose: {dose} mg")
```

> 💬 "Use f-strings always. They are the cleanest and most readable. The others exist in older code you may encounter."

---

---

# SECTION 6 — Introduction to Standard Libraries
## (1:55 – 2:00 | brief overview)

---

## 6.1 What are Standard Libraries?

> Python's **standard library** is a collection of modules (ready-made code) that come with Python — no installation needed. Use `import` to load them.

---

## 6.2 The math Module

```python
import math

# Square root — used in BMI, pharmacokinetic calculations
print(math.sqrt(144))          # 12.0

# Pi — useful in pharmacology (circular dose calculations)
print(math.pi)                 # 3.141592653589793

# Ceiling and floor — rounding doses up/down
dose_calculated = 487.3
print(math.ceil(dose_calculated))    # 488 — round up
print(math.floor(dose_calculated))   # 487 — round down

# Logarithm — used in drug elimination calculations
print(math.log(100))           # Natural log

# Power (same as ** operator)
print(math.pow(2, 10))         # 1024.0

# Drug half-life calculation
import math
C0 = 100           # Initial concentration mg/L
k = 0.173          # Elimination rate constant (1/hr)
t = 4              # Time in hours

C_t = C0 * math.exp(-k * t)
print(f"Concentration at {t} hours: {C_t:.2f} mg/L")
```

---

## 6.3 The datetime Module

```python
from datetime import date, datetime

# Today's date
today = date.today()
print(f"Today: {today}")                       # 2024-06-15

# Current date and time
now = datetime.now()
print(f"Now: {now.strftime('%d/%m/%Y %H:%M')}")   # 15/06/2024 10:30

# Drug expiry check
from datetime import date

expiry_date = date(2025, 3, 31)     # Drug expires 31 March 2025
today = date.today()

days_remaining = (expiry_date - today).days
print(f"Days until expiry: {days_remaining}")

if days_remaining < 30:
    print("⚠️ Drug expiring soon — flag for return")
elif days_remaining < 0:
    print("❌ Drug has EXPIRED — do not dispense")
else:
    print("✅ Drug is within expiry")
```

---

## 6.4 The random Module

```python
import random

# Random patient ID generator
patient_id = "P" + str(random.randint(1000, 9999))
print(f"Generated Patient ID: {patient_id}")    # e.g., P4827

# Randomly select a drug from a list (useful for quiz programs)
drug_list = ["Paracetamol", "Amoxicillin", "Metformin", "Atorvastatin"]
random_drug = random.choice(drug_list)
print(f"Quiz drug: {random_drug}")
```

---

## 🧠 Full Session Key Takeaways

1. **Python** is the leading language for healthcare data analysis — free, readable, powerful
2. **Jupyter Notebook** = interactive learning and analysis; **VS Code** = building programs
3. **Variables** store data; names must be meaningful and follow naming rules
4. **4 core data types:** `int` (whole numbers), `float` (decimals), `str` (text), `bool` (True/False)
5. **Type conversion** — `int()`, `float()`, `str()` — essential when working with `input()`
6. **Arithmetic operators** perform dosage and pharmacokinetic calculations
7. **Comparison operators** (`>, <, ==`) evaluate safety conditions
8. **Logical operators** (`and`, `or`, `not`) combine multiple clinical conditions
9. **f-strings** are the modern, clean way to format output
10. **String methods** — `.upper()`, `.replace()`, `.split()`, `.strip()` — handle all text processing
11. **Standard libraries** — `math`, `datetime`, `random` — extend Python without installation

---

## 💻 Practice Exercises

**Exercise 1 — Variables & Types:**
Create variables for a complete patient record: name (str), age (int), weight (float), blood group (str), is_diabetic (bool), current drug (str), dose (int). Print a formatted patient summary.

**Exercise 2 — Operators:**
Write a program that:
- Takes patient weight as input
- Calculates Paracetamol dose (15 mg/kg)
- Calculates Ibuprofen dose (10 mg/kg)
- Checks if either dose exceeds their respective max (Paracetamol: 1g per dose, Ibuprofen: 800mg per dose)
- Prints a formatted report

**Exercise 3 — Input/Output:**
Build a prescription generator that takes: patient name, drug name, dose, frequency, duration, and doctor name — then prints a clean formatted prescription label using f-strings.

**Exercise 4 — String Manipulation:**
Given the string `"METFORMIN-500MG-TABLET-CIPLA"`:
- Extract the drug name (METFORMIN)
- Extract the dose (500MG)
- Extract the form (TABLET)
- Extract the manufacturer (CIPLA)
- Print each on a separate line in Title Case

**Exercise 5 — Standard Libraries:**
Using the `math` and `datetime` modules:
- Calculate the concentration of a drug after 6 hours (C0 = 80 mg/L, k = 0.15)
- Check if a drug with expiry date 31/12/2024 is still valid today
- Print both results clearly

---

## ❓ Q&A Discussion

- "Why must we write `age = int(input('Enter age: '))` instead of just `age = input('Enter age: ')`?"
- "What data type would you use to store a patient's blood pressure reading like 120/80?"
- "If a drug name comes in as 'PARACETAMOL' from one system and 'paracetamol' from another, how would you compare them in Python?"
