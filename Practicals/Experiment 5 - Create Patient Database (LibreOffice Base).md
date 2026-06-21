# Experiment 5
## Create a Database to Store Patient Information with Required Fields

**Software Used:** LibreOffice Base — *replaces MS Access*

---

## 🎯 Objective

To create a new database in LibreOffice Base and design a `Patients` table with appropriate fields, data types, and a primary key — establishing the foundation for all later patient-record experiments.

---

## 🧠 Why This Experiment Matters

Every hospital and pharmacy management system is built on a database storing patient records. Understanding how to design a table — choosing the right field names, data types, and a primary key — is the single most foundational database skill for healthcare IT.

> 💬 **Key Difference from MS Access:** MS Access saves databases as `.accdb` files. **LibreOffice Base** saves them as `.odb` files. The table design view, data types, and overall workflow are conceptually identical — only some menu names and dialog layouts differ slightly.

---

## 🛠️ Step-by-Step Procedure

### Step 1: Open LibreOffice Base
1. Open **LibreOffice Start Center**
2. Click **Database**
3. The **Database Wizard** opens

### Step 2: Create a New Database
1. Select **Create a new database**
2. Click **Next**
3. Under "What do you want to do after saving the database?" — leave default options (Register database, Open for editing)
4. Click **Finish**

### Step 3: Save the Database File
1. In the save dialog, name it: `PatientDB`
2. Choose your save location (e.g., your `Practicals` folder)
3. Click **Save** — this creates `PatientDB.odb`

### Step 4: Create a New Table in Design View
1. In the Base main window, on the left panel, click **Tables**
2. Click **Create Table in Design View...**
3. The Table Design window opens with columns: **Field Name | Field Type | Description**

### Step 5: Define the Fields

Enter the following fields one by one:

| Field Name | Field Type | Notes |
|------------|-----------|-------|
| PatientID | Integer | Set as Primary Key (see Step 6) |
| FullName | Text [VARCHAR] | Length 100 |
| Age | Integer | |
| Gender | Text [VARCHAR] | Length 10 |
| BloodGroup | Text [VARCHAR] | Length 5 |
| ContactNumber | Text [VARCHAR] | Length 15 |
| Address | Text [VARCHAR] | Length 250 |
| Allergies | Text [VARCHAR] | Length 250 |
| ChronicConditions | Text [VARCHAR] | Length 250 |
| RegistrationDate | Date | |

For each row:
1. Type the **Field Name** in the first column
2. Click the second column → a dropdown arrow appears → select the **Field Type** (Integer, Text [VARCHAR], Date, etc.)
3. In the bottom panel ("Field Properties"), set **Length** for text fields (e.g., 100 for names)

### Step 6: Set the Primary Key
1. Right-click on the row for `PatientID`
2. Select **Primary Key** from the context menu
3. A small key icon appears next to `PatientID`, confirming it is now the unique identifier for every record

> 💬 **Why PatientID as Primary Key?** Names can repeat (two patients could both be named "Ramesh Kumar"), but PatientID must be unique to every individual — this guarantees no record is ever confused with another.

### Step 7: Set Auto-Increment for PatientID (Optional but Recommended)
1. Click on the `PatientID` field row
2. In Field Properties (bottom panel), find **AutoValue**
3. Set it to **Yes**
4. This means LibreOffice Base will automatically assign 1, 2, 3... to each new patient — no manual entry needed

### Step 8: Save the Table
1. Press `Ctrl + S`
2. When prompted for a table name, type: `Patients`
3. Click **OK**

### Step 9: View and Test the Table
1. Double-click the `Patients` table in the left panel to open it in Datasheet View
2. Manually enter 3–4 sample patient records to test:

| PatientID | FullName | Age | Gender | BloodGroup | ContactNumber | Allergies |
|-----------|----------|-----|--------|------------|---------------|-----------|
| 1 | Rahul Sharma | 45 | Male | B+ | 9876543210 | Penicillin |
| 2 | Priya Nair | 32 | Female | O+ | 9876501234 | None |
| 3 | Suresh Kumar | 60 | Male | A+ | 9876512345 | Sulfa drugs |

3. Close the Datasheet view — data is saved automatically as you type, but press `Ctrl + S` to be safe

### Step 10: Confirm the Database Structure
1. In the main Base window, click on **Tables** in the left panel
2. You should see `Patients` listed
3. Right-click → **Edit** to review your field design anytime

---

## ✅ Expected Output

A saved `PatientDB.odb` file containing one table named `Patients`, with 10 well-defined fields, a Primary Key on `PatientID`, and at least 3 sample patient records entered and saved.

---

## 📝 Viva/Record Questions

1. What is a Primary Key, and why must every table have one?
2. Why was `PatientID` chosen as Integer and `FullName` chosen as Text?
3. What does AutoValue do, and why is it useful for ID fields?
4. What file extension does LibreOffice Base use, and how does it differ from MS Access?

---

## 🔁 Practice Variation

Add two more fields to your table: `EmergencyContactName` and `EmergencyContactNumber`. Re-save the table structure and add this data for your existing sample patients.
