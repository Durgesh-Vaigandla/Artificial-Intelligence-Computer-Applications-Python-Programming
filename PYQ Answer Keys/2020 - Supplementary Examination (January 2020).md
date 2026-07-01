# B.Pharmacy II Semester (PCI) — Computer Applications in Pharmacy
# 2020 — Supplementary Examination (January 2020)
## Answer Key

---

> **Instructions reflected in this key:** PART–A — **10 Marks each**. PART–B — **5 Marks each**.

---

# PART – A  (10 Marks Each)

---

## Q1. What is number system? Write Decimal to Binary conversion and Octal to Binary conversion. [10 Marks]

### 1. Definition (1.5 Marks)
A **number system** is a systematic method of representing numbers using a defined set of symbols and positional rules. Computers use the **Binary** system internally; **Decimal** and **Octal** are alternate systems converted to/from binary for human convenience and compact representation respectively.

### 2. Decimal to Binary Conversion (4 Marks)

**Method:** Repeatedly divide the decimal number by 2, recording the remainder at each step, until the quotient becomes 0. Read remainders from bottom to top.

**Worked Example 1:** Convert `13` (decimal) to binary.
```
13 ÷ 2 = 6   remainder 1
 6 ÷ 2 = 3   remainder 0
 3 ÷ 2 = 1   remainder 1
 1 ÷ 2 = 0   remainder 1

Reading bottom→top: 1101
∴ 13 (decimal) = 1101 (binary)
```

**Worked Example 2:** Convert `37` (decimal) to binary.
```
37 ÷ 2 = 18  remainder 1
18 ÷ 2 = 9   remainder 0
 9 ÷ 2 = 4   remainder 1
 4 ÷ 2 = 2   remainder 0
 2 ÷ 2 = 1   remainder 0
 1 ÷ 2 = 0   remainder 1

Reading bottom→top: 100101
∴ 37 (decimal) = 100101 (binary)
```

### 3. Octal to Binary Conversion (4 Marks)

**Method:** Convert each octal digit individually into its 3-bit binary equivalent, then combine.

**Reference Table — Octal Digit to 3-Bit Binary:**

| Octal | Binary |
|-------|--------|
| 0 | 000 |
| 1 | 001 |
| 2 | 010 |
| 3 | 011 |
| 4 | 100 |
| 5 | 101 |
| 6 | 110 |
| 7 | 111 |

**Worked Example 1:** Convert `56` (octal) to binary.
```
5 = 101
6 = 110
∴ 56 (octal) = 101110 (binary)
```

**Worked Example 2:** Convert `372` (octal) to binary.
```
3 = 011
7 = 111
2 = 010
∴ 372 (octal) = 011111010 (binary)
```

### 4. Conclusion (0.5 Mark)
These conversions illustrate the relationship between human-friendly representations (decimal, octal) and the binary form that all computer hardware — including pharmacy management systems — actually processes internally.

---

## Q2. *(i) Discuss briefly about the applications of computers in drug designing and validation. (ii) Explain the application of computers in hospital and clinical pharmacy.* [10 Marks Total — 5 Marks Each]

### (i) Applications of Computers in Drug Designing and Validation [5 Marks]

**Definition:** **Computer-Aided Drug Design (CADD)** uses computational tools and software to identify, design, and optimize new drug candidates, while **validation** refers to computer-assisted verification that a drug/process meets required quality standards.

**Applications:**

| Application | Description |
|-------------|--------------|
| **Molecular Modelling** | Software visualizes 3D structures of drug molecules and target proteins |
| **Virtual Screening** | Computers rapidly evaluate millions of chemical compounds for activity against a target |
| **Structure-Based Drug Design** | Uses protein structure data (e.g., from AlphaFold) to design molecules that fit precisely |
| **QSAR Analysis** | Quantitative Structure-Activity Relationship software predicts biological activity from molecular structure |
| **Process Validation Software** | Statistically validates that manufacturing processes consistently produce quality drugs |

**Importance:** Drastically reduces time and cost of drug discovery — traditional methods take 10–15 years; computer-aided methods can shorten this significantly by eliminating unlikely candidates early.

---

### (ii) Applications of Computers in Hospital and Clinical Pharmacy [5 Marks]

**Definition:** Computer applications in hospital and clinical pharmacy refer to the use of software systems to support medication management, patient care, and pharmacy operations within a hospital setting.

**Applications:**

| Domain | Application |
|--------|-------------|
| **Prescription Management** | Electronic prescribing, automatic interaction/allergy checking |
| **Dispensing** | Automated dispensing cabinets, barcode verification |
| **Patient Records** | Electronic Health Records (EHR) for complete medication history |
| **Clinical Decision Support** | CDSS alerts for dosing errors, contraindications |
| **Inventory Management** | Real-time stock tracking, expiry alerts |
| **Billing** | Automated invoicing and insurance claims |

**Conclusion:** These applications collectively improve patient safety, reduce medication errors, and streamline pharmacy workflows within hospitals.

---

## Q3. *(i) Write a note on web server and server products. (ii) Write about various databases.* [10 Marks Total — 5 Marks Each]

### (i) Web Server and Server Products [5 Marks]

**Definition:** A **Web Server** is software (and hardware) that stores, processes, and delivers web pages to users upon request, using HTTP/HTTPS protocol.

**How it works:**
```
Browser sends HTTP Request → Web Server processes & fetches data → sends HTTP Response → Browser displays page
```

**Common Server Products:**

