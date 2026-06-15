# Unit III – Day 1 (2 Hours)
## Data Structures — Lists, Tuples, Dictionaries

---

## 🎯 Session Goals
By the end of this session, students will be able to:
- Use lists, tuples, and dictionaries to store healthcare data
- Apply indexing, slicing, and common operations
- Build simple drug and patient data structures

---

## ⏱️ Session Plan (2 Hours)

| Time | Topic |
|------|-------|
| 0:00 – 0:10 | Recap Unit II |
| 0:10 – 0:40 | Lists — operations & pharmacy use |
| 0:40 – 1:00 | Tuples |
| 1:00 – 1:40 | Dictionaries — patient & drug records |
| 1:40 – 2:00 | Recap + Q&A |

---

## 1. Lists

> A list is an **ordered, changeable** collection.

```python
drug_inventory = ["Paracetamol", "Amoxicillin", "Metformin", "Atorvastatin", "Ibuprofen"]
```

### Indexing & Slicing

```python
print(drug_inventory[0])      # Paracetamol
print(drug_inventory[-1])     # Ibuprofen
print(drug_inventory[1:3])    # ['Amoxicillin', 'Metformin']
```

### Common List Operations

```python
# Add drug
drug_inventory.append("Omeprazole")

# Remove drug
drug_inventory.remove("Ibuprofen")

# Check if drug exists
if "Metformin" in drug_inventory:
    print("In stock")

# Count items
print(f"Total drugs in stock: {len(drug_inventory)}")

# Sort alphabetically
drug_inventory.sort()
print(drug_inventory)
```

### List of Patient Weights

```python
patient_weights = [55, 70, 62, 80, 48, 91, 67]

print(f"Heaviest patient: {max(patient_weights)} kg")
print(f"Lightest patient: {min(patient_weights)} kg")
print(f"Average weight  : {sum(patient_weights)/len(patient_weights):.1f} kg")
```

---

## 2. Tuples

> A tuple is an **ordered, unchangeable** collection. Use for fixed data.

```python
# Drug details that shouldn't change
drug_info = ("Paracetamol", 500, "mg", "Analgesic")
name, dose, unit, category = drug_info

print(f"{name} {dose}{unit} — {category}")
```

### When to use Tuple vs List?

| Tuple | List |
|-------|------|
| Data that doesn't change | Data that may change |
| Drug classification | Inventory count |
| Patient blood type | Patient prescriptions |
| Lab reference ranges | Lab test results |

```python
# Reference ranges (fixed — use tuple)
normal_glucose = (70, 100)    # mg/dL fasting
normal_bp = (90, 120)         # mmHg systolic

patient_glucose = 95
if normal_glucose[0] <= patient_glucose <= normal_glucose[1]:
    print("Glucose: Normal")
else:
    print("Glucose: Abnormal")
```

---

## 3. Dictionaries

> A dictionary stores **key-value pairs**. Perfect for structured records.

```python
patient = {
    "name": "Rahul Sharma",
    "age": 45,
    "weight": 72,
    "blood_group": "B+",
    "conditions": ["Diabetes", "Hypertension"],
    "current_drugs": ["Metformin", "Amlodipine"]
}
```

### Accessing Data

```python
print(patient["name"])           # Rahul Sharma
print(patient["conditions"])     # ['Diabetes', 'Hypertension']
print(patient.get("allergies", "None recorded"))  # Safe access
```

### Updating Data

```python
patient["age"] = 46
patient["current_drugs"].append("Atorvastatin")
```

### Drug Database as Dictionary

```python
drug_db = {
    "paracetamol": {
        "class": "Analgesic/Antipyretic",
        "dose_per_kg": 15,
        "max_daily_dose": 4000,
        "requires_rx": False
    },
    "amoxicillin": {
        "class": "Antibiotic",
        "dose_per_kg": 25,
        "max_daily_dose": 3000,
        "requires_rx": True
    },
    "metformin": {
        "class": "Antidiabetic",
        "dose_per_kg": None,
        "max_daily_dose": 2000,
        "requires_rx": True
    }
}

# Lookup
drug = "amoxicillin"
info = drug_db[drug]
print(f"{drug.capitalize()} — {info['class']}")
print(f"Prescription required: {info['requires_rx']}")
```

---

## 4. Nested Structures (Real Hospital Data)

```python
hospital_patients = [
    {
        "id": "P001",
        "name": "Priya",
        "age": 32,
        "prescriptions": [
            {"drug": "Ibuprofen", "dose": 400, "days": 5},
            {"drug": "Omeprazole", "dose": 20, "days": 5}
        ]
    },
    {
        "id": "P002",
        "name": "Suresh",
        "age": 58,
        "prescriptions": [
            {"drug": "Metformin", "dose": 500, "days": 30},
            {"drug": "Atorvastatin", "dose": 10, "days": 30}
        ]
    }
]

# Print all prescriptions for all patients
for patient in hospital_patients:
    print(f"\nPatient: {patient['name']} (ID: {patient['id']})")
    for rx in patient["prescriptions"]:
        print(f"  → {rx['drug']} {rx['dose']}mg for {rx['days']} days")
```

---

## 🧠 Key Takeaways

1. **List** — ordered, changeable — use for drug inventory, patient lists
2. **Tuple** — ordered, fixed — use for reference ranges, drug classifications
3. **Dictionary** — key-value pairs — use for patient records, drug databases
4. These structures are the foundation of all data management in Python

---

## 💻 Practice Exercises

**Exercise 1:** Create a list of 5 drugs. Write code to add a new drug, remove one, and print the final sorted list.

**Exercise 2:** Create a patient dictionary with at least 6 fields. Write code to print a formatted patient summary.

**Exercise 3:** Using the hospital_patients nested structure above, calculate the total number of tablets for each patient across all prescriptions.
