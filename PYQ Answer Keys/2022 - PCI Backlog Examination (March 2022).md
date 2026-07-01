# B.Pharmacy II Semester (PCI) — Computer Applications in Pharmacy
# 2022 — PCI Backlog Examination (March 2022)
## Answer Key

---

> **Instructions reflected in this key:** PART–A — **10 Marks each** (Q2 and Q3 are split into two 5-mark sub-parts, (a) and (b)). PART–B — **5 Marks each**.

---

# PART – A  (10 Marks Each)

---

## Q1. Define number system. Explain the conversion process from binary to decimal and hexadecimal to binary. [10 Marks]

### 1. Definition (2 Marks)
A **number system** is a systematic method of representing numbers using a defined set of symbols (digits) and positional rules. Computers operate internally using **Binary** (base-2), while **Decimal** (base-10) is used for human interaction and **Hexadecimal** (base-16) is used as a compact representation of binary, especially in memory addressing and programming.

### 2. Binary to Decimal Conversion (4 Marks)

**Method:** Multiply each binary digit by 2 raised to its positional power (counting from the right, starting at 0), then sum all results.

**Worked Example 1:** Convert `1010` (binary) to decimal.
```
1010 = (1×2³) + (0×2²) + (1×2¹) + (0×2⁰)
     = 8 + 0 + 2 + 0
     = 10 (decimal)
```

**Worked Example 2:** Convert `110011` (binary) to decimal.
```
110011 = (1×2⁵) + (1×2⁴) + (0×2³) + (0×2²) + (1×2¹) + (1×2⁰)
       = 32 + 16 + 0 + 0 + 2 + 1
       = 51 (decimal)
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
∴ F2 (hexadecimal) = 11110010 (binary)
```

**Worked Example 2:** Convert `3A9` (hexadecimal) to binary.
```
3 = 0011
A = 1010
9 = 1001
∴ 3A9 (hexadecimal) = 001110101001 (binary)
```

### 4. Conclusion (Concluding note)
Binary-to-decimal conversion bridges machine-level representation to human-readable numbers, while hexadecimal-to-binary conversion demonstrates the compact 4-bit grouping that makes hexadecimal a practical shorthand for binary in technical computing contexts such as memory addresses and colour codes used in pharmacy software interfaces.

---

## Q2. *(a) Explain any 5 HTML tags with examples. (b) Explain the need of hospital and clinical pharmacy.* [10 Marks Total — 5 Marks Each]

### (a) Any 5 HTML Tags with Examples [5 Marks]

| # | Tag | Description | Example |
|---|-----|--------------|---------|
| 1 | `<h1>` | Defines the main heading of a page | `<h1>Drug Information</h1>` |
| 2 | `<p>` | Defines a paragraph of text | `<p>Paracetamol relieves fever.</p>` |
| 3 | `<table>` | Creates a table (with `<tr>`, `<td>`) | `<table><tr><td>Data</td></tr></table>` |
| 4 | `<a>` | Creates a hyperlink, using `href` attribute | `<a href="who.int">WHO</a>` |
| 5 | `<form>` | Creates an interactive input form | `<form><input type="text"></form>` |

**Combined Example:**
```html
<h1>Paracetamol</h1>
<p>An analgesic and antipyretic drug.</p>
<a href="https://who.int">More info</a>
```

---

### (b) Need of Hospital and Clinical Pharmacy [5 Marks]

**Definitions:**
- **Hospital Pharmacy:** The pharmacy department within a hospital responsible for procurement, storage, compounding, and dispensing of medicines.
- **Clinical Pharmacy:** A patient-care-focused practice where pharmacists work directly with the healthcare team to optimize medication therapy.

**Why They Are Needed:**

| Need | Hospital Pharmacy | Clinical Pharmacy |
|------|---------------------|---------------------|
| **Safety** | Ensures correct, quality-checked drug supply | Reviews therapy for interactions/contraindications |
| **Efficiency** | Centralized procurement and stock control | Direct bedside support reduces prescribing errors |
| **Cost Control** | Bulk purchasing, inventory optimization | Avoids unnecessary or duplicate therapy |
| **Patient Outcomes** | Ensures availability of needed medicines | Optimizes dosing for individual patient response |

**Conclusion:** Both functions are essential and complementary — hospital pharmacy ensures the right drug is available, while clinical pharmacy ensures it is used correctly for each individual patient.

---

## Q3. *(a) What is bioinformatics? Explain its applications. (b) Write note on CDS (Chromatographic Data Systems).* [10 Marks Total — 5 Marks Each]

### (a) Bioinformatics and Its Applications [5 Marks]

**Definition:** **Bioinformatics** is an interdisciplinary field combining biology, computer science, and statistics to collect, store, analyze, and interpret biological data.

**Applications:**

| Application | Description |
|-------------|--------------|
| **Drug Target Identification** | Analyzing genomic data to find disease-related proteins |
| **Protein Structure Prediction** | Tools like AlphaFold predict 3D protein structures |
| **Sequence Alignment** | Comparing DNA/protein sequences for similarities |
| **Personalized Medicine** | Tailoring drug therapy using genetic data |
| **Drug Repurposing** | Finding new uses for existing approved drugs |

