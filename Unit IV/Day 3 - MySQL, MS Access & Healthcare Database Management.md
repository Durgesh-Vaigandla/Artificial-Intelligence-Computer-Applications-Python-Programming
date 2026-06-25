# Unit IV – Day 3 (2 Hours)
## MySQL & MS Access — Complete Guide for Pharmacy Students

---

## 🎯 Session Goals
By the end of this session, you will be able to:
- Define what a database and a DBMS/RDBMS actually are, in your own words
- Explain the components of MySQL and the components of MS Access — a frequently asked exam question
- Understand tables, records, fields, keys, and relationships with healthcare examples
- Compare MySQL and MS Access knowledgeably, not just by a feature checklist
- Write and run SQL queries confidently, having understood the theory behind them first

> 📝 **Exam Relevance:** This session directly covers PYQ topics — *"What is a database? Explain about MySQL Components"* (2023), *"Explain major components of Microsoft Access"* (2023), *"What is database? Explain about MS Access database"* (2018), *"How to create a Database table in MS ACCESS"* (2020), and *"What is the importance of Drug Database system in MySQL?"* (2019).

---

## ⏱️ Session Plan (2 Hours)

| Time | Block | Topic |
|------|-------|-------|
| 0:00 – 0:10 | — | Recap of Day 1/2, session overview |
| 0:10 – 1:00 | **THEORY** | What is a database → DBMS/RDBMS → MySQL components → MS Access components → comparison |
| 1:00 – 1:45 | **PRACTICAL** | MS Access patient database, forms, reports + MySQL setup and tables |
| 1:45 – 1:55 | **QUERIES** | SQL queries — only after the theory and structures are in place |
| 1:55 – 2:00 | — | Recap + Q&A |

> 💬 **Why theory comes before queries:** Every PYQ paper from 2018–2023 asks *"what is a database"* and *"explain components"* before ever asking you to write a query. Examiners want to know you understand **what** you're querying and **why** it's structured that way — not just that you can copy a `SELECT` statement. Build the mental model first.

---
---
---

# 🅰️ PART A — THEORY

---

# SECTION 1 — What is a Database?

## 1.1 Definition

> A **database** is an organized collection of related data, stored electronically, structured in a way that allows it to be easily accessed, managed, retrieved, and updated.

Notice the key words: **organized**, **related**, **electronic**, **easily accessed**. A pile of patient files thrown in a cupboard is data — but it is NOT a database, because it isn't organized or easily searchable. A database imposes structure on data so a computer can work with it reliably.

## 1.2 The Pharmacy Analogy

Think about your pharmacy's physical drug shelf before any computer system existed:

| Physical Pharmacy Shelf | Database Equivalent |
|--------------------------|----------------------|
| Each drug has its own labelled box | Each **record** is one organized unit of data |
| Boxes are arranged alphabetically, by category | **Tables** organize related records together |
| Each box has a fixed set of labels: name, strength, batch, expiry | Each record has the same **fields** (columns) |
| The pharmacist's master list cross-references shelf location to drug name | A **key** uniquely links and looks up each item |

A database is simply the **digital version of this organizational system** — but searchable in milliseconds instead of by physically walking down the shelf.

## 1.3 Why Pharmacy and Healthcare Need Databases

- A single hospital may have **tens of thousands** of patient records — impossible to manage on paper
- Pharmacists need to **instantly cross-check** drug interactions, allergies, and dosing — a manual lookup would take too long in an emergency
- Records must be **updated constantly** — new prescriptions, new lab results, stock changes — without losing earlier history
- Multiple staff (doctors, pharmacists, nurses, billing) need to access the **same, consistent data** at the same time
- Regulatory bodies (CDSCO, NABH) require **traceable, auditable** records — a database can log exactly who changed what, and when

> 💬 "Every time a hospital prevents a wrong-dose error, finds a drug interaction in half a second, or tells you a drug batch is about to expire — there is a database working behind the scenes making that possible."

---

## 1.4 Core Database Terminology

This vocabulary recurs throughout every PYQ paper and every later section in this document — learn it precisely now.

