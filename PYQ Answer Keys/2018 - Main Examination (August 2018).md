# B.Pharmacy II Semester (PCI) — Computer Applications in Pharmacy
# 2018 — Main Examination (August 2018)
## Answer Key

---

> **Instructions reflected in this key:** PART–A: Answer any **two** questions (out of 3) — **10 Marks each**. PART–B: Answer any **six** questions (out of 8) — **5 Marks each**.

---

# PART – A  (10 Marks Each)
*(Answer any two)*

---

## Q1. What is a number system? Convert binary number into decimal, octal, hexadecimal and vice versa with example. [10 Marks]

### 1. Definition (1 Mark)
A **number system** is a systematic method of representing numbers using a defined set of symbols (digits) and positional rules. Computers internally operate using the **Binary Number System** (base-2), while humans commonly use **Decimal** (base-10). **Octal** (base-8) and **Hexadecimal** (base-16) are intermediate systems used to represent binary data more compactly for human readability.

### 2. The Four Number Systems Compared (2 Marks)

| Number System | Base | Digits Used | Example |
|---------------|------|-------------|---------|
| Binary | 2 | 0, 1 | 1010 |
| Decimal | 10 | 0–9 | 245 |
| Octal | 8 | 0–7 | 372 |
| Hexadecimal | 16 | 0–9, A–F | F2 |

**Why computers use binary:** Digital circuits have only two stable electrical states — ON and OFF — which map naturally to the digits 1 and 0. This makes binary the only number system computer hardware can directly represent; all other systems (decimal, octal, hex) are conversions done for human convenience.

### 3. Binary ↔ Decimal Conversion (2 Marks)

**Binary to Decimal — Method:** Multiply each binary digit by 2 raised to its positional power (counting from the right, starting at 0), then sum all the results.

**Worked Example:** Convert `1010` (binary) to decimal.
```
1010 = (1 × 2³) + (0 × 2²) + (1 × 2¹) + (0 × 2⁰)
     = (1 × 8) + (0 × 4) + (1 × 2) + (0 × 1)
     = 8 + 0 + 2 + 0
     = 10 (decimal)
```

**Decimal to Binary — Method:** Repeatedly divide the decimal number by 2, recording the remainder at each step, until the quotient becomes 0. Read the remainders from bottom to top.

**Worked Example:** Convert `13` (decimal) to binary.
```
13 ÷ 2 = 6   remainder 1
 6 ÷ 2 = 3   remainder 0
 3 ÷ 2 = 1   remainder 1
 1 ÷ 2 = 0   remainder 1

Reading remainders bottom→top: 1101
∴ 13 (decimal) = 1101 (binary)
```

### 4. Binary ↔ Octal Conversion (2 Marks)

**Binary to Octal — Method:** Group the binary digits into sets of **3** starting from the right; convert each group to its octal digit.

**Worked Example:** Convert `101110` (binary) to octal.
```
101110 → grouped in 3s: 101 | 110
101 = 5
110 = 6
∴ 101110 (binary) = 56 (octal)
```

**Octal to Binary — Method:** Convert each octal digit individually into its 3-bit binary equivalent.

**Worked Example:** Convert `56` (octal) to binary.
```
5 = 101
6 = 110
∴ 56 (octal) = 101110 (binary)
```

### 5. Binary ↔ Hexadecimal Conversion (2 Marks)

**Binary to Hexadecimal — Method:** Group binary digits into sets of **4** from the right; convert each group to its hex digit.

**Worked Example:** Convert `11110010` (binary) to hexadecimal.
```
11110010 → grouped in 4s: 1111 | 0010
1111 = F
0010 = 2
∴ 11110010 (binary) = F2 (hexadecimal)
```

**Hexadecimal to Binary — Method:** Convert each hex digit individually into its 4-bit binary equivalent.

**Worked Example:** Convert `F2` (hexadecimal) to binary.
```
F = 1111
2 = 0010
∴ F2 (hexadecimal) = 11110010 (binary)
```

