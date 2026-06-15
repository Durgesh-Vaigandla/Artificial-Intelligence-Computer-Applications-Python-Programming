# Unit III – Day 3 (2 Hours)
## Healthcare Databases — Pharmacy Drug Databases & Patient Information Systems

---

## 🎯 Session Goals
By the end of this session, students will be able to:
- Understand healthcare database structure and design
- Simulate a pharmacy drug database in Python
- Build a simple patient information retrieval system

---

## ⏱️ Session Plan (2 Hours)

| Time | Topic |
|------|-------|
| 0:00 – 0:10 | Recap Day 2 |
| 0:10 – 0:40 | Healthcare database design |
| 0:40 – 1:15 | Pharmacy drug database simulation |
| 1:15 – 1:50 | Patient information retrieval system |
| 1:50 – 2:00 | Recap + Q&A |

---

## 1. Healthcare Database Design

### Why Databases in Pharmacy?

- Store thousands of drug records
- Link patients to their prescriptions
- Track drug inventory and expiry
- Search and retrieve patient history instantly

### Standard Pharmacy Database Tables

```
DRUGS
├── DrugID (PK)
├── DrugName
├── GenericName
├── Category
├── DoseStrength (mg)
├── RequiresPrescription (Yes/No)
├── MaxDailyDose
└── StorageCondition

PATIENTS
├── PatientID (PK)
├── Name
├── Age
├── BloodGroup
├── Allergies
└── ChronicConditions

PRESCRIPTIONS
├── RxID (PK)
├── PatientID (FK → PATIENTS)
├── DrugID (FK → DRUGS)
├── Dose
├── Frequency
├── Days
└── PrescribedDate

INVENTORY
├── DrugID (FK)
├── BatchNumber
├── Quantity
├── ExpiryDate
└── SupplierName
```

---

## 2. Pharmacy Drug Database in Python (Using Dictionaries + CSV)

### Step 1: Build the Drug Database

```python
import csv

drug_database = [
    {"DrugID": "D001", "DrugName": "Paracetamol", "GenericName": "Acetaminophen",
     "Category": "Analgesic", "DoseStrength": 500, "RequiresPrescription": "No",
     "MaxDailyDose": 4000},
    {"DrugID": "D002", "DrugName": "Amoxicillin", "GenericName": "Amoxicillin",
     "Category": "Antibiotic", "DoseStrength": 500, "RequiresPrescription": "Yes",
     "MaxDailyDose": 3000},
    {"DrugID": "D003", "DrugName": "Metformin", "GenericName": "Metformin HCl",
     "Category": "Antidiabetic", "DoseStrength": 500, "RequiresPrescription": "Yes",
     "MaxDailyDose": 2000},
    {"DrugID": "D004", "DrugName": "Atorvastatin", "GenericName": "Atorvastatin Calcium",
     "Category": "Statin", "DoseStrength": 10, "RequiresPrescription": "Yes",
     "MaxDailyDose": 80},
    {"DrugID": "D005", "DrugName": "Omeprazole", "GenericName": "Omeprazole",
     "Category": "PPI", "DoseStrength": 20, "RequiresPrescription": "No",
     "MaxDailyDose": 40},
]

# Save to CSV
with open("drug_database.csv", "w", newline="") as f:
    writer = csv.DictWriter(f, fieldnames=drug_database[0].keys())
    writer.writeheader()
    writer.writerows(drug_database)

print("Drug database created and saved.")
```

### Step 2: Search the Drug Database

```python
def search_drug(query):
    results = []
    with open("drug_database.csv", "r") as f:
        reader = csv.DictReader(f)
        for row in reader:
            if query.lower() in row["DrugName"].lower() or query.lower() in row["GenericName"].lower():
                results.append(row)
    return results

query = input("Search drug: ")
found = search_drug(query)

if found:
    for drug in found:
        print(f"\nDrug       : {drug['DrugName']} ({drug['GenericName']})")
        print(f"Category   : {drug['Category']}")
        print(f"Strength   : {drug['DoseStrength']} mg")
        print(f"Rx Required: {drug['RequiresPrescription']}")
        print(f"Max Daily  : {drug['MaxDailyDose']} mg")
else:
    print("Drug not found in database.")
```

