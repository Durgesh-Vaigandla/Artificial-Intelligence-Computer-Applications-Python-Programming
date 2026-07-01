# Unit II – Day 1 (2 Hours)
## Conditional Statements & Loops in Python — Complete Guide for Pharmacy Students

---

## 🎯 Session Goals
By the end of this session, you will be able to:
- Understand what control flow means and why Python needs it
- Write if, elif, else conditions confidently with real pharmacy logic
- Use nested conditions and logical operators to handle complex clinical rules
- Write for loops — iterating over lists, ranges, and collections of patient data
- Write while loops — repeating until a condition changes, validating user input
- Use break, continue, and pass correctly inside loops
- Understand loop control tools like range(), enumerate(), and zip()
- Apply all of this practically by building dosage checkers, patient scanners, and medication reminders

---

## ⏱️ Session Plan (2 Hours)

| Time | Block | Topic |
|------|-------|-------|
| 0:00 – 0:05 | — | Recap of Unit I, session overview |
| 0:05 – 1:00 | **THEORY** | Control flow → if/elif/else → nested conditions → for loops → while loops → loop control |
| 1:00 – 1:55 | **PRACTICAL** | Hands-on programs — dosage by age, drug interactions, patient scanner, medication reminder |
| 1:55 – 2:00 | — | Recap + Q&A |

> 💬 **How to use this document:** Part A covers every concept with explanations first, then small code illustrations. Part B is where you build real, complete programs combining everything. Don't jump to Part B before you've read Part A — understanding *why* each structure works is more important than memorizing the syntax.

---
---
---

# 🅰️ PART A — THEORY

---

# SECTION 1 — What is Control Flow?

## 1.1 The Problem Without Control Flow

Look at this program from Unit I:

```python
weight = 70
dose_per_kg = 15
total_dose = weight * dose_per_kg
print(total_dose)
```

This works fine for one patient — but Python just runs every line top-to-bottom, in order, without making any decisions. In the real world, a pharmacist does NOT just multiply and print. A pharmacist **asks questions first**:

- Is this patient an adult or a child? The dose is different.
- Does this patient have kidney disease? The dose needs adjustment.
- Is this drug even safe for this patient's age?

And a pharmacist does NOT stop after one patient — they process prescription after prescription, all day long. Python needs to do the same.

**Control flow** is the term for Python's ability to:
1. **Make decisions** — running different code depending on conditions
2. **Repeat actions** — doing the same task for many patients or many iterations

Python has two tools for this: **Conditional Statements** (if/elif/else) for decisions, and **Loops** (for/while) for repetition.

---

# SECTION 2 — Conditional Statements (if / elif / else)

## 2.1 The if Statement

> An **if statement** tells Python: "Only run this block of code IF this condition is True."

### Syntax

```python
if condition:
    # this block runs only when condition is True
    # note: indented with 4 spaces — this is how Python knows this belongs to the if
```

### The Most Important Rule — Indentation

Python uses **indentation** (spaces at the start of a line) to define which lines of code belong inside a condition or loop. This is not optional decoration — it is the grammar of Python.

```python
# ✅ CORRECT — the print is indented, so it belongs to the if
if age < 18:
    print("Paediatric dosing needed")

# ❌ WRONG — the print is not indented, so Python treats it as separate code
# that always runs, no matter what
if age < 18:
print("Paediatric dosing needed")     # IndentationError
```

> 💬 "In pharmacy, indentation works like a checklist beneath a condition. Everything indented under `if age < 18:` only happens when the patient is under 18 — just like a form that says 'if patient is a child, complete section B.'"

### Simple Example

```python
glucose = 145

if glucose >= 126:
    print("⚠️ Glucose is in diabetic range")
    print("Refer for HbA1c testing")
```

Because `145 >= 126` is `True`, both indented lines run. If `glucose` were `90`, neither would run.

---

## 2.2 The else Clause

> **else** provides a fallback block that runs when the if condition is False — covering "everything else."

### Syntax