### 6. Summary Table of All Conversions Shown (0.5 Mark)

| From → To | Example Input | Example Output |
|-----------|----------------|------------------|
| Binary → Decimal | 1010 | 10 |
| Decimal → Binary | 13 | 1101 |
| Binary → Octal | 101110 | 56 |
| Octal → Binary | 56 | 101110 |
| Binary → Hexadecimal | 11110010 | F2 |
| Hexadecimal → Binary | F2 | 11110010 |

### 7. Conclusion (0.5 Mark)
Number systems form the foundation of all digital computing. Pharmacy software, barcode systems, and digital health records all rely on binary-based data storage internally, even though pharmacists interact with familiar decimal values on screen.

---

## Q2. Describe any 10 HTML tags. [10 Marks]

### 1. Introduction (1 Mark)
**HTML (HyperText Markup Language)** is the standard markup language used to create the structure of web pages. It uses **tags** — keywords enclosed in angle brackets — to define and label different elements of a page, which the browser then renders visually.

### 2. Ten HTML Tags Explained (8 Marks — 0.8 Mark per tag)

| # | Tag | Description | Example |
|---|-----|--------------|---------|
| 1 | `<html>` | The root element; wraps the entire HTML document | `<html>...</html>` |
| 2 | `<head>` | Contains metadata (title, character set) — not visible on the page | `<head><title>Pharmacy Portal</title></head>` |
| 3 | `<body>` | Contains all visible content of the webpage | `<body>...</body>` |
| 4 | `<h1>` to `<h6>` | Defines headings, `<h1>` largest to `<h6>` smallest | `<h1>Drug Information</h1>` |
| 5 | `<p>` | Defines a paragraph of text | `<p>Paracetamol is an analgesic.</p>` |
| 6 | `<a>` | Creates a hyperlink to another page or resource, using the `href` attribute | `<a href="https://who.int">WHO</a>` |
| 7 | `<img>` | Embeds an image into the page; `alt` provides accessible text | `<img src="tablet.jpg" alt="Tablet">` |
| 8 | `<table>` | Creates a table; used together with `<tr>` (row), `<th>` (header), `<td>` (cell) | `<table><tr><td>Data</td></tr></table>` |
| 9 | `<ul>` / `<li>` | Creates an unordered (bulleted) list, with each item in `<li>` | `<ul><li>Fever</li><li>Pain</li></ul>` |
| 10 | `<form>` | Creates an interactive form to collect user input, using elements like `<input>` | `<form><input type="text"></form>` |

### 3. Combined Worked Example (0.5 Mark)
```html
<html>
<head>
    <title>Drug Information</title>
</head>
<body>
    <h1>Paracetamol</h1>
    <p>Used for fever and mild pain relief.</p>
    <ul>
        <li>Fever</li>
        <li>Headache</li>
    </ul>
    <a href="https://who.int">Learn more</a>
</body>
</html>
```

### 4. Conclusion (0.5 Mark)
These tags form the basic building blocks of any webpage. In pharmacy informatics, such tags are used to build drug information portals, patient registration pages, and hospital websites.

---

## Q3. Write about electronic prescribing and discharge system. [10 Marks]

### 1. Definitions (1 Mark)
**Electronic Prescribing (e-Prescribing)** is the computer-based generation, transmission, and filling of a medical prescription, replacing traditional handwritten paper prescriptions. An **Electronic Discharge System** is the digital process of generating and transmitting a patient's discharge summary, medication list, and follow-up instructions at the end of a hospital stay.

### 2. Electronic Prescribing System — How It Works (3 Marks)

```
Doctor examines patient
        ↓
Doctor enters prescription into e-Prescribing software
        ↓
System automatically checks: drug interactions, allergies, dosage limits
        ↓
Prescription transmitted electronically to pharmacy
        ↓
Pharmacist reviews, verifies, and dispenses
        ↓
Record stored in patient's Electronic Health Record (EHR)
```

