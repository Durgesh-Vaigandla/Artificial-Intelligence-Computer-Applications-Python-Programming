# Experiment 13
## Develop a Pharmaceutical Calculator Using Python

**Software Used:** Jupyter Notebook / VS Code (Python)

---

## 🎯 Objective

To develop a multi-function Python program that performs common pharmaceutical calculations — dosage, BMI, and unit conversions — combining everything learned in Units I and II.

---

## 🧠 Why This Experiment Matters

This is your first complete, practical Python application. It brings together variables, operators, functions, conditionals, and input/output into one usable tool — exactly the kind of small utility a pharmacy might build internally for staff to use at the counter.

---

## 🛠️ Step-by-Step Procedure

### Step 1: Open Your IDE
1. Open **Jupyter Notebook** (recommended for this experiment) or **VS Code**
2. Create a new file/notebook: `pharma_calculator.ipynb` (or `.py` in VS Code)

### Step 2: Write the Dose Calculation Function
```python
def calculate_dose(weight_kg, dose_per_kg):
    """Calculates total drug dose based on patient weight."""
    total_dose = weight_kg * dose_per_kg
    return total_dose
```
Run this cell (Shift+Enter in Jupyter) to load the function into memory.

### Step 3: Write the BMI Calculation Function
```python
def calculate_bmi(weight_kg, height_m):
    """Calculates Body Mass Index and returns value + category."""
    bmi = weight_kg / (height_m ** 2)

    if bmi < 18.5:
        category = "Underweight"
    elif bmi < 25:
        category = "Normal"
    elif bmi < 30:
        category = "Overweight"
    else:
        category = "Obese"

    return round(bmi, 1), category
```

### Step 4: Write the Unit Conversion Function
```python
def convert_units(value, from_unit, to_unit):
    """Converts between common pharmaceutical units."""
    conversions = {
        ("mg", "mcg"): 1000,
        ("mcg", "mg"): 0.001,
        ("mg", "g"): 0.001,
        ("g", "mg"): 1000,
        ("kg", "lbs"): 2.205,
        ("lbs", "kg"): 0.4536,
    }
    factor = conversions.get((from_unit, to_unit))
    if factor:
        return round(value * factor, 3)
    else:
        return "Conversion not supported"
```

### Step 5: Write a Max-Dose Safety Check Function
```python
def check_max_dose(calculated_dose, drug_name):
    """Checks if calculated dose exceeds known safe maximum."""
    max_doses = {
        "paracetamol": 4000,
        "ibuprofen": 2400,
        "amoxicillin": 3000,
        "metformin": 2000,
    }
    max_allowed = max_doses.get(drug_name.lower())

    if max_allowed is None:
        return "⚠️ Drug not in safety database — verify manually"
    elif calculated_dose > max_allowed:
        return f"⚠️ WARNING: Dose exceeds max safe limit of {max_allowed}mg"
    else:
        return f"✅ Dose is within safe limit (max: {max_allowed}mg)"
```

### Step 6: Build the Main Menu Program
```python
def main():
    print("=" * 50)
    print("   PHARMACEUTICAL CALCULATOR")
    print("=" * 50)

    while True:
        print("\nChoose a calculation:")
        print("1. Dosage Calculator")
        print("2. BMI Calculator")
        print("3. Unit Converter")
        print("4. Exit")

        choice = input("Enter choice (1-4): ")

        if choice == "1":
            weight = float(input("Patient weight (kg): "))
            dose_per_kg = float(input("Dose per kg (mg/kg): "))
            drug = input("Drug name: ")

            total = calculate_dose(weight, dose_per_kg)
            print(f"\nCalculated Dose: {total} mg")
            print(check_max_dose(total, drug))

        elif choice == "2":
            weight = float(input("Weight (kg): "))
            height = float(input("Height (m): "))

            bmi, category = calculate_bmi(weight, height)
            print(f"\nBMI: {bmi} — Category: {category}")

        elif choice == "3":
            value = float(input("Value to convert: "))
            from_u = input("From unit (mg/mcg/g/kg/lbs): ")
            to_u = input("To unit (mg/mcg/g/kg/lbs): ")

            result = convert_units(value, from_u, to_u)
            print(f"\nResult: {value} {from_u} = {result} {to_u}")

        elif choice == "4":
            print("\nThank you for using the Pharmaceutical Calculator!")
            break

        else:
            print("Invalid choice. Please enter 1-4.")

# Run the program
main()
```

### Step 7: Run and Test the Program
1. Run all cells in order (Jupyter) or run the full script (VS Code: `Ctrl+F5`)
2. Test each menu option:
   - **Option 1:** Enter weight `60`, dose per kg `15`, drug `paracetamol` → should calculate 900mg and confirm it's safe
   - **Option 2:** Enter weight `68.5`, height `1.65` → should return BMI and category
   - **Option 3:** Convert `500` from `mg` to `mcg` → should return `500000`
   - **Option 4:** Should print thank-you message and stop the loop

### Step 8: Test the Safety Warning
- Run Option 1 again with weight `70`, dose per kg `70`, drug `paracetamol` (this gives 4900mg — exceeding the 4000mg max)
- Confirm the warning message displays correctly

### Step 9: Save Your Work
- **Jupyter:** File → Save and Checkpoint → ensure filename is `pharma_calculator.ipynb`
- **VS Code:** `Ctrl + S`, ensure filename is `pharma_calculator.py`

---

## ✅ Expected Output

A fully working, menu-driven Python program offering Dosage Calculation (with safety check), BMI Calculation (with category), and Unit Conversion — running in a continuous loop until the user selects Exit.

---

## 📝 Viva/Record Questions

1. Why was each calculation written as a separate function instead of one long program?
2. What does the `while True:` loop do in the `main()` function, and how does it eventually stop?
3. Why does `check_max_dose()` use `.lower()` on the drug name before looking it up?
4. What would happen if a user entered text instead of a number for weight? (Try it — what error appears?)

---

## 🔁 Practice Variation

Add a 5th menu option: **"Creatinine Clearance Calculator"** using the Cockcroft-Gault formula:
```
CrCl (mL/min) = [(140 - age) × weight(kg)] / (72 × serum_creatinine(mg/dL))
[× 0.85 if female]
```
