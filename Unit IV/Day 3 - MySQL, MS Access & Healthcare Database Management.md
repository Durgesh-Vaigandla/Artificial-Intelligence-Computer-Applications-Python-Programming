# Unit IV – Day 2 (2 Hours)
## MySQL, MS Access & Healthcare Database Management

---

## 🎯 Session Goals
By the end of this session, students will be able to:
- Understand MySQL and MS Access for healthcare data management
- Create tables, insert records, and run queries
- Design a patient database and drug information system

---

## ⏱️ Session Plan (2 Hours)

| Time | Topic |
|------|-------|
| 0:00 – 0:10 | Recap Day 1 |
| 0:10 – 0:35 | Introduction to MySQL vs MS Access |
| 0:35 – 1:10 | MS Access — patient database practicals |
| 1:10 – 1:50 | MySQL basics + queries |
| 1:50 – 2:00 | Recap + Q&A |

---

## 1. MySQL vs MS Access

| Feature | MySQL | MS Access |
|---------|-------|-----------|
| Type | Server-based RDBMS | Desktop database |
| Best for | Web apps, hospital systems | Small-scale, local use |
| Interface | Command line / GUI tools | Visual (drag & drop) |
| SQL Support | Full SQL | Mostly SQL + visual query builder |
| Cost | Free (open source) | Part of MS Office |
| Used in | Hospital software, EHR systems | Clinic records, small pharmacies |

> 💬 "MS Access is great for learning database concepts. MySQL is what real hospitals and pharmacies use in production."

---

## 2. MS Access — Practical Guide

### Experiment 5: Create Patient Database

**Steps in MS Access:**

1. Open MS Access → New Blank Database → Name it `PatientDB.accdb`
2. Create a new Table in Design View

**PATIENTS Table — Field Design:**

| Field Name | Data Type | Properties |
|------------|-----------|------------|
| PatientID | AutoNumber | Primary Key |
| FullName | Short Text | Required |
| Age | Number | Integer |
| Gender | Short Text | Male/Female |
| BloodGroup | Short Text | A+/B+/O+ etc |
| ContactNumber | Short Text | |
| Address | Long Text | |
| Allergies | Long Text | |
| ChronicConditions | Long Text | |
| RegistrationDate | Date/Time | Default = Today() |

3. Set PatientID as Primary Key (right-click → Primary Key)
4. Save table as `Patients`

---

### Experiment 6: Design Form for Patient Records

**Steps:**
1. Select `Patients` table
2. Go to **Create → Form**
3. Access auto-generates a form
4. Use Form Design view to arrange fields neatly
5. Add header: "PATIENT REGISTRATION FORM"
6. Add buttons: Add New, Delete, Save

**The form allows:**
- ✅ View existing records
- ✅ Add new patients
- ✅ Delete records
- ✅ Edit/modify patient details

---

### Experiment 7: Generate Reports

1. Go to **Create → Report Wizard**
2. Select table: `Patients`
3. Select fields: FullName, Age, BloodGroup, RegistrationDate
4. Group by: RegistrationDate
5. Sort by: FullName (A to Z)
6. Layout: Tabular
7. Title: "Patient Registration Report"
8. Preview and Print

---

### Experiment 9: Drug Information Storage in MS Access

**DRUGS Table:**

| Field Name | Data Type |
|------------|-----------|
| DrugID | AutoNumber (PK) |
| BrandName | Short Text |
| GenericName | Short Text |
| Category | Short Text |
| Manufacturer | Short Text |
| DoseStrength | Number |
| Unit | Short Text |
| RouteOfAdmin | Short Text |
| Indications | Long Text |
| Contraindications | Long Text |
| SideEffects | Long Text |
| StorageCondition | Short Text |
| RequiresPrescription | Yes/No |

---

### Experiment 10: Queries in MS Access

**Creating a Query (Visual):**
1. Create → Query Design
2. Add `Patients` table
3. Drag fields: FullName, Age, BloodGroup

