# Experiment 9
## Drug Information Storage and Retrieval

**Software Used:** LibreOffice Base — *replaces MS Access*

---

## 🎯 Objective

To create a `Drugs` table for storing comprehensive drug information, and to retrieve specific drug details using LibreOffice Base's search and filter tools.

---

## 🧠 Why This Experiment Matters

Beyond patient records, every pharmacy needs a structured **drug master database** — the single source of truth for every medicine's name, category, strength, prescription requirement, and storage condition. This experiment builds that database and teaches you to retrieve information from it quickly, just as a pharmacist would look up a drug at the counter.

---

## 🛠️ Step-by-Step Procedure

### Step 1: Open Your Existing Database
1. Open **LibreOffice Base**
2. Open `PatientDB.odb`

### Step 2: Create the Drugs Table
1. Click **Tables** → **Create Table in Design View...**

### Step 3: Define the Drug Fields

| Field Name | Field Type | Notes |
|------------|-----------|-------|
| DrugID | Integer | Primary Key, AutoValue = Yes |
| DrugName | Text [VARCHAR] | Length 100 |
| GenericName | Text [VARCHAR] | Length 100 |
| Category | Text [VARCHAR] | Length 50 |
| DoseStrength | Integer | |
| Unit | Text [VARCHAR] | Length 10 (mg, mcg, mL) |
| RequiresPrescription | Yes/No (Boolean) | |
| MaxDailyDose | Integer | |
| StorageCondition | Text [VARCHAR] | Length 100 |
| Manufacturer | Text [VARCHAR] | Length 100 |

### Step 4: Set the Primary Key
1. Right-click `DrugID` → **Primary Key**
2. Set **AutoValue = Yes**

### Step 5: Save the Table
1. `Ctrl + S` → name it `Drugs` → **OK**

### Step 6: Enter Sample Drug Records
Double-click `Drugs` to open Datasheet view, and enter:

| DrugID | DrugName | GenericName | Category | DoseStrength | Unit | RequiresPrescription | MaxDailyDose | StorageCondition |
|--------|----------|--------------|----------|---------------|------|----------------------|---------------|-------------------|
| 1 | Crocin | Paracetamol | Analgesic | 500 | mg | No | 4000 | Store below 25°C |
| 2 | Augmentin | Amoxicillin-Clavulanate | Antibiotic | 625 | mg | Yes | 1875 | Store below 25°C, protect from moisture |
| 3 | Glycomet | Metformin | Antidiabetic | 500 | mg | Yes | 2000 | Store below 30°C |
| 4 | Atorva | Atorvastatin | Statin | 10 | mg | Yes | 80 | Store below 25°C |
| 5 | Omez | Omeprazole | PPI | 20 | mg | No | 40 | Store below 25°C, protect from light |

> 💬 For the `RequiresPrescription` Yes/No field, LibreOffice Base typically shows a checkbox in Datasheet view — simply check or uncheck it per row.

### Step 7: Retrieve a Single Drug — Using Find & Replace
1. With the `Drugs` table open in Datasheet view, press `Ctrl + F`
2. Type `Metformin` in the search box
3. Click **Find Next**
4. LibreOffice Base highlights/jumps to the matching record

### Step 8: Retrieve Drugs Matching a Condition — Using AutoFilter
1. Click on the `Category` column header
2. Go to **Data → AutoFilter** (or use the small filter dropdown icon if visible on the column header)
3. Select a specific value, e.g., filter to show only `Antibiotic` category drugs
4. The Datasheet now displays only matching rows
5. To remove the filter: **Data → Reset Filter/Sort**

### Step 9: Retrieve Using Standard Filter (More Powerful)
1. Go to **Data → Standard Filter...**
2. Set condition: `RequiresPrescription` = `Yes`
3. Click **OK**
4. This shows only prescription-required drugs — useful for compliance checks

### Step 10: Sort Drug Records Alphabetically
1. Click on the `DrugName` column header
2. Go to **Data → Sort...**
3. Choose `DrugName`, Ascending
4. Click **OK** — your drug list is now alphabetically organized for easy browsing

---

## ✅ Expected Output

A populated `Drugs` table with at least 5 complete drug records, demonstrating successful information retrieval through Find, AutoFilter, and Standard Filter techniques.

---

## 📝 Viva/Record Questions

1. Why is a separate `Drugs` table necessary instead of just writing drug names directly into the `Invoices` table?
2. What is the difference between AutoFilter and Standard Filter?
3. Why does the `RequiresPrescription` field use a Yes/No (Boolean) type instead of Text?
4. How would a real pharmacy use the "filter by Category" feature in daily operations?

---

## 🔁 Practice Variation

Use Standard Filter to retrieve all drugs with `MaxDailyDose` greater than 1000mg — a useful safety check to quickly identify high-dose medications in your formulary.