| Server Product | Notes |
|------------------|-------|
| **Apache HTTP Server** | Free, open-source |
| **Nginx** | High-speed, high-traffic handling |
| **Microsoft IIS** | Used with Windows Server |
| **Tomcat** | For Java-based web applications |

**Relevance:** Hospital portals and drug databases are hosted on such servers.

---

### (ii) Various Databases [5 Marks]

**Definition:** A **database** is an organized collection of related data, stored electronically, allowing easy access, management, and retrieval.

**Types of Databases Relevant to Pharmacy/Healthcare:**

| Type | Example | Use |
|------|---------|-----|
| **Relational Database (RDBMS)** | MySQL, MS Access | Patient records, drug inventories — data in related tables |
| **Bioinformatics Database** | GenBank, PDB | Genomic/protein data for drug research |
| **Drug Information Database** | MIMS, Micromedex | Clinical drug reference |
| **Literature Database** | PubMed | Research articles |
| **Laboratory Database (via LIMS)** | Lab-specific systems | Test sample and result tracking |

**Conclusion:** Different database types serve different healthcare needs — from day-to-day patient records (RDBMS) to specialized scientific research (bioinformatics databases).

---
---

# PART – B  (5 Marks Each)

---

## Q4. Define HTML and XML. Differentiate between HTML and XML. [5 Marks]

**HTML:** HyperText Markup Language — a markup language used to create the **structure and display** of web pages using a fixed set of predefined tags.

**XML:** eXtensible Markup Language — a markup language designed to **store and transport data** in a structured, self-describing format using user-defined tags.

**Differences:**

| Feature | HTML | XML |
|---------|------|-----|
| Purpose | Display data | Store/transport data |
| Tags | Fixed, predefined | User-defined |
| Case sensitivity | Not case sensitive | Case sensitive |
| Closing tags | Some optional | All mandatory |
| Validation strictness | Browser-forgiving | Strict — must be well-formed |

---

## Q5. Explain the project process life cycle. [5 Marks]

**Definition:** The **Project Process Life Cycle** describes the sequential phases a project passes through, from initial concept to completion.

**Phases:**

| Phase | Description |
|-------|--------------|
| 1. **Initiation** | Define objective, feasibility, scope |
| 2. **Planning** | Define tasks, timeline, resources, budget |
| 3. **Execution** | Implement the planned tasks |
| 4. **Monitoring & Control** | Track progress, manage risks/changes |
| 5. **Closure** | Final delivery, documentation, review |

**Example:** Implementing a new Pharmacy Information System in a hospital would follow exactly this five-phase cycle.

---

## Q6. Explain drug information storage and retrieval system. [5 Marks]

**Definition:** A system for systematically recording comprehensive drug data and enabling fast search/retrieval of that information when needed.

**Storage includes:** Drug name, category, dose, indications, contraindications, side effects, storage conditions.

**Retrieval Process:**
```
User searches drug name → system retrieves monograph from database
        → displays dosing, interactions, warnings
```

**Importance:** Enables pharmacists to instantly access accurate, complete drug information at the point of dispensing, improving patient safety.

---

## Q7. What are the importances of clinical studies? [5 Marks]

**Definition:** Clinical studies are research investigations on human participants evaluating drug safety, efficacy, and dosing.

**Importance:**
1. Establishes safety and efficacy before public release
2. Identifies correct dosage and side effects
3. Provides evidence for regulatory approval
4. Detects rare adverse effects in larger populations
5. Supports evidence-based clinical practice

---

## Q8. Write a short note on Bioinformatics Databases. [5 Marks]

**Definition:** Bioinformatics databases are structured electronic repositories of biological data (sequences, structures, pathways) used in computational biology.

**Examples:**

| Database | Stores |
|----------|--------|
| GenBank | DNA/RNA sequences |
| PDB | Protein 3D structures |
| KEGG | Metabolic pathways |
| DrugBank | Drug-target interaction data |

**Importance:** Support drug target identification and rational drug design.

---

## Q9. Explain laboratory information management system. [5 Marks]

**Definition:** A **LIMS** manages, tracks, and automates laboratory workflow from sample registration to result reporting.

**Workflow:**
```
Sample registered with barcode → routed to test department
        → analyser generates result → validated → report generated → sent to EHR
```

**Advantages:** Eliminates manual transcription errors, prevents sample mix-ups, provides full audit trail.

---

## Q10. How to create a Database table in MS ACCESS. [5 Marks]

**Steps:**
1. Open MS Access → New Blank Database
2. Go to **Create → Table** (or Table Design for full control)
3. In Design View, enter Field Names and select Field Types (Short Text, Number, Date/Time, etc.)
4. Right-click the chosen field (e.g., PatientID) → set as **Primary Key**
5. Save the table with an appropriate name (e.g., `Patients`)
6. Switch to Datasheet View to begin entering records

**Example Field Design:**

| Field Name | Data Type |
|------------|-----------|
| PatientID | AutoNumber (PK) |
| FullName | Short Text |
| Age | Number |

---

## Q11. Write a note on TIMS (Text Information Management System). [5 Marks]

**Definition:** TIMS stores, organizes, searches, and retrieves large volumes of unstructured textual data such as clinical notes and drug literature.

**Workflow:**
```
Documents indexed → user submits query → TIMS retrieves & ranks results → user extracts information
```

**Example:** PubMed acts as a large-scale TIMS for biomedical literature search.

---

**— End of 2020 Supplementary Examination Answer Key —**