**SQL View equivalent:**
```sql
SELECT FullName, Age, BloodGroup
FROM Patients
WHERE Age > 50;
```

**Useful queries for pharmacy:**

```sql
-- Find all diabetic patients
SELECT FullName, Age, ContactNumber
FROM Patients
WHERE ChronicConditions LIKE "*Diabetes*";

-- Find drugs requiring prescription
SELECT BrandName, GenericName, Category
FROM Drugs
WHERE RequiresPrescription = Yes;

-- Find drugs expiring soon
SELECT BrandName, ExpiryDate
FROM Inventory
WHERE ExpiryDate < Date() + 30;
```

---

## 3. MySQL Basics

### Installation & Setup
```bash
# Install MySQL (if not installed)
# Download from: https://dev.mysql.com/downloads/

# Start MySQL in terminal
mysql -u root -p
```

### Create Healthcare Database

```sql
-- Create database
CREATE DATABASE PharmacyDB;
USE PharmacyDB;

-- Create patients table
CREATE TABLE Patients (
    PatientID INT AUTO_INCREMENT PRIMARY KEY,
    FullName VARCHAR(100) NOT NULL,
    Age INT,
    BloodGroup VARCHAR(5),
    Allergies TEXT,
    RegistrationDate DATE DEFAULT (CURDATE())
);

-- Create drugs table
CREATE TABLE Drugs (
    DrugID INT AUTO_INCREMENT PRIMARY KEY,
    BrandName VARCHAR(100),
    GenericName VARCHAR(100),
    Category VARCHAR(50),
    DoseStrength INT,
    RequiresPrescription BOOLEAN
);

-- Insert patients
INSERT INTO Patients (FullName, Age, BloodGroup, Allergies)
VALUES 
    ('Rahul Sharma', 45, 'B+', 'Penicillin'),
    ('Priya Nair', 32, 'O+', 'None'),
    ('Suresh Kumar', 60, 'A+', 'Sulfa drugs');

-- Insert drugs
INSERT INTO Drugs (BrandName, GenericName, Category, DoseStrength, RequiresPrescription)
VALUES
    ('Crocin', 'Paracetamol', 'Analgesic', 500, FALSE),
    ('Augmentin', 'Amoxicillin-Clavulanate', 'Antibiotic', 625, TRUE),
    ('Glucophage', 'Metformin', 'Antidiabetic', 500, TRUE);
```

### Queries

```sql
-- View all patients
SELECT * FROM Patients;

-- View prescription-only drugs
SELECT BrandName, GenericName FROM Drugs WHERE RequiresPrescription = TRUE;

-- Find patients over 50
SELECT FullName, Age FROM Patients WHERE Age > 50;

-- Count patients by blood group
SELECT BloodGroup, COUNT(*) as Total FROM Patients GROUP BY BloodGroup;
```

---

## 4. Experiments 11 & 12: Export to Web & XML

### Export to HTML (MS Access)
1. Right-click table/query → Export → HTML Document
2. Choose destination folder
3. Open the `.html` file in browser — table is auto-formatted

### Export to XML (MS Access)
1. Right-click table → Export → XML File
2. Export includes: data (`.xml`) + structure (`.xsd`)
3. XML can be shared with other healthcare systems

> 💬 "XML is how hospitals share patient data between different software systems. It's the language of healthcare data exchange (HL7 standard uses XML)."

---

## 🧠 Key Takeaways

1. MS Access = visual, beginner-friendly, good for learning and small clinics
2. MySQL = production-grade, used in real hospital systems
3. SQL queries are the universal language to retrieve healthcare data
4. Export to HTML/XML enables data sharing across systems

---

## 💻 Practice Exercises

**Exercise 1:** In MS Access, create a `Prescriptions` table linked to the `Patients` table. Add 5 prescription records.

**Exercise 2:** Write SQL queries to:
- Find all patients with allergies
- List drugs in alphabetical order
- Count how many drugs require prescription vs OTC

**Exercise 3:** Export your Patients table to HTML and open it in a browser.