| Term | Definition | Pharmacy Example |
|------|-------------|------------------|
| **Data** | Raw, individual facts | `"Rahul Sharma"`, `45`, `"B+"` |
| **Field (Column)** | One single category of information | `Name`, `Age`, `BloodGroup` |
| **Record (Row)** | One complete set of related field values — one whole entry | One patient's entire row: Rahul Sharma, 45, B+ |
| **Table** | A collection of records that share the same fields | The entire `Patients` table |
| **Primary Key** | A field that uniquely identifies every record — no two records can share it | `PatientID` |
| **Foreign Key** | A field in one table that refers to the Primary Key of another table, linking them | `PatientID` inside an `Invoices` table |
| **Schema** | The overall structure/blueprint of a database — what tables exist and how they relate | The complete design of `PharmacyDB` |
| **Query** | A request asking the database to retrieve, insert, update, or delete data | "Show me all diabetic patients" |

### Visualizing a Table

```
                    FIELDS (Columns)
              ┌──────────┬─────┬────────────┐
              │ FullName │ Age │ BloodGroup │
              ├──────────┼─────┼────────────┤
   RECORD 1 → │ Rahul S. │ 45  │     B+     │
   RECORD 2 → │ Priya N. │ 32  │     O+     │
   RECORD 3 → │ Suresh K.│ 60  │     A+     │
              └──────────┴─────┴────────────┘
                      ↑ This entire grid = ONE TABLE
```

---
---

# SECTION 2 — DBMS and RDBMS

## 2.1 What is a DBMS?

> A **Database Management System (DBMS)** is software that allows users to create, store, retrieve, update, and manage data in a database, without needing to know the technical details of how the data is physically stored.

Without a DBMS, you'd need to write custom low-level code every single time you wanted to save or search for data. The DBMS handles that complexity for you — you just ask for what you want using simple commands, and the DBMS figures out how to fetch it efficiently.

## 2.2 What is an RDBMS?

> A **Relational Database Management System (RDBMS)** is a type of DBMS that organizes data into **tables** (rows and columns), where tables can be **related** to one another through shared keys.

Both **MySQL** and **MS Access** are RDBMS software. "Relational" is the key word — it means the real strength of the system comes from linking multiple tables together (like linking `Patients` to `Invoices` via `PatientID`), rather than dumping everything into one giant, repetitive table.

### Why "Relational" Matters — A Concrete Example

**❌ Bad design (no relations, everything repeated):**

| InvoiceID | PatientName | PatientAge | BloodGroup | DrugName | Amount |
|-----------|-------------|------------|------------|----------|--------|
| 1 | Rahul Sharma | 45 | B+ | Metformin | 150 |
| 2 | Rahul Sharma | 45 | B+ | Amlodipine | 90 |

Notice "Rahul Sharma, 45, B+" is repeated. If Rahul's age changes, you must update it in *every single invoice row* — error-prone and wasteful.

**✅ Good relational design (linked via a key):**

`Patients` table:
| PatientID | FullName | Age | BloodGroup |
|-----------|----------|-----|------------|
| 1 | Rahul Sharma | 45 | B+ |

`Invoices` table:
| InvoiceID | PatientID | DrugName | Amount |
|-----------|-----------|----------|--------|
| 1 | 1 | Metformin | 150 |
| 2 | 1 | Amlodipine | 90 |

Now Rahul's personal details exist **exactly once**. Every invoice simply *points to* `PatientID = 1`. This is the relational principle, and it's the foundation of both MySQL and MS Access.

## 2.3 Other Examples of DBMS/RDBMS Software