### 3. Advantages of e-Prescribing (1.5 Marks)
1. Eliminates illegible handwriting errors
2. Automatic drug interaction and allergy checking
3. Faster prescription processing
4. Reduces duplicate or fraudulent prescriptions
5. Maintains a complete, searchable medication history

### 4. Electronic Discharge System — How It Works (2 Marks)
When a patient is discharged from hospital, the system automatically compiles:
- Final diagnosis
- Treatment given during admission
- Discharge medications, with dosage and duration
- Follow-up appointment details
- Instructions for home care

This discharge summary is generated digitally and can be:
- Printed for the patient
- Sent electronically to the patient's regular doctor/pharmacy
- Stored permanently in the hospital's EHR system

### 5. Advantages of Electronic Discharge Systems (1.5 Marks)
1. Reduces transcription errors in discharge instructions
2. Ensures continuity of care between hospital and home/local pharmacy
3. Speeds up the discharge process, freeing hospital beds faster
4. Provides a permanent digital record for future reference

### 6. Conclusion (1 Mark)
Both systems are key components of modern Hospital Information Systems (HIS), improving patient safety, reducing medication errors, and streamlining hospital workflows — directly relevant to a pharmacist's role in medication safety.

---
---

# PART – B  (5 Marks Each)
*(Answer any six)*

---

## Q4. Write a note on Web servers and server products. [5 Marks]

**Definition:** A **Web Server** is software (and the hardware it runs on) that stores, processes, and delivers web pages to users upon request, using the HTTP/HTTPS protocol.

**How it works:**
```
Browser sends HTTP Request → Web Server processes & fetches data → sends HTTP Response (HTML page) → Browser displays page
```

**Common Web Server Products:**

| Server Product | Developer | Notes |
|------------------|-----------|-------|
| **Apache HTTP Server** | Apache Software Foundation | Free, open-source, most widely used historically |
| **Nginx** | Nginx Inc. | Known for speed and handling high traffic |
| **Microsoft IIS** | Microsoft | Used with Windows Server environments |
| **Tomcat** | Apache Software Foundation | Specifically for Java-based web applications |

**Relevance to Pharmacy:** Hospital patient portals, online pharmacy ordering systems, and drug information databases are all hosted on web servers, allowing patients and healthcare staff to access them from any browser, anywhere.

---

## Q5. What is database? Explain about MS Access database. [5 Marks]

**Definition:** A **database** is an organized collection of related data, stored electronically, that can be easily accessed, managed, and updated.

**MS Access:** A desktop Relational Database Management System (RDBMS) that combines the database engine with a graphical interface, allowing users to build databases without extensive coding.

**Components of MS Access:**

| Component | Function |
|-----------|----------|
| **Tables** | Store the actual data in rows (records) and columns (fields) |
| **Queries** | Retrieve specific data from tables based on conditions |
| **Forms** | Provide a user-friendly interface for data entry |
| **Reports** | Present data in a formatted, printable layout |

**Example:** A pharmacy creates a `Patients` table with fields PatientID, Name, Age, BloodGroup. Staff use a Form to enter new patients; a Query retrieves all patients over 60; a Report prints a formatted patient list.

---

## Q6. Write about diagnostic and lab-diagnostic system. [5 Marks]

**Definition:** A **Diagnostic System** assists healthcare professionals in identifying diseases based on patient symptoms and test results. A **Lab-Diagnostic System** specifically manages the processing, tracking, and reporting of laboratory test samples and results.

**How it works:**
```
Sample collected → labelled with barcode → entered into Lab system
        → automated analyser generates results → validated by technician
        → transmitted electronically to doctor/EHR
```

**Key Features:**
1. Barcode-based sample tracking to prevent mix-ups
2. Automatic flagging of abnormal results (e.g., high glucose)
3. Integration with hospital EHR for instant doctor access

**Importance in Pharmacy:** Pharmacists use diagnostic data (e.g., kidney function tests) to adjust drug dosages safely.

---

## Q7. Write a note on data flow diagrams. [5 Marks]