```python
if condition:
    # runs when True
else:
    # runs when False
```

### Example — Dose Safety Check

```python
dose_prescribed = 5000   # mg
max_daily_dose = 4000    # mg — Paracetamol safe limit

if dose_prescribed > max_daily_dose:
    print("⚠️ OVERDOSE WARNING — Dose exceeds safe daily limit")
else:
    print("✅ Dose is within safe limits")
```

Here exactly one of the two blocks runs — never both, never neither.

---

## 2.3 The elif Clause

> **elif** (short for "else if") lets you check multiple conditions in sequence. Python works through them top-to-bottom and runs the first one that is True, then skips all the rest.

### Syntax

```python
if condition_1:
    # runs if condition_1 is True
elif condition_2:
    # runs if condition_1 is False AND condition_2 is True
elif condition_3:
    # runs if conditions 1 and 2 are False AND condition_3 is True
else:
    # runs if ALL conditions above are False
```

### Example — Glucose Classification

```python
glucose = float(input("Enter fasting glucose (mg/dL): "))

if glucose < 70:
    print("🔴 HYPOGLYCAEMIA — Immediate action required")
elif glucose <= 100:
    print("🟢 Normal")
elif glucose <= 125:
    print("🟡 Pre-diabetic range — lifestyle intervention recommended")
else:
    print("🔴 Diabetic range — medical review required")
```

> 💬 "This is exactly how a clinical decision support system (CDSS) categorises lab results — a series of thresholds, checked in order, with the first matching one triggering the appropriate alert."

### Why Order Matters in elif Chains

```python
glucose = 80

# ✅ CORRECT ordering — most specific / restrictive first
if glucose < 70:
    print("Hypoglycaemia")
elif glucose <= 100:
    print("Normal")

# ❌ WRONG ordering — the first condition catches too broadly
if glucose <= 100:
    print("Normal")     # This catches 80 — correct
elif glucose < 70:
    print("Hypoglycaemia")    # This NEVER runs — 80 < 70 is False anyway,
                               # but 60 would also hit "Normal" first, and
                               # Hypoglycaemia would never be reported
```

Put the most specific (narrowest) conditions first.

---

## 2.4 Logical Operators — Combining Conditions

Often a clinical decision depends on more than one condition at once. Python's logical operators let you combine them.

| Operator | Meaning | Returns True when |
|----------|---------|-------------------|
| `and` | Both must be True | Both sides are True |
| `or` | At least one must be True | Either side is True |
| `not` | Reverses the condition | The condition is False |

### and — Both Conditions Must Be Met

```python
systolic_bp = 155
glucose = 148
is_diabetic = True

# High risk: BOTH elevated BP AND high glucose
if systolic_bp > 140 and glucose > 126:
    print("⚠️ High cardiovascular risk — dual-risk patient")
```

### or — Either Condition Is Enough to Trigger

```python
is_pregnant = False
has_liver_disease = True

# Drug contraindicated if EITHER condition exists
if is_pregnant or has_liver_disease:
    print("⚠️ Contraindicated — do not dispense without physician review")
```

### not — Reversing a Condition

```python
requires_prescription = True

if not requires_prescription:
    print("OTC drug — can be dispensed without prescription")
else:
    print("Prescription required")
```

### Combining All Three

```python
age = 65
bmi = 32
is_smoker = False
is_diabetic = True

# High cardiovascular risk: (older AND obese) AND (diabetic OR smoker)
high_risk = (age > 60 and bmi > 30) and (is_diabetic or is_smoker)

if high_risk:
    print("⚠️ HIGH CARDIOVASCULAR RISK — refer for specialist review")
else:
    print("Standard care pathway")
```

---

## 2.5 Nested if Statements

A nested if is an if statement placed inside another if statement — for handling multi-level decisions.