---

## 3. Patient Information System

```python
import csv
from datetime import date

# --- Patient Records ---
patients = {}

def add_patient(pid, name, age, blood_group, allergies, conditions):
    patients[pid] = {
        "PatientID": pid,
        "Name": name,
        "Age": age,
        "BloodGroup": blood_group,
        "Allergies": allergies,
        "Conditions": conditions,
        "Prescriptions": []
    }
    print(f"✅ Patient {name} added (ID: {pid})")

def add_prescription(pid, drug, dose, frequency, days):
    if pid not in patients:
        print("Patient not found.")
        return
    rx = {
        "Drug": drug,
        "Dose": dose,
        "Frequency": frequency,
        "Days": days,
        "Date": str(date.today())
    }
    patients[pid]["Prescriptions"].append(rx)
    print(f"✅ Prescription added for {patients[pid]['Name']}")

def get_patient_record(pid):
    if pid not in patients:
        print("Patient not found.")
        return
    p = patients[pid]
    print(f"\n{'='*40}")
    print(f" PATIENT RECORD — {p['PatientID']}")
    print(f"{'='*40}")
    print(f" Name        : {p['Name']}")
    print(f" Age         : {p['Age']}")
    print(f" Blood Group : {p['BloodGroup']}")
    print(f" Allergies   : {', '.join(p['Allergies']) if p['Allergies'] else 'None'}")
    print(f" Conditions  : {', '.join(p['Conditions']) if p['Conditions'] else 'None'}")
    if p["Prescriptions"]:
        print(f"\n Prescriptions:")
        for rx in p["Prescriptions"]:
            print(f"   → {rx['Drug']} {rx['Dose']}mg — {rx['Frequency']}x/day for {rx['Days']} days ({rx['Date']})")
    else:
        print("\n No prescriptions on record.")
    print("="*40)

# --- Demo Run ---
add_patient("P001", "Rahul Sharma", 45, "B+", ["Penicillin"], ["Diabetes", "Hypertension"])
add_patient("P002", "Priya Nair", 32, "O+", [], ["Hypothyroidism"])

add_prescription("P001", "Metformin", 500, 2, 30)
add_prescription("P001", "Amlodipine", 5, 1, 30)
add_prescription("P002", "Levothyroxine", 50, 1, 60)

get_patient_record("P001")
get_patient_record("P002")
```

---

## 4. Pharmaceutical Information Retrieval

### Adverse Drug Reaction (ADR) Database

```python
adr_database = {
    "paracetamol": ["Liver damage (overdose)", "Nausea", "Rash (rare)"],
    "amoxicillin": ["Diarrhea", "Nausea", "Allergic reaction", "Rash"],
    "metformin": ["GI upset", "Nausea", "Lactic acidosis (rare)", "B12 deficiency"],
    "atorvastatin": ["Muscle pain", "Liver enzyme increase", "GI issues"],
    "omeprazole": ["Headache", "Nausea", "Diarrhea", "Hypomagnesemia (long-term)"]
}

def get_adr(drug_name):
    adrs = adr_database.get(drug_name.lower())
    if adrs:
        print(f"\nAdverse Drug Reactions — {drug_name.capitalize()}:")
        for i, adr in enumerate(adrs, 1):
            print(f"  {i}. {adr}")
    else:
        print("Drug not found in ADR database.")

drug = input("Enter drug name to check ADRs: ")
get_adr(drug)
```

---

## 🧠 Key Takeaways

1. Healthcare databases link patients, drugs, prescriptions, and inventory
2. Python dictionaries + CSV files simulate database operations effectively
3. Search and retrieval functions are core to pharmacy information systems
4. ADR databases are critical safety tools for pharmacists

---

## 💻 Unit III Final Exercise

Build a **Mini Pharmacy Management System** that:
1. Maintains a drug database (at least 5 drugs)
2. Adds and retrieves patient records
3. Links prescriptions to patients
4. Checks if prescribed drug causes issues with known patient allergy
5. Saves patient records to a CSV file

This is your **Unit III capstone.**