**Definition:** A **Data Flow Diagram (DFD)** is a graphical representation showing how data moves through a system — illustrating processes, data stores, external entities, and the flow of data between them.

**Components:**

| Symbol | Represents |
|--------|-----------|
| Circle/Oval | A **Process** that transforms data |
| Rectangle | An **External Entity** (e.g., a patient) |
| Open rectangle | A **Data Store** (e.g., a database) |
| Arrow | A **Data Flow** — direction data moves |

**Example — Pharmacy Prescription System:**
```
[Patient] → (Submit Prescription) → [Pharmacy System] → (Check Interactions)
        → [Drug Database] → (Verify) → [Pharmacist] → (Dispense) → [Patient]
```

**Importance:** DFDs help pharmacy IT teams visualize and plan how patient data and prescriptions move through software before it is built.

---

## Q8. Explain the concept of chromatographic data analysis. [5 Marks]

**Definition:** **Chromatographic Data Analysis** refers to the use of specialized software — **Chromatographic Data Systems (CDS)** — to collect, process, analyze, and store data from chromatographic instruments such as HPLC and GC.

**How it works:**
```
Sample injected → instrument separates components, detector signals
        → CDS captures chromatogram → identifies peaks, retention time, area
        → compares against standards → generates validated report
```

**Key Functions:**
1. **Peak Integration** — calculating area under each peak
2. **Calibration** — comparing against known standard concentrations
3. **Audit Trail** — recording every action on the data (GxP compliance)

**Importance:** Essential in pharmaceutical quality control — verifying drug purity before release to patients.

---

## Q9. Discuss about applications of computers in pharmacy. [5 Marks]

**Introduction:** Computers have transformed pharmacy practice across clinical, administrative, research, and regulatory domains.

**Major Applications:**

| Domain | Application |
|--------|-------------|
| **Clinical** | Drug interaction checking, dosage calculation, e-prescribing |
| **Dispensing** | Automated dispensing cabinets, barcode verification |
| **Inventory** | Stock tracking, expiry alerts, automatic reordering |
| **Patient Records** | Electronic Health Records (EHR) |
| **Research** | Drug discovery via bioinformatics |
| **Quality Control** | CDS for testing drug purity |
| **Billing** | Automated invoicing, insurance claims |

**Conclusion:** Computer applications increase accuracy, safety, and efficiency throughout the entire medication-use process.

---

## Q10. Illustrate text information management system. [5 Marks]

**Definition:** A **Text Information Management System (TIMS)** is a software system designed to store, organize, search, and retrieve large volumes of unstructured or semi-structured textual data — such as drug literature and clinical notes.

**How it works:**
```
Text documents → indexed by TIMS (keywords, categories tagged)
        → user submits search query → TIMS retrieves & ranks relevant documents
        → user views/extracts information
```

**Key Features:**
1. Full-text search
2. Indexing for fast retrieval
3. Categorization by topic

**Example:** **PubMed** functions as a large-scale TIMS — pharmacists search millions of articles by keyword and retrieve relevant published studies instantly.

---

## Q11. Write about XML. [5 Marks]

**Definition:** **XML (eXtensible Markup Language)** is a markup language designed to store and transport data in a structured, self-describing format. Unlike HTML (which displays data), XML's purpose is to carry data between systems.

**Key Features:**
1. User-defined tags (unlike HTML's fixed tag set)
2. Platform and software independent
3. Strict syntax rules ("well-formed" requirement)

**Example:**
```xml
<?xml version="1.0" encoding="UTF-8"?>
<patient>
    <name>Rahul Sharma</name>
    <age>45</age>
    <drug>Metformin</drug>
</patient>
```

**Well-Formedness Rules:** Every tag closed; proper nesting; case-sensitive; quoted attribute values; exactly one root element.

**Importance:** XML underlies the **HL7** standard for healthcare data exchange, letting hospital systems share patient records in a universal format.

---

**— End of 2018 Main Examination Answer Key —**