| Software | Type | Common Use |
|----------|------|-------------|
| **MySQL** | RDBMS (server-based) | Web applications, hospital backend systems |
| **MS Access** | RDBMS (desktop) | Small clinics, learning, single-user apps |
| **Oracle Database** | RDBMS (enterprise) | Large hospital chains, government systems |
| **PostgreSQL** | RDBMS (server-based) | Advanced web/healthcare applications |
| **MongoDB** | NoSQL (non-relational) | Unstructured data — not table-based (outside this course's scope) |

---
---

# SECTION 3 — MySQL — Definition and Components

## 3.1 What is MySQL?

> **MySQL** is a free, open-source Relational Database Management System (RDBMS) that uses **Structured Query Language (SQL)** to manage and manipulate data. It runs as a **server**, meaning it can be accessed by many users and applications at the same time, over a network.

MySQL was created in 1995 and today powers an enormous share of the world's websites and backend systems — including, very often, the hospital and pharmacy software running behind the scenes of patient portals.

## 3.2 Why "Drug Database Systems in MySQL" Matter (PYQ Focus)

A **drug database system** built in MySQL is exactly what it sounds like — a structured, centralized, multi-user-accessible repository of drug information (names, categories, dosing, interactions, stock) that an entire hospital's software (pharmacy counter, doctor's prescription screen, billing system) can all query *simultaneously*, in real time, without conflicting with one another.

**Why MySQL specifically, and not just a spreadsheet, for this purpose:**

| Requirement | Why MySQL Satisfies It |
|--------------|------------------------|
| Many staff need access at once | MySQL is a multi-user **server** — handles many simultaneous connections |
| Data must stay consistent and accurate | MySQL enforces rules (constraints, keys) preventing duplicate/invalid entries |
| Must scale to thousands/millions of drug records | MySQL is built for large datasets with fast lookup (indexing) |
| Needs to integrate with hospital websites/apps | MySQL is the most common backend for PHP, Python, and Java-based hospital software |
| Data must be queryable instantly during an emergency | SQL queries return results in milliseconds, even on huge tables |
| Free for institutions with limited budgets | MySQL Community Edition is free and open-source |

> 💬 **Exam-ready one-line answer:** "A drug database system in MySQL provides a centralized, structured, multi-user, real-time-searchable repository of drug data — enabling fast interaction checking, accurate dispensing, and inventory control across an entire hospital, which a single-user tool like a spreadsheet cannot reliably support."

## 3.3 The Components of MySQL

This is a frequently repeated PYQ question — know each component by name and function, not just as a list.

```
┌─────────────────────────────────────────────────────┐
│                  MySQL ARCHITECTURE                 │
├─────────────────────────────────────────────────────┤
│  1. MySQL Server (mysqld)                           │
│     The core engine — stores data, processes queries│
├─────────────────────────────────────────────────────┤
│  2. Client Programs                                  │
│     mysql (CLI), MySQL Workbench (GUI)               │
├─────────────────────────────────────────────────────┤
│  3. Connector / Driver Libraries                     │
│     Let Python, PHP, Java programs talk to MySQL     │
├─────────────────────────────────────────────────────┤
│  4. Storage Engine (InnoDB, MyISAM)                  │
│     Decides HOW data is physically stored on disk    │
├─────────────────────────────────────────────────────┤
│  5. Databases → Tables → Records → Fields            │
│     The actual organized data, as covered in Sec 1   │
├─────────────────────────────────────────────────────┤
│  6. SQL (Structured Query Language)                  │
│     The command language used to interact with all   │
│     of the above                                      │
└─────────────────────────────────────────────────────┘
```

| Component | What It Does | Pharmacy Analogy |
|-----------|--------------|-------------------|
| **MySQL Server (mysqld)** | The background process that actually stores and manages all data, and listens for requests | The hospital's central record room and the staff who manage it |
| **Client / MySQL Workbench** | The application you use to type commands and see results | The counter/terminal where a pharmacist interacts with the system |
| **Connector/Driver** | Software libraries that let other programs (a Python app, a hospital website) talk to MySQL | The internal phone line connecting different hospital departments to the record room |
| **Storage Engine (e.g., InnoDB)** | Controls exactly how data is saved on the hard disk, and whether it supports features like relationships and transaction safety | The actual filing and shelving system used inside the record room |
| **Database** | A named collection of related tables (e.g., `PharmacyDB`) | One hospital's entire set of record cabinets |
| **Table** | A structured grid of records (e.g., `Patients`, `Drugs`) | One labelled cabinet drawer — e.g., "Patient Files" |
| **SQL** | The standardized language used to create, read, update, and delete data | The standard request forms every staff member fills out to get information from the record room |