```python
age = int(input("Patient age: "))
weight = float(input("Patient weight (kg): "))

if age >= 18:
    print("Adult patient")
    if weight < 40:
        print("Low body weight — dose reduction recommended")
        dose = 250
    elif weight <= 80:
        print("Normal weight range")
        dose = 500
    else:
        print("High body weight — consult for adjusted dose")
        dose = 750
    print(f"Recommended dose: {dose} mg")
else:
    print("Paediatric patient — use weight-based paediatric dosing")
    dose = weight * 15
    print(f"Recommended dose: {dose:.0f} mg")
```

> 💬 "Nested conditions mirror real clinical decision trees — first check: is the patient adult or child? Then, within adult patients, what is their weight? Each level adds more precision to the decision."

---

## 2.6 Ternary (One-Line) If Expression

For very simple decisions, Python allows a compact one-line form:

```python
# Full form
if bmi >= 25:
    weight_status = "Overweight"
else:
    weight_status = "Normal"

# One-line equivalent
weight_status = "Overweight" if bmi >= 25 else "Normal"
print(weight_status)
```

Use this only when the decision is simple and the line stays readable. For anything complex, stick to the full if/else.

---
---

# SECTION 3 — For Loops

## 3.1 What is a For Loop?

> A **for loop** repeats a block of code once for each item in a collection — a list, a range of numbers, a string, or any iterable. Use it when you know (or can determine) how many times you need to repeat.

### Syntax

```python
for variable in collection:
    # this block runs once for each item
    # 'variable' takes the value of each item in turn
```

---

## 3.2 Iterating Over a List

The most common use — doing something with each item in a list.

```python
drugs = ["Paracetamol", "Amoxicillin", "Metformin", "Atorvastatin"]

for drug in drugs:
    print(f"Drug in stock: {drug}")
```

Output:
```
Drug in stock: Paracetamol
Drug in stock: Amoxicillin
Drug in stock: Metformin
Drug in stock: Atorvastatin
```

On the first iteration, `drug = "Paracetamol"`. On the second, `drug = "Amoxicillin"`. The loop automatically moves through every item.

### With a Condition Inside

```python
drugs_in_stock = ["Paracetamol", "Amoxicillin", "Metformin"]
drugs_needed = ["Metformin", "Aspirin", "Paracetamol", "Ibuprofen"]

for drug in drugs_needed:
    if drug in drugs_in_stock:
        print(f"✅ {drug} — Available")
    else:
        print(f"❌ {drug} — OUT OF STOCK")
```

---

## 3.3 The range() Function

`range()` generates a sequence of numbers — it's what you use when you need to loop a specific number of times rather than over an existing list.

```python
# range(stop)               → 0 to stop-1
# range(start, stop)        → start to stop-1
# range(start, stop, step)  → start to stop-1, jumping by step
```

```python
# Print day-by-day medication schedule
for day in range(1, 8):    # 1 through 7
    print(f"Day {day}: Take Amoxicillin 500mg — 3 times daily")
```

```python
# Count down remaining tablets — checking in increments of 5
stock = 30
for remaining in range(stock, 0, -5):    # 30, 25, 20, 15...
    print(f"{remaining} tablets remaining")
```

---

## 3.4 enumerate() — Loop With Index

When you need both the item AND its position number in the list:

```python
patients = ["Rahul", "Priya", "Suresh", "Anitha"]

for index, name in enumerate(patients, start=1):
    print(f"Patient {index}: {name}")
```

Output:
```
Patient 1: Rahul
Patient 2: Priya
Patient 3: Suresh
Patient 4: Anitha
```

> 💬 "This is useful when generating numbered prescription lists or patient queue numbers — you need both the position AND the name."

---

## 3.5 zip() — Loop Over Two Lists Together

When you have two related lists and need to process matching pairs:

```python
patients = ["Rahul", "Priya", "Suresh"]
weights  = [72, 58, 85]

for patient, weight in zip(patients, weights):
    dose = weight * 15    # 15 mg/kg
    print(f"{patient} ({weight} kg) → Dose: {dose} mg")
```

