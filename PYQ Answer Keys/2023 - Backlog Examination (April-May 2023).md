# B.Pharmacy II Semester (PCI) — Computer Applications in Pharmacy
# 2023 — Backlog Examination (April/May 2023)
## Answer Key

---

> **Instructions reflected in this key:** PART–A — **10 Marks each** (Q2 and Q3 are split into two 5-mark sub-parts). PART–B — **5 Marks each**.

---

# PART – A  (10 Marks Each)

---

## Q1. Define number system. Explain the conversion process from binary to decimal and hexadecimal to binary. [10 Marks]

### 1. Definition (2 Marks)
A **number system** is a systematic method of representing numbers using a defined set of symbols (digits) and positional rules. Computers operate internally using **Binary** (base-2); **Decimal** is used for human interaction, and **Hexadecimal** is used as a compact representation of binary in technical contexts.

### 2. Binary to Decimal Conversion (4 Marks)

**Method:** Multiply each binary digit by 2 raised to its positional power (right to left, starting at 0), then sum the results.

**Worked Example 1:** Convert `1010` (binary) to decimal.
```
1010 = (1×2³) + (0×2²) + (1×2¹) + (0×2⁰) = 8+0+2+0 = 10 (decimal)
```

**Worked Example 2:** Convert `111001` (binary) to decimal.
```
111001 = (1×2⁵) + (1×2⁴) + (1×2³) + (0×2²) + (0×2¹) + (1×2⁰)
       = 32 + 16 + 8 + 0 + 0 + 1
       = 57 (decimal)
```

### 3. Hexadecimal to Binary Conversion (4 Marks)

**Method:** Convert each hexadecimal digit individually into its 4-bit binary equivalent, then combine.

**Reference Table:**

| Hex | Binary (4-bit) |
|-----|----------------|
| 0–7 | 0000–0111 |
| 8 | 1000 |
| 9 | 1001 |
| A | 1010 |
| B | 1011 |
| C | 1100 |
| D | 1101 |
| E | 1110 |
| F | 1111 |

**Worked Example 1:** Convert `F2` (hexadecimal) to binary.
```
F = 1111
2 = 0010
∴ F2 = 11110010 (binary)
```

**Worked Example 2:** Convert `2C5` (hexadecimal) to binary.
```
2 = 0010
C = 1100
5 = 0101
∴ 2C5 = 001011000101 (binary)
```

### 4. Conclusion
Binary-decimal conversion connects machine-level data to human-readable numbers; hexadecimal-binary conversion via 4-bit grouping is a fast, calculation-free shorthand widely used in programming and system memory addressing.

---

## Q2. *(i) Explain major components of Microsoft Access. (ii) Explain the application of computers in hospital and clinical pharmacy.* [10 Marks Total — 5 Marks Each]

### (i) Major Components of Microsoft Access [5 Marks]

**Definition:** **Microsoft Access** is a desktop Relational Database Management System (RDBMS) combining a database engine with a graphical interface for building databases without extensive coding.

**Four Major Components:**

```
TABLES  →  QUERIES  →  FORMS  →  REPORTS
(store data)  (ask questions)  (data entry)  (printed output)
```

| Component | Function | Example |
|-----------|----------|---------|
| **Tables** | Store the actual raw data in rows (records) and columns (fields) | `Patients` table with PatientID, Name, Age |
| **Queries** | Retrieve specific data from tables based on conditions; filter, sort, calculate | "Show all patients over 60" |
| **Forms** | Provide a user-friendly, point-and-click interface for data entry — staff never touch raw tables | A patient registration screen |
| **Reports** | Present table/query data in a formatted, printable, often-grouped layout | "Daily Patient Registration Report" |

**Additional minor components:** Macros (automate repeated actions), Modules (VBA code for advanced logic).

---

### (ii) Application of Computers in Hospital and Clinical Pharmacy [5 Marks]

**Applications:**

| Domain | Application |
|--------|--------------|
| **Prescription Management** | E-prescribing, automatic interaction/allergy checking |
| **Dispensing** | Automated dispensing cabinets, barcode verification |
| **Patient Records** | EHR for complete medication history |
| **Clinical Decision Support** | CDSS alerts for dosing errors |
| **Inventory** | Real-time stock tracking, expiry alerts |
| **Billing** | Automated invoicing and insurance claims |

**Conclusion:** These applications collectively improve patient safety and pharmacy workflow efficiency in hospital settings.

---

## Q3. *(i) Explain different types of Databases in Bioinformatics. (ii) Write note on CDS (Chromatographic data systems).* [10 Marks Total — 5 Marks Each]

### (i) Different Types of Databases in Bioinformatics [5 Marks]

**Definition:** Bioinformatics databases are structured electronic repositories of biological data used in computational biology and drug research.

**Types:**

| Type | Example | Stores |
|------|---------|--------|
| **Sequence Database** | GenBank, EMBL | DNA/RNA sequences |
| **Protein Structure Database** | PDB (Protein Data Bank) | 3D protein structures |
| **Literature Database** | PubMed | Biomedical research articles |
| **Pathway Database** | KEGG | Metabolic/signalling pathways |
| **Drug-Target Database** | DrugBank | Drug-target interaction data |

**Importance:** Support drug target identification, structure-based drug design, and disease mechanism research.

---

### (ii) CDS (Chromatographic Data Systems) [5 Marks]

**Definition:** Software used to collect, process, and store data from chromatographic instruments (HPLC, GC) for pharmaceutical quality testing.