**Importance:** Reduces time and cost of drug discovery through computational pre-screening.

---

### (b) CDS (Chromatographic Data Systems) [5 Marks]

**Definition:** A **CDS** is software used to collect, process, and store data generated by chromatographic instruments (HPLC, GC) used in pharmaceutical quality control.

**Workflow:**
```
Sample injected → instrument separates components, detector signals
        → CDS captures chromatogram → identifies peaks, retention time, area
        → compares against standards → generates validated report
```

**Key Functions:** Peak integration, calibration, audit trail (essential for GxP regulatory compliance).

**Importance:** Verifies drug purity and ensures every batch meets required quality specifications before release.

---
---

# PART – B  (5 Marks Each)

---

## Q4. Explain the concept of One's complement and Two's complements. [5 Marks]

**Definition:** Methods used by computers to represent negative binary numbers, enabling subtraction via addition circuitry.

**One's Complement:** Invert every bit (0→1, 1→0).

**Example:** One's Complement of `1010` = `0101`

**Two's Complement:** One's Complement + 1.

**Example:**
```
One's Complement of 1010: 0101
Add 1:                  + 0001
                        ------
Two's Complement:         0110
```

**Importance:** The standard method computers use to represent negative numbers and perform subtraction.

---

## Q5. Write about syntax rules for Extensible Mark-up Language declaration. [5 Marks]

**Definition:** **XML (Extensible Markup Language)** requires "well-formed" syntax — strict rules that must be followed for the document to be valid.

**Syntax Rules:**
1. Every opening tag must have a matching closing tag
2. Tags must be properly nested (no overlapping)
3. XML tags are case-sensitive
4. Attribute values must always be quoted
5. There must be exactly one root element
6. Special characters (`<`, `>`, `&`) must be escaped (`&lt;`, `&gt;`, `&amp;`)

**XML Declaration Example:**
```xml
<?xml version="1.0" encoding="UTF-8"?>
<patient>
    <name>Rahul Sharma</name>
</patient>
```

The `<?xml version="1.0" encoding="UTF-8"?>` line, if present, must be the very first line of the document.

---

## Q6. Write a note on web server and server products. [5 Marks]

**Definition:** A **Web Server** stores, processes, and delivers web pages upon request via HTTP/HTTPS.

**Common Server Products:**

| Server | Notes |
|--------|-------|
| Apache HTTP Server | Free, open-source |
| Nginx | High-speed, high-traffic |
| Microsoft IIS | Windows Server environments |
| Tomcat | Java-based applications |

**Relevance:** Hospital portals and drug databases are hosted on web servers.

---

## Q7. Explain the application of computers in Pharmacy. [5 Marks]

**Applications:**

| Domain | Application |
|--------|-------------|
| Clinical | Drug interaction checking, e-prescribing |
| Dispensing | Automated cabinets, barcode verification |
| Inventory | Stock tracking, expiry alerts |
| Records | EHR maintenance |
| Research | Bioinformatics-based drug discovery |

**Conclusion:** Computers improve accuracy, safety, and efficiency across the medication-use process.

---

## Q8. Write about Objective of Bioinformatics. [5 Marks]

**Objectives:**
1. Organize biological data into accessible databases
2. Develop analysis tools/algorithms
3. Interpret data for biological insight
4. Support drug discovery through target identification
5. Enable personalized medicine via genomics

---

## Q9. Explain the importance of TIMS (Text Information Management Systems). [5 Marks]

**Definition:** TIMS stores, organizes, searches, and retrieves large volumes of unstructured textual data.

**Importance:**
1. Manages vast medical literature efficiently
2. Enables fast keyword-based search across documents
3. Supports evidence-based decision-making
4. Tracks updates to clinical guidelines via version control

**Example:** PubMed acts as a large-scale TIMS for biomedical research.

---

## Q10. Explain the importance of Data flow diagram. [5 Marks]

**Definition:** A **DFD** graphically represents how data moves through a system.

**Importance:**
1. Visualizes system design before development
2. Identifies all data sources, processes, and storage points
3. Helps detect inefficiencies/redundancies early
4. Provides clear documentation for developers and stakeholders

**Example:**
```
[Patient] → (Submit Prescription) → [Pharmacy System] → (Check Interactions) → [Pharmacist]
```

---

## Q11. Explain the process of Medication monitoring. [5 Marks]

**Definition:** The ongoing tracking of a patient's response to prescribed medication to ensure efficacy and safety.

**Process:**
```
Drug prescribed → response/lab parameters tracked
        → reviewed by pharmacist/doctor → dose adjusted if needed → monitoring continues
```

**Tools:** EHR, CDSS alerts, LIMS-based lab monitoring.

**Importance:** Detects therapeutic failure or toxicity early, improving patient safety.

---

**— End of 2022 PCI Backlog Examination (March 2022) Answer Key —**