Output:
```
Rahul (72 kg) → Dose: 1080 mg
Priya (58 kg) → Dose: 870 mg
Suresh (85 kg) → Dose: 1275 mg
```

---

## 3.6 Iterating Over a String

A string is itself a sequence of characters — a for loop goes through it one character at a time:

```python
drug_code = "PCM500"

for character in drug_code:
    print(character)
```

---

## 3.7 Nested For Loops

A for loop inside another for loop — the inner loop completes all its iterations for every single iteration of the outer loop.

```python
patients = ["Rahul", "Priya", "Suresh"]
times    = ["Morning", "Afternoon", "Night"]

for patient in patients:
    print(f"\nSchedule for {patient}:")
    for time in times:
        print(f"  → Take 500mg Paracetamol: {time}")
```

---
---

# SECTION 4 — While Loops

## 4.1 What is a While Loop?

> A **while loop** keeps repeating a block of code as long as a condition remains True. Unlike a for loop (where you know how many times to repeat), use a while loop when you don't know in advance how many times you'll need to repeat — you only know the stopping condition.

### Syntax

```python
while condition:
    # this block keeps running as long as condition is True
    # at some point, the condition must become False — otherwise infinite loop!
```

> ⚠️ **Infinite loop warning:** If the condition in a while loop never becomes False, the program runs forever and freezes. Always make sure something inside the loop will eventually make the condition False — or use `break` to exit.

---

## 4.2 Basic While Loop — Counting Down

```python
doses_remaining = 5

while doses_remaining > 0:
    print(f"💊 Take your dose. {doses_remaining} doses remaining.")
    doses_remaining -= 1    # this line is critical — without it, loop runs forever

print("Course of medication complete.")
```

Output:
```
💊 Take your dose. 5 doses remaining.
💊 Take your dose. 4 doses remaining.
💊 Take your dose. 3 doses remaining.
💊 Take your dose. 2 doses remaining.
💊 Take your dose. 1 doses remaining.
Course of medication complete.
```

---

## 4.3 Input Validation — The Most Practical Use

When you're asking a user to enter data, you don't know how many attempts it will take before they enter something valid. A while loop keeps asking until they do.

```python
while True:
    age_input = input("Enter patient age (1-120): ")

    if age_input.isdigit():
        age = int(age_input)
        if 1 <= age <= 120:
            print(f"✅ Age {age} accepted.")
            break    # exits the while True loop
        else:
            print("❌ Age must be between 1 and 120. Try again.")
    else:
        print("❌ Please enter a number only.")
```

> 💬 "`while True` creates an intentional infinite loop, but the `break` inside gives us a clean, controlled exit. This is the standard Python pattern for 'keep asking until valid input is given' — exactly what a pharmacy registration system needs to prevent garbage data entering the database."

---

## 4.4 While Loop with a Counter

```python
attempts = 0
max_attempts = 3

while attempts < max_attempts:
    password = input("Enter pharmacy system password: ")
    attempts += 1

    if password == "pharmacy2025":
        print("✅ Access granted")
        break
    else:
        remaining = max_attempts - attempts
        if remaining > 0:
            print(f"❌ Wrong password. {remaining} attempts remaining.")
        else:
            print("🔒 Account locked. Contact administrator.")
```

---
---

# SECTION 5 — Loop Control: break, continue, pass

## 5.1 break — Exit the Loop Immediately

`break` stops the loop entirely and jumps to the code after it, regardless of how many iterations remain.

```python
drugs_to_check = ["Paracetamol", "Amoxicillin", "BANNED_DRUG", "Metformin"]

for drug in drugs_to_check:
    if drug == "BANNED_DRUG":
        print(f"🚨 BANNED SUBSTANCE DETECTED: {drug} — halting check!")
        break
    print(f"✅ {drug} — cleared")
```

Output:
```
✅ Paracetamol — cleared
✅ Amoxicillin — cleared
🚨 BANNED SUBSTANCE DETECTED: BANNED_DRUG — halting check!
```

---

## 5.2 continue — Skip This Iteration, Keep Going