**Workflow:**
```
Sample injected → instrument separates components → CDS captures chromatogram
        → identifies peaks/retention time/area → generates validated report
```

**Key Functions:** Peak integration, calibration against standards, audit trail (GxP compliance).

**Importance:** Verifies drug purity and batch-to-batch quality consistency.

---
---

# PART – B  (5 Marks Each)

---

## Q4. Explain the process for binary addition and binary subtraction. [5 Marks]

**Binary Addition Rules:**

| A | B | Sum | Carry |
|---|---|-----|-------|
| 0 | 0 | 0 | 0 |
| 0 | 1 | 1 | 0 |
| 1 | 0 | 1 | 0 |
| 1 | 1 | 0 | 1 |

**Worked Example:** Add `1011 + 0110`
```
  1011
+ 0110
------
 10001
```

**Binary Subtraction Rules:**

| A | B | Difference | Borrow |
|---|---|------------|--------|
| 0 | 0 | 0 | 0 |
| 1 | 0 | 1 | 0 |
| 1 | 1 | 0 | 0 |
| 0 | 1 | 1 | 1 (borrow) |

**Worked Example:** Subtract `1010 − 0011`
```
  1010
- 0011
------
  0111
```

**Importance:** Forms the basis of all arithmetic operations performed by computer processors, including pharmacy dosage calculation software.

---

## Q5. Write about syntax rules for Extensible Markup Language declaration. [5 Marks]

**Syntax Rules of XML:**
1. Every opening tag must have a matching closing tag
2. Tags must be properly nested (no overlapping)
3. XML tags are case-sensitive
4. Attribute values must always be quoted
5. There must be exactly one root element
6. Special characters must be escaped (`&lt;`, `&gt;`, `&amp;`)

**XML Declaration Example:**
```xml
<?xml version="1.0" encoding="UTF-8"?>
<drug>
    <name>Metformin</name>
    <dose unit="mg">500</dose>
</drug>
```

The declaration line, if used, must always be the very first line of the document.

---

## Q6. What is a database? Explain about MySQL Components. [5 Marks]

**Database:** An organized collection of related data, stored electronically, allowing easy access, management, and retrieval.

**MySQL Components:**

| Component | Function |
|-----------|----------|
| **MySQL Server (mysqld)** | Core engine — stores data, processes queries |
| **Client / MySQL Workbench** | Application used to type commands and view results |
| **Connector/Driver** | Lets other programs (Python, PHP) communicate with MySQL |
| **Storage Engine (InnoDB)** | Controls how data is physically stored on disk |
| **Database → Table → Record → Field** | The organized data hierarchy |
| **SQL** | The command language used to interact with all the above |

**Importance:** A MySQL-based drug database enables fast, multi-user, real-time access to drug data across an entire hospital.

---

## Q7. Write a note on web server and server products. [5 Marks]

**Definition:** Software (and hardware) that stores, processes, and delivers web pages upon request via HTTP/HTTPS.

**Common Server Products:**

| Server | Notes |
|--------|-------|
| Apache HTTP Server | Free, open-source |
| Nginx | High-speed, high-traffic |
| Microsoft IIS | Windows Server environments |
| Tomcat | Java-based applications |

**Relevance:** Hospital portals and drug databases are hosted on web servers.

---

## Q8. Explain about drug information storage and retrieval. [5 Marks]

**Definition:** Systematic electronic recording of comprehensive drug data, enabling fast search and retrieval.

**Storage includes:** Name, category, dose, indications, contraindications, side effects, storage conditions.

**Retrieval Process:**
```
User searches drug name → system retrieves monograph → displays dosing/interactions/warnings
```

**Importance:** Enables instant access to accurate drug information at the point of dispensing.

---

## Q9. Explain the importance of TIMS (Text Information Management Systems). [5 Marks]

**Definition:** TIMS stores, organizes, searches, and retrieves large volumes of unstructured textual data.

**Importance:**
1. Manages vast medical literature efficiently
2. Enables fast keyword-based search
3. Supports evidence-based clinical decisions
4. Tracks updates to clinical guidelines

**Example:** PubMed functions as a large-scale TIMS.

---

## Q10. Explain the importance of Data flow diagram. [5 Marks]

**Definition:** A DFD graphically represents how data moves through a system.

**Importance:**
1. Visualizes system design before development
2. Identifies data sources, processes, and storage points
3. Detects inefficiencies early
4. Provides clear documentation for development teams

**Example:**
```
[Patient] → (Submit Prescription) → [Pharmacy System] → (Check Interactions) → [Pharmacist]
```

---

## Q11. How does patient monitoring system works? [5 Marks]

**Definition:** A **Patient Monitoring System** continuously or periodically tracks a patient's vital signs, lab values, and medication response to detect changes requiring clinical intervention.

**How It Works:**
```
Patient vitals/lab data collected (manually or via connected devices)
        ↓
Data entered/transmitted into monitoring system / EHR
        ↓
System compares values against normal reference ranges
        ↓
Abnormal values trigger alerts to doctor/pharmacist
        ↓
Clinical team adjusts treatment as needed
        ↓
Continuous tracking continues throughout patient care
```

**Examples:** ICU vital sign monitors linked to hospital systems; glucose monitoring for diabetic inpatients; CDSS-based medication monitoring alerts.

**Importance:** Enables early detection of deterioration or adverse drug reactions, improving patient safety outcomes.

---

**— End of 2023 Backlog Examination (April/May 2023) Answer Key —**
