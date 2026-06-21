# Experiment 10
## Creating and Working with Queries

**Software Used:** LibreOffice Base — *replaces MS Access*

---

## 🎯 Objective

To create and run SQL-based queries in LibreOffice Base that retrieve specific, filtered, and combined information from the `Patients`, `Invoices`, and `Drugs` tables built in previous experiments.

---

## 🧠 Why This Experiment Matters

Tables store data. **Queries** are how you ask meaningful questions of that data — "Which patients are diabetic?", "What is the total billing for each patient?", "Which drugs require a prescription?" Queries are the single most-used database feature in real pharmacy and hospital systems, powering every report, dashboard, and search box you'll ever encounter.

> 💬 **Key Difference from MS Access:** Access's query interface and SQL view work almost identically in LibreOffice Base. Both support a visual **Query Design** view (drag-and-drop) and a **SQL View** for typing direct SQL commands.

---

## 🛠️ Step-by-Step Procedure

### Step 1: Open Your Existing Database
1. Open **LibreOffice Base**
2. Open `PatientDB.odb` (with `Patients`, `Invoices`, and `Drugs` tables already created)

### Step 2: Create a Query Using the Wizard
1. Click **Queries** in the left panel
2. Click **Use Wizard to Create Query...**

### Step 3: Query 1 — Find All Patients Over Age 50
1. In Step 1 of the wizard, select table `Patients`
2. Add fields: `FullName`, `Age`, `ContactNumber`
3. Click **Next** through grouping/sorting screens (set Sort by `Age`, Descending if you like)
4. On the **Search Conditions** step, set:
   - Field: `Age`
   - Condition: `is greater than`
   - Value: `50`
5. Click **Next** → **Finish**
6. Name the query: `Patients_Over_50`

### Step 4: Run and View Query 1
1. Double-click `Patients_Over_50` in the Queries list
2. It runs automatically and shows only patients older than 50

### Step 5: Create Query 2 — Using SQL View Directly (More Powerful)
1. Click **Queries** → **Create Query in SQL View...**
2. Type the following SQL directly:

```sql
SELECT "FullName", "Allergies"
FROM "Patients"
WHERE "Allergies" <> 'None'
```

3. Click the **Run Query** button (▶ icon) to preview results
4. Save with `Ctrl + S`, name it: `Patients_With_Allergies`

> 💬 This query retrieves every patient who has a recorded allergy — instantly useful for a pharmacist double-checking before dispensing.

### Step 6: Create Query 3 — Join Patients and Invoices (Multi-Table Query)
This is the most important query type — combining data from two related tables.

1. **Queries → Create Query in SQL View...**
2. Type:

```sql
SELECT "Patients"."FullName", "Invoices"."DrugName", 
       "Invoices"."Quantity", "Invoices"."TotalAmount", 
       "Invoices"."InvoiceDate"
FROM "Patients"
INNER JOIN "Invoices" 
ON "Patients"."PatientID" = "Invoices"."PatientID"
ORDER BY "Invoices"."InvoiceDate"
```

3. Run the query — you should see patient names alongside their actual purchased drugs and amounts, even though this information lives in two separate tables
4. Save as: `Patient_Purchase_History`

> 💬 **This is the core concept of relational databases.** The `INNER JOIN` combines rows from `Patients` and `Invoices` wherever their `PatientID` matches — exactly like how a real pharmacy system shows a patient's full purchase history without duplicating their personal details in every invoice row.

### Step 7: Create Query 4 — Total Spending Per Patient (Aggregate Query)
1. **Queries → Create Query in SQL View...**
2. Type:

```sql
SELECT "Patients"."FullName", 
       SUM("Invoices"."TotalAmount") AS "TotalSpent"
FROM "Patients"
INNER JOIN "Invoices" 
ON "Patients"."PatientID" = "Invoices"."PatientID"
GROUP BY "Patients"."FullName"
ORDER BY "TotalSpent" DESC
```

3. Run the query — this shows each patient's name with their TOTAL spending across all invoices, sorted from highest to lowest
4. Save as: `Total_Spending_Per_Patient`

### Step 8: Create Query 5 — Drugs Requiring Prescription
1. **Queries → Create Query in SQL View...**
2. Type:

```sql
SELECT "DrugName", "Category", "MaxDailyDose"
FROM "Drugs"
WHERE "RequiresPrescription" = TRUE
ORDER BY "DrugName"
```

3. Run and save as: `Prescription_Required_Drugs`

### Step 9: Review All Saved Queries
1. Click **Queries** in the left panel
2. You should now see 5 saved queries:
   - `Patients_Over_50`
   - `Patients_With_Allergies`
   - `Patient_Purchase_History`
   - `Total_Spending_Per_Patient`
   - `Prescription_Required_Drugs`
3. Double-click any to re-run it — results always reflect the current, live data in your tables

---

## ✅ Expected Output

Five working, saved queries inside `PatientDB.odb`, demonstrating: simple filtering, text-based conditions, multi-table joins, aggregate (SUM) calculations, and Boolean filtering — covering the full spectrum of query types used in real healthcare database systems.

---

## 📝 Viva/Record Questions

1. What is the difference between a Query and a Table?
2. What does `INNER JOIN` do, and why was it necessary for `Patient_Purchase_History`?
3. What does the `SUM()` function do in Query 4, and why is `GROUP BY` required alongside it?
4. Why might a hospital pharmacist run "Prescription_Required_Drugs" as a regular check?

---

## 🔁 Practice Variation

Write a new SQL query that lists each patient's full name alongside the COUNT of invoices they have (i.e., how many times they've visited the pharmacy) — using `COUNT()` instead of `SUM()`.