`continue` skips the rest of the current iteration and moves straight to the next one.

```python
lab_results = [95, -1, 140, -1, 88, 210]
# -1 means the test was not completed

for result in lab_results:
    if result == -1:
        continue    # skip incomplete results
    if result > 126:
        print(f"⚠️ HIGH: {result} mg/dL")
    else:
        print(f"✅ Normal: {result} mg/dL")
```

Output:
```
✅ Normal: 95 mg/dL
⚠️ HIGH: 140 mg/dL
✅ Normal: 88 mg/dL
⚠️ HIGH: 210 mg/dL
```

---

## 5.3 pass — Placeholder (Do Nothing)

`pass` is used when Python syntactically requires a block of code, but you have nothing to put there yet.

```python
for drug in drugs:
    if drug == "Warfarin":
        pass    # TODO: add high-alert handling here later
    else:
        print(f"Processing: {drug}")
```

---
---
---

# 🅱️ PART B — PRACTICAL

> 💬 Now that every concept has been explained, open Jupyter Notebook or VS Code, and build each program below from scratch — typing each line yourself, not copy-pasting. The understanding happens during the typing.

---

## PRACTICAL 1 — Dosage Decision by Age and Weight

**Goal:** Use if/elif/else to determine dosage tier, then calculate the dose.

```python
print("=" * 45)
print("     PARACETAMOL DOSE CALCULATOR")
print("=" * 45)

name   = input("Patient Name  : ")
age    = int(input("Age (years)   : "))
weight = float(input("Weight (kg)   : "))

# Tier 1: Determine dose per kg based on age
if age < 2:
    dose_per_kg = 0
    note = "Consult paediatrician — no standard self-dose for under 2 years"
elif age < 12:
    dose_per_kg = 15    # paediatric
    note = "Paediatric dose: 15 mg/kg"
elif age < 18:
    dose_per_kg = 15    # adolescent same as paediatric
    note = "Adolescent dose: 15 mg/kg"
else:
    dose_per_kg = 10    # adult — or use fixed 500-1000mg
    note = "Adult dose applied"

print(f"\n--- Prescription for {name} ---")

if dose_per_kg == 0:
    print(f"⚠️  {note}")
else:
    total_dose = weight * dose_per_kg

    print(f"Age category  : {note}")
    print(f"Calculated    : {weight} kg × {dose_per_kg} mg/kg = {total_dose:.0f} mg")

    # Tier 2: Safety cap
    MAX_SINGLE_DOSE = 1000
    if total_dose > MAX_SINGLE_DOSE:
        print(f"⚠️  Cap applied: dose reduced to max {MAX_SINGLE_DOSE} mg per single dose")
        total_dose = MAX_SINGLE_DOSE

    print(f"Final Dose    : {total_dose:.0f} mg")
```

**Now extend it yourself:** Add a check — if the patient's weight is below 3 kg, print a warning and stop dosage calculation.

---

## PRACTICAL 2 — Glucose + Blood Pressure Risk Classifier

**Goal:** Combine multiple elif chains and logical operators to classify a patient's overall risk.