> 💬 **Exam tip:** When asked "Explain about MySQL Components," structure your answer exactly like the table above — name each component, then one line on what it does. Examiners reward this structure heavily.

---
---

# SECTION 4 — MS Access — Definition and Components

## 4.1 What is MS Access?

> **Microsoft Access** is a desktop Relational Database Management System (RDBMS) from Microsoft, combining the relational database engine with a graphical user interface, allowing users to build databases, forms, queries, and reports **without writing extensive SQL code**.

Unlike MySQL — which is a *server* meant for many simultaneous users across a network — MS Access is primarily a **single-file, single/few-user desktop application**, well suited to smaller clinics or for learning database concepts visually before moving to a server-based system like MySQL.

## 4.2 The Components of MS Access

This is directly asked in PYQ 2023: *"Explain major components of Microsoft Access."* There are exactly **four core components** to name and explain.

```
┌─────────────────────────────────────────────────────┐
│                MS ACCESS COMPONENTS                  │
├─────────────────────────────────────────────────────┤
│  1. TABLES                                            │
│     Stores the actual raw data — rows and columns     │
├─────────────────────────────────────────────────────┤
│  2. QUERIES                                           │
│     Asks questions of the data; filters, sorts, joins │
├─────────────────────────────────────────────────────┤
│  3. FORMS                                             │
│     A user-friendly screen to view/add/edit records    │
├─────────────────────────────────────────────────────┤
│  4. REPORTS                                           │
│     A formatted, printable summary of the data         │
└─────────────────────────────────────────────────────┘
```

| Component | Purpose | Pharmacy Example |
|-----------|---------|-------------------|
| **Tables** | The foundation — stores all raw data in rows (records) and columns (fields) | A `Patients` table holding every patient's demographic data |
| **Queries** | Lets you ask a specific question of one or more tables, filtering, sorting, or calculating | "Show me every patient over 60 with a Penicillin allergy" |
| **Forms** | A clean, point-and-click data-entry screen — staff never touch the raw table directly | A receptionist's patient registration screen |
| **Reports** | A polished, print-ready, often grouped/summarized document generated from table or query data | A "Daily Patient Registration Report," grouped by gender, ready to print and file |

> 💬 **Exam tip:** A very reliable way to remember all four, in the order data flows through them: **Tables** hold the data → **Queries** ask questions of it → **Forms** let staff add/edit it → **Reports** present it on paper. That flow itself is worth stating in an answer.

### Two Additional, Less-Asked but Useful Components

| Component | Purpose |
|-----------|---------|
| **Macros** | Automate repeated actions (e.g., automatically open a specific form when the database opens) |
| **Modules** | VBA (Visual Basic for Applications) code for advanced custom logic — beyond what queries/macros can do |

---
---

# SECTION 5 — MySQL vs MS Access — A Proper Comparison

## 5.1 Full Comparison Table

| Feature | MySQL | MS Access |
|---------|-------|-----------|
| **Type** | Server-based RDBMS | Desktop-based RDBMS |
| **Best for** | Web apps, hospital backend systems, many simultaneous users | Small-scale, single-clinic, learning |
| **Interface** | Command line, or GUI tools like MySQL Workbench | Fully visual — drag-and-drop tables, forms, reports |
| **SQL Support** | Full, standard SQL | SQL available, but most work is done visually |
| **Multi-user access** | Excellent — designed for many concurrent users over a network | Poor — designed for one or a few users at a time |
| **Scalability** | Handles millions of records efficiently | Becomes slow/unstable beyond a few hundred thousand records |
| **Cost** | Free, open-source (Community Edition) | Paid — part of the Microsoft Office suite |
| **File storage** | Data lives on a server, managed by the MySQL service | Entire database is one `.accdb` file on a single computer |
| **Used in** | Hospital information systems, EHR backends, pharmacy chains | Small individual clinics, student projects, prototyping |

