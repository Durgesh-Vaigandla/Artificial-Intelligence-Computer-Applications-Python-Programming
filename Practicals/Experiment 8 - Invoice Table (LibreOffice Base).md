# Experiment 8
## Create an Invoice Table

**Software Used:** LibreOffice Base — *replaces MS Access*

---

## 🎯 Objective

To design an `Invoices` table linked to the existing `Patients` table, capable of recording pharmacy billing transactions — establishing a relational link between patients and their purchases.

---

## 🧠 Why This Experiment Matters

Every pharmacy transaction — whether at a hospital pharmacy counter or a retail chemist — generates a bill. This experiment introduces **relational database design**: instead of repeating a patient's full details on every single bill, we link an `Invoices` table to the `Patients` table using a shared key (`PatientID`). This is the same principle every real pharmacy billing software uses.

---

## 🛠️ Step-by-Step Procedure

### Step 1: Open Your Existing Database
1. Open **LibreOffice Base**
2. Open `PatientDB.odb`

### Step 2: Create a New Table — Invoices
1. Click **Tables** in the left panel
2. Click **Create Table in Design View...**

### Step 3: Define the Invoice Fields

| Field Name | Field Type | Notes |
|------------|-----------|-------|
| InvoiceID | Integer | Primary Key, AutoValue = Yes |
| PatientID | Integer | Foreign Key — links to Patients table |
| InvoiceDate | Date | |
| DrugName | Text [VARCHAR] | Length 100 |
| Quantity | Integer | |
| UnitPrice | Decimal | Set Length=10, Decimal Places=2 |
| TotalAmount | Decimal | Set Length=10, Decimal Places=2 |
| PaymentMode | Text [VARCHAR] | Length 20 (Cash/Card/UPI/Insurance) |

Enter each field name and select its type from the dropdown, just as in Experiment 5.

> 💬 **What is a Foreign Key?** `PatientID` in this table is NOT the primary key here (that's `InvoiceID`) — but it refers back to the `PatientID` primary key in the `Patients` table. This is called a **Foreign Key**, and it's how two tables "know" which records belong together.

### Step 4: Set the Primary Key
1. Right-click the `InvoiceID` row
2. Select **Primary Key**
3. Set **AutoValue = Yes** in Field Properties (so invoice numbers generate automatically: 1, 2, 3...)

### Step 5: Save the Table
1. Press `Ctrl + S`
2. Name it: `Invoices`
3. Click **OK**

### Step 6: Establish the Relationship Between Tables
This is the most important step — it tells LibreOffice Base that `Invoices.PatientID` and `Patients.PatientID` are connected.

1. Close the table design window if open
2. From the top menu, go to **Tools → Relationships...**
3. A dialog appears: **Add Tables** — select both `Patients` and `Invoices`, click **Add**, then **Close**
4. You'll now see both tables represented as boxes with their field lists
5. Click and hold on `PatientID` in the `Patients` box, then **drag it onto** `PatientID` in the `Invoices` box
6. A line will connect the two fields, and a relationship dialog may appear — confirm the relationship type as **1:n (one-to-many)**, since one patient can have many invoices
7. Click **OK**, then close the Relationships window (it saves automatically, or press `Ctrl + S`)

### Step 7: Enter Sample Invoice Data
Double-click `Invoices` table to open Datasheet view, and enter sample records:

| InvoiceID | PatientID | InvoiceDate | DrugName | Quantity | UnitPrice | TotalAmount | PaymentMode |
|-----------|-----------|--------------|----------|----------|-----------|-------------|-------------|
| 1 | 1 | 2025-06-10 | Metformin 500mg | 60 | 2.50 | 150.00 | Cash |
| 2 | 1 | 2025-06-10 | Amlodipine 5mg | 30 | 3.00 | 90.00 | Cash |
| 3 | 2 | 2025-06-11 | Paracetamol 500mg | 10 | 1.20 | 12.00 | UPI |
| 4 | 3 | 2025-06-12 | Atorvastatin 10mg | 30 | 5.00 | 150.00 | Card |

> 💬 Notice how `PatientID = 1` appears twice — Rahul Sharma (PatientID 1) bought two different drugs in the same visit, recorded as two separate invoice line items. This is exactly how real pharmacy billing works.

### Step 8: Verify the Relationship Works
1. Try entering an invoice with `PatientID = 99` (a number that does NOT exist in the `Patients` table)
2. If **referential integrity** was enforced during relationship setup, LibreOffice Base should reject this entry with an error — because Patient 99 doesn't exist
3. This confirms your relationship is actively protecting data accuracy

### Step 9: Save Everything
1. Close the Datasheet view
2. Press `Ctrl + S` on the main Base window to ensure everything is saved

---

## ✅ Expected Output

A new `Invoices` table inside `PatientDB.odb`, properly linked to the `Patients` table via a one-to-many relationship on `PatientID`, populated with sample billing records.

---

## 📝 Viva/Record Questions

1. What is the difference between a Primary Key and a Foreign Key?
2. Why does the `Invoices` table need a `PatientID` field instead of repeating the patient's full name and address on every invoice?
3. What does "1:n relationship" mean in the context of Patients and Invoices?
4. What happens if you try to create an invoice for a PatientID that doesn't exist in the Patients table (assuming referential integrity is enforced)?

---

## 🔁 Practice Variation

Add a `DrugID` foreign key field to the `Invoices` table that links to a future `Drugs` table (to be built in Experiment 9) — this models how real pharmacy software links invoices to BOTH the patient AND the specific drug record, rather than just typing the drug name as plain text.