```python
print("=" * 45)
print("   PATIENT RISK CLASSIFICATION")
print("=" * 45)

name     = input("Patient Name  : ")
glucose  = float(input("Fasting Glucose (mg/dL): "))
systolic = int(input("Systolic BP (mmHg)     : "))
age      = int(input("Age (years)            : "))

# --- Glucose Classification ---
if glucose < 70:
    glucose_status = "HYPOGLYCAEMIA"
    g_flag = "🔴"
elif glucose <= 100:
    glucose_status = "Normal"
    g_flag = "🟢"
elif glucose <= 125:
    glucose_status = "Pre-Diabetic"
    g_flag = "🟡"
else:
    glucose_status = "Diabetic Range"
    g_flag = "🔴"

# --- Blood Pressure Classification ---
if systolic < 90:
    bp_status = "Hypotensive"
    bp_flag = "🔴"
elif systolic <= 120:
    bp_status = "Normal"
    bp_flag = "🟢"
elif systolic <= 140:
    bp_status = "Elevated"
    bp_flag = "🟡"
else:
    bp_status = "Hypertensive"
    bp_flag = "🔴"

# --- Overall Risk ---
is_elderly    = age > 60
is_diabetic   = glucose > 126
is_hypertensive = systolic > 140

if is_diabetic and is_hypertensive and is_elderly:
    overall = "🔴 CRITICAL RISK — Urgent specialist referral"
elif (is_diabetic or is_hypertensive) and is_elderly:
    overall = "🟠 HIGH RISK — Pharmacist review recommended"
elif is_diabetic or is_hypertensive:
    overall = "🟡 MODERATE RISK — Monitor closely"
else:
    overall = "🟢 LOW RISK — Routine follow-up"

# --- Output ---
print(f"\n--- Report: {name} (Age {age}) ---")
print(f"Glucose    : {g_flag} {glucose} mg/dL — {glucose_status}")
print(f"Blood Pres : {bp_flag} {systolic} mmHg — {bp_status}")
print(f"Overall    : {overall}")
```

---

## PRACTICAL 3 — Multi-Patient Dose Calculator Using For Loop

**Goal:** Use for loop + zip() to process a list of patients and calculate doses.

```python
print("=" * 50)
print("   BATCH DOSE CALCULATION — WARD ROUND")
print("=" * 50)

patients = ["Rahul Sharma", "Priya Nair", "Suresh Kumar", "Anitha Reddy", "Mohan Rao"]
weights  = [72, 58, 85, 55, 78]   # kg
drug     = "Amoxicillin"
dose_per_kg = 25                   # mg/kg for Amoxicillin

print(f"\nDrug: {drug} | Dose: {dose_per_kg} mg/kg")
print("-" * 50)

for index, (patient, weight) in enumerate(zip(patients, weights), start=1):
    total_dose = weight * dose_per_kg

    # Cap at maximum daily dose of 3000mg
    if total_dose > 3000:
        flag = " ⚠️  [CAPPED AT MAX 3000 mg]"
        total_dose = 3000
    else:
        flag = ""

    print(f"{index}. {patient:<20} {weight:>5} kg → {total_dose:>6.0f} mg{flag}")

print("-" * 50)
print(f"Total patients processed: {len(patients)}")
```

---

## PRACTICAL 4 — Drug Inventory Stock Scanner

**Goal:** Use for loop + break + continue to scan a drug list for issues.

```python
print("=" * 50)
print("       PHARMACY STOCK SCANNER")
print("=" * 50)

inventory = [
    {"name": "Paracetamol 500mg", "stock": 240, "near_expiry": False},
    {"name": "Amoxicillin 500mg", "stock": 12, "near_expiry": False},
    {"name": "Metformin 500mg",   "stock": 0,  "near_expiry": False},
    {"name": "Atorvastatin 10mg", "stock": 80, "near_expiry": True},
    {"name": "Ibuprofen 400mg",   "stock": 35, "near_expiry": False},
]

print("\nScanning stock...\n")

for drug in inventory:
    name       = drug["name"]
    stock      = drug["stock"]
    near_expiry = drug["near_expiry"]

    if stock == 0:
        print(f"🔴 OUT OF STOCK    : {name}")
        continue    # skip further checks for this drug

    if stock < 20:
        print(f"🟡 LOW STOCK       : {name} — only {stock} units remaining")

    if near_expiry:
        print(f"🟠 NEAR EXPIRY     : {name} — arrange return/disposal")

    if stock >= 20 and not near_expiry:
        print(f"🟢 OK              : {name} — {stock} units in stock")

print("\nScan complete.")
```

---

## PRACTICAL 5 — Medication Reminder with While Loop

**Goal:** Use while loop + break + continue to simulate a medication intake tracker.

