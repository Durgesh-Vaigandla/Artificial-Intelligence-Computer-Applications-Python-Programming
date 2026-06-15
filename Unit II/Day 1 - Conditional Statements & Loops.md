# Unit II – Day 1 (2 Hours)
## Conditional Statements & Looping in Python

---

## 🎯 Session Goals
By the end of this session, students will be able to:
- Write if/elif/else conditions in Python
- Use for and while loops
- Apply these to healthcare and dosage scenarios

---

## ⏱️ Session Plan (2 Hours)

| Time | Topic |
|------|-------|
| 0:00 – 0:15 | Quick recap of Unit I |
| 0:15 – 0:50 | Conditional statements with pharmacy examples |
| 0:50 – 1:30 | Loops — for and while |
| 1:30 – 1:50 | Combined exercise |
| 1:50 – 2:00 | Recap + Q&A |

---

## 1. Conditional Statements

### Basic if / elif / else

```python
if condition:
    # runs if condition is True
elif another_condition:
    # runs if this condition is True
else:
    # runs if nothing above is True
```

### Pharmacy Example: Dosage by Age

```python
age = int(input("Enter patient age: "))

if age < 2:
    print("Consult paediatrician — no standard dose")
elif age < 12:
    print("Paediatric dose: 125 mg")
elif age < 18:
    print("Adolescent dose: 250 mg")
else:
    print("Adult dose: 500 mg")
```

### Drug Interaction Check

```python
drug_1 = input("Drug 1: ").lower()
drug_2 = input("Drug 2: ").lower()

if drug_1 == "warfarin" and drug_2 == "aspirin":
    print("⚠️ WARNING: High bleeding risk — avoid combination")
elif drug_1 == "metformin" and drug_2 == "alcohol":
    print("⚠️ WARNING: Risk of lactic acidosis")
else:
    print("✅ No major interaction found in this check")
```

### BMI Classification

```python
weight = float(input("Weight (kg): "))
height = float(input("Height (m): "))

bmi = weight / (height ** 2)
print(f"BMI: {bmi:.2f}")

if bmi < 18.5:
    print("Category: Underweight")
elif bmi < 25:
    print("Category: Normal")
elif bmi < 30:
    print("Category: Overweight")
else:
    print("Category: Obese")
```

---

## 2. For Loops

### Basic Syntax

```python
for item in collection:
    # do something
```

### Example: Print Drug List

```python
drugs = ["Paracetamol", "Amoxicillin", "Metformin", "Atorvastatin"]

for drug in drugs:
    print("Drug:", drug)
```

### Range-based loop

```python
# Print tablet schedule for 5 days
for day in range(1, 6):
    print(f"Day {day}: Take 500mg Amoxicillin 3 times")
```

### Dose Calculation for Multiple Patients

```python
weights = [50, 65, 72, 80, 45]   # kg
dose_per_kg = 10                  # mg/kg

for weight in weights:
    total = weight * dose_per_kg
    print(f"Weight: {weight} kg → Dose: {total} mg")
```

---

## 3. While Loops

### Basic Syntax

```python
while condition:
    # runs as long as condition is True
```

### Medication Reminder Simulation

```python
doses_taken = 0
total_doses = 5

while doses_taken < total_doses:
    doses_taken += 1
    print(f"✅ Dose {doses_taken} of {total_doses} taken")

print("Course complete!")
```

### Input Validation (Practical Use)

```python
while True:
    age = int(input("Enter valid age (1-120): "))
    if 1 <= age <= 120:
        print(f"Age {age} accepted.")
        break
    else:
        print("Invalid age. Try again.")
```

---

## 4. Combined Exercise — Prescription Checker

```python
print("=== Prescription Safety Checker ===")

patient_name = input("Patient Name: ")
age = int(input("Age: "))
weight = float(input("Weight (kg): "))
drug = input("Drug prescribed: ").lower()
dose_prescribed = float(input("Dose prescribed (mg): "))

# Dose recommendation
if drug == "paracetamol":
    recommended_dose = weight * 15    # 15 mg/kg
else:
    recommended_dose = weight * 10

# Safety check
print(f"\n--- Report for {patient_name} ---")
print(f"Recommended dose: {recommended_dose:.1f} mg")
print(f"Prescribed dose:  {dose_prescribed} mg")

if dose_prescribed > recommended_dose * 1.2:
    print("⚠️ WARNING: Dose exceeds recommended by >20%")
elif dose_prescribed < recommended_dose * 0.8:
    print("⚠️ NOTE: Dose is below recommended by >20%")
else:
    print("✅ Dose is within safe range")
```

---

## 🧠 Key Takeaways

1. `if/elif/else` — decision making based on conditions
2. `for` loop — when you know how many times to repeat
3. `while` loop — when you repeat until a condition changes
4. All three are essential for dosage logic, patient checks, and data processing

---

## 💻 Practice Exercises

**Exercise 1:** Write a program that takes a creatinine clearance value and prints the kidney function category (Normal, Mild, Moderate, Severe impairment).

**Exercise 2:** Using a for loop, calculate and print doses for a list of 5 patients with different weights.

**Exercise 3:** Build a medicine reminder that counts down from 7 days using a while loop.