## 5.2 So Which Should You Actually Use?

> 💬 "MS Access is excellent for *learning* database concepts visually, and is genuinely still used in small clinics with one front-desk computer. MySQL is what you'll find running behind almost every real hospital management system, pharmacy chain backend, and patient portal at scale. In this course, we learn MS Access first because it makes the concepts of tables/forms/queries/reports visible and tangible — then we move to MySQL, which is what the industry actually runs on."

---
---
---

# 🅱️ PART B — PRACTICAL

> 💬 Now that the theory is solid — what a database is, what RDBMS means, and exactly what MySQL's and MS Access's components are — it's time to actually build. We'll build the same `Patients` and `Drugs` data in **both** tools, so you can directly feel the difference between visual (Access) and command-based (MySQL) database building.

---

## PRACTICAL 1 — MS Access: Create a Patient Database (Table Component)

**Goal:** Apply the "Tables" component from Section 4.2 hands-on.

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

3. Set `PatientID` as the Primary Key (right-click → Primary Key) — recall from Section 1.4 why this field must be unique
4. Save the table as `Patients`

---

## PRACTICAL 2 — MS Access: Build a Form (Forms Component)

**Goal:** Apply the "Forms" component — a clean screen so staff never touch the raw table.

1. Select the `Patients` table
2. Go to **Create → Form**
3. Access auto-generates a form
4. Use Form Design view to arrange fields neatly
5. Add a header: "PATIENT REGISTRATION FORM"
6. Add buttons for: Add New, Delete, Save

**The form allows:**
- ✅ View existing records
- ✅ Add new patients
- ✅ Delete records
- ✅ Edit/modify patient details

---

## PRACTICAL 3 — MS Access: Generate a Report (Reports Component)

**Goal:** Apply the "Reports" component — a polished, printable output.

1. Go to **Create → Report Wizard**
2. Select table: `Patients`
3. Select fields: `FullName`, `Age`, `BloodGroup`, `RegistrationDate`
4. Group by: `RegistrationDate`
5. Sort by: `FullName` (A to Z)
6. Layout: Tabular
7. Title: "Patient Registration Report"
8. Preview and Print

---

## PRACTICAL 4 — MS Access: Drug Information Storage

**Goal:** Build a second table, reinforcing relational design from Section 2.3.

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

## PRACTICAL 5 — MySQL: Installation and Server Components in Action

**Goal:** See the MySQL components from Section 3.3 (Server, Client, Database) directly in use.

```bash
# Install MySQL (if not installed)
# Download from: https://dev.mysql.com/downloads/

# Start the MySQL Client, connecting to the MySQL Server
mysql -u root -p
```

Notice: typing `mysql` launches the **Client**; it connects you to the running **Server (mysqld)**, which is the actual engine storing your data — exactly as described in Section 3.3.

```sql
-- Create a Database (a named collection of tables)
CREATE DATABASE PharmacyDB;
USE PharmacyDB;
```

---

## PRACTICAL 6 — MySQL: Create Tables (More Worked Examples)

**Goal:** Build the relational `Patients` and `Drugs` tables, observing keys directly.

```sql
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
```

> 💬 Notice `PatientID INT AUTO_INCREMENT PRIMARY KEY` — this single line does exactly what we discussed in Section 1.4 (Primary Key) and the relational design example in Section 2.2: it guarantees every patient has a unique, automatically-generated ID, ready to be referenced by other tables later (e.g., an `Invoices` table).

### Worked Example — Inserting Data

```sql
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

### Worked Example — Updating and Deleting (Frequently Skipped, but Essential)

```sql
-- UPDATE: correct a patient's age after a data-entry mistake
UPDATE Patients
SET Age = 46
WHERE FullName = 'Rahul Sharma';