```python
print("=" * 50)
print("     MEDICATION INTAKE TRACKER")
print("=" * 50)

drug          = "Amoxicillin 500mg"
total_doses   = 21    # 3 times a day for 7 days
doses_taken   = 0
doses_skipped = 0

print(f"\nDrug: {drug}")
print(f"Total course: {total_doses} doses\n")

while doses_taken + doses_skipped < total_doses:
    dose_number = doses_taken + doses_skipped + 1
    response    = input(f"Dose {dose_number} of {total_doses} — Did patient take dose? (y/n/q): ").lower()

    if response == "q":
        print("\n⛔ Session ended early by user.")
        break

    if response == "y":
        doses_taken += 1
        print(f"   ✅ Recorded. ({doses_taken} taken, {doses_skipped} skipped so far)\n")

    elif response == "n":
        doses_skipped += 1
        print(f"   ⚠️  Skipped dose noted. ({doses_taken} taken, {doses_skipped} skipped so far)\n")

    else:
        print("   ❓ Please enter y, n, or q\n")
        continue

# Summary
print("=" * 50)
print(f"  Course Summary: {drug}")
print(f"  Doses Taken   : {doses_taken}")
print(f"  Doses Skipped : {doses_skipped}")
adherence = (doses_taken / total_doses) * 100 if total_doses > 0 else 0
print(f"  Adherence     : {adherence:.1f}%")
if adherence >= 80:
    print("  Status        : ✅ Good adherence")
else:
    print("  Status        : ⚠️  Poor adherence — counsel patient")
print("=" * 50)
```

---

## 🧠 Complete Session Key Takeaways

1. **Control flow** gives Python the ability to make decisions and repeat actions — essential for any real clinical program
2. **if / elif / else** — Python checks each condition top-to-bottom; the first True one runs, the rest are skipped; order matters
3. **Indentation** is Python's grammar — inconsistent indentation causes errors, not just ugliness
4. **Logical operators** (`and`, `or`, `not`) combine conditions — critical for multi-factor clinical decisions
5. **Nested if** statements handle multi-level decisions (adult vs child, then weight tier within adult)
6. **for loop** — use when you have a defined collection (list, range) to iterate through; processes every item
7. **range(start, stop, step)** — generates number sequences for counted repetition; doesn't include the stop value
8. **enumerate()** — gives both index and value; **zip()** — processes two lists in parallel
9. **while loop** — use when the stopping point is a condition, not a count; always ensure the condition eventually becomes False
10. **break** exits the loop immediately; **continue** skips to the next iteration; **pass** is a placeholder

---

## ❓ Q&A Discussion

- "Why does Python use indentation instead of curly braces `{}` like other languages?"
- "If a patient's glucose is exactly 100 mg/dL, which branch runs — `glucose <= 100` (Normal) or `glucose <= 125` (Pre-diabetic)? Why?"
- "What's the difference between a `for` loop and a `while` loop — when would you choose one over the other in a pharmacy program?"
- "What happens if you forget the `break` inside a `while True:` loop?"

---

## 💻 Practice Exercises

**Exercise 1 — BP Dosage Rule:** Write an if/elif/else program that takes systolic BP as input and prints the corresponding antihypertensive recommendation: Normal (no drug), Elevated (lifestyle advice), Stage 1 (Amlodipine 5mg), Stage 2 Hypertension (Amlodipine 10mg + Lisinopril).

**Exercise 2 — Drug List Checker:** Given a list of 6 drugs and a separate list of drugs that are contraindicated for a patient, use a for loop to print which drugs on the list are safe and which are contraindicated.

**Exercise 3 — Creatinine Input Validator:** Using a while loop, keep asking the user for a creatinine clearance value until they enter a number between 0 and 150. Then print the kidney function category (Normal ≥ 90; Mildly reduced 60–89; Moderately reduced 30–59; Severely reduced < 30).

**Exercise 4 — Weekly Dose Schedule:** Using nested for loops, print a complete 7-day dose schedule for a patient taking 3 drugs — one loop for days (1 to 7), one loop for each drug.