-- DELETE: remove a discontinued drug record
DELETE FROM Drugs
WHERE BrandName = 'Crocin';
```

> 💬 **Why show UPDATE and DELETE before queries?** A database isn't just "read-only" — real pharmacy systems constantly correct records (a wrong age entered at registration) and remove outdated ones (a discontinued drug). Understanding that SQL has four core operations — **Create, Read, Update, Delete (CRUD)** — completes the picture before you move to "Read" operations (queries) in the next section.

---
---

# SECTION 6 — Queries

> 💬 Only now — having understood what a database is, what RDBMS means, what MySQL's and MS Access's components are, and having built and modified real tables — are we ready for queries. A query is simply the **"Read"** part of CRUD: asking the database a question and getting back exactly the data you need.

## 6.1 Queries in MS Access (Visual + SQL View)

**Creating a Query (Visual):**
1. Create → Query Design
2. Add the `Patients` table
3. Drag fields: `FullName`, `Age`, `BloodGroup`

**SQL View equivalent (Access generates this automatically):**
```sql
SELECT FullName, Age, BloodGroup
FROM Patients
WHERE Age > 50;
```

**More useful queries for pharmacy, in MS Access SQL syntax:**

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

## 6.2 Queries in MySQL

```sql
-- View all patients
SELECT * FROM Patients;

-- View prescription-only drugs
SELECT BrandName, GenericName FROM Drugs WHERE RequiresPrescription = TRUE;

-- Find patients over 50
SELECT FullName, Age FROM Patients WHERE Age > 50;

-- Count patients by blood group
SELECT BloodGroup, COUNT(*) AS Total FROM Patients GROUP BY BloodGroup;
```

## 6.3 Export to Web and XML (MS Access)

### Export to HTML
1. Right-click table/query → Export → HTML Document
2. Choose destination folder
3. Open the `.html` file in a browser — the table is auto-formatted

### Export to XML
1. Right-click table → Export → XML File
2. Export includes: data (`.xml`) + structure (`.xsd`)
3. XML can be shared with other healthcare systems

> 💬 "XML is how hospitals share patient data between different software systems. It's the language of healthcare data exchange — the HL7 standard, widely used internationally, is built on XML."

---

## 🧠 Complete Session Key Takeaways

1. **A database** is an organized, electronic collection of related data — structured for easy access, retrieval, and updating
2. **DBMS** manages databases for you; an **RDBMS** specifically organizes data into related tables — both MySQL and MS Access are RDBMS
3. **MySQL's components**: Server (mysqld), Client/Workbench, Connectors, Storage Engine, Databases/Tables, and SQL — know each one's role
4. **MS Access's components**: Tables → Queries → Forms → Reports, the natural flow of data from storage to presentation
5. **Relational design** avoids repeating data by linking tables through Primary Keys and Foreign Keys
6. **MySQL vs MS Access**: server-based/multi-user/free vs desktop-based/single-user/paid — choose based on scale
7. **CRUD** — Create, Read, Update, Delete — is the complete picture of what SQL does; queries are only the "Read" part
8. **A drug database system in MySQL** matters because it provides centralized, multi-user, real-time-searchable drug data at hospital scale — something a spreadsheet or single-user tool cannot support

---

## ❓ Q&A Discussion

- "In your own words, what is a database, and how is it different from just having data in a spreadsheet?"
- "Name and explain each of the four components of MS Access, in the order data flows through them."
- "Why does MySQL being a 'server-based' system matter for a hospital with many staff computers?"
- "Why is the `PatientID` field set as `AUTO_INCREMENT PRIMARY KEY` instead of letting staff type a patient ID manually?"

---

## 💻 Practice Exercises

**Exercise 1:** In MS Access, create a `Prescriptions` table linked to the `Patients` table via `PatientID`. Add 5 prescription records, explaining in one sentence why you used a Foreign Key rather than repeating patient details.

**Exercise 2:** Write SQL queries (MySQL syntax) to:
- Find all patients with allergies
- List drugs in alphabetical order
- Count how many drugs require prescription vs OTC

**Exercise 3:** Write one `UPDATE` query and one `DELETE` query for the `Drugs` table, and explain in one line each why a real pharmacy might need to run them.

**Exercise 4:** Export your `Patients` table to HTML and open it in a browser.
